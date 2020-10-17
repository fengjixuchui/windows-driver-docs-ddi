---
UID: NC:pepfx.PEPCALLBACKNOTIFYDPM
title: PEPCALLBACKNOTIFYDPM (pepfx.h)
description: An AcceptDeviceNotification event callback routine handles device power management (DPM) notifications from the Windows power management framework (PoFx).
old-location: kernel\acceptdevicenotification.htm
tech.root: kernel
ms.assetid: 56446DA9-EAE9-4EEF-9299-892B7384D506
ms.date: 04/30/2018
keywords: ["PEPCALLBACKNOTIFYDPM callback function"]
ms.keywords: AcceptDeviceNotification, AcceptDeviceNotification routine [Kernel-Mode Driver Architecture], PEPCALLBACKNOTIFYDPM, kernel.acceptdevicenotification, pepfx/AcceptDeviceNotification
req.header: pepfx.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PEPCALLBACKNOTIFYDPM
 - pepfx/PEPCALLBACKNOTIFYDPM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - pepfx.h
api_name:
 - AcceptDeviceNotification
---

# PEPCALLBACKNOTIFYDPM callback function (pepfx.h)


## -description

An <i>AcceptDeviceNotification</i> event callback routine handles device power management (DPM) notifications from the Windows <a href="/windows-hardware/drivers/ddi/index">power management framework</a> (PoFx).

## -parameters

### -param Notification 

[in]
The DPM notification ID. This parameter specifies the type of DPM notification that PoFx is sending. For a list of DPM notification IDs, see <a href="/windows-hardware/drivers/ddi/index">Device power management (DPM) notifications</a>.

### -param Data 

[in, out, optional]
A pointer to a PoFx-allocated structure that contains the input and/or output data for this notification. The type of this structure depends on the notification ID specified by <i>Notification</i>. For a list of the structure types that are defined for the various DPM notification IDs, see <a href="/windows-hardware/drivers/ddi/index">Device power management (DPM) notifications</a>.

## -returns

The <i>AcceptDeviceNotification</i> routine must return TRUE if it handles the notification, or FALSE if it does not.

## -remarks

This routine is implemented by the platform extension plug-in (PEP) for a device. The <b>AcceptDeviceNotification</b> member of the <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_information">PEP_INFORMATION</a> structure is a pointer to an <i>AcceptDeviceNotification</i> routine. The PEP calls the <a href="/windows-hardware/drivers/ddi/pepfx/nf-pepfx-pofxregisterplugin">PoFxRegisterPlugin</a> or <a href="/windows-hardware/drivers/ddi/pepfx/nf-pepfx-pofxregisterpluginex">PoFxRegisterPluginEx</a> routine to register the PEP's <i>AcceptDeviceNotification</i> routine with PoFx.

PoFx calls this routine to send a DPM notification to the PEP. In this call, the <i>Notification</i> parameter specifies the type of notification, and the <i>Data</i> parameter points to a data structure of the type that is associated with this notification. For a list of DPM notification IDs and their associated structure types, see <a href="/windows-hardware/drivers/ddi/index">Device power management (DPM) notifications</a>.

DPM notifications inform the PEP about various system, device, or componentÂ–-level events, or pass requests from the device driver to the PEP.

The <i>AcceptDeviceNotification</i> routine does not have to accept every request from the  device driver—for example, it can ignore idle residency hints. However, the PEP must understand and accept most device power management notifications even if the PEP chooses not to act on them. The PEP must refuse to handle (by returning FALSE) every notification that it does not recognize.

The <i>AcceptDeviceNotification</i> routine can be called at IRQL <= DISPATCH_LEVEL. The IRQL at which the PEP's <i>AcceptAcpiNotification</i> routine is called varies according to the type of notification that is being sent. The notification type is specified by the <i>Notification</i> parameter. For more information, see the individual reference pages under <a href="/windows-hardware/drivers/ddi/index">Device power management (DPM) notifications</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_information">PEP_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/pepfx/nf-pepfx-pofxregisterplugin">PoFxRegisterPlugin</a>



<a href="/windows-hardware/drivers/ddi/pepfx/nf-pepfx-pofxregisterpluginex">PoFxRegisterPluginEx</a>