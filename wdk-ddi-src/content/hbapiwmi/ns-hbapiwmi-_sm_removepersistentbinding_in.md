---
UID: NS:hbapiwmi._SM_RemovePersistentBinding_IN
title: _SM_RemovePersistentBinding_IN (hbapiwmi.h)
description: The SM_RemovePersistentBinding_IN structure is used to provide input parameters to the SM_RemovePersistentBinding method.
old-location: storage\sm_removepersistentbinding_in.htm
tech.root: storage
ms.assetid: 47e6a189-4b16-411a-8552-3e6f998516ba
ms.date: 03/29/2018
keywords: ["_SM_RemovePersistentBinding_IN structure"]
ms.keywords: "*PSM_RemovePersistentBinding_IN, PSM_RemovePersistentBinding_IN, PSM_RemovePersistentBinding_IN structure pointer [Storage Devices], SM_RemovePersistentBinding_IN, SM_RemovePersistentBinding_IN structure [Storage Devices], _SM_RemovePersistentBinding_IN, hbapiwmi/PSM_RemovePersistentBinding_IN, hbapiwmi/SM_RemovePersistentBinding_IN, storage.sm_removepersistentbinding_in, structs-Fibre_d27cd5dc-07ee-470c-ad0d-239f1d378841.xml"
f1_keywords:
 - "hbapiwmi/SM_RemovePersistentBinding_IN"
 - "SM_RemovePersistentBinding_IN"
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
- SM_RemovePersistentBinding_IN
targetos: Windows
req.typenames: SM_RemovePersistentBinding_IN, *PSM_RemovePersistentBinding_IN
---

# _SM_RemovePersistentBinding_IN structure


## -description


The SM_RemovePersistentBinding_IN structure is used to provide input parameters to the SM_RemovePersistentBinding method.


## -struct-fields




### -field HbaPortWWN

The worldwide name (WWN) of the local port whose events the WMI client will receive.


### -field DomainPortWWN

A worldwide name (WWN) that specifies the SAS domain worldwide name of the local port.


### -field EntryCount

The total number of persistent bindings that are associated with the HBA.


### -field Entry

An array of structures of type SMHBA_SCSIENTRY that describes an HBA's bindings between the operating system and the SAS identifiers.


## -remarks



The WMI tool suite generates a declaration of the SM_RemovePersistentBinding_IN structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_TargetInformationMethods WMI class.



