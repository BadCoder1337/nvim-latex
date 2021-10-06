# NVIM-LaTeX

A collection of LaTeX snippets and compilation actions. Built with [TypeScriptToLua](https://typescripttolua.github.io/) scaffolded from [equals03/tstoluaplugin.nvim](https://github.com/equals03/tstoluaplugin.nvim).

Why TypeScript? I was supposed to create a `nvim` plugin, but I couldn't break up with cozy JS/TS syntax & tooling.

## Installation

Using [packer.nvim](https://github.com/wbthomason/packer.nvim)

```lua
use {
  'BadCoder1337/nvim-latex',
  requires = {{'nvim-lua/plenary.nvim'}}
}
```

Using [vim-plug](https://github.com/junegunn/vim-plug)

```viml
Plug 'nvim-lua/plenary.nvim'
Plug 'BadCoder1337/nvim-latex'
```

Open `nvim`.

The built plugin is in the repo so that it can be run right after cloning.

## Usage

Try the command `:LaTeX dump 1 2 3 4`
to see if `tstoluaplugin` is installed correctly.

You should see: `{ 1, 2, 3, 4 }` printed. So much wow.

To see the other commands available just use your standard completion and you should see a few more options pop-up.

It should have a few "builtin" commands and two settings that will be printed to the console.

Commands available:  
`shell`
this will invoke a shell application and print its stdout. Additionally, it will also print the cmd and args used.

```vimL
:LaTeX shell ls -al
```

`dump`  
this will print out whatever arguments are supplied.

```vimL
:LaTeX dump 1 2 three four
```

`not_implemented`  
this will just use the `nivm` api to print a little error message saying "not implemented".

```vimL
:LaTeX not_implemented
```

`config_value_(one|two)`  
this will print the value of the config entry. You can override them using the `.setup()` method (below).

```vimL
:LaTeX config_value_one
```

## Configuration

```lua
require('tstoluaplugin').setup{
  defaults = {
      config_value_two = 42
  }
}
```

You can verify this has been applied by printing the value using the method outlined above.

## Modifying the plugin

```bash
cd ~/development/tstoluaplugin.nvim
npm install
```

Create new/modify any of the files in `./typescript`.
Use `npm run` to run a build step.

```bash
npm run build
```

... will transpile the `.ts` to the `./lua` directory.

```bash
npm run dev
```

... will do the same as above but watching for changes.

```bash
npm run clean
```

... will `rm -rf` the `./lua` directory if you want to be sure of a fresh start.

## Why did you bother?

Because it seemed like fun.

## Something to keep in mind

I am neither an expert in `TypeScript` nor `Lua`. I just enjoy tinkering and exploring the patterns/implementations that these languages make available. I'm aware _everything_ in this repository could be done better.

It seems to work though, so thats a plus.

## Contributing

Even though I'm not sure why... Sure.
Just open a pull request.
