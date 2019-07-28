---
UID: NS:ntifs._ECP_OPEN_PARAMETERS
title: _ECP_OPEN_PARAMETERS (ntifs.h)
description: The ECP_OPEN_PARAMETERS structure allows a caller to specify the purpose of opening of a file without interfering with existing handles and/or oplocks on the file.
old-location: ifsk\ecp_open_parameters.htm
tech.root: ifsk
ms.assetid: 1223C77A-EAEC-4FCF-B2CC-F1E2935AF5CB
ms.date: 04/16/2018
ms.keywords: "*PECP_OPEN_PARAMETERS, ECP_OPEN_PARAMETERS, ECP_OPEN_PARAMETERS structure [Installable File System Drivers], PECP_OPEN_PARAMETERS, PECP_OPEN_PARAMETERS structure pointer [Installable File System Drivers], _ECP_OPEN_PARAMETERS, ifsk.ecp_open_parameters, ntifs/ECP_OPEN_PARAMETERS, ntifs/PECP_OPEN_PARAMETERS"
ms.topic: struct
f1_keywords:
 - "ntifs/ECP_OPEN_PARAMETERS"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10, version 1709.
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
- ECP_OPEN_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: ECP_OPEN_PARAMETERS, *PECP_OPEN_PARAMETERS
---

# _ECP_OPEN_PARAMETERS structure


## -description


The <b>ECP_OPEN_PARAMETERS</b> structure allows a caller to specify the purpose of opening of a file without interfering with existing handles and/or oplocks on the file. 


## -struct-fields




### -field Size

Specifies the size of this context structure, in bytes.


### -field Reserved

Reserved for future use. This must be initialized to 0.


### -field Flags

Flags that Specify the parameters or purpose for opening a file. Contains one of the following values:

<table>
<tr>
<th>Name</th>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>ECP_OPEN_PARAMETERS_FLAG_OPEN_FOR_READ </td>
<td>0x01</td>
<td>Opening file to read it.</td>
</tr>
<tr>
<td>ECP_OPEN_PARAMETERS_FLAG_OPEN_FOR_WRITE</td>
<td>0x02</td>
<td>Opening file to write to it.</td>
</tr>
<tr>
<td>ECP_OPEN_PARAMETERS_FLAG_OPEN_FOR_DELETE</td>
<td>0x04</td>
<td>Opening file to delete it.</td>
</tr>
</table>
 

