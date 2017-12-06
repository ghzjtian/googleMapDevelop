# GoogleMap Android 开发
>https://developers.google.com/maps/documentation/android-api/start

###1.Google基础地图 Demo : 
###[2.导出 SHA-1 KEY](#generate_key)
###[3.在项目中导入 Google Play Services .](#input_play_services)
###[4.创建 API 密钥.](#generate_api_key)
* 1.生成密钥
* 2.把密钥放进项目

###[5.注意事项](#attention_items)

###[6.手机相关截图.](#phone_screenShot)
***
***
***

###1.Google基础地图 Demo : 
>Google Maps Android API v2 Samples
>https://github.com/googlemaps/android-samples

###2.导出 SHA-1 KEY<a name="generate_key"/>

>https://developers.google.com/maps/documentation/android-api/signup

#####* 1.因为 Google 地图要导入 API key 才能运行，而 API key 分为 debug key 和 release key.所以要分别导出这两种 Key 的 sha1.

 * 1.Debug Key:
   * Mac:
     * 在终端输入
     ```
keytool -list -v -keystore ~/.android/debug.keystore -alias androiddebugkey -storepass android -keypass android     
     ```
     出现:
     
     ```
$ keytool -list -v -keystore ~/.android/debug.keystore -alias androiddebugkey -storepass android -keypass android
别名: androiddebugkey
创建日期: 2017-10-16
条目类型: PrivateKeyEntry
证书链长度: 1
证书[1]:
所有者: C=US, O=Android, CN=Android Debug
发布者: C=US, O=Android, CN=Android Debug
序列号: 1
有效期开始日期: Mon Oct 16 15:07:30 CST 2017, 截止日期: Wed Oct 09 15:07:30 CST 2047
证书指纹:
	 MD5: 39:98:89:03:DB:4B:A8:8C:C7:58:3C:16:87:B1:00:00
	 SHA1: C9:9C:70:74:56:56:A0:F4:54:A9:9C:08:92:3B:0D:A1:93:2F:00:00
	 SHA256: 82:53:BB:E4:3B:70:22:7E:96:42:8F:07:72:3E:D2:40:FF:9F:21:2F:25:13:41:95:E3:68:D4:AA:7A:7D:00:00
	 签名算法名称: SHA1withRSA
	 版本: 1

     ```
* 2.Release Key
```
keytool -list -v -keystore your_keystore_name -alias your_alias_name
```

***
###3.在项目中导入 Google Play Services .<a name="input_play_services"/>
>1.因为 Google Map 用到了 Google services .所以项目需要导入 Google services SDK.

>2.国产机默认没有 google services ，所以需要自己手动安装了 google services 才能使用 google map .

>3.参考: https://developers.google.com/android/guides/setup

>4.如果出错 ```Could not find dependency ```，详情请参考上面的链接.
```
If you receive an error, check that your top-level build.gradle contains a reference to the google() repo or to maven { url "https://maven.google.com" }
```
***

###4.创建 API 密钥.<a name="generate_api_key"/>
* 1.生成密钥
>1.修改了密钥后，可能要 5Min 才能生效.
>3.一定要准确，否则会发生以下错误:

```
E/Google Maps Android API: Authorization failure.  Please see ...
```

* 下面是图片教程:
![](/assets/Snip20171122_1.png)
![](/assets/Snip20171122_2.png)
![](/assets/Snip20171122_4.png)
![](/assets/Snip20171122_5.png)
![](/assets/Snip20171122_7.png)
![](/assets/Snip20171122_8.png)

* 2.把密钥放进项目

```
   <string name="google_maps_key" translatable="false" templateMergeStrategy="preserve">AIzaSyA9A-etWlzs4TD-cOKhVW8qiHF3GXF-pvI</string>

```
![](/assets/Snip20171122_10.png)


***

###5.注意事项<a name="attention_items"/>
* 1.更改了 API 密钥后，记得卸载并重新安装.!!!
* 2.出现```Unexpected response code 400```错误，在去除了API限制后，就又可以正常运行了.

![](/assets/Snip20171122_11.png)
***

###6.手机相关截图.<a name="phone_screenShot"/>
* 1.没有安装 Google Play Services 的手机的显示:
![](/assets/WechatIMG116.jpeg)

* 2.正常的手机显示:
![](/assets/WechatIMG117.png)
![](/assets/WechatIMG118.jpeg)





