## Configuracion SLAAC
	
	en 
	conf t
	ipv6 unicast-routing
	int g0/0
	ipv6 address 2001:db8:cafe::1/64
	ipv6 address FE80::1 link-local´
	no shutdown
	end

### Configuracion Cliente Router Cisco
	enable
	conf t
	ipv6 unicast-routing
	int g0/0
	ipv6 enable
	ipv6 address autoconfig
	no shut
	end

## Configuracion DHCPv6 Sin Estado
	enable 
	conf t
	ipv6 unicast-routing
	ipv6 dhcp pool IPV6-STATELESS
	dns-server 2001:db8:cafe:aaaa::5
	domain-name sistemas.lan
	exit
	interface g0/0
	ipv6 address 2001:db8:cafe:1::1/64
	ipv6 address FE80::1 link-local
	ipv6 dhcp server IPV6-STATELESS
	ipv6 nd other-config-flag
	no shutdown
	end

### Configuracion Cliente Router Cisco
	enable
	conf t
	ipv6 unicast-routing
	int g0/0
	ipv6 enable
	ipv6 address autoconfig
	no shut
	end

## Configuracion DHCPv6 Con Estado 
	enable
	conf t
	ipv6 unicast-routing
	ipv6 dhcp pool IPV6-STATEFUL
	address prefix 2001:DB8:CAFE:1::/64 lifetime 429496729 4294967295
	dns-server 2001:db8:cafe:aaaa::5
	domain-name sistemas.lan
	exit
	interface g0/0
	ipv6 address FE80::1 link-local
	ipv6 address 2001:db8:cafe:1::1/64
	ipv6 dhcp server IPV6-STATEFUL
	ipv6 nd managed-config-flag
	no shutdown
	end

### Configuracion del Router Cisco como cliente DHCPv6 con Estado
	enable
	conf t
	ipv6 unicast-routing
	int g0/0
	ipv6 enable
	ipv6 address dhcp
	no shut
	end


--------------------
	en
	conf t
	ipv6 dhcp pool STATEFUL_POOL
	domain-name adminkim.com
	dns-server 2000::10
	prefix-delegation pool STATEFUL_POOL
	exit
	ipv6 local pool STATEFUL_POOL 2000::/64   64
	int g0/0
	ipv6 address FE80::1 link-local
	ipv6 address 2001:db8:cafe:1::1/64
	ipv6 dhcp server STATEFUL_POOL
	ipv6 nd managed-config-flag
	no shut

--------------------
	en
	conf t
	ipv6 dhcp pool STATEFUL_POOL
	domain-name adminkim.com
	dns-server 2000::10
	prefix-delegation pool STATEFUL_POOL
	exit
	ipv6 local pool STATEFUL_POOL 2000::/64   64
	int g0/0
	ipv6 address FE80::1 link-local
	ipv6 address 2001:db8:cafe:1::1/64
	ipv6 dhcp server STATEFUL_POOL
	ipv6 nd managed-config-flag
	no shut
