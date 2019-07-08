# IpaCreateDownloadLink
根据ipa生成对外下载的链接说明，附含安卓生成对外下载链接，附ios和安卓下载链接生成一个二维码


- 生成ipa提交到一个服务器上,生成外链(必须是https)
`https://raw.githubusercontent.com/yangtianyan/HookLive4iPhone/master/live4iphone.ipa`
- 在生成两个icon,`512*512`,`57*57`,提交上服务器,生成外链(必须是https)
`https://raw.githubusercontent.com/yangtianyan/HookLive4iPhone/master/AppIcon57.png`
`https://raw.githubusercontent.com/yangtianyan/HookLive4iPhone/master/AppIcon512.png`

- 创建`manifest.plist`文件
```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
<key>items</key>
<array>
<dict>
<key>assets</key>
<array>
<dict>
<key>kind</key>
<string>software-package</string>
<key>url</key>
<string>https://github.com/bianxiang/IpaCreateDownloadLink/blob/master/App/ios/Runner.ipa</string>//上传上去ipa的外链
</dict>
<dict>
<key>kind</key>
<string>display-image</string>
<key>url</key>
<string>https://github.com/bianxiang/IpaCreateDownloadLink/blob/master/App/ios/logo57*57.png</string>//上传上去的`57*57`icon的外链
</dict>
<dict>
<key>kind</key>
<string>full-size-image</string>
<key>url</key>
<string>https://github.com/bianxiang/IpaCreateDownloadLink/blob/master/App/ios/logo512*512.png</string>//上传上去的`512*512`icon的外链
</dict>
</array>
<key>metadata</key>
<dict>
<key>bundle-identifier</key>
<string>com.zp.swap.test</string>//
<key>bundle-version</key>
<string>1.0</string>//版本号
<key>kind</key>
<string>software</string>
<key>title</key>
<string>SWAP</string>//app名字
<key>subtitle</key>
<string>SWAP</string>//随便
</dict>
</dict>
</array>
</dict>
</plist>
```
- 最后生成可以下载的链接
```
itms-services://?action=download-manifest&url=https://raw.githubusercontent.com/yangtianyan/HookLive4iPhone/master/manifest.plist
```
> `https://raw.githubusercontent.com/yangtianyan/HookLive4iPhone/master/manifest.plist` 是生成的plist的外链

最后讲此链接放入手机的`Safari`中打开就可以了



