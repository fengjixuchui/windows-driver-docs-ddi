---
UID: NI:gnssdriver.IOCTL_GNSS_STOP_FIXSESSION
title: IOCTL_GNSS_STOP_FIXSESSION (gnssdriver.h)
description: The IOCTL_GNSS_STOP_FIXSESSION control code is used by the GNSS adapter to stop an active fix session.
old-location: gnss\ioctl_gnss_stop_fixsession.htm
tech.root: gnss
ms.assetid: 3A15A61A-8822-4E20-9979-B89BFA092281
ms.date: 02/15/2018
ms.keywords: IOCTL_GNSS_STOP_FIXSESSION, IOCTL_GNSS_STOP_FIXSESSION control, IOCTL_GNSS_STOP_FIXSESSION control code [Sensor Devices], gnss.ioctl_gnss_stop_fixsession, gnssdriver/IOCTL_GNSS_STOP_FIXSESSION
ms.topic: ioctl
f1_keywords:
 - "gnssdriver/IOCTL_GNSS_STOP_FIXSESSION"
req.header: gnssdriver.h
req.include-header: 
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- gnssdriver.h
api_name:
- IOCTL_GNSS_STOP_FIXSESSION
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_GNSS_STOP_FIXSESSION IOCTL


## -description


The <b>IOCTL_GNSS_STOP_FIXSESSION</b> control code is used by the GNSS adapter to stop an active fix session.


## -ioctlparameters




### -input-buffer

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/gnssdriver/ns-gnssdriver-gnss_stopfixsession_param">GNSS_STOPFIXSESSION_PARAM</a> structure.


### -input-buffer-length

Set to sizeof(GNSS_STOPFIXSESSION_PARAM).


### -output-buffer

Set to NULL.


### -output-buffer-length

Set to 0.


### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code. 


## -remarks



The driver sets an NTSTATUS value to indicate one of the following results.

<ul>
<li>
The fix session successfully stopped.

</li>
<li>
The fix session is already stopped or is not active.

</li>
</ul>
<h3><a id="GNSS_adapter_notes"></a><a id="gnss_adapter_notes"></a><a id="GNSS_ADAPTER_NOTES"></a>GNSS adapter notes</h3>
The GNSS adapter always issues a stop fix for every successful start fix. If multi-session support is not present, the GNSS adapter stops any active fix session of the same type before issuing a new start fix request.

<h3><a id="GNSS_driver_notes"></a><a id="gnss_driver_notes"></a><a id="GNSS_DRIVER_NOTES"></a>GNSS driver notes</h3>
The GNSS driver must cancel/stop all pending fix requests and then complete the I/O so that when this call returns, the adapter does not receive any fix data pertaining to the stopped session.

If no other fix sessions are active, the GNSS driver should keep the GNSS engine in a cold state.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
 

 

