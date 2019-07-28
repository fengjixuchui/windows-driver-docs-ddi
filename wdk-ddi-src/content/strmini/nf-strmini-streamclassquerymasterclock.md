---
UID: NF:strmini.StreamClassQueryMasterClock
title: StreamClassQueryMasterClock function (strmini.h)
description: When the minidriver calls the StreamClassQueryMasterClock routine, the class driver queries the appropriate time value of the master clock asynchronously, and passes the result to the routine passed in the ClockCallbackRoutine parameter.
old-location: stream\streamclassquerymasterclock.htm
tech.root: stream
ms.assetid: 41b159b6-f365-4ade-b5d4-e7662c75e866
ms.date: 04/23/2018
ms.keywords: StreamClassQueryMasterClock, StreamClassQueryMasterClock routine [Streaming Media Devices], strclass-routines_2049b544-0e7a-4c12-801b-15d0a4a7ce6c.xml, stream.streamclassquerymasterclock, strmini/StreamClassQueryMasterClock
ms.topic: function
f1_keywords:
 - "strmini/StreamClassQueryMasterClock"
req.header: strmini.h
req.include-header: Strmini.h
req.target-type: Desktop
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
req.lib: Stream.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Stream.lib
- Stream.dll
api_name:
- StreamClassQueryMasterClock
product:
- Windows
targetos: Windows
req.typenames: 
---

# StreamClassQueryMasterClock function

## -description

When the minidriver calls the **StreamClassQueryMasterClock** routine, the class driver queries the appropriate time value of the master clock asynchronously, and passes the result to the routine passed in the *ClockCallbackRoutine* parameter.

## -parameters

### -param HwStreamObject [in]

Pointer to a [HW_STREAM_OBJECT](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/ns-strmini-_hw_stream_object) indicating the stream that is querying its master clock. The stream may only have one query pending at a time. The class driver passes this value to the callback in the **HwStreamObject** member of the callback's *TimeContext* parameter.

### -param MasterClockHandle [in]

Specifies the handle for the master clock that is being queried. The class driver passes this in the SRB_INDICATE_MASTER_CLOCK request to the minidriver's [StrMiniReceiveStreamControlPacket](https://docs.microsoft.com/previous-versions/ff568467(v=vs.85)) routine.

### -param TimeFunction [in]

Specifies what time function to query the master clock for. See [HW_TIME_CONTEXT](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/ns-strmini-_hw_time_context) for the possible values. The class driver passes this value to the callback in the **Function** member of the *TimeContext* parameter.

### -param ClockCallbackRoutine [in]

Specifies the routine to which the class driver passes the results. The function prototype must be:

```cpp
ClockCallbackRoutine(PHW_TIME_CONTEXT TimeContext);
```

## -returns

None

## -remarks

The class driver queries the master clock and passes the results in the *TimeContext* parameter (of type [HW_TIME_CONTEXT](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/ns-strmini-_hw_time_context)) of the callback. In particular, it sets the **Time** member of this structure to the time value requested in the *TimeFunction* parameter, the current system time in the **SystemTime** member of the same structure, and the minidriver's device extension in the **HwDeviceExtension** member of that structure.

The class driver deallocates the HW_TIME_CONTEXT structure after the clock callback routine terminates, so the callback must store any information the minidriver wishes to maintain. For that purpose, the callback routine may use previously-allocated space in either the minidriver's device extension (*TimeContext-*>**HwDeviceExtension**), or the stream extension of the stream that queried its master clock (*TimeContext*->**HwStreamObject**->**HwStreamExtension**).

On rare occasions, the graph manager switches the master clock. The class driver exposes a race condition in handling the new master clock. If the minidriver calls a stream class master clock routine immediately after it receives a new clock from the class driver, the class driver may produce unexpected results.

## -see-also

[HW_TIME_CONTEXT](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/ns-strmini-_hw_time_context)

[StrMiniReceiveStreamControlPacket](https://docs.microsoft.com/previous-versions/ff568467(v=vs.85))

[StreamClassQueryMasterClockSync](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/nf-strmini-streamclassquerymasterclocksync)
