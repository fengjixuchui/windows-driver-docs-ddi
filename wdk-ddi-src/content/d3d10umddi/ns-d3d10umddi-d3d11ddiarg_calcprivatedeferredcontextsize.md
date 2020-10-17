---
UID: NS:d3d10umddi.D3D11DDIARG_CALCPRIVATEDEFERREDCONTEXTSIZE
title: D3D11DDIARG_CALCPRIVATEDEFERREDCONTEXTSIZE (d3d10umddi.h)
description: The D3D11DDIARG_CALCPRIVATEDEFERREDCONTEXTSIZE structure describes the parameters that the user-mode display driver uses to calculate the size of a memory block that the driver requires to store frequently-accessed data.
old-location: display\d3d11ddiarg_calcprivatedeferredcontextsize.htm
ms.assetid: 7889400e-bd26-43b5-a860-bea9f9217002
ms.date: 05/10/2018
keywords: ["D3D11DDIARG_CALCPRIVATEDEFERREDCONTEXTSIZE structure"]
ms.keywords: D3D11DDIARG_CALCPRIVATEDEFERREDCONTEXTSIZE, D3D11DDIARG_CALCPRIVATEDEFERREDCONTEXTSIZE structure [Display Devices], UMDisplayDriver_Dx11param_Structs_eca4d605-7188-46b1-b429-04094a9f7db6.xml, d3d10umddi/D3D11DDIARG_CALCPRIVATEDEFERREDCONTEXTSIZE, display.d3d11ddiarg_calcprivatedeferredcontextsize
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11DDIARG_CALCPRIVATEDEFERREDCONTEXTSIZE is supported beginning with the Windows 7 operating system.
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
tech.root: display
req.typenames: D3D11DDIARG_CALCPRIVATEDEFERREDCONTEXTSIZE
f1_keywords:
 - D3D11DDIARG_CALCPRIVATEDEFERREDCONTEXTSIZE
 - d3d10umddi/D3D11DDIARG_CALCPRIVATEDEFERREDCONTEXTSIZE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3D11DDIARG_CALCPRIVATEDEFERREDCONTEXTSIZE
---

# D3D11DDIARG_CALCPRIVATEDEFERREDCONTEXTSIZE structure


## -description

The D3D11DDIARG_CALCPRIVATEDEFERREDCONTEXTSIZE structure describes the parameters that the user-mode display driver uses to calculate the size of a memory block that the driver requires to store frequently-accessed data.

## -struct-fields

### -field Flags

[in] A valid bitwise OR of flag values that identify how to create a rendering device. The Direct3D runtime supports the following flags:  





#### D3D10DDI_CREATEDEVICE_FLAG_DISABLE_EXTRA_THREAD_CREATION (0x1)

If this flag is set, the user-mode display driver should not run multiple threads simultaneously when it processes calls to its functions from the Direct3D runtime. A driver can typically start and run multiple threads to process operations faster, unless D3D10DDI_CREATEDEVICE_FLAG_DISABLE_EXTRA_THREAD_CREATION is set.



#### D3D11DDI_CREATEDEVICE_FLAG_SINGLETHREADED (0x10)

This flag informs the user-mode display driver that the application is single threaded. The Direct3D version 11 runtime allows multiple application threads to enter the driver if the driver allows this mode of operation. However, not all applications can run multiple threads. If this flag is set, the driver will not expect multiple threads to enter it and run simultaneously. The driver can avoid synchronization if this flag is present.



#### The flag that is set in the 0xE mask of the Flags member

This flag represents the level of 3-D pipeline that the driver should support for the display device. The driver uses the following constant and macros to extract one of the values from the <a href="/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11ddi_3dpipelinelevel">D3D11DDI_3DPIPELINELEVEL</a> enumeration that represent the 3-D pipeline level to support. The value in the <b>Flags</b> member is formatted like the <b>Caps</b> member of the <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_3dpipelinesupport_caps">D3D11DDI_3DPIPELINESUPPORT_CAPS</a> structure.

```cpp
#define D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_SHIFT (0x1)
#define D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_MASK (0x7 << D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_SHIFT)
#define D3D11DDI_EXTRACT_3DPIPELINELEVEL_FROM_FLAGS( Flags ) \
    ((D3D11DDI_3DPIPELINELEVEL)(((Flags) & D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_MASK) >> \
    D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_SHIFT))
```

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11ddi_3dpipelinelevel">D3D11DDI_3DPIPELINELEVEL</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_3dpipelinesupport_caps">D3D11DDI_3DPIPELINESUPPORT_CAPS</a>