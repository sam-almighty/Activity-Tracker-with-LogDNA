---

copyright:
  years: 2019
lastupdated: "2019-05-25"

keywords: IBM Cloud, LogDNA, Activity Tracker, account events

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

# Sucesos de gestión de cuentas  
{: #at_events_acc_mgt}

Como agente de seguridad, auditor o gestor, puede utilizar el servicio {{site.data.keyword.at_full_notm}} para realizar un seguimiento de cómo interactúan los usuarios y las aplicaciones con la cuenta de {{site.data.keyword.cloud_notm}}. 
{:shortdesc}

El servicio {{site.data.keyword.at_full_notm}} registra actividades iniciadas por los usuarios que cambian el estado de un servicio en {{site.data.keyword.cloud_notm}}. Para empezar, consulte [{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started). 



## Sucesos para gestionar cuentas
{: #at_events_acc_mgt_account}

En la tabla siguiente se muestran las acciones que generan un suceso:

| Acción                               | Descripción |
|--------------------------------------|-------------|
| `billing.account.create`             | Se genera un suceso cuando suministra una cuenta tras asignar el ID de cuenta a la cuenta. |
| `billing.account.update`             | Se genera un suceso cuando se actualiza la información sobre la cuenta.  |
| `billing.account.active`             | Se genera un suceso cuando se verifica la cuenta, es decir, se genera un suceso cuando la cuenta pasa a estar activa. |
| `billing.account.subscription.create` | Se genera un suceso cuando se crea una <a href="/docs/account?topic=account-accounts#subscription-account">cuenta de suscripción</a>. |
{: caption="Tabla 1. Acciones que generan sucesos" caption-side="top"} 




## Sucesos para gestionar usuarios
{: #at_events_acc_mgt_users}

En la tabla siguiente se muestran las acciones que generan un suceso:

| Acción                               | Descripción |
|--------------------------------------|-------------|
| `user-management.user.create`        | Se genera un suceso cuando se envía una invitación a un usuario para que se una a una cuenta. |
| `user-management.user.active`        | Se genera un suceso cuando se activa el usuario en la cuenta. When the user verifies the email address, the event is generated. |
| `user-management.user.delete`        | Se genera un suceso cuando se elimina un usuario de la cuenta. |
{: caption="Tabla 2. Acciones que generan sucesos" caption-side="top"} 




## Sucesos para gestionar organizaciones
{: #at_events_acc_mgt_org}

En la tabla siguiente se muestran las acciones que generan un suceso:

| Acción                               | Descripción |
|--------------------------------------|-------------|
| `billing.account.org.create`         | Se genera un suceso cuando se añade una organización a la cuenta. |
{: caption="Tabla 3. Acciones que generan sucesos" caption-side="top"} 


## Sucesos para gestionar etiquetas
{: #at_events_acc_mgt_resources}

En la tabla siguiente se muestran las acciones que generan un suceso:

| Acción                               | Descripción |
|--------------------------------------|-------------|
| `ghost-tags.tag.attach-tag`          | Se genera un suceso al añadir una etiqueta a un recurso. |
| `ghost-tags.tag.detach-tag`          | Se genera un suceso al eliminar una etiqueta de un recurso.  |
{: caption="Tabla 4. Acciones que generan sucesos" caption-side="top"} 


## Dónde buscar los sucesos
{: #at_events_acc_mgt_ui}

Los sucesos están disponibles en la región **Frankfurt (eu-de)**. 

Para ver estos sucesos, debe [suministrar una instancia](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision) del servicio {{site.data.keyword.at_full_notm}} en la región **Frankfurt (eu-de)**. A continuación, debe [abrir la interfaz de usuario de {{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2). 












