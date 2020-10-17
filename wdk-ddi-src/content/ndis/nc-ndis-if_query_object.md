---
UID: NC:ndis.IF_QUERY_OBJECT
title: IF_QUERY_OBJECT (ndis.h)
description: The ProviderQueryObject function retrieves information about a network interface.
old-location: netvista\providerqueryobject.htm
tech.root: netvista
ms.assetid: dea90ff0-7620-4364-90dc-2dc5d2e34ce1
ms.date: 05/02/2018
ms.keywords: IFP_QUERY_OBJECT, IFP_QUERY_OBJECT callback function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IF_QUERY_OBJECT
 - ndis/IF_QUERY_OBJECT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndis.h
api_name:
 - IFP_QUERY_OBJECT
product:
 - Windows
---

# IF_QUERY_OBJECT callback function


## -description

The 
  <i>ProviderQueryObject</i> function retrieves information about a network interface.

## -parameters

### -param ProviderIfContext 

[in]
A handle that identifies the interface provider's context area for the interface. The interface
     provider passed this handle to NDIS in a call to the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisifregisterinterface">
     NdisIfRegisterInterface</a> function.

### -param ObjectId 

[in]
An identifier for the object that is the target of the query request. For a list of object
     identifiers (OIDs) that apply to interface providers, see 
     <a href="/windows-hardware/drivers/network/mapping-of-ndis-network-interfaces-to-ndis-oids">NDIS Network Interface
     OIDs</a>.

### -param pOutputBufferLength 

[in, out]
A pointer to an NDIS-supplied variable in which NDIS provides the length of the output buffer. 
     <i>ProviderQueryObject</i> writes the length of the data that it put in the output buffer.

### -param pOutputBuffer 

[out]
A pointer to an NDIS-supplied output buffer in which 
     <i>ProviderQueryObject</i> writes the response to the query request.

## -returns

<i>ProviderQueryObject</i> returns one of the following status values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The operation failed because of insufficient resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The call failed because some of the input parameters were invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_<i>Xxx</i></b></dt>
</dl>
</td>
<td width="60%">
The call failed for some other reason. This function can propagate error codes from the
       functions that it calls or generate an appropriate error code.

</td>
</tr>
</table>

## -remarks

NDIS calls a network interface provider's 
    <i>ProviderQueryObject</i> function to obtain information about an interface that the provider registered.
    For a list of OIDs that apply to interface providers, see 
    <a href="/windows-hardware/drivers/network/mapping-of-ndis-network-interfaces-to-ndis-oids">NDIS Network Interface OIDs</a>.

NDIS calls 
    <i>ProviderQueryObject</i> at IRQL = PASSIVE_LEVEL.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisifregisterinterface">NdisIfRegisterInterface</a>