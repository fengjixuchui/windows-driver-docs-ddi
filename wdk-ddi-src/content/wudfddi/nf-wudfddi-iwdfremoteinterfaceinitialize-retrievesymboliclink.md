---
UID: NF:wudfddi.IWDFRemoteInterfaceInitialize.RetrieveSymbolicLink
title: IWDFRemoteInterfaceInitialize::RetrieveSymbolicLink (wudfddi.h)
description: The RetrieveSymbolicLink method retrieves the symbolic link name that the operating system assigned to a device interface.
old-location: wdf\iwdfremoteinterfaceinitialize_retrievesymboliclink.htm
tech.root: wdf
ms.assetid: e3203542-177c-440a-8d41-4d70d77f804d
ms.date: 02/26/2018
keywords: ["IWDFRemoteInterfaceInitialize::RetrieveSymbolicLink"]
ms.keywords: IWDFRemoteInterfaceInitialize interface,RetrieveSymbolicLink method, IWDFRemoteInterfaceInitialize.RetrieveSymbolicLink, IWDFRemoteInterfaceInitialize::RetrieveSymbolicLink, RetrieveSymbolicLink, RetrieveSymbolicLink method, RetrieveSymbolicLink method,IWDFRemoteInterfaceInitialize interface, UMDFIoTargetObjectRef_e76cdd61-351a-43f9-93a6-6991159e3d53.xml, umdf.iwdfremoteinterfaceinitialize_retrievesymboliclink, wdf.iwdfremoteinterfaceinitialize_retrievesymboliclink, wudfddi/IWDFRemoteInterfaceInitialize::RetrieveSymbolicLink
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
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
 - IWDFRemoteInterfaceInitialize::RetrieveSymbolicLink
 - wudfddi/IWDFRemoteInterfaceInitialize::RetrieveSymbolicLink
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFRemoteInterfaceInitialize.RetrieveSymbolicLink
---

# IWDFRemoteInterfaceInitialize::RetrieveSymbolicLink


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>RetrieveSymbolicLink</b> method retrieves the symbolic link name that the operating system assigned to a <a href="/windows-hardware/drivers/wdf/using-device-interfaces-in-umdf-drivers">device interface</a>.

## -parameters

### -param pSymbolicLink 

[out, optional]
A pointer to a buffer that receives a <b>null</b>-terminated Unicode character string that represents the symbolic link name. Set this pointer to <b>NULL</b> to obtain the required buffer size.

### -param pdwSymbolicLinkLengthInChars 

[in, out]
A pointer to a caller-allocated location. On input, this location must contain the caller-supplied length of the buffer that <i>pSymbolicLink</i> points to. On output, the location receives the length, in characters, of the symbolic link name, including the <b>NULL</b> terminating character.

## -returns

<b>RetrieveSymbolicLink</b> returns S_OK if the operation succeeds. Otherwise the method might return the following value:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOT_SUFFICIENT_BUFFER</b></dt>
</dl>
</td>
<td width="60%">
The buffer that <i>pSymbolicLink</i> points to is too small. In this case, the framework stores the required buffer size in the location that <i>pdwSymbolicLinkLengthInChars</i> points to.

</td>
</tr>
</table>
 

This method might return one of the other values that Winerror.h contains.

## -remarks

The symbolic link name can include an appended backslash (\) character, followed by an instance-specific reference string.

Typically, your driver should call <b>RetrieveSymbolicLink</b> twice, as follows:

<ol>
<li>
Set the <i>pSymbolicLink</i> parameter to <b>NULL</b> and call <b>RetrieveSymbolicLink</b>. The location that <i>pdwSymbolicLinkLengthInChars</i> points to receives the number of characters that the symbolic link name contains.

</li>
<li>
Allocate a buffer that is large enough to receive the symbolic link name.

</li>
<li>
Call <b>RetrieveSymbolicLink</b> again, and set the <i>pSymbolicLink</i> parameter to the address of the buffer that you allocated.

</li>
</ol>
For more information about the <b>RetrieveSymbolicLink</b> method, see <a href="/windows-hardware/drivers/wdf/using-device-interfaces-in-umdf-drivers">Using Device Interfaces in UMDF-based Drivers</a>.


#### Examples

The following code example shows how a driver's <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallbackremoteinterfacenotification-onremoteinterfacearrival">IPnpCallbackRemoteInterfaceNotification::OnRemoteInterfaceArrival</a> callback function can determine the length of device interface's symbolic link name, allocate a buffer for the name, and then retrieve the name.


```
void 
STDMETHODCALLTYPE
CMyDevice::OnRemoteInterfaceArrival(
    __in IWDFRemoteInterfaceInitialize  *FxRemoteInterfaceInit
    )
{
    HRESULT hr;
    INT BufferSize;
    hr= FxRemoteInterfaceInit->RetrieveSymbolicLink(NULL,
                                                    &BufferSize);
    if (FAILED(hr)) goto Error;
    hr = FxDriver->CreateWdfMemory(BufferSize, 
                                   NULL, 
                                   FxRemoteInterface, 
                                   &FxSymLinkBuffer);
    if (FAILED(hr)) goto Error;
    hr= FxRemoteInterfaceInit->RetrieveSymbolicLink(FxSymLinkBuffer->GetDataBuffer(NULL),
                                                    &BufferSize);
    if (FAILED(hr)) goto Error;
...
Error:
...
}
```


## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfremoteinterfaceinitialize">IWDFRemoteInterfaceInitialize</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfremoteinterfaceinitialize-getinterfaceguid">IWDFRemoteInterfaceInitialize::GetInterfaceGuid</a>