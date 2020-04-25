# TIL

## Elixir

In order to enable shell history add this to your ~/.bash_rc (or zsh or whatever u use)

```
export ERL_AFLAGS="-kernel shell_history enabled"
```

or for fish
```
set -x ERL_AFLAGS "-kernel shell_history enabled"
```
