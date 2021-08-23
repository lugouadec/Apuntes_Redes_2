# Proteger con contraseña el Acceso por Consola

    # enable
    # configure terminal 
    # line console 0
    # password contraseña
    # login
    # exit
    # service password-encryption

# Establecer mensaje de Entrada por Consola 

    # enable
    # configure terminal
    (config)# banner motd $ Acceso Solo a Personal Autorizado $
    (config)# exit
    # copy running-config startup-config
