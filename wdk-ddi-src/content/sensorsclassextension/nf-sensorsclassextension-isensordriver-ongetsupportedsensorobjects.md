---
UID: NF:sensorsclassextension.ISensorDriver.OnGetSupportedSensorObjects
title: ISensorDriver::OnGetSupportedSensorObjects (sensorsclassextension.h)
description: The ISensorDriver::OnGetSupportedSensorObjects method retrieves the list of sensors that the driver provides.
old-location: sensors\isensordriver_ongetsupportedsensorobjects.htm
tech.root: sensors
ms.assetid: a8ea63cf-24ba-467b-9c27-ab8e38be1c04
ms.date: 05/03/2018
keywords: ["ISensorDriver::OnGetSupportedSensorObjects"]
ms.keywords: ISensorDriver interface [Sensor Devices],OnGetSupportedSensorObjects method, ISensorDriver.OnGetSupportedSensorObjects, ISensorDriver::OnGetSupportedSensorObjects, OnGetSupportedSensorObjects, OnGetSupportedSensorObjects method [Sensor Devices], OnGetSupportedSensorObjects method [Sensor Devices],ISensorDriver interface, sensors.isensordriver_ongetsupportedsensorobjects, sensorsclassextension/ISensorDriver::OnGetSupportedSensorObjects
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
targetos: Windows
req.typenames: 
f1_keywords:
 - ISensorDriver::OnGetSupportedSensorObjects
 - sensorsclassextension/ISensorDriver::OnGetSupportedSensorObjects
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - SensorsClassExtension.lib
 - SensorsClassExtension.dll
api_name:
 - OnGetSupportedSensorObjects
---

# ISensorDriver::OnGetSupportedSensorObjects


## -description

The <a href="/windows-hardware/drivers/ddi/sensorsclassextension/nf-sensorsclassextension-isensordriver-ongetsupportedsensorobjects">ISensorDriver::OnGetSupportedSensorObjects</a> method retrieves the list of sensors that the driver provides.

## -parameters

### -param ppSensorObjectCollection

Address of an IPortableDeviceValuesCollection pointer that receives the list of sensors.

## -returns

If the operation succeeds, this method returns S_OK. Otherwise, this method returns one of the error codes that are defined in Winerror.h.

## -see-also

<a href="/windows-hardware/drivers/ddi/sensorsclassextension/nn-sensorsclassextension-isensordriver">ISensorDriver</a>