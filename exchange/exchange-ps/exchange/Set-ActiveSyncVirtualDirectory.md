---
applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016
schema: 2.0.0
---

# Set-ActiveSyncVirtualDirectory

## SYNOPSIS
!!! Exchange Server 2010

Use the Set-ActiveSyncVirtualDirectory cmdlet to configure the Microsoft Exchange ActiveSync settings on a specified virtual directory.

!!! Exchange Server 2013

This cmdlet is available only in on-premises Exchange.

Use the Set-ActiveSyncVirtualDirectory cmdlet to configure the Microsoft Exchange ActiveSync settings on a specified virtual directory.

For information about the parameter sets in the Syntax section below, see Exchange cmdlet syntax (https://technet.microsoft.com/library/bb123552.aspx).

!!! Exchange Server 2016

This cmdlet is available only in on-premises Exchange.

Use the Set-ActiveSyncVirtualDirectory cmdlet to modifyexisting Microsoft Exchange ActiveSync virtual directories that are used in Internet Information Services (IIS) on Exchange servers.

For information about the parameter sets in the Syntax section below, see Exchange cmdlet syntax (https://technet.microsoft.com/library/bb123552.aspx).

## SYNTAX

```
Set-ActiveSyncVirtualDirectory [-Identity] <VirtualDirectoryIdParameter> [-ActiveSyncServer <String>]
 [-BadItemReportingEnabled <$true | $false>] [-BasicAuthEnabled <$true | $false>]
 [-ClientCertAuth <Ignore | Accepted | Required>] [-CompressionEnabled <$true | $false>] [-Confirm]
 [-DomainController <Fqdn>] [-ExtendedProtectionFlags <MultiValuedProperty>]
 [-ExtendedProtectionSPNList <MultiValuedProperty>] [-ExtendedProtectionTokenChecking <None | Allow | Require>]
 [-ExternalAuthenticationMethods <MultiValuedProperty>] [-ExternalUrl <Uri>]
 [-InstallIsapiFilter <$true | $false>] [-InternalAuthenticationMethods <MultiValuedProperty>]
 [-InternalUrl <Uri>] [-MobileClientCertificateAuthorityURL <String>]
 [-MobileClientCertificateProvisioningEnabled <$true | $false>] [-MobileClientCertTemplateName <String>]
 [-Name <String>] [-RemoteDocumentsActionForUnknownServers <Allow | Block>]
 [-RemoteDocumentsAllowedServers <MultiValuedProperty>] [-RemoteDocumentsBlockedServers <MultiValuedProperty>]
 [-RemoteDocumentsInternalDomainSuffixList <MultiValuedProperty>] [-SendWatsonReport <$true | $false>]
 [-WhatIf] [-WindowsAuthEnabled <$true | $false>] [<CommonParameters>]
```

## DESCRIPTION
!!! Exchange Server 2010

The Set-ActiveSyncVirtualDirectory cmdlet configures a variety of settings on the virtual directory used for Exchange ActiveSync including security, authentication, and internal and external URL settings.

You need to be assigned permissions before you can run this cmdlet. Although all parameters for this cmdlet are listed in this topic, you may not have access to some parameters if they're not included in the permissions assigned to you. To see what permissions you need, see the "Exchange ActiveSync virtual directory settings" entry in the Client Access Permissions topic.

!!! Exchange Server 2013

The Set-ActiveSyncVirtualDirectory cmdlet configures a variety of settings on the virtual directory used for Exchange ActiveSync including security, authentication, and internal and external URL settings.

You need to be assigned permissions before you can run this cmdlet. Although all parameters for this cmdlet are listed in this topic, you may not have access to some parameters if they're not included in the permissions assigned to you. To see what permissions you need, see the "Exchange ActiveSync virtual directory settings" entry in the Clients and mobile devices permissions topic.

!!! Exchange Server 2016

The Set-ActiveSyncVirtualDirectory cmdlet configures a variety of settings on the virtual directory used for Exchange ActiveSync including security, authentication, and internal and external URL settings.

You need to be assigned permissions before you can run this cmdlet. Although this topic lists all parameters for the cmdlet, you may not have access to some parameters if they're not included in the permissions assigned to you. To find the permissions required to run any cmdlet or parameter in your organization, see Find the permissions required to run any Exchange cmdlet (https://technet.microsoft.com/library/mt432940.aspx).

## EXAMPLES

### Example 1 -------------------------- (Exchange Server 2010)
```
Get-ActiveSyncVirtualDirectory |Set-ActiveSyncVirtualDirectory BasicAuthEnabled:$false
```

This example disables basic authentication on the default Exchange ActiveSync virtual directory on the server Contoso by sending the results of the Get-ActiveSyncVirtualDirectory command to Set-ActiveSyncVirtualDirectory and adding -BasicAuthEnabled:$false.

### Example 1 -------------------------- (Exchange Server 2013)
```
Set-ActiveSyncVirtualDirectory -Identity "contoso\Microsoft-Server-ActiveSync" -BasicAuthEnabled:$false
```

This example disables Basic authentication on the default Exchange ActiveSync virtual directory on the server Contoso.

### Example 1 -------------------------- (Exchange Server 2016)
```
Set-ActiveSyncVirtualDirectory -Identity "contoso\Microsoft-Server-ActiveSync" -BasicAuthEnabled $false
```

This example disables Basic authentication on the default Exchange ActiveSync virtual directory on the server Contoso.

### Example 2 -------------------------- (Exchange Server 2010)
```
Set-ActiveSyncVirtualDirectory -Identity "contoso\Microsoft-Server-ActiveSync (Default Web Site)" -BasicAuthEnabled:$false
```

This example disables Basic authentication on the default Exchange ActiveSync virtual directory on the server Contoso.

### Example 2 -------------------------- (Exchange Server 2013)
```
Set-ActiveSyncVirtualDirectory -Identity "contoso\Microsoft-Server-ActiveSync" -BadItemReportingEnabled:$true -SendWatsonReport:$true
```

This example enables bad item reporting and turns on the option to send Watson reports for errors on the server Contoso.

### Example 2 -------------------------- (Exchange Server 2016)
```
Set-ActiveSyncVirtualDirectory -Identity "contoso\Microsoft-Server-ActiveSync" -BadItemReportingEnabled $true -SendWatsonReport:$true
```

This example enables bad item reporting and turns on the option to send Watson reports for errors on the server Contoso.

### Example 3 -------------------------- (Exchange Server 2010)
```
Set-ActiveSyncVirtualDirectory -Identity "contoso\Microsoft-Server-ActiveSync (Default Web Site)" -BadItemReportingEnabled:$true -SendWatsonReport:$true
```

This example enables bad item reporting and turns on the option to send Watson reports for errors on the server Contoso.

### Example 3 -------------------------- (Exchange Server 2013)
```
Set-ActiveSyncVirtualDirectory -Identity "contoso\Microsoft-Server-ActiveSync" -ExternalUrl "http://contoso.com/mail"
```

This example configures the external URL on the default Exchange ActiveSync virtual directory on the server Contoso.

### Example 3 -------------------------- (Exchange Server 2016)
```
Set-ActiveSyncVirtualDirectory -Identity "contoso\Microsoft-Server-ActiveSync" -ExternalUrl "http://contoso.com/mail"
```

This example configures the external URL on the default Exchange ActiveSync virtual directory on the server Contoso.

### Example 4 -------------------------- (Exchange Server 2010)
```
Set-ActiveSyncVirtualDirectory -Identity "contoso\Microsoft-Server-ActiveSync (Default Web Site)" -ExternalUrl "http://contoso.com/mail"
```

This example configures the external URL on the default Exchange ActiveSync virtual directory on the server Contoso.

## PARAMETERS

### -Identity
!!! Exchange Server 2010

The Identity parameter uniquely identifies the Exchange ActiveSync virtual directory to be configured. This value must be website\\Microsoft-Server-ActiveSync (Default Web Site).



!!! Exchange Server 2013

The Identity parameter uniquely identifies the Exchange ActiveSync virtual directory to be configured. This value must be website\\Microsoft-Server-ActiveSync.



!!! Exchange Server 2016

The Identity parameter specifies the Exchange ActiveSync virtual directory that you want to modify.

You can use any value that uniquely identifies the virtual directory. For example:

- Name or \<Server\>\\Name

- Distinguished name (DN)

- GUID

The Name value uses the syntax "\<VirtualDirectoryName\> (\<WebsiteName\>)" from the properties of the virtual directory. You can specify the wildcard character (\*) instead of the default website by using the syntax \<VirtualDirectoryName\>\*.



```yaml
Type: VirtualDirectoryIdParameter
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: True
Position: 1
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### -ActiveSyncServer
!!! Exchange Server 2010, Exchange Server 2013

The ActiveSyncServer parameter specifies the URL of the Client Access server. This value is in the following format: https://servername/Microsoft-Server-ActiveSync.



!!! Exchange Server 2016

The ActiveSyncServer parameter specifies the URL of the Mailbox server. This value is in the following format: https://servername/Microsoft-Server-ActiveSync.



```yaml
Type: String
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BadItemReportingEnabled
The BadItemReportingEnabled parameter specifies whether items that can't be synchronized should be reported to the user. If set to $true, the user receives a notification when an item can't be synchronized to the mobile phone.

```yaml
Type: $true | $false
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BasicAuthEnabled
!!! Exchange Server 2010, Exchange Server 2013

The BasicAuthEnabled parameter enables or disables Basic authentication. The default setting is $true.



!!! Exchange Server 2016

The BasicAuthentication parameter specifies whether Basic authentication is enabled on the virtual directory. Valid values are:

- $true: Basic authentication is enabled. This is the default value.

- $false: Basic authentication is disabled.



```yaml
Type: $true | $false
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientCertAuth
The ClientCertAuth parameter specifies the status of client certificate authentication. By default, client certificate authentication is disabled. The default setting is Ignore.

```yaml
Type: Ignore | Accepted | Required
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CompressionEnabled
The CompressionEnabled parameter is a Boolean value that identifies the compression applied to the specified Exchange ActiveSync virtual directory. The default setting is $true.

```yaml
Type: $true | $false
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
The Confirm switch specifies whether to show or hide the confirmation prompt. How this switch affects the cmdlet depends on if the cmdlet requires confirmation before proceeding.

- Destructive cmdlets (for example, Remove-\* cmdlets) have a built-in pause that forces you to acknowledge the command before proceeding. For these cmdlets, you can skip the confirmation prompt by using this exact syntax: -Confirm:$false.

- Most other cmdlets (for example, New-\* and Set-\* cmdlets) don't have a built-in pause. For these cmdlets, specifying the Confirm switch without a value introduces a pause that forces you acknowledge the command before proceeding.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainController
The DomainController parameter specifies the domain controller that's used by this cmdlet to read data from or write data to Active Directory. You identify the domain controller by its fully qualified domain name (FQDN). For example, dc01.contoso.com.

```yaml
Type: Fqdn
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExtendedProtectionFlags
!!! Exchange Server 2010, Exchange Server 2013

The ExtendedProtectionFlags parameter is used to customize the options you use if you're using Extended Protection for Authentication. The possible values are:

- None Default setting.

- Proxy Specifies that a proxy is terminating the SSL channel. A Service Principal Name (SPN) must be registered in the ExtendedProtectionSPNList parameter if proxy mode is configured.

- ProxyCoHosting Specifies that both HTTP and HTTPS traffic may be accessing the Client Access server and that a proxy is located between at least some of the clients and the Client Access server.

- AllowDotlessSPN Specifies whether you want to support valid SPNs that aren't in the fully qualified domain name (FQDN) format, for example ContosoMail. You specify valid SPNs with the ExtendedProtectionSPNList parameter. This option makes extended protection less secure because dotless certificates aren't unique, so it isn't possible to ensure that the client-to-proxy connection was established over a secure channel.

- NoServiceNameCheck Specifies that the SPN list won't be checked to validate a channel binding token. This option makes Extended Protection for Authentication less secure. We generally don't recommend this setting.



!!! Exchange Server 2016

The ExtendedProtectionFlags parameter specifies custom settings for Extended Protection for Authentication on the virtual directory. Valid values are:

- None: This is the default setting.

- AllowDotlessSPN: Required if you want to use Service Principal Name (SPN) values that don't contain FQDNs (for example, HTTP/ContosoMail instead of HTTP/mail.contoso.com). You specify SPNs with the ExtendedProtectionSPNList parameter. This setting makes Extended Protection for Authentication less secure because dotless certificates aren't unique, so it isn't possible to ensure that the client-to-proxy connection was established over a secure channel.

- NoServiceNameCheck: The SPN list isn't checked to validate a channel binding token. This setting makes Extended Protection for Authentication less secure. We generally don't recommend this setting.

- Proxy: A proxy server is responsible for terminating the SSL channel. To use this setting, you need to register an SPN by using the ExtendedProtectionSPNList parameter.

- ProxyCoHosting: HTTP and HTTPS traffic may be accessing the virtual directory, and a proxy server is located between at least some of the clients and the Client Access services on the Exchange server.



```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExtendedProtectionSPNList
!!! Exchange Server 2010, Exchange Server 2013

The ExtendedProtectionSPNList parameter specifies a list of valid Service Principal Names (SPNs) if you're using Extended Protection for Authentication on the specified virtual directory.

The possible values are:

- Null This is the default value.

- Single SPN or comma delimited list of valid SPNs By default, you must specify the fully qualified domain name (FQDN) (for example mail.contoso.com) for each SPN. If you want to add an SPN that's not an FQDN (for example, ContosoMail), you must also use the ExtendedProtectionTokenChecking parameter with the AllowDotlessSPN value. You specify the domain in SPN format. The SPN format is \<protocol\>/\<FQDN\>. For example, a valid entry could be HTTP/mail.contoso.com.



!!! Exchange Server 2016

The ExtendedProtectionSPNList parameter specifies a list of valid Service Principal Names (SPNs) if you're using Extended Protection for Authentication on the virtual directory. Valid values are:

- $null: This is the default value.

- Single SPN or comma delimited list of valid SPNs: The SPN value format is \<protocol\>/\<FQDN\>. For example, HTTP/mail.contoso.com. To add an SPN that's not an FQDN (for example, HTTP/ContosoMail), you also need to use the AllowDotlessSPN value for the ExtendedProtectionFlags parameter.



```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExtendedProtectionTokenChecking
!!! Exchange Server 2010

The ExtendedProtectionTokenChecking parameter defines how you want to use Extended Protection for Authentication on the specified Exchange virtual directory. Extended Protection for Authentication isn't enabled by default. The available settings are:

- None Extended Protection for Authentication won't be used. Connections between the client and Exchange won't use Extended Protection for Authentication on this virtual directory. This is the default setting.

- Allow Extended Protection for Authentication will be used for connections between the client and Exchange on this virtual directory if both the client and server support Extended Protection for Authentication. Connections that don't support Extended Protection for Authentication on the client and server will work, but may not be as secure as a connection using Extended Protection for Authentication.

If you have a proxy server between the client and the Client Access server that's configured to terminate the client-to-proxy SSL channel, you must also configure one or more Service Principal Names (SPNs) by using the ExtendedProtectionSPNList parameter.

- Require Extended Protection for Authentication will be used for all connections between clients and Exchange servers for this virtual directory. If either the client or server doesn't support Extended Protection for Authentication, the connection between the client and server will fail. If you set this option, you must also set a value for the ExtendedProtectionSPNList parameter.

If you have a proxy server between the client and the Client Access server that's configured to terminate the client-to-proxy SSL channel, you must also configure one or more SPNs using the parameter ExtendedProtectionSPNList.

To learn more about Extended Protection for Authentication, see Understanding Extended Protection for Authentication.



!!! Exchange Server 2013

The ExtendedProtectionTokenChecking parameter defines how you want to use Extended Protection for Authentication on the specified Exchange virtual directory. Extended Protection for Authentication isn't enabled by default. The available settings are:

- None: Extended Protection for Authentication isn't used. Connections between the client and Exchange don't use Extended Protection for Authentication on the virtual directory. This is the default value.

- Allow: Extended Protection for Authentication is used for connections between the client and Exchange on the virtual directory if both the client and server support it. Connections that don't support Extended Protection for Authentication on the client and server will work, but may not be as secure as a connection using Extended Protection for Authentication.

- Require: Extended Protection for Authentication is used for all connections between clients and Exchange servers for this virtual directory. If either the client or server doesn't support it, the connection between the client and server will fail. If you use this value, you also need to set a value for the ExtendedProtectionSPNList parameter.

Note:

If you use the value Allow or Require, and you have a proxy server between the client and the Client Access server that's configured to terminate the client-to-proxy SSL channel, you also need to configure one or more Service Principal Names (SPNs) using the ExtendedProtectionSPNList parameter.



!!! Exchange Server 2016

The ExtendedProtectionTokenChecking parameter defines how you want to use Extended Protection for Authentication on the virtual directory. Extended Protection for Authentication isn't enabled by default. Valid values are:

- None: Extended Protection for Authentication isn't be used on the virtual directory. This is the default value.

- Allow: Extended Protection for Authentication is used for connections between clients and the virtual directory if both the client and server support it. Connections that don't support Extended Protection for Authentication will work, but may not be as secure as connections that use Extended Protection for Authentication.

- Require: Extended Protection for Authentication is used for all connections between clients and the virtual directory. If either the client or server doesn't support it, the connection will fail. If you use this value, you also need to set an SPN value for the ExtendedProtectionSPNList parameter.

Note:

If you use the value Allow or Require, and you have a proxy server between the client and the Client Access services on the Mailbox server that's configured to terminate the client-to-proxy SSL channel, you also need to configure one or more Service Principal Names (SPNs) by using the ExtendedProtectionSPNList parameter.



```yaml
Type: None | Allow | Require
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExternalAuthenticationMethods
!!! Exchange Server 2010, Exchange Server 2013

The ExternalAuthenticationMethods parameter specifies the authentication methods supported by the server that contains the virtual directory when access is requested from outside the network firewall. If this parameter isn't set, all authentication methods can be used.



!!! Exchange Server 2016

The ExternalAuthenticationMethods parameter restricts the authentication methods that can be used to connect to the virtual directory from outside the firewall. Valid values are:

- Adfs

- Basic

- Certificate

- Digest

- Fba

- Kerberos

- LiveIdBasic

- LiveIdFba

- LiveIdNegotiate

- NegoEx

- Negotiate

- Ntlm

- OAuth

- WindowsIntegrated

- WSSecurity

You can specify multiple values separated by commas.

Although you can specify any of these values, whether or not the authentication method actually works for external connections depends on other factors. For example:

- Is the authentication method available on the virtual directory?

- Is the authentication method available, but disabled on the virtual directory?



```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExternalUrl
!!! Exchange Server 2010, Exchange Server 2013

The ExternalUrl parameter specifies the URL used to connect to the virtual directory from outside the network firewall.



!!! Exchange Server 2016

The ExternalURL parameter specifies the URL that's used to connect to the virtual directory from outside the firewall.



```yaml
Type: Uri
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstallIsapiFilter
The InstallIsapiFilter parameter specifies whether the Internet Server API (ISAPI) filter is installed.

```yaml
Type: $true | $false
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InternalAuthenticationMethods
The InternalAuthenticationMethods parameter specifies the authentication methods supported by the server that contains the virtual directory when access is requested from inside the network firewall. If this parameter isn't set, all authentication methods can be used.

```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InternalUrl
!!! Exchange Server 2010, Exchange Server 2013

The InternalUrl parameter is used for the Client Access server HTTP Proxy feature. If it's set, the Client Access server receiving the incoming client connections proxies the requests to this URL. This can be an Internet-facing FQDN URL or an internal host name.



!!! Exchange Server 2016

The InternalURL parameter specifies the URL that's used to connect to the virtual directory from inside the firewall.



```yaml
Type: Uri
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MobileClientCertificateAuthorityURL
The MobileClientCertificateAuthorityURL parameter specifies the URL for the certification authority (CA) used by the mobile phone.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MobileClientCertificateProvisioningEnabled
The MobileClientCertificateProvisioningEnabled parameter specifies whether the Autodiscover service returns the Certificate Services server URL in the XML file.

```yaml
Type: $true | $false
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MobileClientCertTemplateName
The MobileClientCertTemplateName parameter specifies the template name for the client certificate.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
The Name parameter specifies the name of the Exchange ActiveSync virtual directory.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoteDocumentsActionForUnknownServers
The RemoteDocumentsActionForUnknownServers parameter specifies the action that occurs when a Microsoft Windows SharePoint Services or Microsoft Windows file share request comes in via Exchange ActiveSync. When a request arrives, Exchange ActiveSync looks for the requested host name in the Allow and Block lists. If the host name isn't found in either list, the action specified in this parameter, either Block or Allow, is performed.

```yaml
Type: Allow | Block
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoteDocumentsAllowedServers
The RemoteDocumentsAllowedServers parameter is a multivalued property that lists all the allowed servers for remote document access.

```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoteDocumentsBlockedServers
The RemoteDocumentsBlockedServers parameter is a multivalued property that lists all the blocked servers for remote document access.

```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoteDocumentsInternalDomainSuffixList
The RemoteDocumentsInternalDomainSuffixList parameter is used in organizations that don't run Windows Internet Name Service (WINS) in their network. In these environments, you can specify one or more FQDNs that Exchange ActiveSync treats as internal when a request for remote file access is received.

```yaml
Type: MultiValuedProperty
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SendWatsonReport
The SendWatsonReport parameter specifies whether a Watson report is sent for errors and events.

```yaml
Type: $true | $false
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
The WhatIf switch simulates the actions of the command. You can use this switch to view the changes that would occur without actually applying those changes. You don't need to specify a value with this switch.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WindowsAuthEnabled
!!! Exchange Server 2010

This parameter specifies whether Integrated Windows Authentication is enabled. The default value is $false.



!!! Exchange Server 2013, Exchange Server 2016

The WindowsAuthEnabled parameter specifies whether Integrated Windows authentication is enabled. The default value is $false.



```yaml
Type: $true | $false
Parameter Sets: (All)
Aliases:
Applicable: Exchange Server 2010, Exchange Server 2013, Exchange Server 2016

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/p/?LinkID=113216).

## INPUTS

###  
To see the input types that this cmdlet accepts, see Cmdlet Input and Output Types (https://go.microsoft.com/fwlink/p/?LinkId=616387). If the Input Type field for a cmdlet is blank, the cmdlet doesn't accept input data.

## OUTPUTS

###  
To see the return types, which are also known as output types, that this cmdlet accepts, see Cmdlet Input and Output Types (https://go.microsoft.com/fwlink/p/?LinkId=616387). If the Output Type field is blank, the cmdlet doesn't return data.

## NOTES

## RELATED LINKS

[Online Version](https://technet.microsoft.com/library/899fa80c-41e9-4fc0-b28e-5ca2f55e6369.aspx)
