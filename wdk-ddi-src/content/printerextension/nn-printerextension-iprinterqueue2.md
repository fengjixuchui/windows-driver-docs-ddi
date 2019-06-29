---
UID: NN:printerextension.IPrinterQueue2
title: IPrinterQueue2 (printerextension.h)
description: Represents a single printer queue.
old-location: print\iprinterqueue2.htm
tech.root: print
ms.assetid: 06459A1F-A14B-43BA-9771-47205CC3F388
ms.date: 04/20/2018
ms.keywords: IPrinterQueue2, IPrinterQueue2 interface [Print Devices], IPrinterQueue2 interface [Print Devices],described, print.iprinterqueue2, printerextension/IPrinterQueue2
ms.topic: interface
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
- IPrinterQueue2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrinterQueue2 interface


## -description


Represents a single printer queue. 

This interface extends <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nn-printerextension-iprinterqueue">IPrinterQueue</a> and allows a user to manage print jobs and device maintenance from within a UWP  device app for printers, or from a printer extension.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrinterQueue2</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nn-printerextension-iprinterqueue">IPrinterQueue</a>. <b>IPrinterQueue2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrinterQueue2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprinterqueue2-getprinterqueueview">GetPrinterQueueView</a>
</td>
<td align="left" width="63%">
Retrieves an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nn-printerextension-iprinterqueueview">IPrinterQueueView</a> object, and initializes the object with the range of jobs to be monitored.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprinterqueue2-sendbidisetrequestasync">SendBidiSetRequestAsync</a>
</td>
<td align="left" width="63%">
Uses an XML string value to send a Bidi Set request as an asynchronous operation.

</td>
</tr>
</table> 


## -remarks



<b>IPrinterQueue2</b> also helps to make it possible to perform device maintenance and job management from a UWP  device app or from a printer extension. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/device-maintenance">Device Maintenance</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/print/job-management">Job Management</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/print/device-maintenance">Device Maintenance</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nn-printerextension-iprinterqueue">IPrinterQueue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/print/job-management">Job Management</a>
 

 

