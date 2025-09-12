
# <a name="ConfiguracioDNS"></a> **Configuració i Instal·lació Samba (SMB)**
 ## 1. **Nom del servidor** 
   En aquest punt la nostra màquina s’ha de dir dc, ja que és el controlador de domini.

   En aquest cas el server ja es diu així però si nó fariem servir la comanda:

    sudo hostnamectl set-hostname dc
   
   <p align="center">
      <img src="../imatges/AA3 SAMBA AD DS (Miquel Marquès)_archivos/image001.gif">
   </p>

## 2. Nom complet del servidor.**
   En aquest punt modifiquem l'arxiu de host per posar el nom complet per la màquina

   i li posem una segona línia on posi la IP de la màquina en la xarxa i el nom complet.

    192.168.114.146 	dc.so18.test dc

   <p align="center">
      <img src="../imatges/AA3 SAMBA AD DS (Miquel Marquès)_archivos/image002.gif">
   </p>

   Un cop fet fem la resolució de noms per comprovar-ho.

   <p align="center">
      <img src="../imatges/AA3 SAMBA AD DS (Miquel Marquès)_archivos/image003.gif">
   </p>

## 3. **Desactivar el servei systemd-resolved**
   El següent punt és deshabilitar el servei de resolució de noms de samba, ja que és incompatible amb samba 4.
   <p align="center">
      <img src="../imatges/AA3 SAMBA AD DS (Miquel Marquès)_archivos/image004.gif">
   </p>

## 4. **Eliminar l'enllaç simbòlic a l'arxiu /etc/resolv.conf i configurar**
   Seguidament de deshabilitar el servei de resolució de noms hem de desenllaçar l'arxiu per poder-ho modificar-lo.

   <p align="center">
      <img src="../imatges/AA3 SAMBA AD DS (Miquel Marquès)_archivos/image005.gif">
   </p>

   Un cop fet ara modifiquem l'arxiu i posem el següent on posem la IP del nostre servidor un DNS per accedir a internet i que el domini de cerca és el nostre domini.

   
   <p align="center">
      <img src="../imatges/AA3 SAMBA AD DS (Miquel Marquès)_archivos/image006.gif">
   </p>

   I finalment el convertim en un arxiu immutable és a dir que no es modifica.

   <p align="center">
      <img src="../imatges/AA3 SAMBA AD DS (Miquel Marquès)_archivos/image007.gif">
   </p>

 ## 5.  <a name="Instalacio"></a>**Instal·lació Samba amb les seves dependències**
   Ara ja tenim preparat el nostre servidor per instal·lar samba 4, l’instal·lem amb totes les seves dependències.

   <p align="center">
      <img src="../imatges/AA3 SAMBA AD DS (Miquel Marquès)_archivos/image008.gif">
   </p>

   On ens demanarà el nom que s’ha de buscar en el DNS perquè el registre de Kerberos 5 concordi.

   <p align="center">
      <img src="../imatges/AA3 SAMBA AD DS (Miquel Marquès)_archivos/image009.gif">
   </p>
   En el següent punt ens pregunta el servidor administratiu pel Kerberos que en aquest cas és el nostre.

   <p align="center">
      <img src="../imatges/AA3 SAMBA AD DS (Miquel Marquès)_archivos/image010.gif">
   </p>

## 6. <a name="Configuracio"></a>**Deshabilitar els serveis innecessaris**
   En aquest punt deshabilitem els serveis smbd i nmbd i winbind. Ja que no els necessitem en aquest punt.
   <p align="center">
      <img src="../imatges/AA3 SAMBA AD DS (Miquel Marquès)_archivos/image011.gif">
   </p>

## 7. **Habilitar Samba Active Directory** 
   En aquest cas eliminem la màscara del servei de samba amb AD DS i l'habilitem.

   <p align="center">
      <img src="../imatges/AA3 SAMBA AD DS (Miquel Marquès)_archivos/image012.gif">
   </p>
   
## **Crear una còpia de seguretat de l'arxiu /etc/samba/smb.conf**
   En aquest cas fem una còpia de l'arxiu de /etc/samba/smb.conf per a mantenir l'original.
    <p align="center">
      <img src="../imatges/AA3 SAMBA AD DS (Miquel Marquès)_archivos/image013.gif">
   </p>

## 8. **Configurar el domin i el servidor de Samba 4**
   En aquest cas configurem el nostre Servidor i creem el domini per poder fer el controlador de domini.

   <p align="center">
      <img src="../imatges/AA3 SAMBA AD DS (Miquel Marquès)_archivos/image014.gif">
   </p>

   I un cop realitzat ens demanarà una contrasenya d’administrador. I posem una contrasenya en aquest cas he posat P@ssw0rd i ha començat a desplegar el domini.

   <p align="center">
      <img src="../imatges/AA3 SAMBA AD DS (Miquel Marquès)_archivos/image015.gif">
   </p>

## 9.  **Reemplaçar l'arxiu generat per samba de kbr5**
   El primer que faig és guardar per seguretat l'arxiu que ja està fet canviar-li el nom.

   <p align="center">
      <img src="../imatges/AA3 SAMBA AD DS (Miquel Marquès)_archivos/image016.gif">
   </p>

   I a continuació copio l'arxiu de krb5.conf que s’ha generat per samba en la seva ubicació que toca.

   <p align="center">
      <img src="../imatges/AA3 SAMBA AD DS (Miquel Marquès)_archivos/image017.gif">
   </p>

   Un cop fet ara habilitem el servei samba-ad-dc i comprovem el funcionament.

   <p align="center">
      <img src="../imatges/AA3 SAMBA AD DS (Miquel Marquès)_archivos/image018.gif">
   </p>

# <a name="ConfigTemps"></a>**Configuració de sincronitzacio del temps.**
## 1. **Canviar els permisos del directori ntp\_signd**
   En aquest punt modifiquem la propietat a la carpeta ntp\_signd i els permisos UGO.

   <p align="center">
      <img src="../imatges/AA3 SAMBA AD DS (Miquel Marquès)_archivos/image019.gif">
   </p>

## 2. **Modificar l'arxiu de configuració de chrony** 
   En aquest punt modifico l'arxiu chrony per poder afegir les següents línies:

    bindcmdaddress 192.168.114.146
    allow 192.168.114.0/24
    ntpsigndsocker /var/lib/samba/ntp\_signd

`	`En l'arxiu de /etc/chrony/chrony.conf

 <p align="center">
      <img src="../imatges/AA3 SAMBA AD DS (Miquel Marquès)_archivos/image020.gif">
   </p>

I reiniciem el servei chrony i comprovem el estat

 <p align="center">
      <img src="../imatges/AA3 SAMBA AD DS (Miquel Marquès)_archivos/image021.gif">
   </p>

# <a name="Comprovacions"></a>**Verificació de Samba en AD DS**
## 1. **Verificació dels noms de domini**
  
   <p align="center">
      <img src="../imatges/AA3 SAMBA AD DS (Miquel Marquès)_archivos/image022.gif"> <br>
      <img src="../imatges/AA3 SAMBA AD DS (Miquel Marquès)_archivos/image023.gif">
   </p>

## 2.  **Verificació amb LDAP i Kerberos**
  
   <p align="center">
      <img src="../imatges/AA3 SAMBA AD DS (Miquel Marquès)_archivos/image024.gif">
   </p>

## 3. **Verificació de recursos predeterminats**

 <p align="center">
      <img src="../imatges/AA3 SAMBA AD DS (Miquel Marquès)_archivos/image025.gif">
   </p>

## 4. **Verificació d’autenticació de Kerberos**
  <p align="center">
      <img src="../imatges/AA3 SAMBA AD DS (Miquel Marquès)_archivos/image026.gif">
   </p>

## 5. **Connectar-se al recurs compartit NETLOGON**

   <p align="center">
      <img src="../imatges/AA3 SAMBA AD DS (Miquel Marquès)_archivos/image027.gif">
   </p>
   
# <a name="Altres"></a>**Altres comandes:**
### **Cambiar contrassenya administrador**

    sudo samba-tool user setpassword administrator

### **Veure integritat de l'arxiu de configuració**

    testparm

### **Veure el nivell de domini de Windows AD DC**

    sudo samba-tool domain level show



