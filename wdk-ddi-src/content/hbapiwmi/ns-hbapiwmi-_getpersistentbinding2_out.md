---
UID: NS:hbapiwmi._GetPersistentBinding2_OUT
title: _GetPersistentBinding2_OUT (hbapiwmi.h)
description: The GetBindingSupport_OUT structure is used to report the output parameter data of the GetPersistentBinding2 WMI method to the WMI client.
old-location: storage\getpersistentbinding2_out.htm
tech.root: storage
ms.assetid: 883a7a56-ecb9-428f-a15a-ba428a626bed
ms.date: 03/29/2018
keywords: ["_GetPersistentBinding2_OUT structure"]
ms.keywords: "*PGetPersistentBinding2_OUT, GetPersistentBinding2_OUT, GetPersistentBinding2_OUT structure [Storage Devices], PGetPersistentBinding2_OUT, PGetPersistentBinding2_OUT structure pointer [Storage Devices], _GetPersistentBinding2_OUT, hbapiwmi/GetPersistentBinding2_OUT, hbapiwmi/PGetPersistentBinding2_OUT, storage.getpersistentbinding2_out, structs-Fibre_e6ffe5e2-f1e2-4b40-836c-954eb31301de.xml"
f1_keywords:
 - "hbapiwmi/GetPersistentBinding2_OUT"
 - "GetPersistentBinding2_OUT"
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
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
- hbapiwmi.h
api_name:
- GetPersistentBinding2_OUT
targetos: Windows
req.typenames: GetPersistentBinding2_OUT, *PGetPersistentBinding2_OUT
---

# _GetPersistentBinding2_OUT structure


## -description


The GetBindingSupport_OUT structure is used to report the output parameter data of the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/getpersistentbinding2">GetPersistentBinding2</a> WMI method to the WMI client.


## -struct-fields




### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a>. 


### -field TotalEntryCount

Indicates the number of binding entries that the WMI provider can report.


### -field OutEntryCount

Indicates the total number of persistent bindings retrieved by the GetPersistentBinding2 method.


### -field Bindings

Contains an array of structures of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hbapiwmi/ns-hbapiwmi-_hbafcpbindingentry2">HBAFCPBindingEntry2</a> that describe an HBA's bindings between operating system and fibre channel protocol (FCP) identifiers.


## -remarks



The WMI tool suite generates a declaration of the GetPersistentBinding2_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msfc-hbafcpinfo-wmi-class">MSFC_HBAFCPInfo WMI Class</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/getpersistentbinding2">GetPersistentBinding2</a>
 

 

