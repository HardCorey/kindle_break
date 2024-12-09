# kindle_break
记录 kindle 越狱和资料，大部分内容来源于网页：[bookfere](https://bookfere.com/post/1075.html)，请参考原网页获取最新信息，这里只做备份，防止原网页失联。  
我的 kindle 为 2015 年款 kpw3，固件版本为 5.16.2.1.1，亲测可行。

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
![image](https://github.com/user-attachments/assets/c4398ac2-e8c3-426d-962e-098b3c325026)
注意，在之后的操作中，只要出现带有“展示机无内容或未连接网络（This demonstration device is either missing content or is disconnected from the network）”、“配置设备（CONFIGURE DEVICE）”字样的界面，都同样需要用这里介绍的秘密手势跳过才能继续操作。
如果在进行以上步骤的过程中弹出了“Collecting Debug Info”提示框，说明你正在以错误的方式重试越狱步骤，请参考“常见问题”所提供的方法重置 Kindle 后再重新操作。

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
![image](https://github.com/user-attachments/assets/3dc397c3-c803-430e-bf65-5600909f483f)
11. [若进入演示模式] 上一步完成后，Kindle 会自动重启并进入正常模式，但是如果重启后仍然会进入演示模式：
    - 在 Kindle 界面上方的搜索框中输入 ```;uzb``` 并按回车激活演示模式的 USB 传输功能；
    - 用 USB 数据线将 Kindle 连电脑，将与你当前 Kindle 界面语言相对应的热修复补丁文件 update_hotfix_languagebreak-xx-XX.bin（如美式英语 en-US）拷贝到 Kindle 根目录；
    - 弹出并断开 USB 设备，在 Kindle 上方的搜索框中输入 ```;dsts``` 按回车，然后点击设置界面中的，或菜单中的【更新您的 Kindle】安装热修复补丁，Kindle 此时会自动重启。
    - 重启后 Kindle 会退出演示模式并做一些清理工作，至此全部越狱步骤完毕。
12. [若非演示模式] 出现 Kindle 界面后用 USB 数据线将 Kindle 连电脑
    - 将与你当前 Kindle 界面语言相对应的热修复补丁文件 update_hotfix_languagebreak-xx-XX.bin 拷贝到 Kindle 根目录；
    - 依次点击菜单【设置 → 更新您的 Kindle】安装热修复补丁；
    - 重启后全部越狱步骤完毕。
14. [异常排查] 如果某些功能（如 WiFi、蓝牙）无法使用，可在搜索框中输入 ```;demo``` 并按回车进入激活演示模式界面，然后点击右边的【Yes】按钮，这样 Kindle 会自动重启并重置 Kindle 并进入正常模式。最后重新安装一遍 update_hotfix_languagebreak-xx-XX.bin 即可。
15. 验证：如果想要简单验证越狱是否成功，可以在 Kindle 界面上方的搜索框中输入 ;log runme 并按回车，如果屏幕左上角出现了 No user script found. 的字样就说明没有问题。
