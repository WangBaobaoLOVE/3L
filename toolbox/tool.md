## 工具箱

|工具名|作用|操作系统|网站|安装的说明|
|----|----|----|----|----|
|Dia|流程图工具|ubuntu||[安装](#Dia)|
|GIMP|图像处理|ubuntu|[主页](http://www.gimp.org/)|[安装](#GIMP)|
|natapp|内网穿透|window/ubuntu/macOS|[主页](https://natapp.cn/)|[安装](#natapp)|
|||||
|||||

### Dia

[参考](https://www.cnblogs.com/yibeimingyue/p/11843963.html)

linux下一款不错的流程图工具：dia。

#### 安装
1. 打开终端(快捷键：ctrl+alt+t)。
2. 输入命令：`sudo apt-get install dia`

#### 卸载
1. sudo apt-get autoremove dia

#### 无法输入中文吗？

Input Methods-->x input method

此时有可能发现还是无法使用中文输入，原因可能是因为打开.dia文件的时候，直接右键打开了。所以，此时应该在命令行输入：

$ dia

打开dia软件之后，再打开所要打开的.dia文件。

### GIMP

#### 安装

1. sudo apt-get install gimp

#### 安装插件

1. sudo apt-get install gimp-plugin-registry gimp-data-extras

|插件|描述|
|----|----|
|gimp-data-extras |	刷子/调色板/渐变色的GIMP插件集|
|gimp-gmic |	用于《GREYC魔术图像转换软件》的GIMP插件|
|gimp-gutenprint |	GIMP的打印插件|
|gimp-plugin-registry |	GIMP的可选扩展库|
|gvfs-backends |	用户空间虚拟文件系统-后端|
|xcftools |	命令行工具，用于XCF文件的额外数据|
|gimp-gap |	gif动态图制作插件|
|mathmap	|制作德罗斯特效应插件|


### natapp

[参考]https://blog.csdn.net/misterdongjing/article/details/85068205)
#### 安装

1. 下载安装包
`wget http://download.natapp.cn/assets/downloads/clients/2_3_4/natapp_linux_386_2_3_4.zip`
2. 解压文件`unzip natapp_linux_386_2_3_4.zip`
3. 给natapp执行权限`chmod a+x natapp`

#### 配置隧道——[natapp官网](https://natapp.cn/)

### 启动

**方案一：** 不能关闭运行窗口。
```
./natapp -authtoken=上一步申请的token
```

**方案二：**可以关闭运行窗口，转为后台运行。

[官网参考:linux后台运行natapp(ngrok)教程](https://natapp.cn/article/nohup)