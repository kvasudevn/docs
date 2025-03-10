---
title: What's New
author: NVIDIA
weight: 5
toc: 2
---
This document supports the Cumulus Linux 5.11 release, and lists new platforms, features, and enhancements.
- For a list of open and fixed issues in Cumulus Linux 5.11, see the {{<link title="Cumulus Linux 5.11 Release Notes" text="Cumulus Linux 5.11 Release Notes">}}.
- To upgrade to Cumulus Linux 5.11, follow the steps in {{<link url="Upgrading-Cumulus-Linux">}}.
<!-- vale off -->

## What's New in Cumulus Linux 5.11

### Platforms

### New Features and Enhancements

- The NVIDIA SN5400 switch supports {{<link url="Synchronous-Ethernet-SyncE" text="syncE">}} and {{<link url="Precision-Time-Protocol-PTP/#noise-transfer-servo" text="ITU-T">}}
- {{<link url="Pulse-Per-Second-PPS" text="PPS on the NVIDIA SN5400 switch">}} is now generally available.
- {{<link url="Factory-Reset" text="Factory Reset">}}
- {{<link url="Forwarding-Table-Size-and-Profiles/#spectrum-1" text="ecmp-nh-heavy forwarding profile">}} for Spectrum 1 switches
- {{<link url="Optional-BGP-Configuration/#bgp-prefix-independent-convergence" text="BGP Prefix Independent Convergence">}}
- {{<link url="RADIUS-AAA/#radius-user-command-accounting" text="RADIUS user command accounting">}}
- {{<link url="Upgrading-Cumulus-Linux/#upgrade-cumulus-linux" text="Optimized image upgrade commands">}} (available for future upgrades)
- {{<link url="Equal-Cost-Multipath-Load-Sharing/#adaptive-routing" text="Additional adaptive routing ECMP resource optimization for next hop groups">}} (Beta)
- OTLP
- {{<link url="ASIC-Monitoring/#interface-packet-and-buffer-statistics" text="Interface packet and buffer statistics collection">}}
- NVUE
  - {{<link url="DHCP-Snooping" text="DHCP snooping commands">}}
  - {{<link url="LDAP-Authentication-and-Authorization" text="LDAP authentication and authorization commands">}}
  - {{<link url="Link-Layer-Discovery-Protocol/#disable-lldp" text="Enable and disable LLDP commands">}}
  - {{<link url="Resource-Diagnostics/#disable-lldp" text="Show ASIC resources commands">}} (`cl-resource-query` equivalent)
  - {{<link url="Monitoring-System-Statistics-and-Network-Traffic-with-sFlow" text="sFlow commands">}}
  - {{<link url="DHCP-Servers/#assign-a-port-based-ip-address" text="IPv6 command to assign a port-based DHCP server address">}}
  - {{<link url="Zero-Touch-Provisioning-ZTP/#manually-run-ztp" text="Enable ZTP and run ZTP script commands">}}
  - {{<link url="Interface-Configuration-and-Management/#port-ranges" text="Additional port range support for breakout ports and subinterfaces">}}
  - {{<link url="Interface-Configuration-and-Management/#troubleshooting" text="nv show interface <interface>">}} commands now show the date and time the operational state of an interface changes and number of carrier transitions
  - {{<link url="NVUE-CLI/#show-switch-configuration" text="nv config show --all command">}} to show applied configuration on the switch and include all default options
  - {{<link url="Services-and-Daemons-in-Cumulus-Linux/#limit-resources-for-services" text="Commands to limit resources (memory and CPU usage) for Cumulus Linux services">}}.
  - {{<link url="Optional-BGP-Configuration/#bgp-community-lists" text="Commands to configure BGP large community lists">}}
  - {{<link url="Route-Filtering-and-Redistribution/#match-source-protocol" text="Command to match BGP as the source protocol in a route map">}}
  - {{<link url="Switch-Port-Attributes/#interface-settings" text="nv show interface --view command includes additional filtering options">}}: `svi`, `vrf`, `bonds`, `bond-members`, `up`, and `down`
  - {{<link url="FRRouting/#show-routes-in-the-routing-table" text="Commands to show the number of routes in the routing table">}}
  - {{<link url="Monitoring-Interfaces-and-Transceivers-with-NVUE/#show-transceiver-information" text="Commands to show optical information for transceivers">}}
  - {{<link url="Monitoring-Interfaces-and-Transceivers-with-NVUE/#show-transceiver-information" text="l1-show command equivalent">}}
  - BGP command changes and output updates
  - EVPN command changes and output updates
  - {{< expand "Changed NVUE Commands" >}}
| New Command | Previous Command |
| ----------- | ----------------|
| nv set system snmp-server<br>nv unset system snmp-server | nv set service snmp-server<br>nv unset service snmp-server |
| nv set system snmp-server state enable<br>nv set system snmp-server state disable| nv set service snmp-server enable on<br>nv set service snmp-server enable off|
| nv show system snmp-server | nv show service snmp-server|
| nv set qos advance-buffer-config default-global ingress-service-pool <pool-id> <property> <value> | nv set qos advance-buffer-config default-global ingress-pool <pool-id> <property> <value>|
| nv set qos advance-buffer-config default-global egress-service-pool <pool-id> <property> <value> | nv set qos advance-buffer-config default-global egress-pool <pool-id> <property> <value>  |
| nv show qos advance-buffer-config default-global ingress-service-pool | nv show qos advance-buffer-config default-global ingress-pool |
| nv show qos advance-buffer-config default-global egress-service-pool | nv show qos advance-buffer-config default-global egress-pool |
{{< /expand >}}
  - {{< expand "Removed NVUE Commands" >}}
| Removed Command | 
| --------------- |
|nv show interface pluggables (replaced with nv show platform transceiver) |
|nv show interface <interface> pluggable (replaced with nv show platform transceiver <interface>)|
|nv show vrf <vrf-id> router bgp address-family l2vpn-evpn loc-rib (replaced with nv show vrf <vrf-id> router bgp adress-family l2vpn-evpn route) |
|nv show vrf <vrf-id> router bgp address-family l2vpn-evpn loc-rib rd |
|nv show vrf <vrf-id> router bgp address-family l2vpn-evpn loc-rib rd <rd-id> |
|nv show vrf <vrf-id> router bgp address-family l2vpn-evpn loc-rib rd <rd-id> route-type |
|nv show vrf <vrf-id> router bgp address-family l2vpn-evpn loc-rib rd <rd-id> route-type <route-type-id> |
|nv show vrf <vrf-id> router bgp address-family l2vpn-evpn loc-rib rd <rd-id> route-type <route-type-id> route |
|nv show vrf <vrf-id> router bgp address-family l2vpn-evpn loc-rib rd <rd-id> route-type <route-type-id> route  <evpn-route-id> |

{{< /expand >}}
  - {{< expand "New NVUE Commands" >}}
For descriptions and examples of all NVUE commands, refer to the [NVUE Command Reference]({{<ref "/nvue-reference" >}}) for Cumulus Linux.
{{< tabs "TabID108 ">}}
{{< tab "nv show ">}}

```
nv show bridge domain <domain-id> dhcp-snoop
nv show bridge domain <domain-id> dhcp-snoop vlan
nv show bridge domain <domain-id> dhcp-snoop vlan <vid>
nv show bridge domain <domain-id> dhcp-snoop vlan <vid> trust
nv show bridge domain <domain-id> dhcp-snoop vlan <vid> trust <interface-id>
nv show bridge domain <domain-id> dhcp-snoop vlan <vid> bind
nv show bridge domain <domain-id> dhcp-snoop vlan <vid> bind <interface-id>
nv show bridge domain <domain-id> dhcp-snoop6
nv show bridge domain <domain-id> dhcp-snoop6 vlan
nv show bridge domain <domain-id> dhcp-snoop6 vlan <vid>
nv show bridge domain <domain-id> dhcp-snoop6 vlan <vid> trust
nv show bridge domain <domain-id> dhcp-snoop6 vlan <vid> trust <interface-id>
nv show bridge domain <domain-id> dhcp-snoop6 vlan <vid> bind
nv show bridge domain <domain-id> dhcp-snoop6 vlan <vid> bind <interface-id>
nv show interface <interface-id> sflow
nv show interface <interface-id> transceiver 
nv show interface <interface-id> transceiver thresholds
nv show platform asic resource
nv show platform asic resource acl
nv show platform asic resource global
nv show platform transceiver
nv show platform transceiver <interface-id> 
nv show platform transceiver <interface-id> channel 
nv show platform transceiver <interface-id> channel <channel-id> 
nv show platform transceiver <detail> 
nv show platform transceiver
nv show platform transceiver brief
nv show platform transceiver detail
nv show platform transceiver <transceiver-id>
nv show platform transceiver <transceiver-id> channel
nv show platform transceiver <transceiver-id> channel <channel-id>
nv show router policy large-community-list
nv show router policy large-community-list <list-id>
nv show router policy large-community-list <list-id> rule
nv show router policy large-community-list <list-id> rule <rule-id>
nv show router policy large-community-list <list-id> rule <rule-id> large-community
nv show router policy large-community-list <list-id> rule <rule-id> large-community <large-community-id>
nv show router policy route-map <route-map-id> rule <rule-id> set large-community
nv show router policy route-map <route-map-id> rule <rule-id> set large-community <large-community-id>
nv show service control
nv show service control <service-name-id>
nv show service control <service-name-id> resource-limit
nv show system sflow
nv show system sflow collector
nv show system sflow collector <collector-ip>
nv show system sflow sampling-rate
nv show system sflow agent
nv show system sflow policer
nv show system sflow dropmon
nv show system sflow dropmon <drop-type>
nv show system telemetry interface-stats
nv show system telemetry interface-stats port-group
nv show system telemetry interface-stats port-group <port-group-id>
nv show system telemetry interface-stats port-group <port-group-id> snapshot-file
nv show system telemetry interface-stats port-group <port-group-id> threshold
nv show system telemetry interface-stats port-group <port-group-id> threshold <threshold-stats-id>
nv show system telemetry interface-stats port-group <port-group-id> threshold <threshold-stats-id> action
nv show system telemetry interface-stats port-group <port-group-id> threshold <threshold-stats-id> action log
nv show system telemetry interface-stats port-group <port-group-id> threshold <threshold-stats-id> action collect
nv show system telemetry interface-stats port-group <port-group-id> stats-type
nv show system telemetry interface-stats port-group <port-group-id> snapshot
nv show system telemetry interface-stats port-group <port-group-id> snapshot buffer
nv show system telemetry interface-stats port-group <port-group-id> snapshot buffer pool
nv show system telemetry interface-stats port-group <port-group-id> snapshot buffer pool <buffer-pool-id>
nv show system telemetry interface-stats port-group <port-group-id> snapshot interface
nv show system telemetry interface-stats port-group <port-group-id> snapshot interface <intf-id>
nv show system telemetry interface-stats port-group <port-group-id> snapshot interface <intf-id> packet
nv show system telemetry interface-stats port-group <port-group-id> snapshot interface <intf-id> packet good
nv show system telemetry interface-stats port-group <port-group-id> snapshot interface <intf-id> packet good tx
nv show system telemetry interface-stats port-group <port-group-id> snapshot interface <intf-id> packet good rx
nv show system telemetry interface-stats port-group <port-group-id> snapshot interface <intf-id> packet discard
nv show system telemetry interface-stats port-group <port-group-id> snapshot interface <intf-id> packet discard tx
nv show system telemetry interface-stats port-group <port-group-id> snapshot interface <intf-id> packet discard rx
nv show system telemetry interface-stats port-group <port-group-id> snapshot interface <intf-id> packet discard general
nv show system telemetry interface-stats port-group <port-group-id> snapshot interface <intf-id> packet all
nv show system telemetry interface-stats port-group <port-group-id> snapshot interface <intf-id> packet all tx
nv show system telemetry interface-stats port-group <port-group-id> snapshot interface <intf-id> packet all rx
nv show system telemetry interface-stats port-group <port-group-id> snapshot interface <intf-id> packet tc
nv show system telemetry interface-stats port-group <port-group-id> snapshot interface <intf-id> packet tc <tc-id>
nv show system telemetry interface-stats port-group <port-group-id> snapshot interface <intf-id> packet tc <tc-id> tx
nv show system telemetry interface-stats port-group <port-group-id> snapshot interface <intf-id> packet pg
nv show system telemetry interface-stats port-group <port-group-id> snapshot interface <intf-id> packet pg <pg-id>
nv show system telemetry interface-stats port-group <port-group-id> snapshot interface <intf-id> packet pg <pg-id> tx
nv show system telemetry interface-stats port-group <port-group-id> snapshot interface <intf-id> packet pg <pg-id> rx
nv show system telemetry interface-stats port-group <port-group-id> snapshot interface <intf-id> buffer
nv show system telemetry interface-stats port-group <port-group-id> snapshot interface <intf-id> buffer tc
nv show system telemetry interface-stats port-group <port-group-id> snapshot interface <intf-id> buffer tc <tc-id>
nv show system telemetry interface-stats port-group <port-group-id> snapshot interface <intf-id> buffer pg
nv show system telemetry interface-stats port-group <port-group-id> snapshot interface <intf-id> buffer pg <pg-id>
nv show system telemetry interface-stats port-group <port-group-id> snapshot interface <intf-id> buffer ingress-port
nv show system telemetry interface-stats port-group <port-group-id> snapshot interface <intf-id> buffer ingress-port <buffer-pool-id>
nv show system telemetry interface-stats export
nv show system telemetry interface-stats switch-priority
nv show system telemetry interface-stats switch-priority <pg-id>
nv show system telemetry interface-stats ingress-buffer
nv show system telemetry interface-stats ingress-buffer priority-group
nv show system telemetry interface-stats ingress-buffer priority-group <pg-id>
nv show system telemetry interface-stats egress-buffer
nv show system telemetry interface-stats egress-buffer traffic-class
nv show system telemetry interface-stats egress-buffer traffic-class <tc-id>
nv show system ztp
nv show system ztp script
nv show vrf <vrf-id> router bgp address-family ipv4-unicast route <route-id> path <path-id> large-community
nv show vrf <vrf-id> router bgp address-family ipv6-unicast route <route-id> path <path-id> large-community
nv show vrf <vrf-id> router bgp neighbor <neighbor-id> address-family ipv4-unicast advertised-routes <route-id> path <path-id> large-community
nv show vrf <vrf-id> router bgp neighbor <neighbor-id> address-family ipv4-unicast received-routes <route-id> path <path-id> large-community
nv show vrf <vrf-id> router bgp neighbor <neighbor-id> address-family ipv6-unicast received-routes <route-id> path <path-id> large-community
nv show vrf <vrf-id> router bgp neighbor <neighbor-id> address-family ipv6-unicast advertised-routes <route-id> path <path-id> large-community
nv show vrf <vrf> router rib <address-family> route-count
nv show vrf <vrf> router rib <address-family> route-count <prefix>
nv show vrf <vrf> router rib <address-family> route-count protocol
```

{{< /tab >}}
{{< tab "nv set ">}}

```
nv set bridge domain <domain-id> dhcp-snoop vlan <vid>
nv set bridge domain <domain-id> dhcp-snoop vlan <vid> trust <interface-id>
nv set bridge domain <domain-id> dhcp-snoop6 vlan <vid>
nv set bridge domain <domain-id> dhcp-snoop6 vlan <vid> trust <interface-id>
nv set interface <interface-id> lldp state
nv set interface <interface-id> sflow state
nv set interface <interface-id> sflow sample-rate <rate>
nv set router policy large-community-list <list-id>
nv set router policy large-community-list <list-id> rule <rule-id>
nv set router policy large-community-list <list-id> rule <rule-id> large-community <large-community-id>
nv set router policy large-community-list <list-id> rule <rule-id> action
nv set router policy route-map <route-map-id> rule <rule-id> match large-community-list
nv set router policy route-map <route-map-id> rule <rule-id> set large-community <large-community-id>
nv set router policy route-map <route-map-id> rule <rule-id> set large-community-delete-list 
nv set service dhcp-server6 default static <server-id>
nv set service dhcp-server6 default static <server-id> ip-address <ip-address>
nv set service dhcp-server6 default static <server-id> ifname <interface-id>
nv set service control <service-name-id>
nv set service control <service-name-id> resource-limit memory <size>
nv set service control <service-name-id> resource-limit cpu (percent)
nv set service lldp state
nv set system aaa radius accounting
nv set system sflow collector <collector-ip>
nv set system sflow collector <collector-ip> port
nv set system sflow collector <collector-ip> interface <interface-name>
nv set system sflow sampling-rate default
nv set system sflow sampling-rate speed-100m
nv set system sflow sampling-rate speed-1g
nv set system sflow sampling-rate speed-10g
nv set system sflow sampling-rate speed-25g
nv set system sflow sampling-rate speed-40g
nv set system sflow sampling-rate speed-50g
nv set system sflow sampling-rate speed-100g
nv set system sflow sampling-rate speed-200g
nv set system sflow sampling-rate speed-400g
nv set system sflow sampling-rate speed-800g
nv set system sflow agent ip <ipv4-prefix>
nv set system sflow agent interface <interface-name>
nv set system sflow policer rate
nv set system sflow policer burst
nv set system sflow dropmon <drop-type>
nv set system sflow poll-interval
nv set system sflow state
nv set system telemetry interface-stats port-group <port-group-id>
nv set system telemetry interface-stats port-group <port-group-id> snapshot-file name <value>
nv set system telemetry interface-stats port-group <port-group-id> snapshot-file count
nv set system telemetry interface-stats port-group <port-group-id> threshold <threshold-stats-id>
nv set system telemetry interface-stats port-group <port-group-id> threshold <threshold-stats-id> action log
nv set system telemetry interface-stats port-group <port-group-id> threshold <threshold-stats-id> action collect port-group <value>
nv set system telemetry interface-stats port-group <port-group-id> threshold <threshold-stats-id> value
nv set system telemetry interface-stats port-group <port-group-id> stats-type
nv set system telemetry interface-stats port-group <port-group-id> interface <value>
nv set system telemetry interface-stats port-group <port-group-id> timer-interval
nv set system telemetry interface-stats export state (enabled|disabled)
nv set system telemetry interface-stats switch-priority <pg-id>
nv set system telemetry interface-stats ingress-buffer priority-group <pg-id>
nv set system telemetry interface-stats egress-buffer traffic-class <tc-id>
nv set system telemetry interface-stats sample-interval
```

{{< /tab >}}
{{< tab "nv unset ">}}

```
nv unset bridge domain <domain-id> dhcp-snoop
nv unset bridge domain <domain-id> dhcp-snoop vlan
nv unset bridge domain <domain-id> dhcp-snoop vlan <vid>
nv unset bridge domain <domain-id> dhcp-snoop vlan <vid> trust
nv unset bridge domain <domain-id> dhcp-snoop vlan <vid> trust <interface-id>
nv unset bridge domain <domain-id> dhcp-snoop6
nv unset bridge domain <domain-id> dhcp-snoop6 vlan
nv unset bridge domain <domain-id> dhcp-snoop6 vlan <vid>
nv unset bridge domain <domain-id> dhcp-snoop6 vlan <vid> trust
nv unset bridge domain <domain-id> dhcp-snoop6 vlan <vid> trust <interface-id>
nv unset interface <interface-id> lldp state
nv unset interface <interface-id> sflow sample-rate
nv unset router policy large-community-list
nv unset router policy large-community-list <list-id>
nv unset router policy large-community-list <list-id> rule
nv unset router policy large-community-list <list-id> rule <rule-id>
nv unset router policy large-community-list <list-id> rule <rule-id> large-community
nv unset router policy large-community-list <list-id> rule <rule-id> large-community <large-community-id>
nv unset router policy large-community-list <list-id> rule <rule-id> action
nv unset router policy route-map <route-map-id> rule <rule-id> match large-community-list
nv unset router policy route-map <route-map-id> rule <rule-id> set large-community
nv unset router policy route-map <route-map-id> rule <rule-id> set large-community <large-community-id>
nv unset router policy route-map <route-map-id> rule <rule-id> set large-community-delete-list
nv unset service dhcp-server6 default static <server-id>
nv unset service dhcp-server6 default static <server-id> ip-address <ip-address>
nv unset service dhcp-server6 default static <server-id> ifname <interface-id>
nv unset service lldp state
nv unset system aaa radius accounting
nv unset system sflow
nv unset system sflow collector
nv unset system sflow collector <collector-ip>
nv unset system sflow collector <collector-ip> port
nv unset system sflow collector <collector-ip> interface
nv unset system sflow sampling-rate
nv unset system sflow sampling-rate default
nv unset system sflow sampling-rate speed-100m
nv unset system sflow sampling-rate speed-1g
nv unset system sflow sampling-rate speed-10g
nv unset system sflow sampling-rate speed-25g
nv unset system sflow sampling-rate speed-40g
nv unset system sflow sampling-rate speed-50g
nv unset system sflow sampling-rate speed-100g
nv unset system sflow sampling-rate speed-200g
nv unset system sflow sampling-rate speed-400g
nv unset system sflow sampling-rate speed-800g
nv unset system sflow agent
nv unset system sflow agent ip
nv unset system sflow agent interface
nv unset system sflow policer
nv unset system sflow policer rate
nv unset system sflow policer burst
nv unset system sflow dropmon
nv unset system sflow dropmon <drop-type>
nv unset system sflow poll-interval
nv unset system sflow state
nv unset system telemetry interface-stats
nv unset system telemetry interface-stats port-group
nv unset system telemetry interface-stats port-group <port-group-id>
nv unset system telemetry interface-stats port-group <port-group-id> snapshot-file
nv unset system telemetry interface-stats port-group <port-group-id> snapshot-file name
nv unset system telemetry interface-stats port-group <port-group-id> snapshot-file count
nv unset system telemetry interface-stats port-group <port-group-id> threshold
nv unset system telemetry interface-stats port-group <port-group-id> threshold <threshold-stats-id>
nv unset system telemetry interface-stats port-group <port-group-id> threshold <threshold-stats-id> action
nv unset system telemetry interface-stats port-group <port-group-id> threshold <threshold-stats-id> action log
nv unset system telemetry interface-stats port-group <port-group-id> threshold <threshold-stats-id> action collect
nv unset system telemetry interface-stats port-group <port-group-id> threshold <threshold-stats-id> action collect port-group
nv unset system telemetry interface-stats port-group <port-group-id> threshold <threshold-stats-id> value
nv unset system telemetry interface-stats port-group <port-group-id> stats-type
nv unset system telemetry interface-stats port-group <port-group-id> interface
nv unset system telemetry interface-stats port-group <port-group-id> timer-interval
nv unset system telemetry interface-stats export
nv unset system telemetry interface-stats export state
nv unset system telemetry interface-stats switch-priority
nv unset system telemetry interface-stats switch-priority <if-pg-id>
nv unset system telemetry interface-stats ingress-buffer
nv unset system telemetry interface-stats ingress-buffer priority-group
nv unset system telemetry interface-stats ingress-buffer priority-group <if-pg-id>
nv unset system telemetry interface-stats egress-buffer
nv unset system telemetry interface-stats egress-buffer traffic-class
nv unset system telemetry interface-stats egress-buffer traffic-class <if-tc-id>
nv unset system telemetry interface-stats sample-interval
```

{{< /tab >}}
{{< tab "nv action ">}}

```
nv action reset system factory-reset
nv action reset system factory-reset keep basic
nv action reset system factory-reset keep all-config
nv action reset system factory-reset keep all-files
nv action enable system ztp
nv action disable system ztp
nv action run system ztp
nv action abort system ztp
```

{{< /tab >}}
{{< /tabs >}}
{{< /expand >}}

{{%notice warning%}}
To align with a long-term vision of a common interface between Cumulus Linux, Nvidia OS (NVOS), and Host-Based Networking, certain NVUE commands in Cumulus Linux 5.11 have changed. Before you upgrade to 5.11, review the list of changed NVUE commands above and be sure to make any necessary changes to your automation.
{{%/notice%}}

## Release Considerations

Review the following considerations before you upgrade to Cumulus Linux 5.11.

### DHCP Lease with the host-name Option

When a Cumulus Linux switch with NVUE enabled receives a DHCP lease containing the host-name option, it ignores the received hostname and does not apply it. For details, see this [knowledge base article]({{<ref "/knowledge-base/Configuration-and-Usage/Administration/Hostname-Option-Received-From-DHCP-Ignored" >}}).

### NVUE Commands After Upgrade

Cumulus Linux 5.11 includes the NVUE object model. After you upgrade to Cumulus Linux 5.11, running NVUE configuration commands might override configuration for features that are now configurable with NVUE and removes configuration you added manually to files or with automation tools like Ansible, Chef, or Puppet. To keep your configuration, you can do one of the following:
- Update your automation tools to use NVUE.
- {{<link url="NVUE-CLI/#configure-nvue-to-ignore-linux-files" text="Configure NVUE to ignore certain underlying Linux files">}} when applying configuration changes.
- Use Linux and FRR (vtysh) commands instead of NVUE for **all** switch configuration.
