---
UID: NF:wudfddi.IWDFDevice.CreateWdfFile
title: IWDFDevice::CreateWdfFile (wudfddi.h)
description: The CreateWdfFile method creates a file object for a driver to use.
old-location: wdf\iwdfdevice_createwdffile.htm
tech.root: wdf
ms.assetid: b356e3ac-451d-4a10-94e2-d03fcf76cb29
ms.date: 02/26/2018
ms.keywords: CreateWdfFile, CreateWdfFile method, CreateWdfFile method,IWDFDevice interface, IWDFDevice interface,CreateWdfFile method, IWDFDevice.CreateWdfFile, IWDFDevice::CreateWdfFile, UMDFDeviceObjectRef_d5f035e1-d7ea-474e-9dc4-bc6b64baea2c.xml, umdf.iwdfdevice_createwdffile, wdf.iwdfdevice_createwdffile, wudfddi/IWDFDevice::CreateWdfFile
ms.topic: method
f1_keywords:
 - "wudfddi/IWDFDevice.CreateWdfFile"
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
- IWDFDevice.CreateWdfFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFDevice::CreateWdfFile


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CreateWdfFile</b> method creates a file object for a driver to use.


## -parameters




### -param pcwszFileName [in, optional]

A pointer to a <b>NULL</b>-terminated string that contains the name of the file to create a file object from. This parameter is optional. The driver can pass <b>NULL</b> if the driver does not have to create the file object from a file name. If the driver must supply a name, the string that the driver passes must not contain any path separator characters ("/" or "\\"). 


### -param ppFile [out]

A pointer to a buffer that receives a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdrivercreatedfile">IWDFDriverCreatedFile</a> interface for the driver-created file object.


## -returns



<b>CreateWdfFile</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.




## -remarks



For information about when a UMDF driver uses <b>CreateWdfFile</b> to handle I/O, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-a-file-object-to-handle-i-o">Creating a File Object to Handle I/O</a>.

For information about when a UMDF driver might use <b>CreateWdfFile</b> to prevent an imbalance of create and close notifications to a driver, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/preventing-an-imbalance-of-create-and-close-notifications-to-a-driver">Preventing an Imbalance of Create and Close Notifications to a Driver</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdevice">IWDFDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdrivercreatedfile">IWDFDriverCreatedFile</a>
 

 

