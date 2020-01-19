---
UID: NC:wudfworkitem.WUDF_WORKITEM_FUNCTION
title: WUDF_WORKITEM_FUNCTION (wudfworkitem.h)
description: A driver's OnWorkItem event callback function performs the work that is associated with a specified work item.
old-location: wdf\onworkitem.htm
tech.root: wdf
ms.assetid: 4CCA1F5E-C92E-4D8D-A8C0-B8E9A0F29703
ms.date: 02/26/2018
ms.keywords: OnWorkItem, OnWorkItem callback function, PFN_WUDF_WORKITEM, PFN_WUDF_WORKITEM callback function pointer, WUDF_WORKITEM_FUNCTION, WUDF_WORKITEM_FUNCTION callback, umdf.onworkitem, wdf.onworkitem, wudfworkitem/OnWorkItem, wudfworkitem/PFN_WUDF_WORKITEM
ms.topic: callback
f1_keywords:
 - "wudfworkitem/WUDF_WORKITEM_FUNCTION"
req.header: wudfworkitem.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
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
- UserDefined
api_location:
- Wudfworkitem.h
api_name:
- WUDF_WORKITEM_FUNCTION
product:
- Windows
targetos: Windows
req.typenames: 
---

# WUDF_WORKITEM_FUNCTION callback function


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver's <i>OnWorkItem</i> event callback function performs the work that is associated with a specified work item.


## -parameters




### -param *pWorkItem [in]

A pointer to an  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfworkitem">IWDFWorkItem</a> interface.


## -remarks



To register an <i>OnWorkItem</i> callback function, your driver must place the callback function's address in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfworkitem/ns-wudfworkitem-_wudf_workitem_config">WUDF_WORKITEM_CONFIG</a> structure before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice3-createworkitem">IWDFDevice3::CreateWorkItem</a>.

Typically, a driver's <i>OnWorkItem</i> callback function performs tasks that are specified by information that the driver stored in the context memory of a work-item object.

The driver must not call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfobject-deletewdfobject">IWDFObject::DeleteWdfObject</a> from the <i>OnWorkItem</i> callback function.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-workitems">Using Work Items</a>.


#### Examples

The function type is declared in <i>Wudfworkitem.h</i>, as follows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID
WUDF_WORKITEM_FUNCTION(
    _In_
    IWDFWorkItem* pWorkItem
    );

typedef WUDF_WORKITEM_FUNCTION *PFN_WUDF_WORKITEM;</pre>
</td>
</tr>
</table></span></div>
To define an <i>OnWorkItem</i> callback function that is named <i>MyWorkItem</i>, you must first provide a function declaration that SDV and other verification tools require, as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WUDF_WORKITEM_FUNCTION  MyWorkItem;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
  MyWorkItem (
   _In_
    IWDFWorkItem* pWorkItem
    )
  {…}
</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice3-createworkitem">IWDFDevice3::CreateWorkItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfobject-deletewdfobject">IWDFObject::DeleteWdfObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfworkitem/ns-wudfworkitem-_wudf_workitem_config">WUDF_WORKITEM_CONFIG</a>
 

 

