---

copyright:
  years: 2019
lastupdated: "2019-05-21"

keywords: IBM Cloud, LogDNA, Activity Tracker, resource controller events

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

# Sucesos de instancia de servicio  
{: #at_events_rc}

Como agente de seguridad, auditor o gestor, puede utilizar el servicio {{site.data.keyword.at_full_notm}} para realizar un seguimiento de cómo interactúan los usuarios y las aplicaciones con los servicios de {{site.data.keyword.cloud_notm}}. 
{:shortdesc}

El servicio {{site.data.keyword.at_full_notm}} registra actividades iniciadas por los usuarios que cambian el estado de un servicio en {{site.data.keyword.cloud_notm}}. Para empezar a supervisar las acciones del usuario, consulte [{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started). 


## Sucesos para el suministro y la gestión de instancias de servicio
{: #rc_provision}

En la tabla siguiente se muestran las acciones que generan un suceso:

| Acción                         | Descripción |
|--------------------------------|---------|
| `service_name.instance.create` | Se genera un suceso cuando se suministra una instancia de servicio. |
| `service_name.instance.update` | Se genera un suceso cuando se cambia el nombre de una instancia de servicio o cuando se cambia el plan de servicio. |
| `service_name.instance.delete` | Se genera un suceso cuando se suprime una instancia de servicio. |
{: caption="Tabla 1. Acciones que generan sucesos" caption-side="top"} 


##  Sucesos para gestionar los alias que están asociados a una instancia de servicio
{: #rc_alias}

Un alias es una conexión entre su servicio gestionado por IAM dentro de un grupo de recursos y una aplicación dentro de una organización o un espacio.

En la tabla siguiente se muestran las acciones que generan un suceso:

| Acción                         | Descripción |
|--------------------------------|---------|
| `service_name.alias.create` | Se genera un suceso cuando se crea un alias para una instancia. |
| `service_name.alias.update` | Se genera un suceso cuando se actualiza un alias para una instancia. |
| `service_name.alias.delete` | Se genera un suceso cuando se suprime un alias para una instancia. |
{: caption="Tabla 2. Acciones que generan sucesos" caption-side="top"} 


##  Sucesos para gestionar las credenciales de servicio alias que están asociadas a una instancia de servicio
{: #rc_keys}

Una credencial de servicio proporciona la información necesaria para conectar una aplicación a una instancia de servicio. 

En la tabla siguiente se muestran las acciones que generan un suceso:

| Acción                         | Descripción |
|--------------------------------|---------|
| `service_name.key.create` | Se genera un suceso cuando se crea una clave de API para una instancia de servicio a través de la sección *Credenciales de servicio* de la interfaz de usuario de la instancia de servicio. |
| `service_name.key.delete` | Se genera un suceso cuando una clave de API asociada con una instancia de servicio se suprime desde la sección *Credenciales de servicio* de la interfaz de usuario de la instancia de servicio. |
{: caption="Tabla 3. Acciones que generan sucesos" caption-side="top"} 



##  Sucesos para enlazar y desenlazar una instancia de servicio con una app
{: #rc_bind}

En la tabla siguiente se muestran las acciones que generan un suceso:

| Acción                         | Descripción |
|--------------------------------|---------|
| `service_name.binding.create` | Se genera un suceso cuando se enlaza una instancia de servicio a una aplicación. |
| `service_name.binding.delete` | Se genera un suceso cuando se elimina el enlace de una instancia de servicio de una aplicación. |
{: caption="Tabla 4. Acciones que generan sucesos" caption-side="top"} 



## Dónde buscar los sucesos
{: #rc_ui}

Los sucesos están disponibles en la región **Frankfurt (eu-de)**. 

Para ver estos sucesos, debe [suministrar una instancia](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision) del servicio {{site.data.keyword.at_full_notm}} en la región **Frankfurt (eu-de)**. A continuación, debe [abrir la interfaz de usuario de {{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2). 



## Análisis de sucesos
{: #rc_analyze}

**Acción: service_name.instance.delete**

Cuando se suprime una instancia de servicio, tenga en cuenta la información siguiente:
* Se desencadenan automáticamente otras acciones para limpiar los permisos de IAM. Estas acciones eliminan políticas configuradas para los usuarios e ID de servicio de la cuenta para trabajar con la instancia de servicio. 
* El iniciador de estas acciones es un ID de servicio de {{site.data.keyword.IBM_notm}}.


Cuando la instancia de servicio que se suprime no tiene políticas de IAM configuradas para los usuarios e ID de servicio, los sucesos que se generan automáticamente para cualquier de estos recursos informan de un resultado de `failure` con un código de resultado de
`404`. El ejemplo siguiente muestra los sucesos generados cuando se suprime una instancia de servicio que no tiene políticas configuradas en la cuenta:

```
Apr 30 09:04:16 cloudcerts: delete instance Certificate Manager-v1
Apr 30 09:41:20 IAM Access Management: delete policy -failure
Apr 30 09:41:20 IAM Access Management: delete policy -failure
```
{: screen}



