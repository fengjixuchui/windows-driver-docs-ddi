---
UID: NC:srb.PHW_TIMER
title: PHW_TIMER (srb.h)
description: The PHW_TIMER routine prototype declares a SCSI miniport driver's timer routine.
old-location: storage\phw_timer.htm
tech.root: storage
ms.assetid: 8f537ddb-ba94-4423-95a8-6497710d234f
ms.date: 03/29/2018
ms.keywords: "(*PHW_TIMER), (*PHW_TIMER) callback function [Storage Devices], ide_minikr_55cc9012-04fa-434c-b2b9-d24bbd1d1404.xml, srb/(*PHW_TIMER), storage.phw_timer"
ms.topic: callback
f1_keywords:
 - "srb/(*PHW_TIMER)"
req.header: srb.h
req.include-header: Storport.h, Srb.h, Storport.h
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
req.irql:
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- srb.h
api_name:
- (*PHW_TIMER)
product:
- Windows
targetos: Windows
req.typenames: SPB_CONTROLLER_CONFIG, *PSPB_CONTROLLER_CONFIG
req.product: Windows 10 or later.
---

# PHW_TIMER callback


## -description


The PHW_TIMER routine prototype declares a SCSI miniport driver's timer routine.


## -parameters




### -param DeviceExtension [in]

Pointer to the miniport driver's per-HBA storage area.


## -returns



None




## -remarks



The SCSI miniport driver's timer routine, <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff557327(v=vs.85)">HwScsiTimer</a>, is called after the interval specified when the miniport driver called <b>ScsiPortNotification</b> with the <b>RequestTimerCall</b><i>NotificationType</i> value.

Miniport drivers that work with the StorPort driver do not use this timer routine.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff557327(v=vs.85)">HwScsiTimer</a>
 

 

