---
description: Add Livefyre to your native iOS App.
title: Livefyre iOS SDK
exl-id: 961c41dc-fee8-480c-a189-a20a689e705f
---
# Livefyre iOS SDK{#livefyre-ios-sdk}

Add Livefyre to your native iOS App.

Use this open-source library to integrate Livefyre services into your native iOS app. The Livefyre StreamHub iOS SDK provides a thin layer around our common API mechanisms, based on the excellent AFNetworking library.

Livefyre also provides two iOS Sample Apps based on this SDK: a Comment Stream and a Reviews sample App.

## Integrating the SDK into your project as a Cocoa Pod (recommended) {#section_qc5_h3v_zz}

The most convenient way to add StreamHub-iOS SDK to your project is to use CocoaPods. If you don’t have CocoaPods, run gem install cocoapods and pod setup. Here is an example Podfile:

```
source 'https://github.com/Livefyre/cocoapods.git' 
source 'https://github.com/CocoaPods/Specs.git' 
  
platform :ios, :deployment_target => '6.0' 
  
pod 'StreamHub-iOS-SDK', '~> 0.3.0'
```

You will also need to add a Specs repository to your CocoaPod installation (this will clone it to `~/.cocoapods/repos` directory):

```
pod repo add livefyre https://github.com/Livefyre/cocoapods.git
```

Once your Podfile is created in your app project root and the repository above added, run:

```
pod install
```

This will download all the dependencies and create a file MyApp.xcworkspace, which you should use from now on to open your app project in Xcode.

## As an Xcode subproject {#section_jcm_g3v_zz}

Alternatively, clone the repository:

```
git clone https://github.com/Livefyre/StreamHub-iOS-SDK.git 

```

Next, add the Xcode project (LFSClient.xcodeproj) to your app as a subproject (easily done by simply dragging the LFSClient.xcodeproj file into Project Navigator pane in Xcode).

You will also need to do the same with any of the dependencies ([AFNetworking](https://github.com/AFNetworking/AFNetworking), [JSONKit](https://github.com/escherba/JSONKit)).

## Download everything at once (not recommended) {#section_rpb_f3v_zz}

```
cd ~/dev 
git clone https://github.com/Livefyre/StreamHub-iOS-SDK.git 
cd StreamHub-iOS-SDK 
git submodule init 
git submodule update 
pod repo add livefyre https://github.com/Livefyre/cocoapods.git 
pod install 
cd examples/CommentStream 
pod install 
open CommentStream.xcworkspace
```

>[!NOTE]
>
>To run tests in Xcode 6, you must add $(PLATFORM_DIR)/Developer/Library/Frameworks to FRAMEWORK_SEARCH_PATHS in Pods-test-XCTest+OHHTTPStubSuiteCleanUp pod[https://stackoverflow.com/a/24651704](https://stackoverflow.com/a/24651704).

You need LFSTestConfig.plist file from Livefyre, which Livefyre provides upon request.

## Xcode Documentation {#section_arl_b3v_zz}

You can browse the [documentation](https://livefyre.github.com/StreamHub-iOS-SDK/) or you can build the “Documentation” target in your Xcode (requires appledoc to be installed) on your system.

## Requirements {#section_m5l_13v_zz}

StreamHub iOS SDK versions since v0.2.0 require iOS 6.0 or higher.

## Appendix (JSON support) {#section_pcd_5hv_zz}

For those looking at StreamHub-iOS SDK internals, please note that we use a modified version of [JSONKit](https://github.com/escherba/JSONKit) as the default JSON parser (instead of Apple-provided NSJSONSerialization). We had to do this because the Apple-provided parser does not support decoding JSON files that contain integers or floating point numbers that are larger than those that can be represented by the system. Our modified version of JSONKit truncates very large numbers to corresponding system maximum, instead of throwing an exception.
