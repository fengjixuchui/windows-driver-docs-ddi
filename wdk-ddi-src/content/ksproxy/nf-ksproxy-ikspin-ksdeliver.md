---
UID: NF:ksproxy.IKsPin.KsDeliver
title: IKsPin::KsDeliver (ksproxy.h)
description: The KsDeliver method delivers a media sample from an output pin to an input pin, continues an I/O operation by retrieving the next buffer from an allocator, and submits the buffer to the associated device.
old-location: stream\ikspin_ksdeliver.htm
tech.root: stream
ms.assetid: e527a659-7ed5-4262-bed2-3bab58919401
ms.date: 04/23/2018
keywords: ["IKsPin::KsDeliver"]
ms.keywords: IKsPin interface [Streaming Media Devices],KsDeliver method, IKsPin.KsDeliver, IKsPin::KsDeliver, KsDeliver, KsDeliver method [Streaming Media Devices], KsDeliver method [Streaming Media Devices],IKsPin interface, ksproxy/IKsPin::KsDeliver, ksproxy_3608c6b5-20e3-43e1-b1aa-a283f8d00f17.xml, stream.ikspin_ksdeliver
f1_keywords:
 - "ksproxy/IKsPin.KsDeliver"
 - "IKsPin.KsDeliver"
req.header: ksproxy.h
req.include-header: Ksproxy.h
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- ksproxy.h
api_name:
- IKsPin.KsDeliver
targetos: Windows
req.typenames: 
---

# IKsPin::KsDeliver


## -description


The <b>KsDeliver</b> method delivers a media sample from an output pin to an input pin, continues an I/O operation by retrieving the next buffer from an allocator, and submits the buffer to the associated device.


## -parameters




### -param Sample [in]

Pointer to the <b>IMediaSample</b> interface for the associated media sample.


### -param Flags [in]

Specifies a bitmask enumerating information about the stream header of the media sample. A bitwise OR combination of the following flags is possible:

KSSTREAM_HEADER_OPTIONSF_SPLICEPOINT

KSSTREAM_HEADER_OPTIONSF_PREROLL

KSSTREAM_HEADER_OPTIONSF_DATADISCONTINUITY

KSSTREAM_HEADER_OPTIONSF_TYPECHANGED

KSSTREAM_HEADER_OPTIONSF_TIMEVALID

KSSTREAM_HEADER_OPTIONSF_TIMEDISCONTINUITY

KSSTREAM_HEADER_OPTIONSF_FLUSHONPAUSE

KSSTREAM_HEADER_OPTIONSF_DURATIONVALID

KSSTREAM_HEADER_OPTIONSF_ENDOFSTREAM

KSSTREAM_HEADER_OPTIONSF_LOOPEDDATA

These flags are defined in the <b>OptionsFlags</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksstream_header">KSSTREAM_HEADER</a> structure description.

The pin connection checks for the end-of-stream flag (KSSTREAM_HEADER_OPTIONSF_ENDOFSTREAM) to determine if it must deliver an end-of-stream event after the sample completes.


## -returns



Returns NOERROR if successful; otherwise, returns an error code.




## -remarks



An interface handler (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nn-ksproxy-iksinterfacehandler">IKsInterfaceHandler</a>) calls <b>KsDeliver</b> on the output pin of a filter to deliver a media sample to the input pin of another filter. These input and output pins are connected. 

For an input pin, <b>KsDeliver</b> is an invalid entry point and returns EFAIL. 

For more information about <b>IMediaSample</b>, see the Microsoft Windows SDK documentation.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nn-ksproxy-iksinterfacehandler">IKsInterfaceHandler</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksinterfacehandler-kscompleteio">IKsInterfaceHandler::KsCompleteIo</a>
 

 

