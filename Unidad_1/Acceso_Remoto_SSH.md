# Acceso Remoto de Administracion al Switch / Router Cisco

    1.- Comprobar SSH: #show ip ssh
    2.- Asignar un dominio: (config)#ip domain-name esistemas.edu
    3.- Asignar Nombre al Switch: (config)#hostname nombre
    4.- Generar Llaves RSA de cuando menos 1024 bits: (config)#Crypto key generate RSA 1024
    5.- Crear usuarios y su contraseña (config)# username usuario [privileges 1..15] secret contraseña
    6.- Activar la entrada por las terminales virtuales: (config)# line vty 0 15 //entrar a la consola de configuracion de las VTY's
	(config-line)# transport input ssh //trasporta la entra al protocolo SSH
	(config-line)# login local  //Activa el sistema de usuarios IOS
    7.- activar la version de SSH: (config)#ip ssh version 2