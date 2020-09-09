---
UID: NI:gnssdriver.IOCTL_GNSS_LISTEN_ERROR
title: IOCTL_GNSS_LISTEN_ERROR (gnssdriver.h)
description: The IOCTL_GNSS_LISTEN_ERROR control code is used to start listening for ERROR events from the driver.
old-location: gnss\ioctl_gnss_listen_error_.htm
tech.root: gnss
ms.assetid: 4B08FB8D-8C4A-4C23-A809-11E7DF190236
ms.date: 02/15/2018
keywords: ["IOCTL_GNSS_LISTEN_ERROR IOCTL"]
ms.keywords: IOCTL_GNSS_LISTEN_ERROR, IOCTL_GNSS_LISTEN_ERROR control, IOCTL_GNSS_LISTEN_ERROR control code [Sensor Devices], gnss.ioctl_gnss_listen_error_, gnssdriver/IOCTL_GNSS_LISTEN_ERROR
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_GNSS_LISTEN_ERROR
 - gnssdriver/IOCTL_GNSS_LISTEN_ERROR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - IOCTL_GNSS_LISTEN_ERROR
---

# IOCTL_GNSS_LISTEN_ERROR IOCTL


## -description

The <b>IOCTL_GNSS_LISTEN_ERROR</b>
   control code is used to start listening for ERROR events from the driver.

## -ioctlparameters

### -input-buffer

Set to NULL.

### -input-buffer-length

Set to 0.

### -output-buffer

A pointer to a [GNSS_EVENT](https://docs.microsoft.com/windows-hardware/drivers/ddi/gnssdriver/ns-gnssdriver-gnss_event) structure.

The EventType must be set to GNSS_Event_Error and the ErrorCode, IsRecoverable and ErrorDescription members of ErrorInformation filled in.

### -output-buffer-length

Set to 0.

### -in-out-buffer

### -inout-buffer-length

### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NTSTATUS</a> code.

## -remarks

<h3><a id="GNSS_adapter_notes"></a><a id="gnss_adapter_notes"></a><a id="GNSS_ADAPTER_NOTES"></a>GNSS adapter notes</h3>
The GNSS adapter ensures that this request is always pending, so that the driver can indicate an error.



When the driver completes the I/O call, the adapter issues another IOCTL to continue waiting for further error notifications.

<h3><a id="GNSS_driver_notes"></a><a id="gnss_driver_notes"></a><a id="GNSS_DRIVER_NOTES"></a>GNSS driver notes</h3>
The driver can complete this call when it wants to report an error condition. The GNSS adapter will use the error data to log telemetry events.



The Error code is in HRESULT format. The driver can create codes using the <b>MAKE_HRESULT</b> macro with codes in <b>FACILITY_ITF</b>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>

