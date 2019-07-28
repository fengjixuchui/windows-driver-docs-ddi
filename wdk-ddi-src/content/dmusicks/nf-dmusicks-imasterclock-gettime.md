---
UID: NF:dmusicks.IMasterClock.GetTime
title: IMasterClock::GetTime (dmusicks.h)
description: The GetTime method retrieves the current reference time read from the master clock.
old-location: audio\imasterclock_gettime.htm
tech.root: audio
ms.assetid: 9e88a94d-ce25-43ee-8187-30b406e8d9e4
ms.date: 05/08/2018
ms.keywords: GetTime, GetTime method [Audio Devices], GetTime method [Audio Devices],IMasterClock interface, IMasterClock interface [Audio Devices],GetTime method, IMasterClock.GetTime, IMasterClock::GetTime, audio.imasterclock_gettime, audmp-routines_08af6e05-c432-4560-91fb-f17687291fc0.xml, dmusicks/IMasterClock::GetTime
ms.topic: method
f1_keywords:
 - "dmusicks/IMasterClock.GetTime"
req.header: dmusicks.h
req.include-header: Dmusicks.h
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
req.lib: 
req.dll: 
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dmusicks.h
api_name:
- IMasterClock.GetTime
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMasterClock::GetTime


## -description


The <code>GetTime</code> method retrieves the current reference time read from the master clock.


## -parameters




### -param pTime [out]

Output pointer for the reference time. This parameter points to a caller-allocated variable into which the method writes the reference time. Reference time is measured in 100-nanosecond units.


## -returns



<code>GetTime</code> returns S_OK if the call was successful. Otherwise, the method returns an appropriate error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dmusicks/nn-dmusicks-imasterclock">IMasterClock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dmusicks/nf-dmusicks-iminiportdmus-newstream">IMiniportDMus::NewStream</a>
 

 

