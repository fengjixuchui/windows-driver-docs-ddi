---
UID: NF:dbgeng.IDebugRegisters2.GetInstructionOffset2
title: IDebugRegisters2::GetInstructionOffset2 (dbgeng.h)
description: The GetInstructionOffset2 method returns the location of the current thread's current instruction.
old-location: debugger\getinstructionoffset2.htm
tech.root: debugger
ms.assetid: c5757dbb-16bf-46f9-836f-5a94089bbb1e
ms.date: 05/03/2018
keywords: ["IDebugRegisters2::GetInstructionOffset2"]
ms.keywords: GetInstructionOffset2, GetInstructionOffset2 method [Windows Debugging], GetInstructionOffset2 method [Windows Debugging],IDebugRegisters2 interface, IDebugRegisters2 interface [Windows Debugging],GetInstructionOffset2 method, IDebugRegisters2.GetInstructionOffset2, IDebugRegisters2::GetInstructionOffset2, IDebugRegisters_92189e99-c8f6-4422-8421-62fe194a05b6.xml, dbgeng/IDebugRegisters2::GetInstructionOffset2, debugger.getinstructionoffset2
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
 - IDebugRegisters2::GetInstructionOffset2
 - dbgeng/IDebugRegisters2::GetInstructionOffset2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugRegisters2.GetInstructionOffset2
---

# IDebugRegisters2::GetInstructionOffset2


## -description

The <b>GetInstructionOffset2</b> method returns the location of the current thread's current instruction.

## -parameters

### -param Source 

[in]
Specifies the register source to query.

The possible values are listed in the following table.

<table>
<tr>
<th>Value</th>
<th>Register source</th>
</tr>
<tr>
<td>
DEBUG_REGSRC_DEBUGGEE

</td>
<td>
Fetch register information from the target.

</td>
</tr>
<tr>
<td>
DEBUG_REGSRC_EXPLICIT

</td>
<td>
Fetch register information from the current explicit <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/changing-contexts">register context</a>.

</td>
</tr>
<tr>
<td>
DEBUG_REGSRC_FRAME

</td>
<td>
Fetch register information from the current scope's register context.

<div class="alert"><b>Note</b>    Stack unwinding does not guarantee accurate updating of the register context, so the scope frame's register context might not be accurate in all cases.</div>
<div> </div>
</td>
</tr>
</table>

### -param Offset 

[out]
Receives the location in the process's virtual address space of the current instruction of the current thread.

## -returns

This list does not contain all the errors that might occur.  For a list of possible errors, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">HRESULT Values</a>.

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

The meaning of the value that is returned by this method is architecture-dependent.  In particular, for an Itanium-based processor, the virtual address that is returned can indicate an address within a bundle.

The method <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugregisters2-getinstructionoffset">GetInstructionOffset</a> performs the same task as this method but always uses the target as the register source.

For an overview of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugregisters">IDebugRegisters</a> interface and other register-related methods, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/registers">Registers</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugregisters2-getinstructionoffset">GetInstructionOffset</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugregisters2">IDebugRegisters2</a>

