---
UID: NF:dbgeng.IDebugControl3.GetEventIndexDescription
title: IDebugControl3::GetEventIndexDescription (dbgeng.h)
description: The GetEventIndexDescription method describes the specified event in a static list of events for the current target.
old-location: debugger\geteventindexdescription.htm
tech.root: debugger
ms.assetid: 75aace9d-3f1e-4002-82e6-d581903da4f9
ms.date: 05/03/2018
ms.keywords: GetEventIndexDescription, GetEventIndexDescription method [Windows Debugging], GetEventIndexDescription method [Windows Debugging],IDebugControl3 interface, IDebugControl3 interface [Windows Debugging],GetEventIndexDescription method, IDebugControl3.GetEventIndexDescription, IDebugControl3::GetEventIndexDescription, IDebugControl_53afcbab-2b43-4b99-9b87-050fce6d495b.xml, dbgeng/IDebugControl3::GetEventIndexDescription, debugger.geteventindexdescription
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugControl3.GetEventIndexDescription"
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
- IDebugControl3.GetEventIndexDescription
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl3::GetEventIndexDescription


## -description


The <b>GetEventIndexDescription</b>  method describes the specified event in a static list of events for the current target.


## -parameters




### -param Index [in]

Specifies the index of the event whose description will be returned.


### -param Which [in]

Specifies which piece of the event description to return.  Currently only DEBUG_EINDEX_NAME is supported; this returns the name of the event.


### -param Buffer [in, optional]

Receives the description of the event.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize [in]

Specifies the size, in characters, of the <i>Buffer </i>buffer.


### -param DescSize [out, optional]

Receives the size, in characters, of the description.  If <i>DescSize</i> is <b>NULL</b>, this information is not returned.


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



The amount of descriptive information available for a particular target varies depending on the type of the target.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getcurrenteventindex">GetCurrentEventIndex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getnumberevents">GetNumberEvents</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>
 

 

