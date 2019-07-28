---
UID: NS:printoem._PUBLISHERINFO
title: _PUBLISHERINFO (printoem.h)
description: The PUBLISHERINFO structure is used as an input parameter to the IPrintOemPS::GetInfo method.
old-location: print\publisherinfo.htm
tech.root: print
ms.assetid: 6749b2e8-a9db-48a3-96e1-8592bcfa580d
ms.date: 04/20/2018
ms.keywords: "*PPUBLISHERINFO, PPUBLISHERINFO, PPUBLISHERINFO structure pointer [Print Devices], PUBLISHERINFO, PUBLISHERINFO structure [Print Devices], _PUBLISHERINFO, print.publisherinfo, print_unidrv-pscript_rendering_dbd3e74a-00bd-4c21-80e5-80b788f83bb2.xml, printoem/PPUBLISHERINFO, printoem/PUBLISHERINFO"
ms.topic: struct
f1_keywords:
 - "printoem/PUBLISHERINFO"
req.header: printoem.h
req.include-header: Printoem.h
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
- printoem.h
api_name:
- PUBLISHERINFO
product:
- Windows
targetos: Windows
req.typenames: PUBLISHERINFO, *PPUBLISHERINFO
---

# _PUBLISHERINFO structure


## -description


The PUBLISHERINFO structure is used as an input parameter to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemps-getinfo">IPrintOemPS::GetInfo</a> method.


## -struct-fields




### -field dwMode

Is a set of bit flags. The only flag defined is OEM_MODE_PUBLISHER, which must be set if a rendering plug-in for Pscript5 is using "publishing mode".


### -field wMinoutlinePPEM

Specifies the minimum font size, in pixels, for which the Pscript5 driver will download TrueType fonts as outline (Type 1) fonts. A font smaller than the minimum setting will be downloaded as a bitmap (Type 3) font.


### -field wMaxbitmapPPEM

Specifies the maximum font size, in pixels, for which the Pscript5 driver will download TrueType fonts as bitmap (Type 3) fonts. A font larger than the maximum setting will be downloaded as an outline (Type 1) font.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemps-getinfo">IPrintOemPS::GetInfo</a>
 

 

