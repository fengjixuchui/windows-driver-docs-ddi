---
UID: NC:iddcx.EVT_IDD_CX_MONITOR_UNASSIGN_SWAPCHAIN
title: EVT_IDD_CX_MONITOR_UNASSIGN_SWAPCHAIN (iddcx.h)
description: EVT_IDD_CX_MONITOR_UNASSIGN_SWAPCHAIN is called by the OS to inform the driver that a swapchain associated with a monitor is not valid anymore.
old-location: display\evt_idd_cx_monitor_unassign_swapchain.htm
tech.root: display
ms.assetid: 7e845805-0121-49b0-9c0c-0f63bed6a50c
ms.date: 05/10/2018
ms.keywords: EVT_IDD_CX_MONITOR_UNASSIGN_SWAPCHAIN, EVT_IDD_CX_MONITOR_UNASSIGN_SWAPCHAIN callback, EvtIddCxMonitorUnassignSwapchain, EvtIddCxMonitorUnassignSwapchain callback function [Display Devices], PFN_IDD_CX_MONITOR_UNASSIGN_SWAPCHAIN, PFN_IDD_CX_MONITOR_UNASSIGN_SWAPCHAIN callback function pointer [Display Devices], display.evt_idd_cx_monitor_unassign_swapchain, iddcx/EvtIddCxMonitorUnassignSwapchain
ms.topic: callback
f1_keywords:
 - "iddcx/PFN_IDD_CX_MONITOR_UNASSIGN_SWAPCHAIN"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- iddcx.h
api_name:
- PFN_IDD_CX_MONITOR_UNASSIGN_SWAPCHAIN
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_IDD_CX_MONITOR_UNASSIGN_SWAPCHAIN callback function


## -description


<b>EVT_IDD_CX_MONITOR_UNASSIGN_SWAPCHAIN</b> is called by the OS to inform the driver that a swapchain associated with a monitor is not valid anymore.


## -parameters




### -param MonitorObject [in]

A handle by the OS to identify the monitor that has an invalid associated swapchain.


## -returns




(NTSTATUS) If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, an appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code. 
                    



