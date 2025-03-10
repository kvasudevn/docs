---
title: Action Commands
author: Cumulus Networks
weight: 55

type: nojsscroll
---
<style>
h { color: RGB(118,185,0)}
</style>
<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action

Resets counters for interfaces, BGP, QoS buffers and pools, removes conflicts from protodown MLAG bonds, and disconnects system users.

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv show action</h>

Shows the action jobs.

### Version History

Introduced in Cumulus Linux 5.4.0

### Example

```
cumulus@switch:~$ nv show action
'1':
  detail: acl counters cleared.
  http_status: 200
  issue: []
  percentage: ''
  state: action_success
  status: acl counters cleared.
  timeout: 60
  type: ''
'2':
  detail: Local Time is now Wed 2024-05-29 09:47:30 UTC
  http_status: 200
  issue: []
  percentage: ''
  state: action_success
  status: Local Time is now Wed 2024-05-29 09:47:30 UTC
  timeout: 60
  type: ''
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv show action \<action-job-id\></h>

Shows information about the specified action.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<action-job-id>` | The action ID. |

### Version History

Introduced in Cumulus Linux 5.4.0

### Example

```
cumulus@switch:~$ nv show action 3
detail: acl counters cleared.
http_status: 200
issue: []
state: action_success
status: acl counters cleared.
timeout: 60
type: ''
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action cancel system telemetry hft job \<job-id\> profile \<profile-id\></h>

Cancels a specific or all high frequency telemetry data collection jobs, or a specific or all jobs for a high frequency telemetry profile. You can specify a job ID or `all` to cancel all jobs.

### Command Syntax

| Syntax |  Description   |
| ---------  | -------------- |
| `<job-id>`| The high frequency telemetry data collection job ID or `all`. To see the list of job IDs, run the `nv show system telemetry hft job` command. |
| `<profile-id>` |  The name of the profile. High frequency telemetry uses profiles for data collection. A profile is a set of configurations. Cumulus Linux provides a default profile called `standard`. You can create a maximum of four new profiles (four profiles in addition to the default profile).|

### Version History

Introduced in Cumulus Linux 5.10.0

### Example

```
cumulus@switch:~$ nv action cancel system telemetry hft job 6 profile profile1
Action executing ...
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action change system date-time</h>

Configures the Cumulus Linux software clock. The switch contains a battery backed hardware clock that maintains the time while the switch powers off and between reboots. When the switch is running, the Cumulus Linux operating system maintains its own software clock.

During boot up, the switch copies the time from the hardware clock to the operating system software clock. The software clock takes care of all the timekeeping. During system shutdown, the switch copies the software clock back to the battery backed hardware clock.

The date format is YYYY-MM-DD. The time format is HH:MM:SS.

{{%notice note%}}
In Cumulus Linux 5.7, 5.8, and 5.9, this command is `nv action change system time`.
{{%/notice%}}

### Version History

Introduced in Cumulus Linux 5.10.0

### Example

```
cumulus@switch:~$ nv action change system date-time 2023-12-04 2:33:30
System Date-time changed successfully
Local Time is now Mon 2023-12-04 02:33:30 UTC
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear acl counters</h>

Clears all ACL counters.

### Version History

Introduced in Cumulus Linux 5.6.0

### Example

```
cumulus@switch:~$ nv action clear acl counters
acl counters cleared.
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear evpn vni</h>

Clears duplicate addresses for all VNIs.

### Version History

Introduced in Cumulus Linux 5.6.0

### Example

```
cumulus@switch:~$ nv action clear evpn vni
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear evpn vni \<vni-id\></h>

Clears duplicate addresses for the specified VNI.

### Command Syntax

| Syntax |  Description   |
| --------- | -------------- |
| `<vni-id>` |  The VNI ID.|

### Version History

Introduced in Cumulus Linux 5.6.0

### Example

```
cumulus@switch:~$ nv action clear evpn vni 10
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear evpn vni \<vni-id\> host \<host-id\></h>

Clears the duplicate host address for the specified VNI.

### Command Syntax

| Syntax |  Description   |
| --------- | -------------- |
| `<vni-id>` |  The VNI ID.|
| `<host-id>` | The IP address of the host. |

### Version History

Introduced in Cumulus Linux 5.6.0

### Example

```
cumulus@switch:~$ nv action clear evpn vni 10 host 10.0.0.9
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear evpn vni \<vni\> mac \<mac-address\></h>

Clears the duplicate MAC address for the specified VNI.

### Command Syntax

| Syntax |  Description   |
| --------- | -------------- |
| `<vni-id>` |  The VNI ID.|
| `<mac-address>` | The MAC address you want to clear. |

### Version History

Introduced in Cumulus Linux 5.6.0

### Example

```
cumulus@switch:~$ nv action clear evpn vni 10 mac 00:e0:ec:20:12:62
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear interface counters</h>

Clears all interface-specific counters from all interfaces. Interface counters provide information about an interface, such as the number of packets intentionally or intentionally dropped, the number of inbound and outbound packets discarded (even if the switch detected no errors), the number of inbound and outbound packets not transmitted because of errors, and so on.

This command does not clear counters in the kernel or hardware.

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear interface counters
all interface counters cleared.
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear interface \<interface\> bond mlag lacp-conflict</h>

Clears the MLAG LACP conflict on the specified interface bond. A conflict can be an LACP partner MAC address mismatch or a duplicate LACP partner MAC address.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<interface-id>` | The interface that has an LACP conflict. |

### Version History

Introduced in Cumulus Linux 5.0.0

### Example

```
cumulus@switch:~$ nv action clear interface swp1 bond mlag lacp-conflict
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear interface \<interface-id\> bridge domain \<domain-id\> stp bpduguardviolation</h>

Clears the BPDU guard violation from the specified interface and recovers the interface from the `protodown` state.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<interface-id>` | The interface on which you want to clear the BPDU guard violation. |

### Version History

Introduced in Cumulus Linux 5.7.0

### Example

```
cumulus@switch:~$ nv action clear interface swp1 bridge domain br_default stp bpduguardviolation
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear interface \<interface\> counters</h>

Clears all interface-specific counters from the specified interface. Interface counters provide information about an interface, such as the number of packets intentionally or intentionally dropped, the number of inbound and outbound packets discarded even though the switch detected no errors, the number of inbound and outbound packets not transmitted because of errors, and so on.

This command does not clear counters in the kernel or hardware.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<interface-id>` | The interface on which you want to clear counters. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear interface swp1 counters
swp1 counters cleared.
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear interface \<interface-id\> counters ptp</h>

Clears PTP counters on the specified interface.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<interface-id>` | The interface on which you want to clear PTP counters. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear interface swp1 counters ptp
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear interface \<interface-id\> counters synce</h>

Clears SyncE counters on the specified interface.

{{%notice note%}}
In Cumulus Linux 5.6 and earlier, this command is `nv action clear interface <interface-id> synce counters`.
{{%/notice%}}

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<interface-id>` | The interface on which you want to clear SyncE counters. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear interface swp1 counters synce
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear interface \<interface-id\> link flap-protection violation</h>

Clears the `protodown` state of the interface and brings the interface back up.

{{%notice note%}}
In Cumulus Linux 5.8 and earlier, this command is `nv action clear interface <interface-id> link protodown link-flap`.
{{%/notice%}}

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<interface-id>` | The interface on which you want to clear the `protodown` state. |

### Version History

Introduced in Cumulus Linux 5.9.0

### Example

```
cumulus@switch:~$ nv action clear interface swp1 link flap-protection violation
link-flap state cleared on swp1.
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear interface \<interface-id\> qos buffer</h>

Clears QoS buffer counters on the specified interface.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<interface-id>` | The interface on which you want to clear the QoS buffer. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear interface swp1 qos buffer
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear interface \<interface-id\> qos pfc-watchdog deadlock-count</h>

Clears the QoS PFC watchdog deadlock count on the specified interface. PFC watchdog detects and mitigates pause storms on ports where you enable PFC or link pause.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<interface-id>` | The interface on which you want to clear the PFC watchdog deadlock count. |

### Version History

Introduced in Cumulus Linux 5.6.0

### Example

```
cumulus@switch:~$ nv action clear interface swp1 qos pfc-watchdog deadlock-count
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear interface \<interface-id\> qos roce counters</h>

Clears QoS RoCE counters on the specified interface.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<interface-id>` | The interface on which you want to clear RoCE counters. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear interface swp1 qos roce counters
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear mlag lacp-conflict</h>

Clears the MLAG LACP conflict. A conflict can be an LACP partner MAC address mismatch or a duplicate LACP partner MAC address.

### Version History

Introduced in Cumulus Linux 5.0.0

### Example

```
cumulus@switch:~$ nv action clear mlag lacp-conflict 
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear qos buffer multicast-switch-priority</h>

Clears the QoS multicast switch priority buffers.

### Version History

Introduced in Cumulus Linux 5.4.0

### Example

```
cumulus@switch:~$ nv action clear qos buffer multicast-switch-priority 
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear qos buffer pool</h>

Clears the QoS pool buffers.

### Version History

Introduced in Cumulus Linux 5.4.0

### Example

```
cumulus@switch:~$ nv action clear qos buffer pool 
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear router bgp</h>

Clears BGP sessions with all neighbors.

### Version History

Introduced in Cumulus Linux 5.6.0

### Example

```
cumulus@switch:~$ nv action clear router bgp
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear router bgp in prefix-filter</h>

Clears and refreshes inbound routes for all neighbors, address families, and VRFs and refreshes the outbound route filtering prefix list.

### Version History

Introduced in Cumulus Linux 5.6.0

### Example

```
cumulus@switch:~$ nv action clear router bgp in prefix-filter
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear router bgp soft</h>

Clears all routes with all neighbors, address families, and VRFs.

### Version History

Introduced in Cumulus Linux 5.6.0

### Example

```
cumulus@switch:~$ nv action clear router bgp soft
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear router bgp soft in</h>

Clears and refreshes all inbound routes with all neighbors, address families, and VRFs.

### Version History

Introduced in Cumulus Linux 5.6.0

### Example

```
cumulus@switch:~$ nv action clear router bgp soft in
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear router bgp soft out</h>

Clears and resends all outbound routes with all neighbors, address families, and VRFs.

### Version History

Introduced in Cumulus Linux 5.6.0

### Example

```
cumulus@switch:~$ nv action clear router bgp soft out
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear router bgp out</h>

Clears and refreshes outbound routes for all neighbors, address families, and VRFs.

### Version History

Introduced in Cumulus Linux 5.6.0

### Example

```
cumulus@switch:~$ nv action clear router bgp out
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear router igmp interfaces</h>

Clears the IGMP interface state.

### Version History

Introduced in Cumulus Linux 5.6.0

### Example

```
cumulus@switch:~$ nv action clear router igmp interfaces
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear router policy prefix-list</h>

Clears all IP prefix list statistics.

### Version History

Introduced in Cumulus Linux 5.6.0

### Example

```
cumulus@switch:~$ nv action clear router policy prefix-list
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear router policy prefix-list \<prefix-list-id\></h>

Clears statistics for the specified prefix list.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<prefix-list-id>` | The name of the prefix list whose statistics you want to clear. |

### Version History

Introduced in Cumulus Linux 5.6.0

### Example

```
cumulus@switch:~$ nv action clear router policy prefix-list prefixlist1
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear router policy prefix-list \<prefix-list-id\> rule \<rule-id\> match \<match-id\></h>

Clears statistics for a specific prefix list rule number and match ID.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<prefix-list-id>` | The name of the prefix list whose statistics you want to clear. |
| `<rule-id>` | The prefix list rule number. |
| `<match-id>` | The prefix list match criteria. |

### Version History

Introduced in Cumulus Linux 5.6.0

### Example

```
cumulus@switch:~$ nv action clear router policy prefix-list prefixlist1 rule 10 match 10.0.0.0/16
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear router policy route-map</h>

Clears all route map counters.

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear router policy route-map
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear router policy route-map \<route-map-id\></h>

Clears counters for the specified route map.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<route-map-id>` | The route map you want to clear. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear router policy route-map ROUTEMAP1
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear service ptp \<instance-id\> monitor violations log max-offset</h>

Clears the PTP monitor violation log maximum offset value.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<instance-id>` |  The PTP instance number used for management purposes. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear service ptp 1 monitor violations log max-offset
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear service ptp \<instance-id\> monitor violations log min-offset</h>

Clears the PTP monitor violation log minumum offset value.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<instance-id>` |  The PTP instance number used for management purposes. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear service ptp 1 monitor violations log min-offset
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear service ptp \<instance-id\> monitor violations log path-delay</h>

Clears the PTP monitor violation log path delay value.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<instance-id>` |  The PTP instance number used for management purposes. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear service ptp 1 monitor violations log path-delay
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear system api session user \<user-id\></h>

Clears an NVUE user session.

NVUE uses sessions to authenticate and authorize requests. After authenticating the user with the first request, NVUE stores the session in the `nvued` cache. NVUE authenticates subsequent interactions within the session locally, eliminating the need to repeatedly check with external authentication servers. This process enhances system performance and efficiency, making it ideal for high-traffic environments.
- If you make changes to a user group, password, RADIUS, TACACS, or LDAP server setting locally on the switch, NVUE clears the current session automatically.
- If you make changes directly on the RADIUS, TACACS, or LDAP server, you must clear the user session with the `nv action clear system api session user <user>` command or clear all sessions with the `nv action clear system api session` command.

   {{%notice note%}}
If you do not clear a user session after making changes directly on the RADIUS, TACACS, or LDAP server, NVUE uses the existing session for authentication and authorization until the session times out (up to 60 minutes).
{{%/notice%}}

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<user-id>` |  The user account. |

### Version History

Introduced in Cumulus Linux 5.10.0

### Example

```
cumulus@switch:~$ nv action clear system api session user admin
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear system link flap-protection violation</h>

Clears the `protodown` links on the switch.

{{%notice note%}}
In Cumulus Linux 5.8 and earlier, this command is `nv action clear system link protodown link-flap`.
{{%/notice%}}

### Version History

Introduced in Cumulus Linux 5.9.0

### Example

```
cumulus@switch:~$ nv action clear system link flap-protection violation
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp address-family ipv4-unicast in</h>

Clears BGP IPv4 inbound routes.

This command does not clear counters in the kernel or hardware and does not reset BGP neighbor adjacencies.

- When the switch has a neighbor configured with `soft-reconfiguration inbound` enabled, this command clears the routes in the soft reconfiguration table for the address family. This results in reevaluating routes in the BGP table against any applied input policies.
- When the switch has a neighbor configured *without* the `soft-reconfiguration inbound` option enabled, this command sends the peer a route refresh message.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp address-family ipv4-unicast in
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp address-family ipv4-unicast soft in</h>

Clears BGP IPv4 inbound routes for all BGP peers.

This command does not clear counters in the kernel or hardware and does not reset BGP neighbor adjacencies.

- When the switch has a neighbor configured with `soft-reconfiguration inbound` enabled, this command clears the routes in the soft reconfiguration table for the address family. This results in reevaluating routes in the BGP table against any applied input policies.
- When the switch has a neighbor configured *without* the `soft-reconfiguration inbound` option enabled, this command sends the peer a route refresh message.
- If you do not specify the direction `in`, the command affects both inbound and outbound routes depending on whether you enable soft-reconfiguration inbound.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp address-family soft in
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp address-family ipv4-unicast soft out</h>

Clears BGP IPv4 outbound routes for all BGP peers.

This command does not:
- Clear counters in the kernel or hardware.
- Reset BGP neighbor adjacencies.
- Readvertise all routes to BGP peers.

If you do not specify the direction `out`, the command affects both inbound and outbound routes depending on whether soft-reconfiguration inbound is enabled.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp address-family soft out
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp address-family ipv4-unicast out</h>

Clears BGP IPv4 outbound routes.

This command does not:
- Clear counters in the kernel or hardware.
- Reset BGP neighbor adjacencies.
- Readvertise all routes to BGP peers.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp address-family ipv4-unicast in
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp address-family ipv6-unicast in</h>

Clears BGP IPv6 inbound routes.

This command does not clear counters in the kernel or hardware and does not reset BGP neighbor adjacencies.

- When the switch has a neighbor configured with `soft-reconfiguration inbound` enabled, this command clears the routes in the soft reconfiguration table for the address family. This results in reevaluating routes in the BGP table against any applied input policies.
- When the switch has a neighbor configured *without* the `soft-reconfiguration inbound` option enabled, this command sends the peer a route refresh message.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp address-family ipv6-unicast in
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp address-family ipv6-unicast soft in</h>

Clears BGP IPv6 inbound routes for all BGP peers.

This command does not clear counters in the kernel or hardware and does not reset BGP neighbor adjacencies.

- When the switch has a neighbor configured with `soft-reconfiguration inbound` enabled, this command clears the routes in the soft reconfiguration table for the address family. This results in reevaluating routes in the BGP table against any applied input policies.
- When the switch has a neighbor configured *without* the `soft-reconfiguration inbound` option enabled, this command sends the peer a route refresh message.
- If you do not specify the direction `in`, the command affects both inbound and outbound routes depending on whether soft-reconfiguration inbound is enabled.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp address-family ipv6-unicast soft in
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp address-family ipv6-unicast soft out</h>

Clears BGP IPv6 outbound routes for all BGP peers.

This command does not:
- Clear counters in the kernel or hardware.
- Reset BGP neighbor adjacencies.
- Readvertise all routes to BGP peers.

If you do not specify the direction `out`, the command affects both inbound and outbound routes depending on whether soft-reconfiguration inbound is enabled.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp address-family ipv6-unicast soft out
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp address-family ipv6-unicast out</h>

Clears BGP IPv6 outbound routes.

This command does not:
- Clear counters in the kernel or hardware.
- Reset BGP neighbor adjacencies.
- Readvertise all routes to BGP peers.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp address-family ipv6-unicast out
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp address-family l2vpn-evpn in</h>

Clears BGP EVPN inbound routes.

This command does not clear counters in the kernel or hardware and does not reset BGP neighbor adjacencies.

- When the switch has a neighbor configured with `soft-reconfiguration inbound` enabled, this command clears the routes in the soft reconfiguration table for the address family. This results in reevaluating routes in the BGP table against any applied input policies.
- When the switch has a neighbor configured *without* the `soft-reconfiguration inbound` option enabled, this command sends the peer a route refresh message.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp address-family l2vpn-evpn in
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp address-family l2vpn-evpn soft in</h>

Clears BGP EVPN inbound routes for all BGP peers.

This command does not clear counters in the kernel or hardware and does not reset BGP neighbor adjacencies.

- When the switch has a neighbor configured with `soft-reconfiguration inbound` enabled, this command clears the routes in the soft reconfiguration table for the address family. This results in reevaluating routes in the BGP table against any applied input policies.
- When the switch has a neighbor configured *without* the `soft-reconfiguration inbound` option enabled, this command sends the peer a route refresh message.
- If you do not specify the direction `in`, the command affects both inbound and outbound routes depending on whether soft-reconfiguration inbound is enabled.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp address-family l2vpn-evpn soft in
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp address-family l2vpn-evpn soft out</h>

Clears BGP EVPN outbound routes for all BGP peers.

This command does not:
- Clear counters in the kernel or hardware.
- Reset BGP neighbor adjacencies.
- Readvertise all routes to BGP peers.

If you do not specify the direction `out`, the command affects both inbound and outbound routes depending on whether soft-reconfiguration inbound is enabled.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp address-family l2vpn-evpn soft out
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp address-family l2vpn-evpn out</h>

Clears BGP EVPN outbound routes.

This command does not:
- Clear counters in the kernel or hardware.
- Reset BGP neighbor adjacencies.
- Readvertise all routes to BGP peers.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp address-family l2vpn-evpn out
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp in prefix-filter</h>

Clears and refreshes inbound routes for all neighbors and address families in the specified VRF and refreshes the outbound route filtering prefix list.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |

### Version History

Introduced in Cumulus Linux 5.6.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp in prefix-filter
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp neighbor \<neighbor-id\> address-family ipv4-unicast in</h>

Clears IPv4 inbound routes for a specific BGP peer in the specified VRF.

This command does not clear counters in the kernel or hardware and does not reset BGP neighbor adjacencies.

- When the switch has a neighbor configured with `soft-reconfiguration inbound` enabled, this command clears the routes in the soft reconfiguration table for the address family. This results in reevaluating routes in the BGP table against any applied input policies.
- When the switch has a neighbor configured *without* the `soft-reconfiguration inbound` option enabled, this command sends the peer a route refresh message.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |
| `<neighbor-id>` | The IP address of the BGP peer or the interface if you are using unnumbered BGP. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp neighbor swp51 address-family ipv4-unicast in
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp neighbor \<neighbor-id\> address-family ipv4-unicast soft in</h>

Clears IPv4 inbound routes for a specific BGP peer in the specified VRF without resetting the peer session.

This command does not clear counters in the kernel or hardware and does not reset BGP neighbor adjacencies.

- When the switch has a neighbor configured with `soft-reconfiguration inbound` enabled, this command clears the routes in the soft reconfiguration table for the address family. This results in reevaluating routes in the BGP table against any applied input policies.
- When the switch has a neighbor configured *without* the `soft-reconfiguration inbound` option enabled, this command sends the peer a route refresh message.
- If you do not specify the direction `in`, the command affects both inbound and outbound routes depending on whether soft-reconfiguration inbound is enabled.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |
| `<neighbor-id>` | The IP address of the BGP peer or the interface if you are using unnumbered BGP. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp neighbor swp51 address-family ipv4-unicast soft in
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp neighbor \<neighbor-id\> address-family ipv4-unicast soft out</h>

Clears IPv4 outbound routes for a specific BGP peer in the specified VRF without resetting the peer session.

This command does not:
- Clear counters in the kernel or hardware.
- Reset BGP neighbor adjacencies.
- Readvertise all routes to BGP peers.

If you do not specify the direction `out`, the command affects both inbound and outbound routes depending on whether soft-reconfiguration inbound is enabled.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |
| `<neighbor-id>` | The IP address of the BGP peer or the interface if you are using unnumbered BGP. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp neighbor swp51 address-family ipv4-unicast soft out
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp neighbor \<neighbor-id\> address-family ipv4-unicast out</h>

Clears IPv4 outbound routes for a specific BGP peer in the specified VRF.

This command does not:
- Clear counters in the kernel or hardware.
- Reset BGP neighbor adjacencies.
- Readvertise all routes to BGP peers.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |
| `<neighbor-id>` | The IP address of the BGP peer or the interface if you are using unnumbered BGP. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp neighbor swp51 address-family ipv4-unicast out
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp neighbor \<neighbor-id\> address-family ipv6-unicast in</h>

Clears IPv6 inbound routes for a specific BGP peer in the specified VRF.

This command does not clear counters in the kernel or hardware and does not reset BGP neighbor adjacencies.

- When the switch has a neighbor configured with `soft-reconfiguration inbound` enabled, this command clears the routes in the soft reconfiguration table for the address family. This results in reevaluating routes in the BGP table against any applied input policies.
- When the switch has a neighbor configured *without* the `soft-reconfiguration inbound` option enabled, this command sends the peer a route refresh message.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |
| `<neighbor-id>` | The IP address of the BGP peer or the interface if you are using unnumbered BGP. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp neighbor swp51 address-family ipv6-unicast in
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp neighbor \<neighbor-id\> address-family ipv6-unicast soft in</h>

Clears IPv6 inbound routes for a specific BGP peer in the specified VRF without resetting the peer session.

This command does not clear counters in the kernel or hardware and does not reset BGP neighbor adjacencies.

- When the switch has a neighbor configured with `soft-reconfiguration inbound` enabled, this command clears the routes in the soft reconfiguration table for the address family. This results in reevaluating routes in the BGP table against any applied input policies.
- When the switch has a neighbor configured *without* the `soft-reconfiguration inbound` option enabled, this command sends the peer a route refresh message.
- If you do not specify the direction `in`, the command affects both inbound and outbound routes depending on whether soft-reconfiguration inbound is enabled.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |
| `<neighbor-id>` | The IP address of the BGP peer or the interface if you are using unnumbered BGP. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp neighbor swp51 address-family ipv6-unicast soft in
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp neighbor \<neighbor-id\> address-family ipv6-unicast soft out</h>

Clears IPv6 outbound routes for a specific BGP peer in the specified VRF without resetting the peer session.

This command does not:
- Clear counters in the kernel or hardware.
- Reset BGP neighbor adjacencies.
- Readvertise all routes to BGP peers.

If you do not specify the direction `out`, the command affects both inbound and outbound routes depending on whether soft-reconfiguration inbound is enabled.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |
| `<neighbor-id>` | The IP address of the BGP peer or the interface if you are using unnumbered BGP. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp neighbor swp51 address-family ipv6-unicast soft out
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp neighbor \<neighbor-id\> address-family ipv6-unicast out</h>

Clears IPv6 outbound routes for a specific BGP peer in the specified VRF.

This command does not:
- Clear counters in the kernel or hardware.
- Reset BGP neighbor adjacencies.
- Readvertise all routes to BGP peers.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |
| `<neighbor-id>` | The IP address of the BGP peer or the interface if you are using unnumbered BGP. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp neighbor swp51 address-family ipv6-unicast out
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp neighbor \<neighbor-id\> address-family l2vpn-evpn in</h>

Clears EVPN inbound routes for a specific BGP peer in the specified VRF.

This command does not clear counters in the kernel or hardware and does not reset BGP neighbor adjacencies.

- When the switch has a neighbor configured with `soft-reconfiguration inbound` enabled, this command clears the routes in the soft reconfiguration table for the address family. This results in reevaluating routes in the BGP table against any applied input policies.
- When the switch has a neighbor configured *without* the `soft-reconfiguration inbound` option enabled, this command sends the peer a route refresh message.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |
| `<neighbor-id>` | The IP address of the BGP peer or the interface if you are using unnumbered BGP. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp neighbor swp51 address-family l2vpn-evpn in
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp neighbor \<neighbor-id\> address-family l2vpn-evpn soft in</h>

Clears EVPN inbound routes for a specific BGP peer in the specified VRF without resetting the peer session.

This command does not clear counters in the kernel or hardware and does not reset BGP neighbor adjacencies.

- When the switch has a neighbor configured with `soft-reconfiguration inbound` enabled, this command clears the routes in the soft reconfiguration table for the address family. This results in reevaluating routes in the BGP table against any applied input policies.
- When the switch has a neighbor configured *without* the `soft-reconfiguration inbound` option enabled, this command sends the peer a route refresh message.
- If you do not specify the direction `in`, the command affects both inbound and outbound routes depending on whether soft-reconfiguration inbound is enabled.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |
| `<neighbor-id>` | The IP address of the BGP peer or the interface if you are using unnumbered BGP. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp neighbor swp51 address-family l2vpn-evpn soft in
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp neighbor \<neighbor-id\> address-family l2vpn-evpn soft out</h>

Clears EVPN outbound routes for a specific BGP peer in the specified VRF without resetting the peer session.

This command does not:
- Clear counters in the kernel or hardware.
- Reset BGP neighbor adjacencies.
- Readvertise all routes to BGP peers.

If you do not specify the direction `out`, the command affects both inbound and outbound routes depending on whether soft-reconfiguration inbound is enabled.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |
| `<neighbor-id>` | The IP address of the BGP peer or the interface if you are using unnumbered BGP. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp neighbor swp51 address-family l2vpn-evpn soft out
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp neighbor \<neighbor-id\> address-family l2vpn-evpn out</h>

Clears EVPN outbound routes for a specific BGP peer in the specified VRF.

This command does not:
- Clear counters in the kernel or hardware.
- Reset BGP neighbor adjacencies.
- Readvertise all routes to BGP peers.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |
| `<neighbor-id>` | The IP address of the BGP peer or the interface if you are using unnumbered BGP. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp neighbor swp51 address-family l2vpn-evpn out
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp neighbor \<neighbor-id\> in</h>

Clears inbound routes for a specific BGP peer in the specified VRF.

This command does not clear counters in the kernel or hardware and does not reset BGP neighbor adjacencies.

- When the switch has a neighbor configured with `soft-reconfiguration inbound` enabled, this command clears the routes in the soft reconfiguration table for the address family. This results in reevaluating routes in the BGP table against any applied input policies.
- When the switch has a neighbor configured *without* the `soft-reconfiguration inbound` option enabled, this command sends the peer a route refresh message.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |
| `<neighbor-id>` | The IP address of the BGP peer or the interface if you are using unnumbered BGP. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp neighbor swp51 in
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp neighbor \<neighbor-id\> soft in</h>

Clears inbound routes for a specific BGP peer in the specified VRF without resetting the peer session.

This command does not clear counters in the kernel or hardware and does not reset BGP neighbor adjacencies.

- When the switch has a neighbor configured with `soft-reconfiguration inbound` enabled, this command clears the routes in the soft reconfiguration table for the address family. This results in reevaluating routes in the BGP table against any applied input policies.
- When the switch has a neighbor configured *without* the `soft-reconfiguration inbound` option enabled, this command sends the peer a route refresh message.
- If you do not specify the direction `in`, the command affects both inbound and outbound routes depending on whether soft-reconfiguration inbound is enabled.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |
| `<neighbor-id>` | The IP address of the BGP peer or the interface if you are using unnumbered BGP. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp neighbor swp51 soft in
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp neighbor \<neighbor-id\> soft out</h>

Clears outbound routes for a specific BGP peer in the specified VRF without resetting the peer session.

This command does not:
- Clear counters in the kernel or hardware.
- Reset BGP neighbor adjacencies.
- Readvertise all routes to BGP peers.

If you do not specify the direction `out`, the command affects both inbound and outbound routes depending on whether soft-reconfiguration inbound is enabled.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |
| `<neighbor-id>` | The IP address of the BGP peer or the interface if you are using unnumbered BGP. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp neighbor swp51 soft out
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp neighbor \<neighbor-id\> out</h>

Clears outbound routes for a specific BGP peer in the specified VRF.

This command does not:
- Clear counters in the kernel or hardware.
- Reset BGP neighbor adjacencies.
- Readvertise all routes to BGP peers.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |
| `<neighbor-id>` | The IP address of the BGP peer or the interface if you are using unnumbered BGP. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp neighbor swp51 out
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp peer-group \<peer-group-id\> address-family ipv4-unicast in</h>

Clears IPv4 inbound routes for a specific BGP peer group in the specified VRF.

This command does not clear counters in the kernel or hardware and does not reset BGP neighbor adjacencies.

- When the switch has a neighbor configured with `soft-reconfiguration inbound` enabled, this command clears the routes in the soft reconfiguration table for the address family. This results in reevaluating routes in the BGP table against any applied input policies.
- When the switch has a neighbor configured *without* the `soft-reconfiguration inbound` option enabled, this command sends the peer a route refresh message.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |
| `<peer-group-id>` |  The peer group name. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp peer-group SPINES address-family ipv4-unicast in
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp peer-group \<peer-group-id\> address-family ipv4-unicast soft in</h>

Clears IPv4 inbound routes for a specific BGP peer group in the specified VRF.

This command does not clear counters in the kernel or hardware and does not reset BGP neighbor adjacencies.

- When the switch has a neighbor configured with `soft-reconfiguration inbound` enabled, this command clears the routes in the soft reconfiguration table for the address family. This results in reevaluating routes in the BGP table against any applied input policies.
- When the switch has a neighbor configured *without* the `soft-reconfiguration inbound` option enabled, this command sends the peer a route refresh message.
- If you do not specify the direction `in`, the command affects both inbound and outbound routes depending on whether soft-reconfiguration inbound is enabled.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |
| `<peer-group-id>` |  The peer group name. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp peer-group SPINES address-family ipv4-unicast soft in
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp peer-group \<peer-group-id\> address-family ipv4-unicast soft out</h>

Clears IPv4 outbound routes for a specific BGP peer group in the specified VRF.

This command does not:
- Clear counters in the kernel or hardware.
- Reset BGP neighbor adjacencies.
- Readvertise all routes to BGP peers.

If you do not specify the direction `out`, the command affects both inbound and outbound routes depending on whether soft-reconfiguration inbound is enabled.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |
| `<peer-group-id>` |  The peer group name. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp peer-group SPINES address-family ipv4-unicast soft out
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp peer-group \<peer-group-id\> address-family ipv4-unicast out</h>

Clears IPv4 outbound routes for a specific BGP peer group in the specified VRF.

This command does not:
- Clear counters in the kernel or hardware.
- Reset BGP neighbor adjacencies.
- Readvertise all routes to BGP peers.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |
| `<peer-group-id>` |  The peer group name. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp peer-group SPINES address-family ipv4-unicast out
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp peer-group \<peer-group-id\> address-family ipv6-unicast in</h>

Clears IPv6 inbound routes for a specific BGP peer group in the specified VRF.

This command does not clear counters in the kernel or hardware and does not reset BGP neighbor adjacencies.

- When the switch has a neighbor configured with `soft-reconfiguration inbound` enabled, this command clears the routes in the soft reconfiguration table for the address family. This results in reevaluating routes in the BGP table against any applied input policies.
- When the switch has a neighbor configured *without* the `soft-reconfiguration inbound` option enabled, this command sends the peer a route refresh message.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |
| `<peer-group-id>` |  The peer group name. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp peer-group SPINES address-family ipv6-unicast in
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp peer-group \<peer-group-id\> address-family ipv6-unicast soft in</h>

Clears IPv6 inbound routes for a specific BGP peer group in the specified VRF.

This command does not clear counters in the kernel or hardware and does not reset BGP neighbor adjacencies.

- When the switch has a neighbor configured with `soft-reconfiguration inbound` enabled, this command clears the routes in the soft reconfiguration table for the address family. This results in reevaluating routes in the BGP table against any applied input policies.
- When the switch has a neighbor configured *without* the `soft-reconfiguration inbound` option enabled, this command sends the peer a route refresh message.
- If you do not specify the direction `in`, the command affects both inbound and outbound routes depending on whether soft-reconfiguration inbound is enabled.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |
| `<peer-group-id>` |  The peer group name. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp peer-group SPINES address-family ipv6-unicast soft in
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp peer-group \<peer-group-id\> address-family ipv6-unicast soft out</h>

Clears IPv6 outbound routes for a specific BGP peer group in the specified VRF.

This command does not:
- Clear counters in the kernel or hardware.
- Reset BGP neighbor adjacencies.
- Readvertise all routes to BGP peers.

If you do not specify the direction `out`, the command affects both inbound and outbound routes depending on whether soft-reconfiguration inbound is enabled.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |
| `<peer-group-id>` |  The peer group name. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp peer-group SPINES address-family ipv6-unicast soft out
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp peer-group \<peer-group-id\> address-family ipv6-unicast out</h>

Clears IPv6 outbound routes for a specific BGP peer group in the specified VRF.

This command does not:
- Clear counters in the kernel or hardware.
- Reset BGP neighbor adjacencies.
- Readvertise all routes to BGP peers.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |
| `<peer-group-id>` |  The peer group name. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp peer-group SPINES address-family ipv6-unicast out
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp peer-group \<peer-group-id\> address-family l2vpn-evpn in</h>

Clears EVPN inbound routes for a specific BGP peer group in the specified VRF.

This command does not clear counters in the kernel or hardware and does not reset BGP neighbor adjacencies.

- When the switch has a neighbor configured with `soft-reconfiguration inbound` enabled, this command clears the routes in the soft reconfiguration table for the address family. This results in reevaluating routes in the BGP table against any applied input policies.
- When the switch has a neighbor configured *without* the `soft-reconfiguration inbound` option enabled, this command sends the peer a route refresh message.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |
| `<peer-group-id>` |  The peer group name. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp peer-group SPINES address-family l2vpn-evpn in
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp peer-group \<peer-group-id\> address-family l2vpn-evpn soft in</h>

Clears EVPN inbound routes for a specific BGP peer group in the specified VRF.

This command does not clear counters in the kernel or hardware and does not reset BGP neighbor adjacencies.

- When the switch has a neighbor configured with `soft-reconfiguration inbound` enabled, this command clears the routes in the soft reconfiguration table for the address family. This results in reevaluating routes in the BGP table against any applied input policies.
- When the switch has a neighbor configured *without* the `soft-reconfiguration inbound` option enabled, this command sends the peer a route refresh message.
- If you do not specify the direction `in`, the command affects both inbound and outbound routes depending on whether soft-reconfiguration inbound is enabled.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |
| `<peer-group-id>` |  The peer group name. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp peer-group SPINES address-family l2vpn-evpn soft in
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp peer-group \<peer-group-id\> address-family l2vpn-evpn soft out</h>

Clears EVPN outbound routes for a specific BGP peer group in the specified VRF.

This command:
- Does not clear counters in the kernel or hardware
- Does not reset BGP neighbor adjacencies.
- Does not readvertise all routes to BGP peers.

If you do not specify the direction `out`, the command affects both inbound and outbound routes depending on whether soft-reconfiguration inbound is enabled.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |
| `<peer-group-id>` |  The peer group name. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp peer-group SPINES address-family l2vpn-evpn soft out
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp peer-group \<peer-group-id\> address-family l2vpn-evpn out</h>

Clears EVPN outbound routes for a specific BGP peer group in the specified VRF.

This command does not:
- Clear counters in the kernel or hardware.
- Reset BGP neighbor adjacencies.
- Readvertise all routes to BGP peers.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |
| `<peer-group-id>` |  The peer group name. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp peer-group SPINES address-family l2vpn-evpn out
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp peer-group \<peer-group-id\> in</h>

Clears inbound routes for a specific BGP peer group in the specified VRF.

This command does not clear counters in the kernel or hardware and does not reset BGP neighbor adjacencies.

- When the switch has a neighbor configured with `soft-reconfiguration inbound` enabled, this command clears the routes in the soft reconfiguration table for the address family. This results in reevaluating routes in the BGP table against any applied input policies.
- When the switch has a neighbor configured *without* the `soft-reconfiguration inbound` option enabled, this command sends the peer a route refresh message.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |
| `<peer-group-id>` |  The peer group name. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp peer-group SPINES in
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp peer-group \<peer-group-id\> soft in</h>

Clears inbound routes for a specific BGP peer group in the specified VRF.

This command does not clear counters in the kernel or hardware and does not reset BGP neighbor adjacencies.

- When the switch has a neighbor configured with `soft-reconfiguration inbound` enabled, this command clears the routes in the soft reconfiguration table for the address family. This results in reevaluating routes in the BGP table against any applied input policies.
- When the switch has a neighbor configured *without* the `soft-reconfiguration inbound` option enabled, this command sends the peer a route refresh message.
- If you do not specify the direction `in`, the command affects both inbound and outbound routes depending on whether soft-reconfiguration inbound is enabled.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |
| `<peer-group-id>` |  The peer group name. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp peer-group SPINES soft in
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp peer-group \<peer-group-id\> soft out</h>

Clears outbound routes for a specific BGP peer group in the specified VRF.

This command does not:
- Clear counters in the kernel or hardware.
- Reset BGP neighbor adjacencies.
- Readvertise all routes to BGP peers.

If you do not specify the direction `out`, the command affects both inbound and outbound routes depending on whether soft-reconfiguration inbound is enabled.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |
| `<peer-group-id>` |  The peer group name. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp peer-group SPINES soft out
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp peer-group \<peer-group-id\> out</h>

Clears outbound routes for a specific BGP peer group in the specified VRF.

This command does not:
- Clear counters in the kernel or hardware.
- Reset BGP neighbor adjacencies.
- Readvertise all routes to BGP peers.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |
| `<peer-group-id>` |  The peer group name. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp peer-group SPINES out
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp soft</h>

Clears all routes with all neighbors and address families in the specified VRF.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |

### Version History

Introduced in Cumulus Linux 5.6.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp soft
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp soft in</h>

Clears and refreshes all inbound routes with all neighbors and address families in the specified VRF.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |

### Version History

Introduced in Cumulus Linux 5.6.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp soft in
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp soft out</h>

Clears and resends all outbound routes with all neighbors and address families in the specified VRF.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |

### Version History

Introduced in Cumulus Linux 5.6.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp soft out
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router bgp out</h>

Clears and refreshes outbound routes for all neighbors and address families in the specified VRF.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |

### Version History

Introduced in Cumulus Linux 5.6.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router bgp out
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router ospf database</h>

Clear the OSPF database, reestablishes neighborships, and reoriginates LSAs.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |

### Version History

Introduced in Cumulus Linux 5.10.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router ospf database
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router ospf interface</h>

Clears all counters for the OSPF interfaces.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router ospf interface
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router ospf interface \<interface-id\></h>

Clears OSPF neighbor adjacency on the specified interface.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |
| `<interface-id>` | The interface on which you want to clear OSPF neighbor adjacency. |

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router ospf interface swp2
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router pim interfaces</h>

Clears PIM neighbors for all PIM interfaces in the specified VRF.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |

### Version History

Introduced in Cumulus Linux 5.6.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router pim interfaces
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action clear vrf \<vrf-id\> router pim interface-traffic</h>

Clears traffic statistics for all PIM interfaces in the specified VRF.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |

### Version History

Introduced in Cumulus Linux 5.6.0

### Example

```
cumulus@switch:~$ nv action clear vrf default router pim interface-traffic
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action deauthenticate interface \<interface-id\> dot1x authorized-sessions \<mac-address\></h>

Deauthenticates the 802.1X supplicant on the specified interface. If you do not want to notify the supplicant that they are being deauthenticated, you can add the `silent` option.

### Command Syntax

| Syntax |  Description   |
| ---------  | -------------- |
| `<interface-id>` |  The interface on which you want to deauthenticate the 802.1X supplicant. |
| `<mac-address>` |  The MAC address. |

### Version History

Introduced in Cumulus Linux 5.8.0

### Example

```
cumulus@switch:~$ nv action deauthenticate interface swp1 dot1x authorized-sessions 00:55:00:00:00:09 silent
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action delete system security ca-certificate \<cert-id\></h>

Deletes the CA certificate you specify.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<cert-id>` | The CA certificate you want to delete. |

### Version History

Introduced in Cumulus Linux 5.7.0

### Example

```
cumulus@switch:~$ nv action delete system security ca-certificate cert-1
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action delete system security certificate \<cert-id\></h>

Deletes the entity certificate you specify.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<cert-id>` | The entity certificate you want to delete. |

### Version History

Introduced in Cumulus Linux 5.7.0

### Example

```
cumulus@switch:~$ nv action delete system security certificate cert-1
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action disable system maintenance mode</h>

Disables maintenance mode and restores normal operation.

### Version History

Introduced in Cumulus Linux 5.7.0

### Example

```
cumulus@switch:~$ nv action disable system maintenance mode
System maintenance mode has been disabled successfully
 Current System Mode: cold  
 frr             : cold, up, up time: 12:57:48 (1 restart)
 switchd         : cold, up, up time: 13:12:13
 System Services : cold, up, up time: 13:12:32
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action disable system maintenance ports</h>

Restores the port admin state after maintenance.

### Version History

Introduced in Cumulus Linux 5.7.0

### Example

```
cumulus@switch:~$ nv action disable system maintenance ports
System maintenance ports has been disabled successfully
 Current System Mode: cold  
 Ports shutdown for Maintenance
 frr             : cold, up, up time: 13:00:57 (1 restart)
 switchd         : cold, up, up time: 13:15:22
 System Services : cold, up, up time: 13:15:41
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action disconnect system aaa user \<user-id\></h>

Disconnects authenticated and authorized users.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<user-id>` | The user you want to disconnect. |

### Version History

Introduced in Cumulus Linux 5.4.0

### Example

```
cumulus@switch:~$ nv action disconnect system aaa user admin2
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action enable system maintenance mode</h>

Enables maintenance mode. When maintenance mode is on, ISSU performs a graceful BGP shutdown, redirects traffic over the peerlink and brings down the MLAG port link. `switchd` maintains full capability.

### Version History

Introduced in Cumulus Linux 5.7.0

### Example

```
cumulus@switch:~$ nv action enable system maintenance mode
System maintenance mode has been enabled successfully
 Current System Mode: Maintenance, cold  
 Maintenance mode since Sat Nov 18 07:09:25 2023 (Duration: 00:00:00)
 frr             : Maintenance, cold, down, up time: 12:55:51 (1 restart)
 switchd         : Maintenance, cold, down, up time: 13:10:16
 System Services : Maintenance, cold, down, up time: 13:10:35
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action enable system maintenance ports</h>

Brings down the ports for maintenance.

### Version History

Introduced in Cumulus Linux 5.7.0

### Example

```
cumulus@switch:~$ nv action enable system maintenance ports
System maintenance ports has been enabled successfully
 Current System Mode: Maintenance, cold  
 Maintenance mode since Sat Nov 18 07:09:25 2023 (Duration: 00:00:56)
 frr             : Maintenance, cold, down, up time: 12:56:47 (1 restart)
 switchd         : Maintenance, cold, down, up time: 13:11:12
 System Services : Maintenance, cold, down, up time: 13:11:31
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action delete system tech-support files \<file-id\></h>

Deletes the specified technical support file (a compressed archive file of useful information for troubleshooting). 

### Command Syntax

| Syntax |  Description   |
| --------- | -------------- |
| `<file-id>`  |  The technical support file name and location. |

## Version History

Introduced in Cumulus Linux 5.10.0

### Example

```
cumulus@switch:~$ nv action delete system tech-support files /var/support/cl_support_leaf01_20240725_221237.txz
Action executing ...
File Delete Succeeded
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action generate system tech-support</h>

Generates a technical support file (compressed archive file of useful information for troubleshooting). 

## Version History

Introduced in Cumulus Linux 5.10.0

### Example

```
cumulus@switch:~$ nv action generate system tech-support
Action executing ...
Generating system tech-support file, it might take a few minutes...

Action executing ...
Generated tech-support
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action import system security ca-certificate \<cert-id\></h>

Imports a CA certificate.

Cumulus Linux includes a self-signed certificate and private key to use on the server so that it works out of the box. The switch generates the self-signed certificate and private key when it boots for the first time. The X.509 certificate with the public key is in `/etc/ssl/certs/cumulus.pem` and the corresponding private key is in `/etc/ssl/private/cumulus.key`.

NVIDIA recommends you use your own certificates and keys. 

- You can import a maximum of 50 CA certificates on the switch.
- The CA certificate you import contains sensitive private key information. NVIDIA recommends that you use a secure transport such as SFTP, SCP, or HTTPS.
- If the certificate is passphrase protected, you need to include the passphrase.
- You must provide a certificate ID (`<cert-id>`) to uniquely identify the certificate you import.


### Version History

Introduced in Cumulus Linux 5.7.0

### Example

```
cumulus@switch:~$ nv action import system security ca-certificate tls-cert-1 passphrase mypassphrase data "<public-key>" 
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action import system security certificate \<cert-id\></h>

Imports an entity certificate or certificate bundle.

Cumulus Linux includes a self-signed certificate and private key to use on the server so that it works out of the box. The switch generates the self-signed certificate and private key when it boots for the first time. The X.509 certificate with the public key is in `/etc/ssl/certs/cumulus.pem` and the corresponding private key is in `/etc/ssl/private/cumulus.key`.

NVIDIA recommends you use your own certificates and keys. 

- You can import a maximum of 25 entity certificates on the switch.
- The certificate you import contains sensitive private key information. NVIDIA recommends that you use a secure transport such as SFTP, SCP, or HTTPS.
- If the certificate is passphrase protected, you need to include the passphrase.
- A certificate bundle must be in .PFX or .P12 format.
- You must provide a certificate ID (`<cert-id>`) to uniquely identify the certificate you import.


### Version History

Introduced in Cumulus Linux 5.7.0

### Example

```
cumulus@switch:~$ nv action import system security certificate tls-cert-1 passphrase mypassphrase uri-bundle scp://user@pass:1.2.3.4:/opt/certs/cert.p12
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action reboot system</h>

Reboots the switch.

### Version History

Introduced in Cumulus Linux 5.5.0

### Example

```
cumulus@switch:~$ nv action reboot system
Rebooting System in cold mode
True
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action rotate system log</h>

Rotates the system log files. Cumulus Linux automatically manages log file size, preventing the logs from filling the storage space and slowing down the system.

### Version History

Introduced in Cumulus Linux 5.10.0

### Example

```
cumulus@switch:~$ nv action rotate system log
Action executing ...
Log rotation successful
Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action schedule system telemetry hft job \<date-time\> duration \<duration\> profile \<profile\> ports \<port-id\> description \<text\></h>

Configures the schedule for a high frequency telemetry data collection.

{{%notice note%}}
- You can schedule a maximum of 10 sessions (jobs). The switch can retain data for 10 jobs (completed, cancelled, or failed) in addition to the active jobs.
- You must configure data export (the target) before you can configure the schedule.
{{%/notice%}}

### Command Syntax

| Syntax |  Description   |
| ---------  | -------------- |
| `<date-time>` |  The start date and time for high frequency telemetry data collection in `YYYY-MM-DD HH:MM:SS` format. |
| `duration` | The session duration in seconds. The default value is 20 seconds. |
| `profile-id` | The high frequency telemetry data collection profile name. |
| `port-id` | The ports on which you want to collect the data. You can specify a range of ports, multiple comma separated ports, or `all` for all the ports. The default value is `all`. |
| `<text>` | A short reason why you are collecting the data. If the description contains more than one word, you must enclose the description in quotes. A description is optional.|

### Version History

Introduced in Cumulus Linux 5.10.0

### Example

```
cumulus@switch:~$ nv action schedule system telemetry hft job 2024-07-17 10:00:00 duration 30 profile profile1 ports swp1-swp9 description "bandwidth profiling"
Action executing ...
Job schedule successfull.

Action succeeded
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action upgrade system packages to latest use-vrf \<vrf-id\></h>

Upgrades all the packages to the latest distribution.

By default, the NVUE `nv action upgrade system packages` command runs in the management VRF. To run the command in a non-management VRF such as `default`, you must use the `use-vrf <vrf-id>` option.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |

### Version History

Introduced in Cumulus Linux 5.9.0

### Example

```
cumulus@switch:~$ nv action upgrade system packages to latest use-vrf default
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action upgrade system packages to latest use-vrf \<vrf\> dry-run</h>

Fetches the latest update metadata from the repository so you can review potential upgrade issues (in some cases, upgrading new packages might also upgrade additional existing packages due to dependencies).

By default, the NVUE `nv action upgrade system packages` command runs in the management VRF. To run the command in a non-management VRF such as `default`, you must use the `use-vrf <vrf-id>` option.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<vrf-id>` |  The VRF name.  |

### Version History

Introduced in Cumulus Linux 5.9.0

### Example

```
cumulus@switch:~$ nv action upgrade system packages to latest use-vrf default dry-run
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action upload tech-support files \<file-id\> \<remote-url\></h>

Uploads a technical support file (`cl-support`) off the switch to an external location.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<file-id>` |  The technical support file you want to upload.  |
| `<remote-url>` |  The URL to where you want to upload the technical support file.  |

### Version History

Introduced in Cumulus Linux 5.10.0

### Example

```
cumulus@switch:~$ nv action upload tech-support files cl_support_leaf01_20240725_225811.txz scp://root@host1:/home/tech-support/
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv action upload system telemetry hft job <hft-job-id> \<remote-url\></h>

Uploads high frequency telemetry data for a specific session (job) off the switch to an external location.

### Command Syntax

| Syntax   |  Description  |
| ----------    | ------------  |
| `<hft-job-id>` |  The job ID. You can see the list of jobs with the `nv show system telemetry hft job` command.  |
| `<remote-url>` |  The URL to where you want to upload the data.  |

### Version History

Introduced in Cumulus Linux 5.10.0

### Example

```
cumulus@switch:~$ nv action upload system telemetry hft job 1 scp://root@host1:/home/telemetry/
```

<HR STYLE="BORDER: DASHED RGB(118,185,0) 0.5PX;BACKGROUND-COLOR: RGB(118,185,0);HEIGHT: 4.0PX;"/>

## <h>nv show action</h>

Shows actions, such as cleared interface counters and routes, removed protodown MLAG bond conflicts, and disconnected system users.

### Version History

Introduced in Cumulus Linux 5.4.0

### Example

```
cumulus@switch:~$ nv show action
id  state         
--  --------------
1   action_success
2   action_error  
3   action_success
4   action_success 
5   action_success
6   action_success
```
