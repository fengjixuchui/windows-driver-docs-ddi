---
UID: NS:acpiioct._ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2
title: _ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2 (acpiioct.h)
description: This topic describes the ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2 structure.
old-location: acpi\acpi_eval_input_buffer_complex_v2.htm
tech.root: acpi
ms.assetid: EAF78C14-7BE1-4441-B372-5AB0711E1F19
ms.date: 02/15/2018
keywords: ["_ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2 structure"]
ms.keywords: "*PACPI_EVAL_INPUT_BUFFER_COMPLEX_V2, ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2, ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2 structure [ACPI Devices], PACPI_EVAL_INPUT_BUFFER_COMPLEX_V2, PACPI_EVAL_INPUT_BUFFER_COMPLEX_V2 structure pointer [ACPI Devices], _ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2, acpi.acpi_eval_input_buffer_complex_v2, acpiioct/ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2, acpiioct/PACPI_EVAL_INPUT_BUFFER_COMPLEX_V2"
f1_keywords:
 - "acpiioct/ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2"
 - "ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2"
req.header: acpiioct.h
req.include-header: Acpiioct.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709 and later versions.
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
- Acpiioct.h
api_name:
- ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2
targetos: Windows
req.typenames: ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2, *PACPI_EVAL_INPUT_BUFFER_COMPLEX_V2
---

# _ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2 structure


## -description


This topic describes the <b>ACPI_EVAL_INPUT_BUFFER_COMPLEX_V2</b> structure.


## -struct-fields




### -field Signature

Defines the <b>ULONG</b> member <b>Signature</b>.


### -field DUMMYUNIONNAME

Defines the method name member of <b>DUMMYUNIONNAME</b>.


### -field DUMMYUNIONNAME.MethodName

 


### -field DUMMYUNIONNAME.MethodNameAsUlong

 


### -field Size

Defines the <b>ULONG</b> member <b>Size</b>.


### -field ArgumentCount

Defines the <b>ULONG</b> member <b>ArgumentCount</b>.


### -field Argument

 




#### - Argument[ANYSIZE_ARRAY]

Defines the <b>ACPI_METHOD_ARGUMENT_V2</b> member <b>Argument[ANYSIZE_ARRAY]</b>.

