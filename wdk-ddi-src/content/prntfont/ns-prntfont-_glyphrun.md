---
UID: NS:prntfont._GLYPHRUN
title: _GLYPHRUN (prntfont.h)
description: The GLYPHRUN structure is one of the structures used to define the contents of glyph translation table files (.gtt files).
old-location: print\glyphrun.htm
tech.root: print
ms.assetid: 21f6631c-dff1-459f-a83e-7aa1d5d2ab2b
ms.date: 04/20/2018
keywords: ["GLYPHRUN structure"]
ms.keywords: "*PGLYPHRUN, GLYPHRUN, GLYPHRUN structure [Print Devices], PGLYPHRUN, PGLYPHRUN structure pointer [Print Devices], _GLYPHRUN, print.glyphrun, print_unidrv-pscript_fonts_591184a3-96f1-4b27-bf6a-d1c512a2bf7e.xml, prntfont/GLYPHRUN, prntfont/PGLYPHRUN"
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
req.typenames: GLYPHRUN, *PGLYPHRUN
f1_keywords:
 - _GLYPHRUN
 - prntfont/_GLYPHRUN
 - PGLYPHRUN
 - prntfont/PGLYPHRUN
 - GLYPHRUN
 - prntfont/GLYPHRUN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - prntfont.h
api_name:
 - GLYPHRUN
---

# _GLYPHRUN structure


## -description

The GLYPHRUN structure is one of the structures used to define the contents of <a href="/windows-hardware/drivers/print/customized-font-management">glyph translation table files</a> (.gtt files).

## -struct-fields

### -field wcLow

Specifies a Unicode value representing the first glyph in the glyph run.

### -field wGlyphCount

Specifies the number of glyphs represented by the glyph run.

## -remarks

A .gtt (glyph translation table) file contains an array of GLYPHRUN structures. Each structure identifies a set of Unicode values for which the printer provides glyphs. The array is described by the <b>IoRunOffset</b> and <b>dwRunCount</b> members of a .gtt file's <a href="/windows-hardware/drivers/ddi/prntfont/ns-prntfont-_uni_glyphsetdata">UNI_GLYPHSETDATA</a> structure.

The GLYPHRUN structures must be defined in ascending order, based on the value of <b>wcLow</b>. Unidrv uses the GLYPHRUN array to generate glyph handles. Unidrv stores these glyph handles in a <a href="/windows/win32/api/winddi/ns-winddi-wcrun">WCRUN</a> array within an <a href="/windows/win32/api/winddi/ns-winddi-fd_glyphset">FD_GLYPHSET</a> structure.

## -see-also

<a href="/windows/win32/api/winddi/ns-winddi-fd_glyphset">FD_GLYPHSET</a>



<a href="/windows-hardware/drivers/ddi/prntfont/ns-prntfont-_uni_glyphsetdata">UNI_GLYPHSETDATA</a>



<a href="/windows/win32/api/winddi/ns-winddi-wcrun">WCRUN</a>