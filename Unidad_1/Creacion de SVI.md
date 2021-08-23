1.- Ingrese al modo de configuración global.

    S1# configure terminal

2.- Ingrese al modo de configuración de interfaz para la SVI.

    S1(config)# interface vlan 99

3.- Configure la dirección IPv4 de la interfaz de administración.

    S1(config-if)# ip address 172.17.99.11 255.255.255.0

4.- Habilite la interfaz de administración.

    S1(config-if)# no shutdown


5.- Vuelva al modo EXEC privilegiado.

    S1(config-if)# end

6.- Guarde la configuración en ejecución en la configuración de inicio.

    S1# copy running-config startup-config
