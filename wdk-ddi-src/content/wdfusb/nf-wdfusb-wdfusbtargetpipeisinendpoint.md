---
UID: NF:wdfusb.WdfUsbTargetPipeIsInEndpoint
title: WdfUsbTargetPipeIsInEndpoint function (wdfusb.h)
description: The WdfUsbTargetPipeIsInEndpoint method determines whether a specified USB pipe is connected to an input endpoint.
old-location: wdf\wdfusbtargetpipeisinendpoint.htm
tech.root: wdf
ms.assetid: 431d8f18-18db-460c-9f2f-454a5378825c
ms.date: 02/26/2018
keywords: ["WdfUsbTargetPipeIsInEndpoint function"]
ms.keywords: DFUsbRef_55ca68a2-c334-47b9-9716-68a492987897.xml, WdfUsbTargetPipeIsInEndpoint, WdfUsbTargetPipeIsInEndpoint method, kmdf.wdfusbtargetpipeisinendpoint, wdf.wdfusbtargetpipeisinendpoint, wdfusb/WdfUsbTargetPipeIsInEndpoint
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, UsbKmdfIrql, UsbKmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfUsbTargetPipeIsInEndpoint
 - wdfusb/WdfUsbTargetPipeIsInEndpoint
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
 - WUDFx02000.dll
 - WUDFx02000.dll.dll
api_name:
 - WdfUsbTargetPipeIsInEndpoint
---

# WdfUsbTargetPipeIsInEndpoint function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfUsbTargetPipeIsInEndpoint</b> method determines whether a specified USB pipe is connected to an input endpoint.

## -parameters

### -param Pipe 

[in]
A handle to a framework pipe object that represents a bulk pipe or interrupt pipe and was obtained by calling <a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbinterfacegetconfiguredpipe">WdfUsbInterfaceGetConfiguredPipe</a>.

## -returns

<b>WdfUsbTargetPipeIsInEndpoint</b> returns <b>TRUE</b> if the pipe that the <i>Pipe</i> handle represents is an input endpoint. The method returns <b>FALSE</b> if the endpoint is an output endpoint.

A bug check occurs if the driver supplies an invalid object handle.

## -remarks

For more information about the <b>WdfUsbTargetPipeIsInEndpoint</b> method and USB I/O targets, see <a href="/windows-hardware/drivers/wdf/usb-i-o-targets">USB I/O Targets</a>.


#### Examples

The following code example determines whether a specified USB pipe is connected to an input endpoint.

```cpp
BOOLEAN isInEndPoint;

isInEndPoint = WdfUsbTargetPipeIsInEndpoint(usbPipe);
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_pipe_direction_in">WDF_USB_PIPE_DIRECTION_IN</a>



<a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbinterfacegetconfiguredpipe">WdfUsbInterfaceGetConfiguredPipe</a>



<a href="/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetpipeisoutendpoint">WdfUsbTargetPipeIsOutEndpoint</a>