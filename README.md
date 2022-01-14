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
- ** [Contraseñas](#contraseña)**
- ** [Actualización Firmware](#firmware)**

 
# Introduction

Introducción al motivo de la creación del checklist, al hardening y a los dispositivos UniFi.

## Estado

Trabajo en progreso... :construction_worker:

## Tareas

- [ ] Añadir la información del checklist

## Contraseñas

Modificación de contraseñas para acceder al dispositivos electónico. Accediendo en su web (127.0.0.1), entramos en su interfaz ya que podemos loguearnos con usuario/contraseña, por defecto esta puesta como ubnt/ubnt. Debemos modificar esta contraseña para que nadie pueda acceder a nuestro dispositivo

Por otro lado, es comveniente sustituir la contraseña de acceso al Wifi, más segura de la que viene por defecto, que sea entre 10 y 20 dígitos, con números, símbolos, mayúsculas y minúsculas.

## Actualización Firmware

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

