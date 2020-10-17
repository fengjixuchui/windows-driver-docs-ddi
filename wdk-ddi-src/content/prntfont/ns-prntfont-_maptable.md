---
UID: NS:prntfont._MAPTABLE
title: _MAPTABLE (prntfont.h)
description: The MAPTABLE structure is one of the structures used to define the contents of glyph translation table files (.gtt files).
old-location: print\maptable.htm
tech.root: print
ms.assetid: d3dcf7b0-4244-41c1-801e-cf41b20f2d54
ms.date: 04/20/2018
keywords: ["MAPTABLE structure"]
ms.keywords: "*PMAPTABLE, MAPTABLE, MAPTABLE structure [Print Devices], PMAPTABLE, PMAPTABLE structure pointer [Print Devices], _MAPTABLE, print.maptable, print_unidrv-pscript_fonts_c98fd60e-c56a-4f76-8408-e6680bc49525.xml, prntfont/MAPTABLE, prntfont/PMAPTABLE"
req.header: prntfont.h
req.include-header: Prntfont.h
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
req.typenames: MAPTABLE, *PMAPTABLE
f1_keywords:
 - _MAPTABLE
 - prntfont/_MAPTABLE
 - PMAPTABLE
 - prntfont/PMAPTABLE
 - MAPTABLE
 - prntfont/MAPTABLE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - prntfont.h
api_name:
 - MAPTABLE
---

# _MAPTABLE structure


## -description

The MAPTABLE structure is one of the structures used to define the contents of <a href="/windows-hardware/drivers/print/customized-font-management">glyph translation table files</a> (.gtt files).

## -struct-fields

### -field dwSize

Specifies the size, in bytes, of the MAPTABLE structure, including the <b>Trans</b> array.

### -field dwGlyphNum

Specifies the number of elements in the <b>Trans</b> array.

### -field Trans

Is an array of <a href="/windows-hardware/drivers/ddi/prntfont/ns-prntfont-_transdata">TRANSDATA</a> structures.

## -remarks

A .gtt file's MAPTABLE structure, which contains a glyph mapping table, is accessed by a pointer in the file's <a href="/windows-hardware/drivers/ddi/prntfont/ns-prntfont-_uni_glyphsetdata">UNI_GLYPHSETDATA</a> structure. The table maps glyph handles to the character codes or commands that must be sent to the printer in order to print glyphs.

## -see-also

<a href="/windows-hardware/drivers/ddi/prntfont/ns-prntfont-_transdata">TRANSDATA</a>