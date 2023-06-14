# Chromebook linux 容器配置(一) ：中文环境



此文简单易懂，让没碰过的同志们也能轻松上手linux容器，话不多说，跟着复制粘贴吧。



## 0.启用Linux容器

首先，打开设置，然后高级-开发者-Linux开发环境启用-启用，建议20个g起步，后期也能随便调整。

![img](https://image.coolapk.com/feed/2023/0425/16/13344612_bd3a2f17_1661_3657_186@1234x991.png.m.jpg)

![img](https://image.coolapk.com/feed/2023/0425/16/13344612_da7c46a2_1661_3662_162@820x607.png.m.jpg)

成功后，就像这个样子



## 1.换源和设置中文环境

#### 1.1 更新软件源及应用程序

```text
sudo apt update
sudo apt upgrade
sudo apt install nano
```

#### 1.2换源

> nano是Unix和类Unix系统中的一个文本编辑器，是Pico的复制品（clone）。nano的目标是类似Pico的全功能但又易于使用的编辑器。同类的还有vim、vi等，这里选用最容易最好上手的nano。

- 输入`sudo nano /etc/apt/sources.list`

- 在文件现有的每一行前面插入`#`符号以注释

- 另起一行，将国内镜像源的地址复制进去您可以在浏览器中复制，再在 nano编辑窗口中**右键**以粘贴。

![img](https://image.coolapk.com/feed/2023/0425/16/13344612_c769732d_1661_3666_588@1920x1080.png.m.jpg)

- 然后「Ctrl+O」保存，「Ctrl+X」退出。
	[查看链接](https://www.cnblogs.com/liuguanglin/p/debian11_repo.html)，这里可替换国内源，可以ping一下试试速度。换国内源是为了更快的下载速度。

#### 1.3设置中文环境

- 接下来将linux容器语言环境设置为中文。

	```text
	sudo apt install fonts-wqy-microhei fonts-wqy-zenhei
	sudo dpkg-reconfigure locales
	```

- 接着会跳出图形化选择菜单，按几次 Page Down 键到末尾，找到「zh_CN.UTF-8 UTF-8」，按空格键选中，按回车键进入下一级菜单，然后将光标移动到「zh_CN.UTF-8」，然后回车。

- 回到桌面，按下 「Ctrl+Alt+T」 进入 crosh
	输入下列代码重启 Termina VM

	```text
	vmc stop termina
	vmc start termina
	```

	

## 2. 安装中文输入法

#### 2.1安装Fcitx输入工具

> 仅仅在 Linux 子系统中显示中文是不够的，由于不能使用系统输入法，所以如果想要在 Linux 子系统中输入中文，那么还需要安装中文输入法。

依次执行以下命令

```
sudo apt install fcitx fcitx-lib*
sudo apt install fcitx-googlepinyin
```

#### 2.2配置输入设备

```
im-config
```

在跳出来的窗口，按顺序点击确定 -> Yes -> 选择 fcitx -> 确定 -> 确定。



## 3. 配置中文输入法

#### 3.1 启用中文输入法

- 输入`fcitx && fcitx-configtool`并回车
- 点击左下角的 + ,勾选not only，选择谷歌的拼音输入法。
- 在弹出窗口的底部菜单栏中找到「向上箭头」图标，多次点击，将「拼音(LibPinyin)」移至第二位
- 关闭弹出窗口

#### 3.2设置全局变量

```text
sudo nano /etc/environment
```

- 加入以下

	```text
	GTK_IM_MODULE=fcitx
	QT_IM_MODULE=fcitx
	XMODIFIERS=@im=fcitx
	SDL_IM_MODULE=fcitx
	GLFW_IM_MODULE=ibus
	```

	用Ctrl+O保存，Ctrl+X退出。

- 然后配置fcitx开机自启动
	`sudo nano ~/.sommelierrc`
- 最底部添加
	`/usr/bin/fcitx-autostart`
	用Ctrl+O保存，Ctrl+X退出。
- 好了，现在你已经配置好你的中文环境了，重启一下就行。
	另外说一些要点吧，chromeos的linux容器非常精简，缺库很常见，用的还是wayland，所以很容易软件打不开一类的，这里我教你，把下载好的文件用移动到linux文件中，然后用
	`sudo apt install ./xxx.deb`（你下载的包名，./后面你输入的包名前两三个字母然后按tab键就会自动补全）。`install ./`这个可以帮你自动补依赖，很方便和很好用，别再dpkg -i装了。



## 4. 参考文献

[查看链接](https://sslover.me/2022/05/15/use-zh-cn-locale-in-linux-on-chromebook/)
[查看链接](https://wiki.archlinuxcn.org/zh/Fcitx5)
[查看链接](https://fydeos.com/docs/knowledge-base/)

