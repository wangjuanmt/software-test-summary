# Mobile-Auto

## Android 端的自动化测试框架
### Espresso
Espresso 是 Google 针对 Android 平台开源的一款 Android 自动化测试框架，主要是用于 Android App UI 自动化测试。
优点:

用 Java 来写代码，对 Android 开发者很友好
API 相当的小，当然也会对拓展开放的
Espresso 的测试跑起来那是相当的快（没有等待、睡眠）
Gradle 和 Android Studio 的支持
更多 Espresso 的例子请戳：https://github.com/vgrec/EspressoExamples
### UI Automator
UI Automator 所运行的 JUnit 测试用例是有特殊权限的，这意味着测试用例可以跨越不同的进程，它提供了五种不同的类给开发人员使用：
``````
com.android.uiautomator.core.UiCollection;
com.android.uiautomator.core.UiDevice;
com.android.uiautomator.core.UiObject;
com.android.uiautomator.core.UiScrollable;
com.android.uiautomator.core.UiSelector
``````
UI Automator 只能工作在 API 16 或更高级别的 Android 设备上，而且也没有办法直接访问 Android 对象。
### Appium
Appium 是一款「移动」的自动化测试框架，牛逼的地方在于支持 iOS 和 Android 原生和混生的移动 Web 应用程序。

[Appium Get Started](https://github.com/appium/appium/blob/master/docs/en/about-appium/getting-started.md)

它内部使用的 JSONWireProtocol 通过 Selenium 的 WebDriver，来与 iOS 和 Android 应用进行交互。

通过 UI Automator 和 Seledroid 支持 Android，通过 UI Automation 支持 iOS。

Appium 最大的优点在于你几乎可以用任意一种编程语言（例如，Java、Objective-C、JavaScript、PHP、Ruby）来编写 Appium 脚本而不必选择工具，
兼容最重要的pigtail（Android 和 iOS）而不必安装和配置设备适应测试等等。

## 云测试平台
### 腾讯优测云测试平台
拥有超过1000款测试终端，机型数量庞大，机子比较全。但仅支持 Android 系统，暂时不支持 iOS 系统。
不过，该平台的收费还是蛮高的，一分钟一块钱，而且最低充值 100 元。
### Testin
Testin 是国内较早涉足云测试领域的公司之一。Testin 在云端部署了 300 多款 1000 多部测试终端，终端种类及数量都比较全面。

该平台也是收费的，具体的收费标准，并没有在官网上显示出来，只说了有需要服务的请联系客服。

