# study 

export HISTTIMEFORMAT="%F %T `whoami` "
通过设置环境变量 export HISTTIMEFORMAT="%F %T `whoami` " 给history加上时间戳
echo 'export HISTTIMEFORMAT="%F %T `whoami` "' >> /etc/profile 然后source一下


* bash
* git
* coreutiles命令列表
* tmux
* vim
* 字符集及编码标准
* 日期和时间表示，及标准
* 字节其换算，及标准表示
* 数据结构
* 算法分析
* 设计模式

----------------------------------------------------------------------------

tmux
============================================================================

   | 对象       | 按键        | 说明                                                                                                      |
   | ---        | ---         | ---                                                                                                       |
   | 激活控制台 | Ctrl+b      | 此时以下按键生效                                                                                          |
   | 系统操作   |             |                                                                                                           |
   |            | ?           | 列出所有快捷键；按`q`返回                                                                                   |
   |            | d           | 脱离当前会话；这样可以暂时返回Shell界面，输入`tmux attach`能够重新进入之前的会话                            |
   |            | D           | 选择要脱离的会话；在同时开启了多个会话时使用                                                              |
   |            | Ctrl+z      | 挂起当前会话                                                                                              |
   |            | r           | 强制重绘未脱离的会话                                                                                      |
   |            | s           | 选择并切换会话；在同时开启了多个会话时使用                                                                |
   |            | :           | 进入命令行模式；此时可以输入支持的命令，例如kill-server可以关闭服务器                                     |
   |            | [           | 进入复制模式；此时的操作与vi/emacs相同，按q/Esc退出                                                       |
   |            | ~           | 列出提示信息缓存；其中包含了之前tmux返回的各种提示信息                                                    |
   | 窗口操作   |             |                                                                                                           |
   |            | c           | 创建新窗口                                                                                                |
   |            | &           | 关闭当前窗口                                                                                              |
   |            | 数字键      | 切换至指定窗口                                                                                            |
   |            | p           | 切换至上一窗口                                                                                            |
   |            | n           | 切换至下一窗口                                                                                            |
   |            | l           | 在前后两个窗口间互相切换                                                                                  |
   |            | w           | 通过窗口列表切换窗口                                                                                      |
   |            | ,           | 重命名当前窗口；这样便于识别                                                                              |
   |            | .           | 修改当前窗口编号；相当于窗口重新排序                                                                      |
   |            | f           | 在所有窗口中查找指定文本                                                                                  |
   | 面板操作   |             |                                                                                                           |
   |            | ”           | 将当前面板平分为上下两块                                                                                  |
   |            | %           | 将当前面板平分为左右两块                                                                                  |
   |            | x           | 关闭当前面板                                                                                              |
   |            | !           | 将当前面板置于新窗口；即新建一个窗口，其中仅包含当前面板                                                  |
   |            | Ctrl+方向键 | 以1个单元格为单位移动边缘以调整当前面板大小                                                               |
   |            | Alt+方向键  | 以5个单元格为单位移动边缘以调整当前面板大小                                                               |
   |            | Space       | 在预置的面板布局中循环切换；依次包括even-horizontal、even-vertical、main-horizontal、main-vertical、tiled |
   |            | q           | 显示面板编号                                                                                              |
   |            | o           | 在当前窗口中选择下一面板                                                                                  |
   |            | 方向键      | 移动光标以选择面板                                                                                        |
   |            | {           | 向前置换当前面板                                                                                          |
   |            | }           | 向后置换当前面板                                                                                          |
   |            | Alt+o       | 逆时针旋转当前窗口的面板                                                                                  |
   |            | Ctrl+o      | 顺时针旋转当前窗口的面板                                                                                  |



bash
============================================================================

使用快捷键以高效地编辑命令行
----------------------------------------------------------------------------
 * Ctrl + A 将光标移动到命令行的开始处
 * Ctrl + E 将光标移动到命令行的末尾
 * Ctrl + W 直接删除光标前的字
 * Ctrl + K 直接删除光标前的所有字符
 * Ctrl + Y 撤销一个删除
 * Ctrl + L 为清屏幕
 * Ctrl + R 来“快速查找”先前执行的命令
 * Ctrl + C To terminate（终止进程）
 * Ctrl + D signals EOF（文件结束符）
 * Ctrl + Z suppends a program（暂停一个进程）

频繁地使用参数相同的某个命令,创建一个别名：

```bash
	alias ls=’ls -l’
	unalias ls 
```

git
----------------------------------------------------------------------------

使用命令`git --help`查看

	用法：git [--version] [--help] [-c name=value]
		   [--exec-path[=<path>]] [--html-path] [--man-path] [--info-path]
		   [-p|--paginate|--no-pager] [--no-replace-objects] [--bare]
		   [--git-dir=<path>] [--work-tree=<path>] [--namespace=<name>]
		   <command> [<args>]

	最常用的 git 命令有：
	   add        添加文件内容至索引
	   bisect     通过二分查找定位引入 bug 的变更
	   branch     列出、创建或删除分支
	   checkout   检出一个分支或路径到工作区
	   clone      克隆一个版本库到一个新目录
	   commit     记录变更到版本库
	   diff       显示提交之间、提交和工作区之间等的差异
	   fetch      从另外一个版本库下载对象和引用
	   grep       输出和模式匹配的行
	   init       创建一个空的 Git 版本库或重新初始化一个已存在的版本库
	   log        显示提交日志
	   merge      合并两个或更多开发历史
	   mv         移动或重命名一个文件、目录或符号链接
	   pull       获取并合并另外的版本库或一个本地分支
	   push       更新远程引用和相关的对象
	   rebase     本地提交转移至更新后的上游分支中
	   reset      重置当前HEAD到指定状态
	   rm         从工作区和索引中删除文件
	   show       显示各种类型的对象
	   status     显示工作区状态
	   tag        创建、列出、删除或校验一个GPG签名的 tag 对象

	命令 'git help -a' 和 'git help -g' 显示可用的子命令和一些指南。参见
	'git help <命令>' 或 'git help <指南>' 来查看给定的子命令帮助或指南。


查看配置选项`git config`

	用法：git config [选项]

	配置文件位置
	    --global              使用全局配置文件
	    --system              使用系统级配置文件
	    --local               使用版本库级配置文件
	    -f, --file <文件>     使用指定的配置文件

	操作
	    --get                 获取值：name [value-regex]
	    --get-all             获得所有的值：key [value-regex]
	    --get-regexp          根据正则表达式获得值：name-regex [value-regex]
	    --replace-all         替换所有匹配的变量：name value [value_regex]
	    --add                 添加一个新的变量：name value
	    --unset               删除一个变量：name [value-regex]
	    --unset-all           删除所有匹配项：name [value-regex]
	    --rename-section      重命名小节：old-name new-name
	    --remove-section      删除一个小节：name
	    -l, --list            列出所有
	    -e, --edit            打开一个编辑器
	    --get-color <slot>    找到配置的颜色：[默认]
	    --get-colorbool <slot>
				  找到颜色设置：[stdout-is-tty]

	类型
	    --bool                值是 "true" 或 "false"
	    --int                 值是十进制数
	    --bool-or-int         值是 --bool or --int
	    --path                值是一个路径（文件或目录名）

	其它
	    -z, --null            终止值是NUL字节
	    --includes            查询时参照 include 指令递归查找


## vim 

> vim --version

```bash
	VIM - Vi IMproved 7.4 (2013 Aug 10, compiled Dec 21 2016 17:00:20)
	包含补丁: 1-160
	修改者 <bugzilla@redhat.com>
	编译者 <bugzilla@redhat.com>
	巨型版本 无图形界面。  可使用(+)与不可使用(-)的功能:
	+acl             +farsi           +mouse_netterm   +syntax
	+arabic          +file_in_path    +mouse_sgr       +tag_binary
	+autocmd         +find_in_path    -mouse_sysmouse  +tag_old_static
	-balloon_eval    +float           +mouse_urxvt     -tag_any_white
	-browse          +folding         +mouse_xterm     -tcl
	++builtin_terms  -footer          +multi_byte      +terminfo
	+byte_offset     +fork()          +multi_lang      +termresponse
	+cindent         +gettext         -mzscheme        +textobjects
	-clientserver    -hangul_input    +netbeans_intg   +title
	-clipboard       +iconv           +path_extra      -toolbar
	+cmdline_compl   +insert_expand   +perl            +user_commands
	+cmdline_hist    +jumplist        +persistent_undo +vertsplit
	+cmdline_info    +keymap          +postscript      +virtualedit
	+comments        +langmap         +printer         +visual
	+conceal         +libcall         +profile         +visualextra
	+cryptv          +linebreak       +python/dyn      +viminfo
	+cscope          +lispindent      -python3         +vreplace
	+cursorbind      +listcmds        +quickfix        +wildignore
	+cursorshape     +localmap        +reltime         +wildmenu
	+dialog_con      -lua             +rightleft       +windows
	+diff            +menu            +ruby/dyn        +writebackup
	+digraphs        +mksession       +scrollbind      -X11
	-dnd             +modify_fname    +signs           -xfontset
	-ebcdic          +mouse           +smartindent     -xim
	+emacs_tags      -mouseshape      -sniff           -xsmp
	+eval            +mouse_dec       +startuptime     -xterm_clipboard
	+ex_extra        +mouse_gpm       +statusline      -xterm_save
	+extra_search    -mouse_jsbterm   -sun_workshop    -xpm
	     系统 vimrc 文件: "/etc/vimrc"
	     用户 vimrc 文件: "$HOME/.vimrc"
	 第二用户 vimrc 文件: "~/.vim/vimrc"
	      用户 exrc 文件: "$HOME/.exrc"
		 $VIM 预设值: "/etc"
	  $VIMRUNTIME 预设值: "/usr/share/vim/vim74"
	编译方式: gcc -c -I. -Iproto -DHAVE_CONFIG_H     -O2 -g -pipe -Wall -fexceptions -fstack-protector-strong --param=ssp-buffer-size=4 -grecord-gcc-switches   -m64 -mtune=generic -D_GNU_SOURCE -D_FILE_OFFSET_BITS=64 -U_FORTIFY_SOURCE -D_FORTIFY_SOURCE=1      
	链接方式: gcc   -L. -Wl,-z,relro -fstack-protector -rdynamic -Wl,-export-dynamic -Wl,--enable-new-dtags -Wl,-rpath,/usr/lib64/perl5/CORE  -Wl,-z,relro  -L/usr/local/lib -Wl,--as-needed -o vim        -lm -lnsl  -lselinux  -lncurses -lacl -lattr -lgpm -ldl   -Wl,--enable-new-dtags -Wl,-rpath,/usr/lib64/perl5/CORE  -fstack-protector  -L/usr/lib64/perl5/CORE -lperl -lresolv -lnsl -ldl -lm -lcrypt -lutil -lpthread -lc       

```

## 查看网卡
ifconfig

	ens33: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
		inet 192.168.8.132  netmask 255.255.255.0  broadcast 192.168.8.255
		inet6 fe80::97e8:8c0c:3a9c:9d2f  prefixlen 64  scopeid 0x20<link>
		ether 00:0c:29:dd:c3:07  txqueuelen 1000  (Ethernet)
		RX packets 1274065  bytes 723418594 (689.9 MiB)
		RX errors 0  dropped 0  overruns 0  frame 0
		TX packets 78707  bytes 15189766 (14.4 MiB)
		TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

	lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
		inet 127.0.0.1  netmask 255.0.0.0
		inet6 ::1  prefixlen 128  scopeid 0x10<host>
		loop  txqueuelen 1  (Local Loopback)
		RX packets 320  bytes 26844 (26.2 KiB)
		RX errors 0  dropped 0  overruns 0  frame 0
		TX packets 320  bytes 26844 (26.2 KiB)
		TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

	virbr0: flags=4099<UP,BROADCAST,MULTICAST>  mtu 1500
		inet 192.168.122.1  netmask 255.255.255.0  broadcast 192.168.122.255
		ether 52:54:00:49:fa:0e  txqueuelen 1000  (Ethernet)
		RX packets 0  bytes 0 (0.0 B)
		RX errors 0  dropped 0  overruns 0  frame 0
		TX packets 0  bytes 0 (0.0 B)
		TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
	lbg      :0           2017-06-06 09:44 (:0)

## 查看yum 版本库
yum repolist

	已加载插件：fastestmirror, langpacks
	Loading mirror speeds from cached hostfile
	 * base: mirrors.yun-idc.com
	 * epel: mirrors.tuna.tsinghua.edu.cn
	 * extras: mirrors.btte.net
	 * updates: mirrors.cn99.com
	源标识                   源名称                                           状态
	base/7/x86_64            CentOS-7 - Base                                   9,363
	docker-ce-stable/x86_64  Docker CE Stable - x86_64                             4
	epel/x86_64              Extra Packages for Enterprise Linux 7 - x86_64   11,771
	extras/7/x86_64          CentOS-7 - Extras                                   380
	google-chrome            google-chrome                                         3
	updates/7/x86_64         CentOS-7 - Updates                                1,851
	repolist: 23,372

## 查看当前环境变量
set

	BASH=/bin/bash
	BASHOPTS=cmdhist:extquote:force_fignore:hostcomplete:interactive_comments:progcomp:promptvars:sourcepath
	BASH_ALIASES=()
	BASH_ARGC=()
	BASH_ARGV=()
	BASH_CMDS=()
	BASH_EXECUTION_STRING='(set) < /tmp/vjVMUe2/8 >/tmp/vjVMUe2/9 2>&1'
	BASH_LINENO=()
	BASH_SOURCE=()
	BASH_VERSINFO=([0]="4" [1]="2" [2]="46" [3]="1" [4]="release" [5]="x86_64-redhat-linux-gnu")
	BASH_VERSION='4.2.46(1)-release'
	DBUS_SESSION_BUS_ADDRESS=unix:abstract=/tmp/dbus-jRFUkeoH00,guid=8f115c7013b3df6d2d9bf1f05936090a
	DESKTOP_SESSION=gnome-classic
	DIRSTACK=()
	DISPLAY=:0
	EUID=1000
	GDMSESSION=gnome-classic
	GDM_LANG=zh_CN.UTF-8
	GNOME_DESKTOP_SESSION_ID=this-is-deprecated
	GNOME_SHELL_SESSION_MODE=classic
	GPG_AGENT_INFO=/run/user/1000/keyring/gpg:0:1
	GROUPS=()
	HISTCONTROL=ignoredups
	HISTSIZE=1000
	HOME=/home/lbg
	HOSTNAME=192.168.8.132
	HOSTTYPE=x86_64
	IFS=$' \t\n'
	IMSETTINGS_INTEGRATE_DESKTOP=yes
	IMSETTINGS_MODULE=IBus
	LANG=zh_CN.UTF-8
	LESSOPEN='||/usr/bin/lesspipe.sh %s'
	LOGNAME=lbg
	LS_COLORS='rs=0:di=38;5;27:ln=38;5;51:mh=44;38;5;15:pi=40;38;5;11:so=38;5;13:do=38;5;5:bd=48;5;232;38;5;11:cd=48;5;232;38;5;3:or=48;5;232;38;5;9:mi=05;48;5;232;38;5;15:su=48;5;196;38;5;15:sg=48;5;11;38;5;16:ca=48;5;196;38;5;226:tw=48;5;10;38;5;16:ow=48;5;10;38;5;21:st=48;5;21;38;5;15:ex=38;5;34:*.tar=38;5;9:*.tgz=38;5;9:*.arc=38;5;9:*.arj=38;5;9:*.taz=38;5;9:*.lha=38;5;9:*.lz4=38;5;9:*.lzh=38;5;9:*.lzma=38;5;9:*.tlz=38;5;9:*.txz=38;5;9:*.tzo=38;5;9:*.t7z=38;5;9:*.zip=38;5;9:*.z=38;5;9:*.Z=38;5;9:*.dz=38;5;9:*.gz=38;5;9:*.lrz=38;5;9:*.lz=38;5;9:*.lzo=38;5;9:*.xz=38;5;9:*.bz2=38;5;9:*.bz=38;5;9:*.tbz=38;5;9:*.tbz2=38;5;9:*.tz=38;5;9:*.deb=38;5;9:*.rpm=38;5;9:*.jar=38;5;9:*.war=38;5;9:*.ear=38;5;9:*.sar=38;5;9:*.rar=38;5;9:*.alz=38;5;9:*.ace=38;5;9:*.zoo=38;5;9:*.cpio=38;5;9:*.7z=38;5;9:*.rz=38;5;9:*.cab=38;5;9:*.jpg=38;5;13:*.jpeg=38;5;13:*.gif=38;5;13:*.bmp=38;5;13:*.pbm=38;5;13:*.pgm=38;5;13:*.ppm=38;5;13:*.tga=38;5;13:*.xbm=38;5;13:*.xpm=38;5;13:*.tif=38;5;13:*.tiff=38;5;13:*.png=38;5;13:*.svg=38;5;13:*.svgz=38;5;13:*.mng=38;5;13:*.pcx=38;5;13:*.mov=38;5;13:*.mpg=38;5;13:*.mpeg=38;5;13:*.m2v=38;5;13:*.mkv=38;5;13:*.webm=38;5;13:*.ogm=38;5;13:*.mp4=38;5;13:*.m4v=38;5;13:*.mp4v=38;5;13:*.vob=38;5;13:*.qt=38;5;13:*.nuv=38;5;13:*.wmv=38;5;13:*.asf=38;5;13:*.rm=38;5;13:*.rmvb=38;5;13:*.flc=38;5;13:*.avi=38;5;13:*.fli=38;5;13:*.flv=38;5;13:*.gl=38;5;13:*.dl=38;5;13:*.xcf=38;5;13:*.xwd=38;5;13:*.yuv=38;5;13:*.cgm=38;5;13:*.emf=38;5;13:*.axv=38;5;13:*.anx=38;5;13:*.ogv=38;5;13:*.ogx=38;5;13:*.aac=38;5;45:*.au=38;5;45:*.flac=38;5;45:*.mid=38;5;45:*.midi=38;5;45:*.mka=38;5;45:*.mp3=38;5;45:*.mpc=38;5;45:*.ogg=38;5;45:*.ra=38;5;45:*.wav=38;5;45:*.axa=38;5;45:*.oga=38;5;45:*.spx=38;5;45:*.xspf=38;5;45:'
	MACHTYPE=x86_64-redhat-linux-gnu
	MAIL=/var/spool/mail/lbg
	MYVIMRC=/home/lbg/.vim/vimrc
	OPTERR=1
	OPTIND=1
	OSTYPE=linux-gnu
	PATH=/usr/lib64/qt-3.3/bin:/usr/local/bin:/usr/local/sbin:/usr/bin:/usr/sbin:/bin:/sbin:/home/lbg/.local/bin:/home/lbg/bin
	PPID=27730
	PS4='+ '
	PWD=/home/lbg/biji
	QTDIR=/usr/lib64/qt-3.3
	QTINC=/usr/lib64/qt-3.3/include
	QTLIB=/usr/lib64/qt-3.3/lib
	QT_GRAPHICSSYSTEM_CHECKED=1
	QT_IM_MODULE=ibus
	SESSION_MANAGER=local/unix:@/tmp/.ICE-unix/2948,unix/unix:/tmp/.ICE-unix/2948
	SHELL=/bin/bash
	SHELLOPTS=braceexpand:hashall:interactive-comments
	SHLVL=3
	SSH_AGENT_PID=3112
	SSH_AUTH_SOCK=/run/user/1000/keyring/ssh
	TERM=xterm-256color
	UID=1000
	USER=lbg
	USERNAME=lbg
	VIM=/usr/share/vim
	VIMRUNTIME=/usr/share/vim/vim74
	VTE_VERSION=3804
	WINDOWID=35651591
	WINDOWPATH=1
	XAUTHORITY=/run/gdm/auth-for-lbg-dCU7vV/database
	XDG_CURRENT_DESKTOP=GNOME-Classic:GNOME
	XDG_MENU_PREFIX=gnome-
	XDG_RUNTIME_DIR=/run/user/1000
	XDG_SEAT=seat0
	XDG_SESSION_DESKTOP=gnome-classic
	XDG_SESSION_ID=1
	XDG_VTNR=1
	XMODIFIERS=@im=ibus
	_=/usr/bin/vim


## 查看进程
ps aux

	USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
	root         1  0.0  0.1 193752  6924 ?        Ss   6月06   0:25 /usr/lib/systemd/systemd --switched-root --system --deserialize 21
	root         2  0.0  0.0      0     0 ?        S    6月06   0:00 [kthreadd]
	root         3  0.6  0.0      0     0 ?        S    6月06   6:24 [ksoftirqd/0]
	root         5  0.0  0.0      0     0 ?        S<   6月06   0:00 [kworker/0:0H]
	root         7  0.0  0.0      0     0 ?        S    6月06   0:02 [migration/0]
	root         8  0.0  0.0      0     0 ?        S    6月06   0:00 [rcu_bh]
	root         9  1.4  0.0      0     0 ?        S    6月06  13:14 [rcu_sched]
	root        10  0.0  0.0      0     0 ?        S    6月06   0:08 [watchdog/0]
	root        11  0.0  0.0      0     0 ?        S    6月06   0:06 [watchdog/1]
	root        12  0.0  0.0      0     0 ?        S    6月06   0:01 [migration/1]
	root        13  0.0  0.0      0     0 ?        S    6月06   0:31 [ksoftirqd/1]
	root        15  0.0  0.0      0     0 ?        S<   6月06   0:00 [kworker/1:0H]


## yum 帮助
yum --help

	已加载插件：fastestmirror, langpacks
	Usage: yum [options] COMMAND

	List of Commands:

	check          检查 RPM 数据库问题
	check-update   检查是否有可用的软件包更新
	clean          删除缓存数据
	deplist        列出软件包的依赖关系
	distribution-synchronization 已同步软件包到最新可用版本
	downgrade      降级软件包
	erase          从系统中移除一个或多个软件包
	fs             Acts on the filesystem data of the host, mainly for removing docs/lanuages for minimal hosts.
	fssnapshot     Creates filesystem snapshots, or lists/deletes current snapshots.
	groups         显示或使用、组信息
	help           显示用法提示
	history        显示或使用事务历史
	info           显示关于软件包或组的详细信息
	install        向系统中安装一个或多个软件包
	langavailable  Check available languages
	langinfo       List languages information
	langinstall    Install appropriate language packs for a language
	langlist       List installed languages
	langremove     Remove installed language packs for a language
	list           列出一个或一组软件包
	load-transaction 从文件名中加载一个已存事务
	makecache      创建元数据缓存
	provides       查找提供指定内容的软件包
	reinstall      覆盖安装软件包
	repo-pkgs      将一个源当作一个软件包组，这样我们就可以一次性安装/移除全部软件包。
	repolist       显示已配置的源
	search         在软件包详细信息中搜索指定字符串
	shell          运行交互式的 yum shell
	swap           Simple way to swap packages, instead of using shell
	update         更新系统中的一个或多个软件包
	update-minimal Works like upgrade, but goes to the 'newest' package match which fixes a problem that affects your system
	updateinfo     Acts on repository update information
	upgrade        更新软件包同时考虑软件包取代关系
	version        显示机器和/或可用的源版本。


	Options:
	  -h, --help            显示此帮助消息并退出
	  -t, --tolerant        忽略错误
	  -C, --cacheonly       完全从系统缓存运行，不升级缓存
	  -c [config file], --config=[config file]
				配置文件路径
	  -R [minutes], --randomwait=[minutes]
				命令最长等待时间
	  -d [debug level], --debuglevel=[debug level]
				调试输出级别
	  --showduplicates      在 list/search 命令下，显示源里重复的条目
	  -e [error level], --errorlevel=[error level]
				错误输出级别
	  --rpmverbosity=[debug level name]
				RPM 调试输出级别
	  -q, --quiet           静默执行
	  -v, --verbose         详尽的操作过程
	  -y, --assumeyes       回答全部问题为是
	  --assumeno            回答全部问题为否
	  --version             显示 Yum 版本然后退出
	  --installroot=[path]  设置安装根目录
	  --enablerepo=[repo]   启用一个或多个软件源(支持通配符)
	  --disablerepo=[repo]  禁用一个或多个软件源(支持通配符)
	  -x [package], --exclude=[package]
				采用全名或通配符排除软件包
	  --disableexcludes=[repo]
				禁止从主配置，从源或者从任何位置排除
	  --disableincludes=[repo]
				disable includepkgs for a repo or for everything
	  --obsoletes           更新时处理软件包取代关系
	  --noplugins           禁用 Yum 插件
	  --nogpgcheck          禁用 GPG 签名检查
	  --disableplugin=[plugin]
				禁用指定名称的插件
	  --enableplugin=[plugin]
				启用指定名称的插件
	  --skip-broken         忽略存在依赖关系问题的软件包
	  --color=COLOR         配置是否使用颜色
	  --releasever=RELEASEVER
				在 yum 配置和 repo 文件里设置 $releasever 的值
	  --downloadonly        仅下载而不更新
	  --downloaddir=DLDIR   指定一个其他文件夹用于保存软件包
	  --setopt=SETOPTS      设置任意配置和源选项
	  --bugfix              Include bugfix relevant packages, in updates
	  --security            Include security relevant packages, in updates
	  --advisory=ADVS, --advisories=ADVS
				Include packages needed to fix the given advisory, in
				updates
	  --bzs=BZS             Include packages needed to fix the given BZ, in
				updates
	  --cves=CVES           Include packages needed to fix the given CVE, in
				updates
	  --sec-severity=SEVS, --secseverity=SEVS
				Include security relevant packages matching the
				severity, in updates
