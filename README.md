# TIL

## Table of Contents

1. [Elixir](#elixir)
2. [Phoenix](#phoenix)

### Elixir

#### Shell history

In order to enable shell history add this to your ~/.bash_rc (or zsh or whatever u use)

```
export ERL_AFLAGS="-kernel shell_history enabled"
```

or for fish
```
set -x ERL_AFLAGS "-kernel shell_history enabled"
```

### Phoenix

#### App module name

You can supply various parameters to mix phx.new, one of them is `--module` which allows you to modify how your app main module will be named. So if you have not straight mapping from underscore to camelcase you can supply your own.

```
mix phx.new nottrivial_app --module NotTrivialApp
```
