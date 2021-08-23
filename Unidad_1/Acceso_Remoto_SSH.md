# Acceso Remoto de Administracion al Switch / Router Cisco

    1.- Comprobar caracteristicas de encriptacion IOS: #show version
    2.- Asignar un dominio: (config)#ip domain-name esistemas.edu
    3.- Asignar Nombre al Switch: (config)#hostname nombre
    4.- Generar Llaves RSA de cuando menos 1024 bits: (config)#Crypto key generate RSA 1024
    5.- Crear usuarios y su contraseña (config)# username usuario [privileges 1..15] secret contraseña
    6.- Activar la entrada por las terminales virtuales: (config)# line vty 0 15 
    7.- Redirige las conecciones al protocolo SSH (config-line)# transport input ssh
    8.- Activa el Sistema de Usuarios del IOS: (config-line)# login local
    9.- activar la version de SSH: (config)#ip ssh version 2
    10.- Revisar Estado del Servicio de SSH: # show ip ssh
    
