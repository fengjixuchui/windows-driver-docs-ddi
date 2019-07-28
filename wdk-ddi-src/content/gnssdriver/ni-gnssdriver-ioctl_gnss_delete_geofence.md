---
UID: NI:gnssdriver.IOCTL_GNSS_DELETE_GEOFENCE
title: IOCTL_GNSS_DELETE_GEOFENCE (gnssdriver.h)
description: The IOCTL_GNSS_DELETE_GEOFENCE control code is used by the GNSS adapter to delete a previously created geofence.
old-location: gnss\ioctl_gnss_delete_geofence.htm
tech.root: gnss
ms.assetid: BF50E28A-56CF-4718-93BB-CCC3DFE84072
ms.date: 02/15/2018
ms.keywords: IOCTL_GNSS_DELETE_GEOFENCE, IOCTL_GNSS_DELETE_GEOFENCE control, IOCTL_GNSS_DELETE_GEOFENCE control code [Sensor Devices], gnss.ioctl_gnss_delete_geofence, gnssdriver/IOCTL_GNSS_DELETE_GEOFENCE
ms.topic: ioctl
f1_keywords:
 - "gnssdriver/IOCTL_GNSS_DELETE_GEOFENCE"
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
- IOCTL_GNSS_DELETE_GEOFENCE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_GNSS_DELETE_GEOFENCE IOCTL


## -description


The <b>IOCTL_GNSS_DELETE_GEOFENCE</b> control code is used by the GNSS adapter to delete a previously created geofence.


<div class="alert"><b>Note</b>  Applies to GNSS DDI version 2 and later.

</div><div> </div>

## -ioctlparameters




### -input-buffer

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/gnssdriver/ns-gnssdriver-gnss_geofence_delete_param">GNSS_GEOFENCE_DELETE_PARAM</a> structure that defines the geofence to be deleted.




### -input-buffer-length

Set to sizeof(GNSS_GEOFENCE_DELETE_PARAM).




### -output-buffer

Set to <b>NULL</b>.


### -output-buffer-length

Set to 0.


### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code. 


## -remarks



NTSTATUS  with the following indications:

<ul>
<li>
STATUS_SUCCESS: The driver successfully removed the geofence.

</li>
<li>
STATUS_UNSUCCESSFUL: Failed, the geofence cannot be deleted.

</li>
</ul>
<h3><a id="GNSS_adapter_notes"></a><a id="gnss_adapter_notes"></a><a id="GNSS_ADAPTER_NOTES"></a>GNSS adapter notes</h3>
The GNSS adapter does not expect this call to fail because there is no elegant way to handle the consequence of this failure. On failure, the GNSS adapter will issue the <b>GNSS_ResetGeofencesTracking</b> command and re-add the geofences.

<h3><a id="GNSS_driver__notes"></a><a id="gnss_driver__notes"></a><a id="GNSS_DRIVER__NOTES"></a>GNSS driver  notes</h3>
If this is the last geofence, the GNSS driver should stop geofence tracking. If the GNSS engine was unable to track geofences (due to bad signal conditions or other transient errors) prior to the deletion of the last geofence, the monitoring activity should stop.

If the geofence is successfully removed, the driver returns STATUS_SUCCESS. If the geofence cannot be deleted, a failure code,  STATUS_UNSUCCESSFUL, is returned. If a failure occurs, the GNSS adapter issues the GNSS_ResetGeofencesTracking command and recreates the desired geofences. If this command deletes the last defined geofence, the driver stops geofence tracking.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
 

 

