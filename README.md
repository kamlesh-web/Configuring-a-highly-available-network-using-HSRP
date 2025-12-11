    Switch>
    Switch>enable
    Switch#
    Switch#show ip interface brief
    Interface              IP-Address      OK? Method Status                Protocol 
    FastEthernet0/1        unassigned      YES NVRAM  down                  down 
    FastEthernet0/2        unassigned      YES NVRAM  up                    up 
    FastEthernet0/3        unassigned      YES NVRAM  down                  down 
    FastEthernet0/4        unassigned      YES NVRAM  up                    up 
    FastEthernet0/5        unassigned      YES NVRAM  down                  down 
    FastEthernet0/6        unassigned      YES NVRAM  up                    up 
    FastEthernet0/7        unassigned      YES NVRAM  down                  down 
    FastEthernet0/8        unassigned      YES NVRAM  down                  down 
    FastEthernet0/9        unassigned      YES NVRAM  down                  down 
    FastEthernet0/10       unassigned      YES NVRAM  down                  down 
    FastEthernet0/11       unassigned      YES NVRAM  down                  down 
    FastEthernet0/12       unassigned      YES NVRAM  down                  down 
    FastEthernet0/13       unassigned      YES NVRAM  down                  down 
    FastEthernet0/14       unassigned      YES NVRAM  down                  down 
    FastEthernet0/15       unassigned      YES NVRAM  down                  down 
    FastEthernet0/16       unassigned      YES NVRAM  down                  down 
    FastEthernet0/17       unassigned      YES NVRAM  down                  down 
    FastEthernet0/18       unassigned      YES NVRAM  down                  down 
    FastEthernet0/19       unassigned      YES NVRAM  down                  down 
    FastEthernet0/20       unassigned      YES NVRAM  down                  down 
    FastEthernet0/21       unassigned      YES NVRAM  down                  down 
    FastEthernet0/22       unassigned      YES NVRAM  down                  down 
    FastEthernet0/23       unassigned      YES NVRAM  down                  down 
    FastEthernet0/24       unassigned      YES NVRAM  down                  down 
    GigabitEthernet0/1     unassigned      YES NVRAM  up                    up 
    GigabitEthernet0/2     unassigned      YES NVRAM  down                  down 
    Vlan1                  unassigned      YES unset  administratively down down
    Switch#
    Switch(config)#hostname DLSW2
    DLSW2(config)#
    DLSW2(config)#enable secret CCNA
    DLSW2(config)#
    DLSW2(config)#ip routing
    DLSW2(config)#
    DLSW2(config)#interface g0/2
    DLSW2(config-if)#
    DLSW2(config-if)#no switchport
    DLSW2(config-if)#
    DLSW2(config-if)#ip address 192.168.1.70 255.255.255.252
    DLSW2(config-if)#
    DLSW2(config-if)#no shut
    
    DLSW2(config-if)#
    %LINK-5-CHANGED: Interface GigabitEthernet0/2, changed state to up
    
    %LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/2, changed state to up
    DLSW2(config-if)#
    DLSW2(config-if)#exit
    DLSW2(config)#
    DLSW2(config)#ip route 0.0.0.0 0.0.0.0 192.168.1.69
    DLSW2(config)#
    DLSW2(config)#spanning-tree mode rapid-pvst
    DLSW2(config)#
    DLSW2(config)#vlan 10
    DLSW2(config-vlan)#
    DLSW2(config-vlan)#name IT
    DLSW2(config-vlan)#
    DLSW2(config-vlan)#vlan 20
    DLSW2(config-vlan)#
    DLSW2(config-vlan)#name FINANCE
    DLSW2(config-vlan)#
    DLSW2(config-vlan)#vlan 30
    DLSW2(config-vlan)#
    DLSW2(config-vlan)#name HR
    DLSW2(config-vlan)#
    DLSW2(config-vlan)#vlan 40
    DLSW2(config-vlan)#
    DLSW2(config-vlan)#name SALES
    DLSW2(config-vlan)#
    DLSW2(config-vlan)#exit
    DLSW2(config)#
    DLSW2(config)#interface vlan 10
    DLSW2(config-if)#
    %LINK-5-CHANGED: Interface Vlan10, changed state to up
    
    %LINEPROTO-5-UPDOWN: Line protocol on Interface Vlan10, changed state to up
    
    DLSW2(config-if)#ip address 192.168.1.12 255.255.255.240
    DLSW2(config-if)#
    DLSW2(config-if)#standby version 2
    DLSW2(config-if)#
    DLSW2(config-if)#standby 10 ip 192.168.1.14
    DLSW2(config-if)#
    %HSRP-6-STATECHANGE: Vlan10 Grp 10 state Init -> Init
    
    %HSRP-6-STATECHANGE: Vlan10 Grp 10 state Speak -> Standby
    
    DLSW2(config-if)#interface vlan 20
    DLSW2(config-if)#
    %LINK-5-CHANGED: Interface Vlan20, changed state to up
    
    %LINEPROTO-5-UPDOWN: Line protocol on Interface Vlan20, changed state to up
    
    DLSW2(config-if)#ip address 192.168.1.28 255.255.255.240
    DLSW2(config-if)#
    DLSW2(config-if)#standby version 2
    DLSW2(config-if)#
    DLSW2(config-if)#standby 20 ip 192.168.1.30
    DLSW2(config-if)#
    %HSRP-6-STATECHANGE: Vlan20 Grp 20 state Init -> Init
    
    %HSRP-6-STATECHANGE: Vlan20 Grp 20 state Speak -> Standby
    
    DLSW2(config-if)#interface vlan 30
    DLSW2(config-if)#
    %LINK-5-CHANGED: Interface Vlan30, changed state to up
    
    %LINEPROTO-5-UPDOWN: Line protocol on Interface Vlan30, changed state to up
    
    DLSW2(config-if)#ip address 192.168.1.44 255.255.255.240
    DLSW2(config-if)#
    DLSW2(config-if)#standby version 2
    DLSW2(config-if)#
    DLSW2(config-if)#standby 30 ip 192.168.1.46
    DLSW2(config-if)#
    %HSRP-6-STATECHANGE: Vlan30 Grp 30 state Init -> Init
    
    %HSRP-6-STATECHANGE: Vlan30 Grp 30 state Speak -> Standby
    
    DLSW2(config-if)#standby 30 priority 200
    DLSW2(config-if)#
    DLSW2(config-if)#standby 30 preempt
    DLSW2(config-if)#
     %HSRP-6-STATECHANGE: Vlan30 Grp 30 state Standby -> Active
    
    DLSW2(config-if)#interface vlan 40
    DLSW2(config-if)#
    %LINK-5-CHANGED: Interface Vlan40, changed state to up
    
    %LINEPROTO-5-UPDOWN: Line protocol on Interface Vlan40, changed state to up
    
    DLSW2(config-if)#ip address 192.168.1.60 255.255.255.240
    DLSW2(config-if)#
    DLSW2(config-if)#standby version 2
    DLSW2(config-if)#
    DLSW2(config-if)#standby 40 ip 192.168.1.62
    DLSW2(config-if)#
    %HSRP-6-STATECHANGE: Vlan40 Grp 40 state Init -> Init
    
    %HSRP-6-STATECHANGE: Vlan40 Grp 40 state Speak -> Standby
    
    DLSW2(config-if)#standby 40 priority 200
    DLSW2(config-if)#
    DLSW2(config-if)#standby 40 preempt
    DLSW2(config-if)#
     %HSRP-6-STATECHANGE: Vlan40 Grp 40 state Standby -> Active
     
    DLSW2(config-if)#exit
    DLSW2(config)#
    DLSW2(config)#interface range f0/1-4,f0/8-24,g0/1-2
    DLSW2(config-if-range)#
    DLSW2(config-if-range)#description ## Not in use ##
    DLSW2(config-if-range)#
    DLSW2(config-if-range)#shutdown
    
    %LINK-5-CHANGED: Interface FastEthernet0/1, changed state to administratively down
    
    (trancated...)
    
    %LINK-5-CHANGED: Interface GigabitEthernet0/2, changed state to administratively down
    
    DLSW2(config-if-range)#
    DLSW2(config-if-range)#interface range f0/2,f0/4,g0/1
    DLSW2(config-if-range)#
    DLSW2(config-if-range)#no shutdown
    DLSW2(config-if-range)#
    %LINK-5-CHANGED: Interface FastEthernet0/2, changed state to up
    
    %LINEPROTO-5-UPDOWN: Line protocol on Interface FastEthernet0/2, changed state to up
    
    %LINK-5-CHANGED: Interface FastEthernet0/4, changed state to up
    
    %LINEPROTO-5-UPDOWN: Line protocol on Interface FastEthernet0/4, changed state to up
    
    %LINK-5-CHANGED: Interface GigabitEthernet0/1, changed state to up
    
    %LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/1, changed state to up
    
    DLSW2(config-if-range)#
    DLSW2(config-if-range)#end
    DLSW2#
    %SYS-5-CONFIG_I: Configured from console by console
    
    DLSW2#
    DLSW2#show ip int brief
    Interface              IP-Address      OK? Method Status                Protocol 
    FastEthernet0/1        unassigned      YES NVRAM  administratively down down 
    FastEthernet0/2        unassigned      YES NVRAM  up                    up 
    FastEthernet0/3        unassigned      YES NVRAM  administratively down down 
    FastEthernet0/4        unassigned      YES NVRAM  up                    up 
    FastEthernet0/5        unassigned      YES NVRAM  administratively down down 
    FastEthernet0/6        unassigned      YES NVRAM  up                    up 
    FastEthernet0/7        unassigned      YES NVRAM  administratively down down 
    FastEthernet0/8        unassigned      YES NVRAM  administratively down down 
    FastEthernet0/9        unassigned      YES NVRAM  administratively down down 
    FastEthernet0/10       unassigned      YES NVRAM  administratively down down 
    FastEthernet0/11       unassigned      YES NVRAM  administratively down down 
    FastEthernet0/12       unassigned      YES NVRAM  administratively down down 
    FastEthernet0/13       unassigned      YES NVRAM  administratively down down 
    FastEthernet0/14       unassigned      YES NVRAM  administratively down down 
    FastEthernet0/15       unassigned      YES NVRAM  administratively down down 
    FastEthernet0/16       unassigned      YES NVRAM  administratively down down 
    FastEthernet0/17       unassigned      YES NVRAM  administratively down down 
    FastEthernet0/18       unassigned      YES NVRAM  administratively down down 
    FastEthernet0/19       unassigned      YES NVRAM  administratively down down 
    FastEthernet0/20       unassigned      YES NVRAM  administratively down down 
    FastEthernet0/21       unassigned      YES NVRAM  administratively down down 
    FastEthernet0/22       unassigned      YES NVRAM  administratively down down 
    FastEthernet0/23       unassigned      YES NVRAM  administratively down down 
    FastEthernet0/24       unassigned      YES NVRAM  administratively down down 
    GigabitEthernet0/1     unassigned      YES NVRAM  up                    up 
    GigabitEthernet0/2     192.168.1.70    YES manual up                    up  
    Vlan1                  unassigned      YES unset  administratively down down 
    Vlan10                 192.168.1.12    YES manual up                    up 
    Vlan20                 192.168.1.28    YES manual up                    up 
    Vlan30                 192.168.1.44    YES manual up                    up 
    Vlan40                 192.168.1.60    YES manual up                    up
    DLSW2#
    DLSW2#show standby brief
                         P indicates configured to preempt.
                         |
    Interface   Grp  Pri P State    Active          Standby         Virtual IP
    Vl10        10   100   Standby  192.168.1.13    local           192.168.1.14   
    Vl20        20   100   Standby  192.168.1.29    local           192.168.1.30   
    Vl30        30   200 P Active   local           192.168.1.45    192.168.1.46   
    Vl40        40   200 P Active   local           192.168.1.61    192.168.1.62   
    DLSW2#
    DLSW2#
    DLSW2#show interface trunk
    Port        Mode         Encapsulation  Status        Native vlan
    Fa0/2       auto         n-802.1q       trunking      1
    Fa0/4       auto         n-802.1q       trunking      1
    Fa0/6       auto         n-802.1q       trunking      1
    Gig0/1      auto         n-802.1q       trunking      1
    
    Port        Vlans allowed on trunk
    Fa0/2       1-1005
    Fa0/4       1-1005
    Fa0/6       1-1005
    Gig0/1      1-1005
    
    Port        Vlans allowed and active in management domain
    Fa0/2       1,10,20,30,40
    Fa0/4       1,10,20,30,40
    Fa0/6       1,10,20,30,40
    Gig0/1      1,10,20,30,40
    
    Port        Vlans in spanning tree forwarding state and not pruned
    Fa0/2       10,20
    Fa0/4       10,40
    Fa0/6       1,10,20,30,40
    Gig0/1      1,10,20,30,40
    
    DLSW2#
    DLSW2#write
    Building configuration...
    [OK]
    DLSW2#
