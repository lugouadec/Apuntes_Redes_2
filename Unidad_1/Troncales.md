## Problema de Diseño de Segmentación en VLANs

### Descripción del Escenario
Se necesita diseñar un esquema de segmentación de red utilizando VLANs para una oficina distribuida en tres pisos. Cada piso tiene diferentes PCs conectadas a distintas VLANs a través de interfaces específicas en switches dedicados. Las redes utilizadas serán 192.168.10.0/24, 192.168.20.0/24, 192.168.30.0/24 y 192.168.40.0/24. Además, se deben configurar enlaces troncales entre los switches, utilizando la VLAN nativa 5.

### Requerimientos de Segmentación
#### PISO NO 1:
- **PC0** pertenece a la VLAN 10 y se conecta a través de la interfaz f0/1
- **PC1** pertenece a la VLAN 20 y se conecta a través de la interfaz f0/6
- **PC6** pertenece a la VLAN 30 y se conecta a través de la interfaz f0/11
- **PC7** pertenece a la VLAN 40 y se conecta a través de la interfaz f0/16

#### PISO NO 2:
- **PC2** pertenece a la VLAN 20 y se conecta a través de la interfaz f0/1
- **PC3** pertenece a la VLAN 40 y se conecta a través de la interfaz f0/6

#### PISO NO 3:
- **PC4** pertenece a la VLAN 10 y se conecta a través de la interfaz f0/1
- **PC5** pertenece a la VLAN 20 y se conecta a través de la interfaz f0/6
- **PC8** pertenece a la VLAN 30 y se conecta a través de la interfaz f0/11
- **PC9** pertenece a la VLAN 40 y se conecta a través de la interfaz f0/16

### Asignación de VLANs e Interfaces
#### Switch0:
- **VLAN 10 (Administración):** F0/1 - F0/5
- **VLAN 20 (Ventas):** F0/6 - F0/10
- **VLAN 30 (Sistemas):** F0/11 - F0/15
- **VLAN 40 (Mercadotecnia):** F0/16 - F0/20

#### Switch1:
- **VLAN 10 (Ventas):** F0/1 - F0/5
- **VLAN 40 (Mercadotecnia):** F0/6 - F0/10

#### Switch2:
- **VLAN 10 (Administración):** F0/1 - F0/5
- **VLAN 20 (Ventas):** F0/6 - F0/10
- **VLAN 30 (Sistemas):** F0/11 - F0/15
- **VLAN 40 (Mercadotecnia):** F0/16 - F0/20

### Configuración de Troncales e Interconexiones
Para asegurar la conectividad entre los distintos pisos, se configurarán enlaces troncales entre los switches. Estos enlaces troncales permitirán el paso del tráfico de múltiples VLANs y utilizarán la VLAN nativa 5 para el tráfico de control.

#### Enlaces Troncales:
- **Switch0 a Switch1:** Configuración de un enlace troncal que incluye todas las VLANs (10, 20, 30, 40) y la VLAN nativa 5.
- **Switch1 a Switch2:** Configuración de un enlace troncal que incluye todas las VLANs (10, 20, 30, 40) y la VLAN nativa 5.
- **Switch0 a Switch2:** Configuración de un enlace troncal que incluye todas las VLANs (10, 20, 30, 40) y la VLAN nativa 5.

### Redes Utilizadas:
- **VLAN 10:** 192.168.10.0/24
- **VLAN 20:** 192.168.20.0/24
- **VLAN 30:** 192.168.30.0/24
- **VLAN 40:** 192.168.40.0/24
