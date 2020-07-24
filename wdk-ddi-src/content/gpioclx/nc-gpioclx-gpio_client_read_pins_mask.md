---
UID: NC:gpioclx.GPIO_CLIENT_READ_PINS_MASK
title: GPIO_CLIENT_READ_PINS_MASK (gpioclx.h)
description: The CLIENT_ReadGpioPinsUsingMask event callback function reads a bank of general-purpose I/O (GPIO) pins.
old-location: gpio\client_readgpiopinsusingmask.htm
tech.root: GPIO
ms.assetid: EFF7C3D8-9E52-446A-BF55-0308A0D2835E
ms.date: 02/15/2018
keywords: ["GPIO_CLIENT_READ_PINS_MASK callback function"]
ms.keywords: CLIENT_ReadGpioPinsUsingMask, CLIENT_ReadGpioPinsUsingMask callback, CLIENT_ReadGpioPinsUsingMask callback function [Parallel Ports], GPIO.client_readgpiopinsusingmask, GPIO_CLIENT_READ_PINS_MASK, gpioclx/CLIENT_ReadGpioPinsUsingMask
f1_keywords:
 - "gpioclx/CLIENT_ReadGpioPinsUsingMask"
 - "CLIENT_ReadGpioPinsUsingMask"
req.header: gpioclx.h
req.include-header: 
req.target-type: Desktop
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
req.irql: See Remarks.
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Gpioclx.h
api_name:
- CLIENT_ReadGpioPinsUsingMask
targetos: Windows
req.typenames: 
---

# GPIO_CLIENT_READ_PINS_MASK callback function


## -description


The <i>CLIENT_ReadGpioPinsUsingMask</i> event callback function reads a bank of general-purpose I/O (GPIO) pins.


## -parameters




### -param Context [in]

A pointer to the GPIO controller driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/gpio/gpio-device-contexts">device context</a>.


### -param ReadParameters [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_read_pins_mask_parameters">GPIO_READ_PINS_MASK_PARAMETERS</a> structure that, on entry, describes the GPIO pins to read, and, on exit, contains the data read from the GPIO pins.


## -returns



The <i>CLIENT_ReadGpioPinsUsingMask</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error code.




## -remarks



This callback function is implemented by the GPIO controller driver. The GpioClx calls this function.

The <i>CLIENT_ReadGpioPinsUsingMask</i> callback function reads the values of all of the GPIO pins in a bank of pins. The function stores these values in the <b>PinValues</b> member of the <b>GPIO_READ_PINS_MASK_PARAMETERS</b> structure. Bit 0 (the least significant bit) of this member contains the value of pin 0, bit 1 contains the value of pin 1, and so on.

To register your driver's <i>CLIENT_ReadGpioPinsUsingMask</i> callback function, call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nf-gpioclx-gpio_clx_registerclient">GPIO_CLX_RegisterClient</a> method. This method accepts, as an input parameter, a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_client_registration_packet">GPIO_CLIENT_REGISTRATION_PACKET</a> structure that contains a <i>CLIENT_ReadGpioPinsUsingMask</i> function pointer.

The <i>CLIENT_ReadGpioPinsUsingMask</i> function can be called from the interrupt service routine (ISR) in GpioClx. This ISR runs either at PASSIVE_LEVEL or DIRQL, depending on the device information that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_query_controller_basic_information">CLIENT_QueryControllerBasicInformation</a> callback function supplies to GpioClx. The <i>CLIENT_QueryControllerBasicInformation</i> function provides device information in the form of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_client_controller_basic_information">CLIENT_CONTROLLER_BASIC_INFORMATION</a> structure. If the <b>MemoryMappedController</b> flag bit is set in the <b>Flags</b> member of this structure, the GpioClx ISR runs at DIRQL and calls the <i>CLIENT_ReadGpioPinsUsingMask</i> function at DIRQL. Otherwise, the ISR runs at PASSIVE_LEVEL and calls the function at PASSIVE_LEVEL. For more information about this flag bit, see <a href="https://docs.microsoft.com/windows-hardware/drivers/gpio/optional-and-required-gpio-callback-functions">Optional and Required GPIO Callback Functions</a>.


#### Examples

To define a <i>CLIENT_ReadGpioPinsUsingMask</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>CLIENT_ReadGpioPinsUsingMask</i> callback function that is named <code>MyEvtGpioReadGpioPinsUsingMask</code>, use the GPIO_CLIENT_READ_PINS_MASK function type, as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>GPIO_CLIENT_READ_PINS_MASK MyEvtGpioReadPinsUsingMask;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
NTSTATUS
  MyEvtGpioReadPinsUsingMask(
    PVOID Context,
    PGPIO_READ_PINS_MASK_PARAMETERS ReadParameters
    )
{ ... }</pre>
</td>
</tr>
</table></span></div>
The GPIO_CLIENT_READ_PINS_MASK function type is defined in the Gpioclx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the GPIO_CLIENT_READ_PINS_MASK function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_client_controller_basic_information">CLIENT_CONTROLLER_BASIC_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_query_controller_basic_information">CLIENT_QueryControllerBasicInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_client_registration_packet">GPIO_CLIENT_REGISTRATION_PACKET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nf-gpioclx-gpio_clx_registerclient">GPIO_CLX_RegisterClient</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_read_pins_mask_parameters">GPIO_READ_PINS_MASK_PARAMETERS</a>
 

 

