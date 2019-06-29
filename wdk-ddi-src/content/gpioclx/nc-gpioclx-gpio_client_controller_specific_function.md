---
UID: NC:gpioclx.GPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION
title: GPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION (gpioclx.h)
description: The CLIENT_ControllerSpecificFunction event callback function performs an operation that is specific to a particular general-purpose I/O (GPIO) controller.
old-location: gpio\client_controllerspecificfunction.htm
tech.root: GPIO
ms.assetid: 27551BE5-1260-4F05-9847-97C90ADF7968
ms.date: 02/15/2018
ms.keywords: CLIENT_ControllerSpecificFunction, CLIENT_ControllerSpecificFunction callback, CLIENT_ControllerSpecificFunction callback function [Parallel Ports], GPIO.client_controllerspecificfunction, GPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION, gpioclx/CLIENT_ControllerSpecificFunction
ms.topic: callback
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
req.irql: Called at PASSIVE_LEVEL.
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Gpioclx.h
api_name:
- CLIENT_ControllerSpecificFunction
product:
- Windows
targetos: Windows
req.typenames: 
---

# GPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION callback function


## -description


The <i>CLIENT_ControllerSpecificFunction</i> event callback function performs an operation that is specific to a particular general-purpose I/O (GPIO) controller.


## -parameters




### -param Context [in]

A pointer to the GPIO controller driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/gpio/gpio-device-contexts">device context</a>.


### -param Parameters [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/gpioclx/ns-gpioclx-_gpio_client_controller_specific_function_parameters">GPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION_PARAMETERS</a> structure that contains the input and output buffers for the controller-specific operation.


## -returns



The <i>CLIENT_ControllerSpecificFunction</i> function returns <b>STATUS_SUCCESS</b> if the call is successful. Possible return values include the following error codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The GPIO controller does not support the operation specified by the input parameters.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The size of the input buffer or output buffer is too small.

</td>
</tr>
</table>
 




## -remarks



As an option, a GPIO controller driver can support <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/gpio/ni-gpio-ioctl_gpio_controller_specific_function">IOCTL_GPIO_CONTROLLER_SPECIFIC_FUNCTION</a> requests. This type of I/O control request (IOCTL) performs controller-specific operations for the benefit of peripheral device drivers that require these operations. To support this IOCTL, a GPIO controller driver implements a <i>CLIENT_ControllerSpecificFunction</i> function.

The GPIO framework extension (GpioClx) supports the <i>CLIENT_ControllerSpecificFunction</i> function to address the specific needs of certain hardware platforms. Typical GPIO controller drivers do not implement this function. A peripheral device driver that uses <b>IOCTL_GPIO_CONTROLLER_SPECIFIC_FUNCTION</b> requests to perform a hardware-specific operation on one platform risks the loss of compatibility with other platforms that do not support this operation.

Typically, the <i>CLIENT_ControllerSpecificFunction</i> function programs the GPIO controller to perform a hardware-specific operation on a set of GPIO pins. The input and output parameters for this operation are defined by the developer for the GPIO controller driver. Only a peripheral device driver that is aware of the particular operations implemented by a GPIO controller driver can request these operations.

When GpioClx receives an <b>IOCTL_GPIO_CONTROLLER_SPECIFIC_FUNCTION</b> request, it checks to see whether the GPIO controller driver has implemented a <i>CLIENT_ControllerSpecificFunction</i> function. If so, GpioClx copies the descriptions of the input and output buffers from the IOCTL to a <b>GPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION_PARAMETERS</b> structure and passes a pointer to this structure as a parameter to the <i>CLIENT_ControllerSpecificFunction</i> function. If the parameter values in the <b>GPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION_PARAMETERS</b> structure are valid, the function performs the requested operation and returns STATUS_SUCCESS.

If GpioClx receives an <b>IOCTL_GPIO_CONTROLLER_SPECIFIC_FUNCTION</b> request, and the GPIO controller driver does not implement a <i>CLIENT_ControllerSpecificFunction</i> function, GpioClx completes the IOCTL with error code STATUS_NOT_IMPLEMENTED.


#### Examples

To define a <i>CLIENT_ControllerSpecificFunction</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>CLIENT_ControllerSpecificFunction</i> callback function that is named <code>MyEvtGpioControllerSpecificFunction</code>, use the GPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION function type, as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>GPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION MyEvtGpioControllerSpecificFunction;</pre>
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
  MyEvtGpioControllerSpecificFunction(
    PVOID Context,
    PGPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION_PARAMETERS Parameters
    )
{ ... }</pre>
</td>
</tr>
</table></span></div>
The GPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION function type is defined in the Gpioclx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the GPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/gpioclx/ns-gpioclx-_gpio_client_controller_specific_function_parameters">GPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/gpio/ni-gpio-ioctl_gpio_controller_specific_function">IOCTL_GPIO_CONTROLLER_SPECIFIC_FUNCTION</a>
 

 

