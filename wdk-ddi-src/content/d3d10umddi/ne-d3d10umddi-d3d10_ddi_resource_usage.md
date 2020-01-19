---
UID: NE:d3d10umddi.D3D10_DDI_RESOURCE_USAGE
title: D3D10_DDI_RESOURCE_USAGE (d3d10umddi.h)
description: The D3D10_DDI_RESOURCE_USAGE enumeration type contains values that identify how a resource is used.
old-location: display\d3d10_ddi_resource_usage.htm
ms.assetid: f412b665-3489-4200-8fb8-7b6eb564ba98
ms.date: 05/10/2018
ms.keywords: D3D10_DDI_RESOURCE_USAGE, D3D10_DDI_RESOURCE_USAGE enumeration [Display Devices], D3D10_DDI_USAGE_DEFAULT, D3D10_DDI_USAGE_DYNAMIC, D3D10_DDI_USAGE_IMMUTABLE, D3D10_DDI_USAGE_STAGING, UMDisplayDriver_Dx10param_Structs_1d4cddbd-58a0-45b3-b7a9-8b55654c37a7.xml, d3d10umddi/D3D10_DDI_RESOURCE_USAGE, d3d10umddi/D3D10_DDI_USAGE_DEFAULT, d3d10umddi/D3D10_DDI_USAGE_DYNAMIC, d3d10umddi/D3D10_DDI_USAGE_IMMUTABLE, d3d10umddi/D3D10_DDI_USAGE_STAGING, display.d3d10_ddi_resource_usage
ms.topic: enum
f1_keywords:
 - "d3d10umddi/D3D10_DDI_RESOURCE_USAGE"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
- d3d10umddi.h
api_name:
- D3D10_DDI_RESOURCE_USAGE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D10_DDI_RESOURCE_USAGE
---

# D3D10_DDI_RESOURCE_USAGE enumeration


## -description


The D3D10_DDI_RESOURCE_USAGE enumeration type contains values that identify how a resource is used.


## -enum-fields




### -field D3D10_DDI_USAGE_DEFAULT

The resource is used at the highest level. An application cannot map to default resources. The resources can be bound to the graphics pipeline and used as copy destinations and sources. The Microsoft Direct3D runtime can call only the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourceupdatesubresourceup">ResourceUpdateSubresourceUP</a> function to update the contents directly with the CPU.


### -field D3D10_DDI_USAGE_IMMUTABLE

The resource is immutable and cannot be mapped or copied to. The resource can be bound to the pipeline and copied from. The Direct3D runtime cannot call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourceupdatesubresourceup">ResourceUpdateSubresourceUP</a> to update the contents; therefore, the contents of the resource are provided at creation time.


### -field D3D10_DDI_USAGE_DYNAMIC

The resource is dynamic and should be resident in non-local video memory. The resource can also be mapped. However, when the resource is mapped, the CPU can only write (and not read) to the resource. Therefore, when mapped, the Direct3D runtime must use the D3D10_DDI_MAP_WRITE_DISCARD or D3D10_DDI_MAP_WRITE_NOOVERWRITE access level in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourcemap">ResourceMap</a> function. Because this resource can be mapped, the runtime cannot call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourceupdatesubresourceup">ResourceUpdateSubresourceUP</a>. 


### -field D3D10_DDI_USAGE_STAGING

The resource is a staging resource, which the user-mode display driver should allocate as system memory. The driver allocates system memory to ensure the proper alignment and pitch to enable DMA access to such a region of memory. Staging can be mapped by the application but cannot be bound to the 3-D graphics pipeline. However, staging resources are frequently used to copy between other non-mappable resources. Because this resource can be mapped, the runtime cannot call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourceupdatesubresourceup">ResourceUpdateSubresourceUP</a>. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createresource">D3D10DDIARG_CREATERESOURCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourcemap">ResourceMap</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_resourceupdatesubresourceup">ResourceUpdateSubresourceUP</a>
 

 

