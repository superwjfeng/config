### debian换源

debian换官方源 <https://wiki.debian.org/SourcesList> `/etc/apt/sources.list`

```
deb http://deb.debian.org/debian bookworm main non-free-firmware
deb-src http://deb.debian.org/debian bookworm main non-free-firmware

deb http://deb.debian.org/debian-security/ bookworm-security main non-free-firmware
deb-src http://deb.debian.org/debian-security/ bookworm-security main non-free-firmware

deb http://deb.debian.org/debian bookworm-updates main non-free-firmware
deb-src http://deb.debian.org/debian bookworm-updates main non-free-firmware
```

```shell
sudo apt-update
```

### zsh

安装zsh和oh-my-zsh <[zsh 安装与配置：9步打造高效命令行 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/441676276)>

### vim

安装vim-plug <https://github.com/junegunn/vim-plug>

安装vim-airline <https://github.com/vim-airline/vim-airline>

安装vim-snazzy 主题 <https://github.com/connorholyday/vim-snazzy>

### neovim

安装neovim <https://github.com/neovim/neovim/wiki/Installing-Neovim>

```shell
curl -LO https://github.com/neovim/neovim/releases/latest/download/nvim.appimage
chmod u+x nvim.appimage
./nvim.appimage
```

为了在任意地方输入vim就可以打开它，给它建立一个名为vim的快捷方式（软连接）

```bash
sudo ln -sf /path/to/nvim.appimage /usr/bin/vim
```









```shell
syntax on
set number " 行号
set norelativenumber " 相对行号
set cursorline
set wrap " 过长的自动换行
set showcmd
set wildmenu

set hlsearch " 高亮搜索
exec "nohlsearch"
set incsearch " 边输边高亮
set ignorecase " 忽略大小写
set smartcase " 智能匹配大小写

" set clipboard=unnamed
vnoremap <C-y> "+y
nnoremap <C-p> "*p
" 键位映射
map S :w<CR>
" map Q :q<CR>
map R :source $MYVIMRC<CR>

set tabstop=4

" 插件
call plug#begin()
Plug 'vim-airline/vim-airline'
Plug 'vim-airline/vim-airline-themes'
Plug 'connorholyday/vim-snazzy'
Plug 'neoclide/coc.nvim', {'branch': 'release'}
call plug#end()

color snazzy
```





### 配置ssh

在服务器上配置，公钥放在$HOME下面的.ssh里，注意root和普通用户的密码可以是不同的





`sudo vim /etc/motd`

```shell
   ,     #_
   ~\_  ####_        Welcome to CentOS!
  ~~  \_#####\
  ~~     \###|
  ~~       \#/ ___
   ~~       V~' '->
    ~~~         /
      ~~._.   _/
         _/ _/
       _/m/'         Welcome to CentOS!
```

### 配置git

```shell
git config user.name "gitlab's Name"
git config user.email "gitlab@xx.com"
# 将 /path/to/private/key 替换为私钥文件的完整路径
git config --global core.sshCommand "ssh -i /path/to/private/key" 
```

