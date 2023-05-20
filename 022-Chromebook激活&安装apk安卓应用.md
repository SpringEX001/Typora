# [Chromebook激活&安装apk安卓应用 | Lenovo 10e与Lenovo duet玩机指南](https://www.cnblogs.com/izcat/p/17076423.html)

最近在家对门收了一台联想Chromebook平板，第一次接触Linux平板，在激活登录和安装应用方面踩了一些坑。
本文记录一下设备登录方法、开发者模式开启以及该平板的折腾方式，方便玩机爱好者更快开启新世界大门。

## ChromeOS

Linux平板在国内是十分小众的存在，相比Surface设备更为罕见。
ChromeOS是谷歌推出的基于Linux的系统，应用生态围绕Chrome浏览器和谷歌的各类应用。
虽然后续增加了安卓应用的支持，并引入谷歌Play商店，默认情况下只能安装Play上的安卓应用。

## 设备登录

ChromeBook的核心在于Chrome浏览器和丰富的扩展插件，配合Linux环境也能用于开发，高度依赖网络环境。
激活该设备需要一个谷歌账号，由于国内无法使用谷歌，需要合理的kē xué-Surfing环境。

登录步骤：

1. 笔记本kē xué-Surfing
2. 开启热点分享
3. ChromeBook开机
	连接Wifi => 登录账号 => 同意条款 => 开始使用

- 本人fān-qiáng使用Clash，在网站**ikuuu.club**注册登录，参考下载和教程，可获得免费50G流量（每月）

- win11系统，搜索移动热点，分享到WLAN。实测直接使用Wifi连接，登录账号后会卡在加载条款阶段

- 参考

	知乎方法

	，在电脑端Clash设置代理端口

	- 打开Clash的Allow Lan ，让Clash允许局域网连接
	- 电脑进入cmd，输入ipconfig找到电脑本机的IPv4地址，例如192.168.127.1
	- 记下Clash界面的Port端口数值（在SSR中，是看本地端口，例如本地端口是1125）
	- 平板连接上热点，并进入WiFi的详细设置界面
	- 选项`代理`打开，勾选`允许共享网络使用代理`，连接类型选择`手动配置代理`，
		勾选`对所有协议使用同一代理`， 在下列代理中填上192.168.127.1，端口改为1125，保存

- 设置完毕后，平板所连接的网络相当于**直接**使用电脑的kē xué-Surfing环境

## 应用安装

查阅官方文档，只提供了谷歌Play的安装渠道。如何突破这一限制呢？

### 方法一 Linux下使用adb命令

这是网上大多数博客给出的常见解决方法。

第一步，打开设置-高级-开发者-Linux开发环境，点击启用，默认分配10GB的硬盘空间。然后进入开发Android应用，启用adb调试。
第二步，下载需要安装的应用apk文件，默认保存在`下载内容`目录下，长按设置Linux文件共享。Linux环境下的共享目录路径为`/mnt/chromeos/xxx`
第三步，打开Linux窗口，进入到安装文件路径，输入 `adb install xxx.apk`，稍等一下安装完成。
若提示没有adb命令，则使用 `sudo apt-get install adb`安装。

### 方法二 开启开发者模式（Develop Mode）

本人的平板在重置后，始终无法开启Linux开发环境，在安装Linux容器步骤失败，错误码查阅无果，最终放弃。

激活谷歌Play后，直接点击apk文件会提示需要开启`Develop Mode`安装应用。
网上可以查阅到大量如何开启ChromeOS开发者模式的方法，但Lenovo Chromebook 10e本身不同于一般的Chromebook是包含键盘的笔记本形态，
因此大多数使用键盘按键的教程是不可行的（系统在开机自检可能跳过USB设备），即便在连接了扩展坞和外设情况下。

经过一番摸索，整理出正确开启步骤如下。

1. 关机
2. 同时长按 关机、音量+、音量- 三个按键，等待约10秒
3. 【重点】此时进入启动菜单，提示插入USB恢复系统，【同时按下音量+、音量-】
4. 第三步正确操作后，会看到除了【关机、调试信息、取消三个选项】额外的取消系统验证选项
	![img](https://img2023.cnblogs.com/blog/1446954/202301/1446954-20230130154302066-1927360899.png)
5. 然后选择从内部磁盘启动
	![img](https://img2023.cnblogs.com/blog/1446954/202301/1446954-20230130153852671-679097040.png)
6. 稍安勿躁，等待约3分钟系统重启后，设备切换到开发者模式并重置
7. 重新登录设备，参考前述步骤

如果需要恢复到正常模式，只需重新启动并使用音量键从启动屏幕中选择开启系统验证。

## 玩机指南

Chrome插件：

- AdBlock/AdBlock Plus，广告拦截
- Global Speed，视频播放速度控制
- Tempermonkey，油猴脚本，安装VIP插件
- IDM，多线程下载
- 侧边翻译
- EasyScholar/EasyPubMed，高效学术
- ...

摸鱼网站：

- 知乎 zhihu.com/explore（免登录）
- IT之家 ithome.com
- B站 bilibili.com
- 腾讯视频 v.qq.com
- 爱奇艺 aqiyi.com
- 芒果TV mgtv.com
- 电影 btnull（懂的都懂）
- 摸鱼 mo.fish
- 购物 jd.com、tmall.com、mobile.yangkeduo.com
- 折扣 smzdm.com
- ...

安卓应用：

- BBLL 第三方b站，适合TV/平板
- 静读天下 电子书阅读器，支持epub、PDF等各类格式
- ReadEra 官方市场中支持epub、PDF的免费阅读器
- ...

## Have Fun

![img](https://img2023.cnblogs.com/blog/1446954/202301/1446954-20230130160155161-1680863009.png)

![img](https://img2023.cnblogs.com/blog/1446954/202301/1446954-20230130160712178-1469128982.png)

![img](https://img2023.cnblogs.com/blog/1446954/202301/1446954-20230130160836437-917888611.png)

------

（完）