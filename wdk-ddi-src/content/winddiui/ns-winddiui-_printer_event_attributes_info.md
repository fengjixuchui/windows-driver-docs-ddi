---
UID: NS:winddiui._PRINTER_EVENT_ATTRIBUTES_INFO
title: _PRINTER_EVENT_ATTRIBUTES_INFO (winddiui.h)
description: The PRINTER_EVENT_ATTRIBUTES_INFO structure contains the former attributes and the new attributes for a printer.
old-location: print\printer_event_attributes_info.htm
tech.root: print
ms.assetid: 3c39a515-f4f4-4309-8d4e-461b8835295b
ms.date: 04/20/2018
keywords: ["PRINTER_EVENT_ATTRIBUTES_INFO structure"]
ms.keywords: "*PPRINTER_EVENT_ATTRIBUTES_INFO, PPRINTER_EVENT_ATTRIBUTES_INFO, PPRINTER_EVENT_ATTRIBUTES_INFO structure pointer [Print Devices], PRINTER_EVENT_ATTRIBUTES_INFO, PRINTER_EVENT_ATTRIBUTES_INFO structure [Print Devices], _PRINTER_EVENT_ATTRIBUTES_INFO, print.printer_event_attributes_info, print_interface-graphics_a4fa57f7-bd03-4c38-9c0f-026da9d3535e.xml, winddiui/PPRINTER_EVENT_ATTRIBUTES_INFO, winddiui/PRINTER_EVENT_ATTRIBUTES_INFO"
req.header: winddiui.h
req.include-header: Winddiui.h
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
targetos: Windows
req.typenames: PRINTER_EVENT_ATTRIBUTES_INFO, *PPRINTER_EVENT_ATTRIBUTES_INFO
f1_keywords:
 - _PRINTER_EVENT_ATTRIBUTES_INFO
 - winddiui/_PRINTER_EVENT_ATTRIBUTES_INFO
 - PPRINTER_EVENT_ATTRIBUTES_INFO
 - winddiui/PPRINTER_EVENT_ATTRIBUTES_INFO
 - PRINTER_EVENT_ATTRIBUTES_INFO
 - winddiui/PRINTER_EVENT_ATTRIBUTES_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - winddiui.h
api_name:
 - PRINTER_EVENT_ATTRIBUTES_INFO
---

# _PRINTER_EVENT_ATTRIBUTES_INFO structure


## -description

The PRINTER_EVENT_ATTRIBUTES_INFO structure contains the former attributes and the new attributes for a printer.

## -struct-fields

### -field cbSize

Specifies the size of this structure.

### -field dwOldAttributes

A set of bits describing the current printer attributes.

### -field dwNewAttributes

A set of bits describing the new printer attributes to be applied to the printer.

## -remarks

The bits in the <b>dwOldAttributes</b> and <b>dwNewAttributes</b> members of this structure are set in accordance with the <b>Attributes</b> member of the PRINTER_INFO_2 structure (defined in the Microsoft Windows SDK documentation).

Because this structure might become larger in future operating system versions, anyone using this structure is advised to check that the value in the <b>cbSize</b> member of this structure is at least as large as the offset of the member to be accessed.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvprinterevent">DrvPrinterEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-printerevent">IPrintOemUI::PrinterEvent</a>

