---
UID: NS:pepfx._PEP_PROCESSOR_FEEDBACK_COUNTER
title: _PEP_PROCESSOR_FEEDBACK_COUNTER (pepfx.h)
description: The PEP_PROCESSOR_FEEDBACK_COUNTER structure describes a feedback counter to the operating system.
old-location: kernel\pep_processor_feedback_counter.htm
tech.root: kernel
ms.assetid: 275AE285-6309-4A03-A02C-DBE8D44727CE
ms.date: 04/30/2018
keywords: ["_PEP_PROCESSOR_FEEDBACK_COUNTER structure"]
ms.keywords: "*PPEP_PROCESSOR_FEEDBACK_COUNTER, PEP_PROCESSOR_FEEDBACK_COUNTER, PEP_PROCESSOR_FEEDBACK_COUNTER structure [Kernel-Mode Driver Architecture], PPEP_PROCESSOR_FEEDBACK_COUNTER, PPEP_PROCESSOR_FEEDBACK_COUNTER structure pointer [Kernel-Mode Driver Architecture], PROCESSOR_FEEDBACK_COUNTER_FREQUENCY, PROCESSOR_FEEDBACK_COUNTER_PERFORMANCE, PROCESSOR_FEEDBACK_TYPE_INSTANTANEOUS, PROCESSOR_FEEDBACK_TYPE_RELATIVE, _PEP_PROCESSOR_FEEDBACK_COUNTER, kernel.pep_processor_feedback_counter, pepfx/PEP_PROCESSOR_FEEDBACK_COUNTER, pepfx/PPEP_PROCESSOR_FEEDBACK_COUNTER"
f1_keywords:
 - "pepfx/PEP_PROCESSOR_FEEDBACK_COUNTER"
req.header: pepfx.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- pepfx.h
api_name:
- PEP_PROCESSOR_FEEDBACK_COUNTER
product:
- Windows
targetos: Windows
req.typenames: PEP_PROCESSOR_FEEDBACK_COUNTER, *PPEP_PROCESSOR_FEEDBACK_COUNTER
---

# _PEP_PROCESSOR_FEEDBACK_COUNTER structure


## -description


The <b>PEP_PROCESSOR_FEEDBACK_COUNTER</b> structure describes a feedback counter to the operating system.


## -struct-fields




### -field Affinitized

Identifies the counter process affinity. If set to 1, the counter must be read while executing on the target processor, otherwise, it will be set to 0.


### -field Type

Specifies the data type of the counter.


The processor feedback counter data types are:



|Value|Meaning|
|--- |--- |
|**PROCESSOR_FEEDBACK_TYPE_INSTANTANEOUS** (0x00) |The feedback counter returns the instantaneous value of the property being counted.|
|**PROCESSOR_FEEDBACK_TYPE_RELATIVE** (0x01) |The feedback counter returns two incrementing values: the nominal count, and the actual count. Nominal count increments at a fixed nominal rate. Actual count increments at a variable rate relative to the property being counted. When the property is incrementing at its nominal rate, the two values should increment at the same rate. To compute an average rate over a time period, the OS reads the counter once and the beginning of the period and once at the end and computes: ![The average rate is equal to the nominal rate multiplied by the quotient of the variable rate divided by the fixed rate.](images/PEP_PROCESSOR_FEEDBACK_COUNTER_equation.png)|

 


### -field Counter

Specifies the data the counter is providing.


The processor feedback counter types are:



<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="PROCESSOR_FEEDBACK_COUNTER_FREQUENCY_"></a><a id="processor_feedback_counter_frequency_"></a><dl>
<dt><b>PROCESSOR_FEEDBACK_COUNTER_FREQUENCY </b></dt>
<dt>0x00</dt>
</dl>
</td>
<td width="60%">
The feedback counter returns the clock speed of the processor. The nominal rate is the nominal clock speed, in MHz.

</td>
</tr>
<tr>
<td width="40%"><a id="PROCESSOR_FEEDBACK_COUNTER_PERFORMANCE"></a><a id="processor_feedback_counter_performance"></a><dl>
<dt><b>PROCESSOR_FEEDBACK_COUNTER_PERFORMANCE</b></dt>
<dt>0x01</dt>
</dl>
</td>
<td width="60%">
The feedback counter returns the current processor performance. The nominal rate is equivalent to the processor's <b>NominalPerformance</b> (see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_perf_capabilities">PEP_NOTIFY_PPM_QUERY_PERF_CAPABILITIES notification</a>).

</td>
</tr>
</table>
 


### -field DiscountIdle

 


### -field Reserved

This member is reserved and should be set to zero.


### -field NominalRate

Specifies the nominal rate of the counter. 


## -remarks



This structure 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">PEP structures</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_perf_capabilities">PEP_NOTIFY_PPM_QUERY_PERF_CAPABILITIES notification</a>
 

 

