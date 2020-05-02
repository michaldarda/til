# TIL

## Table of Contents

1. [Arch Linux](#arch-linux)
2. [Clojure](#clojure)
3. [Ecto](#ecto)
4. [Elixir](#elixir)
5. [Phoenix](#phoenix)

### Arch Linux

#### List packages installed from AUR

```bash
pacman -Qm
```

### Regain disk space

Cleanup pacman cache
```
sudo pacman -Scc
```

Cleanup yay AUR cache

```
yay -Scc
```

Remove `~/.cache`.

### Clojure

#### Collections are functions

In Clojure collections are functions, so you can just call your map with a given key

```clojure
user=> ({:a 1 :b 3} :b)
3
```

Your vector to take value at given index

```clojure
user=> ([1 2 3 4 5] 3)
4
```

Or your set to verify if value is its member

```clojure
user=> (#{1 2 3} 3)
3
user=> (#{1 2 3} 0)
nil
```

### Ecto

#### `insert/2` return values

When you call `Ecto.Repo.insert/2` you can't expect to return either `{:ok, struct}` or `{:error, error}`. In case of connection connection failures/non existing table/DB errors Ecto will raise an exception.

From Ecto docs:

It returns {:ok, struct} if the struct has been successfully inserted or {:error, changeset} **if there was a validation or a known constraint error**.

### Elixir

#### Shell history

In order to enable shell history add this to your `~/.bashrc` (or `~/.zshrc` or whatever you use)

```bash
export ERL_AFLAGS="-kernel shell_history enabled"
```

or for fish
```fish
set -x ERL_AFLAGS "-kernel shell_history enabled"
```

#### Pattern match on binaries

You can pattern match on binaries using this syntax

```elixir
iex(2)> <<s::binary-size(6), " is ", rest::binary>> = "Elixir is so cool"
"Elixir is so cool"
iex(3)> s
"Elixir"
iex(4)> rest
"so cool"
```

This has some limitations like only the last binary can be without size, but has some cool things like binary-size being variable.

```elixir
iex(1)> n = 6
iex(2)> <<s::binary-size(n), " is ", rest::binary>> = "Elixir is so cool"
```

More on that can be found in [Elixir's special forms docs](https://hexdocs.pm/elixir/Kernel.SpecialForms.html#%3C%3C%3E%3E/1)

### Phoenix

#### App module name

You can supply various parameters to mix phx.new, one of them is `--module` which allows you to modify how your app's main module will be named. So if you have not straight mapping from underscore to camelcase you can supply your own.

```bash
mix phx.new nottrivial_app --module NotTrivialApp
```
