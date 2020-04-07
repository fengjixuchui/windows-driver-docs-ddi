---
UID: NS:ntifs._FILE_LEVEL_TRIM
title: _FILE_LEVEL_TRIM (ntifs.h)
description: The FILE_LEVEL_TRIM structure contains an array of byte ranges to trim for a file.
old-location: ifsk\file_level_trim.htm
tech.root: ifsk
ms.assetid: 72FD2A3B-B246-41BA-BEB6-169C214C32D7
ms.date: 04/16/2018
keywords: ["_FILE_LEVEL_TRIM structure"]
ms.keywords: "*PFILE_LEVEL_TRIM, FILE_LEVEL_TRIM, FILE_LEVEL_TRIM structure [Installable File System Drivers], PFILE_LEVEL_TRIM, PFILE_LEVEL_TRIM structure pointer [Installable File System Drivers], _FILE_LEVEL_TRIM, ifsk.file_level_trim, ntifs/FILE_LEVEL_TRIM, ntifs/PFILE_LEVEL_TRIM"
f1_keywords:
 - "ntifs/FILE_LEVEL_TRIM"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
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
- ntifs.h
api_name:
- FILE_LEVEL_TRIM
product:
- Windows
targetos: Windows
req.typenames: FILE_LEVEL_TRIM, *PFILE_LEVEL_TRIM
---

# _FILE_LEVEL_TRIM structure


## -description


The <b>FILE_LEVEL_TRIM</b> structure contains an array of byte ranges to trim for a file.


## -struct-fields




### -field Key

The key for the byte range locks. Most callers will set this to 0. Remote file systems use <b>Key</b> for tagging a set of range locks.


### -field NumRanges

Total number of range structures in <b>Ranges</b>.


### -field Ranges

Array of trim ranges for a file.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_level_trim_range">FILE_LEVEL_TRIM_RANGE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-file-level-trim">FSCTL_FILE_LEVEL_TRIM</a>
 

 

