# Neovim via Nix

Neovim config + packages.

Based on [ethanniser/nvim.nix](https://github.com/ethanniser/nvim.nix). The nix part is originally based on the template from [kickstart-nix.nvim](https://github.com/nix-community/kickstart-nix.nvim). With additional inspiration from [pierrot-lc/nvim-nix](https://github.com/pierrot-lc/nvim-nix).

The actually config itself is based on [kickstart.nvim](https://github.com/nvim-lua/kickstart.nvim).

## Usage

Add the flake to your inputs, apply the overlay, and include the `configured-nvim` package.


## Implict dependencies

Many LSPs, formatters and other tools which are potentially used by the plugins in this configuration are not packaged in this flake.

This makes sense because an editor configuration should not describe how to get or build those dependencies, it just expects them to be available.

So you can install them globally, or add them to a per-project flake.

If you want to view all of the potential dependencies, you can look at the [packages.nix](./nix/packages.nix) file. There is defined a list of packages that could be used by the configuration. These are also exposed as their own package in the overlay: `configured-nvim-deps`.
