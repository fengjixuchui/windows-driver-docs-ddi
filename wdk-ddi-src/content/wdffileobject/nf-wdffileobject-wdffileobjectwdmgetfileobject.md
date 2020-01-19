---
UID: NF:wdffileobject.WdfFileObjectWdmGetFileObject
title: WdfFileObjectWdmGetFileObject function (wdffileobject.h)
description: The WdfFileObjectWdmGetFileObject method returns the Windows Driver Model (WDM) file object that is associated with a specified framework file object.
old-location: wdf\wdffileobjectwdmgetfileobject.htm
tech.root: wdf
ms.assetid: f3cc9b23-6140-4cb2-959d-c76f23c697ea
ms.date: 02/26/2018
ms.keywords: DFFileObjectRef_1631ea08-9156-4de4-85e6-9368b89ae0f4.xml, WdfFileObjectWdmGetFileObject, WdfFileObjectWdmGetFileObject method, kmdf.wdffileobjectwdmgetfileobject, wdf.wdffileobjectwdmgetfileobject, wdffileobject/WdfFileObjectWdmGetFileObject
ms.topic: function
f1_keywords:
 - "wdffileobject/WdfFileObjectWdmGetFileObject"
req.header: wdffileobject.h
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfFileObjectWdmGetFileObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfFileObjectWdmGetFileObject function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfFileObjectWdmGetFileObject</b> method returns the Windows Driver Model (WDM) file object that is associated with a specified framework file object.


## -parameters




### -param FileObject [in]

A handle to a framework file object.


## -returns



<b>WdfFileObjectWdmGetFileObject</b> returns a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">FILE_OBJECT</a> structure that is associated with the specified framework file object, or <b>NULL</b> if there is no WDM file object for the specified framework file object.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



The pointer that the <b>WdfFileObjectWdmGetFileObject</b> method returns is valid until the framework file object is deleted. If the driver provides an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup">EvtCleanupCallback</a> function for the framework file object, the pointer is valid until the callback function returns.

For more information about framework file objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-file-objects">Framework File Objects</a>.


#### Examples

The following code example obtains a handle to the WDM file object that is associated with a specified framework file object.

```cpp
PFILE_OBJECT  pReturnedFileObject;

pReturnedFileObject = WdfFileObjectWdmGetFileObject(fileObject);
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">FILE_OBJECT</a>
 

 

