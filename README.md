<p align="center">
  <a href="https://github.com/IES-Rafael-Alberti/unifi-hardening-checklist">
    <img src="https://github.com/IES-Rafael-Alberti/unifi-hardening-checklist/blob/main/img/unifi-hardening-checklist_preview.png" alt="Logo de UniFi Hardening Checklist">
  </a>
</p>

<br>

<p align="center">
  <a href="https://github.com/IES-Rafael-Alberti/unifi-hardening-checklist/pulls">
    <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg?longCache=true" alt="Pull Requests">
  </a>
  <a href="LICENSE.md">
      <img src="https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg?longCache=true" alt="CC BY-SA License">
    </a>
</p>

<div align="center">
  <sub>Creado por el alumnado del Curso de Especialización de Ciberseguridad en Entornos de Tecnologías de la Información del IES Rafael Alberti - Promoción 21/22</a>
</div>

<br>

****

# Tabla de contenidos

- **[Introducción](#introduccion)**
  * [Estado](#estado)
  * [Tareas](#tareas)
- **[Contraseñas](#contraseña)**
- **[Actualización Firmware](#firmware)**
- **[Firewall](#firewall)**
- **[Filtrado por M.A.C](#mac)**
- **[Crear red Invitados](#guest)**
- **[Gestión Avanzada de Malware](#Malware)**
- **[Notificaciones del dispositivo](#Notificaciones)**
- **[configuracion avanzada global threat management](#configuracion-avanzada-global-threat-management)**
- **[configuracion UPNP](#configuracion-UPNP)**
- **[Protección de protocolos de email y VoiP](#EmailyVoIP)**
- **[SNMP](#SNMP)**
- **[Tabla Checklist (Plantilla) Wi-Fi Unifi](#checklist)**


 
# Introduction

Introducción al motivo de la creación del checklist, al hardening y a los dispositivos UniFi.

## Estado

Trabajo en progreso... :construction_worker:

## Tareas

- [ ] Añadir la información del checklist

## Contraseñas<a name="contraseña"></a>

Modificación de contraseñas para acceder al dispositivo electrónico. Accediendo en su web (127.0.0.1), entramos en su interfaz ya que podemos loguearnos con usuario/contraseña, por defecto esta puesta como ubnt/ubnt. Debemos modificar esta contraseña para que nadie pueda acceder a nuestro dispositivo

Por otro lado, es comveniente sustituir la contraseña de acceso al Wifi, más segura de la que viene por defecto, que sea entre 10 y 20 dígitos, con números, símbolos, mayúsculas y minúsculas.

https://app.tango.us/app/workflow/3244a260-907b-4529-ba0c-f795ed96beff

## Actualización Firmware<a name="firmware"></a>

Como sabemos, es importante mantener nuestros dispositivos siempre actualizados. Esto nos permite en princpio subsanar muchas de las vulnerabilidades que se usan en posibles ataques.

Por lo tanto tener un **Firmware** que reciba actualizaciones; es buena señal. Quiere decir que el fabricante se preocupa porque sus dispositivos sean cada vez más seguros.
Y también nos permitirá mas variedad de configuraciones de hardening o bastionado.

En este caso, los _Wi-Fi Unifi_, el fabricante y su comunidad van sacando actualizaciones y tenemos varias maneras de poder actualizarlos a tráves de la interfaz gráfica de su controlador _UniFi-Controller_ y son:

- Actualización simple a la última versión (si el/los dispositivos están _"adoptados"_).
  - También se puede realizar una actualización masiva; solo para los dispositivos inalámbricos, que esten pendientes de actualizarse.
- Actualización en dispositivos con acceso a Internet. El caso de que no se quiera la última versión y queramos una anterior o Beta. Por ejemplo, para probarla en un solo dispositivo, antes de _"adoptar"_ el dispositivo en _UniFi Controller_.
Si ya lo tenemos _"adoptado"_ , también podremos a tráves de las propiedades del dispositivo en _UniFi-Controller_ instalar una versión anterior.
- Actualización en dispositivos sin conexión a Internet (Caché). En el caso de que los dispositivos Wi-Fi Unifi aún no tengan conexión Internet.
Pero _Unifi-Controller_ si. Tendremos esta opción.
  - Nos permite a tráves del controlador, ingresando un link; para actualizar el dispositivo.
    Tiene un apartado de _Dispositivos Conocidos_ o _Dispositivos del Sitio_ , en el que podremos actualizar eligiendo previamente la versión.
    Que posteriormente en un apartado de _Descargas_ , podremos descargarla en los distintos dispositivos que querramos.
- Actualización vía SSH de manera local (Aplicable a UniFi AP) para dispositivos con/sin Internet.
- Actualizaciones automáticas. También podemos recibir las actualizaciones de manera automáticas.
  A tráves del menu de configuración de _Unifi-Controller_ tenemos un _"check"_ que podremos activar/desactivar según nos convenga.

## Firewall<a name="firewall"></a>
Creación en proceso por Jose Manuel Arrieta

## Protocolo de Seguridad<a name="Cifrado"></a>
El uso de WPA2 proporciona a los usuarios de WiFi un mayor nivel de seguridad, de modo que los datos compartidos a través de la red no puedan ser interceptados por terceros. Este protocolo actualmente no se puede considerar absolutamente seguro por lo que existe una nueva revision de este llamado WPA3.
No todos los dipositivos son compatibles con este ultimo protocolo, por lo que tenemos la opción de configurar y hacer uso de uno de ellos dependiendo del dispositivo receptor.

Enlace de configuración:
https://app.tango.us/app/workflow/d2a9580c-8746-43ef-9711-57ce03c3d446

## Configuracion IDS e IPS<a name="IDS"></a>
En el dispositivo tenemos la opción de configurar IDS e IPS para protegernos del acceso al dispositivo y denegar paquetes que nuestro sistema detecte como intrusivo. En el momento que se producte una intrusión o ataque, este emite una alerta a los administradores del sistema

Enlace de configuración: 
https://app.tango.us/app/workflow/1d316b1b-67c0-4c21-ad62-a10c2acac0fb

## Filtrado por M.A.C<a name="mac"></a>
Si queremos tener una capa adicional de seguridad, entre las recomendaciones básicas y si tenemos una lista concreta de los dispositivos que queremos que se conecte a nuestro _Unifi Wi-Fi_, o si por el contrario queremos denegar a _"x"_ dispositivos de que no se puedan conectar a nuestra red Wi-Fi. Tenemos el filtrado por M.A.C

Este dispositivo nos proporciona en sus opciones esta configuración.
- Enlace al proceso de configuración Filtrado por M.A.C en _Unifi Controller_: https://app.tango.us/app/workflow/32d30dd1-f737-4a22-9080-4e9c37614231

## Crear red de Invitados<a name="guest"></a>
En muchas redes el acceso público se ha convertido en algo necesario y muy valioso, desde los aeropuertos hasta las cafeterías, las redes de invitados están satisfaciendo necesidades, minimizando los riesgos de seguridad y asegurando calidad. UniFi habilita a los administradores con las herramientas necesarias para configurar redes de invitados.

Enlace: https://app.tango.us/app/workflow/175f2b3a-3100-4c68-979a-9288f72b01ea

## Gestión Avanzada de Malware<a name='Malware'></a>
Para protegernos de todo tipo de malware tenemos bastantes opciones que podemos ir activando dependiendo de nuestras necesidades, yo elegí las más básicas a modo de demostración.

Enlace: https://app.tango.us/app/workflow/63a77a14-9c29-432b-9717-7e2a6dd8e4ff

## Notificaciones del dispositivo<a name="Notificaciones"></a>
Podemos elegir las notificaciones que nos avisará el dispositivo, podemos seleccionar que se muestre como una notificación PUSH, que nos reenvíe a una página con la notificación o que nos mande un email.

Enlace: https://app.tango.us/app/workflow/4f2067ce-7988-4b63-b10a-919151cd714f

## configuracion avanzada global threat management<a name="configuracion-avanzada-global-threat-management"></a>
En este paso añadimos las configuraciones para control de ip comprometidas, TFTP, SNMP.

link: https://app.tango.us/app/workflow/27232efb-8ed0-4141-977c-811acf4302f5

## configuracion UPNP<a name="configuracion-UPNP"></a>
En este apartado vamso a a añadir  la configuracion upnp para añadir automaticamente la gateway a los dispositivos en la red que queramos.

link: https://app.tango.us/app/workflow/cc8e41e2-32e2-44e7-a3c1-c4204386cce1

## Configuracion frente a ataques a protocolos de email y VoIP<a name="EmailyVoIP"></a>
Aquí vamos a activar la protección frente a ataques a los protocolos de email(IMAP, SMTP y POP3) y frente a los ataques a VoIP.

Enlace a la guía: https://app.tango.us/app/workflow/9834e41d-188b-4c6f-b01b-88e4505d20c6

## Configuracion de SNMP<a name="SNMP"></a>
Aquí vamos a activar la opción de SNMP para facilitar la configuración de administración entre los diferentes dispositivos de red.

Enlace a la guía: https://app.tango.us/app/workflow/60d09e6b-8cab-4417-b6f7-90f376915bce

## Tabla Checklist Wi-Fi Unifi<a name="checklist"></a>

## :ballot_box_with_check: Tabla Checklist (Plantilla)

En el código del archivo copiar/pegar, para ir creando mas filas a la tabla del checklist.

| <b>Control</b> | <b>Nivel Bajo/Medio/Alto</b> | <b>Checkbox</b> |
| :---        | :---:       | :---:        |
| Nombre:Control | Nivel: Bajo/Medio/Alto | :black_square_button: |
| Contraseñas: Se han cambiado las claves por defecto del panel de administración del dispositivo. Haciendo uso de claves robustas entre 10 y 20 carácteres alfanúmericos y carácteres especiales. | Nivel: Alto | :black_square_button: |
| Actualización Firmware: Se ha actualizado el firmware en el dispositivo. | Nivel: Alto | :black_square_button: |
| Microsegmentación de VLAN | Nivel:  | :black_square_button: |
| Creación de backups automáticos | Nivel:  | :black_square_button: |
| Filtrado por M.A.C: Se han establecido listas blancas/negras de M.A.C's en la red Wi-Fi | Nivel: Medio | :black_square_button: |
| Red Guest: Se ha creado red Invitados diferenciada de la red principal. | Nivel: Medio | :black_square_button: |
| Se ha configurado el protocolo de seguridad WPA2/WPA3. | Nivel: Alto | :black_square_button: |
| Se ha configurado los sistemas IDS e IPS. | Nivel: Alto | :black_square_button: |
| Gestión de malware | Nivel: Alto | :black_square_button: |
| Notificaciones | Nivel: Bajo | :black_square_button: |
| Configuracion avanzada global threat | Nivel: alto | :black_square_button: |
| configuracion upnp | Nivel: Bajo | :black_square_button: |
| Configuracion frente a ataques a protocolos de email y VoIP | Nivel: Medio | :black_square_button: |
| Configuracion de SNMP | Nivel: Bajo | :black_square_button: |
