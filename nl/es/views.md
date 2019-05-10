---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, search, filter, events

subcollection: logdnaat

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:codeblock: .codeblock}
{:tip: .tip}
{:download: .download}
{:important: .important}
{:note: .note}


# Creación de vistas personalizadas
{: #views.md}

A través de la interfaz de usuario web de {{site.data.keyword.at_full_notm}}, puede aplicar criterios de búsqueda y filtrado para definir qué sucesos se visualizan a través de una vista personalizada.
{:shortdesc}


## Requisitos previos
{: #views_prereqs}

Antes de empezar, compruebe que el ID de usuario tenga permisos para iniciar la interfaz de usuario web y para ver los sucesos. A continuación,
[vaya a la interfaz de usuario web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).

**Nota:** debe ser un administrador del servicio {{site.data.keyword.at_full_notm}} o un administrador de la instancia de {{site.data.keyword.at_full_notm}} o debe tener permisos de IAM de la cuenta para gestionar políticas.

En la tabla siguiente se muestran las políticas mínimas que debe tener un usuario para poder iniciar la interfaz de usuario web de {{site.data.keyword.at_full_notm}} y visualizar sucesos:

| Rol                      | Permiso otorgado            |
|---------------------------|-------------------------------|  
| Rol de la plataforma: `Visor`     | Permite al usuario ver la lista de instancias de servicio en el panel de control Observabilidad. |
| Rol de servicio: `Lector`      | Permite que el usuario pueda iniciar la interfaz de usuario web y ver sucesos en la interfaz de usuario web.  |
{: caption="Tabla 1. Políticas de IAM" caption-side="top"} 

Para obtener más información sobre cómo configurar estas políticas para un usuario, consulte
[Cómo otorgar permisos de usuario a un usuario o ID de servicio](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events).



## Paso 1. Filtrar sucesos
{: #views_step1}

Puede filtrar sucesos por origen, aplicación y nivel de registro. 

* Un origen puede ser un host, un sistema, una máquina virtual o una app de Heroku.
* Una aplicación representa un archivo de registro, un programa o un contenedor.
* Los ejemplos de niveles de registro son: INFO, DEBUG, ERROR

Realice los pasos siguientes para filtrar registros:

1. En la interfaz de usuario web, pulse el icono **Vistas** ![Icono Configuración](images/views.png "Icono Configuración").
2. Seleccione **Todo** o una vista.
3. Expanda **Todas las etiquetas** para ver la lista de etiquetas disponibles. A continuación, elija las que desee.
4. Expanda **Todos los orígenes** para ver la lista de orígenes disponibles. A continuación, elija las que desee.
5. Expanda **Todas las apps** para ver la lista de apps disponibles. A continuación, elija las que desee.
6. Expanda **Todos los niveles** para ver la lista de niveles disponibles. A continuación, elija las que desee.

A medida que aplica filtros, observará que el nombre de la vista cambia a **Vista sin guardar**.

**Nota:** en cada sección, puede agrupar varias opciones en un grupo. Agrupe etiquetas, orígenes, apps y niveles para reutilizar estas agrupaciones cuando filtre datos en otras vistas personalizadas.

Para crear un grupo, seleccione varios valores. A continuación, pulse **Guardar como grupo**. Especifique un nombre para el grupo y guárduelo.


## Paso 2. Buscar sucesos
{: #views_step2}

Al buscar sucesos, la búsqueda aplica todos los filtros y consultas de tiempo que se hayan configurado en esa vista.

Puede realizar búsquedas simples (búsqueda de series de un solo término), búsquedas compuestas (varios términos de búsqueda y operadores), búsquedas de campo si la línea de registro se puede analizar, y otras. Para obtener más información, consulte [Cómo buscar en los registros en documentos LogDNA ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://docs.logdna.com/docs/search){:new_window}.

**Nota:** los operadores AND y OR distinguen entre mayúsculas y minúsculas y se deben poner en mayúsculas.

A medida que aplica criterios de búsqueda, observará que el nombre de la vista cambia a **Vista sin guardar**.



## Paso 3. Crear una vista personalizada
{: #views_step3}

Tras aplicar un marco de tiempo, filtros y criterios de búsqueda a la vista **Todo** o a una vista personalizada existente, realice los pasos siguientes para guardar el resultado como una vista personalizada:

1. En la interfaz de usuario web, pulse **Vista sin guardar**.
2. Seleccione **Guardar como nueva vista / alerta**. Se abrirá la página *Crear nueva vista*.
3. Especifique un nombre para la vista en el campo *Nombre*.
4. De manera opcional, añada una categoría. Especifique un nombre y, a continuación, pulse **Añadir esta como nueva categoría de vista**.
5. Opcionalmente, adjunte una alerta. Aparecerá una nueva sección para que pueda configurar la alerta.
6. Pulse **Guardar vista**




