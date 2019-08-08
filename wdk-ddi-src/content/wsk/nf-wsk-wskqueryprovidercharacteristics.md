---
UID: NF:wsk.WskQueryProviderCharacteristics
title: WskQueryProviderCharacteristics function (wsk.h)
description: The WskQueryProviderCharacteristics function queries the range of WSK NPI versions supported by the WSK subsystem.
old-location: netvista\wskqueryprovidercharacteristics.htm
tech.root: netvista
ms.assetid: b8a81d7e-abab-4343-a044-ac9dd913c7f2
ms.date: 05/02/2018
ms.keywords: WskQueryProviderCharacteristics, WskQueryProviderCharacteristics function [Network Drivers Starting with Windows Vista], netvista.wskqueryprovidercharacteristics, wsk/WskQueryProviderCharacteristics, wskref_dbe0fc4a-6df6-46aa-a17b-d3835f5d429b.xml
ms.topic: function
f1_keywords:
 - "wsk/WskQueryProviderCharacteristics"
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Universal
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
req.lib: Netio.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- netio.lib
- netio.dll
api_name:
- WskQueryProviderCharacteristics
product:
- Windows
targetos: Windows
req.typenames: 
---

# WskQueryProviderCharacteristics function


## -description


The 
  <b>WskQueryProviderCharacteristics</b> function queries the range of WSK NPI versions supported by the WSK
  subsystem.


## -parameters




### -param WskRegistration [in]

A pointer to the memory location initialized by 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/nf-wsk-wskregister">WskRegister</a> that identifies a WSK
     application's registration instance.


### -param WskProviderCharacteristics [out]

A pointer to the range of WSK NPI versions supported by the WSK subsystem.


## -returns



<b>WskQueryProviderCharacteristics</b> returns one of the following NTSTATUS codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The query completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_NOT_READY</b></dt>
</dl>
</td>
<td width="60%">
The provider NPI was not yet available.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
The query failed.

</td>
</tr>
</table>
 




## -remarks



WSK clients can use this function to determine the WSK NPI versions supported by the WSK
    subsystem.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/ns-wsk-_wsk_provider_characteristics">WSK_PROVIDER_CHARACTERISTICS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wsk/ns-wsk-_wsk_registration">WSK_REGISTRATION</a>
 

 

