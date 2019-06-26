---

copyright:
  years: 2019
lastupdated: "2019-06-03"

keywords: IBM Cloud, LogDNA, Activity Tracker, search, filter, events

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


# Creación de vistas personalizadas
{: #views}

A través de la interfaz de usuario web de {{site.data.keyword.at_full_notm}}, puede aplicar criterios de búsqueda y filtrado para definir qué sucesos se visualizan a través de una vista personalizada.
{:shortdesc}


## Requisitos previos
{: #views_prereqs}

Antes de empezar, compruebe que el ID de usuario tenga permisos para iniciar la interfaz de usuario web y para ver los sucesos. En la tabla siguiente se muestran los roles mínimos que debe tener un usuario para poder iniciar la interfaz de usuario web de {{site.data.keyword.at_full_notm}} y visualizar sucesos:

| Rol                      | Permiso otorgado            |
|---------------------------|-------------------------------|  
| Rol de la plataforma: `Visor`     | Permite al usuario ver la lista de instancias de servicio en el panel de control Observabilidad. |
| Rol de servicio: `Lector`      | Permite que el usuario pueda iniciar la interfaz de usuario web y ver sucesos en la interfaz de usuario web.  |
{: caption="Tabla 1. Roles de IAM" caption-side="top"} 

Para obtener más información sobre cómo configurar las políticas para un usuario, consulte [Cómo otorgar permisos de usuario a un usuario o ID de servicio](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events).



## Paso 1. Acceder a la interfaz de usuario web y seleccionar una vista
{: #views_step1}

Siga los pasos siguientes:

1. [Vaya a la interfaz de usuario web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).
2. Pulse el icono **Vistas** ![Icono Configuración](images/views.png).
3. Seleccione **Todo** o una vista. 


## Paso 2. Seleccionar el conjunto de sucesos a mostrar a través de una vista aplicando una consulta de búsqueda
{: #views_step2}

Para buscar sucesos específicos, puede aplicar una consulta de búsqueda. 

* Puede realizar búsquedas simples (búsqueda de series de un solo término), búsquedas compuestas (varios términos de búsqueda y operadores), búsquedas de campo si la línea de registro se puede analizar, y otras. Para obtener más información, consulte [Cómo buscar en los registros en documentos LogDNA ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://docs.logdna.com/docs/search){:new_window}.
* Los operadores AND y OR distinguen entre mayúsculas y minúsculas y se deben poner en mayúsculas.

Solo puede buscar sucesos durante el número de días especificado a través del plan de servicio de la instancia.
{: important}


Siga los pasos siguientes:
1. Especifique una consulta de búsqueda. 
2. Pulse **Intro**. 

A aplicar una consulta, observará que el nombre de la vista cambia a **Vista sin guardar**.


### Consulta de los sucesos generados por un servicio
{: #views_step1_1}

Para filtrar los sucesos de un servicio específico, necesita especificar la consulta siguiente:

```
_supertenant:SERVICENAME
```
{: codeblock}

Donde `SERVICENAME` es el nombre del servicio en {{site.data.keyword.cloud_notm}}.

En la tabla siguiente se muestran los servicios principales:

| Sucesos generados por               | Valor                         | Consulta de ejemplo                     |
|--------------------------------------------|-------------------------------|----------------------------------|
| [Servicio de gestión de acceso de IAM](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_policies)  | `iam-am`  | `_supertenant:iam-am`    |
| [Servicio de identidad de IAM](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_login)   | `iam-identity`    | `_supertenant:iam-identity`  |
| [Servicio de grupos de acceso de IAM](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_access)   | `iam-groups`  | `_supertenant:iam-groups`     |
| [Servicio de controlador de recursos](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-cloud_services#platform_core_integrated)   | `BSS`  | `_supertenant:BSS`  |            
{: caption="Tabla 2. Consulta por nombre de servicio" caption-side="top"}

### Consulta de conjuntos de sucesos generados por un servicio
{: #views_step1_2}

Cuando un servicio genera distintos tipos de sucesos, puede especificar la consulta siguiente:

```
_supertenant:SERVICENAME [(action TYPEOFACTION)] 
```
{: codeblock}

Donde 

* `SERVICENAME` es el nombre del servicio en {{site.data.keyword.cloud_notm}}
* `TYPEOFACTION` es una consulta compuesta donde puede utilizar operadores AND y OR, así como `-` para excluir datos. Tenga en cuenta que los operadores `AND` y `OR` distinguen entre mayúsculas y minúsculas y deben ir en mayúsculas.


En la tabla siguiente se muestran ejemplos de cómo consultar un grupo de sucesos generado por un servicio:

| Sucesos generados por               | Tipo de sucesos     | Consulta de ejemplo                     |
|--------------------------------------------|--------------------|---------------------------------|
| `Servicio de identidad de IAM`                     | [Sucesos de inicio de sesión](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_login) | `_supertenant:iam-identity (action login)`  |
| `Servicio de identidad de IAM`                     | [Sucesos de clave de API](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_apikeys) | `_supertenant:iam-identity (action user-apikey) -(action login)`  |
| `Servicio de identidad de IAM`                     | [Sucesos de ID de servicio de cuenta](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_serviceids) | `_supertenant:iam-identity (action account-serviceid)`  |
| `Controlador de recursos`                      | [Suministro y gestión de instancias de servicio](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#rc_provision)   | `_supertenant:BSS (action instance)`  | 
| `Controlador de recursos`                      | [Gestión de usuarios de la cuenta](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_acc_mgt#at_events_acc_mgt_users)   |  `_supertenant:BSS (action user-management.user)`  |                   |
{: caption="Tabla 3. Ejemplos de consultas más complejas" caption-side="top"}


### Consulta de sucesos que tienen una acción específica
{: #views_step1_3}

Cada suceso tiene un campo **action** que informa acerca de la acción que ha desencadenado el suceso. Puede especificar la consulta siguiente para buscar todos los sucesos que tengan la misma acción:

```
action ACTIONVALUE
```
{: codeblock}

Donde `ACTIONVALUE` es el valor del campo de acción o parte del valor.

En la tabla siguiente se muestran ejemplos de consultas de distintas acciones:

| Acción                 | Consulta de ejemplo                     |
|------------------------|----------------------------------|
| Suministrar un servicio    | `action instance.create`         |
| Eliminar una instancia     | `action instance.delete`         |
| Añadir un usuario             | `action user-management.user.create` |
{: caption="Tabla 4. Ejemplos de consultas por tipo de acción" caption-side="top"}



### Consulta de sucesos cuya acción falla
{: #views_step1_4}

Cuando una acción solicitada falla, el campo **outcome** se establece en
**failure**. Puede especificar la consulta siguiente para buscar este tipo de sucesos:

```
outcome failure
```
{: codeblock}


### Consulta por gravedad de suceso
{: #views_step1_5}

Cada suceso tiene el campo **severity** (gravedad) que define el nivel de amenaza que puede tener una acción en la nube. 

Los valores válidos son *normal*, *warning* y *critical*. 
* **Normal** está definido para las acciones rutinarias en la nube. Por ejemplo, iniciar una instancia o renovar una señal. 
* **Warning** está definido para las acciones en las que se actualiza un recurso de la nube o se modifican sus metadatos. Por ejemplo, actualizar la versión de un nodo trabajador, cambiar el nombre de un certificado o cambiar el nombre de una instancia de servicio. 
* **Critical** está definido para las acciones que afectan a la seguridad en la nube. Por ejemplo, cambiar las credenciales de un usuario, suprimir datos o acceso no autorizado para trabajar con un recurso en la nube.

Puede especificar la consulta siguiente para buscar este tipo de sucesos:

```
severity VALUE
```
{: codeblock}

Donde `VALUE` se puede establecer en *normal*, *warning* o *critical*

Por ejemplo, para consultar sucesos críticos, puede ejecutar la consulta siguiente:

```
severity critical
```
{: codeblock}



## Paso 3. Crear una vista personalizada
{: #views_step3}

Tras aplicar la consulta de búsqueda a la vista **Todo** o a una vista personalizada existente, realice los pasos siguientes para guardar el resultado como una vista personalizada:

1. En la interfaz de usuario web, pulse **Vista sin guardar**.
2. Seleccione **Guardar como nueva vista / alerta**. Se abrirá la página *Crear nueva vista*.
3. Especifique un nombre para la vista en el campo *Nombre*.
4. De manera opcional, añada una categoría. Especifique un nombre y, a continuación, pulse **Añadir esta como nueva categoría de vista**.
5. Opcionalmente, adjunte una alerta. Aparecerá una nueva sección para que pueda configurar la alerta.
6. Pulse **Guardar vista**


## Paso 4. Personalizar cómo se muestran las líneas de sucesos a través de una vista
{: #views_step4}

Hay distintas opciones para personalizar cómo se visualizan los datos en una vista:
* Puede modificar las propiedades de una vista. Puede renombrar una vista, añadir o modificar su descripción y aplicar un formato de línea específico.
* Puede cambiar el `log format` (formato de registro) en la sección *USER PREFERENCES* (preferencias de usuario).
* Puede aplicar una plantilla de línea desde la sección *Herramientas*. Tenga en cuenta que esto sustituirá a cualquier otra configuración de línea. Si selecciona **Conservar estos valores**, todas las vistas de la interfaz de usuario mostrarán los datos según el formato de línea especificado en esta sección.
* Puede aplicar color a los términos o series estableciendo **Resaltar términos** en la sección
**Herramientas**.



### Cambiar el formato de línea a través de la página de propiedades de vista
{: #views_step4_1}

Realice los pasos siguientes para modificar el formato de una línea de sucesos en una vista individual:

1. En la vista, seleccione **Editar propiedades de vista**. Se abrirá la página *Editar propiedades de vista*.

2. Especifique un formato de línea personalizado en la sección **Personalizado %LINE Plantilla**. El valor predeterminado se establece en `{{line}}`.

    Para obtener más información sobre las directrices sobre plantillas de línea, consulte
[Directrices](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_line).

3. Pulse **Guardar propiedades*.



### Cambiar el formato de línea a través de la sección de preferencias de usuario
{: #views_step4_2}

En la sección **PREFERENCIAS DE USUARIO**, puede modificar el orden de los campos de datos que se muestran en cada línea.

Realice los pasos siguientes para modificar el formato de una línea de suceso:

1. En la interfaz de usuario web, pulse el icono **Configuración** ![Icono Configuración](images/admin.png "Icono Administración").
2. Seleccione **PREFERENCIAS DE USUARIO**. Se abrirá una nueva ventana.
3. Seleccione **Formato de registro**.
4. Modifique la sección *Formato de línea* para que se ajuste a sus requisitos. Arrastre los recuadros.


### Cambiar el formato de línea a través de la plantilla de línea en la sección de herramientas
{: #views_step4_3}

Realice los pasos siguientes para modificar el formato de una línea de suceso:

1. En la vista, pulse el icono **Herramientas** ![Icono Herramientas](images/tool.png "Icono Herramientas").
2. En el campo **Plantilla de línea**, especifique el formato de línea personalizado. Para obtener más información sobre las directrices sobre plantillas de línea, consulte
[Directrices](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_line).
3. De manera opcional, pulse **Conservar estos valores** para aplicar el formato de línea a todas las vistas.



### Resaltar términos
{: #view_events_step4_4}

Realice los pasos siguientes para resaltar términos en una vista:

1. En la vista, pulse el icono **Herramientas** ![Icono Herramientas](images/tool.png "Icono Herramientas").
2. En el campo **Plantilla de línea**, especifique una palabra o serie en la sección **Resaltar términos**.
3. De manera opcional, pulse **Conservar estos valores** para aplicar estos valores a todas las vistas.



## Cambiar el nombre y la descripción de una vista personalizada
{: #views_step5}

Puede renombrar una vista. Puede añadir o modificar la descripción de una vista.


Siga los pasos siguientes:

1. En la vista, seleccione **Editar propiedades de vista**. Se abrirá la página *Editar propiedades de vista*.

    Puede renombrar la vista, añadir o modificar la descripción de la vista, y aplicar un formato de línea personalizado.

2. Especifique un nombre nuevo en la sección **Renombrar vista** para renombrar la vista.

3. Especifique o modifique la descripción en la sección **Descripción**.

4. Pulse **Guardar propiedades**.



## Directrices de definición de plantillas de línea
{: #views_line}

Tenga en cuenta que debe aplicar las directrices siguientes al definir una plantilla de línea:
* Utilice variables de estilo mustache `{{field.name}}` o de estilo bash `${field.name}` para construir la plantilla. 
* Utilice `{{line}}` o `$@` para hacer referencia a la línea original. 
* Todos los demás caracteres o series se interpretan como literales de texto. 


Por ejemplo, puede definir una plantilla de línea como `{{initiator.id}} -- {{action}} -- {{message}}` para ver estos campos para cada suceso de una vista.


