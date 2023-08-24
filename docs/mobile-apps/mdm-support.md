---
id: mdm-support
title: Mobile Device Management (MDM) Support on iOS Real Devices
sidebar_label: MDM Support on iOS Real Devices
---

import useBaseUrl from '@docusaurus/useBaseUrl';

<br/><p><span className="sauceGreen">Real Devices Only</span></p> 
<br/><p><span className="sauceGreen">Private Devices Only</span></p>

With our MDM support, you gain the ability to install your internal application through MDM  onto our private devices, enabling seamless policy enforcement and application management. 

## What You'll Need

- A Sauce Labs account ([Log in](https://accounts.saucelabs.com/am/XUI/#login/) or sign up for a [free trial license](https://saucelabs.com/sign-up)).
- Access to private devices.
- Service account to access your MDM(Intune) account. 

## Key Features

**MDM Profile Application**
You can seamlessly apply and download the MDM profile to our private iOS devices. This ensures centralized management and control over the testing environment.

**App Policy Enforcement**
Sauce Labs supports the enforcement of app policies, allowing you to define and apply specific policies for each testing session. These policies are consistently reapplied to maintain a consistent testing environment.

**App Allowlisting**
You have the option to allowlist your applications, ensuring that only approved apps are installed and available for testing. 

**App VPN Support**
Setting up App VPNs is made easy, enabling you to connect to your internal firewalls without the need for Sauce Connect. Certain applications, like Edge, will automatically configure VPN extensions.

**Retained App Data**
All apps can be retained on the devices of your choice, and the Apple ID used for App Store login can also be retained on the device.

## Installing MDM

1. Start any Live Testing session with the private device where you want to install your MDM.
2. Sign in with your AppleID and download Intune or install your MDM using a specific link.
3. Login with your service account to your MDM/Intune portal.
4. After successful login, download and install the MDM profile through **Settings**.
5. Navigate to **Settings > VPN and Device Management**, click on **Management Profile**, and install the MDM.
6. Once installed, click on the **Home Screen**.
7. Confirm that all the apps related to your company-managed profile have been successfully downloaded.

## Retrieving the BundleID for Allow-listing Your Apps

To prevent our cleaning from removing your application after every session, this guide will help you to obtain the bundleID for these applications. 

Follow these steps during live testing:

1. Open a Live Testing session with an iOS Device.
2. Open Device logs in VERBOSE mode.
3. Clean the device logs.
4. Copy-paste this string in the search bar `SBApplicationStateDisplayIDKey`.
5. Open the application you want to be allow-listed.
6. Check the values of `SBApplicationStateDisplayIDKey`, which is the bundleID for any given app that has been launched.

<img src={useBaseUrl('img/mobile-apps/bundle-id.png')} alt="Bundle ID" width="800"/>

## Restrictions and Recommendations

While our MDM support offers a robust framework for device management, certain limitations and recommendations should be considered during implementation:
- **Sauce-Specific MDM Policy** - You should create a Sauce-specific MDM policy, emphasizing requirements such as passcode lock settings, OS version compatibility, and application installation preferences.
- **Passcode Lock and Setup** - Avoid enforcing passcode lock or device setup to maintain user flexibility.
- **OS Version Compatibility** - Ensure compatibility with a range of iOS versions, not exclusively the latest.
- **USB Data Transfer**- Maintain USB data transfer functionality for efficient interactions.
- **Screen Recording**- We recommend that the  screen recording feature is enabled.
- **Application Installation** - Enable installation of applications to the device.