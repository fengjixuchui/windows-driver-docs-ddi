---
UID: NF:wudfddi_hwaccess.WRITE_PORT_BUFFER_ULONG
title: WRITE_PORT_BUFFER_ULONG function (wudfddi_hwaccess.h)
description: The WRITE_PORT_BUFFER_ULONG function writes a number of ULONG values from a buffer to the specified port address.
old-location: wdf\write_port_buffer_ulong.htm
tech.root: wdf
ms.assetid: B5C6FA66-617E-4DB1-A62A-3F3F41E971B0
ms.date: 02/26/2018
keywords: ["WRITE_PORT_BUFFER_ULONG function"]
ms.keywords: WRITE_PORT_BUFFER_ULONG, WRITE_PORT_BUFFER_ULONG function, umdf.write_port_buffer_ulong, wdf.write_port_buffer_ulong, wudfddi_hwaccess/WRITE_PORT_BUFFER_ULONG
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
 - WRITE_PORT_BUFFER_ULONG
 - wudfddi_hwaccess/WRITE_PORT_BUFFER_ULONG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wudfddi_hwaccess.h
api_name:
 - WRITE_PORT_BUFFER_ULONG
---

# WRITE_PORT_BUFFER_ULONG function (wudfddi_hwaccess.h)


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>WRITE_PORT_BUFFER_ULONG</b> function writes a number of ULONG values from a buffer to the specified port address.

## -parameters

### -param pDevice 

[in]
Specifies a pointer to the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice3">IWDFDevice3</a> interface for the device object of the device to access.

### -param Port 

[in]
A pointer to the port, which must be a mapped memory range in I/O space.

### -param Buffer 

[in]
A pointer to a buffer from which an array of ULONG values is to be written.

### -param Count 

[in]
Specifies the number of ULONG values to be written to the buffer.

## -remarks

For more information, see <a href="/windows-hardware/drivers/wdf/reading-and-writing-to-device-registers-in-umdf-1-x-drivers">Reading and Writing to Device Registers in UMDF 1.x Drivers</a>.