---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, provision instance

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

# Suministro de una instancia
{: #provision}

Para poder supervisar y gestionar datos de sucesos con {{site.data.keyword.at_full_notm}}, primero debe suministrar una instancia del servicio en {{site.data.keyword.cloud_notm}}.
{:shortdesc}

Para suministrar una instancia de {{site.data.keyword.at_full_notm}} en una región de Cloud pública, debe seleccionar el plan de servicio asociado a la instancia, la región donde se recopilan los registros y el plan que determina el periodo de retención de los registros. Puede elegir periodos de retención de 7, 14 o 30 días.

Como alternativa, {{site.data.keyword.at_full_notm}} ofrece un plan `Lite` que puede utilizar para ver los sucesos a medida que pasan a través del sistema. Puede visualizar sucesos utilizando el seguimiento de sucesos. También puede diseñar filtros para preparar la actualización a un plan con un periodo de retención más largo. Este plan tiene un periodo de retención de 0 días.

Para suministrar una instancia de servicio, el ID de usuario debe tener permisos para suministrar un servicio en un grupo de recursos. [Más información](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam#groups).
{: tip}


## Suministro de una instancia a través del panel de control Observabilidad.
{: #provision_ui}

Para suministrar una instancia desde el panel de control Observabilidad en {{site.data.keyword.cloud_notm}}, realice los pasos siguientes:

1. [Inicie sesión en su cuenta de {{site.data.keyword.cloud_notm}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://cloud.ibm.com/login){:new_window}.

	Cuando inicia una sesión con su ID de usuario y su contraseña, se abre la interfaz de usuario de {{site.data.keyword.cloud_notm}}.

2. Vaya al icono de menú ![icono de menú](../../icons/icon_hamburger.svg). A continuación, seleccione **Observabilidad** para acceder al panel de control *Observabilidad*.

3. Seleccione **Activity Tracker** y, a continuación, pulse **Crear instancia**. 

4. Especifique un nombre para la instancia de servicio.

5. Seleccione la región donde tenga pensado suministrar la instancia.

6. Seleccione un grupo de recursos. 

    De forma predeterminada, se selecciona el grupo de recursos **predeterminado**.

    **Nota:** si no puede seleccionar un grupo de recursos, compruebe que tiene permisos de edición sobre el grupo de recursos donde desea suministrar la instancia.

7. Seleccione el plan de servicio `Lite`. 

    De forma predeterminada, se establece el plan Lite.

8. Pulse **Crear**.

Después de suministrar una instancia, se abre el panel de control *Activity Tracker*. 

A continuación, acceda a la interfaz de usuario web para gestionar sucesos en la cuenta. [Más información](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-view_events.md#view_events.md).



## Suministro de una instancia a través del catálogo
{: #provision_catalog}

Para suministrar una instancia de {{site.data.keyword.at_full_notm}} a través del catálogo de {{site.data.keyword.cloud_notm}}, realice los pasos siguientes:

1. [Inicie sesión en su cuenta de {{site.data.keyword.cloud_notm}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://cloud.ibm.com/login){:new_window}.

	Cuando inicia una sesión con su ID de usuario y su contraseña, se abre la interfaz de usuario de {{site.data.keyword.cloud_notm}}.

2. Pulse **Catálogo**. Se abrirá la lista de servicios disponibles en {{site.data.keyword.cloud_notm}}.

3. Para filtrar la lista de servicios que se visualiza, seleccione la categoría **Herramientas de desarrollador**.

4. Pulse el mosaico **{{site.data.keyword.at_full_notm}}**. 

5. Especifique un nombre para la instancia de servicio.

6. Seleccione un grupo de recursos. 

    De forma predeterminada, se selecciona el grupo de recursos **predeterminado**.

    **Nota:** si no puede seleccionar un grupo de recursos, compruebe que tiene permisos de edición sobre el grupo de recursos donde desea suministrar la instancia.

7. Seleccione el plan de servicio `Lite`. 

    De forma predeterminada, se establece el plan Lite.

8. Pulse **Crear**.

Después de suministrar una instancia, se abre el panel de control *Activity Tracker*. 

A continuación, acceda a la interfaz de usuario web para gestionar sucesos en la cuenta. [Más información](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).


## Suministro de una instancia a través de la CLI
{: #provision_cli}

Para suministrar una instancia de {{site.data.keyword.at_full_notm}} a través de la línea de mandatos, realice los pasos siguientes:

1. [Requisito previo] Instalación de la CLI de {{site.data.keyword.cloud_notm}}. [Más información](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli).

   Si la CLI está instalada, continúe en el paso siguiente.

2. Inicie una sesión en {{site.data.keyword.cloud_notm}} donde desea suministrar la instancia. Ejecute el siguiente mandato: [`ibmcloud login`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_login)

3. Establezca el grupo de recursos en el que desea suministrar la instancia. Ejecute el siguiente mandato: [`ibmcloud target`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_target)

    De forma predeterminada, está establecido el grupo de recursos `default`.

4. Cree la instancia. Ejecute el mandato [`ibmcloud resource service-instance-create`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_resource#ibmcloud_resource_service_instance_create):

    ```
    ibmcloud resource service-instance-create NAME logdnaat SERVICE_PLAN_NAME LOCATION
    ```
    {: codeblock}

    Donde

    * NAME es el nombre de la instancia

    * El valor *logdnaat* es el nombre del servicio {{site.data.keyword.at_full_notm}} en {{site.data.keyword.cloud_notm}}

    * SERVICE_PLAN_NAME es el tipo de plan. Los valores válidos son *lite*, *7-days*, *14-days* y *30-days*
    
    * LOCATION es la región donde se crea la instancia de LogDNA. Por ejemplo, un valor válido es *us-south*

    
Por ejemplo, para suministrar una instancia con el plan de retención de 7 días, ejecute el mandato siguiente:

```
ibmcloud resource service-instance-create logdna-instance-01 logdnaat 7-day us-south
```
{: codeblock}



