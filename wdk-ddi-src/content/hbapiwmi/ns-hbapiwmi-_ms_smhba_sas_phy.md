---
UID: NS:hbapiwmi._MS_SMHBA_SAS_PHY
title: _MS_SMHBA_SAS_PHY (hbapiwmi.h)
description: The MS_SMHBA_SAS_PHY structure is used to report the SAS physical port information.
old-location: storage\ms_smhba_sas_phy.htm
tech.root: storage
ms.assetid: 9bbf2f63-4479-47ee-a014-78b13deccb4c
ms.date: 03/29/2018
keywords: ["_MS_SMHBA_SAS_PHY structure"]
ms.keywords: "*PMS_SMHBA_SAS_PHY, MS_SMHBA_SAS_PHY, MS_SMHBA_SAS_PHY structure [Storage Devices], PMS_SMHBA_SAS_PHY, PMS_SMHBA_SAS_PHY structure pointer [Storage Devices], _MS_SMHBA_SAS_PHY, hbapiwmi/MS_SMHBA_SAS_PHY, hbapiwmi/PMS_SMHBA_SAS_PHY, storage.ms_smhba_sas_phy, structs-Fibre_2ff7917d-a369-4cc9-ab8e-c774f63761a7.xml"
f1_keywords:
 - "hbapiwmi/MS_SMHBA_SAS_PHY"
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
- MS_SMHBA_SAS_PHY
product:
- Windows
targetos: Windows
req.typenames: MS_SMHBA_SAS_PHY, *PMS_SMHBA_SAS_PHY
---

# _MS_SMHBA_SAS_PHY structure


## -description


The MS_SMHBA_SAS_PHY structure is used to report the SAS physical port information.


## -struct-fields




### -field PhyIdentifier

The port whose physical configuration and link information is being returned. It is unique within the context of the SAS device that contains the physical port.


### -field NegotiatedLinkRate

The state or the transmission speed that is negotiated by the physical port for the physical link.


### -field ProgrammedMinLinkRate

The minimum physical link rate that is set by the physical port control mechanism.


### -field HardwareMinLinkRate

The minimum physical link rate that is supported by the physical port.


### -field ProgrammedMaxLinkRate

The maximum physical link rate that is set by the physical port control mechanism.


### -field HardwareMaxLinkRate

The maximum physical link rate that is supported by the physical port.


### -field domainPortWWN

The Port_Identifier that has the smallest value of any Port_Identifier of an expander SMP.


## -remarks



Link rates are defined in hpaapi.h as HBA_SASSPEED_1_5GBIT and HBA_SASSPEED_3GBIT.



