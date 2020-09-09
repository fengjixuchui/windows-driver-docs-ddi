---
UID: NF:extsfns.IDebugFailureAnalysis2.SetBuffer
title: IDebugFailureAnalysis2::SetBuffer (extsfns.h)
description: The SetBuffer method searches a DebugFailureAnalysis object for the first FA entry that has a specified tag. If it finds an FA entry with the specified tag, it overwrites the data block of the FA entry with the bytes in a specified buffer.
old-location: debugger\idebugfailureanalysis2_setbuffer.htm
tech.root: debugger
ms.assetid: 366EE066-AD47-4A75-87B4-17279C66C741
ms.date: 05/03/2018
keywords: ["IDebugFailureAnalysis2::SetBuffer"]
ms.keywords: IDebugFailureAnalysis2 interface [Windows Debugging],SetBuffer method, IDebugFailureAnalysis2.SetBuffer, IDebugFailureAnalysis2::SetBuffer, SetBuffer, SetBuffer method [Windows Debugging], SetBuffer method [Windows Debugging],IDebugFailureAnalysis2 interface, debugger.idebugfailureanalysis2_setbuffer, extsfns/IDebugFailureAnalysis2::SetBuffer
req.header: extsfns.h
req.include-header: 
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
 - IDebugFailureAnalysis2::SetBuffer
 - extsfns/IDebugFailureAnalysis2::SetBuffer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - extsfns.h
api_name:
 - IDebugFailureAnalysis2.SetBuffer
---

# IDebugFailureAnalysis2::SetBuffer


## -description

The <b>SetBuffer</b> method searches a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">DebugFailureAnalysis</a> object for the first <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a> that has a specified tag. If it finds an FA entry with the specified tag, it overwrites the data block of the FA entry with the bytes in a specified buffer. If this method does not find an <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a> that has the specified tag, it creates a new FA entry with that tag and overwrites the data block of the new FA entry with the data in the specified buffer.

## -parameters

### -param Tag

A value in the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration.

### -param EntryType 

[in]
A value in the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_ENTRY_TYPE</a> enumeration. This parameter specifies the data type of the data in <i>Buf</i>.

### -param Buf 

[in]
A pointer to a buffer that contains the bytes to be written to the data block of the new or existing <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a>.

### -param Size 

[in]
The size, in bytes, of the buffer pointed to by <i>Buf</i>.

## -returns

If this method succeeds, it returns a pointer to the new or existing <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/ns-extsfns-_fa_entry">FA_ENTRY</a> structure. Otherwise, it returns <b>NULL</b>.

## -remarks

If this method finds an <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a> with the specified tag, it checks to see whether the data type associated with that tag is compatible with the data type specified by <i>EntryType</i>. For example, <b>DEBUG_FA_ENTRY_ULONG64</b>, <b>DEBUG_FA_ENTRY_INSTRUCTION_OFFSET</b>, and <b>DEBUG_FA_ENTRY_POINTER</b> are all compatible with each other. Likewise, <b>DEBUG_FA_ENTRY_ANSI_STRING</b> and <b>DEBUG_FA_ENTRY_EXTENSION_CMD</b> are compatible with each other. If the data types are not compatible, this method returns <b>NULL</b> and does not overwrite the entry's data block.

If this method does not find an <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/failure-analysis-entries">FA entry</a> with the specified tag, it creates a new FA entry with that tag, and it associates the tag with the data type specified by <i>EntryType</i>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfailureanalysis2-addbuffer">AddBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nf-extsfns-idebugfailureanalysis2-getbuffer">GetBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nn-extsfns-idebugfailureanalysis2">IDebugFailureAnalysis2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nc-extsfns-ext_analysis_plugin">_EFN_Analyze</a>

