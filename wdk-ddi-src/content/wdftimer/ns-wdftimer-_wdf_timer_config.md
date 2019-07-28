---
UID: NS:wdftimer._WDF_TIMER_CONFIG
title: _WDF_TIMER_CONFIG (wdftimer.h)
description: The WDF_TIMER_CONFIG structure contains configuration information for a framework timer object.
old-location: wdf\wdf_timer_config.htm
tech.root: wdf
ms.assetid: 5ef6491d-90bb-472c-821a-b296bef17463
ms.date: 02/26/2018
ms.keywords: "*PWDF_TIMER_CONFIG, DFTimerObjectRef_cacde276-7a83-4a7f-87e1-de043aee4725.xml, PWDF_TIMER_CONFIG, PWDF_TIMER_CONFIG structure pointer, WDF_TIMER_CONFIG, WDF_TIMER_CONFIG structure, _WDF_TIMER_CONFIG, kmdf.wdf_timer_config, wdf.wdf_timer_config, wdftimer/PWDF_TIMER_CONFIG, wdftimer/WDF_TIMER_CONFIG"
ms.topic: struct
f1_keywords:
 - "wdftimer/WDF_TIMER_CONFIG"
req.header: wdftimer.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
- wdftimer.h
api_name:
- WDF_TIMER_CONFIG
product:
- Windows
targetos: Windows
req.typenames: WDF_TIMER_CONFIG, *PWDF_TIMER_CONFIG
---

# _WDF_TIMER_CONFIG structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_TIMER_CONFIG</b> structure contains configuration information for a framework timer object.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field EvtTimerFunc

A pointer to a driver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdftimer/nc-wdftimer-evt_wdf_timer">EvtTimerFunc</a> callback function, or <b>NULL</b>.


### -field Period

A time period, in milliseconds. The framework calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdftimer/nc-wdftimer-evt_wdf_timer">EvtTimerFunc</a> callback function repeatedly, whenever the specified number of milliseconds elapses. If this value is zero, the framework does not call the driver's <i>EvtTimerFunc</i> callback function repeatedly. Instead, it calls the callback function once, after the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdftimer/nf-wdftimer-wdftimerstart">WdfTimerStart</a> method's <i>DueTime</i> has elapsed. (The time period must be zero if <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdftimer/nf-wdftimer-wdftimercreate">WdfTimerCreate</a> sets the execution level to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ne-wdfobject-_wdf_execution_level">WdfExecutionLevelPassive</a>.) The time period cannot be a negative value.


### -field AutomaticSerialization

A Boolean value that, if <b>TRUE</b>, indicates that the framework will synchronize execution of the timer object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdftimer/nc-wdftimer-evt_wdf_timer">EvtTimerFunc</a> callback function with callback functions from other objects that are underneath the timer's parent device object. For more information, see the following Remarks section. If <b>FALSE</b>, the framework does not synchronize execution of the <i>EvtTimerFunc</i> callback function.


### -field TolerableDelay

Specifies a tolerance, in milliseconds, for the timer period that <i>Period</i> specifies and for the initial time interval that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdftimer/nf-wdftimer-wdftimerstart">WdfTimerStart</a> method's <i>DueTime</i> specifies. For a periodic timer, the time interval between two successive timer expirations will be in the range from (<i>Period</i> - <i>TolerableDelay</i>) to (<i>Period</i> + <i>TolerableDelay</i>). The initial expiration time will be in the range from <i>DueTime</i> to (<i>DueTime</i> + <i>TolerableDelay</i>). The <i>TolerableDelay</i> value cannot be negative.

 The <b>TolerableDelay</b> member is available in version 1.9 and later versions of KMDF.

 Starting in Windows 8.1, in a driver using at minimum KMDF 1.13 or UMDF 2.0, you can set this member to <b>TolerableDelayUnlimited</b> to specify that the system should not be woken up as a result of this timer's expiration.

If  <b>UseHighResolutionTimer</b> is <b>WdfTrue</b>, you must set <b>TolerableDelay</b> to zero. Otherwise, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdftimer/nf-wdftimer-wdftimercreate">WdfTimerCreate</a> returns a failure code.

For more information about this member, see the following Remarks section.


### -field UseHighResolutionTimer

<b>KMDF only</b>

This member is available starting with Windows 8.1 and KMDF version 1.13.

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdftypes/ne-wdftypes-_wdf_tri_state">WDF_TRI_STATE</a>-typed value. If this value is <b>WdfTrue</b>, the framework uses a high resolution timer that has an accuracy of one millisecond.  If the value is <b>WdfFalse</b> or <b>WdfDefault</b>, the framework uses a standard timer that has an accuracy matching the system clock tick interval, which is by default 15.6 milliseconds.

<div class="alert"><b>Warning</b>  If you set <b>UseHighResolutionTimer</b> to <b>WdfTrue</b>, you must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdftimer/nf-wdftimer-wdftimerstart">WdfTimerStart</a> with the <i>DueTime</i> parameter set to a negative value.  Otherwise, the call causes the system to crash.</div>
<div> </div>
If  <b>UseHighResolutionTimer</b> is <b>WdfTrue</b>, you must set <b>TolerableDelay</b> to zero. Otherwise, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdftimer/nf-wdftimer-wdftimercreate">WdfTimerCreate</a> returns a failure code.


             For more information about this member, see the following Remarks section.


## -remarks



The <b>WDF_TIMER_CONFIG</b> structure is used as input to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdftimer/nf-wdftimer-wdftimercreate">WdfTimerCreate</a> method. To initialize a <b>WDF_TIMER_CONFIG</b> structure, your driver must call either <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdftimer/nf-wdftimer-wdf_timer_config_init">WDF_TIMER_CONFIG_INIT</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdftimer/nf-wdftimer-wdf_timer_config_init_periodic">WDF_TIMER_CONFIG_INIT_PERIODIC</a>.

Setting the <b>AutomaticSerialization</b> member of <b>WDF_TIMER_CONFIG</b> to <b>TRUE</b> has no effect if the parent object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ne-wdfobject-_wdf_synchronization_scope">synchronization scope</a> is set to <b>WdfSynchronizationScopeNone</b>.

If the parent device object's execution level is <b>WdfExecutionLevelPassive</b>, you can set the <b>AutomaticSerialization</b> member to <b>TRUE</b> only if the timer object represents a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-timers">passive-level timer</a>.

If a driver uses the <b>TolerableDelay</b> member, the operating system can group together expiration times that are close together and process them all at once. If the operating system can handle the expirations of multiple timers at once, it can potentially keep the computer in a low-power state for longer periods of time to increase battery life.

If the  <b>TolerableDelay</b> member is <b>TolerableDelayUnlimited</b>, the system will not return to its fully on (S0) state to service the timer if it is in a low-power (S<i>x</i>) state when the timer expires. A driver can specify <b>TolerableDelayUnlimited</b> to increase battery life when the timer is related to a non-critical periodic operation.

Setting <b>UseHighResolutionTimer</b> to <b>WdfTrue</b> may result in decreased battery life.

For more information about <b>AutomaticSerialization</b> and synchronizing driver callback functions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/synchronization-techniques-for-wdf-drivers">Synchronization Techniques for Framework-Based Drivers</a>.

For more information about framework timer objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-timers">Using Timers</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdftimer/nc-wdftimer-evt_wdf_timer">EvtTimerFunc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdftimer/nf-wdftimer-wdf_timer_config_init">WDF_TIMER_CONFIG_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdftimer/nf-wdftimer-wdf_timer_config_init_periodic">WDF_TIMER_CONFIG_INIT_PERIODIC</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdftimer/nf-wdftimer-wdftimercreate">WdfTimerCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdftimer/nf-wdftimer-wdftimerstart">WdfTimerStart</a>
 

 

