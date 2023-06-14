## Linux中为Pycharm创建快捷方式

在Windows中，当我们安装软件时，安装程序往往会自动在桌面上添加快捷方式。而在Linux系统中不是这样的，Linux系统中装完软件往往不会创建快捷方式。

以[ubuntu](https://so.csdn.net/so/search?q=ubuntu&spm=1001.2101.3001.7020)系统中安装完Pycharm为例。![在这里插入图片描述](https://img-blog.csdnimg.cn/759669e7eb44449a84d91ecccc9a58af.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzU0NjIwMTc3,size_16,color_FFFFFF,t_70)
当我们安完软件后，需要在终端中用命令打开Pycharm![在这里插入图片描述](https://img-blog.csdnimg.cn/0bcefb243d1941fdaaff7e01ccec2c2b.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzU0NjIwMTc3,size_16,color_FFFFFF,t_70)
这样每次用命令打开程序很麻烦，所以我们要将它显示到所有应用中

步骤![List item](https://img-blog.csdnimg.cn/2606845e5e0245f2b19946fecab2dab8.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzU0NjIwMTc3,size_16,color_FFFFFF,t_70)

![在这里插入图片描述](https://img-blog.csdnimg.cn/80d6b2d0704140f5abdf9997532928f0.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzU0NjIwMTc3,size_16,color_FFFFFF,t_70)
可以安需求为所有用户创建（需要root密码）。点击OK，然后我们就可以在所有应用中找到Pycharm了。![在这里插入图片描述](https://img-blog.csdnimg.cn/6cb488c41c324c82b808733c718418f9.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzU0NjIwMTc3,size_16,color_FFFFFF,t_70)

我们可以在

> usr/share/applications

中找到应用的桌面配置文件![在这里插入图片描述](https://img-blog.csdnimg.cn/802508b1a0d14d7aa8ae09f33eafe5a8.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzU0NjIwMTc3,size_16,color_FFFFFF,t_70)
可以进行相关配置来修改快捷方式。