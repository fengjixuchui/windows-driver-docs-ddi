---
UID: NF:wudfddi.IPowerPolicyCallbackWakeFromS0.OnArmWakeFromS0
title: IPowerPolicyCallbackWakeFromS0::OnArmWakeFromS0 (wudfddi.h)
description: A driver's OnArmWakeFromS0 callback function arms (that is, enables) a device so that it can trigger a wake signal while in a low-power device state, if the system remains in the system working state (S0).
old-location: wdf\ipowerpolicycallbackwakefroms0_onarmwakefroms0.htm
tech.root: wdf
ms.assetid: 4801a7c4-8bd4-4372-bcdd-49e5570d833e
ms.date: 02/26/2018
keywords: ["IPowerPolicyCallbackWakeFromS0::OnArmWakeFromS0"]
ms.keywords: IPowerPolicyCallbackWakeFromS0 interface,OnArmWakeFromS0 method, IPowerPolicyCallbackWakeFromS0.OnArmWakeFromS0, IPowerPolicyCallbackWakeFromS0::OnArmWakeFromS0, OnArmWakeFromS0, OnArmWakeFromS0 method, OnArmWakeFromS0 method,IPowerPolicyCallbackWakeFromS0 interface, UMDFDeviceObjectRef_7b2a2ca8-d8d4-4da2-ae51-15aabf150973.xml, umdf.ipowerpolicycallbackwakefroms0_onarmwakefroms0, wdf.ipowerpolicycallbackwakefroms0_onarmwakefroms0, wudfddi/IPowerPolicyCallbackWakeFromS0::OnArmWakeFromS0
f1_keywords:
 - "wudfddi/IPowerPolicyCallbackWakeFromS0.OnArmWakeFromS0"
 - "IPowerPolicyCallbackWakeFromS0.OnArmWakeFromS0"
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
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Wudfddi.h
api_name:
- IPowerPolicyCallbackWakeFromS0.OnArmWakeFromS0
targetos: Windows
req.typenames: 
---

# IPowerPolicyCallbackWakeFromS0::OnArmWakeFromS0


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver's <b>OnArmWakeFromS0</b> callback function arms (that is, enables) a device so that it can trigger a wake signal while in a low-power device state, if the system remains in the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/system-working-state-s0">system working state</a> (S0). 


## -parameters




### -param pWdfDevice [in]

A pointer to the <b>IWDFDevice</b> interface of the device object that represents one of the driver's devices.


## -returns



If the operation is successful, the <b>OnArmWakeFromS0</b> callback function must return S_OK or another status value for which SUCCEEDED(<i>status</i>) equals <b>TRUE</b>. Otherwise it must return a status value for which SUCCEEDED(<i>status</i>) equals <b>FALSE</b>.

If SUCCEEDED(status) equals <b>FALSE</b>, the framework calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipowerpolicycallbackwakefroms0-ondisarmwakefroms0">IPowerPolicyCallbackWakeFromS0::OnDisarmWakeFromS0</a> callback function. (The framework does not report a device failure to the PnP manager.) 






## -remarks



Your driver must provide an <b>OnArmWakeFromS0</b> callback function if the driver supports the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-ipowerpolicycallbackwakefroms0">IPowerPolicyCallbackWakeFromS0</a> interface. 

The <b>OnArmWakeFromS0</b> callback function handles device-specific operations that are needed to enable the device to detect an external event that triggers a wake signal on the bus. The kernel-mode bus driver handles bus-specific operations, such as enabling the PCI bus's Power Management Event (PME) signal.

If the driver has registered an <b>OnArmWakeFromS0</b> callback function, the framework calls it while the device is still in the D0 device power state, before the bus driver lowers the device's power state but after the framework has sent a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/sending-a-wait-wake-irp">wait/wake IRP</a> on behalf of the driver. 

The process occurs in the following sequence:

<ol>
<li>
The framework determines that the device has been idle for a preset amount of time.

</li>
<li>
The framework calls the driver's <b>OnArmWakeFromS0</b> callback function.

</li>
<li>
The framework requests the driver for the device's bus to lower the device's power.

</li>
</ol>
Immediately before your device enters a low power state, the framework will call your driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallback-ond0exit">IPnpCallback::OnD0Exit</a> callback function.

For more information about when the framework calls this callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/pnp-and-power-management-scenarios-in-umdf">PnP and Power Management Scenarios in UMDF</a>.

You do not need to provide an <b>OnArmWakeFromS0</b> callback function if your device:

<ul>
<li>
Is a USB device that supports "selective suspend."

</li>
<li>
Cannot be powered down while the system remains fully powered.

</li>
<li>
Does not require special hardware operations that enable the device to trigger a wake signal.

</li>
</ul>
If your device supports USB "selective suspend" and if your driver specifies <b>IdleUsbSelectiveSuspend</b> when it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice2-assigns0idlesettings">IWDFDevice2::AssignS0IdleSettings</a>, the framework sends a "selective suspend" request to the USB bus driver when the device has been idle for a preset amount of time.

For more information about this callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-idle-power-down-in-umdf-drivers">Supporting Idle Power-Down in UMDF-based Drivers</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-ipowerpolicycallbackwakefroms0">IPowerPolicyCallbackWakeFromS0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipowerpolicycallbackwakefroms0-ondisarmwakefroms0">IPowerPolicyCallbackWakeFromS0::OnDisarmWakeFromS0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipowerpolicycallbackwakefroms0-onwakefroms0triggered">IPowerPolicyCallbackWakeFromS0::OnWakeFromS0Triggered</a>
 

 

