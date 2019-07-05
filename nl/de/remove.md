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

# Instanz entfernen
{: #remove}

Sie können eine Instanz des {{site.data.keyword.at_full_notm}}-Service über die {{site.data.keyword.cloud_notm}}-Benutzerschnittstelle oder die Befehlszeile entfernen.
{:shortdesc}



## Instanz über die {{site.data.keyword.cloud_notm}}-Benutzerschnittstelle entfernen
{: #remove_ui}

Führen Sie die folgenden Schritte aus, um eine Instanz von {{site.data.keyword.at_full_notm}} mithilfe der {{site.data.keyword.cloud_notm}}-Benutzerschnittstelle zu entfernen:

1. [Melden Sie sich bei Ihrem {{site.data.keyword.cloud_notm}}-Konto ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://cloud.ibm.com/login){:new_window} an.

	Nachdem Sie sich mit Ihrer Benutzer-ID und Ihrem Kennwort angemeldet haben, wird die {{site.data.keyword.cloud_notm}}-Benutzerschnittstelle geöffnet.

2. Navigieren Sie zum Menüsymbol ![Menüsymbol](../../icons/icon_hamburger.svg) &gt; **Beobachtbarkeit**, um auf das Dashboard *Beobachtbarkeit* zuzugreifen.

3. Wählen Sie **Activity Tracker** aus. Die Liste von Instanzen wird angezeigt.

4. Wählen Sie die Instanz aus, die Sie löschen möchten.

5. Wählen Sie im Menü *Aktion* den Eintrag **Entfernen** aus.

Entfernen Sie im nächsten Schritt Berechtigungen, die Benutzern für die Arbeit mit der gelöschten Instanz erteilt wurden.

## Instanz über die Befehlszeilenschnittstelle entfernen
{: #remove_cli}

Führen Sie die folgenden Schritte aus, um eine Instanz von {{site.data.keyword.at_full_notm}} über die Befehlszeile zu entfernen:

1. [Voraussetzung] Installation der {{site.data.keyword.cloud_notm}}-Befehlszeilenschnittstelle.

   Weitere Informationen finden Sie unter [{{site.data.keyword.cloud_notm}}-Befehlszeilenschnittstelle installieren](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli).

   Wenn die Befehlszeilenschnittstelle installiert ist, fahren Sie mit dem nächsten Schritt fort.

2. Melden Sie sich bei der Region in der {{site.data.keyword.cloud_notm}} an, in der Sie die Instanz bereitstellen möchten. Führen Sie den folgenden Befehl aus: [`ibmcloud login`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_login).

3. Geben Sie die Ressourcengruppe an, in der die Instanz bereitgestellt wird. Führen Sie den folgenden Befehl aus: [`ibmcloud target`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_target).

    Standardmäßig ist die Ressourcengruppe *Standard* festgelegt.

4. Entfernen Sie die Instanz. Führen Sie den Befehl [`ibmcloud resource service-instance-delete`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_resource#ibmcloud_resource_service_instance_delete) aus:

    ```
    ibmcloud resource service-instance-delete NAME 
    ```
    {: codeblock}

    Dabei ist NAME der Name der Instanz.

    Führen Sie den folgenden Befehl aus, um alle Instanzen aufzulisten, die in der Ressourcengruppe, bei der Sie angemeldet sind, verfügbar sind:

    ```
    ibmcloud resource service-instances
    ```
    {: codeblock}
    
    
Führen Sie beispielsweise den folgenden Befehl aus, um eine Instanz zu entfernen:

```
ibmcloud resource service-instance-delete logdna-instance-01
```
{: codeblock}

Entfernen Sie im nächsten Schritt Berechtigungen, die Benutzern für die Arbeit mit der gelöschten Instanz erteilt wurden.


