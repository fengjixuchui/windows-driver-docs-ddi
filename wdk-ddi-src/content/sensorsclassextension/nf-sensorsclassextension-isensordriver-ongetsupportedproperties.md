---
UID: NF:sensorsclassextension.ISensorDriver.OnGetSupportedProperties
title: ISensorDriver::OnGetSupportedProperties (sensorsclassextension.h)
description: The ISensorDriver::OnGetSupportedProperties method retrieves the list of properties that the specified sensor provides.
old-location: sensors\isensordriver_ongetsupportedproperties.htm
tech.root: sensors
ms.assetid: 8712fe85-0af1-4552-9351-aca4fe5430d1
ms.date: 05/03/2018
keywords: ["ISensorDriver::OnGetSupportedProperties"]
ms.keywords: ISensorDriver interface [Sensor Devices],OnGetSupportedProperties method, ISensorDriver.OnGetSupportedProperties, ISensorDriver::OnGetSupportedProperties, OnGetSupportedProperties, OnGetSupportedProperties method [Sensor Devices], OnGetSupportedProperties method [Sensor Devices],ISensorDriver interface, sensors.isensordriver_ongetsupportedproperties, sensorsclassextension/ISensorDriver::OnGetSupportedProperties
f1_keywords:
 - "sensorsclassextension/OnGetSupportedProperties"
 - "OnGetSupportedProperties"
req.header: sensorsclassextension.h
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
req.lib: SensorsClassExtension.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- SensorsClassExtension.lib
- SensorsClassExtension.dll
api_name:
- OnGetSupportedProperties
targetos: Windows
req.typenames: 
---

# ISensorDriver::OnGetSupportedProperties


## -description


The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sensorsclassextension/nf-sensorsclassextension-isensordriver-ongetsupportedproperties">ISensorDriver::OnGetSupportedProperties</a> method retrieves the list of properties that the specified sensor provides.


## -parameters




### -param pwszSensorID

LPWSTR that contains the ID for the sensor from which the client application is requesting the properties list.


### -param ppSupportedProperties

 Address of an IPortableDeviceKeyCollection pointer that receives the list of PROPERTYKEY values that represent the supported properties.


## -returns



If the operation succeeds, this method returns S_OK. Otherwise, this method returns one of the error codes that are defined in Winerror.h.




## -remarks



Properties describe the sensor device, as opposed to data fields, which contain sensor-generated data. Platform-defined properties are defined in sensors.h.

Each <a href="https://go.microsoft.com/fwlink/p/?linkid=131484">IPortableDeviceKeyCollection</a> object returned in this collection must contain <b>PROPERTYKEY</b>s for the  required properties, as described in the <a href="https://docs.microsoft.com/windows-hardware/drivers/sensors/sensor-properties2">Sensor Properties</a> reference section.

<a href="https://go.microsoft.com/fwlink/p/?linkid=131484">IPortableDeviceKeyCollection</a> is documented in Windows Portable Devices.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sensorsclassextension/nn-sensorsclassextension-isensordriver">ISensorDriver</a>
 

 

