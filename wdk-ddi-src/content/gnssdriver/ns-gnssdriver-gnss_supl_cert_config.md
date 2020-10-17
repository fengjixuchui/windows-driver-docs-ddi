---
UID: NS:gnssdriver.__unnamed_struct_41
title: GNSS_SUPL_CERT_CONFIG (gnssdriver.h)
description: This structure contains SUPL certificate information.
old-location: gnss\gnss_supl_cert_config.htm
tech.root: gnss
ms.assetid: F974D5E2-7230-4F85-9C1A-7CE7E240DBE1
ms.date: 02/15/2018
keywords: ["GNSS_SUPL_CERT_CONFIG structure"]
ms.keywords: "*PGNSS_SUPL_CERT_CONFIG, GNSS_SUPL_CERT_CONFIG, GNSS_SUPL_CERT_CONFIG structure [Sensor Devices], PGNSS_SUPL_CERT_CONFIG, PGNSS_SUPL_CERT_CONFIG structure pointer [Sensor Devices], gnss.gnss_supl_cert_config, gnssdriver/GNSS_SUPL_CERT_CONFIG, gnssdriver/PGNSS_SUPL_CERT_CONFIG"
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
targetos: Windows
req.typenames: GNSS_SUPL_CERT_CONFIG, *PGNSS_SUPL_CERT_CONFIG
f1_keywords:
 - PGNSS_SUPL_CERT_CONFIG
 - gnssdriver/PGNSS_SUPL_CERT_CONFIG
 - GNSS_SUPL_CERT_CONFIG
 - gnssdriver/GNSS_SUPL_CERT_CONFIG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - GNSS_SUPL_CERT_CONFIG
---

# GNSS_SUPL_CERT_CONFIG structure


## -description

This structure contains SUPL certificate information.

## -struct-fields

### -field Size

Structure size.

### -field Version

Version number.

### -field CertAction

A <a href="/windows-hardware/drivers/ddi/gnssdriver/ne-gnssdriver-gnss_supl_cert_action">GNSS_SUPL_CERT_ACTION</a> enumeration value that specifies the action to take on the certificate.

<table></table>
 

<table>
<tr>
<td>
<b>GNSS_SUPL_CERT_INJECT</b>

</td>
<td>
Inject the certificate.

</td>
</tr>
<tr>
<td>
<b>GNSS_SUPL_CERT_DELETE</b>

</td>
<td>
Delete the certificate specified by <b>SuplCertName</b>. The values of <b>CertSize</b> and <b>CertData</b> are ignored.

</td>
</tr>
<tr>
<td>
<b>GNSS_SUPL_CERT_PURGE</b>

</td>
<td>
Delete all the certificates injected to the GNSS driver previously. The values of <b>SuplCertName</b> , <b>CertSize</b>, and <b>CertData</b> are ignored.

</td>
</tr>
</table>

### -field SuplCertName

### -field CertSize

The size of the certificate in bytes.

### -field Unused

### -field CertData

 




#### - CertData[ANYSIZE_ARRAY]

The binary content of the certificate.  The total size of the bytes is defined by <b>CertSize</b>. The certificate is Base64 encoded.


#### - IsRoot

Specify whether the certificate is a root certificate.

Multiple root certificates can be configured since some mobile operator require this functionality. An IHV supporting SUPL should have support for multiple certificates.


#### - SuplCertName[MAX_PATH]

String containing the certificate name.


#### - Unused[512]

Padding buffer.