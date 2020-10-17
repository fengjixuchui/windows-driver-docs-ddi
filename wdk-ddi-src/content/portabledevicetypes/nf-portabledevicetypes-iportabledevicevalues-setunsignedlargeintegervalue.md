---
UID: NF:portabledevicetypes.IPortableDeviceValues.SetUnsignedLargeIntegerValue
title: IPortableDeviceValues::SetUnsignedLargeIntegerValue (portabledevicetypes.h)
description: Adds a new ULONGLONG value (type VT_UI8) or overwrites an existing one.
old-location: wpddk\iportabledevicevalues_setunsignedlargeintegervalue.htm
tech.root: wpd_dk
ms.assetid: 717d1ea8-3315-4fa4-b066-c1529f57090f
ms.date: 02/15/2018
keywords: ["IPortableDeviceValues::SetUnsignedLargeIntegerValue"]
ms.keywords: IPortableDeviceValues interface,SetUnsignedLargeIntegerValue method, IPortableDeviceValues.SetUnsignedLargeIntegerValue, IPortableDeviceValues::SetUnsignedLargeIntegerValue, IPortableDeviceValuesSetUnsignedLargeIntegerValue, SetUnsignedLargeIntegerValue, SetUnsignedLargeIntegerValue method, SetUnsignedLargeIntegerValue method,IPortableDeviceValues interface, portabledevicetypes/IPortableDeviceValues::SetUnsignedLargeIntegerValue, wpddk.iportabledevicevalues_setunsignedlargeintegervalue
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
targetos: Windows
req.typenames: 
ms.custom: RS5
f1_keywords:
 - IPortableDeviceValues::SetUnsignedLargeIntegerValue
 - portabledevicetypes/IPortableDeviceValues::SetUnsignedLargeIntegerValue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - PortableDeviceTypes.h
api_name:
 - IPortableDeviceValues.SetUnsignedLargeIntegerValue
---

# IPortableDeviceValues::SetUnsignedLargeIntegerValue


## -description

Adds a new <b>ULONGLONG</b> value (type VT_UI8) or overwrites an existing one.

## -parameters

### -param key 

[in]
A <b>REFPROPERTYKEY</b> that specifies the item to create or overwrite.

### -param Value 

[in]
A <b>ULONGLONG</b> that specifies the new value.

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

None.

## -see-also

<a href="/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicevalues">IPortableDeviceValues Interface</a>



<a href="/windows-hardware/drivers/ddi/portabledevicetypes/nf-portabledevicetypes-iportabledevicevalues-getunsignedlargeintegervalue">IPortableDeviceValues::GetUnsignedLargeIntegerValue</a>