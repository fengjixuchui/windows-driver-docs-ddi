---
UID: NF:wdfcollection.WdfCollectionGetCount
title: WdfCollectionGetCount function (wdfcollection.h)
description: The WdfCollectionGetCount method returns the number of objects that are currently in an object collection.
old-location: wdf\wdfcollectiongetcount.htm
tech.root: wdf
ms.assetid: 95b6e441-f564-4642-8474-8e10e83177b9
ms.date: 02/26/2018
keywords: ["WdfCollectionGetCount function"]
ms.keywords: DFCollectionObjectRef_835a8d24-fd48-4de9-83bc-62a8b5a3a93b.xml, WdfCollectionGetCount, WdfCollectionGetCount method, kmdf.wdfcollectiongetcount, wdf.wdfcollectiongetcount, wdfcollection/WdfCollectionGetCount
f1_keywords:
 - "wdfcollection/WdfCollectionGetCount"
req.header: wdfcollection.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfCollectionGetCount
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfCollectionGetCount function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfCollectionGetCount</b> method returns the number of objects that are currently in an object collection. 


## -parameters




### -param Collection [in]

A handle to a collection object.


## -returns



<b>WdfCollectionGetCount</b> returns the number of objects that are in the collection.

A system bug check occurs if the driver supplies an invalid object handle.




## -remarks



For more information about object collections, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-collections">Framework Object Collections</a>.


#### Examples

The following code example obtains the number of objects in a specified collection and uses the number to examine all objects in the collection.

```cpp
ULONG count;

count = WdfCollectionGetCount(CollectionHandle);
for (i = 0; i < count; i++) {
    ObjectHandle = WdfCollectionGetItem(
                                        CollectionHandle,
                                        i
                                        );
    // 
    // Perform object-specific operations.
    // 
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfcollection/nf-wdfcollection-wdfcollectiongetitem">WdfCollectionGetItem</a>
 

 

