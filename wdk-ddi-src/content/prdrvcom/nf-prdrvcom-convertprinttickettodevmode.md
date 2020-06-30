---
UID: NF:prdrvcom.ConvertPrintTicketToDevMode
title: ConvertPrintTicketToDevMode function (prdrvcom.h)
description: The IPrintTicketProvider::ConvertPrintTicketToDevMode method converts a print ticket to a DEVMODEW structure.
old-location: print\iprintticketprovider_convertprinttickettodevmode.htm
tech.root: print
ms.assetid: 59457b51-5ab5-4e20-a608-a71c799eeeb9
ms.date: 04/20/2018
keywords: ["ConvertPrintTicketToDevMode function"]
ms.keywords: ConvertPrintTicketToDevMode, ConvertPrintTicketToDevMode method [Print Devices], ConvertPrintTicketToDevMode method [Print Devices],IPrintTicketProvider interface, IPrintTicketProvider interface [Print Devices],ConvertPrintTicketToDevMode method, IPrintTicketProvider::ConvertPrintTicketToDevMode, prdrvcom/IPrintTicketProvider::ConvertPrintTicketToDevMode, print.iprintticketprovider_convertprinttickettodevmode, print_ticket-package_5d7b3ff3-0c39-4896-986a-ae2306543644.xml
f1_keywords:
 - "prdrvcom/IPrintTicketProvider.ConvertPrintTicketToDevMode"
req.header: prdrvcom.h
req.include-header: Prdrvcom.h
req.target-type: Desktop
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
- COM
api_location:
- prdrvcom.h
api_name:
- IPrintTicketProvider.ConvertPrintTicketToDevMode
product:
- Windows
targetos: Windows
req.typenames: 
---

# ConvertPrintTicketToDevMode function


## -description


The <code>IPrintTicketProvider::ConvertPrintTicketToDevMode</code> method converts a print ticket to a <a href="https://docs.microsoft.com/windows/win32/api/wingdi/ns-wingdi-devmodew">DEVMODEW</a> structure. 


## -parameters




### -param pPrintTicket [in]

A pointer to the input print ticket. <code>IPrintTicketProvider::ConvertPrintTicketToDevMode</code> converts the settings in the input print ticket into fields in the <a href="https://docs.microsoft.com/windows/win32/api/wingdi/ns-wingdi-devmodew">DEVMODEW</a> structure.


### -param cbDevmodeIn [in]

The size, in bytes, of the input DEVMODEW structure. This size includes both the public and private sections of the DEVMODEW structure. 


### -param pDevmodeIn [in]

A pointer to the input DEVMODEW structure, which contains default settings. The DEVMODEW structure can be the print queue default DEVMODEW structure, or it can be the user default DEVMODEW structure. Because this parameter can represent the user default DEVMODEW structure, the OEM plug-in provider must validate the data in that  structure. A user default DEVMODEW structure might not be valid for a specific driver, for example, when the print queue's driver changes or is upgraded.


### -param pcbDevmodeOut [out]

A pointer to a variable that contains the size, in bytes, of the output <a href="https://docs.microsoft.com/windows/win32/api/wingdi/ns-wingdi-devmodew">DEVMODEW</a> structure.


### -param ppDevmodeOut [out]

A pointer to a variable that contains the address of the output DEVMODEW structure. When <code>IPrintTicketProvider::ConvertPrintTicketToDevMode</code> successfully returns, the members of the output DEVMODEW structure will be reset to reflect the settings in the print ticket. For more information, see the following Remarks section.


## -returns



<code>IPrintTicketProvider::ConvertPrintTicketToDevMode</code> should return S_OK if the operation succeeds. Otherwise, this method should return a standard COM error code.




## -remarks



The core driver calls the <code>IPrintTicketProvider::ConvertPrintTicketToDevMode</code> method before it performs its part of the conversion of a print ticket to a <a href="https://docs.microsoft.com/windows/win32/api/wingdi/ns-wingdi-devicemodew">DEVMODEW</a> structure. In the call to this method, the core driver passes an input print ticket that is fully populated and a DEVMODEW structure that is set to default values. In the conversion, the plug-in must undo any changes that it made to the print ticket during the previous conversion from a DEVMODEW structure to a print ticket. If, during this previous conversion, the plug-in moved a feature from a private namespace to the public namespace, the plug-in must restore the feature to the private namespace in a format that is suitable for the core driver, that is, to the format in which the core driver had previously placed the feature in the print ticket that was provided to the plug-in in the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff553161(v=vs.85)">IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket</a> method. This restoration is necessary so that the core driver can recognize a feature in the print ticket and reflect its settings in the private portion of the core driver's DEVMODEW structure while the core driver performs its part of the print ticket-to-DEVMODEW conversion.

Before the system converts a print ticket back to a <a href="https://docs.microsoft.com/windows/win32/api/wingdi/ns-wingdi-devmodew">DEVMODEW</a> structure, it first loads the default DEVMODEW. The system then calls the provider's <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff554354(v=vs.85)">IPrintTicketProvider::BindPrinter</a> method. This method should then read all of the settings that it supported from the print ticket, and place those settings into the DEVMODEW structure. Note that not all of the features necessarily will be represented, and that often Option instances that are present might not contain all of the Scored Property instances that the provider would normally populate. If the provider makes any changes to the settings that were populated by the system during conversion from print ticket to DEVMODEW, the provider should perform the reverse of that change in this method. After the provider returns, the system then overwrites any public DEVMODEW settings that are represented in the print ticket but that are not explicitly disabled by the provider.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff554375(v=vs.85)">IPrintTicketProvider</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff554360(v=vs.85)">IPrintTicketProvider::ConvertDevModeToPrintTicket</a>
 

 

