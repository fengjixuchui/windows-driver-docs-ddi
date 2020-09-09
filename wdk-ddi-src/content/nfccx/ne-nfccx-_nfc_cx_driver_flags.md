---
UID: NE:nfccx._NFC_CX_DRIVER_FLAGS
title: _NFC_CX_DRIVER_FLAGS (nfccx.h)
description: Specifies run-time driver flags.
old-location: nfpdrivers\nfc_cx_driver_flags.htm
tech.root: nfpdrivers
ms.assetid: 161CA2C2-F4F4-49F3-9007-ADFBDA905119
ms.date: 02/15/2018
keywords: ["NFC_CX_DRIVER_FLAGS enumeration"]
ms.keywords: "*PNFC_CX_DRIVER_FLAGS, NFC_CX_DRIVER_DISABLE_HOST_CARD_EMULATION, NFC_CX_DRIVER_DISABLE_NFCEE_ACTION_NTF, NFC_CX_DRIVER_DISABLE_NFCEE_DISCOVERY, NFC_CX_DRIVER_DISABLE_RECOVERY_MODE, NFC_CX_DRIVER_DISABLE_WTD_TIMER, NFC_CX_DRIVER_ENABLE_EEPROM_WRITE_PROTECTION, NFC_CX_DRIVER_FLAGS, NFC_CX_DRIVER_HCI_NETWORK_PER_NFCEE, NFC_CX_DRIVER_ISODEP_RNAK_PRESENCE_CHK_SUPPORTED, NFC_CX_DRIVER_RF_ROUTING_POWER_SUB_STATES_SUPPORTED, PNFC_CX_DRIVER_FLAGS, PNFC_CX_DRIVER_FLAGS enumeration pointer [Near-Field Proximity Drivers], _NFC_CX_DRIVER_FLAGS, _NFC_CX_DRIVER_FLAGS enumeration [Near-Field Proximity Drivers], nfccx/NFC_CX_DRIVER_DISABLE_HOST_CARD_EMULATION, nfccx/NFC_CX_DRIVER_DISABLE_NFCEE_ACTION_NTF, nfccx/NFC_CX_DRIVER_DISABLE_NFCEE_DISCOVERY, nfccx/NFC_CX_DRIVER_DISABLE_RECOVERY_MODE, nfccx/NFC_CX_DRIVER_DISABLE_WTD_TIMER, nfccx/NFC_CX_DRIVER_ENABLE_EEPROM_WRITE_PROTECTION, nfccx/NFC_CX_DRIVER_HCI_NETWORK_PER_NFCEE, nfccx/NFC_CX_DRIVER_ISODEP_RNAK_PRESENCE_CHK_SUPPORTED, nfccx/NFC_CX_DRIVER_RF_ROUTING_POWER_SUB_STATES_SUPPORTED, nfccx/PNFC_CX_DRIVER_FLAGS, nfccx/_NFC_CX_DRIVER_FLAGS, nfpdrivers.nfc_cx_driver_flags"
req.header: nfccx.h
req.include-header: Ncidef.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: None supported
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
req.typenames: NFC_CX_DRIVER_FLAGS, *PNFC_CX_DRIVER_FLAGS
f1_keywords:
 - _NFC_CX_DRIVER_FLAGS
 - nfccx/_NFC_CX_DRIVER_FLAGS
 - PNFC_CX_DRIVER_FLAGS
 - nfccx/PNFC_CX_DRIVER_FLAGS
 - NFC_CX_DRIVER_FLAGS
 - nfccx/NFC_CX_DRIVER_FLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - nfccx.h
api_name:
 - NFC_CX_DRIVER_FLAGS
---

# _NFC_CX_DRIVER_FLAGS enumeration


## -description

Specifies run-time driver flags.

## -enum-fields

### -field NFC_CX_DRIVER_DISABLE_WTD_TIMER

Disable watchdog timer in CX.

### -field NFC_CX_DRIVER_DISABLE_NFCEE_DISCOVERY

Disable NFCEE discovery.

### -field NFC_CX_DRIVER_DISABLE_RECOVERY_MODE

Disable NCI recovery mechanism in CX.

### -field NFC_CX_DRIVER_DISABLE_HOST_CARD_EMULATION

Disable host card emulation feature.

### -field NFC_CX_DRIVER_HCI_NETWORK_PER_NFCEE

NFCC implements a separate HCI network per NFCEE.

### -field NFC_CX_DRIVER_DISABLE_NFCEE_ACTION_NTF

Disable NFCEE action notification.

### -field NFC_CX_DRIVER_ENABLE_EEPROM_WRITE_PROTECTION

Enable opt to over-write only when configs change.

### -field NFC_CX_DRIVER_ISODEP_RNAK_PRESENCE_CHK_SUPPORTED

The R-NAK command for ISO-DEP will be used for presence check.

### -field NFC_CX_DRIVER_RF_ROUTING_POWER_SUB_STATES_SUPPORTED

Indicates support for RF routing switched ON power sub-states.

## -remarks

The NFC CX allows the NFC client driver to provide some driver flags that can be used to configure the run-time implementation of the class extension. These flags enable the NFC CX to implement some standard NCI operations slightly differently to support different firmware implementations due to ambiguities in the NCI specification.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="https://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>

