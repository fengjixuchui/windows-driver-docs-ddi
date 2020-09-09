---
UID: NS:acpiioct._ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1_EX
title: _ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1_EX (acpiioct.h)
description: The ACPI_EVAL_INPUT_BUFFER_COMPLEX_EX structure is used as input to an IOCTL_ACPI_EVAL_METHOD_EX request and to an IOCTL_ACPI_ASYNC_EVAL_METHOD_EX request.
old-location: acpi\acpi_eval_input_buffer_complex_ex.htm
tech.root: acpi
ms.assetid: 6053f535-da9c-4f9d-885f-01f29cabd9ee
ms.date: 02/15/2018
keywords: ["ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1_EX structure"]
ms.keywords: "*PACPI_EVAL_INPUT_BUFFER_COMPLEX_EX, *PACPI_EVAL_INPUT_BUFFER_COMPLEX_V1_EX, ACPI_EVAL_INPUT_BUFFER_COMPLEX_EX, ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1_EX, ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1_EX structure [ACPI Devices], PACPI_EVAL_INPUT_BUFFER_COMPLEX_V1_EX, PACPI_EVAL_INPUT_BUFFER_COMPLEX_V1_EX structure pointer [ACPI Devices], _ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1_EX, acpi-meth-eval-ref_d66cba5a-75fb-4127-9f7f-d0ecf08c4b6e.xml, acpi.acpi_eval_input_buffer_complex_ex, acpiioct/ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1_EX, acpiioct/PACPI_EVAL_INPUT_BUFFER_COMPLEX_V1_EX"
req.header: acpiioct.h
req.include-header: Acpiioct.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista and later versions of Windows.
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
req.typenames: ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1_EX, *PACPI_EVAL_INPUT_BUFFER_COMPLEX_V1_EX, ACPI_EVAL_INPUT_BUFFER_COMPLEX_EX, *PACPI_EVAL_INPUT_BUFFER_COMPLEX_EX
f1_keywords:
 - _ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1_EX
 - acpiioct/_ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1_EX
 - PACPI_EVAL_INPUT_BUFFER_COMPLEX_V1_EX
 - acpiioct/PACPI_EVAL_INPUT_BUFFER_COMPLEX_V1_EX
 - ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1_EX
 - acpiioct/ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1_EX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Acpiioct.h
api_name:
 - ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1_EX
---

# _ACPI_EVAL_INPUT_BUFFER_COMPLEX_V1_EX structure


## -description

The ACPI_EVAL_INPUT_BUFFER_COMPLEX_EX structure is used as input to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ni-acpiioct-ioctl_acpi_eval_method_ex">IOCTL_ACPI_EVAL_METHOD_EX</a> request and to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ni-acpiioct-ioctl_acpi_async_eval_method_ex">IOCTL_ACPI_ASYNC_EVAL_METHOD_EX</a> request. The structure supplies the path and name of a control method in an ACPI namespace and an input argument array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ns-acpiioct-_acpi_method_argument_v1">ACPI_METHOD_ARGUMENT</a> structures.

## -struct-fields

### -field Signature

The signature of an extended complex input buffer, which must be set to ACPI_EVAL_INPUT_BUFFER_COMPLEX_SIGNATURE_EX.

### -field MethodName

A NULL-terminated ASCII string that contains the path and name of a control method in an ACPI namespace. The maximum number of characters that the string can contain, including a NULL terminator, is 256. 

For more information about how to supply the path and name of a control method, see the Remarks section later in this topic.

### -field Size

The number of bytes that the <b>Argument</b> array contains.

### -field ArgumentCount

The number of variable-length ACPI_METHOD_ARGUMENT structures that the <b>Argument</b> array contains. The <b>Argument</b> array can hold a maximum of seven argument structures.

### -field Argument

An array of ACPI_METHOD_ARGUMENT structures.

## -remarks

A driver for a device can use an IOCTL_ACPI_EVAL_METHOD_EX request or an IOCTL_ACPI_ASYNC_EVAL_METHOD_EX request to evaluate a control method that is a descendant child object of the device. If the method takes a complex array of arguments, these requests take an input ACPI_EVAL_INPUT_BUFFER_COMPLEX_EX structure as follows:

<ul>
<li>
Set <b>Signature</b> to ACPI_EVAL_INPUT_BUFFER_COMPLEX_SIGNATURE_EX.

</li>
<li>
Set <b>MethodName</b> to a NULL-terminated string that supplies either the full path and name to a control method in the ACPI namespace or the path and name of the method relative to the device to which the evaluation request is sent. 

For example, assume that a request is sent to a device named 'ABCD,' which is an immediate child of the root of an ACPI namespace, that 'ABCD' device supports a child device named 'CHLD,' and that the 'CHLD' device supports a method named '_FOO.' In this case, the evaluation request can supply either '\ABCD.CHLD._FOO,' which is the fully qualified path and name of the control method in the ACPI namespace, or 'CHLD._FOO,' which is the path and name of the control method that is relative to the 'ABCD' device in the ACPI namespace. 

For more information about how to obtain the fully qualified path and name of a control method in an ACPI namespace, see <a href="https://docs.microsoft.com/windows-hardware/drivers/acpi/enumerating-child-devices-and-control-methods">Enumerating Child Devices and Control Methods</a>.

</li>
<li>
<b>Size</b> is set to the number of bytes in the <b>Argument</b> array. 

</li>
<li>
<b>ArgumentCount</b> is set to the number of arguments in the <b>Argument</b> array.

</li>
<li>
<b>Argument</b> is set to an array of ACPI_METHOD_ARGUMENT structures.

</li>
</ul>
For more information about how to use this structure, see <a href="https://docs.microsoft.com/windows-hardware/drivers/acpi/evaluating-acpi-control-methods">Evaluating ACPI Control Methods</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ns-acpiioct-_acpi_method_argument_v1">ACPI_METHOD_ARGUMENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ni-acpiioct-ioctl_acpi_async_eval_method_ex">IOCTL_ACPI_ASYNC_EVAL_METHOD_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/acpiioct/ni-acpiioct-ioctl_acpi_eval_method_ex">IOCTL_ACPI_EVAL_METHOD_EX</a>

