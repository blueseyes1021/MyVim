## Vim笔记

## 基础部分

* 打开文件
vi file
vi;  :e file
vi +n file      ==> 打开文件到n行
vi +/search-term==> 打卡文件到第一个匹配首行
vi +?search-term==> 打开文件到第一个匹配底部
vi -t TAG       ==> 暂时不懂

* 保存文件
w:   or  :write
up:  or  :update
w newfile
up newfile
w! newfile   ==> 强制写
up! newfile  ==> 强制写

* 关闭文件
:x  ==> 保存并退出
:wq
ZZ
:q! ==> 不保存退出
:qa ==> 退出所有当前打开文件

## Vim模式
1）正常模式 ==> vi进入后默认模式
2）编辑模式 ==> 按i键后进入编辑模式
3）命令模式 ==> 按<ESC>后，：命令
4）视图模式 ==> v, V, CTRL-V 进行块操作
5）select模式
6）Ex模式

## Vim操作
j       ==> down
k       ==> up
h       ==> right
l       ==> left
CTRL-F  ==> 下翻屏
CTRL-B  ==> 上翻屏
CTRL-D  ==> 下翻半屏
CTRL-U  ==> 上翻半屏
CTRL-E  ==> 下翻一行
CTRL-Y  ==> 上翻一行
word与WORD区别
word: letter,digits and underscores
WORD: non-blank characters
w       ==> 下一个word首
W       ==> 下一个WORD首
e       ==> 当前word尾
E       ==> 当前WORD尾
b       ==> 上一个word首
B       ==> 上一个WORD首
0       ==> 到当前行开头
$       ==> 到当前行结尾
^       ==> 到当前行第一个非空字符
g_      ==> 到当前行最后一个非空字符
{       ==> 到当前段首
}       ==> 到下一个段首
[[      ==> 到当前部分开头
]]      ==> 到下一个部分开头
(       ==> 到前一个句子开头
)       ==> 到下一个句子开头
H到当前屏幕第一行
M到当前屏幕中间行
L到当前屏幕最后一行
z<ENTER>==> 将当前行设为屏幕第一行
z-      ==> 将当前行设为屏幕最后一行
z.      ==> 将当前行设为屏幕中间行
:n      ==> 到第n行
gg      ==> 到文件首
1       ==> G同上
:       ==> $到文件尾
G       ==>  同上
n%      ==> 到文件n%
nl      ==> 到当前位置后第n个字符
n<space>==> 到100个字符后
:goto n ==> 到开头后n字符
n|      ==> 到当前行n字符
ngg     ==> 到第n行
nG      ==> 同上
%       ==> 显示匹配的括号
[(      ==> 到匹配的(
[)      ==> 到匹配的)
[{      ==> 到匹配的{
[}      ==> 到匹配的}
gj      ==> 下翻虚拟行
gk      ==> 上翻虚拟行
g^      ==> 到虚拟行开头
g$      ==> 到虚拟行结尾
gm      ==> 到虚拟行中间
ma      ==> 创建本地标签（小写本地标签；大写全局标签）
`a      ==> 跳转到标签a
'a      ==> 跳转到标签a行首
mP,mG在两个不同文件创建2个标签，`P,`G切换
`"退出前最后编辑的位置
`[之前修改的第一个字符
`]之前修改的最后一个字符
`<之前选择的虚拟行首行
`>之前选择的虚拟行末行
`.最后修改的位置
`^编辑模式最后的位置


## Vim命令
:set number  or set nu      ==> 显示行号
:set nonumber or set nonu   ==> 关闭行号
:set numberwidth=n          ==> 设置行号列宽
:set list                   ==> 显示隐藏字符
:set nolist                 ==> 关闭显示
:version                    ==> 版本信息
:h or help                  ==> 帮助
    CTRL-]  ==> 在帮助文档中跳转至链接指向文档
:helpgrep pattern           ==> 搜索帮助文档中匹配的字符
    :cn     ==> 跳转（vi中是n）
:help 'option'              ==> 在帮助中搜索命令
:jumps                      ==> 跳转访问点
    CTRL-O  ==> 下翻
    CTRL-I  ==> 上翻
:marks                      ==> 显示标签
:set nojoinspaces           ==> join连接时消除空格


Vim配置文件
Unix/Linux      ==> $HOME/.vimrc    本地配置文件
                ==> /etc/vim/vimrc  全局配置文件    Ubuntu
Windows         ==> $HOME/_vimrc    本地

Unix/Linix      ==> $VIM/.vimrc     全局配置文件
Windows         ==> $VIM/_vimrc     全局

vimtutor（Vim教程）

编辑模式
SHIFT-<R Arrow>     ==> word方式右移
SHIFT-<L Arrow>     ==> word方式左移


# 选中数字后 
# ctrl-a	==>	+1
# ctrl-x	==>	-1

# 插入一列递增数字
:put=range(1,100)

## 用法记忆
* nomal模式
~ => 在vim中修改字符大小写
c => 删除并编辑
r => 替换字符
. => 重复上一步操作


## vim宏用法
* normal模式键入 qa ==> 创建宏@a 然后进行编辑，例如：
	stdio.h
	fcntl.h
	unistd.h
	stdlib.h

* 录制宏命令
	#include "stdio.h"

进入normal模式 键入q退出宏编辑
* 执行3@a ==> 执行宏命令3次，结果如下
	#include "stdio.h"
	#include "fcntl.h"
	#include "unistd.h"
	#include "stdlib.h"

## 搜索命令
* 正向搜索
	/pattern
	键入n向下搜索
* 反向搜索
	?pattern
	键入n向上搜索
* 搜索配置项
	set hlsearch	" 设置搜索内容高亮
	set nohlsearch	" 关闭
	set incsearch	" 增量搜索
	set noincsearch " 关闭

## 折叠
* 手动折叠: virtual mode 选择折叠括号内容 键入zf
* 打开折叠: zo
* 折叠范围: zfi{ ==> 折叠大括号内的代码(注：光标移至{位置)
			zfi( ==> 折叠小括号内的代码

## vim多窗体操作


## 指令速记 (vim操作命令可以理解成组合封装，把一系列操作步骤alias为简单名字)
## nomal模式
* .		" 重复上一个操作
* <		" 向左缩进
* >G	" 此行到文件尾全部向右缩进
* >>	" 本行向右缩进
* >3j	" 本行及向下的3行均向右缩进
* A		" 移动到行末 ==> $a (先到行尾，再向后移动一位)
* a		" 移动到当前字母后
* C		" 修改从当前位置到行末内容 ==> c$
* s		" 删除当前字符并进入insert模式 ==> cl
* S		" 删除整行并进入insert模式 ==> ^C
* I		" 在行首进入insert模式 ==> ^i
* o		" ==> A<CR>
* O		" ==> ko
* f{c}	" 查找{c}字符
* ;		" 向后重复上一个f{c}命令
* ,		" 向前重复上一个f{c}命令
* &		" 重复替换操作 :s/target/replacement/
* @x	" 重复执行变化命令序列 qx{changes}q
* *		" 当前光标所在位置，对当前单词执行查找并高亮显示
* cw	" 删除当前单词并进入insert模式
* db	" 从后向前删除单词
* dw	" 从前向后删除单词
* daw	" 光标位于单词中间位置，删除整个单词
* <C-a>	" 数字加1 （配合数字使用 3<C-a> ==> 数字加3）
* <C-x>	" 数字减1 
* ;.	" 重复上一个查找命令后执行上一个修改
* yyp	" 复制当前行并粘贴
* set nrformats=	" 设置数字进制，在vimrc中配置
* d2w	" 删除命令，作用于2个单词
* 2dw	" 执行2次删除命令，每次作用于1个单词
* g~	" 大小写互换
* gu	" 转换小写
* gU	" 转换大写

## insert模式
* <C-h>	" 回退删除一个字符
* <C-w>	" 回退删除一个单词
* <C-u>	" 回退删除至行首
* <Esc>	" 切换回normal模式
* <C-[>	" 同上
* <C-r>=5*25<CR>	" 计算数值
* <C-v>u{1234}		" 插入特殊字符
* :h digraphs-default	" 特殊字符和图形对照表

## visual模式

## command-line模式
* :3,6delete s	" 删除3-6行，并将删除内容注册到s中
* :8put s		" 在第8行添加s中的内容
* :5,8yank s	" 5-8行内容注册到s中
* :3,7copy 9	" 复制3-7行内容到第9行
* :3,7move 9	" 移动3-7行内容到第9行
* :1,5join		" 连接1-5行为一行
* :3,5normal dw	" 在3-5行执行normal模式命令dw 删除单词
* :s/pattern/string/g	" 替换
* :1,10global/bash/d	" 删除1-10行的匹配bash的行(没有行数指定则删所有行)
* :.,$p			" 打印当前位置到行尾的内容
* :%p			" 打印所有行
* :'<,'>p		" '< visual selection起始行 '> vs 结束行
* :/<html>/+1,/<\/html>/-1p	" <html>vs模式选择的起始行的下一行开始
							" html> vs模式选择的终止行的上一行结束


## 文件操作

