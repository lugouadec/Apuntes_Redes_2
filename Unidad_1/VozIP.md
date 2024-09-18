# Configuracion de VozIP utilizando un router 2811

Configuracion de las interfaces
```
Router(config)#int f0/0.10
Router(config-subif)#en do 10
Router(config-subif)#ip add 192.168.10.254 255.255.255.0
Router(config-subif)#no shut
Router(config-subif)#int f0/0.20
Router(config-subif)#en do 20
Router(config-subif)#ip add 192.168.20.254 255.255.255.0
Router(config-subif)#no shut
Router(config-subif)#exit
Router(config)#int f0/0
Router(config-if)#no shut
```

Configuracion de los dhcp
```
Router(config)#ip dhcp pool voz
Router(dhcp-config)#net 192.168.20.0 255.255.255.0
Router(dhcp-config)#defa 192.168.20.254
Router(dhcp-config)#option 150 ip 192.168.20.254
Router(dhcp-config)#exit
Router(config)#ip dhcp pool datos
Router(dhcp-config)#net 192.168.10.0 255.255.255.0
Router(dhcp-config)#defa 192.168.10.254
Router(dhcp-config)#exit
```
Modo de configuración de servicio de telefonía.
```
Router(config)#telephony-service
#especificar el número máximo de números de directorio (DN,Directory Numbers) que se pueden configurar en el sistema.
Router(config-telephony)#max-dn 20
```
Establece el número máximo de teléfonos IP (ephones) que se pueden registrar en el sistema a 10

    Router(config-telephony)#max-ephones 10
    
Define la dirección IP y el puerto utilizado por el servicio de telefonía.

    Router(config-telephony)#ip source-address 192.168.20.254 port 2000

Asigna automáticamente números de directorio en el rango de 1 a 20 a los teléfonos IP que se registren.

    Router(config-telephony)#auto assign 1 to 20

Asignacion de numeros 
```
Router(config)#ephone-dn 1
Router(config-ephone-dn)#number 101

Router(config)#ephone-dn 1
Router(config-ephone-dn)#number 102

Router(config)#ephone-dn 1
Router(config-ephone-dn)#number 103
```
Si necesitas asignar específicamente ciertos números de directorio a ciertos teléfonos IP, puedes usar el comando assign. Pero en este caso, si solo estás usando auto assign, el sistema manejará la asignación automáticamente:
```
ephone 1
 mac-address 0011.2233.4455
 type 7960
 button 1:1

ephone 2
 mac-address 0011.2233.4456
 type 7960
 button 1:2
```
