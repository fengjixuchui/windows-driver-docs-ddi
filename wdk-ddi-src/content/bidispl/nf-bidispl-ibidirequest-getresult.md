---
UID: NF:bidispl.IBidiRequest.GetResult
title: IBidiRequest::GetResult (bidispl.h)
description: The GetResult method tells whether the bidi request was successful.
old-location: print\ibidirequest_ibidirequest__getresult.htm
tech.root: print
ms.assetid: d3d37fd2-b3fa-4664-ba4b-c355197d9b40
ms.date: 04/20/2018
ms.keywords: GetResult, GetResult method [Print Devices], GetResult method [Print Devices],IBidiRequest interface, IBidiRequest interface [Print Devices],GetResult method, IBidiRequest.GetResult, IBidiRequest::GetResult, _win32_IBidiRequest_GetResult, bidispl/IBidiRequest::GetResult, gdi.ibidirequest_ibidirequest__getresult, print.ibidirequest_ibidirequest__getresult
ms.topic: method
f1_keywords:
 - "bidispl/IBidiRequest.GetResult"
req.header: bidispl.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP
req.target-min-winversvr: Windows Server 2003
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
req.dll: Bidispl.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- bidispl.dll
api_name:
- IBidiRequest.GetResult
product:
- Windows
targetos: Windows
req.typenames: 
---

# IBidiRequest::GetResult


## -description


The <b>GetResult</b> method tells whether the bidi request was successful.


## -parameters




### -param phr [out]

Pointer to a variable that specifies the status of the bidi request.


## -returns



The method returns one of the following values. For more information about COM error codes, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">Error Handling</a>.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The operation was successfully carried out.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
The interface handle was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_POINTER</b></dt>
</dl>
</td>
<td width="60%">
At least one of the pointer variable parameters did not reference a valid memory location.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>None of the above</b></dt>
</dl>
</td>
<td width="60%">
The <b>HRESULT</b> contains an error code corresponding to the last error.

</td>
</tr>
</table>
 

Note that the return value indicates whether the method was successful. It does not indicate what happened to the bidi request.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_print/index">Bidirectional Communication Interfaces</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/print/bidirectional-communication-schema">Bidirectional Communication Schema</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bidispl/nn-bidispl-ibidirequest">IBidiRequest</a>
 

 

