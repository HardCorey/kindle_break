# Kindle 越狱和常用软件安装
记录 Kindle 越狱和资料，大部分内容来源于网页：[bookfere](https://bookfere.com/post/1075.html)，请参考原网页获取最新信息，这里只做备份，防止原网页失联。  
使用的 Kindle 为 2015 年款 kpw3，固件版本为 5.16.2.1.1，亲测可行。

## 目录
  - [先决条件](#----)
  - [准备工作](#----)
  - [下载软件](#----)
  - [越狱步骤](#----)
    + [1. 进入演示模式](#1-------)
    + [2. 选择语言越狱](#2-------)
  - [如何正确的重置 Kindle](#--------kindle)
  - [插件安装](#----)
    + [MobileRead Package Installer (MRPI) — 插件安装器](#mobileread-package-installer--mrpi---------)
    + [KUAL — 插件程序启动器](#kual----------)
    + [Koreader — 第三方电子书阅读器](#koreader------------)
    + [Koreader 字体](#koreader---)
    + [Koreader 词典](#koreader---)
    + [Kindle 词典](#kindle---)


## 先决条件
Kindle 固件版本小于等于 5.16.2.1.1。如果你的 Kindle 固件版本小于此版本，建议先升级到 5.16.2.1.1，以增加成功越狱的概率。

## 准备工作
- 备份 documents 文件夹；
- 为避免避免固件自动更新，请务必删除 Kindle 根目录中扩展名为 .bin 的固件文件或名为 update.bin.tmp.partial 未下载完成的固件文件；
- 确保你的 Kindle 没有设置密码保护。如果忘记密码可在密码输入框中输入 111222777 重置 Kindle（注意这会删除 Kindle 设备中的所有用户资料）。

## 下载软件
LanguageBreak：[GitHub 发布页](https://github.com/notmarek/LanguageBreak/releases) 。
解压缩后你会得到如下所示结构的文件夹，包含了本文步骤所需要的所有文件。
```
.
├── DEVICES.txt
├── LanguageBreak
│   ├── DONT_CHECK_BATTERY
│   ├── documents
│   │   └── dictionaries
│   │       ├── a; export SLASH=$(awk 'BEGIN {print substr(ARGV[1], 0, 1)}' ${PWD}); sh ${SLASH}mnt${SLASH}us${SLASH}jb
│   │       └── amisane
│   ├── jb
│   └── patchedUks.sqsh
├── README.MD
├── update_hotfix_languagebreak-de-DE.bin
├── update_hotfix_languagebreak-en-GB.bin
├── update_hotfix_languagebreak-en-US.bin
├── update_hotfix_languagebreak-es-AR.bin
├── update_hotfix_languagebreak-es-CL.bin
├── update_hotfix_languagebreak-es-CO.bin
├── update_hotfix_languagebreak-es-ES.bin
├── update_hotfix_languagebreak-es-MX.bin
├── update_hotfix_languagebreak-fr-CA.bin
├── update_hotfix_languagebreak-fr-FR.bin
├── update_hotfix_languagebreak-it-IT.bin
├── update_hotfix_languagebreak-ja-JP.bin
├── update_hotfix_languagebreak-nl-NL.bin
├── update_hotfix_languagebreak-pt-BR.bin
├── update_hotfix_languagebreak-ru-RU.bin
└── update_hotfix_languagebreak-zh-Hans-CN.bin
```
## 越狱步骤
### 1. 进入演示模式
1. 进入 Kindle 界面并在上方的搜索框中输入 ;enter_demo 并按回车；
2. 通过点击 Kindle 菜单中的【重新启动】重启 Kindle 使其进入演示模式；
3. 跳过 WiFi 设置，在“注册演示样机”表单中输入任意字符并点击【继续】；
4. 在出现的“正在获取可选的演示类型”界面中点击【跳过】后点击【Standard】；
5. 接下来会进入“演示模式：添加内容”界面，直接点击【完成】让设备完成自动配置；
6. 自动配置期间可能会白屏一段时间，完成后会进入屏保界面，点击进入“配置设备”界面；
7. 使用“秘密手势”跳过该界面进入图书馆界面。秘密手势的操作方法参考以下说明。
8. 秘密手势的具体操作方式，不同人的感受有所不同，以下是常见的三种方式，你可以自行尝试：
   - 双指轻点一下屏幕右下角，紧接着单指按下从右向左水平滑动一段距离（如下图所示）。
   - 双指同时点按住屏幕右下角，随后右边手指抬起，紧接着左边手指向左水平滑动一段距离。
   - 双指同时点按住屏幕右下角，直接向左滑动一段距离。
   - 双指轻点一下屏幕右下角，紧接着单指按下从右向左水平滑动一段距离（如下图所示）。
   - 双指同时点按住屏幕右下角，随后右边手指抬起，紧接着左边手指向左水平滑动一段距离。
   - 双指同时点按住屏幕右下角，直接向左滑动一段距离。
![操作手势](kindle-jailbreak-secret-gesture.gif "操作手势")

注意，在之后的操作中，只要出现带有“展示机无内容或未连接网络（This demonstration device is either missing content or is disconnected from the network）”、“配置设备（CONFIGURE DEVICE）”字样的界面，都同样需要用这里介绍的秘密手势跳过才能继续操作。  
如果在进行以上步骤的过程中弹出了“Collecting Debug Info”提示框，说明你正在以错误的方式重试越狱步骤，请参考【如何正确的重置 Kindle】部分所提供的方法重置 Kindle 后再重新操作。

### 2. 选择语言越狱
1. 点击 Kindle 界面上方的搜索框输入 ```;demo``` 按回车进入“演示菜单”界面；
2. 点击【导入内容】按钮，然后用 USB 数据线将 Kindle 连到电脑；
3. 将 LanguageBreak 文件夹中如下所示的文件夹和文件拷贝到 Kindle 根目录：
```
├── documents
├── DONT_CHECK_BATTERY
├── jb
└── patchedUks.sqsh
```
4. 弹出并断开 USB 设备，点击【完成】按钮重新进入“演示菜单”界面；
5. 依次点击【销售设备 → 销售】按钮，稍等片刻等待“Kindle 按钮示意图”出现；
6. 一旦屏幕出现“Kindle 按钮示意图”，**立刻使用 USB 数据线将 Kindle 连到电脑**；
7. 再次将 LanguageBreak 文件夹中的四项内容拷贝到根目录，覆盖已存在文件；
8. 弹出并断开 USB 设备，按示意图所示，按下 Kindle 按钮重启 Kindle 设备；
9. 正常情况下，重启后会出现语言选择界面，依次点击【简体中文 → 下一步】；
10. Kindle 屏幕应会出现越狱相关的日志信息（如下图所示），重启后进行下一步。
    ![越狱信息](kindle-jailbreak-information.png "越狱信息")
11. [若进入演示模式] 上一步完成后，Kindle 会自动重启并进入正常模式，但是如果重启后仍然会进入演示模式：
    - 在 Kindle 界面上方的搜索框中输入 ```;uzb``` 并按回车激活演示模式的 USB 传输功能；
    - 用 USB 数据线将 Kindle 连电脑，将与你当前 Kindle 界面语言相对应的热修复补丁文件 update_hotfix_languagebreak-xx-XX.bin（如美式英语 en-US）拷贝到 Kindle 根目录；
    - 弹出并断开 USB 设备，在 Kindle 上方的搜索框中输入 ```;dsts``` 按回车，然后点击设置界面中的，或菜单中的【更新您的 Kindle】安装热修复补丁，Kindle 此时会自动重启。
    - 重启后 Kindle 会退出演示模式并做一些清理工作，至此全部越狱步骤完毕。
12. [若非演示模式] 出现 Kindle 界面后用 USB 数据线将 Kindle 连电脑
    - 将与你当前 Kindle 界面语言相对应的热修复补丁文件 update_hotfix_languagebreak-xx-XX.bin 拷贝到 Kindle 根目录；
    - 依次点击菜单【设置 → 更新您的 Kindle】安装热修复补丁；
    - 重启后全部越狱步骤完毕。
13. [异常排查] 如果某些功能（如 WiFi、蓝牙）无法使用，可在搜索框中输入 ```;demo``` 并按回车进入激活演示模式界面，然后点击右边的【Yes】按钮，这样 Kindle 会自动重启并重置 Kindle 并进入正常模式。最后重新安装一遍 update_hotfix_languagebreak-xx-XX.bin 即可。
14. 验证：在 Kindle 界面上方的搜索框中输入 ```;log runme``` 并按回车，如果屏幕左上角出现了 ```No user script found.``` 的字样就说明没有问题。

## 如何正确的重置 Kindle
不论是想要放弃越狱、越狱成功后想要解除越狱，还是越狱失败后想要从头开始越狱步骤，都必须先重置一遍 Kindle 设备，再安装一遍同版本号 Kindle 固件文件（方法同普通固件）。  
1. 重置 Kindle 存在两种情况：
   - 如果 Kindle 已退出演示模式，可直接通过击菜单【设置 → 设备选项 → 重置】进行重置。
   - 如果 Kindle 尚处于演示模式，可在 Kindle 界面上方的搜索框中输入 ```;demo``` 并回车进入“演示菜单”（如无法调出菜单重启 Kindle 后重试），点击【导入内容】按钮，用 USB 数据线将 Kindle 连电脑，在根目录中放入名为 ```DO_FACTORY_RESTORE``` 的空文件（注意！是文件，不是文件夹，不带扩展名），最后重启 Kindle 即可自动重置。
2. 重置完成后，安装同版本号的固件：
   - 下载最新固件文件（[亚马逊官方页面下载](https://www.amazon.com/gp/help/customer/display.html?nodeId=GKMQC26VQQMM8XSW)）；
   - 通过 USB 连接电脑，将下载好的固件文件拷贝到“根目录”下（和 documents 文件夹同级）；
   - 拷贝完毕后安全移除或弹出驱动器，并断开 Kindle 和电脑的 USB 连接；
   - 进入 Kindle 界面，依次点击【 菜单（屏幕右上角）→ 设置 → 菜单（屏幕右上角）→ 更新您的 Kindle】（英文版为【menu → settings → menu → update】）；
   - 接下来 Kindle 会自动进入固件更新状态，屏幕上会显示“您的 Kindle 正在更新”的提，更新完毕会自动重启，重启完毕固件就更新成功了。

## 插件安装
### MobileRead Package Installer (MRPI) — 插件安装器
MobileRead Package Installer 是一款 KUAL 插件。因为现在 Kindle 固件不支持直接把插件文件以刷入 bin 的方式安装，所以需要通过 KUAL 的这个插件 MRPI 来安装。  
[下载地址](https://www.mobileread.com/forums/showthread.php?t=225030)
安装步骤：
  - 用 USB 数据线将 Kindle 连接到电脑上，直到出现 Kindle 磁盘；
  - 解压缩下载到的 kual-mrinstaller-1.7.N-xxx.tar.xz 得到一个文件夹；
  - 把文件夹内的 extensions 和 mrpackages 拷贝到 Kindle 的根目录。
如果根目录已有 extensions 这个文件夹，可以只把解压得到的 extensions 文件夹中的内容拷贝到 Kindle 根目录原有的 extensions 文件夹内，以避免原文件夹内的其它文件被删除。  
另外，值得一提的是，如果你需要安装多个插件（比如本文之后所介绍的那些插件），不必重复每一款插件的安装步骤，只需要将所有 bin 文件拷贝到 mrpackage 目录，然后通过 ;log mrpi 命令一次性安装它们。这样，每当需要重新安装插件时，可以节省大量时间。  
### KUAL — 插件程序启动器
KUAL (即 Kindle Unified Application Launcher)，是一款插件启动器。安装 KUAL 之后，你可以下载或自己编写插件并通过 KUAL 启动。比如用来启动 Koreader 之类的插件程序、让电量显示百分比等。
- KO 1/2/3、KPW 4/5、Kindle 8/10 按照以下步骤安装 KUAL：
   - 下载 coplate 版本 KUAL：[官方页面](https://www.mobileread.com/forums/showthread.php?t=225030)
   - 用 USB 数据线将 Kindle 连接到电脑上，直到出现 Kindle 磁盘；
   - 先按照第一部分提供的方法安装 MobileRead Package Installer (MRPI)；
   - 然后解压缩下载到的 KUAL-xxxxxxx-20xxxxxx.tar.xz 得到一个文件夹；
   - 在文件夹中找到 Update_KUALBooklet_xxxxxxx_install.bin 文件，拷贝到 Kindle 根目录下的 mrpackages 文件夹，然后在 Kindle 搜索框中输入 ```;log mrpi``` 点击回车；
   - 这时会调用 MRPI 安装 KUAL，安装完成并等待 Kindle 重启完毕后即可使用 KUAL。

- Kindle 7、KPW 1/2/3、KV 按照以下步骤安装 KUAL：
   - 下载 KUAL：[官方页面](https://www.mobileread.com/forums/showthread.php?t=225030)
   - 固件版本大于 5.8.x 的安装步骤：
      - 用 USB 数据线将 Kindle 连接到电脑上，直到出现 Kindle 磁盘；
      - 先按照第一部分提供的方法安装 MobileRead Package Installer (MRPI)；
      - 然后解压缩下载到的 KUAL-v2.x.xx-xxxxxxxx-20xxxxxx.tar.xz 得到一个文件夹；
      - 在文件夹中找到 Update_KUALBooklet_v2.x.xx_install.bin 文件，拷贝到 Kindle 根目录下的 mrpackages 文件夹，然后在 Kindle 搜索框中输入 ```;log mrpi``` 点击回车；
      - 这时会调用 mrpi 安装 KUAL，安装完成并等待 Kindle 重启完毕后即可使用 KUAL。
   - 固件版本小于 5.8.x 的安装步骤：
      - 用 USB 数据线将 Kindle 连接到电脑上，直到出现 Kindle 磁盘；
      - 解压缩下载到的 KUAL-v2.x.xx-xxxxxxxx-20xxxxxx.tar.xz 得到一个文件夹；
      - 在文件夹中找到 KUAL-KDK-2.0.azw2 拷贝到 Kindle 的 documents 文件夹中；
      - 弹出 Kindle 磁盘并进入 Kindle 界面，即可看到 KUAL（如下图所示）。
成功安装 KUAL 后，我的图书馆中会出现一个名为 KUAL 的个人文档图标，正常情况下，点开此图标应显示菜单。

### Koreader — 第三方电子书阅读器
Koreader 这款软件采用图像分割再重排的方式处理 PDF 文档（包括扫描和非扫描页面），这样不仅支持文字版 PDF 重排和数学公式的重排，还能对扫描版 PDF 和 DJVU 文档进行重新排版。重新排版后的文档，文字放大后可以适应屏幕自动换行，免去不断地左右拖动页面阅读。  
下载 Koreader：[官方页面](https://github.com/koreader/koreader/releases)  
安装步骤：
   - 首先确保安装了 MRPI 和 KUAL；
   - 用 USB 数据线将 Kindle 连接到电脑上，直到出现 Kindle 磁盘；
   - 解压缩下载到的 Koreader 压缩包，可得到 extensions 和 koreader 两个文件夹；
   - 先把文件夹 extensions 中的内容拷贝到 Kindle 根目录下的 extensions 文件夹中；
   - 然后把文件夹内的 koreader 文件夹拷贝到 kindle 根目录下；
   - 通过 KUAL 菜单中启动 Koreader 并用它的文件浏览器打开并阅读电子书。
### Koreader 字体
直接放在 Kindle 根目录的 fonts 目录下，只支持 TTF 和 OTF 格式。
见 releases【Kindle字体】部分。
### Koreader 词典
Koreader 只支持星际译王　StarDict 词典，将包含三个文件文件 idx、ifo（或 ifo.gz） 、 dict（或 dict.dz）的目录复制到 Kindle 下面的 koreader/data/dict 目录下。
常用的、注释比较全的英语和汉语词典见 releases【Koreader词典】部分。
### Kindle 词典
见 releases【Kindle词典】部分。
