---
UID: NF:portabledevicetypes.IWpdSerializer.GetBufferFromIPortableDeviceValues
title: IWpdSerializer::GetBufferFromIPortableDeviceValues (portabledevicetypes.h)
description: Serializes a submitted IPortableDeviceValues interface to an allocated byte array. The byte array returned is allocated for the caller and should be freed by the caller using CoTaskMemFree.
old-location: wpddk\iwpdserializer_getbufferfromiportabledevicevalues.htm
tech.root: wpd_dk
ms.assetid: 139a3c88-271e-4353-883e-9c582f7cdcd3
ms.date: 02/15/2018
ms.keywords: GetBufferFromIPortableDeviceValues, GetBufferFromIPortableDeviceValues method, GetBufferFromIPortableDeviceValues method,IWpdSerializer interface, IWpdSerializer interface,GetBufferFromIPortableDeviceValues method, IWpdSerializer.GetBufferFromIPortableDeviceValues, IWpdSerializer::GetBufferFromIPortableDeviceValues, IWpdSerializerGetBufferFromIPortableDeviceValues, portabledevicetypes/IWpdSerializer::GetBufferFromIPortableDeviceValues, wpddk.iwpdserializer_getbufferfromiportabledevicevalues
ms.topic: method
req.header: portabledevicetypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
- PortableDeviceTypes.h
api_name:
- IWpdSerializer.GetBufferFromIPortableDeviceValues
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IWpdSerializer::GetBufferFromIPortableDeviceValues


## -description



Serializes a submitted <b>IPortableDeviceValues</b> interface to an allocated byte array. The byte array returned is allocated for the caller and should be freed by the caller using <b>CoTaskMemFree</b>.




## -parameters




### -param pSource [in]

Pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portabledevicetypes/nn-portabledevicetypes-iportabledevicevalues">IPortableDeviceValues</a> interface to serialize.


### -param ppBuffer [out]

Pointer to a <b>BYTE</b>* that contains the serialized data. Windows Portable Devices allocates this memory; the caller must free it by calling <b>CoTaskMemFree</b>.


### -param pdwBufferSize [out]

Pointer to a <b>DWORD</b> that specifies the size of allocated buffer, in bytes.


## -returns



The method returns an <b>HRESULT</b>. Possible values include, but are not limited to, those in the following table.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_POINTER</b></dt>
</dl>
</td>
<td width="60%">
A required pointer argument was <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
There was not enough memory available to create the buffer.

</td>
</tr>
</table>
 




## -remarks



None.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portabledevicetypes/nn-portabledevicetypes-iwpdserializer">IWpdSerializer Interface</a>
 

 

