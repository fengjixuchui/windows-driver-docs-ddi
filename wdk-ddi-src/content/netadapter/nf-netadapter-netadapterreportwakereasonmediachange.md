---
UID: NF:netadapter.NetAdapterReportWakeReasonMediaChange
title: NetAdapterReportWakeReasonMediaChange function (netadapter.h)
author: windows-driver-content
description: The NetAdapterReportWakeReasonMediaChange method reports to the framework that a net adapter generated a wake-up event because of a media change.
tech.root: netvista
ms.assetid: 877cde13-87d8-42e6-bf83-7ff81743bacc
ms.author: windowsdriverdev
ms.date: 11/07/2019
keywords: ["NetAdapterReportWakeReasonMediaChange function"]
f1_keywords:
 - "netadapter/NetAdapterReportWakeReasonMediaChange"
ms.keywords: NetAdapterReportWakeReasonMediaChange
req.header: netadapter.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib: netadaptercxstub.lib
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- LibDef
api_location: 
- netadaptercxstub.lib
api_name: 
- NetAdapterReportWakeReasonMediaChange
product: 
- Windows
targetos: Windows
ms.custom: Vb
---

# NetAdapterReportWakeReasonMediaChange function


## -description

The **NetAdapterReportWakeReasonMediaChange** method reports to the framework that a net adapter generated a wake-up event because of a media change.

## -parameters

### -param Adapter

A handle to the NETADAPTER object.

### -param Reason

A [**NET_IF_MEDIA_CONNECT_STATE**](https://docs.microsoft.com/windows/win32/api/ifdef/ne-ifdef-net_if_media_connect_state) value that specifies the network interface connection state that triggered the wake-up event.

## -returns

This method does not return a value.

## -remarks

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_IF_MEDIA_CONNECT_STATE**](https://docs.microsoft.com/windows/win32/api/ifdef/ne-ifdef-net_if_media_connect_state)
