# vim-ripgrep

Use `rg` as you would in your terminal, but in Vim. The results are passed into
the quickfix list.

By default `:Rg` searches in the current working directory; you can get your
current working directory by running `:pwd` in Vim.

netrw users with the
`g:netrw_keepdir` flag set to `0`, your working directory changes as you browse
around in netrw so be prerared that searches will happen in your working
directory which may not always be what you want.

## Usage

```
- Simple standard rg search in the current working directory
:Rg cat

- Case incensitive search
:Rg -i cat
:Rg cat -i

- Multiline search with the `.` character including newlines
:Rg --multiline --multiline-dotall '<html>.*</html>'
```

The word under cursor is searched if no argument is passed to `:Rg`.

## Installation

To install using [vim-plug](https://github.com/junegunn/vim-plug):

```
Plug 'mi544/vim-ripgrep'
```

To install using [dein](https://github.com/Shougo/dein.vim):

```
call dein#add('mi544/vim-ripgrep')
```

## Configuration

| Setting              | Default                   | Details
| ---------------------|---------------------------|----------
| g:rg_binary          | rg                        | path to rg
| g:rg_format          | %f:%l:%c:%m               | value of grepformat 
| g:rg_command         | g:rg_binary --vimgrep     | search command
| g:rg_highlight       | false                     | true if you want matches highlighted
| g:rg_derive_root     | false                     | true if you want to find project root from cwd
| g:rg_root_types      | ['.git']                  | list of files/dir found in project root
| g:rg_window_location | botright                  | quickfix window location
    
## Misc

Show root search dir

```
:RgRoot
```
