---
UID: NS:1394._IRB_REQ_GET_LOCAL_HOST_INFORMATION
title: _IRB_REQ_GET_LOCAL_HOST_INFORMATION (1394.h)
description: This structure contains the fields necessary for the 1394 bus driver to carry out a GetLocalHostInformation request.
old-location: ieee\irb_req_get_local_host_information.htm
tech.root: IEEE
ms.assetid: 172579A1-9B81-42C7-BAC9-C977C69E7E45
ms.date: 02/15/2018
ms.keywords: 1394/IRB_REQ_GET_LOCAL_HOST_INFORMATION, IEEE.irb_req_get_local_host_information, IRB_REQ_GET_LOCAL_HOST_INFORMATION, IRB_REQ_GET_LOCAL_HOST_INFORMATION structure [Buses], _IRB_REQ_GET_LOCAL_HOST_INFORMATION
ms.topic: struct
req.header: 1394.h
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
- HeaderDef
api_location:
- 1394.h
api_name:
- IRB_REQ_GET_LOCAL_HOST_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: IRB_REQ_GET_LOCAL_HOST_INFORMATION
---

# _IRB_REQ_GET_LOCAL_HOST_INFORMATION structure


## -description


This structure contains the fields necessary for the 1394 bus driver to carry out a GetLocalHostInformation request.


## -struct-fields




### -field nLevel

Specifies what level of information is desired from this call. The following flags are provided.

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
 GET_HOST_UNIQUE_ID 

</td>
<td>
Requests the port driver to return the 64-bit unique identifier. 

</td>
</tr>
<tr>
<td>
GET_HOST_CAPABILITIES

</td>
<td>
Requests the port driver to return the host controller's capability flags.

</td>
</tr>
<tr>
<td>
GET_HOST_DDI_VERSION

</td>
<td>
Requests the DDI version of the 1394 bus driver.

</td>
</tr>
<tr>
<td>
GET_POWER_SUPPLIED

</td>
<td>
Requests the port driver to return the power characteristics of the bus.

</td>
</tr>
<tr>
<td>
GET_PHYS_ADDR_ROUTINE

</td>
<td>
Requests the port driver to return the host controller's physical address mapping function. 

</td>
</tr>
<tr>
<td>
GET_HOST_CONFIG_ROM

</td>
<td>
Requests the port driver to return the host controller's configuration ROM.

</td>
</tr>
<tr>
<td>
GET_HOST_CSR_CONTENTS

</td>
<td>
Requests the port driver to return the speed or topology maps from the host controller's CSR. See the IEEE 1394 Specification for a description of CSRs.<div class="alert"><b>Note</b>  In Windows 7, setting <b>nLevel</b> to GET_HOST_CSR_CONTENTS and specifying the SPEED_MAP_LOCATION as <b>CsrBaseAddress</b> is not supported. The speed map is obsolete in the IEEE-1394a specification.</div>
<div> </div>


</td>
</tr>
<tr>
<td>
GET_HOST_DMA_CAPABILITIES

</td>
<td>
Requests the port driver to return the host controller's capability flags and the size of the DMA buffer (PAGESIZE multiplied by the number of mapping registers).

</td>
</tr>
</table>
 


### -field Information

Points to an information block to be filled in, depending on what level of information is desired. Each block has its own particular structure.

<table>
<tr>
<th>Flag</th>
<th>Structure</th>
</tr>
<tr>
<td>
GET_HOST_UNIQUE_ID

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/1394/ns-1394-_get_local_host_info1">GET_LOCAL_HOST_INFO1</a>


</td>
</tr>
<tr>
<td>
GET_HOST_CAPABILITIES

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/1394/ns-1394-_get_local_host_info2">GET_LOCAL_HOST_INFO2</a>


</td>
</tr>
<tr>
<td>
GET_POWER_SUPPLIED

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/1394/ns-1394-_get_local_host_info3">GET_LOCAL_HOST_INFO3</a>


</td>
</tr>
<tr>
<td>
GET_PHYS_ADDR_ROUTINE

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/1394/ns-1394-_get_local_host_info4">GET_LOCAL_HOST_INFO4</a>


</td>
</tr>
<tr>
<td>
GET_HOST_CONFIG_ROM

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/1394/ns-1394-_get_local_host_info5">GET_LOCAL_HOST_INFO5</a>


</td>
</tr>
<tr>
<td>
GET_HOST_CSR_CONTENTS

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/1394/ns-1394-_get_local_host_info6">GET_LOCAL_HOST_INFO6</a>


</td>
</tr>
<tr>
<td>
GET_HOST_DMA_CAPABILITIES

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/1394/ns-1394-_get_local_host_info7_w2k">GET_LOCAL_HOST_INFO7</a>


</td>
</tr>
<tr>
<td>
GET_HOST_DDI_VERSION

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/1394/ns-1394-_get_local_host_info8">GET_LOCAL_HOST_INFO8</a>


</td>
</tr>
</table>
 

