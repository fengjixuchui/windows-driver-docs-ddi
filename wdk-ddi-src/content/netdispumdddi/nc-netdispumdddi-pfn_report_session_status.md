---
UID: NC:netdispumdddi.PFN_REPORT_SESSION_STATUS
title: PFN_REPORT_SESSION_STATUS (netdispumdddi.h)
description: Called by the user-mode display driver to report the status of the current Miracast connected session.The data type of this function is PFN_REPORT_SESSION_STATUS.
old-location: display\reportsessionstatus.htm
tech.root: display
ms.assetid: a3e44e55-5c6a-4a79-8caa-3a3b9db6b456
ms.date: 05/10/2018
ms.keywords: PFN_REPORT_SESSION_STATUS, PFN_REPORT_SESSION_STATUS callback, ReportSessionStatus, ReportSessionStatus callback function [Display Devices], display.reportsessionstatus, netdispumdddi/ReportSessionStatus
ms.topic: callback
req.header: netdispumdddi.h
req.include-header: Netdispumdddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
- Netdispumdddi.h
api_name:
- ReportSessionStatus
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFN_REPORT_SESSION_STATUS callback function


## -description


Called by the user-mode display driver to report the status of the current Miracast connected session.The data type of this function is <b>PFN_REPORT_SESSION_STATUS</b>.




## -parameters




### -param hMiracastDeviceHandle [in]

A handle that represents a Miracast device. The Miracast user-mode driver previously obtained this handle as the <i>hMiracastDeviceHandle</i> parameter in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/netdispumdddi/nc-netdispumdddi-pfn_create_miracast_context">CreateMiracastContext</a> function.


### -param MiracastStatus [in]

The current status of the Miracast link, of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/netdispumdddi/ne-netdispumdddi-miracast_status">MIRACAST_STATUS</a>.


### -param Status [in]

A status value the driver can provide that's logged for diagnostics purposes.


## -returns



Does not return a value.




## -remarks



If the Miracast user-mode driver reports an error in the <i>MiracastStatus</i> parameter, it initiates a tear-down of the current Miracast connected session.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/netdispumdddi/nc-netdispumdddi-pfn_create_miracast_context">CreateMiracastContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/netdispumdddi/ne-netdispumdddi-miracast_status">MIRACAST_STATUS</a>
 

 

