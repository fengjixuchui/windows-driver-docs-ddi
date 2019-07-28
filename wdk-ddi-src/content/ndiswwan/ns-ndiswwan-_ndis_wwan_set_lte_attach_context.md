---
UID: NS:ndiswwan._NDIS_WWAN_SET_LTE_ATTACH_CONTEXT
title: _NDIS_WWAN_SET_LTE_ATTACH_CONTEXT (ndiswwan.h)
description: The NDIS_WWAN_SET_LTE_ATTACH_CONTEXT structure describes default LTE attach contexts a miniport driver should set for the inserted SIM's provider (MCC/MNC pair).
tech.root: netvista
ms.assetid: f5be330f-e65b-41b5-9c29-e73106f46137
ms.date: 08/22/2018
ms.topic: struct
f1_keywords:
 - "ndiswwan/_NDIS_WWAN_SET_LTE_ATTACH_CONTEXT"
ms.keywords: _NDIS_WWAN_SET_LTE_ATTACH_CONTEXT, NDIS_WWAN_SET_LTE_ATTACH_CONTEXT, *PNDIS_WWAN_SET_LTE_ATTACH_CONTEXT, 
req.header: ndiswwan.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1703
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: NDIS_WWAN_SET_LTE_ATTACH_CONTEXT, *PNDIS_WWAN_SET_LTE_ATTACH_CONTEXT
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- ndiswwan.h
api_name: 
- _NDIS_WWAN_SET_LTE_ATTACH_CONTEXT
product: 
- Windows
targetos: Windows
ms.custom: RS5
---

# _NDIS_WWAN_SET_LTE_ATTACH_CONTEXT structure

## -description

The **NDIS_WWAN_SET_LTE_ATTACH_CONTEXT** structure describes default LTE attach contexts a miniport driver should set for the inserted SIM's provider (MCC/MNC pair).

### -field Header

The header with type, revision, and size information about the **NDIS_WWAN_SET_LTE_ATTACH_CONTEXT** structure. The MB Service sets the header with the values that are shown in the following table when it sends the data structure to the miniport driver for set operations. Miniport drivers must set the header with the same values when they send the data structure to the MB service.

| Header submember | Value |
| --- | --- |
| Type | NDIS_OBJECT_TYPE_DEFAULT |
| Revision | NDIS_WWAN_SET_LTE_ATTACH_CONTEXT_REVISION_1 |
| Size | sizeof(NDIS_WWAN_SET_LTE_ATTACH_CONTEXT) |

For more information about these members, see [**NDIS_OBJECT_HEADER**](../ntddndis/ns-ntddndis-_ndis_object_header.md).
 
### -field uStatus

The status of system capability. The following table shows the possible values for this member.

| Value | Meaning |
| --- | --- |
| WWAN_STATUS_SUCCESS | The operation succeeded. |
| WWAN_STATUS_BUSY | The operation failed because the device was busy. In the absence of any explicit information from the function to clear this condition, the host can use subsequent actions by the function (e.g. notifications or command completions) as a hint to retry the failed operation. |
| WWAN_STATUS_FAILURE | The operation failed. |
| WWAN_STATUS_NO_DEVICE_SUPPORT | The operation failed because the device does not support this OID. |
 
### -field SetLteAttachContext

A formatted [**WWAN_SET_LTE_ATTACH**](../wwan/ns-wwan-_wwan_set_lte_attach.md) structure that describes the default LTE attach contexts that the miniport driver should set for the inserted SIM's provider (MCC/MNC pair).

## -remarks

This structure is used in an [OID_WWAN_LTE_ATTACH_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-lte-attach-config) Set request.

## -see-also

[MB LTE Attach Operations](https://docs.microsoft.com/windows-hardware/drivers/network/mb-lte-attach-operations)

[OID_WWAN_LTE_ATTACH_CONFIG](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-lte-attach-config)

[**WWAN_SET_LTE_ATTACH**](../wwan/ns-wwan-_wwan_set_lte_attach.md)
