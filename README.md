# JPush PhoneGap / Cordova Plugin

[![Build Status](https://travis-ci.org/jpush/jpush-phonegap-plugin.svg?branch=master)](https://travis-ci.org/jpush/jpush-phonegap-plugin)
[![Gitter](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/jpush/jpush-phonegap-plugin)
[![release](https://img.shields.io/badge/release-2.1.5-blue.svg)](https://github.com/jpush/jpush-phonegap-plugin/releases)
[![platforms](https://img.shields.io/badge/platforms-iOS%7CAndroid-lightgrey.svg)](https://github.com/jpush/jpush-phonegap-plugin)
[![weibo](https://img.shields.io/badge/weibo-JPush-blue.svg)](http://weibo.com/jpush?refer_flag=1001030101_&is_all=1)

支持 iOS, Android 的 Cordova 推送插件。
> 如需要 IM 功能的插件，可关注 [jmessage-phonegap-plugin](https://github.com/jpush/jmessage-phonegap-plugin)。

## 集成步骤

### 1.首先安装 cordova device 插件

     cordova plugin add cordova-plugin-device

### 2.安装 JPush PhoneGap Plugin
安装 JPush PhoneGap Plugin 有两种方法：

方法一：在线安装

通过 Cordova plugins 安装，要求 PhoneGap/Cordova CLI 5.0+：

	cordova plugin add jpush-phonegap-plugin --variable API_KEY=your_jpush_appkey

直接通过 url 安装：

    cordova plugin add https://github.com/jpush/jpush-phonegap-plugin.git --variable API_KEY=your_jpush_appkey  

方法二：下载到本地再安装

使用 git 命令将 JPush PhoneGap 插件下载的本地，目录标记为 $JPUSH_PLUGIN_DIR：

    git clone https://github.com/jpush/jpush-phonegap-plugin.git

    cordova plugin add $JPUSH_PLUGIN_DIR  --variable API_KEY=your_jpush_appkey

- [Android 手动安装文档地址](/doc/Android_handle_install.md)。

- [iOS 手动安装文档地址](/doc/iOS_install.md)。

### 3.在 js 中调用函数，初始化 JPush

    //由于 PhoneGap 插件采用了 lazy load 的特性，所以建议在 js 文件能执行的最开始就添加。
    window.plugins.jPushPlugin.init();


## Demo
插件项目中包含一个简单的 Demo。若想参考，可以在 /example 文件夹内找到并拷贝以下文件:

	src/example/index.html -> www/index.html
	src/example/css/* -> www/css
	src/example/js/* -> www/js

## 关于 PhoneGap build 云服务

该项目基于 Cordova 实现，目前无法使用 PhoneGap build 云服务进行打包，建议使用本地环境进行打包。

## API 说明

插件的 API 在 JPushPlugin.js 文件中，该文件的具体位置如下：
### Android
	[Project]/assets/www/plugins/cn.jpush.phonegap.JPushPlugin/www

### iOS
	[Project]/www/plugins/cn.jpush.phonegap.JPushPlugin/www

### 具体的 API 请参考：

- [公共 API](/doc/Common_detail_api.md)。

- [iOS API](/doc/iOS_API.md)。

- [Android API](/doc/Android_detail_api.md)。


## 常见问题

若要使用 CLI 来编译项目，注意应使用 cordova compile 而不是 cordova build 命令，因为 cordova build 会清除对插件文件的修改。
Cordova CLI 的具体用法可参考 [Cordova CLI 官方文档](https://cordova.apache.org/docs/en/latest/reference/cordova-cli/index.html)。

### 1. Android

Eclipse 中 import PhoneGap 工程之后出现：*Type CallbackContext cannot be resolved to a type*。

解决方案：Eclipse 中右键单击工程名，Build Path -> Config Build Path -> Projects -> 选中工程名称 -> CordovaLib -> 点击 add。

### 2. iOS

- 收不到推送：
	请首先按照正确方式再次配置证书、描述文件，具体可参考 [iOS 证书设置指南](http://docs.jpush.io/client/ios_tutorials/#ios_1)。

- 设置 PushConfig.plist：
	- APP_KEY：应用标识。
	- CHANNEL：渠道标识。
	- IsProduction：是否生产环境。
	- IsIDFA：是否使用 IDFA 启动 SDK。



## 更多
 [JPush 官网文档](http://docs.jpush.io/)。

 如有问题可访问[极光社区](http://community.jpush.cn/)。
 
 
 关于fami   更多插件：http://fami2u.com/
