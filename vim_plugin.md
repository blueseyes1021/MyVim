## Vim plugin笔记 --> 打造强大的Vim IDE

## 插件管理 Vundle
## 安装
	`$ git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim`
## 配置
	编辑用户目录下的`~/.vimrc`
	```
	set nocompatible	" 关闭vi兼容模式 必须
	filetype off		" 必须

	" 设置runtime path 载入Vundle并初始化
	set rtp+=~/.vim/bundle/Vundle.vim
	call vundle#begin()
	" 也可指定路径切换vundle其他版本
	" call vundle#begin('~/some/path/here')

	" 让Vundle管理Vundle 必须
	Plugin 'VundleVim/Vundle.vim'
	" http://github.com/VundleVim/Vundle.Vim
	" 插件指定github上组件的名称(github.com/后的内容)
	" 添加github上的资源库
	" 在vundle#begin/end之间添加插件
	Plugin 'tpope/vim-fugitive'
	" git插件不在github上的情况，比如私服库
	Plugin 'git://git.wincent.com/command-t.git'
	" 插件在本地路径
	Plugin 'file://home/gmarik/path/to/plugin'
	" 在vim资源库子目录下
	Plugin 'rstacruz/sparkup', {'rtp': 'vim/'}
	" 避免命名冲突
	" Plugin 'L9'
	" Plugin 'ascenator/L9', {'name': 'newL9'}

	" 插件设置结束标记
	call vundle#end()	" 必须
	filetype plugin indent on	" 必须
	```
## 命令
:PluginList			- 列出配置的插件
:PluginInstall		- 安装插件
:PluginInstall!		- 更新插件
:PluginUpdate		- 更新插件
:PluginSearch foo	- 查找foo插件
:PluginClean		- 确认清理不用的插件



## 插件记录
* tpope/vim-pathogen		" 安装管理
* ervandew/supertab			" 补全
* vim-syntastic/syntastic	" 语法检查
* jiangmiao/auto-pairs		" 自动补齐括号
* scrooloose/nerdcommenter	" 注解
* msanders/snipmate.vim		" 添加代码片段
* scrooloose/nerdtree		" 树结构文件浏览器
* MiniBufferExplorer
* Tag List
* undotree
* gdbmgr



