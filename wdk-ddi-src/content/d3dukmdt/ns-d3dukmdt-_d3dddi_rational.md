---
UID: NS:d3dukmdt._D3DDDI_RATIONAL
title: _D3DDDI_RATIONAL (d3dukmdt.h)
description: The D3DDDI_RATIONAL structure describes a fractional value that represents vertical and horizontal frequencies of a video mode (that is, vertical sync and horizontal sync).
old-location: display\d3dddi_rational.htm
tech.root: display
ms.assetid: b6ae3b68-d9a0-45b3-bf5d-00c09b87709f
ms.date: 05/10/2018
keywords: ["_D3DDDI_RATIONAL structure"]
ms.keywords: D3DDDI_RATIONAL, D3DDDI_RATIONAL structure [Display Devices], DmStructs_68540737-a888-46aa-99d7-83a071f3f604.xml, _D3DDDI_RATIONAL, d3dukmdt/D3DDDI_RATIONAL, display.d3dddi_rational
f1_keywords:
 - "d3dukmdt/D3DDDI_RATIONAL"
req.header: d3dukmdt.h
req.include-header: D3dukmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
- d3dukmdt.h
api_name:
- D3DDDI_RATIONAL
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_RATIONAL
---

# _D3DDDI_RATIONAL structure


## -description


The D3DDDI_RATIONAL structure describes a fractional value that represents vertical and horizontal frequencies of a video mode (that is, vertical sync and horizontal sync). 


## -struct-fields




### -field Numerator

[in] The numerator of the frequency fraction.


### -field Denominator

[in] The denominator of the frequency fraction.


## -remarks



Vertical and horizontal frequencies are stored in Hertz (Hz). 
	 The dynamic range of this encoding format, given 10⁻⁷ 
	 resolution, is {0 to (2³² - 1) / 10⁷}. This 
	 range translates to {0 to 428.4967296} Hz for vertical and horizontal 
	 frequencies. This submicrosecond precision range is acceptable even for 
	 a provided application. (An error of one microsecond for video signal 
	 synchronization would imply a time drift with a cycle of 
	 10⁷/(60 x 60 x 24) = 115.741 days.)

For a rational number with a finite fractional sequence, use a denominator of the form 10<sup>(length of fractional sequence)</sup>. For a rational number without a finite fractional sequence, a sequence that exceeds the precision that the dynamic range of the denominator allows, or an irrational number, use an appropriate ratio of integers that best represents the value.



