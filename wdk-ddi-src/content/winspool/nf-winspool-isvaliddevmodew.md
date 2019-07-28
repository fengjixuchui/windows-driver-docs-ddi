---
UID: NF:winspool.IsValidDevmodeW
title: IsValidDevmodeW function (winspool.h)
description: The print spooler's IsValidDevmode function verifies that the contents of a DEVMODE structure are valid.
old-location: print\isvaliddevmode.htm
tech.root: print
ms.assetid: 74da159d-7edc-44fc-abd9-aa068c4de7f2
ms.date: 04/20/2018
ms.keywords: IsValidDevmode, IsValidDevmode function [Print Devices], IsValidDevmodeA, IsValidDevmodeW, print.isvaliddevmode, spoolfnc_ea9b6cc1-6f0b-42a7-835b-df561588691a.xml, winspool/IsValidDevmode
ms.topic: function
f1_keywords:
 - "winspool/IsValidDevmode"
req.header: winspool.h
req.include-header: Winspool.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP with Service Pack 2 and later versions of Windows.
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
req.lib: Winspool.lib
req.dll: Winspool.drv
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Winspool.drv
api_name:
- IsValidDevmode
product:
- Windows
targetos: Windows
req.typenames: 
---

# IsValidDevmodeW function


## -description


The print spooler's <code>IsValidDevmode</code> function verifies that the contents of a <a href="https://docs.microsoft.com/windows/desktop/api/wingdi/ns-wingdi-_devicemodew">DEVMODE</a> structure are valid.


## -parameters




### -param pDevmode [in, optional]

Pointer to the DEVMODE structure to be validated.


### -param DevmodeSize






#### - DevModeSize

Size, in bytes, of the buffer pointed to by <i>pDevmode</i>.


## -returns



If the DEVMODE structure is valid, or if the function succeeds in repairing the structure to make it valid, the function returns <b>TRUE</b>. Otherwise, the function returns <b>FALSE</b>. The caller can obtain an error code by calling <b>GetLastError</b>.




## -remarks



Before using a DEVMODE structure obtained from a possibly unreliable source, a printer driver can call this function to verify that the structure is valid. This function validates only the public members of the DEVMODE structure. It does not check the private members of the structure.

The <b>dmSize</b> member of the DEVMODE structure specifies the size of the DEVMODE structure, not including any private, driver-specified data appended to the structure. The <b>dmDriverExtra</b> member specifies the size of the private data appended to the structure, if there is any. Callers should set <i>DevModeSize</i> to <b>dmSize</b>+<b>dmDriverExtra</b> only if they can guarantee that the input buffer size is at least that large.

This function does not require the caller to obtain elevated privileges.




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/wingdi/ns-wingdi-_devicemodew">DEVMODE</a>
 

 

