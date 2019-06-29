---
UID: NF:portabledevicetypes.IPortableDeviceValues.GetBoolValue
title: IPortableDeviceValues::GetBoolValue (portabledevicetypes.h)
description: Retrieves a Boolean value (type VT_BOOL) specified by a key.
old-location: wpddk\iportabledevicevalues_getboolvalue.htm
tech.root: wpd_dk
ms.assetid: ff66e4b8-25f9-4c53-8755-46c860ec37d9
ms.date: 02/15/2018
ms.keywords: GetBoolValue, GetBoolValue method, GetBoolValue method,IPortableDeviceValues interface, IPortableDeviceValues interface,GetBoolValue method, IPortableDeviceValues.GetBoolValue, IPortableDeviceValues::GetBoolValue, IPortableDeviceValuesGetBoolValue, portabledevicetypes/IPortableDeviceValues::GetBoolValue, wpddk.iportabledevicevalues_getboolvalue
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
- IPortableDeviceValues.GetBoolValue
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IPortableDeviceValues::GetBoolValue


## -description



Retrieves a <b>Boolean</b> value (type VT_BOOL) specified by a key.




## -parameters




### -param key [in]

A <b>REFPROPERTYKEY</b> key that specifies the item to retrieve.


### -param pValue [out]

Pointer to the retrieved <b>BOOL</b> value.


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
<dt><b>DISP_E_TYPEMISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The property specified by <i>key</i> is not a <b>BOOL</b> type.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_NOT_FOUND)</b></dt>
</dl>
</td>
<td width="60%">
The property specified by <i>key</i> is not in the collection.

</td>
</tr>
</table>
 




## -remarks



None.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portabledevicetypes/nn-portabledevicetypes-iportabledevicevalues">IPortableDeviceValues Interface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portabledevicetypes/nf-portabledevicetypes-iportabledevicevalues-setboolvalue">IPortableDeviceValues::SetBoolValue</a>
 

 

