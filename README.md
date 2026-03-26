# MobileIMSDK Android Library

[![](https://jitpack.io/v/xue9052/zack_mobileimsdk.svg)](https://jitpack.io/#xue9052/zack_mobileimsdk)

MobileIMSDK 是一个轻量级即时通讯框架，专为移动端设计。

## 📦 安装

### 通过 JitPack 引入

**Step 1.** 在项目的 `settings.gradle` 中添加 JitPack 仓库：

```gradle
dependencyResolutionManagement {
    repositories {
        google()
        mavenCentral()
        maven { url 'https://jitpack.io' }
    }
}
```

**Step 2.** 在模块的 `build.gradle` 中添加依赖：

```gradle
dependencies {
    implementation 'com.github.xue9052:zack_mobileimsdk:6.2'
}
```

## 🚀 快速开始

### 1. 初始化 SDK

```java
// 在 Application 中初始化
ClientCoreSDK.DEBUG = true; // 开启调试模式
ClientCoreSDK.getInstance().initContext(context);
```

### 2. 设置回调监听

```java
ClientCoreSDK.getInstance().setChatMessageEvent(new ChatMessageEvent() {
    @Override
    public void OnMessageData(String message) {
        // 收到消息
    }
    
    @Override
    public void OnConnectStatusChange(int status) {
        // 连接状态变化
    }
});
```

### 3. 发送消息

```java
String message = "Hello IM";
ClientCoreSDK.getInstance().send(message);
```

## 🔧 配置说明

### 混淆配置

如果使用代码混淆，请在 `proguard-rules.pro` 中添加：

```proguard
-keep class net.x52im.mobileimsdk.** { *; }
-dontwarn net.x52im.mobileimsdk.**
```

### 权限配置

在 `AndroidManifest.xml` 中添加必要权限：

```xml
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
<uses-permission android:name="android.permission.WAKE_LOCK" />
```

## 📝 更新日志

### v6.2
- 优化连接稳定性
- 修复已知问题
- 性能提升

## 📄 许可证

本项目采用 Apache 2.0 许可证。

## 📧 联系方式

- 官网：http://www.52im.net/
- GitHub Issues: https://github.com/xue9052/zack_mobileimsdk/issues

---

**注意**：本库基于原 MobileIMSDK 项目改进，原作者：JackJiang。
原项目地址：https://github.com/JackJiang2011/MobileIMSDK
