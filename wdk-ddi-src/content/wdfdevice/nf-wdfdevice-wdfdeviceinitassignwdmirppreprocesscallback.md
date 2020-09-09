---
UID: NF:wdfdevice.WdfDeviceInitAssignWdmIrpPreprocessCallback
title: WdfDeviceInitAssignWdmIrpPreprocessCallback function (wdfdevice.h)
description: The WdfDeviceInitAssignWdmIrpPreprocessCallback method registers a callback function to handle an IRP major function code and, optionally, one or more minor function codes that are associated with the major function code.
old-location: wdf\wdfdeviceinitassignwdmirppreprocesscallback.htm
tech.root: wdf
ms.assetid: 9c17a5e2-dcf2-493a-9851-11d47adbfc82
ms.date: 02/26/2018
keywords: ["WdfDeviceInitAssignWdmIrpPreprocessCallback function"]
ms.keywords: DFDeviceObjectGeneralRef_ff2869f4-a557-4d3a-bd4d-67b8e1720ba9.xml, WdfDeviceInitAssignWdmIrpPreprocessCallback, WdfDeviceInitAssignWdmIrpPreprocessCallback method, kmdf.wdfdeviceinitassignwdmirppreprocesscallback, wdf.wdfdeviceinitassignwdmirppreprocesscallback, wdfdevice/WdfDeviceInitAssignWdmIrpPreprocessCallback
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: ChildDeviceInitAPI, ControlDeviceInitAPI, DeviceInitAPI, DriverCreate, InitFreeDeviceCallback, InitFreeDeviceCreate, InitFreeNull, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI, PdoInitFreeDeviceCallback, PdoInitFreeDeviceCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfDeviceInitAssignWdmIrpPreprocessCallback
 - wdfdevice/WdfDeviceInitAssignWdmIrpPreprocessCallback
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfDeviceInitAssignWdmIrpPreprocessCallback
---

# WdfDeviceInitAssignWdmIrpPreprocessCallback function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDeviceInitAssignWdmIrpPreprocessCallback</b> method registers a callback function to handle an IRP major function code and, optionally, one or more minor function codes that are associated with the major function code.

## -parameters

### -param DeviceInit 

[in]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure.

### -param EvtDeviceWdmIrpPreprocess 

[in]
A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdfdevice_wdm_irp_preprocess">EvtDeviceWdmIrpPreprocess</a> callback function.

### -param MajorFunction 

[in]
One of the IRP major function codes that are defined in <i>wdm.h</i>.

### -param MinorFunctions 

[in, optional]
A pointer to an array of one or more IRP minor function codes that are associated with the specified major function code. This parameter is optional and can be <b>NULL</b>. For more information, see the following Remarks section.

### -param NumMinorFunctions 

[in]
The number of minor function codes that are contained in the <i>MinorFunctions</i> array.

## -returns

If the operation succeeds, the method returns STATUS_SUCCESS. Additional return values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>MajorFunction</i> value is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There is insufficient memory.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
 The driver previously registered a <i>MinorFunctions</i> array for this major function and is attempting to specify minor functions again for the specified <i>MajorFunction</i> code.

</td>
</tr>
</table>
 

The method might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

## -remarks

Drivers can call the <b>WdfDeviceInitAssignWdmIrpPreprocessCallback</b> method for either of two reasons:

<ul>
<li>
To handle an IRP major or minor function code that the framework does not support. 

For example, the framework does not support <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-flush-buffers">IRP_MJ_FLUSH_BUFFERS</a>. If your driver must support this IRP, it must register an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdfdevice_wdm_irp_preprocess">EvtDeviceWdmIrpPreprocess</a> callback function that handles the IRP. The driver must follow WDM rules for processing IRPs.

</li>
<li>
To preprocess an IRP before the framework handles it.

In rare cases, it might be necessary for a driver to process an IRP before the framework processes it. In such cases, the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdfdevice_wdm_irp_preprocess">EvtDeviceWdmIrpPreprocess</a> callback function can process the IRP and then call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmdispatchpreprocessedirp">WdfDeviceWdmDispatchPreprocessedIrp</a> to return the IRP to the framework. Depending on the IRP's function code, the framework might process the IRP itself or it might deliver the IRP to the driver again in a framework request object.

</li>
</ul>
The framework calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdfdevice_wdm_irp_preprocess">EvtDeviceWdmIrpPreprocess</a> callback function whenever it receives an I/O request packet (IRP) that contains an IRP major function code that matches the <i>MajorFunction</i> parameter and a minor function code that matches one of the minor function codes that are in the <i>MinorFunctions</i> array. 

If the <i>MinorFunctions</i> array pointer is <b>NULL</b>, the framework calls the callback function for all minor function codes that are associated with the specified major function code. If the <i>MinorFunctions</i> array pointer is not <b>NULL</b>, the framework makes a copy of the array so that the driver does not have to permanently keep its array.

If the driver received <i>DeviceInit</i> pointer from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfpdo/nf-wdfpdo-wdfpdoinitallocate">WdfPdoInitAllocate</a> or an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_create_device">EvtChildListCreateDevice</a> event callback function, the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdfdevice_wdm_irp_preprocess">EvtDeviceWdmIrpPreprocess</a> callback function cannot set a completion routine for IRPs that contain a major function code of IRP_MJ_PNP. Otherwise, <a href="https://docs.microsoft.com/windows-hardware/drivers/what-s-new-in-driver-development">Driver Verifier</a> will report an error.

If your driver calls <b>WdfDeviceInitAssignWdmIrpPreprocessCallback</b> one or more times, the framework increments the <b>StackSize</b> member of the driver's WDM <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure one time. As a result, the I/O manager adds an additional <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/i-o-stack-locations">I/O stack location</a> to all IRPs  so that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdfdevice_wdm_irp_preprocess">EvtDeviceWdmIrpPreprocess</a> callback function can set an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_completion_routine">IoCompletion</a> routine. Note that this extra I/O stack location is added to all IRPs, not just the ones that contain an IRP major function code that you specify in a call to <b>WdfDeviceInitAssignWdmIrpPreprocessCallback</b>. Therefore, to avoid unnecessarily increasing your driver's use of  the nonpaged memory pool, you should avoid using <b>WdfDeviceInitAssignWdmIrpPreprocessCallback</b> unless there is no alternative.

If your driver calls <b>WdfDeviceInitAssignWdmIrpPreprocessCallback</b> more than once for the same major code, the framework retains only the most recently set <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdfdevice_wdm_irp_preprocess">EvtDeviceWdmIrpPreprocess</a> callback function for this major code.  (Your driver can’t register multiple preprocess callbacks for a single major code.)

For more information about the <b>WdfDeviceInitAssignWdmIrpPreprocessCallback</b> method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/handling-wdm-irps-outside-of-the-framework">Handling WDM IRPs Outside of the Framework</a>.


#### Examples

The following code example defines an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdfdevice_wdm_irp_preprocess">EvtDeviceWdmIrpPreprocess</a> event callback function, and then registers the callback function to handle <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-query-information">IRP_MJ_QUERY_INFORMATION</a> IRPs.

```cpp
NTSTATUS
SerialQueryInformationFile(
    IN WDFDEVICE Device,
    IN PIRP Irp
    )

/*++

Routine Description:

    This routine is used to query the end of file information on
    the opened serial port.  Any other file information request
    is retured with an invalid parameter.

    This routine always returns an end of file of 0.

Arguments:

    DeviceObject - Pointer to the device object for this device

    Irp - Pointer to the IRP for the current request

Return Value:

    The function value is the final status of the call

--*/

{
    NTSTATUS Status;
    PIO_STACK_LOCATION IrpSp;

    SerialDbgPrintEx(TRACE_LEVEL_INFORMATION, DBG_PNP, ">SerialQueryInformationFile(%p, %p)\n", Device, Irp);

    PAGED_CODE();


    IrpSp = IoGetCurrentIrpStackLocation(Irp);
    Irp->IoStatus.Information = 0L;
    Status = STATUS_SUCCESS;

    if (IrpSp->Parameters.QueryFile.FileInformationClass ==
        FileStandardInformation) {

        if (IrpSp->Parameters.DeviceIoControl.OutputBufferLength <
                sizeof(FILE_STANDARD_INFORMATION))
        {
                Status = STATUS_BUFFER_TOO_SMALL;
        }
        else
        {
            PFILE_STANDARD_INFORMATION Buf = Irp->AssociatedIrp.SystemBuffer;

            Buf->AllocationSize.QuadPart = 0;
            Buf->EndOfFile = Buf->AllocationSize;
            Buf->NumberOfLinks = 0;
            Buf->DeletePending = FALSE;
            Buf->Directory = FALSE;
            Irp->IoStatus.Information = sizeof(FILE_STANDARD_INFORMATION);
        }

    } else if (IrpSp->Parameters.QueryFile.FileInformationClass ==
               FilePositionInformation) {

        if (IrpSp->Parameters.DeviceIoControl.OutputBufferLength <
                sizeof(FILE_POSITION_INFORMATION))
        {
                Status = STATUS_BUFFER_TOO_SMALL;
        }
        else
        {

            ((PFILE_POSITION_INFORMATION)Irp->AssociatedIrp.SystemBuffer)->
                CurrentByteOffset.QuadPart = 0;
            Irp->IoStatus.Information = sizeof(FILE_POSITION_INFORMATION);
        }

    } else {
        Status = STATUS_INVALID_PARAMETER;
    }

    Irp->IoStatus.Status = Status;

    IoCompleteRequest(Irp, IO_NO_INCREMENT);

    return Status;

}

NTSTATUS
SerialEvtDeviceAdd(
    IN WDFDRIVER Driver,
    IN PWDFDEVICE_INIT DeviceInit
    )
{
...
    status = WdfDeviceInitAssignWdmIrpPreprocessCallback(
                                                 DeviceInit,
                                                 SerialQueryInformationFile,
                                                 IRP_MJ_QUERY_INFORMATION,
                                                 NULL, // Pointer to the minor function table
                                                 0 // Number of entries in the table
                                                 ); 
    if (!NT_SUCCESS(status)) {
        return status;
    }
...
}
```

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmdispatchpreprocessedirp">WdfDeviceWdmDispatchPreprocessedIrp</a>

