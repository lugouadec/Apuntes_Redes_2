- [ ] **Paso 0: Verifique que switch tenga un nombre unico de no ser asi cambialo:**
  - Use el comando `hostname Nombre_unico`.

- [ ] **Paso 1: Verifique la compatibilidad con SSH:**
  - Use el comando `show ip ssh`.
  
- [ ] **Paso 2: Configure el dominio IP:**
  - Configure el nombre de dominio IP de la red mediante el comando `ip domain-name`.
  
- [ ] **Paso 3: Genere un par de claves RSA:**
  - La generación de un par de claves RSA activa automáticamente SSH. Use el comando `crypto key generate rsa`.
  - Nota: para eliminar las claves RSA, use el comando `crypto key zeroize rsa`.
  
- [ ] **Paso 4: Configure la autenticación de usuario:**
  - Para usar el método de autenticación local, cree un par de nombre de usuario y contraseña con el comando `username username secret password`.
  
- [ ] **Paso 5: Configure las líneas vty:**
  - Habilite las vty necesarias con el comando `line vty 0 X`.
  - Utilice el comando `transport input ssh` para que las conexiones se realicen por SSH.
  - Luego, el comando `login local` activará el sistema de usuarios local para SSH.
  
- [ ] **Paso 6: Active SSH versión 2:**
  - De manera predeterminada, SSH se habilita con la versión 1.99. Es necesario que por seguridad habilite la versión 2 con el comando `ip ssh version 2`.
