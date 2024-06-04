# **Configurar el acceso administrativo local via Telnet**

  - [ ] **Paso 1.- [Crear y habilitar la Interface Virtual del Switch (SVI)](/Unidad_1/Creacion%20de%20SVI.md)**

  - [ ] **Paso 2.- Establecer la contraseña del modo Privilegiado**

    ```plaintext
    (config)# enable secret contraseña
    ```

  - [ ] **Paso 3.- Configurar las líneas VTY del 0 al 5**

    ```plaintext
    (config)# line vty 0 5
    ```

  - [ ] **Paso 4.- Asignar una contraseña para el acceso via Telnet**

    ```plaintext
    (config-line)# password contraseña
    ```

  - [ ] **Paso 5.- Activar la petición de contraseña al acceso via Telnet**

    ```plaintext
    (config-line)# login
    ```

  - [ ] **Paso 6.- Salir al modo privilegiado**

    ```plaintext
    (config-line)# end
    ```

  - [ ] **Paso 7.- Guardar la configuración**

    ```plaintext
    # copy running-config startup-config
    ```

  - [ ] **Paso 8.- Verifica que la configuración este correcta**

    ```plaintext
    # show running-config
    ```
