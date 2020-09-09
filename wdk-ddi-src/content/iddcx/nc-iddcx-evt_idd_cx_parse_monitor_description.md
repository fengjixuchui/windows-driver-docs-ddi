---
UID: NC:iddcx.EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION
title: EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION (iddcx.h)
description: EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION is called by the OS to request the driver to parse a monitor description into a list of modes the monitor supports.
old-location: display\evt_idd_cx_parse_monitor_description.htm
tech.root: display
ms.assetid: b195cd68-fedc-436d-8afd-5e33ccb96344
ms.date: 07/31/2020
keywords: ["EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION callback function"]
ms.keywords: EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION, EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION callback, EvtIddCxParseMonitorDescription, EvtIddCxParseMonitorDescription callback function [Display Devices], PFN_IDD_CX_PARSE_MONITOR_DESCRIPTION, PFN_IDD_CX_PARSE_MONITOR_DESCRIPTION callback function pointer [Display Devices], display.evt_idd_cx_parse_monitor_description, iddcx/EvtIddCxParseMonitorDescription
req.header: iddcx.h
req.include-header: 
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
req.irql: _requires_same_
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION
 - iddcx/EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - iddcx.h
api_name:
 - PFN_IDD_CX_PARSE_MONITOR_DESCRIPTION
---

# EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION callback function


## -description

**EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION** is called by the OS to request the driver to parse a monitor description into a list of modes that the monitor supports.

## -parameters

### -param pInArgs

[in] Pointer to a [**IDARG_IN_PARSEMONITORDESCRIPTION**](ns-iddcx-idarg_in_parsemonitordescription.md) structure containing the monitor description.

### -param pOutArgs

[out] Pointer to a [**IDARG_OUT_PARSEMONITORDESCRIPTION**](ns-iddcx-idarg_out_parsemonitordescription.md) structure in which the driver returns the monitor mode information.

## -returns

If the operation is successful, **EVT_IDD_CX_PARSE_MONITOR_DESCRIPTION** must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, the driver should return an appropriate NTSTATUS error code.

