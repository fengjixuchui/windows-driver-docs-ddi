---
UID: NI:gpio.IOCTL_GPIO_READ_PINS
title: IOCTL_GPIO_READ_PINS (gpio.h)
description: The IOCTL_GPIO_READ_PINS I/O control code enables a client of the general-purpose I/O (GPIO) controller to read from a set of GPIO pins that are configured as inputs.
old-location: gpio\ioctl_gpio_read_pins.htm
tech.root: GPIO
ms.assetid: A6911DD2-0524-4E83-A42E-6E3E7107A928
ms.date: 02/15/2018
keywords: ["IOCTL_GPIO_READ_PINS IOCTL"]
ms.keywords: GPIO.ioctl_gpio_read_pins, IOCTL_GPIO_READ_PINS, IOCTL_GPIO_READ_PINS control, IOCTL_GPIO_READ_PINS control code [Parallel Ports], gpio/IOCTL_GPIO_READ_PINS
f1_keywords:
 - "gpio/IOCTL_GPIO_READ_PINS"
req.header: gpio.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Gpio.h
api_name:
- IOCTL_GPIO_READ_PINS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_GPIO_READ_PINS IOCTL


## -description


The <b>IOCTL_GPIO_READ_PINS</b> I/O control code enables a client of the general-purpose I/O (GPIO) controller to read from a set of GPIO pins that are configured as inputs. Typically, the clients of a GPIO controller are drivers for peripheral devices that connect to GPIO pins.


## -ioctlparameters




### -input-buffer

No input buffer.


### -input-buffer-length

None.


### -output-buffer

The output buffer.


### -output-buffer-length

The output buffer should be large enough to contain readings from all of the GPIO pins that are part of the target connection to which the client sends the request. For example, if the GPIO controller hardware implements 64 GPIO pins, and the client opens a connection to three of these GPIO pins, a one-byte buffer is sufficiently large to contain the three 1-bit values that are read from the three pins in the connection.


### -in-out-buffer








### -inout-buffer-length








### -status-block

If the operation is successful, the GPIO controller driver sets the <b>Status</b> member to STATUS_SUCCESS, and sets the <b>Information</b> member to the total number of bytes transferred during the requested operation. If the operation transfers N bits, the number of bytes transferred is (N + 7) / 8. (That is, 7 is added to N to round up to the next byte boundary before the integer division by 8.)

If this request fails, the <b>Status</b> member is set to an error code and no data is read from the GPIO pins. The requested operation might fail for various reasons, which can include invalid client input, low resources, and device malfunction.

If the output buffer is not large enough to contain the data that is read from all of the GPIO pins in the target connection, the <b>Status</b> member is set to STATUS_BUFFER_TOO_SMALL. If the GPIO pins in the target connection are configured as outputs, the <b>Status</b> member is set to STATUS_GPIO_OPERATION_DENIED.


## -remarks



This request reads all of the GPIO pins that are part of the target connection to which the client sends the request. For example, if the connection has three pins, the 1-bit values that are read from these pins are saved in bits 0, 1, and 2 in the output buffer. The three pins in this example connection might map to GPIO pins 7, 8, and 23 in the GPIO controller hardware. If so, GPIO pin 7 is saved in bit 0 (the least significant bit) of the buffer, GPIO pin 8 is saved in bit 1 of the buffer, and GPIO pin 23 is saved in bit 2 of the buffer.

When the client opens a connection to a target GPIO device, all of the GPIO pins in this connection are configured either as inputs or as outputs. An <b>IOCTL_GPIO_READ_PINS</b> request can succeed only if the target pins are inputs.

 The client sends this I/O control request to the file object for the target device. The file object is a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">FILE_OBJECT</a> structure that represents a logical connection to the target. <a href="https://docs.microsoft.com/previous-versions/windows/hardware/download/dn550976(v=vs.85)">Kernel-mode driver framework</a> (KMDF) drivers call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetcreate">WdfIoTargetCreate</a> method to open this connection. <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/overview-of-the-umdf">User-mode driver framework</a> (UMDF) drivers call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfremotetarget-openfilebyname">IWDFRemoteTarget::OpenFileByName</a> method to open the connection.

For code examples that show how to use the <b>IOCTL_GPIO_READ_PINS</b> request to read a set of GPIO I/O pins, see the following topics:

<a href="https://docs.microsoft.com/windows-hardware/drivers/gpio/connecting-a-kmdf-driver-to-gpio-i-o-pins">Connecting a KMDF Driver to GPIO I/O Pins</a>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">FILE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfremotetarget-openfilebyname">IWDFRemoteTarget::OpenFileByName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetcreate">WdfIoTargetCreate</a>
 

 

