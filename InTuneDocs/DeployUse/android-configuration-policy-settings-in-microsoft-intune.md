---
title: Android configuration policy settings in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 71cc39cf-e726-40fd-8d08-78776e099a4b
author: robstackmsft
---
# Android configuration policy settings in Microsoft Intune
Use the [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)] **Android general configuration policy** to configure settings for:

-   **Mobile device security settings** – Choose from a list of predefined settings that let you control a range of features and functionality on the device.

-   **Kiosk mode** (for Samsung KNOX devices only) - Lock a device to only allow certain features to work. For example, you can allow a device to only run one managed app that you specify, or you can disable the volume buttons on a device. These settings might be used for a demonstration model of a device, or a device that is dedicated to performing only one function, such as a point of sale device.

-   **Compliant and noncompliant apps** - Specify a list of apps that are compliant, or not compliant in your company. On Android and iOS devices, the **Noncompliant Apps Report** can be used to view the compliance of apps you specified in the list against the apps that users have installed (but cannot actually block the installation of the app).

> [!TIP]
> You can configure terms and conditions for users to ensure that they acknowledge that apps on their device, including personal apps will be evaluated, and noncompliant apps will either be blocked, or reported as noncompliant. Users must accept these terms and conditions before they can enroll their device and use the company portal to get apps. For more information about using terms and conditions, see [Working with terms and conditions policies in Microsoft Intune](http://msdn.microsoft.com/en-us/library/ce59fb93-01fd-4822-a57d-45ca7d89843d).

If the setting you are looking for does not appear in this topic, you might be able to create it using an Android custom policy that lets you use OMA-URI settings to control the device. For more information, see [Android custom policy settings in Microsoft Intune](android-custom-policy-settings-in-microsoft-intune.md).

## Password settings

|Setting name|Details|Android 4.0+|Samsung KNOX|
|----------------|-|----------------|----------------|
|**Require a password to unlock mobile devices**|Require a password on supported devices.|Yes|Yes|
|**Minimum password length**|The minimum length for the password.|Yes|Yes|
|**Number of repeated sign-in failures to allow before the device is wiped**|Wipes the device if this number of login attempts fail.|Yes|Yes|
|**Minutes of inactivity before screen turns off**|Specify the number of minutes before the device automatically locks.|Yes|Yes|
|**Password expiration (days)**|The number of days before a password must be changed.|Yes|Yes|
|**Remember password history**|Remember this many previously used passwords.|Yes|Yes|
|**Remember password history** – **Prevent reuse of previous passwords**|Prevents re-using previously used passwords.|Yes|Yes|
|**Password quality**|Select the password complexity level required and also whether biometric devices can be used.|Yes|Yes|
|**Allow fingerprint unlock**|Allow the use of a fingerprint to unlock the device.|No|Yes|

## Encryption settings

|Setting name|Details|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Require encryption on mobile device**|Requires that files on the mobile device are encrypted.|Yes|Yes|
|**Require encryption on storage cards**|Specifies whether the device storage card must be encrypted.|No|Yes|

## System settings

|Setting name|Details|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Allow screen capture**|Let's the user capture the screen contents as an image.|No|Yes|
|**Allow diagnostic data submission**|Allows the device to submit diagnostic information to Google.|No|Yes|
|**Allow factory reset**|Allow the user to perform a factory reset on the device.|No|Yes|

## Cloud settings – documents and data

|Setting name|Details|Android and Samsung KNOX|Android 4.0+|
|----------------|----------------------------|----------------|
|**Allow Google backup**|Allows use of Google backup.|No|Yes|

## Cloud settings – accounts and synchronization

|Setting name|Details|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Allow Google account auto sync**|Allows Google account settings to be automatically synchronized.|No|Yes|

## Application settings - browser

|Setting name|Details|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Allow web browser**|Specifies whether the device web browser can be used.|No|Yes|
|**Allow autofill**|Allow the Autofill function of the web browser to be used.|No|Yes|
|**Allow pop-up blocker**|Allows the use of the pop-up blocker in the web browser.|No|Yes|
|**Allow cookies**|No|Yes|
|**Allow active scripting**|No|Yes|

## Application settings - apps

|Setting name|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Allow Google Play store**|No|Yes|

## Device capabilities settings - hardware

|Setting name|Details|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Allow camera**|Allows the use of the device camera.|Yes|Yes|
|**Allow removable storage**|Allows the device to use removable storage, like an SD card.|No|Yes|
|**Allow Wi-Fi**|Allows the use of the Wi-Fi capabilities of the device.|No|Yes|
|**Allow Wi-Fi tethering**|Allows the use of Wi-Fi tethering on the device.|No|Yes|
|**Allow geolocation**|Allows the device to utilize location information.|No|Yes|
|**Allow NFC**|Allows operations that use near field communication if the device supports it.|No|Yes|
|**Allow Bluetooth**|Allows the use of Bluetooth on the device.|No|Yes|
|**Allow power off**|Allows the user to power off the device.<br /><br />If this setting is disabled, the setting **Number of repeated sign in failures to allow before the device is wiped** for Samsung KNOX devices does not function.|No|Yes|

## Device capabilities settings - cellular

|Setting name|Details|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Allow voice roaming**|-|No|Yes|
|**Allow data roaming**|Allow data roaming when the device is on a cellular network.|No|Yes|
|**Allow SMS/MMS messaging**|-|No|Yes|

## Device capabilities settings - features

|Setting name|Details|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Allow voice assistant**|Allows the use of voice assistant software on the device.|No|Yes|
|**Allow voice dialing**|No|Yes|
|**Allow copy and paste**|Allow copy and paste functions on the device.|No|Yes|
|**Allow clipboard share between applications**|Use the clipboard to copy and paste between apps.|No|Yes|
|**Allow YouTube**|Allow the use of YouTube on the device.|No|Yes|

## Settings for compliant and noncompliant apps
In the **Compliant &amp; Noncompliant Apps** list, specify a list of compliant or noncompliant apps using the following information:

> [!NOTE]
> A single policy can only contain a list of compliant, or a list of noncompliant apps. You cannot specify both in the same policy.

|Setting name|Details|
|----------------|--------------------|
|**Report noncompliance when users install the listed apps**|Lists the apps that are not managed by Intune which users are not allowed to install and run.|
|**Do not report noncompliance when users install the listed apps**|Lists the apps that users are allowed to install. To remain compliant, users must not install apps that are not listed. Apps that are managed by Intune are automatically allowed.|
|**Add**|Adds an app to the selected list. Specify a name of your choice, optionally the app publisher, and the URL to the app in the app store.<br /><br />[How to specify URLs to app stores](ios-configuration-policy-settings-in-microsoft-intune.md#BKMK_URL)|
|**Import Apps**|Imports a list of apps you have specified in a comma-separated values file. Use the format, application name, publisher, app URL in the file.|
|**Edit**|Let’s you edit the name, publisher and URL of the selected app.|
|**Delete**|Deletes the selected app from the list.|

## Kiosk mode settings
Specify the following settings for **Samsung KNOX devices**:

|Setting name|Details|
|----------------|--------------------|
|**Select a managed app that will be allowed to run when the device is in kiosk mode**|Click **Browse**, then select the managed app, or app from a store that will be allowed to run when the device is in kiosk mode. No other apps will be allowed to run on the device.<br /><br />[How to specify URLs to app stores](ios-configuration-policy-settings-in-microsoft-intune.md#BKMK_URL)|
|**Allow volume buttons**|Enables or disables the use of the volume buttons on the device.|
|**Allow screen sleep wake button**|Enables or disables the screen sleep wake button on the device.|

## Reference information for compliant and noncompliant apps

### Monitor compliant and noncompliant apps
Use the **Noncompliant Apps Report** to view the compliance of allowed and blocked apps.

##### To run the Noncompliant Apps Report

1.  In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Reports** &gt; **Noncompliant Apps Report**.

2.  Select the device groups that you would like to check, whether you want to check for compliant apps, noncompliant apps, or both, then click **View Report**.

### <a name="BKMK_URL"></a>How to specify URLs to app stores
To specify an app URL in the compliant and noncompliant apps list, or in the **Select a managed app that will be allowed to run when the device is in kiosk mode** option (iOS only), use the following format:

In the [Apps section of Google Play](https://play.google.com/store/apps), search for the app you want to use.

Open the installation page for the app, and copy the URL to the clipboard. You can now use this as the URL in either the compliant or noncompliant apps list.

**Example:** Search Google Play for Microsoft Office Mobile. The URL you use will be **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub**.

### See Also
[Use policies to manage computers and mobile devices with Microsoft Intune](use-policies-to-manage-computers-and-mobile-devices-with-microsoft-intune.md)
