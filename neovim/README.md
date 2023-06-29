## Add Hoon language support to neovim

### Using packer

Add this to your packer `startup` function in your `init.config` file. (default location in linux is `~/.config/nvim/init.lua`)

```lua
require('packer').startup(function(use)
	use {
        	'nvim-treesitter/nvim-treesitter',
        	run = function()
		    local ts_update = require('nvim-treesitter.install').update({ with_sync = true })
		    ts_update()
		end,	
    	}
end)
```

and then add this to your `init.config` to enable treesitter highlighting and auto install the hoon tree-sitter parser.

```lua
require'nvim-treesitter.configs'.setup {
	auto_install = true,
	ensure_installed = { "hoon" },
	highlight = {
		enable = true,
		additional_vim_regex_highlighting = false,
	},
}
```
