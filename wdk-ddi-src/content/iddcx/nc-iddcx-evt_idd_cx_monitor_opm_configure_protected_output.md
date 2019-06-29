---
UID: NC:iddcx.EVT_IDD_CX_MONITOR_OPM_CONFIGURE_PROTECTED_OUTPUT
title: EVT_IDD_CX_MONITOR_OPM_CONFIGURE_PROTECTED_OUTPUT (iddcx.h)
description: EVT_IDD_CX_MONITOR_OPM_CONFIGURE_PROTECTED_OUTPUT is called by the OS to configure the protected output.
old-location: display\evt_idd_cx_monitor_opm_configure_protected_output.htm
tech.root: display
ms.assetid: 5314c5e3-bbc7-4179-bb59-4bd58110aee1
ms.date: 05/10/2018
ms.keywords: EVT_IDD_CX_MONITOR_OPM_CONFIGURE_PROTECTED_OUTPUT, EVT_IDD_CX_MONITOR_OPM_CONFIGURE_PROTECTED_OUTPUT callback, EvtIddCxMonitorOpmConfigureProtectedOutput, EvtIddCxMonitorOpmConfigureProtectedOutput callback function [Display Devices], PFN_IDD_CX_MONITOR_OPM_CONFIGURE_PROTECTED_OUTPUT, PFN_IDD_CX_MONITOR_OPM_CONFIGURE_PROTECTED_OUTPUT callback function pointer [Display Devices], display.evt_idd_cx_monitor_opm_configure_protected_output, iddcx/EvtIddCxMonitorOpmConfigureProtectedOutput
ms.topic: callback
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
req.irql: "_requires_same_"
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- iddcx.h
api_name:
- PFN_IDD_CX_MONITOR_OPM_CONFIGURE_PROTECTED_OUTPUT
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_IDD_CX_MONITOR_OPM_CONFIGURE_PROTECTED_OUTPUT callback function


## -description


<b>EVT_IDD_CX_MONITOR_OPM_CONFIGURE_PROTECTED_OUTPUT</b> is called by the OS to configure the protected output.


## -parameters




### -param OpmCxtObject [in]

A context used by the OS to identify the OPM context to configure output for.


### -param pInArgs [in]

Input arguments used by <b>EVT_IDD_CX_MONITOR_OPM CONFIGURE_PROTECTED_OUTPUT</b>.


## -returns




(NTSTATUS) If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, an appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code. 
                    



