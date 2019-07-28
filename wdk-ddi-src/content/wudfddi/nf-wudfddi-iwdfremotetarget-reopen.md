---
UID: NF:wudfddi.IWDFRemoteTarget.Reopen
title: IWDFRemoteTarget::Reopen (wudfddi.h)
description: The Reopen method reopens a remote I/O target after it has been temporarily closed.
old-location: wdf\iwdfremotetarget_reopen.htm
tech.root: wdf
ms.assetid: 904904e7-ca59-4dcb-92db-8c7f6a9cbff7
ms.date: 02/26/2018
ms.keywords: IWDFRemoteTarget interface,Reopen method, IWDFRemoteTarget.Reopen, IWDFRemoteTarget::Reopen, Reopen, Reopen method, Reopen method,IWDFRemoteTarget interface, UMDFIoTargetObjectRef_13b81124-2d7f-4fed-b4f9-1a5cb647a811.xml, umdf.iwdfremotetarget_reopen, wdf.iwdfremotetarget_reopen, wudfddi/IWDFRemoteTarget::Reopen
ms.topic: method
f1_keywords:
 - "wudfddi/IWDFRemoteTarget.Reopen"
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
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
- IWDFRemoteTarget.Reopen
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFRemoteTarget::Reopen


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Reopen</b> method reopens a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/general-i-o-targets-in-umdf">remote I/O target</a> after it has been temporarily closed.


## -parameters






## -returns



<b>Reopen</b> returns S_OK if the operation succeeds. Otherwise, the method might return the following value:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
The framework's attempt to allocate memory failed. 

</td>
</tr>
</table>
 

This method might return one of the other values that Winerror.h contains.



The framework's <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/-verifier">verifier</a> reports an error if the framework cannot open the file.




## -remarks



Typically, a driver calls <b>Reopen</b> from within the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iremotetargetcallbackremoval-onremotetargetremovecanceled">IRemoteTargetCallbackRemoval::OnRemoteTargetRemoveCanceled</a> callback function, but <b>Reopen</b> can instead be called after <b>OnRemoteTargetRemoveCanceled</b> returns. 

Reopen uses the file or interface name that the driver previously specified to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfremotetarget-openfilebyname">IWDFRemoteTarget::OpenFileByName</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfremotetarget-openremoteinterface">IWDFRemoteTarget::OpenRemoteInterface</a>. If you want to change the file or interface that the driver is using, the driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfremotetarget-close">IWDFRemoteTarget::Close</a>, and then it can call <b>OpenFileByName</b> or <b>OpenRemoteInterface</b> instead of <b>Reopen</b>.

For more information about <b>Reopen</b> and how to use remote I/O targets in UMDF-based drivers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/controlling-a-general-i-o-target-s-state-in-umdf">Controlling a General I/O Target's State in UMDF</a>.


#### Examples

The following code example shows an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iremotetargetcallbackremoval-onremotetargetremovecanceled">IRemoteTargetCallbackRemoval::OnRemoteTargetRemoveCanceled</a> callback function that calls <b>Reopen</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID 
STDMETHODCALLTYPE
CMyRemoteTarget::OnRemoteTargetRemoveCanceled(
    __in IWDFRemoteTarget* FxTarget
    )
{
 if (S_OK == (FxTarget->Reopen()))
    {
    //
    // Resume sending I/O requests to the remote target.
    //
    ...
    }
 else
    {
       FxTarget->Close();
    }
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfremotetarget">IWDFRemoteTarget</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfremotetarget-close">IWDFRemoteTarget::Close</a>
 

 

