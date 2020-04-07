---
UID: NS:1394._IRB_REQ_CONTROL
title: _IRB_REQ_CONTROL (1394.h)
description: This structure contains the fields necessary for the 1394 bus driver to carry out a control request.
old-location: ieee\irb_req_control.htm
tech.root: IEEE
ms.assetid: F0ABD318-AC63-40D5-B94E-BD6FEA1A57AC
ms.date: 02/15/2018
keywords: ["_IRB_REQ_CONTROL structure"]
ms.keywords: 1394/IRB_REQ_CONTROL, IEEE.irb_req_control, IRB_REQ_CONTROL, IRB_REQ_CONTROL structure [Buses], _IRB_REQ_CONTROL
f1_keywords:
 - "1394/IRB_REQ_CONTROL"
req.header: 1394.h
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
- 1394.h
api_name:
- IRB_REQ_CONTROL
product:
- Windows
targetos: Windows
req.typenames: IRB_REQ_CONTROL
---

# _IRB_REQ_CONTROL structure


## -description


This structure contains the fields necessary for the 1394 bus driver to carry out a control request.


## -struct-fields




### -field ulIoControlCode

Specifies the control code used in this request. Vendors should make these control codes unique, so that they do not overlap.


### -field pInBuffer

Points to an MDL that describes the input buffer. The input buffer contains user-defined information.


### -field ulInBufferLength

Specifies the length of the input buffer.


### -field pOutBuffer

Points to an MDL that describes the output buffer. The output buffer contains user-defined information.


### -field ulOutBufferLength

Specifies the length of the output buffer.


### -field BytesReturned

Specifies the number of bytes returned.

