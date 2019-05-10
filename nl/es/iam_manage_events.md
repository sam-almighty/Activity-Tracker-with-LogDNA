---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, iam, manage user access, viewer

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

 
# Cómo otorgar permisos de administración a un usuario o ID de servicio
{: #iam_manage_events}

{{site.data.keyword.iamlong}} (IAM) le permite autenticar usuarios de forma segura y controlar el acceso a todos los recursos de la nube de forma coherente en {{site.data.keyword.cloud_notm}}. Realice los pasos siguientes para otorgar a un usuario o ID de servicio permisos de administración para trabajar con el servicio {{site.data.keyword.at_full_notm}}:
{:shortdesc}

Por ejemplo, como administrador del servicio, puede suministrar y eliminar instancias del servicio, otorgar a otros usuarios permisos para trabajar con el servicio, archivar registros en una instancia de {{site.data.keyword.cos_full_notm}} (COS), etc. [Más información](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam#iam).

## Paso 1. Crear un grupo de acceso
{: #ime_step1}

Realice los pasos siguientes para crear un grupo de acceso:

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Grupos de acceso**.
2. Pulse **Crear**.
3. Especifique un nombre y una descripción opcional para el grupo y pulse **Crear**.

Puede suprimir un grupo seleccionando la opción **Eliminar grupo**. Cuando elimina un grupo de la cuenta, también elimina todos los usuarios e ID de servicio del grupo y todo el acceso asignado al grupo.
{: note}

Para crear un grupo de acceso utilizando la CLI, puede utilizar el mandato [ibmcloud iam access-group-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_create).
```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION]
```
{: codeblock}




## Paso 2. Añadir permisos para gestionar sucesos
{: #ime_step2}

Después de configurar el grupo, puede asignar una política de acceso común al grupo. 

Cualquier política que establezca para un grupo de acceso se aplicará a todas las entidades, usuarios e ID de servicio dentro del grupo. 
{: note}

Puede asignar la política utilizando la interfaz de usuario o a través de la línea de mandatos.

Para crear una política de grupo de acceso utilizando la CLI, puede utilizar el mandato [ibmcloud iam access-group-policy-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_policy_create).

```
ibmcloud iam access-group-policy-create GROUP_NAME {-f, --file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```
{: codeblock}

Realice los pasos siguientes para asignar una política a un grupo de acceso a través de la interfaz de usuario:

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Grupos de acceso**.
2. Seleccione el nombre del grupo al que desea asignar el acceso. 
3. Pulse **Políticas de acceso**.
4. Pulse **Asignar acceso**.
5. Elija asignar acceso por recursos en un grupo de recursos, en recursos individuales disponibles en la cuenta o en servicios de gestión de la cuenta. Por ejemplo, puede elegir cualquiera de las opciones siguientes para otorgar a un usuario un rol de administrador para gestionar una instancia de {{site.data.keyword.at_full_notm}}:

### Opción 1. Otorgar permisos a un usuario para que pase a ser un administrador del servicio en la cuenta de {{site.data.keyword.cloud_notm}}
{: #admin_account_opt1}

Para otorgar a un usuario el rol de administrador para gestionar el servicio en la cuenta, el usuario debe tener una política de IAM para el servicio {{site.data.keyword.at_full_notm}} con el rol de **Administrador** de la plataforma. Debe asignar a este usuario acceso a un recurso individual de la cuenta. 

Siga los pasos siguientes para asignar a un usuario el rol de administrador sobre el servicio {{site.data.keyword.at_full_notm}} en la cuenta: 

1. Seleccione **Asignar acceso a recursos**.
2. Seleccione **IBM Cloud Activity Tracker with LogDNA**.
3. Seleccione **Todas las regiones actuales**.
4. Seleccione **Todas las instancias de servicio actuales**.
5. Seleccione el rol de **Administrador** de la plataforma.
6. Seleccione el rol de **Gestor** del servicio.
7. Pulse **Asignar**.

### Opción 2. Otorgar permisos a un usuario para que pase a ser un administrador del servicio dentro de un grupo de recursos
{: #admin_account_opt2}

Para otorgar a un usuario el rol de administrador para gestionar instancias dentro de un grupo de recursos en la cuenta, el usuario debe tener una política de IAM para el servicio {{site.data.keyword.at_full_notm}} con el rol de **Administrador** de la plataforma dentro del contexto del grupo de recursos. 

Siga los pasos siguientes para asignar a un usuario el rol de administrador sobre el servicio {{site.data.keyword.at_full_notm}} dentro del contexto de un grupo de recursos: 

1. Seleccione **Asignar acceso dentro de un grupo de recursos**.
2. Seleccione un grupo de recursos.
3. Si el usuario no tiene todavía un rol otorgado para el grupo de recursos seleccionado, elija un rol para el campo **Asignar acceso a un grupo de recursos**. 

    En función del rol que seleccione, el usuario puede ver el grupo de recursos en su panel de control, editar el nombre del grupo de recursos o gestionar el acceso de usuarios al grupo. 
    
    Puede seleccionar **Sin acceso** si desea que el usuario solo tenga acceso al servicio {{site.data.keyword.at_full_notm}} en el grupo de recursos.

4. Seleccione **IBM Cloud Activity Tracker with LogDNA**.
5. Seleccione el rol de **Administrador** de la plataforma.
6. Seleccione el rol de **Gestor** del servicio.
7. Pulse **Asignar**.

### Opción 3. Otorgar permisos a un usuario para que pase a ser un administrador de una instancia individual del servicio en {{site.data.keyword.cloud_notm}}
{: #admin_account_opt3}

Realice los pasos siguientes para asignar a un usuario el rol de administrador sobre una instancia del servicio {{site.data.keyword.at_full_notm}}: 

1. Seleccione **Asignar acceso a recursos**.
2. Seleccione **IBM Cloud Activity Tracker with LogDNA**.
3. Seleccione la instancia.
4. Seleccione el rol de **Administrador** de la plataforma.
5. Seleccione el rol de **Gestor** del servicio.
6. Pulse **Asignar**.



## Paso 3. Añadir un usuario o ID de servicio al grupo de acceso
{: #ime_step3}

Continúe para configurar el grupo añadiendo usuarios o ID de servicio.

### Añadir un usuario al grupo de acceso
{: #ime_step3_user}

Realice los pasos siguientes para añadir un usuario:

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Grupos de acceso**.
2. Seleccione el nombre del grupo al que desea asignar el acceso. 
3. Pulse **Añadir usuarios** en el separador **Usuarios**.
4. Seleccione los usuarios de la lista que desea añadir y pulse **Añadir a grupo**.


### Añadir un ID de servicio al grupo de acceso
{: #ime_step3_svcid}

Realice los pasos siguientes para añadir un ID de servicio:

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Grupos de acceso**.
2. Seleccione el nombre del grupo al que desea asignar el acceso. 
3. Pulse el separador **ID de servicio** y pulse **Añadir ID de servicio**.
4. Seleccione los ID de la lista que desea añadir y pulse **Añadir a grupo**.




