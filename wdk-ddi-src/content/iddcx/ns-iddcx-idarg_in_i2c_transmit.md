---
UID: NS:iddcx.IDARG_IN_I2C_TRANSMIT
title: IDARG_IN_I2C_TRANSMIT (iddcx.h)
description: Gives information about the I2C data being transmitted by the OS.
old-location: display\idarg_in_i2c_transmit.htm
tech.root: display
ms.assetid: 1422f1fc-9653-4e6b-a7dd-c224ce7b9ca0
ms.date: 05/10/2018
ms.keywords: IDARG_IN_I2C_TRANSMIT, IDARG_IN_I2C_TRANSMIT structure [Display Devices], display.idarg_in_i2c_transmit, iddcx/IDARG_IN_I2C_TRANSMIT
ms.topic: struct
f1_keywords:
 - "iddcx/IDARG_IN_I2C_TRANSMIT"
req.header: iddcx.h
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
- iddcx.h
api_name:
- IDARG_IN_I2C_TRANSMIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDARG_IN_I2C_TRANSMIT structure


## -description



                 Gives information about the I2C data being transmitted by the OS.
             


## -struct-fields




### -field SevenBitI2CAddress


                     [in] The address of the I2C device to which data will be transmitted
                 


### -field DataSizeInBytes


                     [in] The size, in bytes, of the buffer pointed to by <b>pData</b>. This parameter must be between 1 and 64, inclusively.
                 


### -field pData


                     [in] A pointer to a buffer that holds the data to be transmitted.
                 

