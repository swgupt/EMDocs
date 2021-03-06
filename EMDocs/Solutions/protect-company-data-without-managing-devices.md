---
# required metadata

title: Protect company data without managing devices | Microsoft Docs
description: EMS delivers innovative data loss protection capabilities with Microsoft Intune. With it, you can protect company data and preserve the great user experience with Office 365 apps that employees are accustomed to without managing their devices.
keywords:
author: jeffgilb
manager: swadhwa
ms.date: 01/23/2017
ms.topic: solution
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: b46877f3-cf32-4919-ba63-4df55cd2af32

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: vlpetros
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Protect company data without managing devices with Intune
We live in a mobile world where employees require on the go access to corporate data and productivity tools on their own mobile devices. Because of its popularity and importance, many organizations are looking to further protect Office 365 data by preventing data loss from Office mobile apps while preserving great end user experiences. IT needs to protect access to Office 365 and prevent data loss of corporate data from mobile devices and apps that the organization does not own or manage. Trouble is, while IT needs to keep corporate data secure, many employees have a privacy concern when IT takes control over their personal device.

## How can Enterprise Mobility + Security (EMS) help you?

EMS delivers innovative data loss protection capabilities with Microsoft Intune. With it, you can protect company data and preserve the great user experience with Office 365 apps that employees are accustomed to. And you can do it without requiring users to enroll their devices for management, which can significantly increase the chances of success of your BYOD program and end user compliance with IT policies. You get the control you need and users enjoy modern experience they've come to expect.  Because Microsoft Intune works directly with Azure Active Directory and Office 365 to manage access and protect company data, there’s no need to install and maintain an on-premises infrastructure or to route all traffic through it.

### Recommended solution

Microsoft Intune empowers organizations to provide access to mobile apps and protect Office 365 data leaks without requiring employees to enroll into device management. Device management (MDM) can still be done if needed, but it is now optional. Intune's powerful application protection capabilities help IT protect company data at the app level without having to manage actual devices. For highly confidential data, protection can be extended even further to the file level with Azure Information Protection. Employees, vendors, and partners can use their favorite mobile devices to access familiar productivity tools and corporate data without risking intrusion on their privacy. And if IT already has an MDM solution in place, Intune can add advanced Office 365 access control data loss protection without requiring devices be unenrolled from the current MDM solution and re-enrolled into Intune MDM.

Watch this demo to see how you can prevent data loss from mobile apps (including O365 and your internal line-of-business (LOB) apps) using Intune’s innovative application protection capabilities that do not require enrollment of user devices into Intune MDM:

<iframe width="675" height="480"  src="https://www.youtube.com/embed/BcwgKmsAy18?list=TLGGQ9qBhVYxOZIxMzEyMjAxNg" frameborder="0" allowfullscreen></iframe>

### How to implement this solution

The rest of this solution is divided into the following sections that show you how to protect Office 365 company data with Intune:

- **Protect app data with Intune mobile app protection policies**. This section describes how to create and deploy Microsoft Intune application protection policies to provide data loss prevention capabilities (like copy/paste/save as/PIN/encryption/selective wipe/etc.) to users of unmanaged mobile devices.

- **Allow only mobile apps that support app protection policies to access Office 365 services**. In this section you learn how create a policy that allows only mobile apps that support Intune MAM policies to access O365 services like Exchange Online.

## Protect app data with Intune mobile app protection policies

When protecting app data on unmanaged devices, you don’t deploy apps like you would with managed devices. Instead, users download Office 365 apps from the public app store on their personal iOS or Android devices and then log in with their work accounts just like usual.

App protection policies for those apps are simple to create for iOS and Android devices in the Azure portal. These kinds of policies allow you to restrict user actions like cut, copy, paste, and save as or enforce a PIN, require encryption, and selectively wipe company data from mobile apps. When they are assigned to users, app protection policies are automatically applied by Intune and enforced between personal and work accounts and apps. Because Intune is seamlessly integrated with Azure AD and Office 365, work data is protected while personal data in the same Office apps remains untouched.

>[!NOTE]
>App protection polices like these are available for Windows 10 computers managed by Intune as mobile devices using [Windows Information Protection (WIP)  policies](https://technet.microsoft.com/itpro/windows/keep-secure/create-wip-policy-using-intune).

Here’s how easy it is to select apps to protect, configure app protection policy settings, and deploy policy to groups of end users after you log into the Azure portal:

>[!TIP]
>To find the Intune app protection policy settings, just log into [the Azure portal](https://portal.azure.com) with your Intune administrator credentials and search for **Intune App Protection** in the *Search resources* box at the top of the portal. All of the following steps are completed from there.

-   **Create a mobile app protection policy.** Other than naming (and optionally providing a description) for the policy, all you need to do to [create an app protection policy](https://docs.microsoft.com/intune-azure/manage-apps/app-protection-policies#create-an-app-protection-policy) is to define the platform, select the apps you want to protect, and configure the policy settings to enforce:

> **Define the platform**: You’ll be able to select either the iOS or Android platforms when creating a new policy, but you won’t be able to create app protection policies for Windows devices here. Instead, you can [use Windows Information Protection (WIP) policies](https://technet.microsoft.com/itpro/windows/keep-secure/create-wip-policy-using-intune).

> **Select one or more apps** to target from the list of available apps capable of being protected on unmanaged devices. As more apps become supported, they’ll automatically be added to the list of available apps. By default, none are selected, but you can CTRL+Click to multi-select as many apps as you’d like to protect with the policy. Alternatively, you can [add our own line of business (LOB) app](https://docs.microsoft.com/intune/deploy-use/protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune) for iOS or Android.

> **Configure required policy settings** [for iOS or Android](https://docs.microsoft.com/en-us/intune-azure/manage-apps/app-protection-policies#policy-settings) for Data Relocation (cut, copy, paste, save as, encryption, etc.) and Access (require a PIN, offline interval, etc.).

- **Deploy the app protection policy to user groups** by [selecting the user groups](https://docs.microsoft.com/intune-azure/manage-apps/app-protection-policies#deploy-a-policy-to-users) the policies will apply to. This can be the same groups you already manage in Office 365 or any group available in Azure Active Directory.

The first time an end user opens an app protected by an app protection policy, they will receive a message telling them that their IT department is now protecting company data in the app. If the policy Access settings have been configured to require a PIN or password, the user will also be prompted to create one before gaining access the protected app as shown below from an Android device:

![App protection policy PIN reqirement](..\Solutions\media\protect-company-data-without-managing-devices\protect-company-data-without-managing-devices-fig1.png)

Because app protection polices work at the application instead of device level, Intune makes it easy for IT to protect company data by restricting the sharing of company data between managed and personal apps, between corporate and personal accounts within the same app, and only allowing corporate data to be saved to approved locations. Mobile employees no longer need to give up control of their devices to get access to vital corporate tools and data on the go.

>[!TIP]
>For highly confidential data, protection can be extended even further to the file level with the protection technology used by Azure Information Protection: [Azure Rights Management (Azure RMS).](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)

## Allow only mobile apps that support app protection policies to access Office 365 services
By default, all users and all apps have access to company information hosted by Exchange Online. With Intune you can easily control who and what apps are granted access by configuring app conditional access policies that restrict access to Office 365 services to only apps that support Intune’s app protection policies. For example, from [the Azure portal](https://portal.azure.com) you can create a policy that restricts access to Exchange Online to only certain groups and apps on Android and iOS whether the device is managed or not.

- **Create an app protection conditional access policy to Exchange Online.** [These policies are created](https://docs.microsoft.com/intune/deploy-use/mam-ca-for-exchange-online) in the same place as the app protection polices discussed earlier. In addition to defining the apps allowed to access Exchange Online, you’ll also need to define user access groups to manage connections to Exchange Online.

- Users will need to **configure a broker app** the first time that they try to use a policy supported app to access Exchange Online. For iOS devices the broker app is the Microsoft Authenticator app and Android devices will need to install the Intune Company Portal app. While [these broker apps](https://docs.microsoft.com/intune/deploy-use/use-apps-with-mam-ca) will register the device with Azure AD to provide device identity verification, they will not enroll the device into management.

With the conditional access policy for Exchange Online in place, users will receive an email similar to the following when they try to access their corporate email using the native email client as shown on an Android device:

![App protection policy Outlook app requirement](..\Solutions\media\protect-company-data-without-managing-devices\protect-company-data-without-managing-devices-fig2.png)

When the end user taps the *Get started now* link in the email, the default web browser for the device opens and displays https://portal.manage.microsoft.com/OutlookRedirect.aspx. From there, the user is prompted to install the free Microsoft Outlook app from the app store used by the device.

### Learn more

[Start using Enterprise Mobility + Security](https://docs.microsoft.com/enterprise-mobility/solutions/ems-get-started)

[Microsoft Enterprise Mobility](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)
