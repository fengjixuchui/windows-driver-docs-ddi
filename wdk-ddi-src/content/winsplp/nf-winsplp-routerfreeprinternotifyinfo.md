---
UID: NF:winsplp.RouterFreePrinterNotifyInfo
title: RouterFreePrinterNotifyInfo function (winsplp.h)
description: The print spooler's RouterFreePrinterNotifyInfo function deallocates a specified PRINTER_NOTIFY_INFO structure and its associated PRINTER_NOTIFY_INFO_DATA structure array.
old-location: print\routerfreeprinternotifyinfo.htm
tech.root: print
ms.assetid: 11beef0b-061a-4d73-b723-d0214f479503
ms.date: 04/20/2018
keywords: ["RouterFreePrinterNotifyInfo function"]
ms.keywords: RouterFreePrinterNotifyInfo, RouterFreePrinterNotifyInfo function [Print Devices], print.routerfreeprinternotifyinfo, spoolfnc_7ae0296f-8bfe-4ee3-b621-1d1582deafdf.xml, winsplp/RouterFreePrinterNotifyInfo
f1_keywords:
 - "winsplp/RouterFreePrinterNotifyInfo"
 - "RouterFreePrinterNotifyInfo"
req.header: winsplp.h
req.include-header: Winsplp.h
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
req.lib: Spoolss.lib
req.dll: Spoolss.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Spoolss.dll
api_name:
- RouterFreePrinterNotifyInfo
targetos: Windows
req.typenames: 
---

# RouterFreePrinterNotifyInfo function


## -description


The print spooler's <code>RouterFreePrinterNotifyInfo</code> function deallocates a specified PRINTER_NOTIFY_INFO structure and its associated PRINTER_NOTIFY_INFO_DATA structure array. (These structures are described in the Microsoft Windows SDK documentation.)


## -parameters




### -param pInfo [in, optional]

Caller-supplied pointer to a PRINTER_NOTIFY_INFO structure (described in the Windows SDK documentation).


## -returns



If the operation succeeds, the function returns <b>TRUE</b>. Otherwise the function returns <b>FALSE</b>.




## -remarks



A print provider's <a href="https://docs.microsoft.com/previous-versions/ff561930(v=vs.85)">RefreshPrinterChangeNotification</a> function should call <code>RouterFreePrinterNotifyInfo</code> to deallocate structures previously allocated by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/nf-winsplp-routerallocprinternotifyinfo">RouterAllocPrinterNotifyInfo</a>, but only if <b>RefreshPrinterChangeNotification</b> encounters a error. If <b>RefreshPrinterChangeNotification</b> succeeds, you should assume that the client application will deallocate the structures.

Besides deallocating the specified PRINTER_NOTIFY_INFO structure and its associated PRINTER_NOTIFY_INFO_DATA structure array, the function also deallocates buffer space pointed to by <i>pBuf</i> in any element of the PRINTER_NOTIFY_INFO_DATA structure array.

For additional information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/supporting-printer-change-notifications">Supporting Printer Change Notifications</a>.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/ff561930(v=vs.85)">RefreshPrinterChangeNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/nf-winsplp-routerallocprinternotifyinfo">RouterAllocPrinterNotifyInfo</a>
 

 

