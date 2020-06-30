---
UID: NC:iddcx.PFN_IDDCXMONITORSETSRMLIST
title: PFN_IDDCXMONITORSETSRMLIST (iddcx.h)
description: Implemented by the client driver to pass a HDCP SRM list to the GPU driver associated with the rendering of the specified monitor.
ms.assetid: 38dfb1cf-f2fd-462f-bce0-a95505cead96
ms.date: 10/19/2018
keywords: ["PFN_IDDCXMONITORSETSRMLIST callback function"]
f1_keywords:
 - "iddcx/PFN_IDDCXMONITORSETSRMLIST"
req.header: iddcx.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql:
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library:
topic_type:
- apiref
api_type:
- UserDefined
api_location:
- iddcx.h
api_name:
- PFN_IDDCXMONITORSETSRMLIST
product: 
- Windows
targetos: Windows
tech.root: display
---

# *PFN_IDDCXMONITORSETSRMLIST callback function

## -description

Implemented by the client driver to pass a HDCP SRM list to the GPU driver associated with the rendering of the specified monitor.

## -prototype

```cpp
//Declaration

*PFN_IDDCXMONITORSETSRMLIST *PfnIddcxmonitorsetsrmlist;

// Definition

NTSTATUS *PfnIddcxmonitorsetsrmlist
(
	PIDD_DRIVER_GLOBALS DriverGlobals
	IDDCX_MONITOR MonitorObject
	CONST IDARG_IN_SETSRMLIST *pInArgs
)
{...}

*PFN_IDDCXMONITORSETSRMLIST


```

## -parameters

### -param DriverGlobals [in]

Contains system-defined per-driver data.

### -param MonitorObject [in]

The monitor object that the SRM list is associated with.

### -param pInArgs [in]

Input arguments of function.

## -returns

Returns NTSTATUS with the following error codes:

| Return value | Description |
| --- | --- |
| STATUS_SUCCESS | The routine succeeded. |
| STATUS_GRAPHICS_OPM_NOT_SUPPORTED | The GPU driver does not support this new functionality. |
| STATUS_GRAPHICS_OPM_INVALID_SRM | the GPU driver does recognize the format of the SRM list, this include if the driver detected the list had been tampered with. |


## -remarks

Register your implementation of this callback function by setting the appropriate member of IDARG_IN_SETSRMLIST and then calling IddCxMonitorSetSrmList.


## -see-also
