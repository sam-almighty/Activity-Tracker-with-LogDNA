---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, IAM events

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


# Sucesos de IAM
{: #at_events_iam}

Como agente de seguridad, auditor o gestor, puede utilizar el servicio {{site.data.keyword.at_full_notm}} para realizar un seguimiento de cómo interactúan los usuarios y las aplicaciones con el servicio {{site.data.keyword.iamlong}} (IAM) en {{site.data.keyword.cloud_notm}}. 
{:shortdesc}

El servicio {{site.data.keyword.at_full_notm}} registra actividades iniciadas por los usuarios que cambian el estado de un servicio en {{site.data.keyword.cloud_notm}}. Para empezar a supervisar las acciones del usuario, consulte [{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started). 

Un iniciador puede ser un usuario, un servicio o una aplicación.
{: tip}

## Gestión de sucesos de grupos de acceso
{: #at_events_iam_access}

En la tabla siguiente se muestran las acciones que generan un suceso:

| Acción | Descripción |
|----------|---------|
| `iam-groups.group.create`   | Se genera un suceso cuando un iniciador crea un grupo de acceso. | 
| `iam-groups.group.read`     | Se genera un suceso cuando un iniciador consulta información relacionada con grupos de acceso. |
| `iam-groups.group.update`   | Se genera un suceso cuando un iniciador actualiza un nombre de grupo o una descripción. |
| `iam-groups.group.delete`   | Se genera un suceso cuando un iniciador suprime un grupo de acceso. |
| `iam-groups.member.add`     | Se genera un suceso cuando un iniciador añade un miembro a un grupo de acceso. |
| `iam-groups.member.delete`  | Se genera un suceso cuando un iniciador elimina miembro de un grupo de acceso. |
| `iam-groups.member.read`    | Se genera un suceso cuando un iniciador comprueba la pertenencia de un miembro. |
| `iam-groups.rule.read`      | Se genera un suceso cuando un iniciador visualiza una regla en un grupo de acceso. |
| `iam-groups.rule.create`    | Se genera un suceso cuando un iniciador añade una regla a un grupo de acceso. |
| `iam-groups.rule.update`    | Se genera un suceso cuando un iniciador modifica el nombre de una regla. |
| `iam-groups.rule.delete`    | Se genera un suceso cuando un iniciador suprime una regla de un grupo de acceso. |
{: caption="Tabla 1. Acciones de gestión de grupos de acceso" caption-side="top"} 




## Visualización de sucesos
{: #at_events_iam_ui}

Los sucesos están disponibles en la región **EE.UU. sur**. 

Para ver estos sucesos, debe [suministrar una instancia](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision) del servicio {{site.data.keyword.at_full_notm}} en la región **EE. UU. sur**. A continuación, debe [abrir la interfaz de usuario de {{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2). 


