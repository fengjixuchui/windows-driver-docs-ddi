---
UID: NF:dbgeng.IDebugControl4.AddExtensionWide
title: IDebugControl4::AddExtensionWide (dbgeng.h)
description: The AddExtensionWide method loads an extension library into the debugger engine.
old-location: debugger\addextensionwide.htm
tech.root: debugger
ms.assetid: 5c918f44-1ee7-4666-b83a-e13ce02e26db
ms.date: 05/03/2018
keywords: ["IDebugControl4::AddExtensionWide"]
ms.keywords: AddExtensionWide, AddExtensionWide method [Windows Debugging], AddExtensionWide method [Windows Debugging],IDebugControl4 interface, IDebugControl4 interface [Windows Debugging],AddExtensionWide method, IDebugControl4.AddExtensionWide, IDebugControl4::AddExtensionWide, dbgeng/IDebugControl4::AddExtensionWide, debugger.addextensionwide
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
 - IDebugControl4::AddExtensionWide
 - dbgeng/IDebugControl4::AddExtensionWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Dbgeng.h
api_name:
 - IDebugControl4.AddExtensionWide
---

# IDebugControl4::AddExtensionWide


## -description

The <b>AddExtensionWide</b>  method loads an extension library into the <a href="/windows-hardware/drivers/debugger/introduction">debugger engine</a>.

## -parameters

### -param Path 

[in]
Specifies the fully qualified path and file name of the extension library to load.

### -param Flags 

[in]
Set to zero.

### -param Handle 

[out]
Receives the handle of the loaded extension library.

## -returns

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
</table>
 

This method can also return error values.  See <a href="/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

## -remarks

If the extension library has already been loaded, the handle to already loaded library is returned.  The extension library is not loaded again.

The extension library is loaded into the host engine and <i>Path</i> contains a path and file name for this instance of the debugger engine.

For more information on using extension libraries, see <a href="/windows-hardware/drivers/debugger/calling-extensions-and-extension-functions">Calling Extensions and Extension Functions</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-getextensionbypath">GetExtensionByPath</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugcontrol4">IDebugControl4</a>



<a href="/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugcontrol3-removeextension">RemoveExtension</a>