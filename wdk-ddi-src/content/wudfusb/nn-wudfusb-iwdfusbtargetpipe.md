---
UID: NN:wudfusb.IWDFUsbTargetPipe
title: IWDFUsbTargetPipe (wudfusb.h)
description: The IWDFUsbTargetPipe interface exposes a USB pipe (endpoint), which is also an I/O target.
old-location: wdf\iwdfusbtargetpipe.htm
tech.root: wdf
ms.assetid: 16364b13-d902-4ba3-8d0a-c044946afa1e
ms.date: 02/26/2018
ms.keywords: IWDFUsbTargetPipe, IWDFUsbTargetPipe interface, IWDFUsbTargetPipe interface,described, UMDFUSBref_985f9453-7475-4e9b-894c-5d4e7b8d3971.xml, umdf.iwdfusbtargetpipe, wdf.iwdfusbtargetpipe, wudfusb/IWDFUsbTargetPipe
ms.topic: interface
req.header: wudfusb.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFUsbTargetPipe
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFUsbTargetPipe interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


The <b>IWDFUsbTargetPipe</b> interface exposes a USB pipe (endpoint), which is also an I/O target.




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFUsbTargetPipe</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfiotarget">IWDFIoTarget</a>. <b>IWDFUsbTargetPipe</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWDFUsbTargetPipe</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nf-wudfusb-iwdfusbtargetpipe-abort">IWDFUsbTargetPipe::Abort</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nf-wudfusb-iwdfusbtargetpipe-abort">Abort</a> method aborts all pending transfers on a USB pipe.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nf-wudfusb-iwdfusbtargetpipe-flush">IWDFUsbTargetPipe::Flush</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfworkitem-flush">Flush</a> method discards any data that WinUsb saved when the device returned more data than the client requested.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nf-wudfusb-iwdfusbtargetpipe-getinformation">IWDFUsbTargetPipe::GetInformation</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nf-wudfusb-iwdfusbtargetpipe-getinformation">GetInformation</a> method retrieves information about a USB pipe (endpoint).

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nf-wudfusb-iwdfusbtargetpipe-gettype">IWDFUsbTargetPipe::GetType</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nf-extsfns-idebugfaentrytags-gettype">GetType</a> method retrieves the type of a USB pipe.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nf-wudfusb-iwdfusbtargetpipe-isinendpoint">IWDFUsbTargetPipe::IsInEndPoint</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nf-wudfusb-iwdfusbtargetpipe-isinendpoint">IsInEndPoint</a> method determines whether a USB pipe (endpoint) is an IN pipe.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nf-wudfusb-iwdfusbtargetpipe-isoutendpoint">IWDFUsbTargetPipe::IsOutEndPoint</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nf-wudfusb-iwdfusbtargetpipe-isoutendpoint">IsOutEndPoint</a> method determines whether a USB pipe (endpoint) is an OUT pipe.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nf-wudfusb-iwdfusbtargetpipe-reset">IWDFUsbTargetPipe::Reset</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/test/wpt/reset">Reset</a> method resets the data toggle and clears the stall condition on a USB pipe.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nf-wudfusb-iwdfusbtargetpipe-retrievepipepolicy">IWDFUsbTargetPipe::RetrievePipePolicy</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nf-wudfusb-iwdfusbtargetpipe-retrievepipepolicy">RetrievePipePolicy</a> method retrieves a WinUsb pipe policy.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nf-wudfusb-iwdfusbtargetpipe-setpipepolicy">IWDFUsbTargetPipe::SetPipePolicy</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfusb/nf-wudfusb-iwdfusbtargetpipe-setpipepolicy">SetPipePolicy</a> method sets the WinUsb pipe policy.

</td>
</tr>
</table> 

