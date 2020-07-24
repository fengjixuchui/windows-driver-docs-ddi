---
UID: NS:storport._STOR_DEVICE_CAPABILITIES_EX
title: _STOR_DEVICE_CAPABILITIES_EX (storport.h)
description: The STOR_DEVICE_CAPABILITIES_EX structure reports device capabilities to the Storport driver in response to a capabilities query in a SCSI request block (SRB) with a function of SRB_FUNCTION_PNP.
old-location: storage\stor_device_capabilities_ex.htm
tech.root: storage
ms.assetid: 6DCD1F8A-45E3-4084-9688-AE59597D65AF
ms.date: 03/29/2018
keywords: ["_STOR_DEVICE_CAPABILITIES_EX structure"]
ms.keywords: "*PSTOR_DEVICE_CAPABILITIES_EX, PSTOR_DEVICE_CAPABILITIES_EX, PSTOR_DEVICE_CAPABILITIES_EX structure pointer [Storage Devices], STOR_DEVICE_CAPABILITIES_EX, STOR_DEVICE_CAPABILITIES_EX structure [Storage Devices], _STOR_DEVICE_CAPABILITIES_EX, storage.stor_device_capabilities_ex, storport/PSTOR_DEVICE_CAPABILITIES_EX, storport/STOR_DEVICE_CAPABILITIES_EX"
f1_keywords:
 - "storport/STOR_DEVICE_CAPABILITIES_EX"
 - "STOR_DEVICE_CAPABILITIES_EX"
req.header: storport.h
req.include-header: Storport.h, Minitape.h, Srb.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
- storport.h
api_name:
- STOR_DEVICE_CAPABILITIES_EX
targetos: Windows
req.typenames: STOR_DEVICE_CAPABILITIES_EX, *PSTOR_DEVICE_CAPABILITIES_EX
---

# _STOR_DEVICE_CAPABILITIES_EX structure


## -description


The <b>STOR_DEVICE_CAPABILITIES_EX</b> structure reports device capabilities to the Storport driver in response to a capabilities query in a SCSI request block (SRB) with a function of SRB_FUNCTION_PNP.<b> STOR_DEVICE_CAPABILITIES_EX</b> is a subset of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_capabilities">DEVICE_CAPABILITIES</a> structure containing the members relevant to storage devices.


## -struct-fields




### -field Version

Specifies the version of the structure. Set to STOR_DEVICE_CAPABILITIES_EX_VERSION_1 by Storport.


### -field Size

Specifies the size of the structure. Set to <b>sizeof</b>(STOR_DEVICE_CAPABILITIES_EX) by Storport.


### -field DeviceD1

Specifies whether the device hardware supports the D1 power state. Miniport drivers set this bit to 0.


### -field DeviceD2

Specifies whether the device hardware supports the D2 power state. Miniport drivers set this bit to 0.


### -field LockSupported

Specifies whether the device supports physical-device locking that prevents device ejection. This member pertains to ejecting a LUN or a unit device.


### -field EjectSupported

Specifies whether the device supports software-controlled device ejection while the system is in the <b>PowerSystemWorking</b> state. This member pertains to ejecting a LUN or unit device.


### -field Removable

 


### -field DockDevice

Specifies whether the device is a docking peripheral.


### -field UniqueID

Specifies whether the device's instance ID is unique system-wide. This bit is clear if the instance ID is unique only within the scope of the bus.


### -field SilentInstall

Specifies whether <b>Device Manager</b> should suppress all installation dialog boxes; except required dialog boxes such as "no compatible drivers found."


### -field RawDeviceOK

Specifies whether the driver for the underlying bus can drive the device if there is no function driver (for example, SCSI devices in pass-through mode). This mode of operation is called raw mode.


### -field SurpriseRemovalOK

Specifies whether the miniport driver for the device can handle the case where the device is removed before Storport can send SRB_FUNCTION_PNP with <b>StorRemoveDevice</b> as the <b>PnPAction</b> in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-_scsi_pnp_request_block">SCSI_PNP_REQUEST_BLOCK</a> structure. If <b>SurpriseRemovalOK</b> is set to <b>TRUE</b>, the device can be safely removed from its immediate parent regardless of the state that its driver is in. 


### -field NoDisplayInUI

Do not display the device in the user interface. If this bit is set, the device is never displayed in the user interface, even if the device is present but fails to start. Miniport drivers do not set this bit.


### -field DefaultWriteCacheEnabled

The storage device's write cache is enabled by default at initialization.


### -field Reserved0

Reserved bits.


### -field Address

LUN address of the storage unit device.


### -field UINumber

Specifies a number associated with the device that can be displayed in the user interface. 

This number might be an ID value chosen to make locating the physical device easier for the user. When the <b>UINumber</b> is unknown, the miniport driver can set this member to its default value of 0xFFFFFFFF.



### -field Reserved1

Reserved bits.


#### - Removeable

Specifies whether the device can be dynamically removed from its immediate parent. If <b>Removable</b> is set to <b>TRUE</b>, the device does not belong to the same physical object as its parent. 

If <b>Removable</b> is set to <b>TRUE</b>, the device is displayed in the Unplug or Eject Hardware program, unless <b>SurpriseRemovalOK</b> is also set to <b>TRUE</b>.


## -remarks



When a miniport driver receives an SRB in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nc-storport-hw_startio">HwStorStartIo</a> routine where the SRB function is SRB_FUNCTION_PNP, the SRB is formatted as a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-_scsi_pnp_request_block">SCSI_PNP_REQUEST_BLOCK</a> structure. If the <b>PnPAction</b> member of the SRB is <b>StorQueryCapabilities</b>, the miniport can return a <b>STOR_DEVICE_CAPABILITIES_EX</b> structure in the <b>DataBuffer</b> member of the SRB.

The eject, removal, and install characteristics for the device are set in the <b>STOR_DEVICE_CAPABILITIES_EX</b> structure. To support the use of this structure, the miniport must set the  STOR_FEATURE_FULL_PNP_DEVICE_CAPABILITIES flag in the  <b>FeatureSupport</b> flags member in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_initialization_data">HW_INITIALIZATION_DATA</a> before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportinitialize">StorPortInitialize</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_capabilities">DEVICE_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/strmini/ns-strmini-_hw_initialization_data">HW_INITIALIZATION_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-_scsi_pnp_request_block">SCSI_PNP_REQUEST_BLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportinitialize">StorPortInitialize</a>
 

 

