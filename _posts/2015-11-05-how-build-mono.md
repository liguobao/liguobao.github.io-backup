 从github上下载了mono的源码，然后打算编译了。
百度了一下教程，我去...居然没有教程。
换bing搜索一下，我去...还是没有。
关键字换一下：how to build mono on linux....嗯，结果还真出来一两个能看的。
http://www.linuxidc.com/Linux/2012-08/68198.htm 
http://www.codeproject.com/Articles/769292/How-to-build-Mono-on-Windowshttp://www.codeproject.com/Articles/769292/How-to-build-Mono-on-Windows
 
借鉴一下。心急的喵当然直接就 ./autogen.sh 咯,很明显华丽丽报错咯。
喵了一眼报错信息，有几个编译环境没有配置，开始一步一步配置吧。
图片

apt-get install autoconf
apt-get install libtool 
apt-get install automake

安装完毕上面三个编译环境，开工。
cd mono-master/
然后
./autogen.sh
华丽丽开始不断滚动....

图片

图片

好像编译完了，赶紧ls看看。

图片
好像确实多了不少东西，对比第一次的图就知道了。
哎呀，看到期待已久的configure了！！！
还好linux基础没有全部还给老师！果断继续！
输入./configure

华丽丽的滚动条又出来了！！
图片

图片

漂亮! 
ls 看看！

图片
啦啦啦，终于看到makefile了！！！

嗯嗯，先make一下！
输入make咯。
又滚动起来了！
图片
上次make了好像好几分钟，看起来好像没什么问题！等等看咯。
图片 
还在跑....
嗯，终于完了....
我去，为嘛有好几个error！！！我去，什么鬼。
图片

build/deps/basic-profile-check.out 这个鬼的时候开始报错，百度看看什么回事。
http://图片
 http://
英语太渣，直接先去看了张老师....那个，很明显然并卵。
咦，居然有一个stackoverflow的问答，据说这个高大上哦，去喵一眼看看。 
http://stackoverflow.com/questions/20797283/compiling-mono-3-x-on-raspberry-pi



图片

图片

好像看到了解决方案....
试一下make get-monolite-latest。开始下载好多文件....
然后又开始了一轮make。额，为嘛还是报错。

回去再看看回答。

这个是不是有个Keep cloning from git, but use make get-monolite-latest command before make. More detailshere.
那里不是有个链接么？点进去看看会死啊！逗逼！
图片
唉，喵你太逗比了。好好看文档再搞不行么？

清理一下之前的文件，make clean

重新make中。
图片
好像还是少点东西，感觉这次编译还是要跪。
果然是跪了...滚回去看看说明文档。

$ cd mono  
$ ./autogen.sh --prefix=/usr/local  
$ make  
$ make install

喵，你脑子傻了啊，少了参数你都不知道！.....
喵喵喵！ 
继续等.... 

额，感觉是下载的文件有问题，还是去官网重新下一个吧。

wget http://download.mono-project.com/sources/mono/mono-4.2.0.207.tar.bz2

解压一下。

$ cd mono  
$ ./autogen.sh --prefix=/usr/local  
$ make  
$ make install
正在等待.......

 图片
终于编译成功了。
make一下，make ok！
make install。