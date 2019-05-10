---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, view events

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


# Visualización de sucesos
{: #view_events.md}

Tras suministrar una instancia del servicio {{site.data.keyword.at_full_notm}} en
{{site.data.keyword.cloud_notm}}, puede ver sucesos a través de la interfaz de usuario web de
{{site.data.keyword.at_full_notm}}.
{:shortdesc}


## Requisitos previos
{: #view_events_prereqs}

Antes de empezar, compruebe que el ID de usuario tenga permisos para iniciar la interfaz de usuario web y para ver los sucesos. 

**Nota:** debe ser un administrador del servicio {{site.data.keyword.at_full_notm}} o un administrador de la instancia de {{site.data.keyword.at_full_notm}} o debe tener permisos de IAM de la cuenta para gestionar políticas.

En la tabla siguiente se muestran las políticas mínimas que debe tener un usuario para poder iniciar la interfaz de usuario web de {{site.data.keyword.at_full_notm}} y visualizar sucesos:

| Rol                      | Permiso otorgado            |
|---------------------------|-------------------------------|  
| Rol de la plataforma: `Visor`     | Permite al usuario ver la lista de instancias de servicio en el panel de control Observabilidad. |
| Rol de servicio: `Lector`      | Permite que el usuario pueda iniciar la interfaz de usuario web y ver sucesos en la interfaz de usuario web.  |
{: caption="Tabla 1. Políticas de IAM" caption-side="top"} 

Para obtener más información sobre cómo configurar estas políticas para un usuario, consulte
[Cómo otorgar permisos de usuario a un usuario o ID de servicio](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events).


## Ver sucesos a través de la interfaz de usuario web
{: #view_events_step1}

Para iniciar la interfaz de usuario web de {{site.data.keyword.at_full_notm}}, realice los pasos siguientes:

1. [Inicie sesión en su cuenta de {{site.data.keyword.cloud_notm}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://cloud.ibm.com/login){:new_window}.

	Después de iniciar sesión con su ID de usuario y su contraseña, se abre el *Panel de control* de {{site.data.keyword.cloud_notm}}.

2. Vaya al icono de menú ![Icono Menú](../../icons/icon_hamburger.svg) y seleccione **Observabilidad**. 

3. Seleccione **Activity Tracker**. 

    Se muestra la lista de instancias de {{site.data.keyword.at_full_notm}}.

    **Nota:** hay 1 instancia por región.

4. Seleccione la región donde desee ver los sucesos. A continuación, pulse **Ver LogDNA**.

Se abre la interfaz de usuario web de {{site.data.keyword.at_full_notm}} y muestra la vista **Todo**. A través de esta vista, puede ver los sucesos de su cuenta para la región que haya seleccionado.

**Nota:** si tiene un plan `Lite` y no puede ver los sucesos que está buscando, es posible que necesite actualizar a un plan de pago para habilitar las funciones de búsqueda para sucesos anteriores. El número de días que los sucesos están disponibles para la búsqueda depende del plan que elija. [Más información](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan#service_plan).


## Personalizar la vista predeterminada
{: #view_events_step2}

En la sección **PREFERENCIAS DE USUARIO**, puede modificar el orden de los campos de datos que se muestran en cada línea.

Realice los pasos siguientes para modificar el formato de una línea de suceso:

1. En la interfaz de usuario web, pulse el icono **Configuración** ![Icono Configuración](images/admin.png "Icono Administración").
2. Seleccione **PREFERENCIAS DE USUARIO**. Se abre una nueva ventana.
3. Seleccione **Formato de registro**.
4. Modifique la sección *Formato de línea* para que se ajuste a sus requisitos. Arrastre los recuadros.




## Ver un suceso en contexto
{: #view_events_step3}

En cualquier momento, puede ver cada línea en su contexto.

Siga los pasos siguientes: 

1. En la interfaz de usuario web, pulse el icono **Vistas** ![Icono Configuración](images/views.png "Icono Configuración").
2. Seleccione **Todo** o una vista personalizada.
3. Identifique una línea que desee explorar.
4. Expanda la línea. 

    Aparece información sobre identificadores, códigos y etiquetas de línea.

5. Pulse **Ver en contexto** para ver la línea de suceso en el contexto de otras entradas de dicho host, app, o ambos.

Cuando haya terminado de explorar el suceso, pulse **Cerrar** para cerrar la línea.




## Copiar un suceso en el portapapeles
{: #view_events_step4}


Realice los pasos siguientes para copiar un suceso en el portapapeles: 

1. En la interfaz de usuario web, pulse el icono **Vistas** ![Icono Configuración](images/views.png "Icono Configuración").
2. Seleccione **Todo** o una vista personalizada.
3. Identifique una línea que desee explorar.
4. Expanda la línea. 

    Aparece información sobre identificadores, códigos y etiquetas de línea.

5. Pulse **Copiar al portapapeles** para copiar el suceso al portapapeles.

Cuando haya terminado de explorar el suceso, pulse **Cerrar** para cerrar la línea.




