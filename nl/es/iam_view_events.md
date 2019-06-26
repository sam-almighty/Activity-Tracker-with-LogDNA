---

copyright:
  years: 2019
lastupdated: "2019-05-22"

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

 
# Cómo otorgar permisos de usuario a un usuario o ID de servicio
{: #iam_view_events}

{{site.data.keyword.iamlong}} (IAM) le permite autenticar usuarios de forma segura y controlar el acceso a todos los recursos de la nube de forma coherente en {{site.data.keyword.cloud_notm}}. Realice los pasos siguientes para otorgar a un usuario o ID de servicio los permisos mínimos para trabajar con el servicio {{site.data.keyword.at_full_notm}}: 
{:shortdesc}

## Requisitos previos
{: #iam_view_events_prereq}

El ID de usuario necesita **permisos de plataforma de administrador** para gestionar el servicio de
{{site.data.keyword.at_full_notm}}. Póngase en contacto con el administrador de la cuenta. El propietario de la cuenta puede otorgar a otro usuario acceso a la cuenta con fines de gestión del acceso de usuario y de gestión de recursos de la cuenta. [Más información](/docs/iam?topic=iam-userroles).



## Paso 1. Crear un grupo de acceso
{: #iam_view_events_step1}

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



## Paso 2. Añadir permisos para ver sucesos
{: #iam_view_events_step2}

Después de configurar el grupo, puede asignar una política de acceso común al grupo. 

Cualquier política que establezca para un grupo de acceso se aplicará a todas las entidades, usuarios e ID de servicio dentro del grupo. 
{: note}

Puede asignar la política utilizando la interfaz de usuario o a través de la línea de mandatos.

Para crear una política de grupo de acceso utilizando la CLI, puede utilizar el mandato [ibmcloud iam access-group-policy-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_policy_create).

```
ibmcloud iam access-group-policy-create GROUP_NAME {-f, --file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```
{: codeblock}

Al definir la política, necesita seleccionar un rol de plataforma y un rol de servicio:
* Los roles de gestión de plataforma cubren un rango de acciones, que incluyen la capacidad de crear y suprimir instancias, gestionar alias, enlaces y credenciales y gestionar el acceso. Los roles de plataforma son: administrador, editor, operador y visor. Los roles de gestión de plataforma también se aplican a los servicios de gestión de cuentas que permiten a los usuarios invitar a usuarios, gestionar ID de servicio, acceder a políticas, catalogar entradas y realizar un seguimiento de la facturación y del uso, en función de su rol asignado en un servicio de gestión de cuentas.
* Los roles de acceso al servicio definen la capacidad de un usuario o servicio de realizar acciones en una instancia de servicio. Los roles de acceso al servicio son el gestor, escritor y lector.

Para gestionar el servicio {{site.data.keyword.at_full_notm}}, un usuario necesita los roles siguientes:
* Rol de plataforma: **Visor**. 
* Rol de servicio: **Lector**. 
[Más información](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam#iam).



Realice los pasos siguientes para asignar una política a un grupo de acceso a través de la interfaz de usuario:

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Grupos de acceso**.
2. Seleccione el nombre del grupo al que desea asignar el acceso. 
3. Pulse **Políticas de acceso**.
4. Pulse **Asignar acceso**.
5. Otorgue los permisos. Elija una de estas opciones:


### Opción 1. Otorgar permisos en el servicio
{: #user_opt1}

Siga los pasos siguientes: 

1. Seleccione **Asignar acceso a recursos**.
2. Seleccione **IBM Cloud Activity Tracker with LogDNA**.
3. Seleccione **Todas las regiones actuales**.
4. Seleccione **Todas las instancias de servicio actuales**.
5. Seleccione el rol de **Visor** de la plataforma.
6. Seleccione el rol de servicio **Lector**.
7. Pulse **Asignar**.

### Opción 2. Otorgar permisos dentro del contexto de un grupo de recursos
{: #user_opt2}

Siga los pasos siguientes: 

1. Seleccione **Asignar acceso dentro de un grupo de recursos**.
2. Seleccione un grupo de recursos.
3. Si el usuario no tiene todavía un rol otorgado para el grupo de recursos seleccionado, elija un rol para el campo **Asignar acceso a un grupo de recursos**. 

    En función del rol que seleccione, el usuario puede ver el grupo de recursos en su panel de control, editar el nombre del grupo de recursos o gestionar el acceso de usuarios al grupo. 
    
    Puede seleccionar **Sin acceso** si desea que el usuario solo tenga acceso al servicio {{site.data.keyword.at_full_notm}} en el grupo de recursos.

4. Seleccione **IBM Cloud Activity Tracker with LogDNA**.
5. Seleccione el rol de **Visor** de la plataforma.
6. Seleccione el rol de servicio **Lector**.
7. Pulse **Asignar**.

### Opción 3. Otorgar permisos en una ubicación
{: #user_opt3}

Solo puede suministrar una instancia por ubicación. Por lo tanto, para otorgar permisos para ver sucesos en una región, realice los pasos siguientes: 

1. Seleccione **Asignar acceso a recursos**.
2. Seleccione **IBM Cloud Activity Tracker with LogDNA**.
3. Seleccione la instancia en la región en la que el usuario debe tener permiso para ver sucesos.
4. Seleccione el rol de **Visor** de la plataforma.
5. Seleccione el rol de servicio **Lector**.
6. Pulse **Asignar**.


## Paso 3. Añadir un usuario al grupo de acceso
{: #iam_view_events_step3}

Continúe para configurar el grupo añadiendo usuarios o ID de servicio.

### Añadir un usuario al grupo de acceso
{: #iam_manage_events_step3_user}

Realice los pasos siguientes para añadir un usuario:

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Grupos de acceso**.
2. Seleccione el nombre del grupo al que desea asignar el acceso. 
3. Pulse **Añadir usuarios** en el separador **Usuarios**.
4. Seleccione los usuarios de la lista que desea añadir y pulse **Añadir a grupo**.


### Añadir un ID de servicio al grupo de acceso
{: #iam_manage_events_step3_svcid}

Realice los pasos siguientes para añadir un ID de servicio:

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Grupos de acceso**.
2. Seleccione el nombre del grupo al que desea asignar el acceso. 
3. Pulse el separador **ID de servicio** y pulse **Añadir ID de servicio**.
4. Seleccione los ID de la lista que desea añadir y pulse **Añadir a grupo**.


