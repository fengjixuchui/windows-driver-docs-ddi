---
UID: NS:fltkernel._FLT_CALLBACK_DATA_QUEUE
title: _FLT_CALLBACK_DATA_QUEUE (fltkernel.h)
description: FLT_CALLBACK_DATA_QUEUE is an opaque structure that is used to specify the callback routines for a minifilter's callback data queue. Do not set the members of this structure directly. Use FltCbdqInitialize to initialize this structure.
old-location: ifsk\flt_callback_data_queue.htm
tech.root: ifsk
ms.assetid: bd0defc1-7c06-4b54-b4e3-3c17c49a6c57
ms.date: 04/16/2018
keywords: ["_FLT_CALLBACK_DATA_QUEUE structure"]
ms.keywords: "*PFLT_CALLBACK_DATA_QUEUE, FLT_CALLBACK_DATA_QUEUE, FLT_CALLBACK_DATA_QUEUE structure [Installable File System Drivers], FltSystemStructures_d43817d6-bc53-407d-8a3f-c6268112eb6e.xml, PFLT_CALLBACK_DATA_QUEUE, PFLT_CALLBACK_DATA_QUEUE structure pointer [Installable File System Drivers], _FLT_CALLBACK_DATA_QUEUE, fltkernel/FLT_CALLBACK_DATA_QUEUE, fltkernel/PFLT_CALLBACK_DATA_QUEUE, ifsk.flt_callback_data_queue"
f1_keywords:
 - "fltkernel/FLT_CALLBACK_DATA_QUEUE"
 - "FLT_CALLBACK_DATA_QUEUE"
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Windows
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- fltkernel.h
api_name:
- FLT_CALLBACK_DATA_QUEUE
targetos: Windows
req.typenames: FLT_CALLBACK_DATA_QUEUE, *PFLT_CALLBACK_DATA_QUEUE
---

# _FLT_CALLBACK_DATA_QUEUE structure


## -description


FLT_CALLBACK_DATA_QUEUE is an opaque structure that is used to specify the callback routines for a minifilter's callback data queue. Do not set the members of this structure directly. Use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqinitialize">FltCbdqInitialize</a> to initialize this structure. 




## -struct-fields


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqdisable">FltCbdqDisable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqenable">FltCbdqEnable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqinitialize">FltCbdqInitialize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqinsertio">FltCbdqInsertIo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqremoveio">FltCbdqRemoveIo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcbdqremovenextio">FltCbdqRemoveNextIo</a>
 

 

