### 必要的第一步，在注册表中配置 mpv 协议
*___注意替换 mpv 路径___
```
Windows Registry Editor Version 5.00

[HKEY_CLASSES_ROOT\mpv]
@="URL:mpv"
"URL Protocol"=""

[HKEY_CLASSES_ROOT\mpv\shell]

[HKEY_CLASSES_ROOT\mpv\shell\open]

[HKEY_CLASSES_ROOT\mpv\shell\open\command]
@="C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe" "-Command" "& {Add-Type -AssemblyName System.Web; $PARAMS=([System.Web.HTTPUtility]::UrlDecode(\"%1\") -replace \"^mpv://\"); Start-Process -FilePath \"<你的 mpv 安装路径，例子：C:\Users\zhong\scoop\apps\mpv-lazy\current\mpv.com>\" -ArgumentList $PARAMS;}"

```

### 第二步，注册 [pastebin](https://pastebin.com/) 账号，导出多文件时必需此步
注册成功后，前往此地址 https://pastebin.com/doc_api 获取 api_dev_key 和 api_user_key，该页面有详细说明，按步骤来即可。

![image](https://github.com/Asukaaaaaa/tricks/assets/24503369/24e30912-34d8-4067-ba5b-7f89580d649b)
![image](https://github.com/Asukaaaaaa/tricks/assets/24503369/70f407a5-fe96-445e-9eea-94a5a6fe40a5)

### 注意事项
- 导出多文件时提示跨域访问请允许
- 导出多文件时创建的 pastebin 链接默认设置了10分钟有效期，失效后请重新操作
