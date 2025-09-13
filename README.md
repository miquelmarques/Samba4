# **ACTIVE DIRECTORY AMB SAMBA 4**

En entrons de sistemes opertaius de forma lliure i gratuita existeixen varies opcions quan volem aconseguir un equip com un AD DS busquem opcions com NFS4 i SAMBA 4. Que son opcions que principalment en entorns basics serveixen per compartir fitxers, carpetes i en alguns casos impressores.

<h2 style="text-align:center"> 📖Introducció</h2>

En aquesta guia crearem un Servidor Ubuntu 24.04.2 LTS amb SAMBA 4 que amb una gestió de Kerberos 5. En que fen servir Kerberos permet la connexió del dominia amb equips Windows i Linux (usant SSD). En aquesta guia fem servir una simulació de creació amb Maquines Virtuals.

<h2 align="center"> Índex</h2>

<h3>Instal·lació i desplegament </h3>

1. <a href="guia/Desplegament.md/#ConfiguracioDNS">Configuració de espai de Noms Servidor</a>

1. <a href="guia/Desplegament.md#Instalacio">Instal·lació SAMBA</a>

1. <a href="guia/Desplegament.md#ConfigTemps">Configuració/sicronització temps</a>

1. <a href="guia/Desplegament.md#Comprovacions">Comprovació de la Instal·lació</a>

1. <a href="guia/Desplegament.md#Altres">Altres comandes</a>

<h3>Configurant usuaris amb comandes</h3>

En procés, disculpi les molesties

<h3> Configurant un equip Windows</h3>

1. <a href="guia/Windows11RSAT.md/#ConfigXarxa">Configuració Xarxa</a>

1. <a href="guia/Windows11RSAT.md/#AgregarCl">Agregar al Domini</a>

1. <a href="guia/Windows11RSAT.md/#LogInAdmin">Comprovació amb usuari Admin</a>

<h3>Configurant els usuaris amb RSAT</h3>

1. <a href="guia/Windows11RSAT.md/#InsRSAT">Instal·lació de RSAT AD DS(Active Directory Domain Services)</a>

1. <a href="guia/Windows11RSAT.md/#RSATADDS">Exemple de configuració amb RSAT AD DS</a>

<h3>Conifugració Equip Linux</h3>

1. <a href="guia/LinuxClientSAMBA.md/#ConfXarxa">Configuració de Xarxa</a>

1. <a href="guia/LinuxClientSAMBA.md/#UsuLocal">Creació d'un usuari local</a>

1. <a href="guia/LinuxClientSAMBA.md/#ConDomini">Connectar el client al domini</a>

1. <a href="guia/LinuxClientSAMBA.md/#Comprovacio">Comprovació de la configuració</a>

<h3>Creació i configuració carpeta HOME</h3>

1. <a href="guia/Carpetahome.md/#Creacio">Creació de la carpeta Home amb els permisos adients</a>

1. <a href="guia/Carpetahome.md/#Compartir">Comparticio mitjançant Samba</a>

1. <a href="guia/Carpetahome.md/#ConfUsu">Configuració dels usuari amb RSAT</a>

1. <a href="guia/Carpetahome.md/#Comprovacio">Comprovació de la configuració</a>

<h3>Bibliografia i Webgrafia</h3>

Computer, C. (2024, 19 mayo). AD DS - ACTIVE DIRECTORY DOMAIN SERVICES. Clockwork Computer. [https://clockworkcomputerip.blogspot.com/2022/11/ad-ds-active-directory-domain-services.html](https://clockworkcomputerip.blogspot.com/2022/11/ad-ds-active-directory-domain-services.html)

Setting up Samba as an active Directory domain controller - SambaWiki. (n.d.). [https://wiki.samba.org/index.php/Setting_up_Samba_as_an_Active_Directory_Domain_Controller](https://wiki.samba.org/index.php/Setting_up_Samba_as_an_Active_Directory_Domain_Controller)

Clockwork Computer. (2024, 21 marzo). 💻SAMBA 4ACTIVE DIRECTORY DOMAIN CONTROLLER EN UBUNTU SERVER + UNION WINDOWS 10 [Vídeo]. YouTube. [https://www.youtube.com/watch?v=61ChELri2_k](https://youtu.be/61ChELri2_k)