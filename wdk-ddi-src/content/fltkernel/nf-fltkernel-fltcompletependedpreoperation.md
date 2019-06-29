---
UID: NF:fltkernel.FltCompletePendedPreOperation
title: FltCompletePendedPreOperation function (fltkernel.h)
description: FltCompletePendedPreOperation resumes processing for an I/O operation that was pended in a minifilter driver's preoperation callback (PFLT_PRE_OPERATION_CALLBACK) routine.
old-location: ifsk\fltcompletependedpreoperation.htm
tech.root: ifsk
ms.assetid: bdd9f304-b26e-401e-81c7-da7d1e4f5635
ms.date: 04/16/2018
ms.keywords: FLT_PREOP_COMPLETE, FLT_PREOP_SUCCESS_NO_CALLBACK, FLT_PREOP_SUCCESS_WITH_CALLBACK, FltApiRef_a_to_d_170adc13-ea3d-4346-99b2-85d5c1c464b8.xml, FltCompletePendedPreOperation, FltCompletePendedPreOperation routine [Installable File System Drivers], fltkernel/FltCompletePendedPreOperation, ifsk.fltcompletependedpreoperation
ms.topic: function
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
req.lib: FltMgr.lib
req.dll: 
req.irql: See Remarks section.
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- FltMgr.lib
- FltMgr.dll
api_name:
- FltCompletePendedPreOperation
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltCompletePendedPreOperation function


## -description


**FltCompletePendedPreOperation** resumes processing for an I/O operation that was pended in a minifilter driver's preoperation callback ([PFLT_PRE_OPERATION_CALLBACK](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nc-fltkernel-pflt_pre_operation_callback) ) routine. 


## -parameters




### -param CallbackData

Pointer to the callback data (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>) structure for the I/O operation. This parameter is required and cannot be NULL. 


### -param CallbackStatus [in]

The status value that the minifilter driver is returning for this I/O operation. Cannot be FLT_PREOP_PENDING, FLT_PREOP_SYNCHRONIZE, or FLT_PREOP_DISALLOW_FASTIO. Must be one of the following FLT_PREOP_CALLBACK_STATUS values. For more information about the effect of these values, see the Remarks section of the reference entry for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nc-fltkernel-pflt_pre_operation_callback">PFLT_PRE_OPERATION_CALLBACK</a>. 



#### FLT_PREOP_COMPLETE

The minifilter driver is completing the I/O operation. The Filter Manager does not send the I/O operation to any minifilter drivers below the caller or to the file system. The Filter Manager only calls the postoperation callback (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nc-fltkernel-pflt_post_operation_callback">PFLT_POST_OPERATION_CALLBACK</a>) routines of the minifilter drivers above the caller. 



#### FLT_PREOP_SUCCESS_NO_CALLBACK

The minifilter driver is returning control of the I/O operation to the Filter Manager. The Filter Manager does not call the corresponding postoperation callback, if one exists, during I/O completion. 



#### FLT_PREOP_SUCCESS_WITH_CALLBACK

The minifilter driver is returning control of the I/O operation to the Filter Manager. The Filter Manager calls the corresponding postoperation callback during I/O completion. 


### -param Context [in, optional]

If FLT_PREOP_SUCCESS_WITH_CALLBACK is specified for <i>CallbackStatus</i>, this parameter is an optional context pointer to be passed to the corresponding postoperation callback routine. If FLT_PREOP_COMPLETE or FLT_PREOP_SUCCESS_NO_CALLBACK is specified for <i>CallbackStatus</i>, this parameter must be <b>NULL</b>. 


#### - Data [in]

Pointer to the callback data (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>) structure for the I/O operation. This parameter is required and cannot be <b>NULL</b>. 


## -returns



None 




## -remarks



When a minifilter driver's preoperation callback (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nc-fltkernel-pflt_pre_operation_callback">PFLT_PRE_OPERATION_CALLBACK</a>) routine posts an I/O operation to a work queue and returns FLT_PREOP_PENDING, the Filter Manager stops processing the operation. When the operation is eventually dequeued and processed, the minifilter driver must call <b>FltCompletePendedPreOperation</b> to return the operation to the Filter Manager, which then resumes processing as directed by the <i>CallbackStatus</i> specified by the minifilter driver. 

If the <i>CallbackStatus</i> parameter is FLT_PREOP_COMPLETE, <b>FltCompletePendedPreOperation</b> can be called at IRQL <= DISPATCH_LEVEL. Otherwise, callers of <b>FltCompletePendedPreOperation</b> must be running at IRQL <= APC_LEVEL. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcbdqinitialize">FltCbdqInitialize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcompletependedpostoperation">FltCompletePendedPostOperation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltqueuedeferredioworkitem">FltQueueDeferredIoWorkItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nc-fltkernel-pflt_pre_operation_callback">PFLT_PRE_OPERATION_CALLBACK</a>
 

 

