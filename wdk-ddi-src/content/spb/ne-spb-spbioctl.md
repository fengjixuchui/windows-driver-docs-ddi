---
UID: NE:spb.SpbIoctl
title: SpbIoctl (spb.h)
description: Defines values to indicate the type I/O control request.
old-location: spb\spbioctl.htm
tech.root: SPB
ms.assetid: 83260550-B364-4790-BDB5-5C6E5AD76A72
ms.date: 04/30/2018
keywords: ["SpbIoctl enumeration"]
ms.keywords: "*PSpbIoctl, *PSpbIoctl enumeration [Buses], IOCTL_SPB_EXECUTE_SEQUENCE, IOCTL_SPB_FULL_DUPLEX, IOCTL_SPB_LOCK_CONNECTION, IOCTL_SPB_LOCK_CONTROLLER, IOCTL_SPB_UNLOCK_CONNECTION, IOCTL_SPB_UNLOCK_CONTROLLER, SPB.spbioctl, SpbIoctl, SpbIoctl enumeration [Buses], spb/*PSpbIoctl, spb/IOCTL_SPB_EXECUTE_SEQUENCE, spb/IOCTL_SPB_FULL_DUPLEX, spb/IOCTL_SPB_LOCK_CONNECTION, spb/IOCTL_SPB_LOCK_CONTROLLER, spb/IOCTL_SPB_UNLOCK_CONNECTION, spb/IOCTL_SPB_UNLOCK_CONTROLLER, spb/SpbIoctl"
req.header: spb.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
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
req.typenames: SpbIoctl, *PSpbIoctl
f1_keywords:
 - SpbIoctl
 - spb/SpbIoctl
 - PSpbIoctl
 - spb/PSpbIoctl
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Spb.h
api_name:
 - SpbIoctl
---

# SpbIoctl enumeration


## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

Defines values to indicate the type I/O control request.

## -enum-fields

### -field IOCTL_SPB_LOCK_CONTROLLER

The <a href="/windows-hardware/drivers/spb/spb-ioctls">IOCTL_SPB_LOCK_CONTROLLER</a> control code is used by a client (peripheral driver) to lock the SPB controller. While the controller is locked, the client has exclusive use of the bus to access the specified target device for the lock.

### -field IOCTL_SPB_UNLOCK_CONTROLLER

The <a href="/windows-hardware/drivers/spb/spb-ioctls">IOCTL_SPB_UNLOCK_CONTROLLER</a> I/O control code is used by a client (peripheral driver) to unlock the SPB controller. The client previously locked the controller to gain exclusive use of the bus to access a target device on the bus.

### -field IOCTL_SPB_EXECUTE_SEQUENCE

The <a href="/windows-hardware/drivers/spb/spb-ioctls">IOCTL_SPB_EXECUTE_SEQUENCE</a> I/O control code enables a client (peripheral driver) of the SPB controller driver to perform a sequence of transfers (reads and writes) as a single, atomic operation with one I/O request. The designated device on the bus is the target for all transfers in the sequence.

### -field IOCTL_SPB_LOCK_CONNECTION

The <a href="/windows-hardware/drivers/spb/spb-ioctls">IOCTL_SPB_LOCK_CONNECTION</a> control code is used by a client (peripheral driver) to acquire the connection lock on an SPB-connected target device that is shared with another client. While a client holds the connection lock,  this client has exclusive access to the device.

### -field IOCTL_SPB_UNLOCK_CONNECTION

The <a href="/windows-hardware/drivers/spb/spb-ioctls">IOCTL_SPB_UNLOCK_CONNECTION</a> I/O control code is used by a client (peripheral driver) to release the connection lock on an SPB-connected target device that is shared with another client. The client previously sent an <a href="https://msdn.microsoft.com/library/windows/hardware/jj819324">IOCTL_SPB_LOCK_CONNECTION</a> request to acquire exclusive access to the device.

### -field IOCTL_SPB_FULL_DUPLEX

The <a href="/windows-hardware/drivers/spb/spb-ioctls">IOCTL_SPB_FULL_DUPLEX</a> control code is used by a client (peripheral driver) to request a full-duplex I/O operation. Full-duplex I/O operations are supported by controllers for buses such as SPI that can simultaneously read and write data.