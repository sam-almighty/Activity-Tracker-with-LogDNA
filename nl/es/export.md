---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, export

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

 
# Exportación de sucesos
{: #export}

Puede exportar datos en formato JSONL de una instancia de {{site.data.keyword.at_full_notm}} a un archivo local. Puede exportar registros mediante programación o desde la interfaz de usuario web de IBM Log Analysis. 
{:shortdesc}

Tenga en cuenta la información siguiente al exportar datos de registro:
* Exporte un conjunto de entradas de sucesos. Para definir el conjunto de datos que desea exportar, puede aplicar filtros y búsquedas. También puede especificar el intervalo de tiempo. 
* Desde la interfaz de usuario web, al exportar sucesos, recibe un correo electrónico enviado a su dirección de correo electrónico, con un enlace a un archivo comprimido que incluye los datos. Para obtener los datos, debe pulsar en enlace y descargar el archivo comprimido.
* Al exportar sucesos mediante programación, puede elegir enviar un correo electrónico o transmitir los sucesos a su terminal.
* El archivo comprimido que contiene los datos que desea exportar está disponible durante un máximo de 48 horas. 
* El número máximo de líneas que puede exportar es de 10 000.



## Requisitos previos
{: #export_prereqs}

Antes de empezar, compruebe que el ID de usuario tenga permisos para iniciar la interfaz de usuario web y para ver los sucesos. A continuación, [vaya a la interfaz de usuario web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).

**Nota:** debe ser un administrador del servicio {{site.data.keyword.at_full_notm}} o un administrador de la instancia de {{site.data.keyword.at_full_notm}} o debe tener permisos de IAM de la cuenta para gestionar políticas.

En la tabla siguiente se muestran las políticas mínimas que debe tener un usuario para poder iniciar la interfaz de usuario web de {{site.data.keyword.at_full_notm}} y visualizar sucesos:

| Rol                      | Permiso otorgado            |
|---------------------------|-------------------------------|  
| Rol de la plataforma: `Visor`     | Permite al usuario ver la lista de instancias de servicio en el panel de control Observabilidad. |
| Rol de servicio: `Lector`      | Permite que el usuario pueda iniciar la interfaz de usuario web y ver sucesos en la interfaz de usuario web.  |
{: caption="Tabla 1. Políticas de IAM" caption-side="top"} 

Para obtener más información sobre cómo configurar estas políticas para un usuario, consulte [Cómo otorgar permisos de usuario a un usuario o ID de servicio](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events).

**Debe tener un plan de servicio de pago** para el servicio {{site.data.keyword.at_full_notm}}. [Más información](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan#service_plan). 



## Paso 1. Acceder a la interfaz de usuario web
{: #export_step1}

[Vaya a la interfaz de usuario web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).


## Paso 2. Crear una vista
{: #export_step2}

[Cree una vista](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views.md#views.md).


## Paso 3. Exportar datos
{: #export_step3}

Elija una de las siguientes opciones para exportar sucesos:

### Opción 1. Exportación de sucesos desde la interfaz de usuario web
{: #export_ui}

Realice los pasos siguientes para exportar datos:

1. Pulse el icono **Vistas** ![Icono Configuración](images/views.png).
2. Seleccione **Todo** o una vista.
3. Aplique un marco de tiempo, filtros y criterios de búsqueda hasta que vea las entradas que desee exportar.
4. Pulse **Vista sin guardar** si está comenzando a partir de la vista **Todo**. Pulse sobre el nombre de la vista si ha seleccionado una vista en el paso anterior.
5. Seleccione **Exportar líneas**. Se abrirá una nueva ventana.
6. Compruebe el intervalo de tiempo. Si necesita cambiarlo, pulse sobre el intervalo de tiempo predefinido en el campo *Cambiar el intervalo de tiempo para la exportación*.
7. Seleccione **Preferir líneas más nuevas** o **Preferir líneas más antiguas** en caso de que la solicitud de exportación sobrepase el límite de líneas.
8. Compruebe el correo electrónico. Recibirá un correo electrónico de **LogDNA** con un enlace para descargar las líneas exportadas.


### Opción 2. Exportación de sucesos mediante programación utilizando la API
{: #export_api}

Realice los pasos siguientes para exportar sucesos mediante programación:

1. Genere una clave de servicio. 

    **Nota:** debe tener el rol **gestor** para el servicio o la instancia de {{site.data.keyword.at_full_notm}} para poder completar este paso.

    1. Inicie la interfaz de usuario web de {{site.data.keyword.at_full_notm}}. Para obtener más información, consulte [Acceder a la interfaz de usuario web de {{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2).

    2. Seleccione el icono **Configuración** ![Icono Configuración](images/admin.png). A continuación, seleccione **Organización**. 

    3. Seleccione **Claves de API**.

        Puede ver las claves de servicio que ha creado. 

    4. Pulse **Generar clave de servicio**.

        Se añade una nueva clave a la lista. Copie esta clave.

2. Exporte sucesos. Ejecute el siguiente mandato cURL:

    ```
    curl "ENDPOINT/v1/export?QUERY_PARAMETERS" -u SERVICE_KEY:
    ```
    {: codeblock}

    Donde 

    * ENDPOINT representa el punto de entrada al servicio. Cada región tiene un URL diferente. [Más información](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-endpoints#endpoints).
    * QUERY_PARAMETERS son parámetros que definen los criterios de filtro que se aplican a la solicitud de exportación.
    * SERVICE_KEY es la clave de servicio que ha creado en el paso anterior.

En la tabla siguiente se muestran los parámetros de consulta que puede establecer:

| Parámetro de consulta | Tipo       | Estado     | Descripción |
|-----------|------------|------------|-------------|
| `from`      | `int32`      | Obligatorio   | Hora de inicio. Establecer como indicación de fecha y hora de UNIX en segundos o milisegundos. |
| `to`        | `int32`      | Obligatorio   | Hora de finalización. Establecer como indicación de fecha y hora de UNIX en segundos o milisegundos.    |
| `size`      | `string`     | Opcional   | Número de líneas de registro a incluir en la exportación.  | 
| `hosts`     | `string`     | Opcional   | Lista de hosts separados por comas. |
| `apps`      | `string`     | Opcional   | Lista de aplicaciones separadas por comas. |
| `levels`    | `string`     | Opcional   | Lista de niveles de registro separados por comas. |
| `query`     | `string`     | Opcional   | Consulta de búsqueda. Para obtener más información, consulte [Buscar en registros](/docs/services/Log-Analysis-with-LogDNA?topic=LogDNA-view_logs#view_logs_step6). |
| `prefer`    | `string`     | Opcional   | Define las líneas de registro que desea exportar. Los valores válidos son `head`, primeras líneas de registro, y `tail`, últimas líneas de registro. Si no se especifica, el valor predeterminado será tail.  |
| `email`     | `string`     | Opcional   | Especifica el correo electrónico con el enlace descargable de la exportación. De forma predeterminada, se transmiten las líneas de registro.|
| `emailSubject` | `string`     | Opcional   | Se utiliza para establecer el asunto del correo electrónico. </br>Utilice `%20` para representar un espacio. Un valor de ejemplo es `Export%20logs`. |
{: caption="Parámetros de consulta" caption-side="top"} 

Por ejemplo, para transmitir sucesos en el terminal, puede ejecutar el mandato siguiente:

```
curl "https://api.us-south.logging.cloud.ibm.com/v1/export?to=$(date +%s)000&from=$(($(date +%s)-86400))000" -u e08c0c759663491880b0d61712346789:
```
{: codeblock}

Para enviar un correo electrónico con el enlace para descargar los sucesos especificados en la exportación, puede ejecutar el mandato siguiente:

```
curl "https://api.us-south.logging.cloud.ibm.com/v1/export?to=$(date +%s)000&from=$(($(date +%s)-86400))000&email=joe@ibm.com" -u e08c0c759663491880b0d61712346789:
```
{: codeblock}


Para enviar un correo electrónico con un asunto personalizado, puede ejecutar el mandato siguiente:

```
curl "https://api.us-south.logging.cloud.ibm.com/v1/export?to=$(date +%s)000&from=$(($(date +%s)-86400))000&email=joe@ibm.com&emailSubject=Export%20test" -u e08c0c759663491880b0d61712346789:
```
{: codeblock}

