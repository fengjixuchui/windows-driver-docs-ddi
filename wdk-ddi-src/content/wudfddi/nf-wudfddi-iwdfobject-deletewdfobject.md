---
UID: NF:wudfddi.IWDFObject.DeleteWdfObject
title: IWDFObject::DeleteWdfObject (wudfddi.h)
description: The DeleteWdfObject method deletes a previously created Microsoft Windows Driver Frameworks (WDF) object.
old-location: wdf\iwdfobject_deletewdfobject.htm
tech.root: wdf
ms.assetid: a777b8df-e255-402a-aa55-14e5861b215f
ms.date: 02/26/2018
ms.keywords: DeleteWdfObject, DeleteWdfObject method, DeleteWdfObject method,IWDFObject interface, IWDFObject interface,DeleteWdfObject method, IWDFObject.DeleteWdfObject, IWDFObject::DeleteWdfObject, UMDFBaseObjectRef_e8c4d75a-eed6-4da3-9cce-79d863a01cd6.xml, umdf.iwdfobject_deletewdfobject, wdf.iwdfobject_deletewdfobject, wudfddi/IWDFObject::DeleteWdfObject
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFObject.DeleteWdfObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFObject::DeleteWdfObject


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>DeleteWdfObject</b> method deletes a previously created Microsoft Windows Driver Frameworks (WDF) object.


## -parameters






## -returns



<b>DeleteWdfObject</b> returns S_OK if the operation succeeds. Otherwise, this method returns HRESULT_FROM_WIN32(ERROR_ACCESS_DENIED) or one of the other error codes that are defined in Winerror.h. 




## -remarks



A driver is unable to delete some WDF objects. For example, the driver cannot delete a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-a-framework-device-object">framework device object</a> because the framework owns and controls device objects. For more information about the hierarchy of WDF objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-hierarchy">Framework Object Hierarchy</a>. 

The driver typically deletes only WDF objects that it creates and owns. For more information about deleting framework objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/managing-the-lifetime-of-objects">Managing the Lifetime of Objects</a>. 

However, when a parent object is deleted, all child objects are automatically deleted. For example, if the driver called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfdevice-createioqueue">IWDFDevice::CreateIoQueue</a> to create an I/O queue object, the newly created I/O queue becomes a child of the device object. The I/O queue object is then automatically deleted when the device object is deleted without the driver explicitly calling <b>DeleteWdfObject</b>.


#### Examples

For a code example of how to use the <b>DeleteWdfObject</b> method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfdevice-setpnpstate">IWDFDevice::SetPnpState</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfdevice-createioqueue">IWDFDevice::CreateIoQueue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfobject">IWDFObject</a>
 

 

