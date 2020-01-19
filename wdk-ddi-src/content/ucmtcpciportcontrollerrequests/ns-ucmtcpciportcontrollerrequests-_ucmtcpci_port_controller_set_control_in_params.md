---
UID: NS:ucmtcpciportcontrollerrequests._UCMTCPCI_PORT_CONTROLLER_SET_CONTROL_IN_PARAMS
title: _UCMTCPCI_PORT_CONTROLLER_SET_CONTROL_IN_PARAMS (ucmtcpciportcontrollerrequests.h)
description: Stores the values of all control registers. This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL request.
old-location: buses\ucmtcpci_port_controller_set_control_in_params.htm
tech.root: usbref
ms.assetid: d81d76a9-e482-4e22-93c0-a320905ee203
ms.date: 05/07/2018
ms.keywords: "*PUCMTCPCI_PORT_CONTROLLER_SET_CONTROL_IN_PARAMS, PUCMTCPCI_PORT_CONTROLLER_SET_CONTROL_IN_PARAMS, PUCMTCPCI_PORT_CONTROLLER_SET_CONTROL_IN_PARAMS structure pointer [Buses], UCMTCPCI_PORT_CONTROLLER_SET_CONTROL_IN_PARAMS, UCMTCPCI_PORT_CONTROLLER_SET_CONTROL_IN_PARAMS structure [Buses], _UCMTCPCI_PORT_CONTROLLER_SET_CONTROL_IN_PARAMS, buses.ucmtcpci_port_controller_set_control_in_params, ucmtcpciportcontrollerrequests/PUCMTCPCI_PORT_CONTROLLER_SET_CONTROL_IN_PARAMS, ucmtcpciportcontrollerrequests/UCMTCPCI_PORT_CONTROLLER_SET_CONTROL_IN_PARAMS"
ms.topic: struct
f1_keywords:
 - "ucmtcpciportcontrollerrequests/UCMTCPCI_PORT_CONTROLLER_SET_CONTROL_IN_PARAMS"
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
- UCMTCPCI_PORT_CONTROLLER_SET_CONTROL_IN_PARAMS
product:
- Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_SET_CONTROL_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_SET_CONTROL_IN_PARAMS
---

# _UCMTCPCI_PORT_CONTROLLER_SET_CONTROL_IN_PARAMS structure


## -description



             Stores the values of all control registers. This structure is used in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontrollerrequests/ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_control">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL</a> request.


## -struct-fields




### -field PortControllerObject

Handle to the port controller object that the client driver received in the previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontroller/nf-ucmtcpciportcontroller-ucmtcpciportcontrollercreate">UcmTcpciPortControllerCreate</a>.


### -field ControlType


                     A <b>UCMTCPCI_PORT_CONTROLLER_CONTROL_TYPE</b>-value that 
                 indicates the type of control register. This enumeration is declared in UcmTcpciSpec.h.


### -field TCPCControl


                     A 
                 <b>UCMTCPCI_PORT_CONTROLLER_TCPC_CONTROL</b> structure that describes the TCPC_CONTROL Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. This structure is declared in UcmTcpciSpec.h.


### -field RoleControl


                     A 
                 <b>UCMTCPCI_PORT_CONTROLLER_ROLE_CONTROL</b> structure that describes the ROLE_CONTROL Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. This structure is declared in UcmTcpciSpec.h.


### -field FaultControl


                     A 
                 <b>UCMTCPCI_PORT_CONTROLLER_FAULT_CONTROL</b> structure that describes the FAULT_CONTROL Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. This structure is declared in UcmTcpciSpec.h.


### -field PowerControl


                     A 
                 <b>UCMTCPCI_PORT_CONTROLLER_POWER_CONTROL</b> structure that describes the FAULT_POWER Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. This structure is declared in UcmTcpciSpec.h.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontrollerrequests/ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_control">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL</a>
 

 

