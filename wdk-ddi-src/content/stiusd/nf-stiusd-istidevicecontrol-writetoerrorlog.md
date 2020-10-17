---
UID: NF:stiusd.IStiDeviceControl.WriteToErrorLog
title: IStiDeviceControl::WriteToErrorLog (stiusd.h)
description: The IStiDeviceControl::WriteToErrorLog method allows a user-mode still image minidriver to write a message into the still image error log.
old-location: image\istidevicecontrol_writetoerrorlog.htm
tech.root: image
ms.assetid: 22f9688e-1e61-46a6-a9f6-0244d7dd47ce
ms.date: 05/03/2018
keywords: ["IStiDeviceControl::WriteToErrorLog"]
ms.keywords: IStiDeviceControl interface [Imaging Devices],WriteToErrorLog method, IStiDeviceControl.WriteToErrorLog, IStiDeviceControl::WriteToErrorLog, WriteToErrorLog, WriteToErrorLog method [Imaging Devices], WriteToErrorLog method [Imaging Devices],IStiDeviceControl interface, image.istidevicecontrol_writetoerrorlog, stifnc_62f132a6-f597-4f46-9242-736a4e591942.xml, stiusd/IStiDeviceControl::WriteToErrorLog
req.header: stiusd.h
req.include-header: Stiusd.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IStiDeviceControl::WriteToErrorLog
 - stiusd/IStiDeviceControl::WriteToErrorLog
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - stiusd.h
api_name:
 - IStiDeviceControl.WriteToErrorLog
---

# IStiDeviceControl::WriteToErrorLog


## -description

The <b>IStiDeviceControl::WriteToErrorLog</b> method allows a user-mode still image minidriver to write a message into the still image error log.

## -parameters

### -param dwMessageType

Caller-supplied constant value representing the message type. The following values are defined in <i>Sti.h</i>:

STI_TRACE_INFORMATION

STI_TRACE_WARNING

STI_TRACE_ERROR

### -param pszMessage

Caller-supplied pointer to a message string to be written to the log file.

### -param dwErrorCode

<i>Not used</i>.

## -returns

If the operation succeeds, the method returns S_OK. Otherwise, it returns one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.

## -remarks

The still image error log file is named <i>sti_trace.log</i> and is located in the Windows directory. Control Panel allows a user to select which still image error types (informational, warning, or error) are written to the error log (see <a href="/windows-hardware/drivers/image/registry-entries-for-still-image-devices">Nonmodifiable Registry Entries</a>).

Error messages should be reserved for critical error conditions, such as device hardware failures. Informational messages can be used for your own debugging purposes. Logged messages aren't visible to users, but they might be used by a support engineer to help debug a user's problems.

A still image minidriver receives an <b>IStiDeviceControl</b> interface pointer as input to its <a href="/windows-hardware/drivers/ddi/stiusd/nf-stiusd-istiusd-initialize">IStiUSD::Initialize</a> method.