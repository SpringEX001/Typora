

# Pycharm安装在Linux系统中

### [Pycharm安装](https://so.csdn.net/so/search?q=Pycharm安装&spm=1001.2101.3001.7020)在Linux系统中

- [Pycharm安装在Linux系统中](https://blog.csdn.net/lifeisme666/article/details/122455961#PycharmLinux_1)
- - [1.下载安装包，linux的安装包是以.tar.gz格式的。](https://blog.csdn.net/lifeisme666/article/details/122455961#1linuxtargz_2)
	- [2.解压下载好的安装包并安装](https://blog.csdn.net/lifeisme666/article/details/122455961#2_5)
	- [3.使用安装好的pycharm运行一下自带的程序](https://blog.csdn.net/lifeisme666/article/details/122455961#3pycharm_17)
	- - - [报错了，错误信息为：Failed to create virtual environment](https://blog.csdn.net/lifeisme666/article/details/122455961#Failed_to_create_virtual_environment_18)
			- [原因是：ubuntu18.04默认没有安装setuptools](https://blog.csdn.net/lifeisme666/article/details/122455961#ubuntu1804setuptools_19)
			- [解决办法：在新的终端执行下面命令：](https://blog.csdn.net/lifeisme666/article/details/122455961#_20)
			- [然后运行程序](https://blog.csdn.net/lifeisme666/article/details/122455961#_25)
			- [又报错了，不要紧，选择一个python的解析器即可。由于上一次已经安装了Anacond，所以使用Anaconda创建虚拟环境，然后在Pycharm里自由切换环境即可。具体过程参考[利用Anaconda安装PyTorch并将Anaconda创建的虚拟环境添加到Pycharm中](https://blog.csdn.net/lifeisme666/article/details/122417518?spm=1001.2014.3001.5501)。](https://blog.csdn.net/lifeisme666/article/details/122455961#pythonAnacondAnacondaPycharmAnacondaPyTorchAnacondaPycharmhttpsblogcsdnnetlifeisme666articledetails122417518spm1001201430015501_27)
	- [4.设置启动图标](https://blog.csdn.net/lifeisme666/article/details/122455961#4_30)
	- - - [选择菜单Tools /Create Desktop Entry... ，设置任务栏启动图标。](https://blog.csdn.net/lifeisme666/article/details/122455961#Tools_Create_Desktop_Entry__31)
	- [5.卸载](https://blog.csdn.net/lifeisme666/article/details/122455961#5_37)
	- - - [安装过程出现任何错误可以卸载重装。](https://blog.csdn.net/lifeisme666/article/details/122455961#_38)
	- 



## Pycharm安装在Linux系统中

## 1.下载安装包，linux的安装包是以.tar.gz格式的。

[pycharm官方网站](https://www.jetbrains.com/pycharm/download/#section=linux)
![在这里插入图片描述](https://img-blog.csdnimg.cn/08c9ddd35ba046d6bce6346c3717b6f0.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5Zyo5LqO5o6i57Si,size_20,color_FFFFFF,t_70,g_se,x_16)

## 2.解压下载好的安装包并安装

```bash
tar zxf pycharm-community-2021.3.1.tar.gz 
cd pycharm-community-2021.3.1/bin
./pycharm.sh                                 ##运行pycharm安装脚本
123
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/8625270e64ee48ca826fb33b572c86f6.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/36ce0fa003524808b9f8abc3a03c5635.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5Zyo5LqO5o6i57Si,size_20,color_FFFFFF,t_70,g_se,x_16)
![在这里插入图片描述](https://img-blog.csdnimg.cn/2ca9835e14d54dd7b427de1053ae5968.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5Zyo5LqO5o6i57Si,size_20,color_FFFFFF,t_70,g_se,x_16)

## 3.使用安装好的pycharm运行一下自带的程序

#### 报错了，错误信息为：Failed to create virtual environment

#### 原因是：ubuntu18.04默认没有安装[setuptools](https://so.csdn.net/so/search?q=setuptools&spm=1001.2101.3001.7020)

#### 解决办法：在新的终端执行下面命令：

```bash
sudo apt install python3-setuptools
1
```

#### 然后运行程序

#### 又报错了，不要紧，选择一个python的解析器即可。由于上一次已经安装了Anacond，所以使用[Anaconda创建虚拟环境](https://so.csdn.net/so/search?q=Anaconda创建虚拟环境&spm=1001.2101.3001.7020)，然后在Pycharm里自由切换环境即可。具体过程参考[利用Anaconda安装PyTorch并将Anaconda创建的虚拟环境添加到Pycharm中](https://blog.csdn.net/lifeisme666/article/details/122417518?spm=1001.2014.3001.5501)。

![在这里插入图片描述](https://img-blog.csdnimg.cn/09fbd6c14f9344779f87ed7b171a603d.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5Zyo5LqO5o6i57Si,size_20,color_FFFFFF,t_70,g_se,x_16)

## 4.设置启动图标

#### 选择菜单Tools /Create Desktop Entry… ，设置任务栏启动图标。

![在这里插入图片描述](https://img-blog.csdnimg.cn/8c37cdec17fa48f3b74eff787dbc7610.png)![在这里插入图片描述](https://img-blog.csdnimg.cn/954aab59f12c49069491560967f4ae9d.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5Zyo5LqO5o6i57Si,size_19,color_FFFFFF,t_70,g_se,x_16)
![在这里插入图片描述](https://img-blog.csdnimg.cn/6da86213a1054bb18a008da0f16a1cee.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA5Zyo5LqO5o6i57Si,size_20,color_FFFFFF,t_70,g_se,x_16)

## 5.卸载

#### 安装过程出现任何错误可以卸载重装。

```bash
ls -a
rm -fr .PyCharmCE2021.3.1
```