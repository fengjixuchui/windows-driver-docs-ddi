---
UID: NF:ntifs.FsRtlIsAnsiCharacterLegalFat
title: FsRtlIsAnsiCharacterLegalFat macro (ntifs.h)
description: The FsRtlIsAnsiCharacterLegalFat macro determines whether an ANSI character is legal for FAT file names.
old-location: ifsk\fsrtlisansicharacterlegalfat.htm
tech.root: ifsk
ms.assetid: 4bbd50a8-1f1f-45d9-9b63-6c1576fe7b98
ms.date: 04/16/2018
keywords: ["FsRtlIsAnsiCharacterLegalFat macro"]
ms.keywords: FsRtlIsAnsiCharacterLegalFat, FsRtlIsAnsiCharacterLegalFat function [Installable File System Drivers], fsrtlref_9d13203c-5fc4-4f4f-9372-09459f053bbc.xml, ifsk.fsrtlisansicharacterlegalfat, ntifs/FsRtlIsAnsiCharacterLegalFat
f1_keywords:
 - "ntifs/FsRtlIsAnsiCharacterLegalFat"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Desktop
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
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntifs.h
api_name:
- FsRtlIsAnsiCharacterLegalFat
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlIsAnsiCharacterLegalFat macro


## -description


The <b>FsRtlIsAnsiCharacterLegalFat</b> macro determines whether an ANSI character is legal for FAT file names.


## -parameters




### -param C

<p>Pointer to the character to be tested.</p>


### -param WILD_OK

<p>Set to <b>TRUE</b> if wildcard characters are to be considered legal, <b>FALSE</b> otherwise.</p>






## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlisansicharacterlegal">FsRtlIsAnsiCharacterLegal</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlisansicharacterlegalhpfs">FsRtlIsAnsiCharacterLegalHpfs</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlisansicharacterlegalntfs">FsRtlIsAnsiCharacterLegalNtfs</a>
 

 

