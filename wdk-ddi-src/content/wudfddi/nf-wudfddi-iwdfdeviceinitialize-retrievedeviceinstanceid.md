---
UID: NF:wudfddi.IWDFDeviceInitialize.RetrieveDeviceInstanceId
title: IWDFDeviceInitialize::RetrieveDeviceInstanceId (wudfddi.h)
description: The RetrieveDeviceInstanceId method retrieves the identifier of an instance of a device.
old-location: wdf\iwdfdeviceinitialize_retrievedeviceinstanceid.htm
tech.root: wdf
ms.assetid: 5f1651f9-4952-4e87-90fc-3f79948b8457
ms.date: 02/26/2018
keywords: ["IWDFDeviceInitialize::RetrieveDeviceInstanceId"]
ms.keywords: IWDFDeviceInitialize interface,RetrieveDeviceInstanceId method, IWDFDeviceInitialize.RetrieveDeviceInstanceId, IWDFDeviceInitialize::RetrieveDeviceInstanceId, RetrieveDeviceInstanceId, RetrieveDeviceInstanceId method, RetrieveDeviceInstanceId method,IWDFDeviceInitialize interface, UMDFDeviceObjectRef_b383227b-ba03-4c85-9517-bb87eac631ef.xml, umdf.iwdfdeviceinitialize_retrievedeviceinstanceid, wdf.iwdfdeviceinitialize_retrievedeviceinstanceid, wudfddi/IWDFDeviceInitialize::RetrieveDeviceInstanceId
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFDeviceInitialize::RetrieveDeviceInstanceId
 - wudfddi/IWDFDeviceInitialize::RetrieveDeviceInstanceId
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFDeviceInitialize.RetrieveDeviceInstanceId
---

# IWDFDeviceInitialize::RetrieveDeviceInstanceId


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-retrievedeviceinstanceid">RetrieveDeviceInstanceId</a> method retrieves the identifier of an instance of a device.

## -parameters

### -param Buffer 

[out, optional]
A pointer to a buffer that receives a <b>NULL</b>-terminated string that represents the identifier of an instance of a device if the supplied buffer is non-<b>NULL</b> and <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-retrievedeviceinstanceid">RetrieveDeviceInstanceId</a> is successful.

### -param pdwSizeInChars 

[in, out]
A pointer to a variable that receives the number of characters, including the <b>NULL</b> character, in the string that <i>Buffer</i> points to.

If <i>Buffer</i> is <b>NULL</b>, the value that the driver supplies is zero. The framework then returns the size, in characters, that is required for the identifier string.

If <i>Buffer</i> is non-<b>NULL</b>, the framework returns the size, in characters, of the identifier string.

## -returns

<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-retrievedeviceinstanceid">RetrieveDeviceInstanceId</a> returns S_OK for the following scenarios: 


<ul>
<li>
The buffer that the <i>Buffer</i> parameter pointed to was non-<b>NULL</b> and large enough to hold the identifier string, including the <b>NULL</b> character, and the framework successfully copied the string into the supplied buffer and set the variable that was pointed to by the <i>pdwSizeInChars</i> parameter to the number of characters in the string.

</li>
<li>
The buffer at <i>Buffer</i> was <b>NULL</b>, the driver preset the variable at <i>pdwSizeInChars</i> to 0, and the framework set the variable at <i>pdwSizeInChars</i> to the number of characters that are required for the string.

</li>
</ul>
<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-retrievedeviceinstanceid">RetrieveDeviceInstanceId</a> returns HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER) to indicate that the supplied buffer is non-<b>NULL</b> and does not contain enough space to hold the identifier string. The framework sets the variable at <i>pdwSizeInChars</i> to the number of characters that are required for the string.




<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-retrievedeviceinstanceid">RetrieveDeviceInstanceId</a> might also return other HRESULT values.

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdeviceinitialize">IWDFDeviceInitialize</a>