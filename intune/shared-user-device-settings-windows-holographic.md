---
# required metadata

title: Windows Holographic Business shared device settings - Microsoft Intune - Azure | Microsoft Docs
description: Add and use Windows Holographic for Business to configure devices that are shared, or used by multiple users in Microsoft Intune. See a list of the Account Management settings and what they do on the devices, including Microsoft HoloLens. 
keywords:
author: MandiOhlinger

ms.author: mandia
manager: dougeby
ms.date: 01/09/2019
ms.topic: conceptual
ms.prod:
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology:
ms.assetid:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
---

# Windows Holographic for Business settings to manage shared devices using Intune

Windows Holographic for Business devices, such as the Microsoft HoloLens, can be used by multiple users. Devices that have multiple users are called shared devices, and are a part of mobile device management (MDM) solutions.

Using Microsoft Intune, users can sign in to these shared devices with a guest account. As they use the device, they only get access to features you allow.

This article lists and describes the settings you use in a Windows Holographic for Business device configuration profile. When the profile is created in Intune, you then deploy or assign the profile to device groups in your organization. You can also assign this profile to a device group with mixed device types and OS versions.

For more information on this feature in Intune, see [Control access, accounts, and power features on shared PC or multi-user devices](shared-user-device-settings.md). For more information on the Windows CSP, see [AccountManagement CSP](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp).

## Before your begin

[Create the profile](shared-user-device-settings.md).

## Shared multi-user device settings

> [!NOTE]
> Devices that run Windows Holographic for Business, including the Microsoft HoloLens, only support the **Account management** settings. If you configure any of the other settings shown in Intune, including **Shared PC mode**, it has no impact on these devices.

- **Account management**: Set to **Enable** to automatically delete local accounts created by guests, and accounts in AD and Azure AD. When a user signs off the device, or when system maintenance runs, these accounts are deleted. When enabled, also set:
  - **Account Deletion**: Choose when accounts are deleted: **At storage space threshold**, **At storage space threshold and inactive threshold**, or **Immediately after log-out**. Also enter:
    - **Start delete threshold(%)**: Enter a percentage (0-100) of disk space. When the total disk/storage space drops below the value you enter, the cached accounts are deleted. It continuously deletes accounts to reclaim disk space. Accounts that are inactive the longest are deleted first.
    - **Stop delete threshold(%)**: Enter a percentage (0-100) of disk space. When the total disk/storage space meets the value you enter, the deleting stops.

  Set to **Disable** to keep the local, AD, and Azure AD accounts created by guests.

  > [!NOTE]
  > Microsoft HoloLens devices only support the **Account management** settings.

## Next steps

- [Assign the profile](device-profile-assign.md) and [monitor its status](device-profile-monitor.md).
- See the settings for [Windows 10 and newer](shared-user-device-settings-windows.md).
