---
UID: NS:netioddk._NPI_REGISTRATION_INSTANCE
title: _NPI_REGISTRATION_INSTANCE (netioddk.h)
description: The NPI_REGISTRATION_INSTANCE structure defines the data related to the registration of a network module with the NMR.
old-location: netvista\npi_registration_instance.htm
tech.root: netvista
ms.assetid: a368f9d9-a7e0-4b35-ba14-b0919f74029d
ms.date: 05/02/2018
keywords: ["NPI_REGISTRATION_INSTANCE structure"]
ms.keywords: NPI_REGISTRATION_INSTANCE, NPI_REGISTRATION_INSTANCE structure [Network Drivers Starting with Windows Vista], PNPI_REGISTRATION_INSTANCE, PNPI_REGISTRATION_INSTANCE structure pointer [Network Drivers Starting with Windows Vista], _NPI_REGISTRATION_INSTANCE, netioddk/NPI_REGISTRATION_INSTANCE, netioddk/PNPI_REGISTRATION_INSTANCE, netvista.npi_registration_instance, nmrref_a31a8531-bab8-47d5-b79e-a239dcde475f.xml
req.header: netioddk.h
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
targetos: Windows
req.typenames: NPI_REGISTRATION_INSTANCE
f1_keywords:
 - _NPI_REGISTRATION_INSTANCE
 - netioddk/_NPI_REGISTRATION_INSTANCE
 - NPI_REGISTRATION_INSTANCE
 - netioddk/NPI_REGISTRATION_INSTANCE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - netioddk.h
api_name:
 - NPI_REGISTRATION_INSTANCE
---

# _NPI_REGISTRATION_INSTANCE structure


## -description

The NPI_REGISTRATION_INSTANCE structure defines the data related to the registration of a network
  module with the NMR.

## -struct-fields

### -field Version

The version of the NMR with which the network module is registering. A network module should set
     this member to zero.

### -field Size

The size, in bytes, of the NPI_REGISTRATION_INSTANCE structure.

### -field NpiId

A pointer to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/network-programming-interface">NPI</a> identifier for the specific 
     NPI to which the network module
     is registering as either a client or a provider. The NPIID data type is defined as:
     

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef GUID NPIID;
typedef CONST NPIID *PNPIID;</pre>
</td>
</tr>
</table></span></div>

### -field ModuleId

A pointer to an 
     <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff568813(v=vs.85)">NPI_MODULEID</a> structure that uniquely
     identifies the network module.

### -field Number

The implementation number of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/network-programming-interface">NPI</a> for which the network module
     is registering as either a client or a provider. A network module can support multiple implementations
     of the same 
     NPI by registering as either a
     client or a provider of each implementation of the 
     NPI. If there is only one
     implementation of an 
     NPI, this member is set to
     zero.

### -field OPTIONAL

 




#### - NpiSpecificCharacteristics

A pointer to a structure that specifies characteristics that are unique to the network module. The
     contents of the structure are 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/network-programming-interface">NPI</a>-specific. A network module
     should set this member to <b>NULL</b> if it is registering as a client of an NPI that does not define a client
     characteristics structure or if it is registering as a provider of an NPI that does not define a
     provider characteristics structure.

## -remarks

An NPI_REGISTRATION_INSTANCE structure is a member of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/ns-netioddk-_npi_client_characteristics">NPI_CLIENT_CHARACTERISTICS</a> and 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/ns-netioddk-_npi_provider_characteristics">
    NPI_PROVIDER_CHARACTERISTICS</a> structures. These structures are used for registering network modules
    with the NMR.

When the NMR calls a cleint module's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nc-netioddk-npi_client_attach_provider_fn">ClientAttachProvider</a> callback
    function, it passes a pointer to the NPI_REGISTRATION_INSTANCE structure for the provider module to which
    the client module can attach itself. Likewise, when the NMR calls a provider module's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nc-netioddk-npi_provider_attach_client_fn">ProviderAttachClient</a> callback
    function, it passes a pointer to the NPI_REGISTRATION_INSTANCE structure for the client module to which
    the provider module can attach itself.

A network module must make sure that the memory for the NPIID pointed to by the 
    <b>NpiId</b> member, the memory for the 
    <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff568813(v=vs.85)">NPI_MODULEID</a> structure pointed to by the 
    <b>ModuleId</b> member, and the memory for the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/network-programming-interface">NPI</a>-specific characteristics
    structure pointed to by the 
    <b>NpiSpecificCharacteristics</b> member remain valid and resident in memory as long as the network module
    is registered with the NMR.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nc-netioddk-npi_client_attach_provider_fn">ClientAttachProvider</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/ns-netioddk-_npi_client_characteristics">NPI_CLIENT_CHARACTERISTICS</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff568813(v=vs.85)">NPI_MODULEID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/ns-netioddk-_npi_provider_characteristics">NPI_PROVIDER_CHARACTERISTICS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netioddk/nc-netioddk-npi_provider_attach_client_fn">ProviderAttachClient</a>

