---
UID: NE:gnssdriver.__unnamed_enum_10
title: GNSS_SUPL_CERT_ACTION (gnssdriver.h)
description: This enumeration indicates the action to take upon receipt of the SUPL certificate, which is defined by the GNSS_SUPL_CERT_CONFIG structure.
old-location: gnss\gnss_supl_cert_action.htm
tech.root: gnss
ms.assetid: DE51CB88-E761-40DC-B437-7572CD95FB4A
ms.date: 02/15/2018
ms.keywords: GNSS_SUPL_CERT_ACTION, GNSS_SUPL_CERT_ACTION enumeration [Sensor Devices], GNSS_Supl_Cert_Delete, GNSS_Supl_Cert_Inject, GNSS_Supl_Cert_Purge, gnss.gnss_supl_cert_action, gnssdriver/GNSS_SUPL_CERT_ACTION, gnssdriver/GNSS_Supl_Cert_Delete, gnssdriver/GNSS_Supl_Cert_Inject, gnssdriver/GNSS_Supl_Cert_Purge
ms.topic: enum
f1_keywords:
 - "gnssdriver/GNSS_SUPL_CERT_ACTION"
req.header: gnssdriver.h
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
- gnssdriver.h
api_name:
- GNSS_SUPL_CERT_ACTION
product:
- Windows
targetos: Windows
req.typenames: GNSS_SUPL_CERT_ACTION
---

# GNSS_SUPL_CERT_ACTION enumeration


## -description


This enumeration indicates the action to take upon receipt of the SUPL certificate, which is defined by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gnssdriver/ns-gnssdriver-gnss_supl_cert_config">GNSS_SUPL_CERT_CONFIG</a> structure.


## -enum-fields




### -field GNSS_Supl_Cert_Inject

Indicates that the certificate should be injected.


### -field GNSS_Supl_Cert_Delete

Indicates that the certificate specified by the <b>SuplCertName</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gnssdriver/ns-gnssdriver-gnss_supl_cert_config">GNSS_SUPL_CERT_CONFIG</a> structure should be deleted.


### -field GNSS_Supl_Cert_Purge

Indicates that all certificates previously injected into the GNSS driver should be deleted.

