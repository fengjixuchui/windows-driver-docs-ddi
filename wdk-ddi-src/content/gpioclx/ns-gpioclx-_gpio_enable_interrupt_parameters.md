---
UID: NS:gpioclx._GPIO_ENABLE_INTERRUPT_PARAMETERS
title: _GPIO_ENABLE_INTERRUPT_PARAMETERS (gpioclx.h)
description: The GPIO_ENABLE_INTERRUPT_PARAMETERS structure specifies a general-purpose I/O (GPIO) pin and describes the interrupt attributes of this pin.
old-location: gpio\gpio_enable_interrupt_parameters.htm
tech.root: GPIO
ms.assetid: 9F9AA4C1-A202-4AF8-8E1D-F7E56C08A2C1
ms.date: 02/15/2018
ms.keywords: "*PGPIO_ENABLE_INTERRUPT_PARAMETERS, GPIO.gpio_enable_interrupt_parameters, GPIO_ENABLE_INTERRUPT_PARAMETERS, GPIO_ENABLE_INTERRUPT_PARAMETERS structure [Parallel Ports], PGPIO_ENABLE_INTERRUPT_PARAMETERS, PGPIO_ENABLE_INTERRUPT_PARAMETERS structure pointer [Parallel Ports], _GPIO_ENABLE_INTERRUPT_PARAMETERS, gpioclx/GPIO_ENABLE_INTERRUPT_PARAMETERS, gpioclx/PGPIO_ENABLE_INTERRUPT_PARAMETERS"
ms.topic: struct
f1_keywords:
 - "gpioclx/GPIO_ENABLE_INTERRUPT_PARAMETERS"
req.header: gpioclx.h
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
- Gpioclx.h
api_name:
- GPIO_ENABLE_INTERRUPT_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: GPIO_ENABLE_INTERRUPT_PARAMETERS, *PGPIO_ENABLE_INTERRUPT_PARAMETERS
---

# _GPIO_ENABLE_INTERRUPT_PARAMETERS structure


## -description


The <b>GPIO_ENABLE_INTERRUPT_PARAMETERS</b> structure specifies a general-purpose I/O (GPIO) pin and describes the interrupt attributes of this pin.


## -struct-fields




### -field BankId

The identifier for the bank that contains the GPIO pin. If M is the number of banks in the GPIO controller, <b>BankId</b> is an integer in the range 0 to M–1. The GPIO framework extension (GpioClx) previously obtained the number of banks in the controller from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/gpioclx/nc-gpioclx-gpio_client_query_controller_basic_information">CLIENT_QueryControllerBasicInformation</a> event callback function. For more information, see Remarks in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/gpioclx/ns-gpioclx-_client_controller_basic_information">CLIENT_CONTROLLER_BASIC_INFORMATION</a>.


### -field PinNumber

The bank-relative pin number. If N is the number pins in this bank, <i>PinNumber</i> is an integer in the range 0 to N–1. GpioClx previously obtained the number of pins in each bank from the <i>CLIENT_QueryControllerBasicInformation</i> event callback function. For more information, see the description of the <b>NumberOfPinsPerBank</b> member in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/gpioclx/ns-gpioclx-_client_controller_basic_information">CLIENT_CONTROLLER_BASIC_INFORMATION</a>.


### -field Flags

A set of flags that control the configuration of the GPIO pins. No flags are currently defined for this member.


### -field InterruptMode

Whether the interrupt request from this GPIO pin is level-sensitive or edge-triggered. This member is set to one of the following values:

<ul>
<li><b>LevelSensitive</b></li>
<li><b>Latched</b></li>
</ul>
For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_kinterrupt_mode">KINTERRUPT_MODE</a>.


### -field Polarity

Whether the interrupt line from this GPIO pin is active-high or active-low. This member is set to one of the following values:

<ul>
<li><b>InterruptActiveHigh</b></li>
<li><b>InterruptRisingEdge</b></li>
<li><b>InterruptActiveLow</b></li>
<li><b>InterruptFallingEdge</b></li>
<li><b>InterruptActiveBoth</b></li>
</ul>
For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_kinterrupt_polarity">KINTERRUPT_POLARITY</a>.


### -field PullConfiguration

Whether this GPIO pin is pulled up or pulled down. This member is typically set to one of the following system-defined constants:

<ul>
<li><b>GPIO_PIN_PULL_CONFIGURATION_PULLDEFAULT</b></li>
<li><b>GPIO_PIN_PULL_CONFIGURATION_PULLUP</b></li>
<li><b>GPIO_PIN_PULL_CONFIGURATION_PULLDOWN</b></li>
<li><b>GPIO_PIN_PULL_CONFIGURATION_PULLNONE</b></li>
</ul>
If none of these constants appropriately describes the pin configuration, this member can be set to a vendor-defined constant in the range 128-255. For more information about these constants, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/gpioclx/ns-gpioclx-_gpio_enable_interrupt_parameters">GPIO_PIN_PULL_CONFIGURATION</a>.


### -field DebounceTimeout

The debounce time in units of 10 microseconds. For example, a debounce time of 5.84 milliseconds is specified as 584. The debounce time is the time required for an input signal to stabilize at a high level after the start of a low-to-high transition, or at a low level after the start of a high-to-low transition. For example, if an interrupt signal is generated by a mechanical switch, the debounce time is the time required for the metal contact in the switch to stop bouncing after the switch is turned on or off.


### -field VendorData

A pointer to a caller-allocated buffer that contains vendor-defined data for this GPIO pin. This member is optional and is set to NULL if no vendor-defined data is available. For more information about vendor-defined data, see the description of the <i>GPIO connection descriptor</i> in the [ACPI 5.0 specification](https://uefi.org/specifications).


### -field VendorDataLength

The size, in bytes, of the data buffer that is pointed to by the <b>VendorData</b> member.


## -remarks



The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/gpioclx/nc-gpioclx-gpio_client_enable_interrupt">CLIENT_EnableInterrupt</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/gpioclx/nc-gpioclx-gpio_client_unmask_interrupt">CLIENT_UnmaskInterrupt</a> event callback functions use a <b>GPIO_ENABLE_INTERRUPT_PARAMETERS</b> structure to specify a GPIO pin and to describe the interrupt attributes of this pin.


    The <b>GPIO_PIN_PULL_CONFIGURATION_<i>XXX</i></b> constants specify whether a general-purpose I/O (GPIO) pin is pulled up or pulled down.
   


<pre class="syntax">#define GPIO_PIN_PULL_CONFIGURATION_DEFAULT (0x0)
#define GPIO_PIN_PULL_CONFIGURATION_PULLUP (0x1)
#define GPIO_PIN_PULL_CONFIGURATION_PULLDOWN (0x2)
#define GPIO_PIN_PULL_CONFIGURATION_NONE (0x3)</pre>




The <b>PullConfiguration</b> member of the <b>GPIO_ENABLE_INTERRUPT_PARAMETERS</b> structure is set to a <b>GPIO_PIN_PULL_CONFIGURATION_<i>XXX</i></b> constant.

If none of the system-defined <b>GPIO_PIN_PULL_CONFIGURATION_<i>XXX</i></b> constants appropriately describes the pin configuration, this member can be set to a vendor-defined constant in the range 128 to 255.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/gpioclx/ns-gpioclx-_client_controller_basic_information">CLIENT_CONTROLLER_BASIC_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/gpioclx/nc-gpioclx-gpio_client_enable_interrupt">CLIENT_EnableInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/gpioclx/nc-gpioclx-gpio_client_query_controller_basic_information">CLIENT_QueryControllerBasicInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/gpioclx/nc-gpioclx-gpio_client_unmask_interrupt">CLIENT_UnmaskInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_kinterrupt_mode">KINTERRUPT_MODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_kinterrupt_polarity">KINTERRUPT_POLARITY</a>
 

 

