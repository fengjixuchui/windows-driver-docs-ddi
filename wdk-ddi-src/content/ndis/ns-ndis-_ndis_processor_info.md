---
UID: NS:ndis._NDIS_PROCESSOR_INFO
title: _NDIS_PROCESSOR_INFO (ndis.h)
description: The NDIS_PROCESSOR_INFO structure specifies information about a processor in the local computer.
old-location: netvista\ndis_processor_info.htm
tech.root: netvista
ms.assetid: 55c7044e-20db-4245-a644-93cbeb9cd512
ms.date: 05/02/2018
keywords: ["NDIS_PROCESSOR_INFO structure"]
ms.keywords: "*PNDIS_PROCESSOR_INFO, NDIS_PROCESSOR_INFO, NDIS_PROCESSOR_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_PROCESSOR_INFO, PNDIS_PROCESSOR_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PROCESSOR_INFO, ndis/NDIS_PROCESSOR_INFO, ndis/PNDIS_PROCESSOR_INFO, ndis_sysinfo_ref_87f00f3b-dc88-4f7d-be9e-39a649aa87a6.xml, netvista.ndis_processor_info"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and 6.1. For NDIS 6.20 and later, use NDIS_PROCESSOR_INFO_EX.
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
req.typenames: NDIS_PROCESSOR_INFO, *PNDIS_PROCESSOR_INFO
f1_keywords:
 - _NDIS_PROCESSOR_INFO
 - ndis/_NDIS_PROCESSOR_INFO
 - PNDIS_PROCESSOR_INFO
 - ndis/PNDIS_PROCESSOR_INFO
 - NDIS_PROCESSOR_INFO
 - ndis/NDIS_PROCESSOR_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NDIS_PROCESSOR_INFO
---

# _NDIS_PROCESSOR_INFO structure


## -description

The <b>NDIS_PROCESSOR_INFO</b> structure specifies information about a processor in the local
  computer.

## -struct-fields

### -field CpuNumber

The CPU number that is assigned to the processor. The value is in the range from zero through the
     number of active CPUs minus one.

### -field PhysicalPackageId

The physical package ID of the processor. The value is in the range from zero through the number
     in the 
     <b>NumPhysicalPackages</b> member of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_system_processor_info">
     NDIS_SYSTEM_PROCESSOR_INFO</a> structure minus one.

### -field CoreId

The core ID of the processor. The value is in the range from zero through the number in the 
     <b>NumCoresPerPhysicalPackage</b> member of the NDIS_SYSTEM_PROCESSOR_INFO structure minus one.

### -field HyperThreadID

The hyper-threading ID of the processor. The value is in the range from zero through the number in
     the 
     <b>MaxHyperThreadingCpusPerCore</b> member of the NDIS_SYSTEM_PROCESSOR_INFO structure minus one.

## -remarks

The NDIS_PROCESSOR_INFO structure is used in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_system_processor_info">
    NDIS_SYSTEM_PROCESSOR_INFO</a> structure.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_processor_info_ex">NDIS_PROCESSOR_INFO_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_system_processor_info">NDIS_SYSTEM_PROCESSOR_INFO</a>

