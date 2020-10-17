---
UID: NS:d3dkmthk._D3DKMT_GETMULTISAMPLEMETHODLIST
title: _D3DKMT_GETMULTISAMPLEMETHODLIST (d3dkmthk.h)
description: The D3DKMT_GETMULTISAMPLEMETHODLIST structure describes parameters to retrieve the list of multiple-sample methods for an allocation.
old-location: display\d3dkmt_getmultisamplemethodlist.htm
ms.assetid: 138f6f75-3986-42f8-840c-d48edb271203
ms.date: 05/10/2018
keywords: ["D3DKMT_GETMULTISAMPLEMETHODLIST structure"]
ms.keywords: D3DKMT_GETMULTISAMPLEMETHODLIST, D3DKMT_GETMULTISAMPLEMETHODLIST structure [Display Devices], OpenGL_Structs_ccb62d63-4a70-4fb4-b6db-d8a5e585b222.xml, _D3DKMT_GETMULTISAMPLEMETHODLIST, d3dkmthk/D3DKMT_GETMULTISAMPLEMETHODLIST, display.d3dkmt_getmultisamplemethodlist
req.header: d3dkmthk.h
req.include-header: D3dumddi.h
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
targetos: Windows
tech.root: display
req.typenames: D3DKMT_GETMULTISAMPLEMETHODLIST
f1_keywords:
 - _D3DKMT_GETMULTISAMPLEMETHODLIST
 - d3dkmthk/_D3DKMT_GETMULTISAMPLEMETHODLIST
 - D3DKMT_GETMULTISAMPLEMETHODLIST
 - d3dkmthk/D3DKMT_GETMULTISAMPLEMETHODLIST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - D3DKMT_GETMULTISAMPLEMETHODLIST
---

# _D3DKMT_GETMULTISAMPLEMETHODLIST structure


## -description

The D3DKMT_GETMULTISAMPLEMETHODLIST structure describes parameters to retrieve the list of multiple-sample methods for an allocation.

## -struct-fields

### -field hAdapter

[in] A handle to the graphics adapter.

### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the allocation is on.

### -field Width

[in] The width of the allocation, in pixels.

### -field Height

[in] The height of the allocation, in pixels.

### -field Format

[in] A <a href="/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a>-typed value that indicates the pixel format of the allocation.

### -field pMethodList

[out] An array of <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_multisamplemethod">D3DKMT_MULTISAMPLEMETHOD</a> structures that describe the list of multiple-sampling methods used for the allocation; otherwise, this member is <b>NULL</b>.

### -field MethodCount

[in/out] On input, the number of elements that the array that is specified by <b>pMethodList</b> can hold. On output, this member specifies the required number of elements that the array that is specified by <b>pMethodList</b> should hold.

## -remarks

If the runtime returns a non-<b>NULL</b> value in <b>pMethodList</b>, the runtime returns a value in <b>MethodCount</b> that represents the number of elements that the array can hold. If the runtime returns <b>NULL</b> in <b>pMethodList</b>, the runtime returns a value in <b>MethodCount</b> that represents the size of the array buffer that is required, in number of elements.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a>



<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtgetmultisamplemethodlist">D3DKMTGetMultisampleMethodList</a>



<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_multisamplemethod">D3DKMT_MULTISAMPLEMETHOD</a>