# Pasos para configurar un banner en Cisco IOS

1. **Accede al modo de configuración global:** Para hacer esto, ingresa al modo privilegiado del router o switch utilizando el comando `enable` y luego accede al modo de configuración global con el comando `configure terminal`.

   ```bash
   Router> enable
   Router# configure terminal
   ```
2. **Configura el banner de mensaje de bienvenida:** Utiliza el comando banner motd seguido del delimitador que deseas utilizar para el mensaje (por ejemplo, #, %, etc.) y luego escribe el mensaje que deseas mostrar.
  ```bash
    Router(config)# banner motd #  Enter your message here. This message will be displayed when someone logs in. #
```
El mensaje entre los delimitadores será mostrado cuando alguien inicie sesión en el dispositivo.

3.- **Configura el banner de mensaje de acceso:** Puedes configurar un mensaje que se muestra antes de que alguien inicie sesión en el dispositivo utilizando el comando `banner login`.
```bash
  Router(config)# banner login # Enter your message here. This message will be displayed before login. #
```
Este mensaje se mostrará antes de que se pida la autenticación.

4.-**Salir de la configuración y guardar los cambios:** Una vez que hayas configurado los banners, sal del modo de configuración y guarda los cambios utilizando los comandos `exit` y `write memory` (o `copy running-config startup-config`).
  ```bash
    Router(config)# exit
    Router# write memory
 ```
Esto guardará la configuración y la aplicará en el reinicio del dispositivo.
