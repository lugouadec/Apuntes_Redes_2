# Ejemplo Acceso Remoto de Administracion al Switch / Router Cisco
    enable
    show version
    configure terminal
    ip domain-name esistemas.edu
    hostname swTorreon
    Crypto key generate RSA 
    // Generar llave de 1024 bits
    username usuario secret cisco
    username admin privilege 15 sercret cisco
    line vty 0 15 
    transport input ssh
    login local
    exit
    ip ssh version 2
    end
    show ip ssh
