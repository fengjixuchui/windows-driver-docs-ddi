---
UID: NF:wudfddi_hwaccess.WRITE_REGISTER_BUFFER_USHORT
title: WRITE_REGISTER_BUFFER_USHORT function (wudfddi_hwaccess.h)
description: The WRITE_REGISTER_BUFFER_USHORT routine writes a number of USHORT values from a buffer to the specified register.
old-location: wdf\write_register_buffer_ushort.htm
tech.root: wdf
ms.assetid: 45E51355-9570-4548-B056-D1655BED5462
ms.date: 02/26/2018
keywords: ["WRITE_REGISTER_BUFFER_USHORT function"]
ms.keywords: WRITE_REGISTER_BUFFER_USHORT, WRITE_REGISTER_BUFFER_USHORT function, umdf.write_register_buffer_ushort, wdf.write_register_buffer_ushort, wudfddi_hwaccess/WRITE_REGISTER_BUFFER_USHORT
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
targetos: Windows
req.typenames: 
f1_keywords:
 - WRITE_REGISTER_BUFFER_USHORT
 - wudfddi_hwaccess/WRITE_REGISTER_BUFFER_USHORT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wudfddi_hwaccess.h
api_name:
 - WRITE_REGISTER_BUFFER_USHORT
---

# WRITE_REGISTER_BUFFER_USHORT function (wudfddi_hwaccess.h)


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>WRITE_REGISTER_BUFFER_USHORT</b> routine writes a number of USHORT values from a buffer to the specified register.

## -parameters

### -param pDevice 

[in]
Specifies a pointer to the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice3">IWDFDevice3</a> interface for the device object of the device to access.

### -param Register 

[in]
A pointer to the register, which must be a mapped range in memory space.

### -param Buffer 

[in]
A pointer to a buffer into which an array of USHORT values is to be written.

### -param Count 

[in]
Specifies the number of USHORT values to write to the register.

## -remarks

The size of the buffer must be large enough to contain at least the specified number of bytes.

For more information, see <a href="/windows-hardware/drivers/wdf/reading-and-writing-to-device-registers-in-umdf-1-x-drivers">Reading and Writing to Device Registers in UMDF 1.x Drivers</a>.