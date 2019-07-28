---
UID: NF:usbdlib.USBD_IsInterfaceVersionSupported
title: USBD_IsInterfaceVersionSupported function (usbdlib.h)
description: The USBD_IsInterfaceVersionSupported routine is called by a USB client driver to check whether the underlying USB driver stack supports a particular USBD interface version.
old-location: buses\usbd_isusbdinterfaceversionsupported.htm
tech.root: usbref
ms.assetid: AEA5B6AA-8EEA-4D82-9991-1DE32BAE7DCE
ms.date: 05/07/2018
ms.keywords: USBD_IsInterfaceVersionSupported, USBD_IsInterfaceVersionSupported routine [Buses], buses.usbd_isusbdinterfaceversionsupported, usbdlib/USBD_IsInterfaceVersionSupported
ms.topic: function
f1_keywords:
 - "usbdlib/USBD_IsInterfaceVersionSupported"
req.header: usbdlib.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Requires WDK for Windows 8. Targets Windows Vista and later versions of the Windows operating system.
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
req.lib: Usbdex.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Usbdex.lib
- Usbdex.dll
api_name:
- USBD_IsInterfaceVersionSupported
product:
- Windows
targetos: Windows
req.typenames: 
---

# USBD_IsInterfaceVersionSupported function


## -description


The <b>USBD_IsInterfaceVersionSupported</b> routine is called by a USB client driver to check whether the underlying USB driver stack supports a particular USBD interface version.


## -parameters




### -param USBDHandle [in]

USBD handle that is retrieved by the client driver in a previous call to  the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbdlib/nf-usbdlib-usbd_createhandle">USBD_CreateHandle</a> routine.


### -param USBDInterfaceVersion [in]

A 	LONG value that represents the USBD interface version to check against the USB driver stack. Possible values include  USBD_INTERFACE_VERSION_602 or USBD_INTERFACE_VERSION_600. For more information, see Remarks.


## -returns



<b>USBD_IsInterfaceVersionSupported</b> returns TRUE if the specified USBD interface version is supported by the USB driver stack; FALSE otherwise.  For more information, see Remarks.




## -remarks



The USB driver stack loaded for a device depends on the version of Windows, the host controller hardware, and the USB device. Windows 7  and earlier versions of Windows support USBD_INTERFACE_VERSION_600. The USBD interface versions, supported by the Windows 8 driver stack, are USBD_INTERFACE_VERSION_602 and USBD_INTERFACE_VERSION_600. A USB client driver rarely needs to know about the underlying driver stack's  interface version. In cases where such information is required, the client driver can call the <b>USBD_IsInterfaceVersionSupported</b> routine to check whether a particular interface version is supported by the underlying driver stack. For instance, the client driver calls <b>USBD_IsInterfaceVersionSupported</b> to determine whether the driver stack supports USBD_INTERFACE_VERSION_602. If it supports that version, the routine returns TRUE.

The routine requires a valid USBD handle (obtained in a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbdlib/nf-usbdlib-usbd_createhandle">USBD_CreateHandle</a>).  <b>USBD_IsInterfaceVersionSupported</b> can only  be called by client drivers that target Windows Vista and later versions of Windows. Those client drivers must get Windows Driver Kit (WDK) for Windows 8 in order to call the routines successfully.  <b>USBD_IsInterfaceVersionSupported</b> replaces the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbdlib/nf-usbdlib-usbd_getusbdiversion">USBD_GetUSBDIVersion</a>  routine. 

The USBD interface version does not indicate the capabilities supported by the USB driver stack. For example just because the underlying driver stack supports  USBD_INTERFACE_VERSION_602, the client driver <i>must not</i> assume that the driver can use the static streams capability. That is because, even though the driver stack supports the capability, the host controller hardware or the USB device might not support streams. To determine whether the USB driver stack supports a certain capability, call <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/hh406230(v=vs.85)">USBD_QueryUsbCapability</a>.



