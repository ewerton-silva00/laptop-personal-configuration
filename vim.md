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
```
Reload `~/.vimrc` and `:PlugInstall` to install plugins.
