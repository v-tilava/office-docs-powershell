---
applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015
schema: 2.0.0
---

# Remove-CsAVEdgeConfiguration

## SYNOPSIS
**Below Content Applies To:** Lync Server 2010

Enables you to remove an existing collection of configuration settings applied to computers running the Access Edge service (these computers are also known as A/V Edge servers).
An A/V Edge server enables internal users to share audio and video data with external users (that is, users who are not logged on to your internal network).

**Below Content Applies To:** Lync Server 2013, Skype for Business Server 2015

Enables you to remove an existing collection of configuration settings applied to computers running the Access Edge service (these computers are also known as A/V Edge servers).
An A/V Edge server enables internal users to share audio and video data with external users (that is, users who are not logged on to your internal network).
This cmdlet was introduced in Lync Server 2010.



## SYNTAX

```
Remove-CsAVEdgeConfiguration [-Identity] <XdsIdentity> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
**Below Content Applies To:** Lync Server 2010

An A/V Edge server provides a way for audio and video traffic to be exchanged across an organization's firewall.
Among other things, this enables users to use Microsoft Lync Server 2010 across the Internet, and then exchange audio and video data with users who have logged onto the system from inside the firewall.
Edge Server configuration settings can be assigned at the global scope, the site scope, and the service scope.
The A/V Edge configuration settings enable administrators to do such things as manage the amount of time that user authentication is valid before it must be renewed, and to limit the amount of bandwidth that can be used by a single user or a single port.

The Remove-CsAVEdgeConfiguration cmdlet enables you to delete A/V Edge configuration settings that have been applied to either the site or the service scope.
The cmdlet can also be run against the global settings; however, those global settings will not be deleted.
Instead, the properties contained within the global collection will all be reset to their default values.

Who can run this cmdlet: By default, members of the following groups are authorized to run the Remove-CsAVEdgeConfiguration cmdlet locally: RTCUniversalServerAdmins.
To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Remove-CsAVEdgeConfiguration"}

**Below Content Applies To:** Lync Server 2013

An A/V Edge server provides a way for audio and video traffic to be exchanged across an organization's firewall.
Among other things, this enables users to use Lync Server across the Internet, and then exchange audio and video data with users who have logged onto the system from inside the firewall.
Edge Server configuration settings can be assigned at the global scope, the site scope, and the service scope.
The A/V Edge configuration settings enable administrators to do such things as manage the amount of time that user authentication is valid before it must be renewed, and to limit the amount of bandwidth that can be used by a single user or a single port.

The Remove-CsAVEdgeConfiguration cmdlet enables you to delete A/V Edge configuration settings that have been applied to either the site or the service scope.
The cmdlet can also be run against the global settings; however, those global settings will not be deleted.
Instead, the properties contained within the global collection will all be reset to their default values.

Who can run this cmdlet: By default, members of the following groups are authorized to run the Remove-CsAVEdgeConfiguration cmdlet locally: RTCUniversalServerAdmins.
To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Remove-CsAVEdgeConfiguration"}

**Below Content Applies To:** Skype for Business Server 2015

An A/V Edge server provides a way for audio and video traffic to be exchanged across an organization's firewall.
Among other things, this enables users to use Skype for Business Server 2015 across the Internet, and then exchange audio and video data with users who have logged onto the system from inside the firewall.
Edge Server configuration settings can be assigned at the global scope, the site scope, and the service scope.
The A/V Edge configuration settings enable administrators to do such things as manage the amount of time that user authentication is valid before it must be renewed, and to limit the amount of bandwidth that can be used by a single user or a single port.

The Remove-CsAVEdgeConfiguration cmdlet enables you to delete A/V Edge configuration settings that have been applied to either the site or the service scope.
The cmdlet can also be run against the global settings; however, those global settings will not be deleted.
Instead, the properties contained within the global collection will all be reset to their default values.



## EXAMPLES

### -------------------------- Example 1 ------------------------ (Lync Server 2010)
```
Remove-CsAVEdgeConfiguration -Identity site:Redmond
```

The preceding command removes the A/V Edge configuration settings that have the Identity site:Redmond.
After the settings are removed, A/V Edge servers in the Redmond site will be governed by the global configuration settings.

### -------------------------- EXAMPLE 1 -------------------------- (Lync Server 2013)
```

```

The command shown in Example 1 removes the A/V Edge configuration settings that have the Identity site:Redmond.
After the settings are removed, A/V Edge servers in the Redmond site will be governed by the global configuration settings.

Remove-CsAVEdgeConfiguration -Identity site:Redmond

### -------------------------- EXAMPLE 1 -------------------------- (Skype for Business Server 2015)
```

```

The command shown in Example 1 removes the A/V Edge configuration settings that have the Identity site:Redmond.
After the settings are removed, A/V Edge servers in the Redmond site will be governed by the global configuration settings.

Remove-CsAVEdgeConfiguration -Identity site:Redmond

### -------------------------- Example 2 ------------------------ (Lync Server 2010)
```
Get-CsAVEdgeConfiguration -Filter "service:*" | Remove-CsAVEdgeConfiguration
```

In Example 2, all of the A/V Edge configuration settings that have been applied at the service scope are removed.
To do this, the command first calls Get-CsAVEdgeConfiguration along with the Filter parameter; the filter value "service:*" ensures that only settings configured at the service scope are returned.
This filtered collection is then piped to Remove-CsAVEdgeConfiguration, which deletes each item in the collection.

### -------------------------- EXAMPLE 2 -------------------------- (Lync Server 2013)
```

```

In Example 2, all of the A/V Edge configuration settings that have been applied at the service scope are removed.
To do this, the command first calls Get-CsAVEdgeConfiguration along with the Filter parameter; the filter value "service:*" ensures that only settings configured at the service scope are returned.
This filtered collection is then piped to Remove-CsAVEdgeConfiguration, which deletes each item in the collection.

Get-CsAVEdgeConfiguration -Filter "service:*" | Remove-CsAVEdgeConfiguration

### -------------------------- EXAMPLE 2 -------------------------- (Skype for Business Server 2015)
```

```

In Example 2, all of the A/V Edge configuration settings that have been applied at the service scope are removed.
To do this, the command first calls the Get-CsAVEdgeConfiguration cmdlet along with the Filter parameter; the filter value "service:*" ensures that only settings configured at the service scope are returned.
This filtered collection is then piped to the Remove-CsAVEdgeConfiguration cmdlet, which deletes each item in the collection.

Get-CsAVEdgeConfiguration -Filter "service:*" | Remove-CsAVEdgeConfiguration

### -------------------------- Example 3 ------------------------ (Lync Server 2010)
```
Get-CsAVEdgeConfiguration | Where-Object {$_.MaxBandwidthPerUserKB -lt 5000} | Remove-CsAVEdgeConfiguration
```

The command shown in Example 3 deletes all of the A/V Edge configuration settings where the value of the MaxBandwidthPerUserKB property is less than 5,000 kilobits per second.
To carry out this task, the command first uses Get-CsAVEdgeConfiguration without any additional parameters in order to return a collection of all the A/V Edge settings currently in use in the organization.
This collection is piped to the Where-Object cmdlet, which selects only those settings where the MaxBandwidthPerUserKB property is less than 5000.
The filtered collection is then piped to Remove-CsAVEdgeConfiguration, which deletes each item in that collection.

### -------------------------- EXAMPLE 3 -------------------------- (Lync Server 2013)
```

```

The command shown in Example 3 deletes all of the A/V Edge configuration settings where the value of the MaxBandwidthPerUserKB property is less than 5,000 kilobits per second.
To carry out this task, the command first uses Get-CsAVEdgeConfiguration without any additional parameters in order to return a collection of all the A/V Edge settings currently in use in the organization.
This collection is piped to the Where-Object cmdlet, which selects only those settings where the MaxBandwidthPerUserKB property is less than 5000.
The filtered collection is then piped to Remove-CsAVEdgeConfiguration, which deletes each item in that collection.

Get-CsAVEdgeConfiguration | Where-Object {$_.MaxBandwidthPerUserKB -lt 5000} | Remove-CsAVEdgeConfiguration

### -------------------------- EXAMPLE 3 -------------------------- (Skype for Business Server 2015)
```

```

The command shown in Example 3 deletes all of the A/V Edge configuration settings where the value of the MaxBandwidthPerUserKB property is less than 5,000 kilobits per second.
To carry out this task, the command first uses the Get-CsAVEdgeConfiguration cmdlet without any additional parameters in order to return a collection of all the A/V Edge settings currently in use in the organization.
This collection is piped to the Where-Object cmdlet, which selects only those settings where the MaxBandwidthPerUserKB property is less than 5000.
The filtered collection is then piped to the Remove-CsAVEdgeConfiguration cmdlet, which deletes each item in that collection.

Get-CsAVEdgeConfiguration | Where-Object {$_.MaxBandwidthPerUserKB -lt 5000} | Remove-CsAVEdgeConfiguration

## PARAMETERS

### -Identity
Unique identifier for the collection of A/V Edge configuration settings to be removed.
To "remove" the global collection, use the following syntax: -Identity global.
(As noted previously, the global settings cannot be removed; the properties can only be reset to their default values.) To remove a site collection, use syntax similar to this: -Identity site:Redmond.
Settings configured at the service scope should be referred to using syntax similar to this:

-Identity service:EdgeServer:atl-cs-001.litwareinc.com

You cannot use wildcards when specifying a policy Identity.

```yaml
Type: XdsIdentity
Parameter Sets: (All)
Aliases: 
Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Suppresses the display of any non-fatal error message that might occur when running the command.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 
Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Describes what would happen if you executed the command without actually executing the command.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi
Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before executing the command.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf
Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

###  
Microsoft.Rtc.Management.WritableConfig.Settings.Edge.MediaRelaySettings object.
Remove-CsAVEdgeConfiguration accepts pipelined input of media relay settings objects.
These objects retrieved by running the Get-CsAVEdgeConfiguration cmdlet.

###  
Microsoft.Rtc.Management.WritableConfig.Settings.Edge.MediaRelaySettings object.
The Remove-CsAVEdgeConfiguration cmdlet accepts pipelined input of media relay settings objects.
These objects retrieved by running the Get-CsAVEdgeConfiguration cmdlet.

## OUTPUTS

###  
Remove-CsAVEdgeConfiguration does not return a value or object.
Instead, the cmdlet deletes instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Edge.MediaRelaySettings object.

###  
The Remove-CsAVEdgeConfiguration cmdlet does not return a value or object.
Instead, the cmdlet deletes instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Edge.MediaRelaySettings object.

## NOTES

## RELATED LINKS

[Online Version](http://technet.microsoft.com/EN-US/library/98bceec5-ed9d-4574-b6bf-f51e0f414ca7(OCS.14).aspx)

[Get-CsAVEdgeConfiguration]()

[New-CsAVEdgeConfiguration]()

[Set-CsAVEdgeConfiguration]()

[Online Version](http://technet.microsoft.com/EN-US/library/98bceec5-ed9d-4574-b6bf-f51e0f414ca7(OCS.15).aspx)

[Online Version](http://technet.microsoft.com/EN-US/library/98bceec5-ed9d-4574-b6bf-f51e0f414ca7(OCS.16).aspx)
