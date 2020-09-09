---
UID: NS:wdm._IO_SESSION_STATE_NOTIFICATION
title: _IO_SESSION_STATE_NOTIFICATION (wdm.h)
description: The IO_SESSION_STATE_NOTIFICATION structure contains information that a kernel-mode driver supplies to the IoRegisterContainerNotification routine when the driver registers to receive notifications of session events.
old-location: kernel\io_session_state_notification.htm
tech.root: kernel
ms.assetid: 19ff9c3a-d416-4468-b5a5-e2e6e896802a
ms.date: 04/30/2018
keywords: ["IO_SESSION_STATE_NOTIFICATION structure"]
ms.keywords: "*PIO_SESSION_STATE_NOTIFICATION, IO_SESSION_STATE_ALL_EVENTS, IO_SESSION_STATE_CONNECT_EVENT, IO_SESSION_STATE_CREATION_EVENT, IO_SESSION_STATE_DISCONNECT_EVENT, IO_SESSION_STATE_LOGOFF_EVENT, IO_SESSION_STATE_LOGON_EVENT, IO_SESSION_STATE_NOTIFICATION, IO_SESSION_STATE_NOTIFICATION structure [Kernel-Mode Driver Architecture], IO_SESSION_STATE_TERMINATION_EVENT, IO_SESSION_STATE_VALID_EVENT_MASK, PIO_SESSION_STATE_NOTIFICATION, PIO_SESSION_STATE_NOTIFICATION structure pointer [Kernel-Mode Driver Architecture], _IO_SESSION_STATE_NOTIFICATION, kernel.io_session_state_notification, kstruct_b_b25d50a3-6254-4eeb-800e-c5fc73c56dfb.xml, wdm/IO_SESSION_STATE_NOTIFICATION, wdm/PIO_SESSION_STATE_NOTIFICATION"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows 7 and later versions of the Windows operating system.
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
req.typenames: IO_SESSION_STATE_NOTIFICATION, *PIO_SESSION_STATE_NOTIFICATION
f1_keywords:
 - _IO_SESSION_STATE_NOTIFICATION
 - wdm/_IO_SESSION_STATE_NOTIFICATION
 - PIO_SESSION_STATE_NOTIFICATION
 - wdm/PIO_SESSION_STATE_NOTIFICATION
 - IO_SESSION_STATE_NOTIFICATION
 - wdm/IO_SESSION_STATE_NOTIFICATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - IO_SESSION_STATE_NOTIFICATION
---

# _IO_SESSION_STATE_NOTIFICATION structure


## -description

The <b>IO_SESSION_STATE_NOTIFICATION</b> structure contains information that a kernel-mode driver supplies to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioregistercontainernotification">IoRegisterContainerNotification</a> routine when the driver registers to receive notifications of session events.

## -struct-fields

### -field Size

The size, in bytes, of the <b>IO_SESSION_STATE_NOTIFICATION</b> structure.

### -field Flags

No flags are currently defined for this member. Set to zero.

### -field IoObject

A pointer to an I/O object owned by the driver. This member can point to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">FILE_OBJECT</a> structure. The I/O object must remain valid for the lifetime of the registration. Before you delete a registered device object, unload a registered driver, or close a registered file object, call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iounregistercontainernotification">IoUnregisterContainerNotification</a> routine to cancel the registration. A driver can maintain simultaneous registrations for more than one I/O object, but it cannot create more than one active registration for the same I/O object.

### -field EventMask

Mask bits for session events. These mask bits indicate the events for which the driver requests notifications.

To register to receive notifications of session events, a kernel-mode driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioregistercontainernotification">IoRegisterContainerNotification</a> routine. To specify the session events for which the driver wants to receive notifications, the driver sets this structure's <b>EventMask</b> member to the bitwise OR of one or more <b>IO_SESSION_STATE_<i>XXX</i></b> constants. 

Set this member to the bitwise OR of one or more of the following <b>IO_SESSION_STATE_<i>XXX</i></b> constants:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="IO_SESSION_STATE_ALL_EVENTS"></a><a id="io_session_state_all_events"></a><dl>
<dt><b>IO_SESSION_STATE_ALL_EVENTS</b></dt>
<dt>0xffffffff</dt>
</dl>
</td>
<td width="60%">
Send notifications of all session events.

</td>
</tr>
<tr>
<td width="40%"><a id="IO_SESSION_STATE_CREATION_EVENT"></a><a id="io_session_state_creation_event"></a><dl>
<dt><b>IO_SESSION_STATE_CREATION_EVENT</b></dt>
<dt>0x00000001</dt>
</dl>
</td>
<td width="60%">
Send a notification when the user session is created.

</td>
</tr>
<tr>
<td width="40%"><a id="IO_SESSION_STATE_TERMINATION_EVENT"></a><a id="io_session_state_termination_event"></a><dl>
<dt><b>IO_SESSION_STATE_TERMINATION_EVENT</b></dt>
<dt>0x00000002</dt>
</dl>
</td>
<td width="60%">
Send a notification when the user session ends.

</td>
</tr>
<tr>
<td width="40%"><a id="IO_SESSION_STATE_CONNECT_EVENT"></a><a id="io_session_state_connect_event"></a><dl>
<dt><b>IO_SESSION_STATE_CONNECT_EVENT</b></dt>
<dt>0x00000004</dt>
</dl>
</td>
<td width="60%">
Send a notification when the user session is connected.

</td>
</tr>
<tr>
<td width="40%"><a id="IO_SESSION_STATE_DISCONNECT_EVENT"></a><a id="io_session_state_disconnect_event"></a><dl>
<dt><b>IO_SESSION_STATE_DISCONNECT_EVENT</b></dt>
<dt>0x00000008</dt>
</dl>
</td>
<td width="60%">
Send a notification when the user session is disconnected.

</td>
</tr>
<tr>
<td width="40%"><a id="IO_SESSION_STATE_LOGON_EVENT"></a><a id="io_session_state_logon_event"></a><dl>
<dt><b>IO_SESSION_STATE_LOGON_EVENT</b></dt>
<dt>0x00000010</dt>
</dl>
</td>
<td width="60%">
Send a notification when the user logs on to the session.

</td>
</tr>
<tr>
<td width="40%"><a id="IO_SESSION_STATE_LOGOFF_EVENT"></a><a id="io_session_state_logoff_event"></a><dl>
<dt><b>IO_SESSION_STATE_LOGOFF_EVENT</b></dt>
<dt>0x00000020</dt>
</dl>
</td>
<td width="60%">
Send a notification when the user logs off of the session.

</td>
</tr>
<tr>
<td width="40%"><a id="IO_SESSION_STATE_VALID_EVENT_MASK"></a><a id="io_session_state_valid_event_mask"></a><dl>
<dt><b>IO_SESSION_STATE_VALID_EVENT_MASK</b></dt>
<dt>0x0000003f</dt>
</dl>
</td>
<td width="60%">
Send a notification when any type of session event occurs.

</td>
</tr>
</table>

### -field Context

A pointer to a context buffer in which the driver can store its private data for a particular session notification registration. The I/O manager passes this pointer to the driver's notification callback routine (specified by the <b>IoRegisterContainerNotification</b> routine's <i>CallbackFunction</i> parameter). The I/O manager does not try to validate the <i>Context</i> pointer or to access the buffer that it points to. This member can be <b>NULL</b> if the driver does not require a context buffer.

## -remarks

This structure is used by the <b>IoRegisterContainerNotification</b> routine. A driver that calls <b>IoRegisterContainerNotification</b> uses this structure to specify the session event notifications that it is registering for.

A per-session device object represents a device that can be accessed only by a particular user session. If a driver sets the <b>IoObject</b> member to point to a device object that is a per-session device object, <b>IoRegisterContainerNotification</b> registers the driver to receive only notifications of events that occur in the session that is represented by the device object. If <b>IoObject</b> points to a device object that is not a per-session device object, or if <b>IoObject</b> points to an object that is not a device object, <b>IoRegisterContainerNotification</b> registers the driver to receive notifications of events that occur in all sessions on the computer.

To determine whether a device object is a per-session device object, a driver can call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdevicepropertydata">IoGetDevicePropertyData</a> routine to query the <a href="https://docs.microsoft.com/windows-hardware/drivers/install/devpkey-device-sessionid">DEVPKEY_Device_SessionId</a> property key in the property store of the device object. If the <b>DEVPKEY_Device_SessionId</b> property exists and the value of the property is set to a nonzero <a href="https://go.microsoft.com/fwlink/p/?linkid=155045">Terminal Services</a> session identifier, the device object is a per-session device object. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/install/devpkey-device-sessionid">DEVPKEY_Device_SessionId</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/install/devpkey-device-sessionid">DEVPKEY_Device_SessionId</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">FILE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdevicepropertydata">IoGetDevicePropertyData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioregistercontainernotification">IoRegisterContainerNotification</a>

