---
UID: NF:wdfmemory.WdfMemoryCopyToBuffer
title: WdfMemoryCopyToBuffer function (wdfmemory.h)
description: The WdfMemoryCopyToBuffer method copies the contents of a specified memory object's buffer into a specified destination buffer.
old-location: wdf\wdfmemorycopytobuffer.htm
tech.root: wdf
ms.assetid: cb1fc590-3d3a-4b06-b467-28c3adb43706
ms.date: 02/26/2018
ms.keywords: DFMemoryObjectRef_8668c3aa-f5f0-4a1a-9290-27cf78fbcd24.xml, WdfMemoryCopyToBuffer, WdfMemoryCopyToBuffer method, kmdf.wdfmemorycopytobuffer, wdf.wdfmemorycopytobuffer, wdfmemory/WdfMemoryCopyToBuffer
ms.topic: function
req.header: wdfmemory.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: BufAfterReqCompletedIntIoctlA, BufAfterReqCompletedIoctlA, BufAfterReqCompletedReadA, BufAfterReqCompletedWriteA, DriverCreate, MemAfterReqCompletedIntIoctlA, MemAfterReqCompletedIoctlA, MemAfterReqCompletedReadA, MemAfterReqCompletedWriteA
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: Any level (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfMemoryCopyToBuffer
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfMemoryCopyToBuffer function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfMemoryCopyToBuffer</b> method copies the contents of a specified memory object's buffer into a specified destination buffer.


## -parameters




### -param SourceMemory [in]

A handle to a framework memory object that represents the source buffer.


### -param SourceOffset [in]

An offset, in bytes, from the beginning of the source buffer. The copy operation begins at the specified offset in the source buffer.


### -param Buffer [out]

A pointer to a destination buffer.


### -param NumBytesToCopyTo [in]

The number of bytes to copy from the source buffer to the destination buffer. This value must not be greater than the size of the source buffer.


## -returns



<b>WdfMemoryCopyToBuffer</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

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
An invalid parameter was detected.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The byte offset that the <i>SourceOffset</i> parameter specified was too large, or the <i>NumBytesToCopyTo</i> parameter was greater than the size of the source buffer.

</td>
</tr>
</table>
 

This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



The framework does not allow the driver to copy more bytes than the source buffer that the <i>SourceMemory</i> parameter specifies can contain. 

For more information about framework memory objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-memory-buffers">Using Memory Buffers</a>.

If the source or destination buffer was allocated from the pageable memory pool, the <b>WdfMemoryCopyToBuffer</b> method must be called at IRQL <= APC_LEVEL. Otherwise, the method can be called at any IRQL.


#### Examples

The following code example allocates a new buffer and copies the contents of a memory object's buffer into the new buffer.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PVOID  pOutputBuffer = NULL;
NTSTATUS  status = STATUS_SUCCESS;

pOutputBuffer = ExAllocatePoolWithTag(
                                      NonPagedPool,
                                      MY_BUFFER_LENGTH,
                                      MY_POOL_TAG
                                      );
if (pOutputBuffer != NULL){
    status = WdfMemoryCopyToBuffer(
                                   outputMemoryHandle,
                                   0,
                                   pOutputBuffer,
                                   MY_BUFFER_LENGTH
                                   );
}
else{
    status = STATUS_INSUFFICIENT_RESOURCES;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfmemory/nf-wdfmemory-wdfmemorycopyfrombuffer">WdfMemoryCopyFromBuffer</a>
 

 

