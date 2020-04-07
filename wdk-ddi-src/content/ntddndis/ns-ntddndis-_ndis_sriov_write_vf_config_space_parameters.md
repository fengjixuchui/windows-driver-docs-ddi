---
UID: NS:ntddndis._NDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS
title: _NDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS (ntddndis.h)
description: The NDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS structure specifies the parameters for a write operation on the PCI Express (PCIe) configuration space of a network adapter's Virtual Function (VF).
old-location: netvista\ndis_sriov_write_vf_config_space_parameters.htm
tech.root: netvista
ms.assetid: f5f8959f-edde-4d45-b93c-8f5acb08ec98
ms.date: 05/02/2018
keywords: ["_NDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS structure"]
ms.keywords: "*PNDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS, NDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS, NDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS, PNDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS, netvista.ndis_sriov_write_vf_config_space_parameters, ntddndis/NDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS, ntddndis/PNDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS"
f1_keywords:
 - "ntddndis/NDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS"
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
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
- Ntddndis.h
api_name:
- NDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: NDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS, *PNDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS
---

# _NDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS structure


## -description


The <b>NDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS</b> structure specifies the parameters for a write operation on the PCI Express (PCIe) configuration space  of a network adapter's Virtual Function (VF).


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS</b> structure. This member is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_SRIOV_WRITE_VF_CONFIG_BLOCK_PARAMETERS_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_SRIOV_WRITE_VF_CONFIG_BLOCK_PARAMETERS_REVISION_1.


### -field VFId

An NDIS_SRIOV_FUNCTION_ID value that specifies the unique identifier of the VF on the network adapter.

<div class="alert"><b>Note</b>  The VF with the specified NDIS_SRIOV_FUNCTION_ID value must have resources that were previously allocated through an OID set request of <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-nic-switch-allocate-vf">OID_NIC_SWITCH_ALLOCATE_VF</a>.

</div>
<div> </div>

### -field Offset

A ULONG value that specifies the offset within the PCI configuration space of the VF in which data will be written.


### -field Length

A ULONG value that specifies the length, in units of bytes, of the write operation.


### -field BufferOffset

A ULONG value that specifies the offset, in units of bytes, from the beginning of this structure to a buffer that contains the data to be written to the PCI configuration space of the VF.


## -remarks



 The <b>NDIS_SRIOV_WRITE_VF_CONFIG_SPACE_PARAMETERS</b> structure is used in an OID set request of <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-sriov-write-vf-config-space">OID_SRIOV_WRITE_VF_CONFIG_SPACE</a>.




## -see-also




<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-sriov-write-vf-config-space">OID_SRIOV_WRITE_VF_CONFIG_SPACE</a>
 

 

