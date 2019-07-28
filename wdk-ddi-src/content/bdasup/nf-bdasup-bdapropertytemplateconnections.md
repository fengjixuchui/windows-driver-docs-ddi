---
UID: NF:bdasup.BdaPropertyTemplateConnections
title: BdaPropertyTemplateConnections function (bdasup.h)
description: The BdaPropertyTemplateConnections function retrieves a list of connections that describe how pin types and node types are connected in a template topology.
old-location: stream\bdapropertytemplateconnections.htm
tech.root: stream
ms.assetid: 64b55b53-677a-4977-b865-0a07d34d2530
ms.date: 04/23/2018
ms.keywords: BdaPropertyTemplateConnections, BdaPropertyTemplateConnections function [Streaming Media Devices], bdaref_919b0c2d-5bb9-4e17-8028-79f669ab7b8c.xml, bdasup/BdaPropertyTemplateConnections, stream.bdapropertytemplateconnections
ms.topic: function
f1_keywords:
 - "bdasup/BdaPropertyTemplateConnections"
req.header: bdasup.h
req.include-header: Bdasup.h
req.target-type: Desktop
req.target-min-winverclnt: Available on Microsoft Windows XP and later operating systems. This routine is available on the Windows 2000 platform only if Microsoft DirectX 9.0 and later is installed on that platform.
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
req.lib: Bdasup.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Bdasup.lib
- Bdasup.dll
api_name:
- BdaPropertyTemplateConnections
product:
- Windows
targetos: Windows
req.typenames: 
---

# BdaPropertyTemplateConnections function


## -description


The <b>BdaPropertyTemplateConnections</b> function retrieves a list of connections that describe how pin types and node types are connected in a template topology. 


## -parameters




### -param pIrp




### -param pKSProperty [in]

Points to a <a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a> structure that describes the property and request type of the property request.


### -param pConnectionProperty [out, optional]

Points to an array that receives the list of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-kstopology_connection">KSTOPOLOGY_CONNECTION</a> structures that describe the connections in a template topology. 


#### - Irp [in]

Points to the IRP for the request to retrieve the list of connections. The BDA minidriver receives this IRP with the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-bda-template-connections">KSPROPERTY_BDA_TEMPLATE_CONNECTIONS</a> request.


## -returns



Returns STATUS_SUCCESS or an appropriate error code. 




## -remarks



A BDA minidriver calls the <b>BdaPropertyTemplateConnections</b> function to retrieve the list of template connections after the minidriver receives a <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-bda-template-connections">KSPROPERTY_BDA_TEMPLATE_CONNECTIONS</a> request of the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/kspropsetid-bdatopology">KSPROPSETID_BdaTopology</a> property set from the network provider. Most BDA minidrivers can define dispatch and filter-automation tables so that those minidrivers dispatch the <b>BdaPropertyTemplateConnections</b> function directly, without intercepting this request using an internal get-handler (<a href="https://docs.microsoft.com/previous-versions/ff567177(v=vs.85)">KStrGetPropertyHandler</a>). See <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/defining-automation-tables">Defining Automation Tables</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/determining-bda-device-topology">Determining BDA Device Topology</a> for more information. 

The BDA minidriver provided a list of connections to the BDA support library in an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-kstopology_connection">KSTOPOLOGY_CONNECTION</a> structures when the BDA minidriver passed the BDA filter template (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bdasup/ns-bdasup-_bda_filter_template">BDA_FILTER_TEMPLATE</a>) in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bdasup/nf-bdasup-bdacreatefilterfactory">BdaCreateFilterFactory</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bdasup/nf-bdasup-bdainitfilter">BdaInitFilter</a> function calls. This array is a representation of all the possible connections between node and pin types that can be made within the filter or between the filter and adjoining filters. The <b>BdaPropertyTemplateConnections</b> function returns this array.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bdasup/ns-bdasup-_bda_filter_template">BDA_FILTER_TEMPLATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bdasup/nf-bdasup-bdacreatefilterfactory">BdaCreateFilterFactory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bdasup/nf-bdasup-bdainitfilter">BdaInitFilter</a>



<a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-bda-template-connections">KSPROPERTY_BDA_TEMPLATE_CONNECTIONS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/kspropsetid-bdatopology">KSPROPSETID_BdaTopology</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-kstopology_connection">KSTOPOLOGY_CONNECTION</a>
 

 

