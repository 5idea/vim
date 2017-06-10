# my git study 

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

