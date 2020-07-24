---
UID: NE:d3d10umddi.D3D11_1DDI_BUS_TYPE
title: D3D11_1DDI_BUS_TYPE (d3d10umddi.h)
description: Specifies the type of I/O bus that is used by the graphics adapter.
old-location: display\d3d11_1ddi_bus_type.htm
ms.assetid: 07cf1893-1ced-4bfa-a6f7-ec71345b9f18
ms.date: 05/10/2018
keywords: ["D3D11_1DDI_BUS_TYPE enumeration"]
ms.keywords: D3D11_1DDI_BUS_IMPL_MODIFIER_DAUGHTER_BOARD_CONNECTOR, D3D11_1DDI_BUS_IMPL_MODIFIER_DAUGHTER_BOARD_CONNECTOR_INSIDE_OF_NUAE, D3D11_1DDI_BUS_IMPL_MODIFIER_INSIDE_OF_CHIPSET, D3D11_1DDI_BUS_IMPL_MODIFIER_NON_STANDARD, D3D11_1DDI_BUS_IMPL_MODIFIER_TRACKS_ON_MOTHER_BOARD_TO_CHIP, D3D11_1DDI_BUS_IMPL_MODIFIER_TRACKS_ON_MOTHER_BOARD_TO_SOCKET, D3D11_1DDI_BUS_TYPE, D3D11_1DDI_BUS_TYPE enumeration [Display Devices], D3D11_1DDI_BUS_TYPE_AGP, D3D11_1DDI_BUS_TYPE_OTHER, D3D11_1DDI_BUS_TYPE_PCI, D3D11_1DDI_BUS_TYPE_PCIEXPRESS, D3D11_1DDI_BUS_TYPE_PCIX, d3d10umddi/D3D11_1DDI_BUS_IMPL_MODIFIER_DAUGHTER_BOARD_CONNECTOR, d3d10umddi/D3D11_1DDI_BUS_IMPL_MODIFIER_DAUGHTER_BOARD_CONNECTOR_INSIDE_OF_NUAE, d3d10umddi/D3D11_1DDI_BUS_IMPL_MODIFIER_INSIDE_OF_CHIPSET, d3d10umddi/D3D11_1DDI_BUS_IMPL_MODIFIER_NON_STANDARD, d3d10umddi/D3D11_1DDI_BUS_IMPL_MODIFIER_TRACKS_ON_MOTHER_BOARD_TO_CHIP, d3d10umddi/D3D11_1DDI_BUS_IMPL_MODIFIER_TRACKS_ON_MOTHER_BOARD_TO_SOCKET, d3d10umddi/D3D11_1DDI_BUS_TYPE, d3d10umddi/D3D11_1DDI_BUS_TYPE_AGP, d3d10umddi/D3D11_1DDI_BUS_TYPE_OTHER, d3d10umddi/D3D11_1DDI_BUS_TYPE_PCI, d3d10umddi/D3D11_1DDI_BUS_TYPE_PCIEXPRESS, d3d10umddi/D3D11_1DDI_BUS_TYPE_PCIX, display.d3d11_1ddi_bus_type
f1_keywords:
 - "d3d10umddi/D3D11_1DDI_BUS_TYPE"
 - "D3D11_1DDI_BUS_TYPE"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
- D3d10umddi.h
api_name:
- D3D11_1DDI_BUS_TYPE
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDI_BUS_TYPE
---

# D3D11_1DDI_BUS_TYPE enumeration


## -description


Specifies the type of I/O bus that is used by the graphics adapter.


## -enum-fields




### -field D3D11_1DDI_BUS_TYPE_OTHER

Indicates a type of bus other than the types listed here.


### -field D3D11_1DDI_BUS_TYPE_PCI

PCI bus.


### -field D3D11_1DDI_BUS_TYPE_PCIX

PCI-X bus.


### -field D3D11_1DDI_BUS_TYPE_PCIEXPRESS

PCI Express bus.


### -field D3D11_1DDI_BUS_TYPE_AGP

Accelerated Graphics Port (AGP) bus.


### -field D3D11_1DDI_BUS_IMPL_MODIFIER_INSIDE_OF_CHIPSET

The implementation for the graphics adapter is in a motherboard chipset's north bridge. This flag implies that data never goes over an expansion bus (such as PCI or AGP) when it is transferred from main memory to the graphics adapter.


### -field D3D11_1DDI_BUS_IMPL_MODIFIER_TRACKS_ON_MOTHER_BOARD_TO_CHIP

Indicates that the graphics adapter is connected to a motherboard chipset's north bridge by tracks on the motherboard, and all of the graphics adapter's chips are soldered to the motherboard. This flag implies that data never goes over an expansion bus (such as PCI or AGP) when it is transferred from main memory to the graphics adapter.


### -field D3D11_1DDI_BUS_IMPL_MODIFIER_TRACKS_ON_MOTHER_BOARD_TO_SOCKET

The graphics adapter is connected to a motherboard chipset's north bridge by tracks on the motherboard, and all of the graphics adapter's chips are connected through sockets to the motherboard.


### -field D3D11_1DDI_BUS_IMPL_MODIFIER_DAUGHTER_BOARD_CONNECTOR

The graphics adapter is connected to the motherboard through a daughterboard connector.


### -field D3D11_1DDI_BUS_IMPL_MODIFIER_DAUGHTER_BOARD_CONNECTOR_INSIDE_OF_NUAE

The graphics adapter is connected to the motherboard through a daughterboard connector, and the graphics adapter is inside an enclosure that is not user accessible.


### -field D3D11_1DDI_BUS_IMPL_MODIFIER_NON_STANDARD

One of the D3D11_1DDI_BUS_IMPL_MODIFIER_Xxx flags is set.

