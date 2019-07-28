---
UID: NF:fltkernel.FltCbdqEnable
title: FltCbdqEnable function (fltkernel.h)
description: FltCbdqEnable enables a callback data queue that was disabled by a previous call to FltCbdqDisable.
old-location: ifsk\fltcbdqenable.htm
tech.root: ifsk
ms.assetid: cc9167cc-366e-4824-9968-1e2895a61a0c
ms.date: 04/16/2018
ms.keywords: FltApiRef_a_to_d_518b7b11-d2cd-4d69-9191-da63831da3bd.xml, FltCbdqEnable, FltCbdqEnable function [Installable File System Drivers], fltkernel/FltCbdqEnable, ifsk.fltcbdqenable
ms.topic: function
f1_keywords:
 - "fltkernel/FltCbdqEnable"
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
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
req.irql: See Remarks section
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- fltkernel.h
api_name:
- FltCbdqEnable
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltCbdqEnable function


## -description


<i>FltCbdqEnable</i> enables a callback data queue that was disabled by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcbdqdisable">FltCbdqDisable</a>. 


## -parameters




### -param Cbdq [in, out]

Pointer to the callback data queue. 


## -returns



None 




## -remarks



<i>FltCbdqEnable</i> reenables a callback data queue that was disabled by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcbdqdisable">FltCbdqDisable</a>. After the callback data queue is reenabled, it can once again accept new items. 

Minifilter drivers can use the <b>FltCbdq</b><i>Xxx</i> routines to implement a callback data queue for IRP-based I/O operations. By using these routines, minifilter drivers can make their queue cancel-safe; the system transparently handles I/O cancellation for the minifilter driver. 

The <b>FltCbdq</b><i>Xxx</i> routines can only be used for IRP-based I/O operations. To determine whether a given callback data structure represents an IRP-based I/O operation, use the <a href="https://docs.microsoft.com/previous-versions/ff544654(v=vs.85)">FLT_IS_IRP_OPERATION</a> macro. 

If the queue is protected by a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/spin-locks">spin lock</a> rather than a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mutex-objects">mutex object</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-exinitializeresourcelite">resource variable</a>, the caller of <i>FltCbdqEnable</i> can be running at IRQL <= DISPATCH_LEVEL. If a mutex or resource is used, the caller must be running at IRQL <= APC_LEVEL. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_callback_data_queue">FLT_CALLBACK_DATA_QUEUE</a>



<a href="https://docs.microsoft.com/previous-versions/ff544654(v=vs.85)">FLT_IS_IRP_OPERATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcbdqdisable">FltCbdqDisable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcbdqinitialize">FltCbdqInitialize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcbdqinsertio">FltCbdqInsertIo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcbdqremoveio">FltCbdqRemoveIo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcbdqremovenextio">FltCbdqRemoveNextIo</a>
 

 

