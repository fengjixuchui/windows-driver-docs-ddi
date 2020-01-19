---
UID: NS:printoem._OEM_DMEXTRAHEADER
title: _OEM_DMEXTRAHEADER (printoem.h)
description: The OEM_DMEXTRAHEADER structure must be used to define the first members of a set of private DEVMODEW structure members.
old-location: print\oem_dmextraheader.htm
tech.root: print
ms.assetid: fecefdbc-3036-4991-900c-203ae8be254b
ms.date: 04/20/2018
ms.keywords: "*POEM_DMEXTRAHEADER, OEM_DMEXTRAHEADER, OEM_DMEXTRAHEADER structure [Print Devices], POEM_DMEXTRAHEADER, POEM_DMEXTRAHEADER structure pointer [Print Devices], _OEM_DMEXTRAHEADER, print.oem_dmextraheader, print_unidrv-pscript_ui_f356f9c1-f867-4c53-8b12-be48da73de4f.xml, printoem/OEM_DMEXTRAHEADER, printoem/POEM_DMEXTRAHEADER"
ms.topic: struct
f1_keywords:
 - "printoem/OEM_DMEXTRAHEADER"
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
- OEM_DMEXTRAHEADER
product:
- Windows
targetos: Windows
req.typenames: OEM_DMEXTRAHEADER, *POEM_DMEXTRAHEADER
---

# _OEM_DMEXTRAHEADER structure


## -description


The OEM_DMEXTRAHEADER structure must be used to define the first members of a set of private <a href="https://docs.microsoft.com/windows/desktop/api/wingdi/ns-wingdi-_devicemodew">DEVMODEW</a> structure members.


## -struct-fields




### -field dwSize

Total size, in bytes, of the added private DEVMODEW structure members, including the bytes contained in the OEM_DMEXTRAHEADER structure.


### -field dwSignature

Unique signature value that the plug-in also returns when its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-getinfo">IPrintOemUI::GetInfo</a> method receives the OEMGI_GETSIGNATURE flag.


### -field dwVersion

Version number of the user interface plug-in that is defining the private DEVMODEW structure members. The version format is developer-defined.


## -remarks



For more information about adding DEVMODEW structure members, see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/providing-devmode-structure-additions">Providing DEVMODE Structure Additions</a>. 



