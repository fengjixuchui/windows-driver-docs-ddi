---
UID: NF:oprghdlr.RegisterOpRegionHandler
title: RegisterOpRegionHandler function (oprghdlr.h)
description: The RegisterOpRegionHandler routine registers an operation region handler with the ACPI driver.
old-location: acpi\registeropregionhandler.htm
tech.root: acpi
ms.assetid: 5795a1d1-0e13-4f9f-b2f2-37bbd71bde7a
ms.date: 02/15/2018
keywords: ["RegisterOpRegionHandler function"]
ms.keywords: RegisterOpRegionHandler, RegisterOpRegionHandler routine [ACPI Devices], acpi.registeropregionhandler, opregref_9742e50b-613d-4191-b0a2-6d1b0f365494.xml, oprghdlr/RegisterOpRegionHandler
req.header: oprghdlr.h
req.include-header: Oprghdlr.h
req.target-type: Universal
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
req.lib: Oprghdlr.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RegisterOpRegionHandler
 - oprghdlr/RegisterOpRegionHandler
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Oprghdlr.lib
 - Oprghdlr.dll
api_name:
 - RegisterOpRegionHandler
---

# RegisterOpRegionHandler function


## -description

The <b>RegisterOpRegionHandler</b> routine registers an operation region handler with the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/acpi-driver">ACPI driver</a>.

## -parameters

### -param DeviceObject 

[in]
Pointer to the physical device object (<a href="https://docs.microsoft.com/windows-hardware/drivers/">PDO</a>) that represents the ACPI device that defines the operation region.

### -param AccessType 

[in]
Specifies ACPI_OPREGION_ACCESS_AS_COOKED.

### -param RegionSpace 

[in]
Specifies one of the following types of region space.

<table>
<tr>
<th>Region Space Identifier</th>
<th>Description</th>
</tr>
<tr>
<td>
ACPI_OPREGION_REGION_SPACE_MEMORY

</td>
<td>
System memory

</td>
</tr>
<tr>
<td>
ACPI_OPREGION_REGION_SPACE_IO

</td>
<td>
I/O space

</td>
</tr>
<tr>
<td>
ACPI_OPREGION_REGION_SPACE_PCI_CONFIG

</td>
<td>
PCI configuration

</td>
</tr>
<tr>
<td>
ACPI_OPREGION_REGION_SPACE_EC

</td>
<td>
Embedded controller

</td>
</tr>
<tr>
<td>
ACPI_OPREGION_REGION_SPACE_SMB

</td>
<td>
System Management Bus

</td>
</tr>
<tr>
<td>
ACPI_OPREGION_REGION_SPACE_CMOS_CONFIG

</td>
<td>
CMOS configuration

</td>
</tr>
<tr>
<td>
ACPI_OPREGION_REGION_SPACE_PCIBARTARGET

</td>
<td>
PCI Base Address Register

</td>
</tr>
<tr>
<td>
Vendor-defined value from 0x80 to 0xFF

</td>
<td>
Vendor-defined

</td>
</tr>
</table>

### -param Handler 

[in]
Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/oprghdlr/nc-oprghdlr-acpi_op_region_handler">ACPI_OP_REGION_HANDLER</a>-typed operation region handler (supplied by an ACPI device function driver).

### -param Context 

[in]
Pointer to a device-specific operation region context (supplied by an ACPI device function driver).

### -param Flags 

[in]
Reserved for internal use.

### -param OperationRegionObject 

[out]
Pointer to caller-allocated buffer that, on output, contains a pointer to the operation region object that the ACPI driver creates for the operation region.

## -returns

Returns one of the following status values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operating region handler was successfully registered.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACPI_INVALID_DATA</b></dt>
</dl>
</td>
<td width="60%">
The specified information is not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The routine could not allocate the necessary system resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_Xxx</b></dt>
</dl>
</td>
<td width="60%">
An internal error occurred.

</td>
</tr>
</table>

## -remarks

The operation region context specified by <i>Context</i> is device-specific and is only used by the function driver. Typically, the context is the device extension for the functional device object (<a href="https://docs.microsoft.com/windows-hardware/drivers/">FDO</a>). The ACPI driver passes this context back to the function driver when it calls the operation region handler. The operation region object is only used by a function driver to uniquely identify the operation region when it deregisters the operation region handler.

For more information about operation regions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/acpi/supporting-an-operation-region">Supporting an Operation Region</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/oprghdlr/nc-oprghdlr-acpi_op_region_handler">ACPI_OP_REGION_HANDLER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/oprghdlr/nf-oprghdlr-deregisteropregionhandler">DeRegisterOpRegionHandler</a>

