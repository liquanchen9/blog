# 简单的jemeter之旅 #
====================
## 基本目的：jekins 利用 ant 调用jemeter ##
--------------------


## 基本环境 ##
--------------------
* jekins
* ant
* jmeter


## 基本原理分析 ##
--------------------
要调用就要在jekins安装的机器上也安装这个2个软件，当然ant jekins会自己下载 ，但是jmeter就不会了。我们可以自己下载到jekins安装的机器里去。
都安装好了调用逻辑就比较清晰了， jekins中在build构建步骤设置里就可以添加 ant构建器
![jekins截图](/images/image.png "jekins里ant 调用截图")
相信用过jenkins的都知道 上图是用来构建项目的 步骤设置！
那么 ant怎么调jmeter呢？ 按照ant 基本结构是 先要有依赖jar路径；这里我们需要时候再指定就好了；然后就是ant执行文件build.xml文件？
怎么写呢？其实不用着急 ，jmeter提供我们ant调用的方法老规矩看官看下图
![jmeter截图](/images/45.png "jmeter示例截图")                
jmeter写的这build.xml文件都能干嘛？ 这应该就是我们的重点了。只有明白了这个build文件我没就能调用了jmeter了.

## jmeter/extras下build.xml ##
---------------------
先运行一把
![jmeter截图](/images/49.png "jmeter示例截图")
失败了！但可以看到 一个重要的信息  指定了一个 Test.jmx 的文件。jmx文件 这个相信用过jmeter的人都知道怎么来的吧！
这个文件的位置就在extras目录下面，我们看看它写的是什么吧!
![Test.jmx截图](/images/201.png "Test.jmx示例截图")
调用了java代码随便测试了一下而已。。
