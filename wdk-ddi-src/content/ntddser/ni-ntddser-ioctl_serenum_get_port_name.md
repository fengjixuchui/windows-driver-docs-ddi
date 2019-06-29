---
UID: NI:ntddser.IOCTL_SERENUM_GET_PORT_NAME
title: IOCTL_SERENUM_GET_PORT_NAME (ntddser.h)
description: The IOCTL_SERENUM_GET_PORT_NAME request returns the value of the PortName (or Identifier) entry value for the RS-232 port -- see Registry Settings for a Plug and Play Serial Device.
old-location: serports\ioctl_serenum_get_port_name.htm
tech.root: serports
ms.assetid: c61bc594-91be-418f-9e40-ebe99e31304f
ms.date: 04/23/2018
ms.keywords: IOCTL_SERENUM_GET_PORT_NAME, IOCTL_SERENUM_GET_PORT_NAME control, IOCTL_SERENUM_GET_PORT_NAME control code [Serial Ports], ntddser/IOCTL_SERENUM_GET_PORT_NAME, senumref_448bb4bf-eda4-4fbc-abb6-5f470d07861e.xml, serports.ioctl_serenum_get_port_name
ms.topic: ioctl
req.header: ntddser.h
req.include-header: Ntddser.h
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
- ntddser.h
api_name:
- IOCTL_SERENUM_GET_PORT_NAME
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SERENUM_GET_PORT_NAME IOCTL


## -description



The IOCTL_SERENUM_GET_PORT_NAME request returns the value of the <b>PortName</b> (or <b>Identifier</b>) entry value for the RS-232 port -- see <a href="https://docs.microsoft.com/previous-versions/ff546972(v=vs.85)">Registry Settings for a Plug and Play Serial Device</a>.




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a client-allocated buffer that Serenum uses to output the port name. The port name is a null-terminated Unicode string.


### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is set to the size in bytes of a client-allocated output buffer.


### -in-out-buffer








### -inout-buffer-length








### -status-block

If the request is successful, the <b>Information</b> member is set to the size in bytes of the null-terminated Unicode string that is returned in the client's output buffer.

The <b>Status</b> member is set to one of the following values:




#### -STATUS_BUFFER_TOO_SMALL

The output buffer is too small to hold the port name string.


#### -STATUS_SUCCESS

The request completed successfully.


#### -STATUS_UNSUCCESSFUL

An error occurred when opening the registry key for the device or reading the <b>PortName</b> (or <b>Identifier)</b> entry value.

