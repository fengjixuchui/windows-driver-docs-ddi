---
UID: NS:ucmtcpciportcontrollerrequests._UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS
title: _UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS (ucmtcpciportcontrollerrequests.h)
description: Stores the values of TRANSMIT Register. This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT request.
old-location: buses\ucmtcpci_port_controller_set_transmit_in_params.htm
tech.root: usbref
ms.assetid: 115cbcd8-0ee0-4713-a750-e89d269b766e
ms.date: 05/07/2018
ms.keywords: "*PUCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS, PUCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS, PUCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS structure pointer [Buses], UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS, UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS structure [Buses], _UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS, buses.ucmtcpci_port_controller_set_transmit_in_params, ucmtcpciportcontrollerrequests/PUCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS, ucmtcpciportcontrollerrequests/UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS"
ms.topic: struct
f1_keywords:
 - "ucmtcpciportcontrollerrequests/UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS"
req.header: ucmtcpciportcontrollerrequests.h
req.include-header: 
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
- Ucmtcpciportcontrollerrequests.h
api_name:
- UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS
product:
- Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS
---

# _UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS structure


## -description



             Stores the values of TRANSMIT Register. This structure is used in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucmtcpciportcontrollerrequests/ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_transmit">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT</a> request.
                 


## -struct-fields




### -field PortControllerObject

Handle to the port controller object that the client driver received in the previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucmtcpciportcontroller/nf-ucmtcpciportcontroller-ucmtcpciportcontrollercreate">UcmTcpciPortControllerCreate</a>.


### -field Transmit

A pointer to the 
                     <a href="https://msdn.microsoft.com/936256cd-bd44-4139-b83f-6f0cd9fcc3a5">UCMTCPCI_PORT_CONTROLLER_TRANSMIT</a> structure that contains 
                 the value to set in the TRANSMIT  Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. This structure is declared in UcmTcpciSpec.h.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ucmtcpciportcontrollerrequests/ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_transmit">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT</a>
 

 

