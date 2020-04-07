---
UID: NS:ntifs._FILE_ZERO_DATA_INFORMATION_EX
title: _FILE_ZERO_DATA_INFORMATION_EX (ntifs.h)
description: Contains a range of a file to set to zeros.
old-location: ifsk\file_zero_data_information_ex.htm
tech.root: ifsk
ms.assetid: 429C644C-C784-4C0E-96C3-EC82698F6624
ms.date: 04/16/2018
keywords: ["_FILE_ZERO_DATA_INFORMATION_EX structure"]
ms.keywords: "*PFILE_ZERO_DATA_INFORMATION_EX, FILE_ZERO_DATA_INFORMATION_EX, FILE_ZERO_DATA_INFORMATION_EX structure [Installable File System Drivers], PFILE_ZERO_DATA_INFORMATION_EX, PFILE_ZERO_DATA_INFORMATION_EX structure pointer [Installable File System Drivers], _FILE_ZERO_DATA_INFORMATION_EX, ifsk.file_zero_data_information_ex, ntifs/FILE_ZERO_DATA_INFORMATION_EX, ntifs/PFILE_ZERO_DATA_INFORMATION_EX"
f1_keywords:
 - "ntifs/FILE_ZERO_DATA_INFORMATION_EX"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
- FILE_ZERO_DATA_INFORMATION_EX
product:
- Windows
targetos: Windows
req.typenames: FILE_ZERO_DATA_INFORMATION_EX, *PFILE_ZERO_DATA_INFORMATION_EX
---

# _FILE_ZERO_DATA_INFORMATION_EX structure


## -description


Contains a range of a file to set to zeros. This structure is used by the 
<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-set-zero-data">FSCTL_SET_ZERO_DATA</a> control code. It's similar to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_zero_data_information">FILE_ZERO_DATA_INFORMATION</a>, but contains an additional <b>Flags</b> member. 


## -struct-fields




### -field FileOffset

The file offset of the start of the range to set to zeros, in bytes.


### -field BeyondFinalZero

The byte offset of the first byte beyond the last zeroed byte.


### -field Flags

The following flags are supported:

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td><b>FILE_ZERO_DATA_INFORMATION_FLAG_PRESERVE_CACHED_DATA</b></td>
<td>Indicates not to purge the contents of the cache corresponding to this range of the file. Only drivers can set this flag.</td>
</tr>
</table>
 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_zero_data_information">FILE_ZERO_DATA_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-set-zero-data">FSCTL_SET_ZERO_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfscontrolfile">FltFsControlFile</a>
 

 

