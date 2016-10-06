# Windows 10的一些初始化设置

## 设置win10文件资源管理器默认打开“此电脑”，并不显示“快速访问”
1. 从开始菜单中打开文件资源管理器
2. 在文件资源管理器的菜单栏中选择“查看”
3. 然后从弹出的菜单中中点击“选项”
4. 在选项卡的最上面有一个下拉列表选择“打开文件资源管理器时打开”，选择“此电脑”
5. 在选项卡的最下面，将“隐私”中的两个选项都清空
6. “确定”

## 移除Dropbox在资源管理器中的显示
```cmd
HKEY_CLASSES_ROOT\CLSID\{E31EA727-12ED-4702-820C-4B6445F28E1A}
HKEY_CLASSES_ROOT\WOW6432Node\CLSID\{E31EA727-12ED-4702-820C-4B6445F28E1A}
```
* 将名称为 System.IsPinnedToNameSpaceTree 的值改为 0 即可

## 移除OneDirve在资源管理器中的显示
* 定位到：
```cmd
HKEY_CLASSES_ROOT\CLSID\{018D5C66-4533-4307-9B53-224DE2ED1FE6}
HKEY_CLASSES_ROOT\WOW6432Node\CLSID\{018D5C66-4533-4307-9B53-224DE2ED1FE6}
```
* 将名称为 System.IsPinnedToNameSpaceTree 的值改为 0 即可

## 移除Dropbox在资源管理器中的显示
* 定位到：
```cmd
HKEY_CLASSES_ROOT\CLSID\{E31EA727-12ED-4702-820C-4B6445F28E1A}
```
* 将名称为 System.IsPinnedToNameSpaceTree 的值改为 0 即可

## 移除Windows 10“此电脑”电脑中不需要的文件夹
* 移除“桌面”文件夹
```cmd
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{B4BFCC3A-DB2C-424C-B029-7FE99A87C641}
HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{B4BFCC3A-DB2C-424C-B029-7FE99A87C641}
```
* 移除“文档”文件夹
```cmd
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{A8CDFF1C-4878-43be-B5FD-F8091C1C60D0}
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{d3162b92-9365-467a-956b-92703aca08af}
HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{A8CDFF1C-4878-43be-B5FD-F8091C1C60D0}
HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{d3162b92-9365-467a-956b-92703aca08af}
```
* 移除“下载”文件夹
```cmd
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{374DE290-123F-4565-9164-39C4925E467B}
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{088e3905-0323-4b02-9826-5d99428e115f}
HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{374DE290-123F-4565-9164-39C4925E467B}
HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{088e3905-0323-4b02-9826-5d99428e115f}
```
* 移除“音乐”文件夹
```cmd
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{1CF1260C-4DD0-4ebb-811F-33C572699FDE}
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{3dfdf296-dbec-4fb4-81d1-6a3438bcf4de}
HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{1CF1260C-4DD0-4ebb-811F-33C572699FDE}
HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{3dfdf296-dbec-4fb4-81d1-6a3438bcf4de}
```
* 移除“图片”文件夹
```cmd
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{3ADD1653-EB32-4cb0-BBD7-DFA0ABB5ACCA}
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{24ad3ad4-a569-4530-98e1-ab02f9417aa8}
HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{3ADD1653-EB32-4cb0-BBD7-DFA0ABB5ACCA}
HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{24ad3ad4-a569-4530-98e1-ab02f9417aa8}
```
* 移除“视频”文件夹
```cmd
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{A0953C92-50DC-43bf-BE83-3742FED03C9C}
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{f86fa3ab-70d2-4fc7-9c99-fcbf05467f3a}
HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{A0953C92-50DC-43bf-BE83-3742FED03C9C}
HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{f86fa3ab-70d2-4fc7-9c99-fcbf05467f3a}
```

## 禁用或卸载 OneDrive
### 禁用
1. 按下Windows+ R — 输入 GPedit.msc 打开组策略编辑器
2. 在计算机配置 — 管理模板 — Windows 组件 — OneDrive 中双击打开禁止使用OneDrive进行文件存储
3. 选择启用后点击确定

### 完全卸载OneDrive
#### 卸载
* 以管理员方式打开命令提示符，先输入如下命令结束 OneDrive 进程
```cmd
taskkill /f /im OneDrive.exe
```
* 32位Windows 10 (x86) 使用如下命令卸载 OneDrive 应用
```cmd
%SystemRoot%\System32\OneDriveSetup.exe /uninstall
```
* 64位Windows 10 (x64) 使用如下命令卸载 OneDrive 应用
```cmd
%SystemRoot%\SysWOW64\OneDriveSetup.exe /uninstall
```
#### 清理
* 清理残留数据
```cmd
rd "%UserProfile%\OneDrive" /Q /S
rd "%LocalAppData%\Microsoft\OneDrive" /Q /S
rd "%ProgramData%\Microsoft OneDrive" /Q /S
rd "C:\OneDriveTemp" /Q /S
```
* 清理注册表
```cmd
REG Delete "HKEY_CLASSES_ROOT\CLSID\{018D5C66-4533-4307-9B53-224DE2ED1FE6}" /f
REG Delete "HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{018D5C66-4533-4307-9B53-224DE2ED1FE6}" /f
```
