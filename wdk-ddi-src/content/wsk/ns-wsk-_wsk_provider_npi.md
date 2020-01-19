---
UID: NS:wsk._WSK_PROVIDER_NPI
title: _WSK_PROVIDER_NPI (wsk.h)
description: The WSK_PROVIDER_NPI structure identifies a provider Network Programming Interface (NPI) implemented by the WSK subsystem.
old-location: netvista\wsk_provider_npi.htm
tech.root: netvista
ms.assetid: 471689f4-d1f6-4785-82df-313fe2ca627a
ms.date: 05/02/2018
ms.keywords: "*PWSK_PROVIDER_NPI, PWSK_PROVIDER_NPI, PWSK_PROVIDER_NPI structure pointer [Network Drivers Starting with Windows Vista], WSK_PROVIDER_NPI, WSK_PROVIDER_NPI structure [Network Drivers Starting with Windows Vista], _WSK_PROVIDER_NPI, netvista.wsk_provider_npi, wsk/PWSK_PROVIDER_NPI, wsk/WSK_PROVIDER_NPI, wskref_cbed200a-9ed1-4cd6-b6be-220799cbae1c.xml"
ms.topic: struct
f1_keywords:
 - "wsk/WSK_PROVIDER_NPI"
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
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
- wsk.h
api_name:
- WSK_PROVIDER_NPI
product:
- Windows
targetos: Windows
req.typenames: WSK_PROVIDER_NPI, *PWSK_PROVIDER_NPI
---

# _WSK_PROVIDER_NPI structure


## -description


The WSK_PROVIDER_NPI structure identifies a provider 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/network/network-programming-interface">Network Programming Interface
  (NPI)</a> implemented by the WSK subsystem.


## -struct-fields




### -field Client

A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wsk-client">WSK_CLIENT</a> structure that was returned through
     the 
     <i>WskProviderNpi</i> parameter of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nf-wsk-wskcaptureprovidernpi">
     WskCaptureProviderNPI</a> function.


### -field Dispatch

A pointer to a constant 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_provider_dispatch">
     WSK_PROVIDER_DISPATCH</a> structure.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wsk-client">WSK_CLIENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_provider_dispatch">WSK_PROVIDER_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nf-wsk-wskcaptureprovidernpi">WskCaptureProviderNPI</a>
 

 

