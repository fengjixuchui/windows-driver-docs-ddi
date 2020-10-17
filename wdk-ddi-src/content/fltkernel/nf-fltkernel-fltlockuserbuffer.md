---
UID: NF:fltkernel.FltLockUserBuffer
title: FltLockUserBuffer function (fltkernel.h)
description: The FltLockUserBuffer routine locks the user buffer for a given I/O operation.
old-location: ifsk\fltlockuserbuffer.htm
tech.root: ifsk
ms.assetid: ab8e873b-b16d-45fc-b732-6d390ae60ce9
ms.date: 04/16/2018
keywords: ["FltLockUserBuffer function"]
ms.keywords: FltApiRef_e_to_o_7d39ba00-c97d-4adb-a0e1-a019ca4056b0.xml, FltLockUserBuffer, FltLockUserBuffer routine [Installable File System Drivers], fltkernel/FltLockUserBuffer, ifsk.fltlockuserbuffer
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
req.dll: Fltmgr.sys
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltLockUserBuffer
 - fltkernel/FltLockUserBuffer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltLockUserBuffer
---

# FltLockUserBuffer function


## -description

The <b>FltLockUserBuffer</b> routine locks the user buffer for a given I/O operation.

## -parameters

### -param CallbackData 

[in]
Pointer to the callback data  structure for the I/O operation (<a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>).

## -returns

If the user buffer is successfully locked, <b>FltLockUserBuffer</b> returns STATUS_SUCCESS. (This is the case even if the buffer was already locked by a previous call to <b>FltLockUserBuffer</b>.) Otherwise, it returns an appropriate NTSTATUS value, such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>FltLockUserBuffer</b> encountered a pool allocation failure. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The I/O operation is not one of the operations listed in the following Remarks section. This is an error code. 

</td>
</tr>
</table>

## -remarks

A minifilter driver calls <b>FltLockUserBuffer</b> to lock the user buffer for one of the following I/O operations: 

<ul>
<li>
IRP_MJ_DEVICE_CONTROL

</li>
<li>
IRP_MJ_DIRECTORY_CONTROL

</li>
<li>
IRP_MJ_FILE_SYSTEM_CONTROL

</li>
<li>
IRP_MJ_INTERNAL_DEVICE_CONTROL

</li>
<li>
IRP_MJ_QUERY_EA

</li>
<li>
IRP_MJ_QUERY_QUOTA

</li>
<li>
IRP_MJ_QUERY_SECURITY

</li>
<li>
IRP_MJ_READ

</li>
<li>
IRP_MJ_SET_EA

</li>
<li>
IRP_MJ_SET_QUOTA

</li>
<li>
IRP_MJ_WRITE

</li>
</ul>
<b>FltLockUserBuffer</b> determines the appropriate access method (IoReadAccess, IoWriteAccess, or IoModifyAccess) to apply for the locked buffer based on the type of I/O operation. 

<b>FltLockUserBuffer</b> sets the <b>MdlAddress</b> (or <b>OutputMdlAddress</b>) member  in the callback data parameter structure (<a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_parameters">FLT_PARAMETERS</a>) to point to the MDL for the locked pages. If there is no MDL, <b>FltLockUserBuffer</b> allocates one. 

If the callback data parameter structure contains a system buffer and does not contain a user buffer, <b>FltLockUserBuffer</b> locks the system buffer. If there is no MDL for the system buffer, <b>FltLockUserBuffer</b> allocates one. 

If <b>FltLockUserBuffer</b> is called from a preoperation callback routine (<a href="/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_pre_operation_callback">PFLT_PRE_OPERATION_CALLBACK</a>) and it allocates an MDL, <b>FltLockUserBuffer</b> sets the FLTFL_CALLBACK_DATA_DIRTY flag in the callback data structure (<a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>) so that the I/O system frees the MDL when the I/O operation is completed. 

To conserve system page table entries (PTE), <b>FltLockUserBuffer</b> does not map the locked pages. After calling <b>FltLockUserBuffer</b>, the caller must call <a href="/windows-hardware/drivers/kernel/mm-bad-pointer">MmGetSystemAddressForMdlSafe</a>, passing the <b>MdlAddress</b> (or <b>OutputMdlAddress</b>) member in the callback data parameter structure as the value of the <i>Mdl</i> parameter, to get a system buffer that represents this memory. 

Use of <b>FltLockUserBuffer</b> can slow system performance. This is not because of <b>FltLockUserBuffer</b> itself, but rather because of the performance penalty incurred by <a href="/windows-hardware/drivers/kernel/mm-bad-pointer">MmGetSystemAddressForMdlSafe</a>. 

The caller can be running in any process context. <b>FltLockUserBuffer</b> automatically locks the buffer in the correct process context. 

When the callback data structure is freed, the locked buffer is automatically unlocked, and the MDL is freed. The caller should never free the MDL; the I/O system does this automatically. 

<b>FltLockUserBuffer</b> can be called for fast I/O and IRP-based operations.

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data">FLT_CALLBACK_DATA</a>



<a href="/windows-hardware/drivers/ddi/index">FLT_IS_FASTIO_OPERATION</a>



<a href="/previous-versions/ff544654(v=vs.85)">FLT_IS_IRP_OPERATION</a>



<a href="/previous-versions/ff544663(v=vs.85)">FLT_IS_SYSTEM_BUFFER</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_parameters">FLT_PARAMETERS</a>



<a href="/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-device-control-and-irp-mj-internal-device-co">FLT_PARAMETERS for IRP_MJ_DEVICE_CONTROL and IRP_MJ_INTERNAL_DEVICE_CONTROL</a>



<a href="/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-directory-control">FLT_PARAMETERS for IRP_MJ_DIRECTORY_CONTROL</a>



<a href="/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-file-system-control">FLT_PARAMETERS for IRP_MJ_FILE_SYSTEM_CONTROL</a>



<a href="/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-query-ea">FLT_PARAMETERS for IRP_MJ_QUERY_EA</a>



<a href="/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-query-quota">FLT_PARAMETERS for IRP_MJ_QUERY_QUOTA</a>



<a href="/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-query-security">FLT_PARAMETERS for IRP_MJ_QUERY_SECURITY</a>



<a href="/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-read">FLT_PARAMETERS for IRP_MJ_READ</a>



<a href="/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-set-ea">FLT_PARAMETERS for IRP_MJ_SET_EA</a>



<a href="/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-set-quota">FLT_PARAMETERS for IRP_MJ_SET_QUOTA</a>



<a href="/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-write">FLT_PARAMETERS for IRP_MJ_WRITE</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltdecodeparameters">FltDecodeParameters</a>



<a href="/windows-hardware/drivers/kernel/mm-bad-pointer">MmGetSystemAddressForMdlSafe</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_post_operation_callback">PFLT_POST_OPERATION_CALLBACK</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_pre_operation_callback">PFLT_PRE_OPERATION_CALLBACK</a>