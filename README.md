# My Vim

# **Vim Plugin**

### **vim-plug**

[https://github.com/junegunn/vim-plug](https://github.com/junegunn/vim-plug)

Install

```bash
curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
    https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```

Vimrc

```bash
call plug#begin('~/.vim/plugged')

Plug '...'

call plug#end()
```

Download

```bash
~/.vim/autoload
```

PlugInstall

```bash
:PlugInstall
```

### vim-pathogen

[https://github.com/tpope/vim-pathogen](https://github.com/tpope/vim-pathogen)

```bash
filetype off

call pathogen#infect()
call pathogen#helptags()

filetype plugin indent on
syntax on
```

### vim-startify

[https://github.com/mhinz/vim-startify](https://github.com/mhinz/vim-startify)

```bash
:h startify
:h startify-faq
```

### vim-gotham

[https://github.com/whatyouhide/vim-gotham](https://github.com/whatyouhide/vim-gotham)

```bash
colorscheme gotham
colorscheme gotham256
:AirlineTheme gotham
:AirlineTheme gotham256
```

### vim-airline

[https://github.com/vim-airline/vim-airline](https://github.com/vim-airline/vim-airline)

```bash
let laststatus = 2
let g:airline_powerline_fonts = 1
let g:airline_theme="dark"   
let g:airline#extensions#tabline#enabled = 1
let g:airline#extensions#tabline#left_sep = ' '
let g:airline#extensions#tabline#left_alt_sep = '|'
let g:airline#extensions#tabline#buffer_nr_show = 1      
nnoremap [b :bp<CR>
nnoremap ]b :bn<CR>
```

### Powerline fonts

[https://github.com/powerline/fonts](https://github.com/powerline/fonts)

```bash
set guifont=Inconsolata\ for\ Powerline\ 20
```

### vim-fugitive

[https://github.com/tpope/vim-fugitive](https://github.com/tpope/vim-fugitive)

```bash
mkdir -p ~/.vim/pack/tpope/start
cd ~/.vim/pack/tpope/start
git clone https://tpope.io/vim/fugitive.git
vim -u NONE -c "helptags fugitive/doc" -c q
```

### git-blame

[https://github.com/zivyangll/git-blame.vim](https://github.com/zivyangll/git-blame.vim)

```bash
nnoremap <Leader>s :<C-u>call gitblame#echo()<CR>
```

### vim-nerdtree

[https://github.com/preservim/nerdtree](https://github.com/preservim/nerdtree)

```bash
map <C-n> :NERDTreeToggle<CR>
map  <C-l> :tabn<CR>
map  <C-h> :tabp<CR>
let g:NERDTreeShowLineNumbers=1
let NERDTreeMinimalUI = 1
let NERDTreeShowHidden = 1
autocmd bufenter * if (winnr("$") == 1 && exists("b:NERDTree") && b:NERDTree.isTabTree()) | q | endif
```

### Vim-neocomplate

[https://github.com/shougo/neocomplete.vim](https://github.com/shougo/neocomplete.vim)

```bash
" Disable AutoComplPop.
let g:acp_enableAtStartup = 0
" Use neocomplete.
let g:neocomplete#enable_at_startup = 1
" Use smartcase.
let g:neocomplete#enable_smart_case = 1
" Set minimum syntax keyword length.
let g:neocomplete#sources#syntax#min_keyword_length = 3

" Define dictionary.
let g:neocomplete#sources#dictionary#dictionaries = {
    \ 'default' : '',
    \ 'vimshell' : $HOME.'/.vimshell_hist',
    \ 'scheme' : $HOME.'/.gosh_completions'
        \ }

" Define keyword.
if !exists('g:neocomplete#keyword_patterns')
    let g:neocomplete#keyword_patterns = {}
endif
let g:neocomplete#keyword_patterns['default'] = '\h\w*'

" Plugin key-mappings.
inoremap <expr><C-g>     neocomplete#undo_completion()
inoremap <expr><C-l>     neocomplete#complete_common_string()

" Recommended key-mappings.
" <CR>: close popup and save indent.
inoremap <silent> <CR> <C-r>=<SID>my_cr_function()<CR>
function! s:my_cr_function()
  return (pumvisible() ? "\<C-y>" : "" ) . "\<CR>"
  " For no inserting <CR> key.
  "return pumvisible() ? "\<C-y>" : "\<CR>"
endfunction
" <TAB>: completion.
inoremap <expr><TAB>  pumvisible() ? "\<C-n>" : "\<TAB>"
" <C-h>, <BS>: close popup and delete backword char.
inoremap <expr><C-h> neocomplete#smart_close_popup()."\<C-h>"
inoremap <expr><BS> neocomplete#smart_close_popup()."\<C-h>"
" Close popup by <Space>.
"inoremap <expr><Space> pumvisible() ? "\<C-y>" : "\<Space>"

" AutoComplPop like behavior.
"let g:neocomplete#enable_auto_select = 1

" Shell like behavior(not recommended).
"set completeopt+=longest
"let g:neocomplete#enable_auto_select = 1
"let g:neocomplete#disable_auto_complete = 1
"inoremap <expr><TAB>  pumvisible() ? "\<Down>" : "\<C-x>\<C-u>"

" Enable omni completion.
autocmd FileType css setlocal omnifunc=csscomplete#CompleteCSS
autocmd FileType html,markdown setlocal omnifunc=htmlcomplete#CompleteTags
autocmd FileType javascript setlocal omnifunc=javascriptcomplete#CompleteJS
autocmd FileType python setlocal omnifunc=pythoncomplete#Complete
autocmd FileType xml setlocal omnifunc=xmlcomplete#CompleteTags

" Enable heavy omni completion.
if !exists('g:neocomplete#sources#omni#input_patterns')
  let g:neocomplete#sources#omni#input_patterns = {}
endif
"let g:neocomplete#sources#omni#input_patterns.php = '[^. \t]->\h\w*\|\h\w*::'
"let g:neocomplete#sources#omni#input_patterns.c = '[^.[:digit:] *\t]\%(\.\|->\)'
"let g:neocomplete#sources#omni#input_patterns.cpp = '[^.[:digit:] *\t]\%(\.\|->\)\|\h\w*::'

" For perlomni.vim setting.
" https://github.com/c9s/perlomni.vim
let g:neocomplete#sources#omni#input_patterns.perl = '\h\w*->\h\w*\|\h\w*::'
```

### ctrlp.vim

[https://github.com/ctrlpvim/ctrlp.vim](https://github.com/ctrlpvim/ctrlp.vim)

```bash
let g:ctrlp_map = '<c-p>'
let g:ctrlp_cmd = 'CtrlP'
```

ctrlp-funky

[https://github.com/tacahiroy/ctrlp-funky](https://github.com/tacahiroy/ctrlp-funky)

```bash
nnoremap <Leader>fu :CtrlPFunky<Cr>
" narrow the list down with a word under cursor
nnoremap <Leader>fU :execute 'CtrlPFunky ' . expand('<cword>')<Cr>
let g:ctrlp_funky_syntax_highlight = 1
let g:ctrlp_funky_matchtype = 'path'
```

## vim-mustache-handlebars

[https://github.com/mustache/vim-mustache-handlebars](https://github.com/mustache/vim-mustache-handlebars)

# .ivimrc

```bash
filetype off

call pathogen#infect()
call pathogen#helptags()

filetype plugin indent on
syntax on
syntax enable
set encoding=utf8
set fileencodings=utf8
filetype on
filetype indent on
set t_Co=256
set mouse=a
set number
colorscheme gotham256
set cursorline
set smartindent
set nobackup
set cindent
set ai
set wrap
set hlsearch
set guifont=Powerline_Consolas:h16

let mapleader = ","  " map leader键设置
let g:mapleader = ","

"netrw setting

" airline setting
let laststatus = 2
let g:airline_powerline_fonts = 1
let g:airline#extensions#tabline#enabled = 1
let g:airline#extensions#tabline#left_sep = ' '
let g:airline#extensions#tabline#left_alt_sep = '|'
let g:airline#extensions#tabline#buffer_nr_show = 1      
let g:gotham_airline_emphasised_insert = 0
nnoremap [b :bp<CR>
nnoremap ]b :bn<CR>

" nardtree setting
"autocmd vimenter * NERDTree
map <C-n> :NERDTreeToggle<CR>
map  <C-l> :tabn<CR>
map  <C-h> :tabp<CR>
let g:NERDTreeShowLineNumbers=1
let NERDTreeMinimalUI = 1
let NERDTreeShowHidden = 1
autocmd bufenter * if (winnr("$") == 1 && exists("b:NERDTree") && b:NERDTree.isTabTree()) | q | endif

" neocomplete setting
" Disable AutoComplPop.
let g:acp_enableAtStartup = 0
" Use neocomplete.
let g:neocomplete#enable_at_startup = 1
" Use smartcase.
let g:neocomplete#enable_smart_case = 1
" Set minimum syntax keyword length.
let g:neocomplete#sources#syntax#min_keyword_length = 3

" Define dictionary.
let g:neocomplete#sources#dictionary#dictionaries = {
    \ 'default' : '',
    \ 'vimshell' : $HOME.'/.vimshell_hist',
    \ 'scheme' : $HOME.'/.gosh_completions'
        \ }

" Define keyword.
if !exists('g:neocomplete#keyword_patterns')
    let g:neocomplete#keyword_patterns = {}
endif
let g:neocomplete#keyword_patterns['default'] = '\h\w*'

" Plugin key-mappings.
inoremap <expr><C-g>     neocomplete#undo_completion()
inoremap <expr><C-l>     neocomplete#complete_common_string()

" Recommended key-mappings.
" <CR>: close popup and save indent.
inoremap <silent> <CR> <C-r>=<SID>my_cr_function()<CR>
function! s:my_cr_function()
  return (pumvisible() ? "\<C-y>" : "" ) . "\<CR>"
  " For no inserting <CR> key.
  "return pumvisible() ? "\<C-y>" : "\<CR>"
endfunction
" <TAB>: completion.
inoremap <expr><TAB>  pumvisible() ? "\<C-n>" : "\<TAB>"
" <C-h>, <BS>: close popup and delete backword char.
inoremap <expr><C-h> neocomplete#smart_close_popup()."\<C-h>"
inoremap <expr><BS> neocomplete#smart_close_popup()."\<C-h>"
" Close popup by <Space>.
"inoremap <expr><Space> pumvisible() ? "\<C-y>" : "\<Space>"

" AutoComplPop like behavior.
"let g:neocomplete#enable_auto_select = 1

" Shell like behavior(not recommended).
"set completeopt+=longest
"let g:neocomplete#enable_auto_select = 1
"let g:neocomplete#disable_auto_complete = 1
"inoremap <expr><TAB>  pumvisible() ? "\<Down>" : "\<C-x>\<C-u>"

" Enable omni completion.
autocmd FileType css setlocal omnifunc=csscomplete#CompleteCSS
autocmd FileType html,markdown setlocal omnifunc=htmlcomplete#CompleteTags
autocmd FileType javascript setlocal omnifunc=javascriptcomplete#CompleteJS
autocmd FileType python setlocal omnifunc=pythoncomplete#Complete
autocmd FileType xml setlocal omnifunc=xmlcomplete#CompleteTags

" Enable heavy omni completion.
if !exists('g:neocomplete#sources#omni#input_patterns')
  let g:neocomplete#sources#omni#input_patterns = {}
endif
"let g:neocomplete#sources#omni#input_patterns.php = '[^. \t]->\h\w*\|\h\w*::'
"let g:neocomplete#sources#omni#input_patterns.c = '[^.[:digit:] *\t]\%(\.\|->\)'
"let g:neocomplete#sources#omni#input_patterns.cpp = '[^.[:digit:] *\t]\%(\.\|->\)\|\h\w*::'

" For perlomni.vim setting.
" https://github.com/c9s/perlomni.vim
let g:neocomplete#sources#omni#input_patterns.perl = '\h\w*->\h\w*\|\h\w*::'

" Ctrlp
let g:ctrlp_map = '<c-p>'
let g:ctrlp_cmd = 'CtrlP'

" CtrlpPFunky
nnoremap <Leader>fu :CtrlPFunky<Cr>
" narrow the list down with a word under cursor
nnoremap <Leader>fU :execute 'CtrlPFunky ' . expand('<cword>')<Cr>
let g:ctrlp_funky_syntax_highlight = 1
let g:ctrlp_funky_matchtype = 'path'

" git-blame
nnoremap <Leader>s :<C-u>call gitblame#echo()<CR>
```

# Vim Key

### reformat

```bash
gg  =  G
```

### 註解

```bash
按下 CTRL + v 進入 — VISUAL BLOCK — 模式
選擇要註解的區塊
按下 Shift + i 進入輸入模式
輸入註解符號（假設是 //）
按下 Esc 鍵（網路上寫說按一次就好，但在我的電腦上需要按兩次）
```

### 取消註解

```bash
按下 CTRL + v 進入 — VISUAL BLOCK — 模式
選擇要註解的區塊
按下 Shift + i 進入輸入模式
輸入註解符號（假設是 //）
按下 Esc 鍵（網路上寫說按一次就好，但在我的電腦上需要按兩次）
```

### 檔首尾移動

```bash
G  移至檔尾
gg 移至檔首
```

### 複製剪下貼上

```bash
y  複製選定塊 
yy 複製整行
d  剪下選定區塊 
dd 剪下整行
p  貼至遊標後
P  貼至遊標前
```

### left

```bash
:{range}left[margin]
```

### Undo / Redo

```bash

R  取代字元至按 Esc 為止。
U  在游標沒離開本行之前，回復所有編輯動作。
Crtl+r 這個也是很重要，就是 redo 鍵。
```

### 排版

```bash
:ce(nter)  本行文字置中。
:ri(ght)   本行文字靠右。
:le(ft)    本行文字靠左。
```