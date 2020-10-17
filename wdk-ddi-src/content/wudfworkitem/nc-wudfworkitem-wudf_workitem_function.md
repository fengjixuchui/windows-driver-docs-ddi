---
UID: NC:wudfworkitem.WUDF_WORKITEM_FUNCTION
title: WUDF_WORKITEM_FUNCTION (wudfworkitem.h)
description: A driver's OnWorkItem event callback function performs the work that is associated with a specified work item.
old-location: wdf\onworkitem.htm
tech.root: wdf
ms.assetid: 4CCA1F5E-C92E-4D8D-A8C0-B8E9A0F29703
ms.date: 02/26/2018
keywords: ["WUDF_WORKITEM_FUNCTION callback function"]
ms.keywords: OnWorkItem, OnWorkItem callback function, PFN_WUDF_WORKITEM, PFN_WUDF_WORKITEM callback function pointer, WUDF_WORKITEM_FUNCTION, WUDF_WORKITEM_FUNCTION callback, umdf.onworkitem, wdf.onworkitem, wudfworkitem/OnWorkItem, wudfworkitem/PFN_WUDF_WORKITEM
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
targetos: Windows
req.typenames: 
f1_keywords:
 - WUDF_WORKITEM_FUNCTION
 - wudfworkitem/WUDF_WORKITEM_FUNCTION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wudfworkitem.h
api_name:
 - WUDF_WORKITEM_FUNCTION
---

# WUDF_WORKITEM_FUNCTION callback function


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver's <i>OnWorkItem</i> event callback function performs the work that is associated with a specified work item.

## -parameters

### -param pWorkItem 

[in]
A pointer to an  <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfworkitem">IWDFWorkItem</a> interface.

## -remarks

To register an <i>OnWorkItem</i> callback function, your driver must place the callback function's address in a <a href="/windows-hardware/drivers/ddi/wudfworkitem/ns-wudfworkitem-_wudf_workitem_config">WUDF_WORKITEM_CONFIG</a> structure before calling <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice3-createworkitem">IWDFDevice3::CreateWorkItem</a>.

Typically, a driver's <i>OnWorkItem</i> callback function performs tasks that are specified by information that the driver stored in the context memory of a work-item object.

The driver must not call <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfobject-deletewdfobject">IWDFObject::DeleteWdfObject</a> from the <i>OnWorkItem</i> callback function.

For more information, see <a href="/windows-hardware/drivers/wdf/using-workitems">Using Work Items</a>.


#### Examples

The function type is declared in <i>Wudfworkitem.h</i>, as follows.


```
typedef
VOID
WUDF_WORKITEM_FUNCTION(
    _In_
    IWDFWorkItem* pWorkItem
    );

typedef WUDF_WORKITEM_FUNCTION *PFN_WUDF_WORKITEM;
```

To define an <i>OnWorkItem</i> callback function that is named <i>MyWorkItem</i>, you must first provide a function declaration that SDV and other verification tools require, as follows:


```
WUDF_WORKITEM_FUNCTION  MyWorkItem;
```

Then, implement your callback function as follows:


```
VOID
  MyWorkItem (
   _In_
    IWDFWorkItem* pWorkItem
    )
  {…}

```


## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice3-createworkitem">IWDFDevice3::CreateWorkItem</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfobject-deletewdfobject">IWDFObject::DeleteWdfObject</a>



<a href="/windows-hardware/drivers/ddi/wudfworkitem/ns-wudfworkitem-_wudf_workitem_config">WUDF_WORKITEM_CONFIG</a>