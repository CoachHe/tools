# 设置配置文件的方法：

首先进入主目录：
```
cd ~
```
然后新建一个文件夹
```
mkdir .vim
```
然后新建文件vimrc
```
vim vimrc
```

#配置文件
```shell
let mapleader=" "       " 第一行注释的意思是将leader键更改为空格
syntax on		" 自动语法高亮
set number		" 显示行号
set norelativenumber	" 不显示相对行号
set cursorline		" 突出显示当前行
set wrap
set showcmd

set hlsearch		" 搜索时启动高亮
exec "nohlsearch"	
set incsearch		" 
set ignorecase		" 搜索时忽略大小写
set smartcase

set nocompatible	" 保证使用流畅
filetype on
filetype indent on
filetype plugin on
filetype plugin indent on  " 这四行是硬性要求,识别不同的文件格式
set mouse=a 		" 让vim可以使用鼠标
set encoding=utf-8	" 支持中文
let &t_ut=' '		" 改变有些终端可能配色不对的问题

set expandtab           " 用向上的箭头将窗口向上移5个单位
set tabstop=2
set shiftwidth=2
set softtabstop=2

" 可以显示空格
set listchars=tab:▸\ ,trail:▫
set scrolloff=5
" 缩进选项
set tw=0
set indentexpr=

set backspace=indent,eol,start        " 这行的作用是能让行首back时回到行尾
set foldmethod=indent
set foldlevel=99
let &t_SI = "\<Esc>]50;CursorShape=1\x7"
let &t_SR = "\<Esc>]50;CursorShape=2\x7"
let &t_EI = "\<Esc>]50;CursorShape=0\x7"
set laststatus=2
set autochdir

"作用：关闭vim之后重新打开，光标能回到上一次的位置
au BufReadPost * if line("'\"") > 1 && line("'\"") <= line("$") | exe "normal! g'\"" | endif


noremap <LEADER><CR> :nohlsearch<CR>
			" 用空格+回车取消搜索的高亮
map s <nop>
			" 
map S :w<CR>
			" 用S来进行保存
map Q :q<CR>
			" 用Q来退出
map R :source $MYVIMRC<CR>
			" 用R来执行这个配置文件让其直接起作用

map sl :set splitright<CR>:vsplit<CR>
			" 向右分屏，并且将光标放到右边
map sh :set nosplitright<CR>:vsplit<CR>
			" 向左分屏，并且将光标放到左边
map sk :set nosplitbelow<CR>:split<CR>
			" 向上分屏，并且将光标放到上面
map sj :set splitbelow<CR>:split<CR>
			" 向下分屏，并且将光标放到下面

map <LEADER>l <C-w>l
			" 用空格+l将光标切换到右边
map <LEADER>j <C-w>k
			" 用空格+k将光标切换到下面
map <LEADER>h <C-w>h
			" 用空格+j将光标切换到左边
map <LEADER>k <C-w>j 
			" 用空格+i将光标切换到上面
map <up> :res + 5<CR>
			" 用向上的箭头将窗口向上移5个单位
map <down> :res -5<CR>
                        " 用向下的箭头将窗口向下移5个单位
map <left> :vertical resize-5<CR>
                        " 用向左的箭头将窗口向左移5个单位
map <right> :vertical resize+5<CR>
			" 用向右的箭头将窗口向右移5个单位

" 进行插件的安装
call plug#begin('~/.vim/plugged')	

Plug 'vim-airline/vim-airline'
			" 该插件安装后能在下面出现工作框
Plug 'connorholyday/vim-snazzy'
			" 该插件安装后使用snazzy字体

" File navigation
Plug 'Xuyuanp/nerdtree-git-plugin'

" Taglist
Plug 'majutsushi/tagbar', { 'on': 'TagbarOpenAutoClose' }

" Error checking
Plug 'w0rp/ale'

" Other visual enhancement
Plug 'nathanaelkane/vim-indent-guides'
Plug 'itchyny/vim-cursorword'


" HTML, CSS, JavaScript, PHP, JSON, etc.
Plug 'elzr/vim-json'
Plug 'hail2u/vim-css3-syntax'
Plug 'spf13/PIV', { 'for' :['php', 'vim-plug'] }
Plug 'gko/vim-coloresque', { 'for': ['vim-plug', 'php', 'html', 'javascript', 'css', 'less'] }
Plug 'pangloss/vim-javascript', { 'for' :['javascript', 'vim-plug'] }
Plug 'mattn/emmet-vim'


" Other useful utilities
Plug 'terryma/vim-multiple-cursors'
Plug 'junegunn/goyo.vim' " distraction free writing mode
Plug 'tpope/vim-surround' " type ysks' to wrap the word with '' or type cs'` to change 'word' to `word`
Plug 'godlygeek/tabular' " type ;Tabularize /= to align the =
Plug 'gcmt/wildfire.vim' " in Visual mode, type i' to select all text in '', or type i) i] i} ip
Plug 'scrooloose/nerdcommenter' " in <space>cc to comment a line

" Dependencies
Plug 'MarcWeber/vim-addon-mw-utils'
Plug 'kana/vim-textobj-user'
Plug 'fadein/vim-FIGlet'

call plug#end()

" 这里进行snazy的设置
color snazzy
let g:SnazzyTransparent = 1

```

