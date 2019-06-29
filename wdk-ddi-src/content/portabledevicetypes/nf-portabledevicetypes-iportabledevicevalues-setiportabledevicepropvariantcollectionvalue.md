---
UID: NF:portabledevicetypes.IPortableDeviceValues.SetIPortableDevicePropVariantCollectionValue
title: IPortableDeviceValues::SetIPortableDevicePropVariantCollectionValue (portabledevicetypes.h)
description: Adds a new IPortableDevicePropVariantCollection value (type VT_UNKNOWN) or overwrites an existing one.
old-location: wpddk\iportabledevicevalues_setiportabledevicepropvariantcollectionvalue.htm
tech.root: wpd_dk
ms.assetid: b5cf93f3-e648-4b61-8c9a-8e9080acd424
ms.date: 02/15/2018
ms.keywords: IPortableDeviceValues interface,SetIPortableDevicePropVariantCollectionValue method, IPortableDeviceValues.SetIPortableDevicePropVariantCollectionValue, IPortableDeviceValues::SetIPortableDevicePropVariantCollectionValue, IPortableDeviceValuesSetIPortableDevicePropVariantCollectionValue, SetIPortableDevicePropVariantCollectionValue, SetIPortableDevicePropVariantCollectionValue method, SetIPortableDevicePropVariantCollectionValue method,IPortableDeviceValues interface, portabledevicetypes/IPortableDeviceValues::SetIPortableDevicePropVariantCollectionValue, wpddk.iportabledevicevalues_setiportabledevicepropvariantcollectionvalue
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
- IPortableDeviceValues.SetIPortableDevicePropVariantCollectionValue
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IPortableDeviceValues::SetIPortableDevicePropVariantCollectionValue


## -description



Adds a new <b>IPortableDevicePropVariantCollection</b> value (type VT_UNKNOWN) or overwrites an existing one.




## -parameters




### -param key [in]

A <b>REFPROPERTYKEY</b> that specifies the item to create or overwrite.


### -param pValue [in]

Pointer to an <b>IPortableDevicePropVariantCollection</b> interface that specifies the new value. The SDK copies a reference to the submitted interface and calls <b>AddRef</b> on it.


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
</table>
 




## -remarks



If an existing value has the same key that is specified by the <i>key</i> parameter, it overwrites the existing value without any warning. The existing key memory is released appropriately.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portabledevicetypes/nn-portabledevicetypes-iportabledevicevalues">IPortableDeviceValues Interface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portabledevicetypes/nf-portabledevicetypes-iportabledevicevalues-getiportabledevicepropvariantcollectionvalue">IPortableDeviceValues::GetIPortableDevicePropVariantCollectionValue</a>
 

 

