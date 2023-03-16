# Android Studio Q&As

*只会给出基本的步骤，操作指导过程写得比较简略。*

## Android Studio中SDK缺失问题

安装SDK，步骤如下：
1. 安装Android SDK，可到此网站下载[SDK Tools](https://www.androiddevtools.cn/)；
2. SDK Tools需要JDK，所以记得到[Java官网](https://www.oracle.com/java/technologies/downloads/)下载JDK并安装；
3. 安装SDK Tools，注意安装路径不要有空格；
4. （此步可跳过）启动SDK Manager，选择对应版本进行安装（在Packages点击License，然后点击右侧Accept License后，再点击按钮Install，然后静待下载安装）；
5. 在Android Studio-File-Settings-Appearance & Behavio-System Settings-Android SDK中指定SDK的路径。


## HAXM is not install

在创建虚拟设备时，如果出现这种提醒，在
1. Settings --> Appereance & Behavior --> System Settings --> Android SDK中，选择SDK Tools
2. 在下面的列表中找到：Intel X86 Emulator Accelerator (HAXM installer)，选择并安装。
3. 如果安装安装失败，有如下几种可能：
   1. 你的电脑是否是Intel的CPU？如果是AMD，是不支持的。 
   2. 如果是Intel的CPU，如果还是无法使用，有可能是硬件没有配置好。重启电脑，进去BIOS界面，在`Advanced`-`CPU Setup`中，将`Intel Virtual Technology`的选项改为`Enabled`，记得保存后再退出。
   3. 如果是Intel的CPU，也有可能是不支持的。

参考：
* [https://github.com/intel/haxm/wiki/Installation-Instructions-on-Windows](https://github.com/intel/haxm/wiki/Installation-Instructions-on-Windows)
* [https://github.com/intel/haxm/wiki/Windows-System-Configurations](https://github.com/intel/haxm/wiki/Windows-System-Configurations)


## 如果点击Run，但虚拟机上没能自动启动，怎么办？

1. 检查AndroidManifest.xml中，是否制定了主Activity的LAUCHER？
2. 确认app --> build.gradle 文件里面的CompileSdk参数指定的版本，在File-->Settings-->Appereance & Behavior-->System Settings-->Android SDK-->SDK Platform中是否安装了对应Android API level版本？
3. 在Run-->Edit Configurations-->Android App-->app-->Launch Options-->Launch:中是否选择了Default Activity？

