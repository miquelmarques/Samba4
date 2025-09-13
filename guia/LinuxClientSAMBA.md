# 0. Introducció

Per configurar un equip Linux perquè accediexi al Domini de Samba 4 es pot realitzar de dues formes la configuració mentre s'instal·la o amb un client ja instal·lat, en aquest punt es mostra mentre ho instal·les. Et deixo dues guies per poder realitzar la configuració amb tots els pasos més detallats mentre s'instal·la i un cop tent el SO instal·lat.

**[Opció 1: Configurar des de un client ja instal·lat.](Altres/ConfiguracióLinux1.md)**

**[Opcio 2: Mentre s'instal·la](Altres/ConfiguracióLinux2.md)**

# 1. <a name="ConfXarxa" ></a> Configuració de xarxa abans d’instal·lar

Abans d’instal·lar el Zorin hem de seleccionar que el volem provar per tal de poder modificar la xarxa perquè el DNS apunti al servidor SAMBA 4.

   <p align="center">
      <img src="../imatges/LinuxClient/image002.gif" alt="Configuració de la xarxa abans d'instal·lar el SO">
   </p>

# 2. <a name="UsuLocal" ></a>Creació usuari local

Com ja hem configurat el DNS ara ens posem a fer la instal·lació normal fins al punt que arribem a l'apartat d'usuari allà crearem un usuari local i marquem l'opció d'un directori actiu.

   <p align="center">
      <img src="../imatges/LinuxClient/image004.gif" alt="Establint un usuari local per pooder getionar la maquina localment.">
   </p>

# 3. <a name="ConDomini" ></a> Connectar el client al domini

Ara en la següent pantalla ens demanarà la configuració del domini, per tant, hem de posar el nom i l'usuari administrador amb la seva contrasenya.

   <p align="center">
      <img src="../imatges/LinuxClient/image006.gif" alt="Afegint el equip en el Samba4">
   </p>

# 4.<a name="Comprovacio" ></a> Acces amb un usuari

En aquest punt anem a l’opció d'usuari no llistat i posem l'usuari com si fos un compte de correu ([usuari@so18.test](mailto:usuari@so18.test)) i un cop ho tenim posem la contrassenya.

   <p align="center">
      <img src="../imatges/LinuxClient/image008.gif" alt="Comprovació de que el equip estigui connectat realitzant la comanda id.">
   </p>