- [ ] **Paso 1.-** Entrar en modo de configuración Global
      

      router>enable
      router#configure terminal 
      Enter configuration commands, one per line.  End with CNTL/Z.

      
- [ ] **Paso 2.-** Establecer un nombre único.

      router(config)#hostname R1

- [ ] **Paso 3.-** Proteger el acceso al modo privilegiado.

      R1(config)#enable secret class

- [ ] **Paso 4.-** Proteger el acceso del usuario por el puerto de consola.

      R1(config)#line console 0
      R1(config-line)#password cisco
      R1(config-line)#login
      R1(config-line)#exit

- [ ] **Paso 5.-** Activar la administración remota  

      R1(config)#line vty 0 4
      R1(config-line)#password cisco
      R1(config-line)#login
      R1(config-line)#exit

- [ ] **Paso 6.-** Activar la encriptación de contraseñas

      R1(config)#service password-encryption

