---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, delete instance

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

# Eliminación de una instancia
{: #remove}

Puede eliminar una instancia del servicio {{site.data.keyword.at_full_notm}} desde la interfaz de usuario de {{site.data.keyword.cloud_notm}} o a través de la línea de mandatos.
{:shortdesc}



## Eliminación de una instancia mediante la interfaz de usuario de {{site.data.keyword.cloud_notm}}
{: #remove_ui}

Para eliminar una instancia de {{site.data.keyword.at_full_notm}} mediante la interfaz de usuario de {{site.data.keyword.cloud_notm}}, siga los pasos siguientes:

1. [Inicie sesión en su cuenta de {{site.data.keyword.cloud_notm}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://cloud.ibm.com/login){:new_window}.

	Cuando inicia una sesión con su ID de usuario y su contraseña, se abre la interfaz de usuario de {{site.data.keyword.cloud_notm}}.

2. Vaya al icono de menú ![Icono de menú](../../icons/icon_hamburger.svg) &gt; **Observabilidad** para acceder al Panel de control *Observabilidad*.

3. Seleccione **Activity Tracker**. Se mostrará la lista de instancias.

4. Seleccione la instancia que desea suprimir.

5. En el menú *Acción*, seleccione **Eliminar**.

A continuación, elimine los permisos que se hayan otorgado a los usuarios para trabajar con la instancia que ha suprimir.

## Eliminación de una instancia mediante la CLI
{: #remove_cli}

Para eliminar una instancia de {{site.data.keyword.at_full_notm}} mediante la línea de mandatos, siga los pasos siguientes:

1. [Requisito previo] Instalación de la CLI de {{site.data.keyword.cloud_notm}}.

   Para obtener más información, consulte [Instalación de la CLI de {{site.data.keyword.cloud_notm}}](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli).

   Si la CLI está instalada, continúe en el paso siguiente.

2. Inicie una sesión en {{site.data.keyword.cloud_notm}} donde desea suministrar la instancia. Ejecute el siguiente mandato: [`ibmcloud login`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_login)

3. Establezca el grupo de recursos en el que se ha suministrado la instancia. Ejecute el siguiente mandato: [`ibmcloud target`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_target)

    De forma predeterminada, está establecido el grupo de recursos *default*.

4. Elimine la instancia. Ejecute el mandato [`ibmcloud resource service-instance-delete`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_resource#ibmcloud_resource_service_instance_delete):

    ```
    ibmcloud resource service-instance-delete NAME 
    ```
    {: codeblock}

    Donde NAME es el nombre de la instancia

    Para mostrar una lista de todas las instancias disponibles en el grupo de recursos donde ha iniciado sesión, ejecute el mandato siguiente:

    ```
    ibmcloud resource service-instances
    ```
    {: codeblock}
    
    
Por ejemplo, para eliminar una instancia, ejecute el mandato siguiente:

```
ibmcloud resource service-instance-delete logdna-instance-01
```
{: codeblock}

A continuación, elimine los permisos que se hayan otorgado a los usuarios para trabajar con la instancia que ha suprimir.


