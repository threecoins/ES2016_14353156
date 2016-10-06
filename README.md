# ES2016_14353156
## LAB2: DOL开发环境配置笔记

### Description
>The definition of DOL(Distributed Operation Layer) : 
>
>The distributed operation layer (DOL) is a software development framework to program parallel applications. The DOL allows to specify applications based on the Kahn process network model of computation and features a simulation engine based on SystemC. Moreover, the DOL provides an XML-based specification format to describe the implementation of a parallel application on a multi-processor systems, including binding and mapping.

### DOL 安装笔记
>#### 1.安装一些必要的环境
>$	sudo apt-get update
>
>$	sudo apt-get install ant
>
>$ 	sudo apt-get install openjdk-7-jdk
>
>$	sudo apt-get install unzip

>#### 2.下载文件
>$	sudo wget http://www.accellera.org/images/downloads/standards/systemc/systemc-2.3.1.tgz
>
>$	sudo wget http://www.tik.ee.ethz.ch/~shapes/downloads/dol_ethz.zip

>#### 3.解压文件
>$	mkdir dol #新建dol的文件夹 
>
>$	unzip dol_ethz.zip -d dol #将dolethz.zip解压到 dol文件夹中
>
>$	tar -zxvf systemc-2.3.1.tgz　#解压systemc

>#### 4.编译systemc
>$	cd systemc-2.3.1 #解压后进入systemc-2.3.1的目录下
>
>$	mkdir objdir #新建一个临时文件夹objdir
>
>$	cd objdir #进入该文件夹objdir
>
>$	../configure CXX=g++ --disable-async-updates #运行configure(能根据系统的环境设置一下参数，用于编译)
>
>![](http://p1.bpimg.com/567571/175af1fb7586b8f1.jpg)
>
>$	sudo make install #编译systemc
>
>$ cd ..
>
>$ ls
>
>![](http://i1.piimg.com/567571/9a1b787871352df2.jpg)
>
>$	pwd #输出当前的工作路径


>#### 5.编译dol
>$	cd ../dol #进入刚刚dol的文件夹并修改build_zip.xml文件
>
>$	ant -f build_zip.xml all #若成功会显示build successful
>
>![](http://i1.piimg.com/567571/d918af918216ba2a.jpg)
>
>$	cd build/bin/main
>
>$	ant -f runexample.xml -Dnumber=1 #运行第一个例子
>
>![](http://i1.piimg.com/567571/d612582f1bae0480.jpg)

### 实验感想
>安装DOL过程中遇到的问题大多是因为自己对ubuntu的不熟悉，虽然只是安装，对DOL的体会或许还不够，但安装过程中却加深了对虚拟机使用的熟悉程度。至于实验二，其实也就是熟悉一下git语句和markdown的使用，目前还都只是探索，相对还是比较轻松。



