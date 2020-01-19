---
UID: NN:printerextension.IPrinterQueueView
title: IPrinterQueueView (printerextension.h)
description: Provides a way to change the range of print jobs being monitored.
old-location: print\iprinterqueueview.htm
tech.root: print
ms.assetid: 81B3D4A3-7176-4656-B23D-04F0F84D9000
ms.date: 04/20/2018
ms.keywords: IPrinterQueueView, IPrinterQueueView interface [Print Devices], IPrinterQueueView interface [Print Devices],described, print.iprinterqueueview, printerextension/IPrinterQueueView
ms.topic: interface
f1_keywords:
 - "printerextension/IPrinterQueueView"
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
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
- COM
api_location:
- Printerextension.h
api_name:
- IPrinterQueueView
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrinterQueueView interface


## -description


Provides a way to change the range of print jobs being monitored.


## -inheritance

The <b xmlns:loc="https://microsoft.com/wdcml/l10n">IPrinterQueueView</b> interface inherits from the <a href="ebbff4bc-36b2-4861-9efa-ffa45e013eb5">IDispatch</a> interface. <b>IPrinterQueueView</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -remarks



An event is raised whenever the status of the print queue changes. So when a client uses <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprinterqueueview-setviewrange">SetViewRange</a> to specify the range of print jobs (the view) to be monitored, the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprinterqueueviewevent-onchanged">IPrinterQueueViewEvent::OnChanged</a> event method fires, and the live queue is returned in response.

And also, note that job enumeration starts when the first event handler is added and stops when the last event handler is removed.

<b>IPrinterQueueView</b> also helps to make it possible to perform job management from a UWP  device app or from a printer extension. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/job-management">Job Management</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprinterqueueviewevent-onchanged">IPrinterQueueViewEvent::OnChanged</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/print/job-management">Job Management</a>
 

 

