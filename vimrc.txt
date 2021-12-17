set nocp
if has("autocmd")
  au VimEnter,InsertLeave * silent execute '!echo -ne "\e[2 q"' | redraw!
  au InsertEnter,InsertChange *
\ if v:insertmode == 'i' |
\   silent execute '!echo -ne "\e[6 q"' | redraw! |
\ elseif v:insertmode == 'r' |
\   silent execute '!echo -ne "\e[4 q"' | redraw! |
\ endif
au VimLeave * silent execute '!echo -ne "\e[ q"' | redraw!
endif

"let g:user_emmet_leader_key = '<tab>'
let g:user_emmet_leader_key = '<C-W>'
let g:user_emmet_install_global = 0
let @p='A,j0'
let @q='i''lxA'',j0'
command Virgula 10000@p
command Aspas 10000@q
command! F :execute '%!python -c "import json,sys,collections,re; sys.stdout.write(re.sub(r\"\\\u[0-9a-f]{4}\", lambda m:m.group().decode(\"unicode_escape\").encode(\"utf-8\"),json.dumps(json.load(sys.stdin, object_pairs_hook=collections.OrderedDict), indent=2)))"'
autocmd FileType htmldjango,html,css EmmetInstall
syntax on
set background=dark
"colorscheme pablo
set laststatus=2
set relativenumber
set nocompatible              " be iMproved, required
command! W :w
command! Q :q
noremap j gj
noremap k gk
noremap M 1000@q
noremap m 1000@p
map <C-up> :tabr<cr>
map <C-down> :tabl<cr>
map <C-left> :tabp<cr>
map <C-right> :tabn<cr>
set tabstop=2
set shiftwidth=2
set softtabstop=2 expandtab
set noshowmode
set hlsearch
set incsearch
set ignorecase
filetype off                  " required
set showcmd
set number
nmap <F6> :NERDTreeToggle<CR>
" set the runtime path to include Vundle and initialize
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()
" alternatively, pass a path where Vundle should install plugins
"call vundle#begin('~/some/path/here')

" let Vundle manage Vundle, required
Plugin 'VundleVim/Vundle.vim'
Plugin 'MarcWeber/vim-addon-mw-utils'
Plugin 'tomtom/tlib_vim'
Plugin 'vim-scripts/upAndDown'
Plugin 'garbas/vim-snipmate'
Plugin 'jiangmiao/auto-pairs' 
Plugin 'itchyny/lightline.vim'
Plugin 'leafgarland/typescript-vim'
Plugin 'ayu-theme/ayu-vim'
Plugin 'mattn/emmet-vim'
Plugin 'rafi/awesome-vim-colorschemes'
Plugin 'terryma/vim-multiple-cursors'
" The following are examples of different formats supported.
" Keep Plugin commands between vundle#begin/end.
" plugin on GitHub repo
Plugin 'tpope/vim-fugitive'
Plugin 'scrooloose/nerdtree'
Plugin 'morhetz/gruvbox'
Plugin 'elixir-editors/vim-elixir'
" plugin from http://vim-scripts.org/vim/scripts.html
" Plugin 'L9'
" Git plugin not hosted on GitHub
Plugin 'git://git.wincent.com/command-t.git'
" git repos on your local machine (i.e. when working on your own plugin)
" The sparkup vim script is in a subdirectory of this repo called vim.
" Pass the path to set the runtimepath properly.
Plugin 'rstacruz/sparkup', {'rtp': 'vim/'}
Plugin 'sonph/onehalf', {'rtp': 'vim/'}
Plugin 'dart-lang/dart-vim-plugin'
Plugin 'thosakwe/vim-flutter'
Plugin 'OmniSharp/omnisharp-vim'
" Install L9 and avoid a Naming conflict if you've already installed a
" different version somewhere else.
" Plugin 'ascenator/L9', {'name': 'newL9'}

" All of your Plugins must be added before the following line
call vundle#end()            " required
colorscheme afterglow
filetype plugin indent on    " required
" To ignore plugin indent changes, instead use:
"filetype plugin on
"
" Brief help
" :PluginList       - lists configured plugins
" :PluginInstall    - installs plugins; append `!` to update or just :PluginUpdate
" :PluginSearch foo - searches for foo; append `!` to refresh local cache
" :PluginClean      - confirms removal of unused plugins; append `!` to auto-approve removal
"
" see :h vundle for more details or wiki for FAQ
" Put your non-Plugin stuff after this line
