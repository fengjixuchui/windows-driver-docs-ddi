---
UID: NS:hbapiwmi._GetFCPStatistics_OUT
title: _GetFCPStatistics_OUT (hbapiwmi.h)
description: The GetFCPStatistics_OUT structure is used by the miniport driver to report the output parameters of the GetFCPStatistics WMI method.
old-location: storage\getfcpstatistics_out.htm
tech.root: storage
ms.assetid: 150773a3-a3a9-41a7-9985-4387bba5a766
ms.date: 03/29/2018
ms.keywords: "*PGetFCPStatistics_OUT, GetFCPStatistics_OUT, GetFCPStatistics_OUT structure [Storage Devices], PGetFCPStatistics_OUT, PGetFCPStatistics_OUT structure pointer [Storage Devices], _GetFCPStatistics_OUT, hbapiwmi/GetFCPStatistics_OUT, hbapiwmi/PGetFCPStatistics_OUT, storage.getfcpstatistics_out, structs-Fibre_cb7a0157-9213-4c4f-adbe-5855d8cca225.xml"
ms.topic: struct
f1_keywords:
 - "hbapiwmi/GetFCPStatistics_OUT"
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
- GetFCPStatistics_OUT
product:
- Windows
targetos: Windows
req.typenames: GetFCPStatistics_OUT, *PGetFCPStatistics_OUT
---

# _GetFCPStatistics_OUT structure


## -description


The GetFCPStatistics_OUT structure is used by the miniport driver to report the output parameters of the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/getfcpstatistics">GetFCPStatistics</a> WMI method. 


## -struct-fields




### -field HBAStatus

Contains a value associated with the WMI class qualifier <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a> that indicates the result of an HBA query operation.


### -field FC4Statistics

Contains a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hbapiwmi/ns-hbapiwmi-_msfc_fc4statistics">MSFC_FC4STATISTICS</a> that holds statistics for the specified FC-4 protocol.


## -remarks



The WMI tool suite generates a declaration of the GetFCPStatistics_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msfc-hbaadaptermethods-wmi-class">MSFC_HBAAdapterMethods WMI Class</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/getfcpstatistics">GetFCPStatistics</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hbapiwmi/ns-hbapiwmi-_getfcpstatistics_in">GetFCPStatistics_IN</a>
 

 

