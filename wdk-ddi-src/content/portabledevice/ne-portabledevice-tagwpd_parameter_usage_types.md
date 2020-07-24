---
UID: NE:portabledevice.tagWPD_PARAMETER_USAGE_TYPES
title: WPD_PARAMETER_USAGE_TYPES (portabledevice.h)
description: The WPD_PARAMETER_USAGE_TYPES enumeration type specifies the inheritance relationship for a service.
old-location: wpddk\wpd_parameter_usage_types.htm
tech.root: wpd_dk
ms.assetid: 0359017b-42a1-414b-a19d-89e29a0df8eb
ms.date: 02/15/2018
keywords: ["tagWPD_PARAMETER_USAGE_TYPES enumeration"]
ms.keywords: WPD_PARAMETER_USAGE_IN, WPD_PARAMETER_USAGE_INOUT, WPD_PARAMETER_USAGE_OUT, WPD_PARAMETER_USAGE_RETURN, WPD_PARAMETER_USAGE_TYPES, WPD_PARAMETER_USAGE_TYPES enumeration, portabledevice/WPD_PARAMETER_USAGE_IN, portabledevice/WPD_PARAMETER_USAGE_INOUT, portabledevice/WPD_PARAMETER_USAGE_OUT, portabledevice/WPD_PARAMETER_USAGE_RETURN, portabledevice/WPD_PARAMETER_USAGE_TYPES, tagWPD_PARAMETER_USAGE_TYPES, wpddk.wpd_parameter_usage_types
f1_keywords:
 - "portabledevice/WPD_PARAMETER_USAGE_TYPES"
 - "WPD_PARAMETER_USAGE_TYPES"
req.header: portabledevice.h
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
- PortableDevice.h
api_name:
- WPD_PARAMETER_USAGE_TYPES
targetos: Windows
req.typenames: WPD_PARAMETER_USAGE_TYPES
ms.custom: RS5
---

# tagWPD_PARAMETER_USAGE_TYPES enumeration


## -description


The <b>WPD_PARAMETER_USAGE_TYPES</b> enumeration type specifies the inheritance relationship for a service.


## -enum-fields




### -field WPD_PARAMETER_USAGE_RETURN

The parameter receives the return value, if specified by the method.


### -field WPD_PARAMETER_USAGE_IN

The parameter contains an input value before the method is called.


### -field WPD_PARAMETER_USAGE_OUT

The parameter contains an output value when the method returns.


### -field WPD_PARAMETER_USAGE_INOUT

The parameter contains an input value before the method is called and an output value when it returns.

