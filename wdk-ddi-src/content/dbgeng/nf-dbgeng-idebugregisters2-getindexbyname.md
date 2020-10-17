---
UID: NF:dbgeng.IDebugRegisters2.GetIndexByName
title: IDebugRegisters2::GetIndexByName (dbgeng.h)
description: The GetIndexByName method returns the index of the named register.
old-location: debugger\getindexbyname.htm
tech.root: debugger
ms.assetid: a012b235-ed50-4009-a7ee-01783f9e3597
ms.date: 05/03/2018
keywords: ["IDebugRegisters2::GetIndexByName"]
ms.keywords: GetIndexByName, GetIndexByName method [Windows Debugging], GetIndexByName method [Windows Debugging],IDebugRegisters interface, GetIndexByName method [Windows Debugging],IDebugRegisters2 interface, IDebugRegisters interface [Windows Debugging],GetIndexByName method, IDebugRegisters2 interface [Windows Debugging],GetIndexByName method, IDebugRegisters2.GetIndexByName, IDebugRegisters2::GetIndexByName, IDebugRegisters::GetIndexByName, IDebugRegisters_5b85eaa4-3c90-47e0-9f7f-7f493617fa37.xml, dbgeng/IDebugRegisters2::GetIndexByName, dbgeng/IDebugRegisters::GetIndexByName, debugger.getindexbyname
req.header: dbgeng.h
req.include-header: DbgEng.h
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
 - IDebugRegisters2::GetIndexByName
 - dbgeng/IDebugRegisters2::GetIndexByName
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugRegisters.GetIndexByName
 - IDebugRegisters2.GetIndexByName
---

# IDebugRegisters2::GetIndexByName


## -description

The <b>GetIndexByName</b> method returns the index of the named register.

## -parameters

### -param Name 

[in]
Specifies the name of the register whose index is requested.

### -param Index 

[out]
Receives the index of the register.

## -returns

This list does not contain all the errors that might occur.  For a list of possible errors, see <a href="/windows-hardware/drivers/debugger/hresult-values">HRESULT Values</a>.

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
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
The register was not found.

</td>
</tr>
</table>

## -remarks

For an overview of the <a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugregisters">IDebugRegisters</a> interface and other register-related methods, see <a href="/windows-hardware/drivers/debugger/registers">Registers</a>.