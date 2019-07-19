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

 
# Einem Benutzer oder einer Service-ID Benutzerberechtigungen erteilen
{: #iam_view_events}

Mit {{site.data.keyword.iamlong}} (IAM) können Sie Benutzer sicher authentifizieren und den Zugriff auf alle Cloudressourcen konsistent in der {{site.data.keyword.cloud_notm}} steuern. Führen Sie die folgenden Schritte aus, um einem Benutzer oder einer Service-ID die mindestens erforderlichen Berechtigungen für die Arbeit mit dem {{site.data.keyword.at_full_notm}}-Service zu erteilen: 
{:shortdesc}

## Voraussetzungen
{: #iam_view_events_prereq}

Ihre Benutzer-ID benötigt **Administratorplattformberechtigungen**, um den {{site.data.keyword.at_full_notm}}-Service zu verwalten. Wenden Sie sich an den Kontoadministrator. Der Kontoeigner kann einen anderen Benutzerzugriff auf das Konto für die Verwaltung des Benutzerzugriffs und die Verwaltung von Kontoressourcen erteilen. [Weitere Informationen](/docs/iam?topic=iam-userroles).



## Schritt 1. Zugriffsgruppe erstellen
{: #iam_view_events_step1}

Führen Sie die folgenden Schritte aus, um eine Zugriffsgruppe zu erstellen:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Zugriffsgruppen** aus.
2. Klicken Sie auf **Erstellen**.
3. Geben Sie einen Namen und eine optionale Beschreibung für Ihre Gruppe ein und klicken Sie auf **Erstellen**.

Sie können eine Gruppe löschen, indem Sie die Option **Gruppe entfernen** auswählen. Wenn Sie eine Gruppe aus dem Konto löschen, entfernen Sie alle Benutzer und Service-IDs aus der Gruppe und damit den Zugriff, der der Gruppe zugewiesen ist.
{: note}

Um eine Zugriffsgruppe mithilfe der Befehlszeilenschnittstelle zu erstellen, können Sie den Befehl [ibmcloud iam access-group-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_create) verwenden.
```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION]
```
{: codeblock}



## Schritt 2. Berechtigungen zum Anzeigen von Ereignissen hinzufügen
{: #iam_view_events_step2}

Nachdem Sie Ihre Gruppe eingerichtet haben, können Sie der Gruppe eine allgemeine Zugriffsrichtlinie zuweisen. 

Jede Richtlinie, die Sie für eine Zugriffsgruppe festlegen, gilt für alle Entitäten, Benutzer und Service-IDs in der Gruppe. 
{: note}

Sie können die Richtlinie über die Benutzerschnittstelle oder die Befehlszeile zuweisen.

Um eine Zugriffsgruppenrichtlinie mithilfe der Befehlszeilenschnittstelle zu erstellen, können Sie den Befehl [ibmcloud iam access-group-policy-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_policy_create) verwenden.

```
ibmcloud iam access-group-policy-create GROUP_NAME {-f, --file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```
{: codeblock}

Wenn Sie die Richtlinie definieren, müssen Sie eine Plattformrolle und eine Servicerolle auswählen:
* Plattformmanagementrollen decken eine Reihe von Aktionen ab, einschließlich der Möglichkeit, Instanzen zu erstellen und zu löschen, Aliasnamen, Bindungen und Berechtigungsnachweise zu verwalten sowie den Zugriff zu verwalten. Bei den Plattformrollen handelt es sich um Administrator, Editor, Operator und Anzeigeberechtigter. Plattformmanagementrollen gelten auch für Kontoverwaltungsservices, die es Benutzern abhängig von der zugewiesenen Rolle für den jeweiligen Kontoverwaltungsservice ermöglichen, Benutzer einzuladen, Service-IDs, Zugriffsrichtlinien und Katalogeinträge zu verwalten sowie Abrechnungen und Nutzung zu verfolgen. 
* Servicezugriffsrollen definieren die Fähigkeit eines Benutzers oder Service, Aktionen für eine Serviceinstanz auszuführen. Bei den Servicezugriffsrollen handelt es sich um Manager, Schreibberechtigter und Leseberechtigter.

Für die Verwaltung des {{site.data.keyword.at_full_notm}}-Service benötigt ein Benutzer die folgenden Rollen:
* Plattformrolle: **Anzeigeberechtigter**. 
* Servicerolle: **Leseberechtigter**. 
[Weitere Informationen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam#iam).



Führen Sie die folgenden Schritte aus, um einer Zugriffsgruppe über die Benutzerschnittstelle eine Richtlinie zuzuweisen:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Zugriffsgruppen** aus.
2. Wählen Sie den Namen der Gruppe aus, der Sie Zugriff zuweisen möchten. 
3. Klicken Sie auf **Zugriffsrichtlinien**.
4. Klicken Sie auf **Zugriff zuweisen**.
5. Erteilen Sie Berechtigungen. Wählen Sie eine der folgenden Optionen aus:


### Option 1. Berechtigungen für den Service erteilen
{: #user_opt1}

Führen Sie die folgenden Schritte aus: 

1. Wählen Sie **Zugriff auf Ressourcen zuweisen** aus. 
2. Wählen Sie **IBM Cloud Activity Tracker mit LogDNA** aus.
3. Wählen Sie **Alle aktuellen Regionen** aus.
4. Wählen Sie **Alle aktuellen Serviceinstanzen** aus.
5. Wählen Sie die Plattformrolle **Anzeigeberechtigter** aus. 
6. Wählen Sie die Servicerolle **Leseberechtigter** aus.
7. Klicken Sie auf **Zuweisen**.

### Option 2. Berechtigungen im Kontext einer Ressourcengruppe erteilen
{: #user_opt2}

Führen Sie die folgenden Schritte aus: 

1. Wählen Sie **Zugriff in einer Ressourcengruppe zuweisen** aus.
2. Wählen Sie eine Ressourcengruppe aus.
3. Wenn dem Benutzer noch keine Rolle für die ausgewählte Ressourcengruppe zugewiesen wurde, wählen Sie eine Rolle für das Feld **Zugriff für eine Ressourcengruppe zuweisen** aus. 

    Abhängig von der ausgewählten Rolle kann der Benutzer die Ressourcengruppe im Dashboard anzeigen, den Ressourcengruppennamen bearbeiten oder den Benutzerzugriff auf die Gruppe verwalten. 
    
    Sie können **Kein Zugriff** auswählen, wenn der Benutzer nur auf den {{site.data.keyword.at_full_notm}}-Service in der Ressourcengruppe zugreifen soll.

4. Wählen Sie **IBM Cloud Activity Tracker mit LogDNA** aus.
5. Wählen Sie die Plattformrolle **Anzeigeberechtigter** aus. 
6. Wählen Sie die Servicerolle **Leseberechtigter** aus.
7. Klicken Sie auf **Zuweisen**.

### Option 3. Berechtigungen für eine Position erteilen
{: #user_opt3}

Sie können nur 1 Instanz pro Position bereitstellen. Führen Sie daher die folgenden Schritte aus, um Berechtigungen zum Anzeigen von Ereignissen in einer Region zu erteilen: 

1. Wählen Sie **Zugriff auf Ressourcen zuweisen** aus.
2. Wählen Sie **IBM Cloud Activity Tracker mit LogDNA** aus.
3. Wählen Sie die Instanz in der Region aus, für die der Benutzer über die Berechtigung zum Anzeigen von Ereignissen verfügen muss.
4. Wählen Sie die Plattformrolle **Anzeigeberechtigter** aus.
5. Wählen Sie die Servicerolle **Leseberechtigter** aus.
6. Klicken Sie auf **Zuweisen**.


## Schritt 3. Benutzer zur Zugriffsgruppe hinzufügen
{: #iam_view_events_step3}

Setzen Sie die Einrichtung Ihrer Gruppe mit dem Hinzufügen von Benutzern oder Service-IDs fort.

### Benutzer zur Zugriffsgruppe hinzufügen
{: #iam_manage_events_step3_user}

Führen Sie die folgenden Schritte aus, um einen Benutzer hinzuzufügen:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Zugriffsgruppen** aus.
2. Wählen Sie den Namen der Gruppe aus, der Sie Zugriff zuweisen möchten. 
3. Klicken Sie auf der Registerkarte **Benutzer** auf **Benutzer hinzufügen**.
4. Wählen Sie die Benutzer aus, den Sie aus der Liste hinzufügen möchten, und klicken Sie auf **Zu Gruppe hinzufügen**.


### Service-ID zur Zugriffsgruppe hinzufügen
{: #iam_manage_events_step3_svcid}

Führen Sie die folgenden Schritte aus, um eine Service-ID hinzuzufügen:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Zugriffsgruppen** aus.
2. Wählen Sie den Namen der Gruppe aus, der Sie Zugriff zuweisen möchten. 
3. Klicken Sie auf die Registerkarte **Service-IDs** und klicken Sie auf **Service-ID hinzufügen**.
4. Wählen Sie die IDs aus, die Sie aus der Liste hinzufügen möchten, und klicken Sie auf **Zu Gruppe hinzufügen**.


