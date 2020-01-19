---
UID: NS:hbapiwmi._GetFC3MgmtInfo_OUT
title: _GetFC3MgmtInfo_OUT (hbapiwmi.h)
description: The GetFC3MgmtInfo_OUT structure is used to report the output parameter data of the GetFC3MgmtInfo WMI method to the WMI client.
old-location: storage\getfc3mgmtinfo_out.htm
tech.root: storage
ms.assetid: 5cce25e7-582b-49b3-9f10-be59471e377f
ms.date: 03/29/2018
ms.keywords: "*PGetFC3MgmtInfo_OUT, GetFC3MgmtInfo_OUT, GetFC3MgmtInfo_OUT structure [Storage Devices], PGetFC3MgmtInfo_OUT, PGetFC3MgmtInfo_OUT structure pointer [Storage Devices], _GetFC3MgmtInfo_OUT, hbapiwmi/GetFC3MgmtInfo_OUT, hbapiwmi/PGetFC3MgmtInfo_OUT, storage.getfc3mgmtinfo_out, structs-Fibre_599fab97-a877-4299-8697-1decb1305672.xml"
ms.topic: struct
f1_keywords:
 - "hbapiwmi/GetFC3MgmtInfo_OUT"
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
- GetFC3MgmtInfo_OUT
product:
- Windows
targetos: Windows
req.typenames: GetFC3MgmtInfo_OUT, *PGetFC3MgmtInfo_OUT
---

# _GetFC3MgmtInfo_OUT structure


## -description


The GetFC3MgmtInfo_OUT structure is used to report the output parameter data of the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/getfc3mgmtinfo">GetFC3MgmtInfo</a> WMI method to the WMI client.


## -struct-fields




### -field HBAStatus

Contains a value associated with the WMI class qualifier <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a> that indicates the result of an HBA query operation. 


### -field MgmtInfo

Contains a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hbapiwmi/ns-hbapiwmi-_hbafc3mgmtinfo">HBAFC3MgmtInfo</a> that reports FC3 management information. 


## -remarks



The <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/getfc3mgmtinfo">GetFC3MgmtInfo</a> method reports fibre channel-3 management information.

The WMI tool suite generates a declaration of the GetEventBuffer_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msfc-hbaadaptermethods-wmi-class">MSFC_HBAAdapterMethods WMI Class</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/getfc3mgmtinfo">GetFC3MgmtInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hbapiwmi/ns-hbapiwmi-_hbafc3mgmtinfo">HBAFC3MgmtInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a>
 

 

