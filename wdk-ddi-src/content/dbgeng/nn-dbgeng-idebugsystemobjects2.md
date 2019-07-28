---
UID: NN:dbgeng.IDebugSystemObjects2
title: IDebugSystemObjects2 (dbgeng.h)
description: IDebugSystemObjects2 interface
old-location: debugger\idebugsystemobjects2.htm
tech.root: debugger
ms.assetid: 9e354357-590b-45cf-bace-5b431f408422
ms.date: 05/03/2018
ms.keywords: IDebugSystemObjects2, IDebugSystemObjects2 interface [Windows Debugging], IDebugSystemObjects2 interface [Windows Debugging],described, dbgeng/IDebugSystemObjects2, debugger.idebugsystemobjects2
ms.topic: interface
f1_keywords:
 - "dbgeng/IDebugSystemObjects2"
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
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
- IDebugSystemObjects2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSystemObjects2 interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugSystemObjects2</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugsystemobjects">IDebugSystemObjects</a>. <b>IDebugSystemObjects2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugSystemObjects2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsystemobjects4-getcurrentprocessuptime">GetCurrentProcessUpTime</a>
</td>
<td align="left" width="63%">
Returns the length of time the current process has been running.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsystemobjects4-getimplicitprocessdataoffset">GetImplicitProcessDataOffset</a>
</td>
<td align="left" width="63%">
Returns the implicit process for the current target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsystemobjects4-getimplicitthreaddataoffset">GetImplicitThreadDataOffset</a>
</td>
<td align="left" width="63%">
Returns the implicit thread for the current process.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsystemobjects4-setimplicitprocessdataoffset">SetImplicitProcessDataOffset</a>
</td>
<td align="left" width="63%">
Sets the implicit process for the current target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugsystemobjects4-setimplicitthreaddataoffset">SetImplicitThreadDataOffset</a>
</td>
<td align="left" width="63%">
Sets the implicit thread for the current process.

</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugsystemobjects">IDebugSystemObjects</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugsystemobjects3">IDebugSystemObjects3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugsystemobjects4">IDebugSystemObjects4</a>
 

 

