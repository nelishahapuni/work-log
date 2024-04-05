# work-log
Logs and description of all my work, updated on a (mostly) daily basis.

5 April 2024

# Preparation Topics for Client

- [Appium with Java](#appium-with-java)
- [Accessibility Labels (Android & iOS)](#accessibility-labels-android-ios)
- [Create APP Binary Exposed for Automation](#create-app-binary-exposed-for-automation)
- [How SDKs Interact with App](#how-sdks-interact-with-app)
- [How Web Views Work](#how-web-views-work)
- [Exposing WebViews to APPIUM](#exposing-web-views-to-appium)
- [Setup Mock Server to Test API](#setup-mock-server-to-test-api)
- [Production & Non-Production binaries](#production-non-production-binaries)

## APPIUM with Java
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

### Additionally
- Open app from background
- Screen Orientation
- Touch Gesture

Test on devices with most users, latest OS version, and minimum supported version.
