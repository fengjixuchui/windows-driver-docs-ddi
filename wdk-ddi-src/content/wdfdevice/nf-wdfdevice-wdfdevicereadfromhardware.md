---
UID: NF:wdfdevice.WdfDeviceReadFromHardware
title: WdfDeviceReadFromHardware function (wdfdevice.h)
description: The WdfDeviceReadFromHardware method is used internally by the framework. Do not use.
old-location: wdf\wdfdevicereadfromhardware.htm
tech.root: wdf
ms.assetid: 3E9ECB09-39DD-4A16-B096-24AAD96D52E9
ms.date: 02/26/2018
keywords: ["WdfDeviceReadFromHardware function"]
ms.keywords: PFN_WDFDEVICEREADFROMHARDWARE, WdfDeviceReadFromHardware, WdfDeviceReadFromHardware method, wdf.wdfdevicereadfromhardware, wdfdevice/WdfDeviceReadFromHardware, wdfhwaccess/WdfDeviceReadFromHardware
f1_keywords:
 - "wdfdevice/WdfDeviceReadFromHardware"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfDeviceReadFromHardware
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceReadFromHardware function


## -description


The <b>WdfDeviceReadFromHardware</b> method is used internally by the framework. Do not use.

Instead, use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfhwaccess/">WDF Register/Port Access Functions</a>.


## -parameters




### -param Device [in]


### -param Type [in]


### -param Size [in]


### -param TargetAddress [in]


### -param Buffer [out, optional]


### -param Count [in, optional]


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice3-readfromhardware">ReadFromHardware</a>
 

 

