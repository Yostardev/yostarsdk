## 2. 接入流程
* 在info.plist添加如下内容：

```
<key>NSPhotoLibraryUsageDescription</key>
<string>NeedToAccessYourPhotoAlbum</string>

<key>CFBundleURLTypes</key>
<array>
    <dict>
        <key>CFBundleURLName</key>
        <string>facebook-unity-sdk</string>
        <key>CFBundleURLSchemes</key>
        <array>
            <string>fb962***1548(填写你的fbid)</string>
        </array>
    </dict>
    <dict>
        <key>CFBundleTypeRole</key>
        <string>Editor</string>
        <key>CFBundleURLSchemes</key>
        <array>
            <string>twitterkit-e7wRygYH7***VXzeUKm(填写你的twkey)</string>
        </array>
        </dict>
</array>

<key>FacebookAppID</key>
<string>962****548(填写你的fbid)</string>
<key>LSApplicationQueriesSchemes</key>
<array>
    <string>twitter</string>
    <string>twitterauth</string>
    <string>fbapi</string>
    <string>fbauth2</string>
    <string>fb-messenger-api</string>
    <string>fbshareextension</string>
</array>
```

* 配置后台模式功能，启用以下功能:

•    Background fetch

•    Remote notifications
如图：
![](https://upload-images.jianshu.io/upload_images/1948913-02273c6beb8989b6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 2.1. 使用Cocoapods进行自动集成
请Podfile根据要集成的版本将以下行添加到您的行中。
```
pod 'AiriSDK'，'~>2.1.4'＃需要接入的版本
pod 'AiriSDK'＃或者直接pod使用最新的SDK版本
```
并运行`pod install`或`pod update`刷新您的依赖项，至此接入完成。
### 2.2. 手动集成

[下载最新的Airi iOS SDK](https://github.com/Yostardev/yostar-sdk-ios)
* 解压后如图，Libraries文件夹下就是所需的Airi iOS SDK，把这些文件导入到你的工程中
![](https://upload-images.jianshu.io/upload_images/1948913-8e0913df9ad8e44d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
* 并导入一下所需的系统framework
`AdSupport`
`iAd`
`CoreTelephony`
`CoreGraphics`
`QuartzCore`
`CoreText`
`SystemConfiguration`
`CoreTelephony`
`UIKit`
`Security`
`QuickLook`
`CoreLocation`
`MobileCoreServices`
`CoreSpotlight`
`Photos`
`WebKit`
`SafariServices`
`libsqlite3.tbd`
`libicucore.tbd`
`libz.tbd`
添加完成后如图：
![](https://upload-images.jianshu.io/upload_images/1948913-cebf3cf912812bc6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
* 导入资源包成功如图：
![](https://upload-images.jianshu.io/upload_images/1948913-8575cd5252d89fa6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
* 设置Other Linker Flags
在工程 Target 的 Build Settings ->Linking ->Other Linker Flags 添加“-ObjC”，如下图：
![](https://upload-images.jianshu.io/upload_images/1948913-41590a26bd94178c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

* **注意：需要将AiriSDKConf.plist里面的参数替换为分配的参数，使用Cocoapods集成的工程plist文件在下图位置**
![image.png](https://upload-images.jianshu.io/upload_images/1948913-f2f84289d6fffb9a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)