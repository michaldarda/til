# TIL

## Table of Contents

1. [Clojure](#clojure)
2. [Elixir](#elixir)
3. [Phoenix](#phoenix)

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

### Phoenix

#### App module name

You can supply various parameters to mix phx.new, one of them is `--module` which allows you to modify how your app's main module will be named. So if you have not straight mapping from underscore to camelcase you can supply your own.

```bash
mix phx.new nottrivial_app --module NotTrivialApp
```
