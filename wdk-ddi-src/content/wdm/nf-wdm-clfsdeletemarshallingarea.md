---
UID: NF:wdm.ClfsDeleteMarshallingArea
title: ClfsDeleteMarshallingArea function (wdm.h)
description: The ClfsDeleteMarshallingArea routine deletes a marshalling area.
old-location: kernel\clfsdeletemarshallingarea.htm
tech.root: kernel
ms.assetid: 8aa7aec3-85d7-40a2-a63d-bee8c5ce1ff9
ms.date: 04/30/2018
keywords: ["ClfsDeleteMarshallingArea function"]
ms.keywords: ClfsDeleteMarshallingArea, ClfsDeleteMarshallingArea routine [Kernel-Mode Driver Architecture], Clfs_a015edd3-4625-4b24-995f-75217a711528.xml, kernel.clfsdeletemarshallingarea, wdm/ClfsDeleteMarshallingArea
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
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
req.lib: Clfs.lib
req.dll: Clfs.sys
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - ClfsDeleteMarshallingArea
 - wdm/ClfsDeleteMarshallingArea
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Clfs.sys
 - Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
 - ClfsDeleteMarshallingArea
---

# ClfsDeleteMarshallingArea function


## -description

The <b>ClfsDeleteMarshallingArea</b> routine deletes a marshalling area.

## -parameters

### -param pvMarshalContext 

[in]
A pointer to an opaque context that represents a marshalling area. The caller previously obtained this pointer by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfscreatemarshallingarea">ClfsCreateMarshallingArea</a>.

## -returns

<b>ClfsDeleteMarshallingArea</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.

## -remarks

Before deleting the marshalling area, <b>ClfsDeleteMarshallingArea</b> flushes all of the log I/O blocks associated with the marshalling area.

The marshalling area goes away only after all references to it go away. For example, the marshalling area remains in memory if it still has an open read context.

For an explanation of CLFS concepts and terminology, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-common-log-file-system">Common Log File System</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-clfscreatemarshallingarea">ClfsCreateMarshallingArea</a>

