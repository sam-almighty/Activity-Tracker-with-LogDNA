---

copyright:
  years: 2019
lastupdated: "2019-05-25"

keywords: IBM Cloud, LogDNA, Activity Tracker, view events

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


# Visualización de sucesos
{: #view_events}

Tras suministrar una instancia del servicio {{site.data.keyword.at_full_notm}} en
{{site.data.keyword.cloud_notm}}, puede ver sucesos a través de la interfaz de usuario web de
{{site.data.keyword.at_full_notm}}. Puede ver los sucesos en su hora local.
{:shortdesc}


## Ver sucesos
{: #view_events_step1}

Realice los pasos siguientes para visualizar sucesos:

1. Compruebe que el ID de usuario tenga permisos para iniciar la interfaz de usuario web y para ver los sucesos. 

    En la tabla siguiente se muestran los roles mínimos que debe tener un usuario para poder iniciar la interfaz de usuario web de {{site.data.keyword.at_full_notm}} y visualizar sucesos:

    <table>
      <caption>Tabla 1. Roles de IAM</caption>
      <tr>
        <th>Rol</th>
        <th>Permiso otorgado</th>
      </tr>
      <tr>
        <td>Rol de la plataforma: `Visor`</td>
        <td>Permite al usuario ver la lista de instancias de servicio en el panel de control *Observabilidad*.</td>
      </tr>
      <tr>
        <td>Rol de servicio: `Lector`</td>
        <td>Permite al usuario iniciar la interfaz de usuario web y ver, buscar y filtrar sucesos en la interfaz de usuario web.</td>
      </tr>
    </table>

    Para obtener más información sobre cómo configurar las políticas para un usuario, consulte [Cómo otorgar permisos de usuario a un usuario o ID de servicio](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events).

2. [Vaya a la interfaz de usuario web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).

3. Pulse el icono **Vistas** ![Icono Configuración](images/views.png).

4. Seleccione **Todo** para ver todos los sucesos, o una vista. 

Puede ver sucesos a través de la vista que haya seleccionado.



## Ver un subconjunto de los sucesos aplicando una consulta de búsqueda
{: #view_events_step2}

Puede seleccionar los sucesos que se muestran a través de una vista aplicando una consulta de búsqueda. Puede guardar dicha vista para reutilizarla más adelante. [Más información](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_step2).

 


## Ver un subconjunto de los sucesos aplicando un periodo de tiempo
{: #view_events_step3}

Puede seleccionar los sucesos que se muestran a través de una vista aplicando un periodo de tiempo.

Puede aplicar una indicación de fecha y hora especificando una hora absoluta, una hora relativa o un intervalo de tiempo.

Realice los pasos siguientes para saltar a una hora específica:
1. [Vaya a la interfaz de usuario web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).
2. Pulse el icono **Vistas** ![Icono Configuración](images/views.png).
3. Seleccione **Todo** o una vista.
4. Especifique una consulta de tiempo. Elija cualquiera de las opciones siguientes:

    * Especifique una hora absoluta para saltar a un momento específico en los sucesos, como `May 20 7:00pm`.
    
    * Especifique una hora relativa como `2 days ago`, `today at 12am` o `an hour ago`.

    * Especifique un intervalo de tiempo como `yesterday 10am to yesterday 11am`, `last fri 4:30pm to 11/12 1 AM`, `last wed 4:30pm to 23/05 1 AM` o `May 20 10am to May 22 10am`. Asegúrese de incluir `to` para separar la indicación de fecha y hora inicial de la indicación de fecha y hora final.

5. Pulse **INTRO**.

    Podría recibir el mensaje de error: `La solicitud tarda más de lo esperado, intente renovar el navegador en poco tiempo. Reintentar.` Puede recibir este error cuando el periodo de tiempo que ha especificado no tenga ningún suceso disponible que mostrar. Cambie la consulta temporal y vuelva a intentarlo.



## Ver un suceso en contexto
{: #view_events_step4}

En cualquier momento, puede ver cada línea en su contexto.

Siga los pasos siguientes: 

1. En la interfaz de usuario web, pulse el icono **Vistas** ![Icono Configuración](images/views.png "Icono Configuración").
2. Seleccione **Todo** o una vista personalizada.
3. Identifique una línea que desee explorar.
4. Expanda la línea. 

    Aparece información sobre identificadores, códigos y etiquetas de línea.

5. Pulse **Ver en contexto** para ver la línea de suceso en el contexto de otras entradas de dicho host, app, o ambos.

Cuando haya terminado de explorar el suceso, pulse **Cerrar** para cerrar la línea.



## Copiar un suceso en el portapapeles
{: #view_events_step5}


Realice los pasos siguientes para copiar un suceso en el portapapeles: 

1. En la interfaz de usuario web, pulse el icono **Vistas** ![Icono Configuración](images/views.png "Icono Configuración").
2. Seleccione **Todo** o una vista personalizada.
3. Identifique una línea que desee explorar.
4. Expanda la línea. 

    Aparece información sobre identificadores, códigos y etiquetas de línea.

5. Pulse **Copiar al portapapeles** para copiar el suceso al portapapeles.

Cuando haya terminado de explorar el suceso, pulse **Cerrar** para cerrar la línea.




