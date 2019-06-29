---
UID: NF:wdfpdo.WdfPdoRetrieveAddressDescription
title: WdfPdoRetrieveAddressDescription function (wdfpdo.h)
description: The WdfPdoRetrieveAddressDescription method retrieves the address description that is associated with a specified framework device object.
old-location: wdf\wdfpdoretrieveaddressdescription.htm
tech.root: wdf
ms.assetid: b19e6492-af8d-48dc-8d17-81c2d8c25a6a
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectFdoPdoRef_14653cca-1eb9-44c0-bcdd-cbb450617659.xml, WdfPdoRetrieveAddressDescription, WdfPdoRetrieveAddressDescription method, kmdf.wdfpdoretrieveaddressdescription, wdf.wdfpdoretrieveaddressdescription, wdfpdo/WdfPdoRetrieveAddressDescription
ms.topic: function
req.header: wdfpdo.h
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfPdoRetrieveAddressDescription
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfPdoRetrieveAddressDescription function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfPdoRetrieveAddressDescription</b> method retrieves the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dynamic-enumeration">address description</a> that is associated with a specified framework device object.


## -parameters




### -param Device [in]

A handle to a framework device object that represents the device's physical device object (PDO).


### -param AddressDescription [in, out]

A pointer to a caller-allocated buffer that will receive the address description. The address description must contain a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/ns-wdfchildlist-_wdf_child_address_description_header">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a> structure.


## -returns



If the operation succeeds, the function returns STATUS_SUCCESS. Additional return values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>Device</i> handle does not represent a PDO. 


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The <i>Device</i> handle does not represent a device that was <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dynamic-enumeration">dynamically enumerated</a>. 

</td>
</tr>
</table>
 

The method might also return other<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values"> NTSTATUS values</a>.

A system bug check occurs if the driver supplies an invalid object handle.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdf_child_address_description_header_init">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistretrieveaddressdescription">WdfChildListRetrieveAddressDescription</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfpdo/nf-wdfpdo-wdfpdoretrieveidentificationdescription">WdfPdoRetrieveIdentificationDescription</a>
 

 

