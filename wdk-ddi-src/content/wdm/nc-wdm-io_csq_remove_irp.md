---
UID: NC:wdm.IO_CSQ_REMOVE_IRP
title: IO_CSQ_REMOVE_IRP (wdm.h)
description: The CsqRemoveIrp routine is used by the system to remove the specified IRP from a driver-implemented, cancel-safe IRP queue.
old-location: kernel\csqremoveirp.htm
tech.root: kernel
ms.assetid: 9d99a20b-3a95-4e27-96bd-41f38a631573
ms.date: 04/30/2018
keywords: ["IO_CSQ_REMOVE_IRP callback function"]
ms.keywords: CsqRemoveIrp, CsqRemoveIrp routine [Kernel-Mode Driver Architecture], DrvrRtns_6d9086c3-65b8-4e0e-b5e9-0c4edbf513b1.xml, IO_CSQ_REMOVE_IRP, kernel.csqremoveirp, wdm/CsqRemoveIrp
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
 - IO_CSQ_REMOVE_IRP
 - wdm/IO_CSQ_REMOVE_IRP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - CsqRemoveIrp
---

# IO_CSQ_REMOVE_IRP callback function


## -description

The <i>CsqRemoveIrp</i> routine is used by the system to remove the specified IRP from a driver-implemented, cancel-safe IRP queue.

## -parameters

### -param Csq 

[in]
Pointer to the <a href="/windows-hardware/drivers/kernel/eprocess">IO_CSQ</a> structure for the cancel-safe IRP queue.

### -param Irp 

[in]
Pointer to the IRP to remove from the IRP queue.

## -remarks

The driver specifies the <i>CsqRemoveIrp</i> routine for a cancel-safe IRP queue when it initializes the queue's <b>IO_CSQ</b> structure. The driver specifies the routine as the <i>CsqRemoveIrp</i> parameter of <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitialize">IoCsqInitialize</a> or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitializeex">IoCsqInitializeEx</a> when it initializes <b>IO_CSQ</b>. For more information, see <a href="/windows-hardware/drivers/kernel/cancel-safe-irp-queues">Cancel-Safe IRP Queues</a>.

The <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqremoveirp">IoCsqRemoveIrp</a> and <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqremovenextirp">IoCsqRemoveNextIrp</a> routines call the cancel-safe IRP queue's <i>CsqRemoveIrp</i> routine to remove the specified IRP from the queue. The system also uses <i>CsqRemoveIrp</i> to remove a canceled IRP from the queue.


#### Examples

To define a <i>CsqRemoveIrp</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>CsqRemoveIrp</i> callback routine that is named <code>MyCsqRemoveIrp</code>, use the IO_CSQ_REMOVE_IRP type as shown in this code example:


```
IO_CSQ_REMOVE_IRP MyCsqRemoveIrp;
```

Then, implement your callback routine as follows:


```
_Use_decl_annotations_
VOID 
 MyCsqRemoveIrp(
    PIO_CSQ  Csq,
    PIRP  Irp
    )
  {
      // Function body
  }
```

The IO_CSQ_REMOVE_IRP function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the IO_CSQ_REMOVE_IRP function type in the header file are used. For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_acquire_lock">CsqAcquireLock</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_complete_canceled_irp">CsqCompleteCanceledIrp</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_insert_irp">CsqInsertIrp</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_insert_irp_ex">CsqInsertIrpEx</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_peek_next_irp">CsqPeekNextIrp</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_release_lock">CsqReleaseLock</a>



<a href="/windows-hardware/drivers/kernel/eprocess">IO_CSQ</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitialize">IoCsqInitialize</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitializeex">IoCsqInitializeEx</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinsertirp">IoCsqInsertIrp</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinsertirpex">IoCsqInsertIrpEx</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqremoveirp">IoCsqRemoveIrp</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqremovenextirp">IoCsqRemoveNextIrp</a>