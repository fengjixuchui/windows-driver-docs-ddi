---
UID: NF:ucmtcpciportcontroller.UcmTcpciPortControllerStart
title: UcmTcpciPortControllerStart function (ucmtcpciportcontroller.h)
description: Indicates to the UcmTcpciCx class extension that the client driver is now ready to service hardware requests for the port controller.
old-location: buses\ucmtcpciportcontrollerstart.htm
tech.root: usbref
ms.assetid: 94e7c36a-e45c-4d98-aeb7-f23769347ca5
ms.date: 05/07/2018
ms.keywords: UcmTcpciPortControllerStart, UcmTcpciPortControllerStart method [Buses], buses.ucmtcpciportcontrollerstart, ucmtcpciportcontroller/UcmTcpciPortControllerStart
ms.topic: function
req.header: ucmtcpciportcontroller.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ucmtcpcicxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ucmtcpcicxstub.lib
- ucmtcpcicxstub.dll
api_name:
- UcmTcpciPortControllerStart
product:
- Windows
targetos: Windows
req.typenames: 
---

# UcmTcpciPortControllerStart function


## -description


Indicates to the UcmTcpciCx class extension that the client driver  is now ready to service hardware requests for the port controller.


## -parameters




### -param PortControllerObject

Handle to the port controller  object that the client driver received in the previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucmtcpciportcontroller/nf-ucmtcpciportcontroller-ucmtcpciportcontrollercreate">UcmTcpciPortControllerCreate</a>.


## -returns




(NTSTATUS) The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.
                    

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The port controller is already in Start state.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
Hardware request queue has not been set by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucmtcpciportcontroller/nf-ucmtcpciportcontroller-ucmtcpciportcontrollersethardwarerequestqueue">UcmTcpciPortControllerSetHardwareRequestQueue</a>.

</td>
</tr>
</table>
 




## -remarks



After the client driver has received the UCMPORTCONTROLLER handle for the port controller object, the driver calls this method to notify the class extension that the driver can start receiving hardware requests. This method call allows the client driver to perform initialization of its framework context space on the port controller object, before the class extension can invoke the driver's callback functions or requests for the port controller object. The driver cannot call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucmtcpciportcontroller/nf-ucmtcpciportcontroller-ucmtcpciportcontrolleralert">UcmTcpciPortControllerAlert</a> or  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucmtcpciportcontroller/nf-ucmtcpciportcontroller-ucmtcpciportcontrollerstop">UcmTcpciPortControllerStop</a> until the port controller has been started.

The client driver calls this method right after calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucmtcpciportcontroller/nf-ucmtcpciportcontroller-ucmtcpciportcontrollercreate">UcmTcpciPortControllerCreate</a> and initializing its context structure, if it was specified in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure as the <i>Attributes</i> parameter value.
The driver must assume that the class extension may submit requests even before <b>UcmTcpciPortControllerStart</b> returns, i.e., from within this DDI call. If the driver is holding a lock while calling <b>UcmTcpciPortControllerStart</b> and also attempts to acquire a lock while handling a hardware request (in its hardware request queue callback), it might result in a deadlock.


A call to <b>UcmTcpciPortControllerStart</b> to start a port controller object already in Start state, results in an error. 


On boot, if the BIOS had already negotiated a PD contract, UcmTcpciCx starts from an unattached state.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucmtcpciportcontroller/nf-ucmtcpciportcontroller-ucmtcpciportcontrollerstop">UcmTcpciPortControllerStop</a>
 

 

