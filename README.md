# xbox
how to install the Xbox app and log in on PC
## 安装
可以直接在[网站](https://www.xbox.com/zh-HK/apps/xbox-app-on-pc)上下载exe文件进行安装，也可以在Microsoft Store中直接安装。
如果有VPN推荐在网站上下载安装，如果Microsoft Store无法打开，可以参考登录中的方法。
安装时需要启用windows update，如果之前通过组策略或者使用WUB禁用了更新，需要重新修改组策略。如果修改后还是失效，可以尝试以下步骤：
1. 按下 `Win + R`
2. 输入 `cmd` 并以管理员身份打开命令提示符
3. 输入 `gpupdate /force` 并回车
## 登录
Xbox没有在CN地区提供服务，所以在登录前需要修改地区（以Windows10为例）：
1. 打开开始菜单，选择设置
2. 在设置中选择**时间和语言**
3. 在左边的导航栏中选择**区域**
4. 将**国家或地区**改为：**香港特别行政区**，**区域格式**改为：**中文（简体汉字，香港特别行政区）**
5. 在左边的导航栏中选择**语言**
6. 将首选语言中的 **中文（简体，中国）** 拖拽移动到首位

接下来登录Xbox app，如果登录失败，可以尝试以下步骤（Microsoft Store无法打开也可以使用这个方法，只是可能还需要关闭VPN）：
1. 按下 `Win + R`
2. 输入 `inetcpl.cpl` 打开**Internet 属性**窗口
3. 在**Internet 属性**窗口中，点击顶部的**高级选项卡**
4. 找到**SSL 3.0**、**TLS 1.0**、**TLS 1.1** 和 **TLS 1.2**，将它们都勾上
## 暂停windows update（100年）的方法
1. 按下 `Win + R`
2. 输入 `regedit` 打开注册表
3. 找到**计算机\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\WindowsUpdate\UX\Settings**
4. 在**Settings**右边新建一个**DWORD项(32位)**，名字叫**FlightSettingsMaxPauseDays**
5. 右键**FlightSettingsMaxPauseDays**，选择**修改**
6. 将**基数**改为**十进制**，数值数据改为**36524**，然后关闭注册表
7. 打开开始菜单，选择设置
8. 在设置中选择**更新和安全**
9. 点击**高级选项**
10. 将**暂停更新**的日期选择为100年后
