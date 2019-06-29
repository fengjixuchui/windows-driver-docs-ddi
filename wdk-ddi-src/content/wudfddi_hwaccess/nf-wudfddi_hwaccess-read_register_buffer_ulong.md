---
UID: NF:wudfddi_hwaccess.READ_REGISTER_BUFFER_ULONG
title: READ_REGISTER_BUFFER_ULONG function (wudfddi_hwaccess.h)
description: The READ_REGISTER_BUFFER_ULONG function reads a number of ULONG values from the specified register address into a buffer.
old-location: wdf\read_register_buffer_ulong.htm
tech.root: wdf
ms.assetid: 615A19E7-ED3B-4C41-9B3B-F4FB77811BC2
ms.date: 02/26/2018
ms.keywords: READ_REGISTER_BUFFER_ULONG, READ_REGISTER_BUFFER_ULONG function, umdf.read_register_buffer_ulong, wdf.read_register_buffer_ulong, wudfddi_hwaccess/READ_REGISTER_BUFFER_ULONG
ms.topic: function
req.header: wudfddi_hwaccess.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wudfddi_hwaccess.h
api_name:
- READ_REGISTER_BUFFER_ULONG
product:
- Windows
targetos: Windows
req.typenames: 
---

# READ_REGISTER_BUFFER_ULONG function


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>READ_REGISTER_BUFFER_ULONG</b> function reads a number of ULONG values  from the specified register address into a buffer.


## -parameters




### -param pDevice [in]

Specifies a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfdevice3">IWDFDevice3</a> interface for the device object of the device to access.


### -param Register [in]

A pointer to the register, which must be a mapped range in memory space.


### -param Buffer [out]

A pointer to a buffer into which an array of ULONG values is read.


### -param Count [in]

Specifies the number of ULONG values to be read into the buffer.


## -returns



This function does not return a value.




## -remarks



For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/reading-and-writing-to-device-registers-in-umdf-1-x-drivers">Reading and Writing to Device Registers in UMDF 1.x Drivers</a>.



