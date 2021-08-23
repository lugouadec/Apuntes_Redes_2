# Acceso Administrativo via Telnet 

## [1.- Crear y habilitar la Interface Virtual del Switch (SVI)](/Unidad_1/Creacion%20de%20SVI.md)

## 2.- Establecer la contraseña del modo Privilegiado

    (config)# enable secret contraseña

## 3.- Configurar las lineas **VTY** del  0 a la 5 

    (config)# line vty 0 5 

## 4.- Asignar una contraseña, para el acceso via Telnet

    (config-line)# password contraseña

## 5.- Activar la peticion de contraseña al acceso via Telnet

    (config-line)# login 

## 6.- Salir de al modo privilegiado

    (config-line)# end

## 7.- Guarda la Configuracion

    # copy running-config startup-config

