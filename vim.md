## Configuração do Editor VIM

Instalação do [`vim-plug`](https://github.com/junegunn/vim-plug) para gerenciar os plugins.
```bash
curl -fLo ~/.vim/autoload/plug.vim --create-dirs https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```

No arquivo de configuração `~/.vimrc`.
```
call plug#begin()

Plug 'scrooloose/nerdtree'
Plug 'vim-airline/vim-airline'
Plug 'vim-airline/vim-airline-themes'
Plug 'stephpy/vim-yaml'
Plug 'yggdroot/indentline'
Plug 'plasticboy/vim-markdown'
Plug 'dracula/vim',{'as':'dracula'}
Plug 'tomtom/tcomment_vim'
Plug 'hashivim/vim-terraform'
" https://vimawesome.com/plugin/vim-gitgutter
Plug 'airblade/vim-gitgutter'
" https://github.com/voldikss/vim-floaterm
Plug 'voldikss/vim-floaterm'

call plug#end()

" Keybind NERDTree
map <F2> :NERDTreeToggle<CR>

" VIM Airline Theme
let g:airline_theme='papercolor'

" Indentiline
let g:indentLine_char = '.'
let g:indentLine_enabled = 0

" https://vimawesome.com/plugin/markdown-syntax
" Disable Folding
let g:vim_markdown_folding_disabled = 1

syntax on
colorscheme dracula
set visualbell

" Floaterm Configuration
" Configuration example
let g:floaterm_keymap_new    = '<F6>'
let g:floaterm_keymap_kill   = '<F7>'
let g:floaterm_keymap_prev   = '<F8>'
let g:floaterm_keymap_next   = '<F9>'
let g:floaterm_keymap_toggle = '<F10>'

let g:floaterm_width = 0.9
let g:floaterm_height = 0.9

syntax on
colorscheme dracula
```
Reload `~/.vimrc` and `:PlugInstall` to install plugins.
