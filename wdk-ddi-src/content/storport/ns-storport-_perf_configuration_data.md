---
UID: NS:storport._PERF_CONFIGURATION_DATA
title: _PERF_CONFIGURATION_DATA (storport.h)
description: The PERF_CONFIGURATION_DATA structure describes the performance optimizations that are supported by the StorPortInitializePerfOpts routine.
old-location: storage\perf_configuration_data.htm
tech.root: storage
ms.assetid: 47db8f0f-9f3b-44d9-8110-dc0b79d0e26a
ms.date: 03/29/2018
keywords: ["PERF_CONFIGURATION_DATA structure"]
ms.keywords: "*PPERF_CONFIGURATION_DATA, PERF_CONFIGURATION_DATA, PERF_CONFIGURATION_DATA structure [Storage Devices], PPERF_CONFIGURATION_DATA, PPERF_CONFIGURATION_DATA structure pointer [Storage Devices], _PERF_CONFIGURATION_DATA, storage.perf_configuration_data, storport/PERF_CONFIGURATION_DATA, storport/PPERF_CONFIGURATION_DATA, structs-storport_3ff35217-29b1-43ab-a6e4-72aeaf90e931.xml"
req.header: storport.h
req.include-header: Storport.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: PERF_CONFIGURATION_DATA, *PPERF_CONFIGURATION_DATA
f1_keywords:
 - _PERF_CONFIGURATION_DATA
 - storport/_PERF_CONFIGURATION_DATA
 - PPERF_CONFIGURATION_DATA
 - storport/PPERF_CONFIGURATION_DATA
 - PERF_CONFIGURATION_DATA
 - storport/PERF_CONFIGURATION_DATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - PERF_CONFIGURATION_DATA
---

# _PERF_CONFIGURATION_DATA structure


## -description

The PERF_CONFIGURATION_DATA structure describes the performance optimizations that are supported by the <a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportinitializeperfopts">StorPortInitializePerfOpts</a> routine.

## -struct-fields

### -field Version

The version number of the structure. Set this member when querying and initializing optimizations.

### -field Size

The size of the structure, set to <b>sizeof(PERF_CONFIGURATION_DATA)</b>.

### -field Flags

A bitwise-OR of supported flags. Currently, the following flags are supported:
	  

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
STOR_PERF_DPC_REDIRECTION

</td>
<td>
This flag is used to indicate that DPC processing should be spread out over multiple CPUs.

This flag is valid when <b>Version</b> is set to 2 or 3.

</td>
</tr>
<tr>
<td>
STOR_PERF_CONCURRENT_CHANNELS

</td>
<td>
This flag is used to indicate that concurrent calls to the <a href="/windows-hardware/drivers/ddi/storport/nc-storport-hw_startio">HwStorStartIo</a> routine are supported. Prior to Windows 8, miniports must not set this flag.

This flag is valid when <b>Version</b> is set to 2 or 3.

</td>
</tr>
<tr>
<td>
STOR_PERF_INTERRUPT_MESSAGE_RANGES

</td>
<td>
This flag is used to indicate that interrupt redirection is supported. When you use this flag, you must also set the STOR_PERF_DPC_REDIRECTION flag.

This flag is valid when <b>Version</b> is set to 2 or 3.

</td>
</tr>
<tr>
<td>
STOR_PERF_ADV_CONFIG_LOCALITY

</td>
<td>
This flag is used to indicate that you should use the group and mask that pertain to the message group with the correct affinity. When you use this flag, you must also set the STOR_PERF_INTERRUPT_MESSAGE_RANGES and the STOR_PERF_DPC_REDIRECTION flags.

This flag is valid when <b>Version</b> is set to 3.

</td>
</tr>
<tr>
<td>
STOR_PERF_OPTIMIZE_FOR_COMPLETION_DURING_STARTIO

</td>
<td>
This flag is used to indicate that the miniport driver will complete I/Os concurrently with the submission of new I/Os. When you use this flag, you must also set the STOR_PERF_DPC_REDIRECTION flag.

This flag is valid when <b>Version</b> is set to 3. See remarks below.

</td>
</tr>
<tr>
<td>
STOR_PERF_DPC_REDIRECTION_CURRENT_CPU

</td>
<td>
This flag is used to indicate that you are opting into DPC Redirection (required) but the IO redirection choice is set to the CPU requesting the DPC and not the CPU originating the IO request into Storport.

When you use this flag, you must also set the STOR_PERF_DPC_REDIRECTION flag.

This flag is valid when <b>Version</b> is set to 4.

</td>
</tr>
<tr>
<td>
STOR_PERF_NO_SGL

</td>
<td>
This flag is used to indicate that miniport doesn't need SGLs to be created by storport driver for an IO request buffer. 

This flag is valid when <b>Version</b> is set to 5.

</td>
</tr>
</table>

### -field ConcurrentChannels

The number of concurrent calls to the <a href="/windows-hardware/drivers/ddi/storport/nc-storport-hw_startio">HwStorStartIo</a> routine that the miniport driver and the device  support. This member is only accessed when the STOR_PERF_CONCURRENT_CHANNELS flag has been set. Prior to Windows 8, miniports must not set this value.

### -field FirstRedirectionMessageNumber

When the <b>Flags</b> member has the STOR_PERF_INTERRUPT_MESSAGE_RANGES flag set, the miniport driver initializes interrupt redirection to begin with this message number. This member is only accessed when the STOR_PERF_INTERRUPT_MESSAGE_RANGES flag is set.

### -field LastRedirectionMessageNumber

When the <b>Flags</b> member has the STOR_PERF_INTERRUPT_MESSAGE_RANGES flag set, the miniport driver initializes interrupt redirection to end with this message number. This member is only accessed when the STOR_PERF_INTERRUPT_MESSAGE_RANGES flag is set.

### -field DeviceNode

When the <b>Flags</b> member has the STOR_PERF_ADV_CONFIG_LOCALITY flag set, Storport initializes this field to contain the NUMA node number in which the miniport driver's device resides.

### -field Reserved

Reserved for system use.

### -field MessageTargets

When the <b>Flags</b> member has the STOR_PERF_ADV_CONFIG_LOCALITY flag set, Storport initializes the fields of in the structures of a <a href="/windows-hardware/drivers/ddi/miniport/ns-miniport-_group_affinity">GROUP_AFFINITY</a> array. These structures correspond to the redirection messages that are currently in use. The array itself is zero-based, but <b>FirstRedirectionMessageNumber</b> is not required to be zero. The miniport allocates this array and sets <b>MessageTargets</b> to point to it. The miniport driver must allocate a <b>GROUP_AFFINITY</b> array large enough to hold all the returned affinity masks.

## -remarks

The current version of this structure is defined by <b>STOR_PERF_VERSION</b>. Setting <b>Version</b> to this value will allow <b>Flags</b> to specify all  supported optimizations.

The purpose of the STOR_PERF_DPC_REDIRECTION flag is to ensure that individual CPUs are not overwhelmed with DPC processing. When this flag is set, DPC processing is spread over multiple CPUs. If STOR_PERF_DPC_REDIRECTION_CURRENT_CPU is not set, StorPort will attempt to schedule I/O completion DPCs on the same CPU that originated the I/O.

Typically, a miniport  completes I/O requests in it's <a href="/windows-hardware/drivers/ddi/storport/nc-storport-hw_startio">HwStorStartIo</a> routine and calls <a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportnotification">StorPortNotification</a> with the <b>RequestComplete</b> notification type. For processing I/O in this manner, the miniport will leave the STOR_PERF_OPTIMIZE_FOR_COMPLETION_DURING_STARTIO flag set in the <b>Flags</b> member allowing Storport to adjust DPC redirection.

For information about enabling message-signaled interrupts for a device, see <a href="/windows-hardware/drivers/kernel/enabling-message-signaled-interrupts-in-the-registry">Enabling Message-Signaled Interrupts in the Registry</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportinitializeperfopts">StorPortInitializePerfOpts</a>