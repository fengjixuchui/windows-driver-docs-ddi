---
UID: NF:wdfinterrupt.WdfInterruptSynchronize
title: WdfInterruptSynchronize function (wdfinterrupt.h)
description: The WdfInterruptSynchronize method executes a specified callback function at the device's DIRQL while holding an interrupt object's spin lock.
old-location: wdf\wdfinterruptsynchronize.htm
tech.root: wdf
ms.assetid: b41fc37a-d41f-49ca-848f-844e049dd987
ms.date: 02/26/2018
keywords: ["WdfInterruptSynchronize function"]
ms.keywords: DFInterruptObjectRef_d56eadd2-4636-43bb-b842-318243bcf192.xml, WdfInterruptSynchronize, WdfInterruptSynchronize method, kmdf.wdfinterruptsynchronize, wdf.wdfinterruptsynchronize, wdfinterrupt/WdfInterruptSynchronize
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
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
 - WdfInterruptSynchronize
 - wdfinterrupt/WdfInterruptSynchronize
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
 - WdfInterruptSynchronize
---

# WdfInterruptSynchronize function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfInterruptSynchronize</b> method executes a specified callback function at the device's DIRQL while holding an interrupt object's spin lock.

For passive level interrupt objects, this method executes a specified callback function at passive level while holding an interrupt object's passive-level interrupt lock.

## -parameters

### -param Interrupt 

[in]
A handle to a framework interrupt object.

### -param Callback 

[in]
A pointer to an <a href="/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_synchronize">EvtInterruptSynchronize</a> callback function.

### -param Context 

[in]
An untyped pointer to driver-supplied information that the framework passes to the <a href="/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_synchronize">EvtInterruptSynchronize</a> callback function.

## -returns

<b>WdfInterruptSynchronize</b> returns the Boolean status value that the <a href="/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_synchronize">EvtInterruptSynchronize</a> callback function returns.

A bug check occurs if the driver supplies an invalid object handle.

## -remarks

If you want your driver to execute code that must run without being preempted and with servicing of device interrupts effectively disabled, you should place that code in an <a href="/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_synchronize">EvtInterruptSynchronize</a> callback function. To schedule execution of the callback function, your driver must call <b>WdfInterruptSynchronize</b>.

The <b>WdfInterruptSynchronize</b> method returns after the <a href="/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_synchronize">EvtInterruptSynchronize</a> callback function has finished executing.

Instead of calling <b>WdfInterruptSynchronize</b>, your driver can call <a href="/previous-versions/ff547340(v=vs.85)">WdfInterruptAcquireLock</a> and <a href="/previous-versions/ff547376(v=vs.85)">WdfInterruptReleaseLock</a>.

For more information about the <b>WdfInterruptSynchronize</b> method, see <a href="/windows-hardware/drivers/wdf/synchronizing-interrupt-code">Synchronizing Interrupt Code</a>.

For more information about handling interrupts in framework-based drivers, see <a href="/windows-hardware/drivers/wdf/handling-hardware-interrupts">Handling Hardware Interrupts</a>.

For passive level interrupts, the driver must call <b>WdfInterruptSynchronize</b> at IRQL = PASSIVE_LEVEL.

Do not call <b>WdfInterruptSynchronize</b> from an arbitrary thread context,  such as a <a href="/windows-hardware/drivers/wdf/request-handlers">request handler</a>.


#### Examples

The following code example shows how to call <b>WdfInterruptSynchronize</b> to schedule execution of an <a href="/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_synchronize">EvtInterruptSynchronize</a>  callback function.

```cpp
BOOLEAN synchronizeReturnValue;

synchronizeReturnValue = WdfInterruptSynchronize(
                                         WdfInterrupt,
                                         MyEvtInterruptSynchronize,
                                         CallbackContext
                                         );
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_synchronize">EvtInterruptSynchronize</a>



<a href="/previous-versions/ff547340(v=vs.85)">WdfInterruptAcquireLock</a>



<a href="/previous-versions/ff547376(v=vs.85)">WdfInterruptReleaseLock</a>