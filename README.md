# work-log
Logs and description of all my work.

# Fix unreachable elements in Appium
*Log Date: 22 April 2024*

- The core issue is related to the nested elements, Appium cannot load all of them.
- This is caused by the "Stack Navigator" (in react native), specifically in iOS due to how the XCUITEST driver loads elements.
- It seems that it generates lots of nested element and it makes deeper-nested elements unreachable.

How I resolved it:
1. Replace "Stack Navigator" with "Native Stack Navigator" in the react native code. This is a different library which generates less nested elements, so the smaller ones are reachable.
2. Make sure that in APPIUM you set **"appium:settings[snapshotMaxDepth]": 62**
(you can try with a bigger number, but appium times out on my machine when I input 63 or more)
3. Both conditions need to be met, only one or the other is not enough


# Preparation Tasks
*Log Date: 6 April 2024*

- Installed Eclipse, Java, Selenium, Maven
- To get Device ID use the following command: **xcrun xctrace list devices**
- Download Drivers: xcuitest, uiautomator, safari, chromium
- Execute automation via Eclipse using java/selenium commands
- Watched: [How to create iOS automation testing project in java](https://youtu.be/eVfVacefiGo?si=GZEUtCtQW1iyKmXC)
- Read: [iOS Desired Capabilities](https://appium.io/docs/en/2.0/guides/caps/)

*Log Date: 5 April 2024*

# Questions
- Do I need to receive devices to test on? (Android/iPhone)
- What are the practical/everyday tasks that will be done with Appium?
- What knowledge should I have in Android/Flutter/React Native (other than accessibility IDs)

# Completed Tasks
- Installed Java, Android Studio, NodeJS
- Installed Appium, Appium Inspector, open WebDriverAgent
- Completed "Preparation Topics for Client"
- Watched: [Setup appium for iOS Real Device and Simulator](https://youtu.be/hKHHGZq82Bk?si=zEWDa67Sctf4Ardk)
- Read: [Appium Accessibility IDs: Why and How to Set Them](https://www.waldo.com/blog/appium-accessibility-id)

# Preparation Topics for Client

- [Appium with Java](#appium-with-java)
- [Accessibility Labels (Android & iOS)](#accessibility-labels-android-ios)
- [Create App Binaries Exposed for Automation](#create-app-binaries-exposed-for-automation)
- [How SDKs Interact with App](#how-sdks-interact-with-app)
- [How Web Views Work](#how-web-views-work)
- [Exposing WebViews to APPIUM](#exposing-web-views-to-appium)
- [Setup Mock Server to Test API](#setup-mock-server-to-test-api)
- [Production & Non-Production binaries](#production-non-production-binaries)

## APPIUM with Java (installed via Terminal)
- XCUItest iOS driver (Instruments)
- UI Automator for Android

### Emulator vs Simulator
- Emulator - software + hardware + OS (Android) mimics physical device
- Simulator - software (iOS) 

### Application Extensions
- IPA (iOS App Store Package)
- APK (Android Applicatoin Package File)
- EXE (Executable File)
- JAD (Java Application Descriptor)

### End to End Testing
- Installation
- Launch Activity
- UI orientation
- Network Scenarios
- Response to invalid info
- Performance Testing

### Kinds of testings
- installation -> functionality -> connectivity -> uninstallation -> interruption scenarios -> performance testing

### Basic Requirements for writing tests
- Driver Client - drives apps as if it’s a user -> write steps & send to server
- Appium Session - init session -> test takes place in session
- Desired Capabilities -> device version
- Driver Commands -> write desired steps

### APPIUM Inspector
- Identify element hierarchy
- Find element name, description, values, and attributes
- Record manual actions with the app

### Selenium Commands
- Locate commands using ID or class names
- Click() to trigger events on elements
- Text commands like Type()
- Get/Set element properties
- Commands to run JavaScript
- Switch contexts between different views

### Manual VS Automation Testing
Automation
- If the regression tests are repeated
- Testing apps for complex scenarios
Manual
- If app has new functionality
- If there are only 1-2 tests

### Types of Tests
- Functional
- Performance
- Memory Leak
- Interrupt
- Network
- Installation
- Force Upgrade
- Localization/Internationalization

### Key Testing Areas 
- Open app from background
- Screen Orientation
- Touch Gesture

Test on devices with most users, latest OS version, and minimum supported version.

# Accessibility Labels (Android & iOS)
- Accessibility ID on iOS and 'content description' on Android to find element in Appium Inspector
- Cross-platform frameworks (React Native or Flutter) have the same accessibility ID for Android/iOS
- Used to identify elements without text (usually buttons or images)
- Locator Strategies: Find element by ID *e.g. driver.findElement(By.id("com.google.android.calculator:id/digit_5"))*
- ![image](https://github.com/nelishahapuni/work-log/assets/28424871/b42252a4-f281-43d8-85b2-91ed3dc2e5a8)

# Create App Binaries Exposed for Automation

## iOS Binaries
- Binary Framework - already compiled source code w/defined interface that you can use in your apps
- Protects code that contains intellectual property
- Create **Cocoa Touch Framework** -> MyCustomFramework
- Header file *MyCustomFramework.h*: header that interacts between framework & host app

# How SDKs Interact with App

[Integrating React Native as an SDK into Existing iOS App](https://medium.com/@saikrishnakotagiri16/integrating-react-native-as-an-sdk-into-a-existing-ios-app-f659cc1645a)

1. Create new React Native Project

# How Web Views Work

- 'android.webkit.WebView' on Android and 'WKWebView' or 'UIWebView' on iOS

## Switch from Native to Web View in Appium

