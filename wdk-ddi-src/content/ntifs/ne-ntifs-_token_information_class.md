---
UID: NE:ntifs._TOKEN_INFORMATION_CLASS
title: _TOKEN_INFORMATION_CLASS (ntifs.h)
description: The TOKEN_INFORMATION_CLASS enumeration type contains values that specify the type of information being assigned to or retrieved from an access token.
old-location: ifsk\token_information_class.htm
tech.root: ifsk
ms.assetid: dd2323fa-2c58-462e-905f-3b201ef0c343
ms.date: 04/16/2018
keywords: ["TOKEN_INFORMATION_CLASS enumeration"]
ms.keywords: "*PTOKEN_INFORMATION_CLASS, MaxTokenInfoClass, PTOKEN_INFORMATION_CLASS, PTOKEN_INFORMATION_CLASS enumeration pointer [Installable File System Drivers], TOKEN_INFORMATION_CLASS, TOKEN_INFORMATION_CLASS enumeration [Installable File System Drivers], TokenAccessInformation, TokenAppContainerNumber, TokenAppContainerSid, TokenAuditPolicy, TokenCapabilities, TokenDefaultDacl, TokenDeviceClaimAttributes, TokenDeviceGroups, TokenElevation, TokenGroups, TokenGroupsAndPrivileges, TokenHasRestrictions, TokenImpersonationLevel, TokenIntegrityLevel, TokenIsAppContainer, TokenIsRestricted, TokenLinkedToken, TokenLogonSid, TokenMandatoryPolicy, TokenOrigin, TokenOwner, TokenPrimaryGroup, TokenPrivileges, TokenProcessTrustLevel, TokenRestrictedDeviceClaimAttributes, TokenRestrictedDeviceGroups, TokenRestrictedSids, TokenRestrictedUserClaimAttributes, TokenSandBoxInert, TokenSecurityAttributes, TokenSessionId, TokenSessionReference, TokenSource, TokenStatistics, TokenType, TokenUIAccess, TokenUser, TokenUserClaimAttributes, TokenVirtualizationAllowed, TokenVirtualizationEnabled, _TOKEN_INFORMATION_CLASS, ifsk.token_information_class, ntifs/MaxTokenInfoClass, ntifs/PTOKEN_INFORMATION_CLASS, ntifs/TOKEN_INFORMATION_CLASS, ntifs/TokenAccessInformation, ntifs/TokenAppContainerNumber, ntifs/TokenAppContainerSid, ntifs/TokenAuditPolicy, ntifs/TokenCapabilities, ntifs/TokenDefaultDacl, ntifs/TokenDeviceClaimAttributes, ntifs/TokenDeviceGroups, ntifs/TokenElevation, ntifs/TokenGroups, ntifs/TokenGroupsAndPrivileges, ntifs/TokenHasRestrictions, ntifs/TokenImpersonationLevel, ntifs/TokenIntegrityLevel, ntifs/TokenIsAppContainer, ntifs/TokenIsRestricted, ntifs/TokenLinkedToken, ntifs/TokenLogonSid, ntifs/TokenMandatoryPolicy, ntifs/TokenOrigin, ntifs/TokenOwner, ntifs/TokenPrimaryGroup, ntifs/TokenPrivileges, ntifs/TokenProcessTrustLevel, ntifs/TokenRestrictedDeviceClaimAttributes, ntifs/TokenRestrictedDeviceGroups, ntifs/TokenRestrictedSids, ntifs/TokenRestrictedUserClaimAttributes, ntifs/TokenSandBoxInert, ntifs/TokenSecurityAttributes, ntifs/TokenSessionId, ntifs/TokenSessionReference, ntifs/TokenSource, ntifs/TokenStatistics, ntifs/TokenType, ntifs/TokenUIAccess, ntifs/TokenUser, ntifs/TokenUserClaimAttributes, ntifs/TokenVirtualizationAllowed, ntifs/TokenVirtualizationEnabled, securitystructures_525fb6c8-0030-40ea-927a-72fe89eff87e.xml"
req.header: ntifs.h
req.include-header: Ntifs.h
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
targetos: Windows
req.typenames: TOKEN_INFORMATION_CLASS, *PTOKEN_INFORMATION_CLASS
f1_keywords:
 - _TOKEN_INFORMATION_CLASS
 - ntifs/_TOKEN_INFORMATION_CLASS
 - PTOKEN_INFORMATION_CLASS
 - ntifs/PTOKEN_INFORMATION_CLASS
 - TOKEN_INFORMATION_CLASS
 - ntifs/TOKEN_INFORMATION_CLASS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - TOKEN_INFORMATION_CLASS
---

# _TOKEN_INFORMATION_CLASS enumeration


## -description

The <b>TOKEN_INFORMATION_CLASS</b> enumeration type contains values that specify the type of information being assigned to or retrieved from an access token. 


<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sequeryinformationtoken">SeQueryInformationToken</a> and <a href="/previous-versions/ff567055(v=vs.85)">ZwQueryInformationToken</a> use <b>TOKEN_INFORMATION_CLASS</b> values to indicate the type of token information to retrieve.

## -enum-fields

### -field TokenUser

The buffer receives a <a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_user">TOKEN_USER</a> structure containing the token's user account.

### -field TokenGroups

The buffer receives a <a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_groups">TOKEN_GROUPS</a> structure containing the group accounts associated with the token.

### -field TokenPrivileges

The buffer receives a <a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_privileges">TOKEN_PRIVILEGES</a> structure containing the token's privileges.

### -field TokenOwner

The buffer receives a <a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_owner">TOKEN_OWNER</a> structure containing the default owner SID for newly created objects.

### -field TokenPrimaryGroup

The buffer receives a <a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_primary_group">TOKEN_PRIMARY_GROUP</a> structure containing the default primary group SID for newly created objects.

### -field TokenDefaultDacl

The buffer receives a <a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_default_dacl">TOKEN_DEFAULT_DACL</a> structure containing the default discretionary ACL (DACL)) for newly created objects.

### -field TokenSource

The buffer receives a <a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_source">TOKEN_SOURCE</a> structure containing the source of the token. TOKEN_QUERY_SOURCE access is needed to retrieve this information.

### -field TokenType

The buffer receives a <a href="/windows-hardware/drivers/ddi/ntifs/ne-ntifs-_token_type">TOKEN_TYPE</a> value indicating whether the token is a primary or impersonation token.

### -field TokenImpersonationLevel

The buffer receives a <a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_security_impersonation_level">SECURITY_IMPERSONATION_LEVEL</a> value indicating the impersonation level of the token. If the access token is not an impersonation token, the call to <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sequeryinformationtoken">SeQueryInformationToken</a> or <a href="/previous-versions/ff567055(v=vs.85)">ZwQueryInformationToken</a> fails.

### -field TokenStatistics

The buffer receives a <a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_statistics">TOKEN_STATISTICS</a> structure containing various token statistics.

### -field TokenRestrictedSids

The buffer receives a <a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_groups">TOKEN_GROUPS</a> structure containing the list of restricting SIDs in a restricted token. This value is valid starting with Windows Vista.

### -field TokenSessionId

The buffer receives a DWORD value that indicates the Terminal Services session identifier associated with the token. If the token is associated with the Terminal Server console session, the session identifier is zero. A nonzero session identifier indicates a Terminal Services client session. In a non-Terminal Services environment, the session identifier is zero. This value is valid starting with Windows Vista.

### -field TokenGroupsAndPrivileges

The buffer receives a <a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_groups_and_privileges">TOKEN_GROUPS_AND_PRIVILEGES</a> structure that contains the user SID, the group accounts, the restricted SIDs, and the authentication ID associated with the token. This value is valid starting with Windows Vista.

### -field TokenSessionReference

Reserved for system use.

### -field TokenSandBoxInert

The buffer receives a DWORD value that is nonzero if the token includes the SANDBOX_INERT flag. This value is valid starting with Windows Vista.

### -field TokenAuditPolicy

Reserved for system use.

### -field TokenOrigin

The buffer receives a <a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_origin">TOKEN_ORIGIN</a> value. 

If the token resulted from a logon that used explicit credentials, such as passing a name, domain, and password to the user-mode <a href="/windows/win32/api/winbase/nf-winbase-logonusera">LogonUser</a> function, then the <b>TOKEN_ORIGIN</b> structure will contain the ID of the logon session that created it.

If the token resulted from network authentication, such as a call to user-mode <b>AcceptSecurityContext</b> function or a call to user-mode <b>LogonUser</b> function with dwLogonType set to LOGON32_LOGON_NETWORK or LOGON32_LOGON_NETWORK_CLEARTEXT, then this value will be zero.

 This value is valid starting with Windows Server 2003.

### -field TokenElevationType

### -field TokenLinkedToken

The buffer receives a <a href="/windows/win32/api/winnt/ns-winnt-token_linked_token">TOKEN_LINKED_TOKEN</a> structure that contains a handle to another token that is linked to this token. This value is valid starting with Windows Vista.

### -field TokenElevation

The buffer receives a <a href="/windows/win32/api/winnt/ns-winnt-token_elevation">TOKEN_ELEVATION</a> structure that specifies whether the token is elevated. This value is valid starting with Windows Vista.

### -field TokenHasRestrictions

The buffer receives a <b>DWORD</b> value that is nonzero if the token has ever been filtered. This value is valid starting with Windows Vista.

### -field TokenAccessInformation

The buffer receives a <a href="/windows/win32/api/winnt/ns-winnt-token_access_information">TOKEN_ACCESS_INFORMATION</a> structure that specifies  security information contained in the token. This value is valid starting with Windows Vista.

### -field TokenVirtualizationAllowed

The buffer receives a <b>DWORD</b> value that is nonzero if  <a href="/previous-versions/windows/hardware/design/dn614617(v=vs.85)">virtualization</a> is allowed for the token. This value is valid starting with Windows Vista.

### -field TokenVirtualizationEnabled

The buffer receives a <b>DWORD</b> value that is nonzero if  <a href="/previous-versions/windows/hardware/design/dn614617(v=vs.85)">virtualization</a> is enabled for the token. This value is valid starting with Windows Vista.

### -field TokenIntegrityLevel

The buffer receives a <a href="/windows/win32/api/winnt/ns-winnt-token_mandatory_label">TOKEN_MANDATORY_LABEL</a> structure that specifies the token's integrity level. This value is valid starting with Windows Vista. For <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sequeryinformationtoken">SeQueryInformationToken</a> the output is the actual integrity level  (<b>DWORD</b>).

### -field TokenUIAccess

The buffer receives a <b>DWORD</b> value that is nonzero if  the token has the UIAccess flag set. This value is valid starting with Windows Vista.

### -field TokenMandatoryPolicy

The buffer receives a <a href="/windows/win32/api/winnt/ns-winnt-token_mandatory_policy">TOKEN_MANDATORY_POLICY</a> structure that specifies the token's mandatory integrity policy. This value is valid starting with Windows Vista.

### -field TokenLogonSid

The buffer receives a <a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_groups">TOKEN_GROUPS</a> structure that specifies the token's logon SID. This value is valid starting with Windows Vista.

### -field TokenIsAppContainer

The buffer receives a <b>DWORD</b> value that is nonzero if  the token has the application container flag set. This value is valid starting with Windows 8.

### -field TokenCapabilities

The buffer receives a <b>TOKEN_GROUPS</b> structure and an array of <b>SID_AND_ATTRIBUTES</b> structures for each token capability. This value is valid starting with Windows 8.

### -field TokenAppContainerSid

The buffer receives a <b>TOKEN_APPCONTAINER_INFORMATION</b> structure that contains the AppContainerSid associated with the token. If the token is not associated with an app container, the TokenAppContainer member of the <b>TOKEN_APPCONTAINER_INFORMATION</b> structure points to NULL. This value is valid starting with Windows 8.

### -field TokenAppContainerNumber

The buffer receives a <b>DWORD</b> value that is the application container number. This value is valid starting with Windows 8.

### -field TokenUserClaimAttributes

The buffer receives a <a href="/windows/win32/api/winnt/ns-winnt-token_mandatory_policy">CLAIM_SECURITY_ATTRIBUTES_INFORMATION</a> structure that specifies the user's claim attributes. This value is valid starting with Windows 8.

### -field TokenDeviceClaimAttributes

The buffer receives a <a href="/windows/win32/api/winnt/ns-winnt-token_mandatory_policy">CLAIM_SECURITY_ATTRIBUTES_INFORMATION</a> structure that specifies the device's claim attributes. This value is valid starting with Windows 8.

### -field TokenRestrictedUserClaimAttributes

Reserved for system use.

### -field TokenRestrictedDeviceClaimAttributes

Reserved for system use.

### -field TokenDeviceGroups

The buffer receives a <b>TOKEN_GROUPS</b> structure and an array of <b>SID_AND_ATTRIBUTES</b> structures for each device group. This value is valid starting with Windows 8.

### -field TokenRestrictedDeviceGroups

Reserved for system use.

### -field TokenSecurityAttributes

Reserved for system use.

### -field TokenIsRestricted

Reserved for system use.

### -field TokenProcessTrustLevel

Reserved for system use.

### -field TokenPrivateNameSpace

### -field TokenSingletonAttributes

### -field TokenBnoIsolation

### -field TokenChildProcessFlags

### -field MaxTokenInfoClass

The maximum value for this enumeration.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_acl">ACL</a>



<a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_security_impersonation_level">SECURITY_IMPERSONATION_LEVEL</a>



<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid">SID</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sefiltertoken">SeFilterToken</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sequeryinformationtoken">SeQueryInformationToken</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-setokenisrestricted">SeTokenIsRestricted</a>



<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_default_dacl">TOKEN_DEFAULT_DACL</a>



<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_groups">TOKEN_GROUPS</a>



<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_origin">TOKEN_ORIGIN</a>



<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_owner">TOKEN_OWNER</a>



<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_primary_group">TOKEN_PRIMARY_GROUP</a>



<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_privileges">TOKEN_PRIVILEGES</a>



<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_source">TOKEN_SOURCE</a>



<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_statistics">TOKEN_STATISTICS</a>



<a href="/windows-hardware/drivers/ddi/ntifs/ne-ntifs-_token_type">TOKEN_TYPE</a>



<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_user">TOKEN_USER</a>



<a href="/previous-versions/ff567055(v=vs.85)">ZwQueryInformationToken</a>



<a href="/previous-versions/ff567102(v=vs.85)">ZwSetInformationToken</a>