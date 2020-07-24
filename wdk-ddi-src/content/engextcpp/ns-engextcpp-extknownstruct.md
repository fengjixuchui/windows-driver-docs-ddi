---
UID: NS:engextcpp.ExtKnownStruct
title: ExtKnownStruct (engextcpp.h)
description: The ExtKnownStruct structure is used to specify how a target's structure can be formatted for output.
old-location: debugger\extknownstruct.htm
tech.root: debugger
ms.assetid: 95bf9a47-e121-4432-a28f-5476467f1823
ms.date: 05/03/2018
keywords: ["ExtKnownStruct structure"]
ms.keywords: EngExtCpp_Ref_b59346d2-06da-4112-9bed-ce64de0f2807.xml, ExtKnownStruct, ExtKnownStruct structure [Windows Debugging], debugger.extknownstruct, engextcpp/ExtKnownStruct
f1_keywords:
 - "engextcpp/ExtKnownStruct"
 - "ExtKnownStruct"
req.header: engextcpp.hpp
req.include-header: Engextcpp.hpp
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
- Engextcpp.hpp
api_name:
- ExtKnownStruct
targetos: Windows
req.typenames: 
---

# ExtKnownStruct structure


## -description


The <b>ExtKnownStruct</b> structure is used to specify how a target's structure can be formatted for output.


## -struct-fields




### -field TypeName

The name of the structure type.


### -field Method

The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/ff543989(v=vs.85)">ExtKnownStructMethod</a> callback function that can be called to format an instance of the structure specified in <b>TypeName</b>.


### -field SuppressesTypeName

A Boolean flag that specifies whether the formatted output includes the name of the structure's type.  If <b>FALSE</b>, the name is included in the formatted output; otherwise, the name is not included.


## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/ff543989(v=vs.85)">ExtKnownStructMethod</a>
 

 

