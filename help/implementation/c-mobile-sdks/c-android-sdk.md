---
description: Create Android Apps powered by Livefyre.
seo-description: Create Android Apps powered by Livefyre.
seo-title: Android SDK
solution: Experience Manager
title: Android SDK
uuid: 68793fa9-3ea1-4890-b36d-b631f1c6f7de
exl-id: 54ea6537-5f27-4174-af25-d17257f23e48
---
# Android SDK{#android-sdk}

Create Android Apps powered by Livefyre.

Use this library to integrate Livefyre services into your native Android app. The [Livefyre StreamHub Android SDK](https://github.com/Livefyre/StreamHub-Android-SDK) provides a thin layer around our common API mechanisms, based on the Gradle/Android Studio development environment.

Livefyre also provides a [Reviews](https://github.com/Livefyre/StreamHub-iOS-Reviews-App) sample App, based on this SDK.

This Livefyre Android SDK can be used in both Eclipse and Android Studio.

>[!NOTE]
>
>Before installing the Livefyre Android SDK you must have the [Android SDK](https://developer.android.com/sdk/index.html) installed on your environment. You must also include some additional Android SDK packages, as described in the Android Developer docs > .
>[Adding SDK Packages](https://developer.android.com/sdk/installing/adding-packages.html)

Use the Android SDK Manager (available from the Android Studio or Eclipse toolbar) to install all recommended packages. Be certain to also include the Android Support Repository.

## Eclipse {#section_dtm_slv_zz}

To add the Livefyre Android SDK to your project in Eclipse:

1. Get the latest [StreamHub-Android-SDK](https://github.com/Livefyre/StreamHub-Android-SDK) from GitHub.
1. Start with an existing project or create a new one.
1. To import the StreamHub-Android-SDK into your workspace go to **[!UICONTROL File > Import > General > Existing Project into Workspace]**.
1. Browse and select the StreamHub-Android-SDK; it should now show in the package explorer.
1. Right click on your project and select **[!UICONTROL Properties,]** then the Android tab.
1. Under the Library section, select **[!UICONTROL Add button,]** then select StreamHub-Android-SDK from the list of libraries.
1. Click on **[!UICONTROL Apply]** and **[!UICONTROL OK]**.

## Android Studio {#section_vpw_klv_zz}

To add the Livefyre Android SDK to your project in Android Studio:

1. Get the latest [StreamHub-Android-SDK](https://github.com/Livefyre/StreamHub-Android-SDK) from GitHub.
1. Start with an existing project or create a new one.
1. Right click on your project and select **[!UICONTROL Open Module Settings]**.
1. Select the **[!UICONTROL +]** button in the top left corner of the window.
1. Select **[!UICONTROL Import Existing Project.]** (In new version of Android studio, you can find **[!UICONTROL Import Existing Project]** under **[!UICONTROL More Modules]**.)

1. Browse and select the StreamHub-Android-SDK.

Android Studio may request that you convert the SDK to gradle version; if this occurs, select **[!UICONTROL next]** then **[!UICONTROL finish]**.

Go to **project folder > app folder > build.gradle** file under dependencies to add the the following dependency:

```
dependencies {   compile project(':streamHubAndroidSDK') } 

```

Make sure that the following line is in your **project folder > settings.gradle** file:

```
include ':streamHubAndroidSDK' 

```

>[!NOTE]
>
>You can customize configurations from within Config.java.

## Clients {#section_yfq_blv_zz}

The StreamHub Android SDK exposes several client classes that can be used to request Livefyre API endpoints:

* **AdminClient** Exchange a user authentication token for user information, keys, and other metadata.

* **BootstrapClient** Get recent content and metadata about a particular Collection.

* **StreamClient** Poll a stream for a Collection to retrieve new, updated, and deleted content.

* **WriteClient** Post, flag, and like content in a Collection.
