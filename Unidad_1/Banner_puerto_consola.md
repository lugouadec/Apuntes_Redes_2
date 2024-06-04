# Activacion del banner en el puerto de consola 
```
R1>enable
R1#configure terminal
Enter configuration commands, one per line.  End with CNTL/Z.
R1(config)#banner motd $ Texto a mostrar$
R1(config)#line console 0
R1(config-line)#motd-banner
R1(config-line)#exit
R1(config)#exit
R1#exit
```
