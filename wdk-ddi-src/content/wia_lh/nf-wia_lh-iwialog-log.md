---
UID: NF:wia_lh.IWiaLog.Log
title: IWiaLog::Log (wia_lh.h)
description: The IWiaLog interface is obsolete for Windows XP and later, and is no longer supported. Use the Diagnostic Log Macros instead.The IWiaLog::Log method writes a diagnostic log message to Wiaservc.log.
old-location: image\iwialog_log.htm
tech.root: image
ms.assetid: bca012b4-76ae-4ba5-99b4-92a367774de7
ms.date: 05/03/2018
ms.keywords: IWiaLog interface [Imaging Devices],Log method, IWiaLog.Log, IWiaLog::Log, IWiaLog_e3605b5e-0494-46a7-85c1-3a0707a74764.xml, Log, Log method [Imaging Devices], Log method [Imaging Devices],IWiaLog interface, image.iwialog_log, wia_lh/IWiaLog::Log
ms.topic: method
req.header: wia_lh.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Me, Windows XP, and later. Obsoletefor Microsoft Windows XP and later, and is no longer supported. Instead, use the Diagnostic Log Macros.
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- wia_lh.h
api_name:
- IWiaLog.Log
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWiaLog::Log


## -description


The <b>IWiaLog</b> interface is obsolete for Windows XP and later, and is no longer supported. Use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_image/index">Diagnostic Log Macros</a> instead.The <b>IWiaLog::Log</b> method writes a diagnostic log message to <i>Wiaservc.log</i>.


## -parameters




### -param lFlags [in]

Specifies the type of diagnostic message. This parameter can be WIA_WARNING, WIA_TRACE or WIA_ERROR.


### -param lResID




### -param lDetail [in]

Specifies the diagnostic detail level of the message. This parameter can be one of the following values.

<table>
<tr>
<th>Level</th>
<th>Description</th>
</tr>
<tr>
<td>
WIALOG_LEVEL1

</td>
<td>
Logs entry and exit points for all WIA methods and functions.

</td>
</tr>
<tr>
<td>
WIALOG_LEVEL2

</td>
<td>
Logs additional details for WIALOG_LEVEL1.

</td>
</tr>
<tr>
<td>
WIALOG_LEVEL3

</td>
<td>
Logs entry and exit points for all WIA methods and functions and additional vendor-supplied functions.

</td>
</tr>
<tr>
<td>
WIALOG_LEVEL4

</td>
<td>
Logs additional details for WIALOG_LEVEL3. 

</td>
</tr>
<tr>
<td>
WIALOG_LEVELXXX

</td>
<td>
User-defined log levels.

</td>
</tr>
</table>
 


### -param bstrText [in]

Specifies the error text. The error text should be prefixed with the full name of the method or function and generate the message in the format of "class::method, error-text".


#### - lResId [in]

Specifies the resource id. This parameter should be set to WIALOG_NO_RESOURCE_ID.


## -returns



If the method succeeds, it returns S_OK.  If the method fails, it returns a standard COM error code.



