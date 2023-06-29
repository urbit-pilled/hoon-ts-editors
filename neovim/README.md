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
		config = function()
			local parser_config = require('nvim-treesitter.parsers').get_parser_configs()
			parser_config.hoon = {
				install_info = {
					url = "https://github.com/urbit-pilled/tree-sitter-hoon.git", -- local path or git repo
					files = {"src/parser.c"},
					generate_requires_npm = false,
					requires_generate_from_grammar = false,
				},
				filetype = "hoon",
			}
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

### Using other package managers

Follow the instructions from [here](https://github.com/nvim-treesitter/nvim-treesitter#adding-parsers) and use the [tree-sitter-hoon](https://github.com/urbit-pilled/tree-sitter-hoon) repository.