MCC
===

Mail Control Computer

##目的：
本程序通过邮件控制电脑。

##原理：
Python使用Poplib库，周期性访问邮箱，根据邮件主题的相应名称执行对应的操作。

目前奴隶邮箱（Python检查的那个邮箱，简称奴隶邮箱）使用sina邮箱测试成功，其他邮箱未做测试。
主人邮箱（发送命令的邮箱称为主人邮箱），通过发送邮件给奴隶邮箱来控制操作。目前测试使用QQ邮箱与使用微信发送的QQ邮件能测试通过。
##配置
打开_config.ini文件:

* host填写奴隶邮箱的pop3服务器，例如新浪的pop3服务器为
	
		pop.sina.com

* username为奴隶邮箱的邮箱号
* password为奴隶邮箱的密码
* boss_email为主人邮箱号
* time_limit控制程序检查邮箱的评论，默认为300秒，也就是5分钟
* \<command\>与\</command\>之间为命令区，此处可以使用任何能在CMD命令提示符中执行的命令格式为：

		名字=命令
注意=左右不能出现空格

*  \<open_file\>\</open_file\>之间为可以打开的文件。任何在电脑上可以使用鼠标双击打开的程序、文件均可把其地址写在此处。格式为：

		名字=地址
注意=左右不能出现空格

##使用
使用主人邮箱往奴隶邮箱发送邮件，标题为_config.ini中的任一命令的名字。例如，使用邮件发送：music到奴隶邮箱，即可使电脑放音乐。

##编译
	python mysetup.py py2exe
