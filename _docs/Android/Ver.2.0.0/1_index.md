---
title: "Project Setup"
permalink: ver_2.0.0_index.html
sidebar: mps_side_bar
---

## Prerequisites
* Running Android Studio 1.0 or higher
* Developing for Android API level 19 or higher

<p id="download">
    <a  href="https://github.com/NBCUOTS/mobile_mps_sdk_android_examples/releases/tag/release-1.0.0">Download MPS SDK Examples
    </a>
</p>

In order to complete the Get Started guide, you need to have Android Studio installed on your development machine. If you don't already have it, see the Android Studio site for instructions on how to download everything you need to get up and running.

### 1. Create a new project

In this step, you create a brand new project in Android Studio to use for our example. If you don't already have Studio running, go ahead and open it now.

### 1.1 Start the new project wizard

{% include image.html file="android/1_new_project.png" caption="Create New Project" %}

If you see the above welcome screen, select Start a new Android Studio project. Otherwise, select File > New Project from the menu.

### 1.2 Name your project

{% include image.html file="android/2_naming.png" caption="Project Naming" %}

Give your project the desired Product Name. For the purposes of this example we will call it ReferenceTestApp.
Enter your Organization Name and Identifier.

### 1.3 Set the required SDK version

{% include image.html file="android/3_min_sdk_version.png" caption="Selecting SDK version" %}

On the next screen, select **Phone and Tablet** for the form factor and a minimum SDK version of 19. That's the minimum version supported by the MPS SDK.

### 1.4 Add your main activity

{% include image.html file="android/4_empty_activity.png" caption="Selecting Activity Template" %}

We're keeping it simple for this example, so on this screen select **Empty Activity**.

### 1.5 Name your activity

{% include image.html file="android/5_activity_naming.png" caption="Activity Naming" %}

On this screen you have the option of choosing names for the app's activity and its related resources. Use the default names for this example, and just click the **Finish** button.

### 1.6 Add SDK to Your Project

Copy **mps-sdk-${VERSION}.aar** to your libs folder and add the following code to your project’s **build.gradle** file:

```gradle
allprojects {
    repositories {
        jcenter()
        flatDir {
            dirs 'libs'
        }
    }
}
```

Add the following line to your **dependencies** section in your app's **build.gradle** file:

```
dependencies {
    ...
    compile(name:'mps-sdk-${VERSION}', ext:'aar')
    ...
}
```

Then add the following dependency which is used by SDK:

```
dependencies {
    ...
    compile 'com.google.android.gms:play-services-ads:11.0.4'
    ...
}
```

*Note: If you see a message about updating the Google Mobile Ads SDK, please contact the MPS SDK Support team prior to updating:*

* *Email: [mps-sdk-support@nbcuni.com](mailto:mps-sdk-support@nbcuni.com)*
* *DPIM Slack channel: [#mps_sdk_support](https://dpim.slack.com/messages/G4QJLA56Z)*

<style>
#download > a
{
    background-color: #2980b9;
    color: #fff;
    box-shadow: 0 2px 5px 0 rgba(0,0,0,.26);  
    border: 0;
    border-radius: 2px;
    cursor: pointer;
    display: inline-block;
    height: 44px;
    margin: 0;
    min-width: 36px;
    outline: 0;
    padding: 8px;
    padding-left: 16px;
    padding-right: 16px;
    vertical-align: middle;
    text-align: center;
    vertical-align: middle;
}
</style>