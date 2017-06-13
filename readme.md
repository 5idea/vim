# study 

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

