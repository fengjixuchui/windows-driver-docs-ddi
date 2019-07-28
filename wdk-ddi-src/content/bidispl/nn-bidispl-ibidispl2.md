---
UID: NN:bidispl.IBidiSpl2
title: IBidiSpl2 (bidispl.h)
description: The IBidiSpl2 interface enables an application or other objects to send one or more bidi requests using one of the Bidi Request Schemas and receive information formatted as one of the Bidi Response Schemas.
old-location: print\ibidispl2.htm
tech.root: print
ms.assetid: 90e8a390-7d30-4bcf-8c81-438c86529ceb
ms.date: 04/20/2018
ms.keywords: IBidiSpl2, IBidiSpl2 interface [Print Devices], IBidiSpl2 interface [Print Devices],described, _win32_IBidiSpl2, bidispl/IBidiSpl2, gdi.ibidispl2, print.ibidispl2
ms.topic: interface
f1_keywords:
 - "bidispl/IBidiSpl2"
req.header: bidispl.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
req.target-min-winversvr: Windows Server 2008
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
- Bidispl.h
api_name:
- IBidiSpl2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IBidiSpl2 interface


## -description


The <b>IBidiSpl2</b> interface enables an application or other objects to send one or more bidi requests using one of the Bidi Request Schemas and receive information formatted as one of the Bidi Response Schemas. The requests and responses can be either strings or Streams.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IBidiSpl2</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IBidiSpl2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IBidiSpl2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bidispl/nf-bidispl-ibidispl2-binddevice">BindDevice</a>
</td>
<td align="left" width="63%">
Binds a printer to a bidirectional communication request.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bidispl/nf-bidispl-ibidispl2-sendrecvxmlstream">SendRecvXMLStream</a>
</td>
<td align="left" width="63%">
Sends a bidirectional communication request (and receives the response) as   Bidi Request and Response-compliant <a href="https://docs.microsoft.com/windows/desktop/api/objidl/nn-objidl-istream">IStream</a>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bidispl/nf-bidispl-ibidispl2-sendrecvxmlstring">SendRecvXMLString</a>
</td>
<td align="left" width="63%">
Sends a bidirectional communication request (and receives the response) as   Bidi Request and Response-compliant strings.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bidispl/nf-bidispl-ibidispl2-unbinddevice">UnbindDevice</a>
</td>
<td align="left" width="63%">
Releases a printer from a bidirectional communication request.

</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_print/index">Bidirectional Communication Interfaces</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/print/bidirectional-communication-schema">Bidirectional Communication Schema</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/print/print-spooler-components">Print Spooler Components</a>
 

 

