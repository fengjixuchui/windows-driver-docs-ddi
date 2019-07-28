---
UID: NF:wudfddi.IWDFDevice.SetPnpState
title: IWDFDevice::SetPnpState (wudfddi.h)
description: The SetPnpState method turns on or off (or sets to the default state) the specified Plug and Play (PnP) property of a device.
old-location: wdf\iwdfdevice_setpnpstate.htm
tech.root: wdf
ms.assetid: 3bd88ecd-7c7c-4ee9-8eb8-bc5653bd4ed0
ms.date: 02/26/2018
ms.keywords: IWDFDevice interface,SetPnpState method, IWDFDevice.SetPnpState, IWDFDevice::SetPnpState, SetPnpState, SetPnpState method, SetPnpState method,IWDFDevice interface, UMDFDeviceObjectRef_1efea639-31d7-4420-8b8a-c528597ceffb.xml, umdf.iwdfdevice_setpnpstate, wdf.iwdfdevice_setpnpstate, wudfddi/IWDFDevice::SetPnpState
ms.topic: method
f1_keywords:
 - "wudfddi/IWDFDevice.SetPnpState"
req.header: wudfddi.h
req.include-header: Wudfddi.h
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
- IWDFDevice.SetPnpState
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFDevice::SetPnpState


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>SetPnpState</b> method turns on or off (or sets to the default state) the specified Plug and Play (PnP) property of a device.


## -parameters




### -param State [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi_types/ne-wudfddi_types-_wdf_pnp_state">WDF_PNP_STATE</a>-typed value that identifies the PnP property to set.


### -param Value [in]

A WDF_TRI_STATE-typed value that identifies how to set the PnP property that <i>State</i> specifies. The following table shows the possible values for <i>Value</i>.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>WdfUseDefault</b> (0)

</td>
<td>
Set the PnP property to the default state.

</td>
</tr>
<tr>
<td>
<b>WdfFalse</b> (1)

</td>
<td>
Turn off the PnP property.

</td>
</tr>
<tr>
<td>
<b>WdfTrue</b> (2)

</td>
<td>
Turn on the PnP property.

</td>
</tr>
</table>
 


## -returns



None




## -remarks



Before the state of the PnP property that <b>SetPnpState</b> set can take effect, the driver must call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfdevice-commitpnpstate">IWDFDevice::CommitPnpState</a> method.


#### Examples

The following code example shows how to indicate that a device failed as the result of a request.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
CUmdfHidDevice::OnCompletion(
    __in IWDFIoRequest* WdfRequest,
    __in IWDFIoTarget* /* WdfTarget */,
    __in IWDFRequestCompletionParams* WdfCompletionParams,
    __in PVOID /* Context */
    )
{
    ULONG_PTR bytesRead;

 if (!SUCCEEDED(WdfCompletionParams->GetCompletionStatus()))
    {
        m_WdfDevice->SetPnpState(WdfPnpStateFailed, WdfTrue);
        m_WdfDevice->CommitPnpState();
        return;
    }

    // Lock the device to prevent files from closing.
    m_WdfDevice->AcquireLock();

    // Retrieve the number of bytes that were read.
    bytesRead = WdfCompletionParams->GetInformation();

    // Process the reports.
    ProcessInputReports((PBYTE) m_ReadMemory->GetDataBuffer(NULL), bytesRead);

    m_WdfDevice->ReleaseLock();

    // Release the request.
    m_InterruptReadRequest = NULL;
    WdfRequest->DeleteWdfObject();

    // Send a new request.
    SendInterruptPipeRead();
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfdevice">IWDFDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfdevice-commitpnpstate">IWDFDevice::CommitPnpState</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfdevice-getpnpstate">IWDFDevice::GetPnpState</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi_types/ne-wudfddi_types-_wdf_pnp_state">WDF_PNP_STATE</a>
 

 

