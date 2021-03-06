---
layout: post
title: 关于iOS多任务页面底部出现“xxx，早上好”banner的调研
---

### 多任务页面底部banner出现的种类
![Image_1](/media/image/ios_bottom_banners_1.png)
***1、handoff（接力）
2、xxx，早上好
3、基于您的当前位置
4、“耳机”已连接
5、（未知。。。）***

### 实现

#### handoff
设置 -> 通用 -> 接力 -> 打开接力

通过“接力”功能，您在某设备开始操作后，可立即使用iCloud账号从另一设备继续相同操作。您需要的应用会显示在应用切换器和Mac的程序坞上。

这种一般应用在需要跨设备共享编辑的应用上，例如“印象笔记”，在手机上编辑了一段文字后，可以切换到Mac上继续编辑。**Bigo Live应该没有这种需求**。

官方简介：https://support.apple.com/zh-cn/HT204681

***这是开发者唯一能控制的底部banner种类***


#### Siri应用建议
***xxx，早上好
基于您的当前位置
“耳机”已连接***
##### 关于前两种情况：
系统会记录用户长期的使用应用的习惯，自主地向用户推荐相关的应用。例如，早上起床后我会习惯打开微博，系统早上就会给我推荐微博；来到公司我会习惯打开微信，系统也会根据地理位置给我推荐微信。系统会通过记录用户的使用频率、时间、地理位置等维度，向用户推荐应用。

##### 关于“耳机”已连接
手机连接蓝牙耳机或者有线耳机后，系统会弹出 “耳机”已连接 的banner，如果手机装有多个音乐应用，目前观察到的情况是会弹出最常用的那个应用。但是有时候又不会弹，而且弹出维持的时间也没有规律。

##### 国外用户如是说：
***
This is a feature suggesting which app you normally use in a certain situation. Like location, time of day, headphones or Bluetooth connected. Phone tries to learn if you always do something. Like I always open maps when I connect to my car Bluetooth. Or always open music when by headphones are plugged in. Or always open weather at 7am.
***

##### 用户怎么打开应用推荐


![Image_1](/media/image/ios_bottom_banners_2.png)

1、设置 -> Siri与搜索 -> 打开 搜索建议 查询建议 锁屏建议
2、设置 -> 隐私 -> 定位服务 -> 系统服务 -> 打开 基于位置的建议 基于位置的提醒
3、通知栏 -> 右滑 -> 编辑 -> 添加 Siri应用建议 小组件

### 结论
iOS多任务页面底部出现“xxx，早上好”banner是一个系统行为，系统的Siri会根据用户的使用习惯，在多任务页面底部显示推荐应用，开发者无法干预。

### 参考
https://stackoverflow.com/questions/46039851/how-may-i-customize-app-suggestions-in-ios
https://www.phonearena.com/news/App-suggestions-in-iOS-10-how-they-work-whats-changed-how-to-disable-them_id89219
https://discussions.apple.com/message/30065692#30065692



