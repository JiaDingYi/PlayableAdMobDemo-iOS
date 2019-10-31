- [1 Integrate ZPLAY Ads SDK and AdMob SDK](#1-integrate-zplay-ads-sdk-and-admob-sdk)
- [2 Add ZPLAY Ads as a New Network on AdMob](#2-add-zplay-ads-as-a-new-network-on-admob)
     - [2.1 Add New App](#21-add-new-app)
     - [2.2 Add New Ad Unit](#22-add-new-ad-unit)
     - [2.3 Add ZPLAY Ads as a New Network on AdMob](#23-add-zplay-ads-as-a-new-network-on-admob)
- [3 Test](#3-Test)


## 1 Integrate ZPLAY Ads SDK and AdMob SDK

Using cocoapods as an example, here is some major steps. If you use other integration methods, please refer to [ZPLAY Ads SDK Integration Guide chapter 2.2](https://github.com/zplayads/PlayableAdsDemo-iOS/blob/master/README-EN.md#22-manual-integration) and [AdMob SDK Integration](https://developers.google.com/admob/ios/quick-start) Guide.

1. Execute `pod init` under project terminal.

2. Edit Podfile, and add library
```object-c
pod 'GoogleMobileAdsMediationZplayAds'
```
As following screenshot shows

![image](imgs/image01.png)

3. Execute `pod install --repo-update` to install dependent libraries.

> If you want to know more about Adapter and Request, please refer to the code sample in [DEMO](https://github.com/zplayads/PlayableAdMobDemo-iOS/tree/master/PlayableAdMobDemo).

## 2 Add ZPLAY Ads as a New Network on [AdMob](https://apps.admob.com/v2/home)

#### 2.1 Add New App

1. Click "Apps" in the menu bar, and then click "ADD APP" button. 
![image](imgs/018addapp1.png)

2. Choose whether your app has published in Google Play or App Store. If your App has been published in Google Play or App Store, choose "YES", otherwise choose "NO", here take unpublished as an example.
![image](imgs/018addapp2.png)

3. Enter your app information and choose a platform, and click "ADD" to add an app.
![image](imgs/019addapp3.png)

#### 2.2 Add New Ad Unit

1. After you add an App, click "NEXT: CREATE AD UNIT" button to create an ad unit for this App
![image](imgs/addunit.jpg)

2. Choose an ad format. ZPLAY Ads supports Interstitial and Rewarded now. Using Rewarded as an example. 
![image](imgs/003addadunit2RV1.png)

3. Fill in the name of Ad unit, then click "CREATE AD UNIT" to add ad unit.
![image](imgs/004addadunit2RV2.png)

4. Get app ID and ad unit ID of this ad unit. Click "DONE" to accomplish ad unit creation.
![image](imgs/005addadunit2RV3.png)

#### 2.3 Add ZPLAY Ads as a New Network on AdMob
1. Choose "Mediation" in the menu bar, and click "CREATE MEDIATION GROUP" button.
![img](imgs/007mediationgroupcreate.png)

2. Choose ad format and platform. ZPLAY Ads supports Interstitial and Rewarded now. Here take Rewarded as an example. Click "CONTINUE" button to go on. 
![img](imgs/008mediationgroupcreate1.png)

3. Fill in the name of Mediation and select locations to target. Mediation is only available when the status is Enabled, please make sure that status is Enabled. Click "ADD AD UNITS" to choose ad unit. 
![img](imgs/009mediationgroupcreat2.png)

4. Choose the app and ad unit you want to configure in the selection box, and click "DONE" to complete configuration.
![img](imgs/011mediationgroupcreate4.png)

5. Click "ADD CUSTOM EVENT" to add custom ad sources.
![img](imgs/012mediationgroupcreate5.png)

6. Fill in the label of custom ad resource, using ZPLAYAds as an example, you can customize it and set floor price according to your needs. 
![img](imgs/013mediationgroupcreate6.png)

7. Configure ZPLAY Ads ad source. Fill in adapter name in "Class Name" (as the following image shows, the class name in the picture is just a sample, please use the following adapter name).  
	- The Interstitial adapter name is `ZPLAYAdsAdMobInterstitialAdapter`.
	- The Rewarded Video adapter name is `ZPLAYAdsAdMobAdapter`.
	- The Banner adapter name is `ZplayAdsAdMobBannerAdapter` 
	- Please enter Your [App ID](https://sellers.zplayads.com/#/app/appList/) and [Ad Unit ID](https://sellers.zplayads.com/#/ad/placeList/). Note: please use the json format, like `{"AppID":"YOUR_APP_ID","AdUnitID":"YOUR_ADUNIT_ID"}`. Then click "DONE" to complete configuration.
![img](imgs/014mediationgroupcreate7.png)

Note: You are available to use the following ID when testing your App (no charge). Please replace them with the ID you applied in [ZPLAY Ads](https://sellers.zplayads.com/) when you publish your App.

| OS  | Ad Format    | App_ID                               | Ad_Unit_id                           |
| --- | ------------ | ------------------------------------ | ------------------------------------ |
| iOS | Rewarded     | A650AB0D-7BFC-2A81-3066-D3170947C3DA | BAE5DAAC-04A2-2591-D5B0-38FA846E45E7 |
| iOS | Interstitial | A650AB0D-7BFC-2A81-3066-D3170947C3DA | 0868EBC0-7768-40CA-4226-F9924221C8EB |

8. You can see ZPLAY Ads in Ad sources list. Click "SAVE" to complete ZPLAYAds configuration.
![img](imgs/015mediationgroupcreate8.png)

9. Check whether third-party ad source has been added successfully. In the Apps list, find the application and ad unit selected in step d. The active number in the "mediation groups" increased, indicating that the ad source is successfully configured.
![img](imgs/016mediationgroupcreate9.png)


## 3 Test

You are available to use the following ID when testing your App (no charge). Please replace them with the ID you applied in [ZPLAY Ads](https://sellers.zplayads.com/) when you publish your App.

| OS  | Ad Format    | App_ID                               | Ad_Unit_id                           |
| --- | ------------ | ------------------------------------ | ------------------------------------ |
| iOS | Rewarded     | A650AB0D-7BFC-2A81-3066-D3170947C3DA | BAE5DAAC-04A2-2591-D5B0-38FA846E45E7 |
| iOS | Interstitial | A650AB0D-7BFC-2A81-3066-D3170947C3DA | 0868EBC0-7768-40CA-4226-F9924221C8EB |
