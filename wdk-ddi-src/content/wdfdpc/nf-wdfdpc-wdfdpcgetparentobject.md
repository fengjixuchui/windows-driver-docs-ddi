---
UID: NF:wdfdpc.WdfDpcGetParentObject
title: WdfDpcGetParentObject function (wdfdpc.h)
description: The WdfDpcGetParentObject method returns the parent object of a specified DPC object.
old-location: wdf\wdfdpcgetparentobject.htm
tech.root: wdf
ms.assetid: 77ebca0f-3056-4f11-9d59-fbd166967ed3
ms.date: 02/26/2018
keywords: ["WdfDpcGetParentObject function"]
ms.keywords: DFDpcObjectRef_28be5a7f-4f65-4b9e-b9f4-80b754cc8ca3.xml, WdfDpcGetParentObject, WdfDpcGetParentObject method, kmdf.wdfdpcgetparentobject, wdf.wdfdpcgetparentobject, wdfdpc/WdfDpcGetParentObject
f1_keywords:
 - "wdfdpc/WdfDpcGetParentObject"
req.header: wdfdpc.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfDpcGetParentObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDpcGetParentObject function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDpcGetParentObject</b> method returns the parent object of a specified DPC object.


## -parameters




### -param Dpc [in]

A handle to a framework DPC object.


## -returns



<b>WdfDpcGetParentObject</b> returns a handle to the parent object of a specified DPC object.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



A driver might call <b>WdfDpcGetParentObject</b> from within its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/nc-wdfdpc-evt_wdf_dpc">EvtDpcFunc</a> callback function.


#### Examples

The following code example returns a handle to the parent object of a specified DPC object. The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/nf-wdfdpc-wdfdpccreate">WdfDpcCreate</a> code example shows how the specified DPC object was created.

```cpp
WDFDEVICE Device;

Device = WdfDpcGetParentObject(PDevExt->CompleteWriteDpc);
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/nc-wdfdpc-evt_wdf_dpc">EvtDpcFunc</a>
 

 

