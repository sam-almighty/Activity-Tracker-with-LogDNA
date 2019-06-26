---

copyright:
  years: 2019
lastupdated: "2019-06-03"

keywords: IBM Cloud, LogDNA, Activity Tracker, monitor events

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


# Supervisión de la actividad en la cuenta
{: #monitor_events}

Puede supervisar la actividad de su cuenta a través de la interfaz de usuario web de
{{site.data.keyword.at_full_notm}}. También puede exportar conjuntos de sucesos para analizarlos en un contexto distinto.
{:shortdesc}

Hay una instancia del servicio {{site.data.keyword.at_full_notm}} por ubicación. Por lo tanto, para supervisar la actividad de su cuenta, es posible que necesite ver y analizar los sucesos a través de diferentes instancias de {{site.data.keyword.at_full_notm}}. 

En {{site.data.keyword.cloud_notm}}, puede pulsar el icono **Menú** ![Icono Menú](../icons/icon_hamburger.svg) > **Observabilidad** > **Activity Tracker** para ver el panel de control donde aparecen todas las instancias suministradas en la cuenta. 
{: tip}

Para ver los sucesos, debe [iniciar la interfaz de usuario web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch) en la ubicación donde estén disponibles los sucesos. A continuación, puede trabajar con vistas para supervisar dichos sucesos. Puede ver los sucesos en su hora local.

Puede seleccionar los sucesos mostrados a través de una vista mediante la aplicación de una indicación de fecha y hora, una consulta de búsqueda, o ambas.

* Puede aplicar una consulta de búsqueda y guardarla como una vista personalizada. 
* Puede aplicar una indicación de fecha y hora para saltar a una hora específica en el registro de sucesos. 

Al aplicar una consulta de búsqueda, puede guardar dicha vista para reutilizarla más adelante. No obstante, las indicaciones de fecha y hora no se guardarán.

Tenga en cuenta que las instancias pueden tener distintos planes de servicio y, como consecuencia, distintos periodos de retención de datos que determinan el número de días que los datos están disponibles para su búsqueda a través de la interfaz de usuario web. Solo puede supervisar sucesos que estén dentro del periodo de retención. Los distintos [planes de servicio](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan) tienen distintos periodos de retención.


## Supervisión de sucesos globales y basados en ubicación
{: #mon_def_event_type}

Los sucesos se pueden clasificar como globales o como basados en ubicación. El tipo de suceso determina dónde debe supervisar los sucesos.

El tema común para los sucesos globales es una ubicación única sincronizada donde los administradores pueden supervisar determinados tipos de actividad en Cloud. Por otra parte, los sucesos basados en ubicación siguen siendo locales para la ubicación donde se aloja un servicio de nube suscrito.
{: note}

### Sucesos globales
{: #mon_def_global}

Los **sucesos globales** informan sobre la actividad de la cuenta que está relacionada con los datos y recursos que normalmente se sincronizan en todas las regiones.
{: note}

Los servicios con los que interactúan los usuarios se integran en el núcleo de la experiencia global de {{site.data.keyword.cloud_notm}}.

El dominio global se establece en **Frankfurt**. Los sucesos globales se capturan y se establecen como disponibles a través de la instancia de {{site.data.keyword.at_full_notm}} configurada en Frankfurt.

Por ejemplo, cuando un administrador de la cuenta invita a usuarios a que se unan a la cuenta, pueden hacerlo desde cualquier ubicación de Cloud. Pueden invitar a un usuario que esté ubicado en Frankfurt y otorgarle permisos para trabajar con un servicio suministrado en Dallas. ¿A dónde debe ir el suceso? La respuesta es un dominio global independiente del origen o de la ubicación, y donde se sincronice la información en todas las regiones.
    
Como otro ejemplo más, los sucesos de controlador de recursos también se consideran sucesos globales en IBM Cloud. Estos sucesos informan sobre el suministro y la supresión de instancias de servicio en Cloud. Aunque una instancia de servicio se crea en una ubicación específica, las acciones de controlador de recursos se notifican como sucesos globales para ofrecer una vista única de todas las instancias de servicio suministradas en la cuenta.


### Sucesos basados en ubicación
{: #mon_def_location}

Los **sucesos basados en ubicación** informan sobre la actividad de la cuenta generada por los servicios de
{{site.data.keyword.cloud_notm}} que se alojan dentro de una ubicación de un centro de datos de
{{site.data.keyword.IBM_notm}}, como Dallas o Frankfurt. 
{: note}


Cuando los clientes y aplicaciones interactúan con los servicios de nube alojados dentro de una ubicación, se capturan sucesos basados en ubicación y se establecen como disponibles a través de la instancia de
{{site.data.keyword.at_full_notm}} configurada en dicha ubicación. Puede ver estos sucesos [iniciando la interfaz de usuario web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch) en dicha ubicación.
    
Los sucesos basados en ubicación mantienen la ubicación de los datos en los servicios que se ejecutan en dicha ubicación de Cloud.

Por ejemplo, si suministra el servicio {{site.data.keyword.cloudcerts_short}} en la ubicación de Frankfurt, los sucesos de dicha instancia se enviarán a la instancia de {{site.data.keyword.at_full_notm}} que se suministre en Frankfurt. Si suministra el servicio
{{site.data.keyword.cloudcerts_short}} en la ubicación de Dallas, los sucesos de dicha instancia se enviarán a la instancia de
{{site.data.keyword.at_full_notm}} que se suministre en Dallas. En ambos casos, los sucesos siguen siendo locales para la región y la ubicación del servicio de Cloud suscrito.




## Supervisión de sucesos a través de la vista predeterminada
{: #mon_def_view}

La vista predeterminada se denomina **Todo**. 

Tan pronto como abra la interfaz de usuario web en una ubicación, esta será la vista que utilice. 

Todos los sucesos de la instancia se muestran a través de esta vista.

Para obtener información sobre cómo ver sucesos a través de esta vista, consulte [Visualización de sucesos](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-view_events#view_events_step1).

## Supervisión de sucesos a través de vistas personalizadas
{: #mon_cus_view}

Es posible que desee supervisar un conjunto de sucesos de su cuenta. Para analizar un subconjunto de sucesos, puede crear vistas personalizadas. 

Para crear una vista personalizada, debe aplicar una consulta de búsqueda que defina qué sucesos se van a mostrar a través de la vista. [Más información](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-view_events#view_events_step2).

Puede [adjuntar alertas](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-alerts) a una vista personalizada. 

Puede [exportar datos](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-export) de una vista personalizada. 

Puede [renombrar, añadir o modificar la descripción de una vista](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_step5). 

Puede [aplicar una plantilla de línea](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_step4) a una vista para personalizar cómo se muestran los datos. 

Puede organizar vistas agrupándolas en **categorías*.


## Supervisión de sucesos aplicando un periodo de tiempo
{: #mon_time_view}

Es posible que desee ver los sucesos dentro de un periodo de tiempo específico.

Puede seleccionar los sucesos que se muestran a través de una vista [aplicando un periodo de tiempo](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-view_events#view_events_step3).

Puede aplicar una indicación de fecha y hora especificando una hora absoluta, una hora relativa o un intervalo de tiempo.

* Una hora absoluta especifica un punto preciso en el tiempo en el registro de sucesos, como `20 de mayo a las 7:00pm`.
    
* Una hora relativa especifica un periodo de tiempo que no es preciso, como `Hace 2 días`.

* Un intervalo de tiempo especifica un intervalo en el tiempo, como `Desde ayer a las 10am hasta ayer a las 11am`.



## Configuración de alertas
{: #mon_alerts}

Existen casos de ejemplo en los que es posible que desee recibir una notificación si se generan sucesos específicos en la cuenta. Por ejemplo, es posible que desee que se le notifique si el número de acciones que fallan sobrepasa un umbral especificado. 

A través de la interfaz de usuario web de {{site.data.keyword.at_full_notm}}, puede aplicar consultas de búsqueda para definir qué sucesos se visualizan a través de una vista personalizada. A continuación, puede adjuntar una alerta a dicha vista para que se le notifique cuando se produzca una condición. Se mostrará un icono de campana con la vista para indicar que esta vista tiene una alerta añadida.

* Puede [adjuntar una alerta](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-alerts#alerts_step4) por vista.
* Puede configurar condiciones basadas en el número de líneas de sucesos que satisfacen la consulta de búsqueda en la vista, en la frecuencia temporal, o en ambas.
* Puede definir varios canales de notificación para una alerta. Para obtener información sobre los canales admitidos, consulte
[Canales de notificación de alertas](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-channels).
* Puede [definir un
valor preestablecido](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-alerts#alerts_step3). Un valor preestablecido es una plantilla de alerta que puede adjuntar a cualquier número de vistas. Puede utilizar valores preestablecidos para definir plantillas que pueden reutilizar los usuarios al adjuntar una alerta a una vista. 
* Puede silenciar alertas. 
* Puede [quitar una alerta](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-alerts#alerts_delete_view) de una vista. 


### Tipos de alerta
{: #mon_alerts_types}

Puede configurar los tipos de alertas siguientes:

* **Alerta de presencia**: puede utilizar este tipo de alerta para recibir una notificación cuando el número de sucesos que se muestran en una vista sea mayor que el esperado. 
* **Alerta de ausencia**: puede utilizar este tipo de alerta para recibir una notificación cuando el número de sucesos que se muestran en una vista sea menor que el esperado, o no haya ninguno. 

Por ejemplo, es posible que tenga una vista que muestre sucesos que informan sobre la supresión de instancias de servicio en su cuenta. No espera la supresión de las instancias de servicio. Puede configurar una *alerta de presencia** que desencadene una alerta cuando se muestren uno o más sucesos en la vista.

La alerta de ausencia se habilita después de que un suceso aparezca en la vista.
{: note}


### Condiciones de alerta
{: #mon_alerts_conditions}

Puede configurar cualquiera de las condiciones siguientes para una alerta:

* **Frecuencia**: establezca esta condición para especificar la frecuencia con la que se desencadena una alerta. Los valores válidos son: 30 segundos, 1 minuto, 5 minutos, 15 minutos, 30 minutos, 1 hora, 6 horas, 12 horas, 24 horas
* **Contador de líneas de sucesos**: establezca esta condición para especificar el número de líneas de sucesos que coinciden con los criterios de filtrado y búsqueda de la vista. Cuando se alcanza el número de líneas de sucesos, se desencadena una alerta.

Puede decidir si deben comprobarse ambas condiciones o solo una de ellas. Si se establecen ambas condiciones, se desencadena una alerta cuando se alcanza cualquiera de los umbrales. 

Si establece el *contador de líneas de sucesos* para que sea la única condición que desencadene una alerta, tenga en cuenta que la frecuencia establecida al configurar la condición determina el tiempo que tarda en restablecerse una condición de alerta después de que se desencadene la alerta.
{: note}

Por ejemplo, puede configurar una alerta que se desencadene después de 30 segundos, o cuando se recopilen 100 líneas de sucesos que coincidan con los criterios de filtrado y de búsqueda de la vista.



## Exportación de sucesos
{: #mon_export}

Es posible que necesite acceder a un conjunto de sucesos fuera de la interfaz de usuario web para investigar un problema con más detalle. 

Puede exportar datos en formato JSONL de una instancia de {{site.data.keyword.at_full_notm}} a un archivo local. 

Puede exportar sucesos a través de una vista en la interfaz de usuario web, o mediante programación utilizando una API REST.

Tenga en cuenta la información siguiente al exportar sucesos:
* Exporte un conjunto de entradas de sucesos. 
* Para definir el conjunto de datos que desea exportar, puede aplicar filtros y búsquedas. También puede especificar el intervalo de tiempo. 
* El número máximo de líneas que puede exportar es de 20 000.

### Mediante la API REST
{: #mon_export_api}

Puede exportar sucesos mediante programación utilizando la API REST LogDNA. [Más información](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-export#export_api).

Al exportar sucesos mediante programación, tenga en cuenta la información siguiente:

* Puede elegir enviar un correo electrónico o transmitir los sucesos a su terminal.
* Debe utilizar una clave de servicio que se utiliza para pasar las credenciales que se deben usar al realizar una llamada de exportación a la API REST. 

    Debe tener el rol de **gestor** para el servicio o la instancia de {{site.data.keyword.at_full_notm}} para ver y generar claves de servicio en la interfaz de usuario web.


### A través de una vista en la interfaz de usuario web
{: #mon_export_ui}

Puede exportar sucesos a través de una vista en la interfaz de usuario web. 

En la interfaz de usuario web, puede seleccionar una vista que muestre los datos que desea exportar. Para esta vista, debe elegir la tarea para **Exportar líneas**. Debe especificar un intervalo de tiempo y si se deben exportar o no las líneas más nuevas o más antiguas. A continuación, puede solicitar la exportación. 

Tras enviar una solicitud, recibirá un correo electrónico enviado a su dirección de correo electrónico, con un enlace a un archivo comprimido que incluye los datos. 
* Para obtener los datos, debe pulsar en enlace y descargar el archivo comprimido. 
* El archivo comprimido que contiene los datos que desea exportar está disponible durante un máximo de 48 horas. 

[Obtenga más información sobre cómo exportar sucesos a través de la interfaz de usuario web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-export#export_ui).








