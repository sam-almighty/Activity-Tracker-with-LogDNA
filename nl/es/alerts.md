---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, alerts, events

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


# Configuración de alertas
{: #alerts.md}

A través de la interfaz de usuario web de {{site.data.keyword.at_full_notm}}, puede aplicar criterios de búsqueda y filtrado para definir qué sucesos se visualizan a través de una vista personalizada. A continuación, puede añadir una alerta a una vista para que se le notifique. Puede adjuntar una o más alertas a una vista. Puede definir varios canales de notificación para una alerta. Puede silenciar alertas. Puede desvincular alertas de una vista.
{:shortdesc}


Puede configurar cualquiera de las condiciones siguientes para una alerta:

* *Frecuencia*: especifique la frecuencia con la que se desencadena una alerta. Los valores válidos son: 30 segundos, 1 minuto, 5 minutos, 15 minutos, 30 minutos, 1 hora, 6 horas, 12 horas, 24 horas
* *Contador de líneas de sucesos*: especifique el número de líneas de sucesos que coinciden con los criterios de filtrado y búsqueda de la vista. Cuando se alcanza el número de líneas de sucesos, se desencadena una alerta.

Puede decidir si deben comprobarse ambas condiciones o solo una de ellas. Si se establecen ambas condiciones, se desencadena una alerta cuando se alcanza cualquiera de los umbrales. 

Por ejemplo, puede configurar una alerta que se desencadene después de 30 segundos, o cuando se recopilen 100 líneas de sucesos que coincidan con los criterios de filtrado y de búsqueda de la vista.

Puede configurar varios canales de notificación. Los valores válidos son: `email`, `Slack`, `PagerDuty`, `Webhook`, `OpsGenie`, `Datadog`, `AppOptics`, `VictorOps`

También puede definir un **valor preestablecido**. Un valor preestablecido es una plantilla de alerta que puede adjuntar a cualquier número de vistas. 

Se mostrará un icono de campana con la vista para indicar que esta vista tiene una alerta añadida.


## Requisitos previos
{: #views_prereqs}

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

**Debe tener un plan de servicio de pago** para el servicio {{site.data.keyword.at_full_notm}}. [Más información](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan#service_plan). 


## Paso 1. Acceder a la interfaz de usuario web
{: #alerts_step1}

[Vaya a la interfaz de usuario web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).


## Paso 2. Crear una vista
{: #alerts_step2}

[Cree una vista](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views.md#views.md).



## Paso 3. [Opcional] Configurar un valor preestablecido (plantilla de alerta)
{: #alerts_step3}

Para reutilizar una configuración de alerta con distintas vistas, configure un **valor preestablecido de alerta**.
{: note}

Realice los pasos siguientes para configurar un valor preestablecido:

1. En la interfaz de usuario web, seleccione el icono **Configuración** ![Icono Configuración](images/admin.png "Icono Administración").
2. Seleccione **Alertas**.
3. Seleccione **Añadir un valor preestablecido de alerta**.
4. Elija un canal de notificación. 
5. Defina las condiciones de umbral.

    1. Seleccione la frecuencia. Por ejemplo, 12 horas.

    2. Especifique el número de líneas de sucesos tras el cual desea que se desencadene la alerta.

    3. Seleccione si desea que se comprueben ambas condiciones o solo una de ellas.

6. Añada los detalles del canal de notificación que ha elegido.

    Por ejemplo, para el canal de notificación por correo electrónico, añada uno o más destinatarios y, de manera opcional, un huso horario.

7. Pulse **Guardar alerta**.



## Paso 4. Configurar una alerta
{: #alerts_step4}

Elija cualquiera de las opciones siguientes para añadir una alerta a una vista:

### Opción 1. Configurar una alerta utilizando un valor preestablecido
{: #alerts_step4_preset}

Realice los pasos siguientes para añadir un valor preestablecido a una vista:

1. En la interfaz de usuario web, pulse el icono **Vistas** ![Icono Configuración](images/views.png).
2. Pulse sobre el nombre de la vista a la que desee adjuntar una alerta. A continuación, seleccione **Adjuntar una alerta**.
3. Elija un valor preestablecido para reutilizar una definición de alerta. 
4. Pulse **Guardar alerta**. 




### Opción 2. Configurar una alerta específica de la vista
{: #alerts_step4_view}

Realice los pasos siguientes para añadir una alerta a una vista:

1. En la interfaz de usuario web, pulse el icono **Vistas** ![Icono Configuración](images/views.png).
2. Pulse el nombre de la vista. A continuación, seleccione **Adjuntar una alerta**.
3. Elija **Alerta específica de vista**.
4. Elija un canal de notificación. 
5. Defina las condiciones de umbral.

    1. Seleccione la frecuencia. Por ejemplo, 12 horas.

    2. Especifique el número de líneas de sucesos tras el cual desea que se desencadene la alerta.

    3. Seleccione si desea que se comprueben ambas condiciones o solo una de ellas.

6. Añada los detalles del canal de notificación que ha elegido.

    Por ejemplo, para el canal de notificación por correo electrónico, añada uno o más destinatarios y, de manera opcional, un huso horario.

7. Pulse **Guardar alerta**.



## Suprimir un valor preestablecido (plantilla de alerta)
{: #alerts_delete_preset}

Realice los pasos siguientes para suprimir un valor preestablecido:

1. En la interfaz de usuario web, seleccione el icono **Configuración** ![Icono Configuración](images/admin.png "Icono Administración").
2. Seleccione **Alertas**.
3. Pase el puntero del ratón sobre el botón *Editar* del valor preestablecido que desee suprimir. Aparecerá la opción *Suprimir*.
4. Seleccione **Suprimir**.
5. Confirme que desea suprimir el valor preestablecido. Pulse **Suprimir**.

## Desvincular una alerta específica de vista de una vista
{: #alerts_delete_view}

Realice los pasos siguientes para desvincular un valor preestablecido:

1. En la interfaz de usuario web, seleccione el icono **Configuración** ![Icono Configuración](images/admin.png "Icono Administración").
2. Seleccione **Alertas**.
3. Pase el puntero del ratón sobre el botón *Editar* de la alerta que desee suprimir. Aparecerá la opción *Suprimir*.
4. Seleccione **Desvincular**.
5. Confirme que desea suprimir la alerta. Pulse **Desvincular**.












