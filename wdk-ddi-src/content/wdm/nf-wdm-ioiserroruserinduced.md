---
UID: NF:wdm.IoIsErrorUserInduced
title: IoIsErrorUserInduced macro (wdm.h)
description: The IoIsErrorUserInduced routine determines whether an I/O error encountered while processing a request to a removable-media device was caused by the user.
old-location: kernel\ioiserroruserinduced.htm
tech.root: kernel
ms.assetid: 6f5e54e8-c127-44d9-b1a6-e6f7ac3b3b51
ms.date: 04/30/2018
keywords: ["IoIsErrorUserInduced macro"]
ms.keywords: IoIsErrorUserInduced, IoIsErrorUserInduced routine [Kernel-Mode Driver Architecture], k104_860a6f10-e6c0-44cd-9386-c09e356f3472.xml, kernel.ioiserroruserinduced, wdm/IoIsErrorUserInduced
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - IoIsErrorUserInduced
 - wdm/IoIsErrorUserInduced
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - IoIsErrorUserInduced
---

# IoIsErrorUserInduced macro


## -description

The <b>IoIsErrorUserInduced</b> routine determines whether an I/O error encountered while processing a request to a removable-media device was caused by the user.

## -parameters

### -param Status 

[in]
Specifies the current NTSTATUS value, usually within the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_dpc_routine">DpcForIsr</a> routine.

## -syntax

```cpp
BOOLEAN IoIsErrorUserInduced(
   Status
);
```

## -remarks

**IoIsErrorUserInduced** returns TRUE if an I/O request failed because of a user-induced error.


This routine indicates whether an I/O request failed for one of the following user-correctable conditions:  

STATUS_DEVICE_NOT_READY

STATUS_IO_TIMEOUT

STATUS_MEDIA_WRITE_PROTECTED

STATUS_NO_MEDIA_IN_DEVICE

STATUS_UNRECOGNIZED_MEDIA

STATUS_VERIFY_REQUIRED

STATUS_WRONG_VOLUME

If <b>IoIsErrorUserInduced</b> returns <b>TRUE</b>, the removable-media driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iosetharderrororverifydevice">IoSetHardErrorOrVerifyDevice</a> before completing the IRP.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateerrorlogentry">IoAllocateErrorLogEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iosetharderrororverifydevice">IoSetHardErrorOrVerifyDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iowriteerrorlogentry">IoWriteErrorLogEntry</a>

