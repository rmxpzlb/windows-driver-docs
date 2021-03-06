---
title: Handling a GUID\_TARGET\_DEVICE\_REMOVE\_COMPLETE Event
author: windows-driver-content
description: Handling a GUID\_TARGET\_DEVICE\_REMOVE\_COMPLETE Event
ms.assetid: 7f20faae-b5ef-4a64-9150-bff14b04aaa4
keywords: ["notifications WDK PnP , target device changes", "target device change notifications WDK PnP", "EventCategoryTargetDeviceChange notification", "GUID_TARGET_DEVICE_REMOVE_COMPLETE"]
ms.author: windowsdriverdev
ms.date: 06/16/2017
ms.topic: article
ms.prod: windows-hardware
ms.technology: windows-devices
---

# Handling a GUID\_TARGET\_DEVICE\_REMOVE\_COMPLETE Event


## <a href="" id="ddk-handling-a-guid-target-device-remove-complete-event-kg"></a>


Before the PnP manager sends an [**IRP\_MN\_REMOVE\_DEVICE**](https://msdn.microsoft.com/library/windows/hardware/ff551738) IRP to the drivers for a device, the PnP manager calls any kernel-mode notification callback routines that registered for **EventCategoryTargetDeviceChange** on the device. The PnP manager specifies a *NotificationStructure*.**Event** of GUID\_TARGET\_DEVICE\_REMOVE\_COMPLETE.

When handling a GUID\_TARGET\_DEVICE\_REMOVE\_COMPLETE event, a notification callback routine should:

-   Remove notification registration on the device.

    The device has been removed, so the driver calls [**IoUnregisterPlugPlayNotification**](https://msdn.microsoft.com/library/windows/hardware/ff550398) to remove the notification registration.

    The device may still be physically present on the machine, but all device objects have been deleted and the device is not available for use.

-   Perform surprise-remove processing if the driver did not receive a previous query-remove notification.

    If a device is surprise-removed, the PnP manager sends registered drivers a remove-complete notification without a prior query-remove notification. In this case a driver has to perform any necessary cleanup, such as closing any handles to the device and removing any outstanding references to the file object.

 

 


--------------------
[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bkernel\kernel%5D:%20Handling%20a%20GUID_TARGET_DEVICE_REMOVE_COMPLETE%20Event%20%20RELEASE:%20%286/14/2017%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")


