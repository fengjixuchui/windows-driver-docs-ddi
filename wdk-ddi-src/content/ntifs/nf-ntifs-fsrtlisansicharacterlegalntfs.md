---
UID: NF:ntifs.FsRtlIsAnsiCharacterLegalNtfs
title: FsRtlIsAnsiCharacterLegalNtfs macro (ntifs.h)
description: The FsRtlIsAnsiCharacterLegalNtfs macro determines whether an ANSI character is legal for NTFS file names.
old-location: ifsk\fsrtlisansicharacterlegalntfs.htm
tech.root: ifsk
ms.assetid: 05d03799-752d-4f59-b96e-1a6d91bee8c4
ms.date: 04/16/2018
ms.keywords: FsRtlIsAnsiCharacterLegalNtfs, FsRtlIsAnsiCharacterLegalNtfs function [Installable File System Drivers], fsrtlref_9150101b-7411-4de2-afd5-0b928ed0e6b1.xml, ifsk.fsrtlisansicharacterlegalntfs, ntifs/FsRtlIsAnsiCharacterLegalNtfs
ms.topic: macro
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
- FsRtlIsAnsiCharacterLegalNtfs
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlIsAnsiCharacterLegalNtfs macro


## -description


The <b>FsRtlIsAnsiCharacterLegalNtfs</b> macro determines whether an ANSI character is legal for NTFS file names.


## -parameters




### -param C

<p>Pointer to the character to be tested.</p>


### -param WILD_OK

<p>Set to <b>TRUE</b> if wildcard characters are to be considered legal, <b>FALSE</b> otherwise.</p>






## -remarks



For information about other string-handling routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">Strings</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-fsrtlisansicharacterlegal">FsRtlIsAnsiCharacterLegal</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-fsrtlisansicharacterlegalfat">FsRtlIsAnsiCharacterLegalFat</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-fsrtlisansicharacterlegalhpfs">FsRtlIsAnsiCharacterLegalHpfs</a>
 

 

