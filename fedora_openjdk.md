#fedora24 安装openjdk1.7
****
openjdk 下载地址
> [http://rpmfind.net/linux/rpm2html/search.php?query=java-1.7.0-openjdk-devel&submit=Search+...&system=&arch=](URL)

安装使用rpm --nodeps -ivh进行
> sudo rpm --nodeps -ivh java-1.7.0-openjdk-1.7.0.121-2.6.8.1.el6_8.x86_64.rpm
> 
> sudo rpm --nodeps -ivh java-1.7.0-openjdk-devel-1.7.0.121-2.6.8.1.el6_8.x86_64.rpm

删除时先查看已安装的JDK
> rpm -qa| grep jdk

使用rpm -e 删除对应的JDK
> sudo rpm -e java-1.7.0-openjdk-devel-1.7.0.121-2.6.8.1.el6_8.x86_64

openjdk切换方法
> alternatives --config javac

> alternatives --config java

> 然后先择版本


****
#Android 源码国内静像下载
****
参考网址如下
> [http://blog.csdn.net/song19891121/article/details/50099857](URL)

安装git完成之后，需要对Git进行配置，设置git的电子邮件和用户名。
> git config --global user.email "你的电子邮件地址"
> git config --global user.name "你的名字"

新建一个bin目录
> mkdir ~/bin

将bin目录写入环境变量（这样你在任何目录下都可以访问）
> PATH=~/bin:$PATH

轮到curl工具了，我们使用curl工具下载repo，并将其放置到bin目录
> curl https://storage-googleapis.lug.ustc.edu.cn/git-repo-downloads/repo > ~/bin/repo

更改repo权限
> chmod a+x ~/bin/repo

接下来新建一个目录，用于放置Android源码（我先执行一下pwd命令，大家看看我的当前的目录），并进入该目录，如下：
> mkdir android

> cd android

接下来我们初始化仓库
> repo init -u git://mirrors.ustc.edu.cn/aosp/platform/manifest

接下来这一步就是从服务器取代码了，如果你只想下载特定的android版本，可以使用如下命令：
>repo init -u git://mirrors.ustc.edu.cn/aosp/platform/manifest -b Android版本

Android 版本可以参考这个网址
> [https://source.android.com/source/build-numbers.html#source-code-tags-and-builds](URL)

下载全部代码，运行命令：
> repo sync
****
