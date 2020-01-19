---
UID: NS:printoem.__unnamed_struct_1
title: OEMMEMORYUSAGE (printoem.h)
description: The OEMMEMORYUSAGE structure is used as an input parameter to a rendering plug-in's IPrintOemUni::MemoryUsage method.
old-location: print\oemmemoryusage.htm
tech.root: print
ms.assetid: a7a522b8-7aa2-45b6-9200-407471dca82f
ms.date: 04/20/2018
ms.keywords: "*POEMMEMORYUSAGE, OEMMEMORYUSAGE, OEMMEMORYUSAGE structure [Print Devices], POEMMEMORYUSAGE, POEMMEMORYUSAGE structure pointer [Print Devices], print.oemmemoryusage, print_unidrv-pscript_rendering_c6746c1c-f6c5-4acf-bcd3-bc1f69382dae.xml, printoem/OEMMEMORYUSAGE, printoem/POEMMEMORYUSAGE"
ms.topic: struct
f1_keywords:
 - "printoem/OEMMEMORYUSAGE"
req.header: printoem.h
req.include-header: Printoem.h
req.target-type: Windows
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
- HeaderDef
api_location:
- printoem.h
api_name:
- OEMMEMORYUSAGE
product:
- Windows
targetos: Windows
req.typenames: OEMMEMORYUSAGE, *POEMMEMORYUSAGE
---

# OEMMEMORYUSAGE structure


## -description


The OEMMEMORYUSAGE structure is used as an input parameter to a rendering plug-in's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-memoryusage">IPrintOemUni::MemoryUsage</a> method.


## -struct-fields




### -field dwFixedMemoryUsage

Specifies the amount, in bytes, of fixed-sized memory required by the <b>IPrintOemUni::MemoryUsage</b> method. Supplied by the rendering plug-in.


### -field dwPercentMemoryUsage

Specifies the amount of variably-sized memory required by the <b>IPrintOemUni::MemoryUsage</b> method, expressed as a percentage of the size of the source bitmap received by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-imageprocessing">IPrintOemUni::ImageProcessing</a>. Supplied by the rendering plug-in.


### -field dwMaxBandSize

Specifies the maximum size, in bytes, that can be used for source bitmaps. This is the value that Unidrv uses to subtract from when applying the plug-in supplied values contained in <b>dwFixedMemoryUsage</b> and <b>dwPercentMemoryUsage</b>. Supplied by Unidrv.


## -remarks



The Unidrv driver uses the values in the <b>dwFixedMemoryUsage</b> and <b>dwPercentMemoryUsage</b> members of this structure to determine the optimum size for a GDI drawing surface, taking into account any memory requirements of a rendering plug-in's <b>IPrintOemUni::ImageProcessing</b> method. For more information about how these members are used, see the Remarks section in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-memoryusage">IPrintOemUni::MemoryUsage</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-imageprocessing">IPrintOemUni::ImageProcessing</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-memoryusage">IPrintOemUni::MemoryUsage</a>
 

 

