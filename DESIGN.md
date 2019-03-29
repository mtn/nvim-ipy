# Design
> i.nvim -- Interactive programming fully inside neovim

Seeing the results of your computation eases cognitive load while programming.
This the idea behind Jupyter/IPython/interactive computing, that I'm trying to
integrate more deeply into my editor.

## Implementation

To make incremental computation work, (partial) results will be rendered as [EOL
virtual text](https://github.com/neovim/neovim/pull/8180). For full output,
there'll be an internal map between line numbers and computed results.

## Problems to Solve

- Line numbers change -> need to update the computation map
  - Solution: computation map :: nvim namespace -> result

## Eventual Problems

- Cell invalidation tracking
- Need to figure out how to get itermplot to work with neovim terminal
  - Not working on right now, because this won't work with tmux anyways
