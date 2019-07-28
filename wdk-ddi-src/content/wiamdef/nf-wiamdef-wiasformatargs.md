---
UID: NF:wiamdef.wiasFormatArgs
title: wiasFormatArgs function (wiamdef.h)
description: The wiasFormatArgs function formats an argument list into a packaged string for logging.
old-location: image\wiasformatargs.htm
tech.root: image
ms.assetid: 409c4ff6-3a0e-408a-879d-2875ac245fb8
ms.date: 05/03/2018
ms.keywords: image.wiasformatargs, wiamdef/wiasFormatArgs, wiasFncs_c4e9a1bd-3760-47fb-b828-1f0c521717c5.xml, wiasFormatArgs, wiasFormatArgs function [Imaging Devices]
ms.topic: function
f1_keywords:
 - "wiamdef/wiasFormatArgs"
req.header: wiamdef.h
req.include-header: Wiamdef.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows Me and in Windows XP and later versions of the Windows operating systems.
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
req.lib: Wiaservc.lib
req.dll: Wiaservc.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Wiaservc.dll
api_name:
- wiasFormatArgs
product:
- Windows
targetos: Windows
req.typenames: 
---

# wiasFormatArgs function


## -description


The <b>wiasFormatArgs</b> function formats an argument list into a packaged string for logging.


## -parameters




### -param lpszFormat




### -param param






####### - lpszFormat, ...

Specifies a variable argument list, which starts with an ANSI format string containing the message and any format specifiers. The ellipsis (...) specifies a variable number of arguments that follow the format string.


## -returns



This function returns a BSTR containing the format string, the arguments following the format string, and a format signature.



