---
UID: NF:dbgeng.IDebugSymbols3.GetModuleByOffset2
title: IDebugSymbols3::GetModuleByOffset2 (dbgeng.h)
description: The GetModuleByOffset2 method searches through the process's modules for one whose memory allocation includes the specified location.
old-location: debugger\getmodulebyoffset2.htm
tech.root: debugger
ms.assetid: 2bb23245-9d5c-4b9d-8f4a-ce5fe552efc2
ms.date: 05/03/2018
ms.keywords: GetModuleByOffset2, GetModuleByOffset2 method [Windows Debugging], GetModuleByOffset2 method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],GetModuleByOffset2 method, IDebugSymbols3.GetModuleByOffset2, IDebugSymbols3::GetModuleByOffset2, IDebugSymbols_0eead97d-6ca0-4682-bc06-71df2cf04c69.xml, dbgeng/IDebugSymbols3::GetModuleByOffset2, debugger.getmodulebyoffset2
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugSymbols3.GetModuleByOffset2"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugSymbols3.GetModuleByOffset2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::GetModuleByOffset2


## -description


The <b>GetModuleByOffset2</b> method searches through the process's <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/modules">modules</a> for one whose memory allocation includes the specified location.


## -parameters




### -param Offset [in]

Specifies a location in the target's virtual address space which is inside the desired module's memory allocation -- for example, the address of a symbol belonging to the module.


### -param StartIndex [in]

Specifies the index to start searching from.


### -param Flags [in]

Specifies a bit-set containing options used when searching for the module with the specified location.  <i>Flags</i> may contain the following bit-flags:

<table>
<tr>
<th>Flag</th>
<th>Effect</th>
</tr>
<tr>
<td>
DEBUG_GETMOD_NO_LOADED_MODULES

</td>
<td>
Do not search the loaded modules.

</td>
</tr>
<tr>
<td>
DEBUG_GETMOD_NO_UNLOADED_MODULES

</td>
<td>
Do not search the unloaded modules.

</td>
</tr>
</table>
 


### -param Index [out, optional]

Receives the index of the module.  If <i>Index</i> is <b>NULL</b>, this information is not returned.


### -param Base [out, optional]

Receives the location in the target's memory address space of the base of the module.  If <i>Base</i> is <b>NULL</b>, this information is not returned.


## -returns



This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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
 




## -remarks



Starting at the specified index, this method returns the first module it finds whose memory allocation address range includes the specified location.  If the target has more than one module whose memory address range includes this location, then subsequent modules can be found by repeated calls to this method with higher values of <i>StartIndex</i>.

For more information about modules, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/modules">Modules</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getmodulebyindex">GetModuleByIndex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsymbols3-getmodulebyoffset">GetModuleByOffset</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugsymbols3">IDebugSymbols3</a>
 

 

