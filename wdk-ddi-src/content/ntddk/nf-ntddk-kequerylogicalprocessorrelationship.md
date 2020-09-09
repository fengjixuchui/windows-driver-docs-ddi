---
UID: NF:ntddk.KeQueryLogicalProcessorRelationship
title: KeQueryLogicalProcessorRelationship function (ntddk.h)
description: The KeQueryLogicalProcessorRelationship routine gets information about the relationships of one or more processors to the other processors in a multiprocessor system.
old-location: kernel\kequerylogicalprocessorrelationship.htm
tech.root: kernel
ms.assetid: 343d965d-3e85-423e-a46b-894b19d5df4e
ms.date: 04/30/2018
keywords: ["KeQueryLogicalProcessorRelationship function"]
ms.keywords: KeQueryLogicalProcessorRelationship, KeQueryLogicalProcessorRelationship routine [Kernel-Mode Driver Architecture], k105_0db645b1-dfa2-4d90-856f-975997dc09a8.xml, kernel.kequerylogicalprocessorrelationship, wdm/KeQueryLogicalProcessorRelationship
req.header: ntddk.h
req.include-header: Ntddk.h, Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - KeQueryLogicalProcessorRelationship
 - ntddk/KeQueryLogicalProcessorRelationship
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeQueryLogicalProcessorRelationship
---

# KeQueryLogicalProcessorRelationship function (ntddk.h)


## -description

The <b>KeQueryLogicalProcessorRelationship</b> routine gets information about the relationships of one or more processors to the other processors in a multiprocessor system.

## -parameters

### -param ProcessorNumber 

[in, optional]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/miniport/ns-miniport-_processor_number">PROCESSOR_NUMBER</a> structure that identifies the logical processor for which the caller requests relationship information. To request information about <u>all</u> logical processors in the system, set this parameter to <b>NULL</b>.

### -param RelationshipType 

[in]
Specifies the type of relationship information that is requested by the caller. Set this parameter to one of the following <a href="https://go.microsoft.com/fwlink/p/?linkid=155068">LOGICAL_PROCESSOR_RELATIONSHIP</a> enumeration values:

<ul>
<li>
<b>RelationProcessorCore</b>

</li>
<li>
<b>RelationNumaNode</b>

</li>
<li>
<b>RelationCache</b>

</li>
<li>
<b>RelationProcessorPackage</b>

</li>
<li>
<b>RelationGroup</b>

</li>
<li>
<b>RelationAll</b>

</li>
</ul>

### -param Information 

[out, optional]
A pointer to a caller-allocated buffer into which the routine writes an array of one or more <a href="https://go.microsoft.com/fwlink/p/?linkid=155065">SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX</a> structures that contain the information requested by the caller. If the function fails, the contents of this buffer are undefined. Set <i>Information</i> = <b>NULL</b> to obtain the required buffer length before you allocate the buffer. For more information, see the following Remarks section.

### -param Length 

[in, out]
A pointer to a location that contains the size, in bytes, of the buffer that is pointed to by <i>Information</i>. On entry, *<i>Length</i> contains the size of the caller-allocated buffer that is pointed to by <i>Information</i>. During the call, the routine overwrites the value that is pointed to by <i>Length</i> with the buffer size that is required to contain the requested relationship information.

## -returns

<b>KeQueryLogicalProcessorRelationship</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>ProcessorNumber</i> parameter points to a PROCESSOR_NUMBER structure that contains invalid information.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The caller-allocated buffer that is pointed to by the <i>Information</i> parameter is not large enough to contain the requested relationship information.

</td>
</tr>
</table>

## -remarks

To determine the buffer size to allocate, initially call <b>KeQueryLogicalProcessorRelationship</b> with <i>Information</i> = <b>NULL</b> and *<i>Length</i> = 0. In response, the routine writes the required buffer size to *<i>Length</i> and returns STATUS_INFO_LENGTH_MISMATCH. Next, allocate a buffer of the required size and call <b>KeQueryLogicalProcessorRelationship</b> a second time. In this second call, set <i>Information</i> to the buffer address and *<i>Length</i> to the buffer size. If the second call succeeds, the routine writes the requested relationship information to the buffer and returns STATUS_SUCCESS.


#### Examples

The following code example gets processor relationship information for all the logical processors in a multiprocessor system:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>    //
    // Get required buffer size.
    //
    NTSTATUS Status;
    PSYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX Info = NULL;
    ULONG BufferSize = 0;
    Status = KeQueryLogicalProcessorRelationship(NULL, RelationAll, NULL, &BufferSize);

    NT_ASSERT(Status == STATUS_INFO_LENGTH_MISMATCH && BufferSize > 0);

    //
    // Allocate buffer (assume IRQL <= APC_LEVEL).
    //
    Info = ExAllocatePoolWithTag(PagedPool, BufferSize, ' gaT');
    if (Info == NULL)
    {
        Status = STATUS_INSUFFICIENT_RESOURCES;
    }

    //
    // Get processor relationship information.
    //
    if (NT_SUCCESS(Status))
    {
        Status = KeQueryLogicalProcessorRelationship(NULL, RelationAll, Info, &BufferSize);
    }</pre>
</td>
</tr>
</table></span></div>
The NT_ASSERT macro is defined in the Wdm.h header file. The NT_SUCCESS macro is defined in the Ntdef.h header file.

<div class="code"></div>

## -see-also

<a href="https://go.microsoft.com/fwlink/p/?linkid=155068">LOGICAL_PROCESSOR_RELATIONSHIP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/miniport/ns-miniport-_processor_number">PROCESSOR_NUMBER</a>



<a href="https://go.microsoft.com/fwlink/p/?linkid=155065">SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX</a>

