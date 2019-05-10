---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, getting started

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


# Lernprogramm 'Einführung'
{: #getting-started}

Verwenden Sie den {{site.data.keyword.at_full}}-Service, um nachzuverfolgen, wie Anwendungen mit {{site.data.keyword.cloud_notm}}-Services interagieren. Sie können diesen Service verwenden, um nach anormaler Aktivität und kritischen Aktionen zu suchen und um regulatorische Prüfvorschriften zu erfüllen. Darüber hinaus können Sie zeitnah zu Aktionen benachrichtigt werden. Die gesammelten Ereignisse sind mit dem CADF-Standard (Cloud Auditing Data Federation) kompatibel.
{:shortdesc}

![Der {{site.data.keyword.at_full_notm}}-Service](images/atov.png "Der {{site.data.keyword.at_full_notm}}-Service")


{{site.data.keyword.at_full_notm}} sammelt und speichert Auditdatensätze für API-Aufrufe von Ressourcen, die in der {{site.data.keyword.cloud_notm}} ausgeführt werden. Sie können diese Ereignisse in der {{site.data.keyword.cloud_notm}} langfristig speichern.
{: note}



## Informationen zu {{site.data.keyword.at_full}}
{: #ov}

Compliance mit internen Richtlinien und Branchenregularien ist eine zentrale Anforderung jeder Unternehmensstrategie, unabhängig davon, wo Anwendungen ausgeführt werden: lokal, in einer hybriden Cloud oder in einer öffentlichen Cloud. Der {{site.data.keyword.at_full_notm}}-Service stellt das Framework und die Funktionalität für die Überwachung von API-Aufrufen an Services in der {{site.data.keyword.cloud_notm}} bereit und erzeugt die Nachweise für die Compliance mit Unternehmensrichtlinien und branchenspezifischen Regularien. 

Wenn Sie in einer Cloudumgebung arbeiten, z. B. {{site.data.keyword.cloud_notm}}, müssen Sie die Cloudstrategie für die Prüfung und Überwachung von Workloads und Daten in Übereinstimmung mit Ihren internen Richtlinien und mit branchen- und länderspezifischen Compliance-Anforderungen planen. Sie können die Informationen verwenden, die über den {{site.data.keyword.at_full_notm}}-Service registriert werden, um Sicherheitsvorfälle zu ermitteln, nicht autorisierte Zugriffe festzustellen und mit regulatorischen und internen Auditanforderungen konform zu bleiben. 

* {{site.data.keyword.at_full_notm}} unterstützt übergeordnete Sicherheits-Governance für Ihre IT-Ressourcen in der Cloud. 
* {{site.data.keyword.at_full_notm}} stellt eine Lösung für Administratoren zum Erfassen, Speichern, Anzeigen, Suchen und Überwachen von API-Aktivität an einem zentralen Ort bereit. Es bietet auch eine Benachrichtigungsfunktion, um Sie über einen der unterstützten Benachrichtigungskanäle zu warnen. 
* {{site.data.keyword.at_full_notm}} stellt Funktionen für den Export von Ereignissen bereit, die Sie anschließend verwenden können, um einen Auditprotokollbericht zu generieren. Unter Umständen brauchen Sie diese Berichte, um sicherzustellen, dass Ihre Organisation mit internen Regularien und externen Branchen- und Länderregularien konform ist. 

![Zentrale Funktionen des {{site.data.keyword.at_full_notm}}-Service](images/features.png "Zentrale Funktionen des {{site.data.keyword.at_full_notm}}-Service")

Sie können beispielsweise die {{site.data.keyword.at_full_notm}}-Ereignisse verwenden, um die folgenden Informationen zu ermitteln: 
* Die Benutzer, die API-Aufrufe an Cloud-Services gestartet haben. 
* Die Zeitmarke der API-Aufrufe. 
* Der Status des API-Aufrufs. 
* Die Kritikalität der Aktion. 


Berücksichtigen Sie die folgenden Informationen zur Sicherheit, wenn Sie mit dem {{site.data.keyword.at_full_notm}}-Service arbeiten: 

* IBM Services, die {{site.data.keyword.at_full_notm}}-Ereignisse generieren, befolgen die {{site.data.keyword.IBM_notm}} Cloud-Sicherheitsrichtlinie. Weitere Informationen finden Sie unter [Sicherheit in der IBM Cloud ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://www.ibm.com/cloud/security){: new_window}. 
* Der {{site.data.keyword.at_full_notm}}-Service zeichnet benutzerinitiierte Aktivitäten auf, die den Status von Cloud-Services ändern. Die Informationen geben keinen direkten Zugriff auf Datenbanken oder Anwendungen. 
* Nur berechtigte Benutzer können {{site.data.keyword.at_full_notm}}-Ereignisprotokolle anzeigen und überwachen. Jeder Benutzer ist durch seine eindeutige ID in der {{site.data.keyword.cloud_notm}} angegeben. 


## Ziele
{: #gs_objectives}

Führen Sie dieses Lernprogramm aus, um zu erfahren, wie Sie einen Service in der {{site.data.keyword.cloud_notm}} bereitstellen können. Finden Sie heraus, welche allgemeinen Daten in den einzelnen Ereignissen verfügbar sind und wie diese Ihnen dabei helfen, Ihre Cloudumgebung zu überwachen. Lernen Sie, wie Sie sich in der Webbenutzerschnittstelle zurechtfinden.  


## Voraussetzungen
{: #gs_prereq}

* Sie benötigen eine Benutzer-ID, die ein Mitglied oder ein Eigner eines {{site.data.keyword.cloud_notm}}-Kontos ist. So rufen Sie eine {{site.data.keyword.cloud_notm}}-Benutzer-ID ab: [Registrierung ![Symbol für externen Link](../../../icons/launch-glyph.svg "Symbol für externen Link")](https://cloud.ibm.com/login){:new_window}. 

* Ihrer {{site.data.keyword.IBM_notm}} ID müssen IAM-Richtlinien für die Arbeit in der {{site.data.keyword.cloud_notm}} mit dem {{site.data.keyword.at_full_notm}}-Service zugewiesen sein. In der folgenden Tabelle sind die Mindestberechtigungen aufgeführt, die Sie benötigen, um dieses Lernprogramm abzuschließen.  

| Ressource                             | Gültigkeitsbereich der Zugriffsrichtlinie | Rolle    | Region    | Informationen                  |
|--------------------------------------|----------------------------|---------|-----------|------------------------------|
| Ressourcengruppe **Standard**           |  Ressourcengruppe            | Editor  | us-south  | Diese Richtlinie ist erforderlich, damit der Benutzer Serviceinstanzen in der Ressourcengruppe 'Standard' anzeigen kann.    |
| {{site.data.keyword.at_full_notm}}-Service |  Ressourcengruppe            | Editor  | us-south  | Diese Richtlinie ist erforderlich, damit der Benutzer den {{site.data.keyword.at_full_notm}}-Service in der Ressourcengruppe 'Standard' bereitstellen und verwalten kann.   |
{: caption="Tabelle 1. Liste von IAM-Richtlinien, die zum Ausführen des Lernprogramms erforderlich sind" caption-side="top"} 

* Wenn Sie die Befehlszeile vorziehen, müssen Sie die {{site.data.keyword.cloud_notm}}-Befehlszeilenschnittstelle installieren. Weitere Informationen finden Sie unter [{{site.data.keyword.cloud_notm}}-Befehlszeilenschnittstelle installieren](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli). 


## Schritt 1. Instanz des {{site.data.keyword.at_full_notm}}-Service bereitstellen
{: #gs_step1}

Führen Sie die folgenden Schritte aus, um eine Instanz bereitzustellen: 

1. [Melden Sie sich bei Ihrem {{site.data.keyword.cloud_notm}}-Konto ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://cloud.ibm.com/login){:new_window} an. 

	Nachdem Sie sich mit Ihrer Benutzer-ID und Ihrem Kennwort angemeldet haben, wird die {{site.data.keyword.cloud_notm}}-Benutzerschnittstelle geöffnet. 

2. Navigieren Sie zum Menüsymbol ![Menüsymbol](../../icons/icon_hamburger.svg). Wählen Sie dann **Beobachtbarkeit** aus, um auf das Dashboard *Beobachtbarkeit* zuzugreifen. 

3. Wählen Sie **Activity Tracker** aus und klicken Sie dann auf **Instanz erstellen**.  

4. Geben Sie einen Namen für die Serviceinstanz ein. 

5. Wählen Sie die Region aus, in der Sie die Instanz bereitstellen möchten. 

6. Wählen Sie eine Ressourcengruppe aus.  

    Standardmäßig ist die Ressourcengruppe **Standard** festgelegt. 

    **Hinweis:** Wenn Sie keine Ressourcengruppe auswählen können, prüfen Sie, dass Sie über Bearbeitungsberechtigungen für die Ressourcengruppe verfügen, in der Sie die Instanz bereitstellen möchten. 

7. Wählen Sie den Serviceplan `Lite` aus.  

    Der Plan 'Lite' ist standardmäßig festgelegt. 

8. Klicken Sie auf **Erstellen**. 

Nachdem Sie eine Instanz bereitgestellt haben, wird das *Activity Tracker*-Dashboard geöffnet.  


## Schritt 2. Zugriff auf den Service verwalten
{: #gs_step2}

**Jedem Benutzer, der auf den {{site.data.keyword.at_full_notm}}-Service in Ihrem Konto zugreift, muss eine Zugriffsrichtlinie mit einer definierten IAM-Benutzerrolle zugewiesen werden.** Die Richtlinie bestimmt, welche Aktionen der Benutzer im Kontext des ausgewählten Service oder der ausgewählten Instanz ausführen kann. Die zulässigen Aktionen werden angepasst und definiert als Operationen, die für den Service ausgeführt werden dürfen. Die Aktionen werden dann IAM-Benutzerrollen zugeordnet.  

In diesem Lernprogramm erfahren Sie, wie Sie einem Benutzer Verwaltungsberechtigungen für die Arbeit mit dem {{site.data.keyword.at_full_notm}}-Service im Kontext einer Ressourcengruppe erteilen. [Weitere Informationen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam#iam). 


### 1. Zugriffsgruppe erstellen
{: #gs_step2_step1}

Führen Sie die folgenden Schritte aus, um eine Zugriffsgruppe zu erstellen: 

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Zugriffsgruppen** aus. 
2. Klicken Sie auf **Erstellen**. 
3. Geben Sie einen Namen und eine optionale Beschreibung für Ihre Gruppe ein und klicken Sie auf **Erstellen**. 

### 2. Berechtigungen zum Verwalten von Ereignissen hinzufügen
{: #gs_step2_step2}

Nachdem Sie Ihre Gruppe eingerichtet haben, können Sie der Gruppe eine allgemeine Zugriffsrichtlinie zuweisen. 

Um einem Benutzer eine Administratorrolle für die Verwaltung von Instanzen in einer Ressourcengruppe im Konto zu erteilen, muss der Benutzer über eine IAM-Richtlinie für den {{site.data.keyword.at_full_notm}}-Service mit der Plattformrolle **Administrator** im Kontext der Ressourcengruppe verfügen.  

Führen Sie die folgenden Schritte aus, um einer Zugriffsgruppe über die Benutzerschnittstelle eine Richtlinie zuzuweisen: 

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)**. 
2. Wählen Sie **Zugriffsgruppen** aus. 
3. Wählen Sie den Namen der Gruppe aus, der Sie Zugriff zuweisen möchten.  
4. Klicken Sie auf **Zugriffsrichtlinien**. 
5. Klicken Sie auf **Zugriff zuweisen**. 
6. Wählen Sie **Zugriff in einer Ressourcengruppe zuweisen** aus. 
7. Wählen Sie eine Ressourcengruppe aus. 
8. Wenn dem Benutzer noch keine Rolle für die ausgewählte Ressourcengruppe zugewiesen wurde, wählen Sie eine Rolle für das Feld **Zugriff für eine Ressourcengruppe zuweisen** aus.  

    Abhängig von der ausgewählten Rolle kann der Benutzer die Ressourcengruppe im Dashboard anzeigen, den Ressourcengruppennamen bearbeiten oder den Benutzerzugriff auf die Gruppe verwalten.  
    
    Sie können **Kein Zugriff** auswählen, wenn der Benutzer nur auf den {{site.data.keyword.at_full_notm}}-Service in der Ressourcengruppe zugreifen soll. 

9. Wählen Sie **IBM Cloud Activity Tracker mit LogDNA** aus. 
10. Wählen Sie die Plattformrolle **Administrator** aus. 
11. Wählen Sie die Servicerolle **Manager** aus. 
12. Klicken Sie auf **Zuweisen**. 


### 3.  Benutzer zur Gruppe hinzufügen
{: #gs_step2_step3}

Führen Sie die folgenden Schritte aus, um den Benutzer zur Zugriffsgruppe hinzuzufügen. 
1. Klicken Sie auf der Registerkarte **Benutzer** auf **Benutzer hinzufügen**. 
2. Wählen Sie den Benutzer aus, den Sie aus der Liste hinzufügen möchten, und klicken Sie auf **Zu Gruppe hinzufügen**. 



## Schritt 3. {{site.data.keyword.at_full_notm}}-Ereignisse generieren
{: #gs_step3}

Führen Sie die folgenden Schritte aus, um ein Ereignis zu generieren, wenn Sie eine Zugriffsgruppe erstellen. 


1. Wählen Sie im [{{site.data.keyword.cloud_notm}}-Katalog ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://cloud.ibm.com/catalog){:new_window} den Eintrag **Verwalten** &gt; **Sicherheit und Identität** aus. 

2. Wählen Sie **Zugriffsgruppen** aus. 

3. Wählen Sie **Erstellen** aus. Geben Sie dann einen Namen für die Zugriffsgruppe ein. 

4. Klicken Sie auf **Erstellen**. 

Eine Zugriffsgruppe wird erstellt. 

## Schritt 4. Webbenutzerschnittstelle starten 
{: #gs_step4}

Führen Sie die folgenden Schritte aus, um die Webbenutzerschnittstelle zu starten: 

1. [Melden Sie sich bei Ihrem {{site.data.keyword.cloud_notm}}-Konto ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://cloud.ibm.com/login){:new_window} an. 

	Nachdem Sie sich mit Ihrer Benutzer-ID und Ihrem Kennwort angemeldet haben, wird das {{site.data.keyword.cloud_notm}}-Dashboard geöffnet. 

2. Wählen Sie im Navigationsmenü **Beobachtbarkeit** aus.  

3. Wählen Sie **Activity Tracker** aus.  

    Die Liste von Instanzen, die in der {{site.data.keyword.cloud_notm}} verfügbar sind, wird angezeigt. 

4. Wählen Sie eine Instanz aus. Klicken Sie dann auf **LogDNA anzeigen**. 

Die Webbenutzerschnittstelle wird geöffnet.  




## Schritt 5. Ereignisse anzeigen
{: #gs_step5}


Der {{site.data.keyword.at_full_notm}}-Service erfasst Aktivitätsdaten mit Bezug auf API-Aufrufe und andere Aktionen, die für ausgewählte Cloud-Services in der {{site.data.keyword.cloud_notm}} gestartet werden.  

* Ereignisse werden automatisch erfasst.  
* Die in {{site.data.keyword.at_full_notm}} gesammelten Ereignisse sind mit dem **CADF-Standard (Cloud Auditing Data Federation)** kompatibel. Der CADF-Standard definiert ein umfassendes Ereignismodell, das die Informationen enthält, die zum Zertifizieren, Verwalten und Prüfen der Sicherheit von Anwendungen in Cloudumgebungen erforderlich sind. 
* {{site.data.keyword.at_full_notm}} speichert und gruppiert Ereignisse nach Region.  
* Ereignisse, die über globale {{site.data.keyword.cloud_notm}}-Kontoaktionen berichten, werden gesammelt und in der Region **US-South** (USA (Süden)) gespeichert. 
* Der Serviceplan, den Sie für Ihre {{site.data.keyword.at_full_notm}}-Instanz auswählen, bestimmt, wie viele Tage Ereignisse in der Webbenutzerschnittstelle gesucht werden können.  


Sie können die Ereigniszeilen jederzeit im Kontext anzeigen. Führen Sie die folgenden Schritte aus, um ein Ereignis im Kontext anzuzeigen:  

1. Klicken Sie in der Webbenutzerschnittstelle auf das Symbol **Ansichten** ![Konfigurationssymbol](images/views.png "Konfigurationssymbol"). 
2. Wählen Sie **Alles** aus. 
3. Geben Sie eine Zeile an, die Sie untersuchen möchten. 
4. Erweitern Sie die Ereigniszeile.  

    Informationen zu Zeilenkennungen, Tags und Bezeichnungen werden angezeigt. 

5. Klicken Sie auf **In Kontext anzeigen**, um die Ereigniszeile im Kontext anderer Einträge von diesem Host, dieser App oder beiden anzuzeigen. 

Wenn Sie das Ereignis abschließend untersucht haben, klicken Sie auf **Schließen**, um die Zeile zu schließen. 


[Weitere Informationen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-view_events.md#view_events.md). 




## Schritt 6. Struktur von Ereignissen verstehen
{: #gs_step6}

Ereignisse sind mit dem **CADF-Standard (Cloud Auditing Data Federation)** kompatibel. Der CADF-Standard definiert ein umfassendes Ereignismodell, das die Informationen enthält, die zum Zertifizieren, Verwalten und Prüfen der Sicherheit von Anwendungen in Cloudumgebungen erforderlich sind. 

Das CADF-Ereignismodell schließt die folgenden Komponenten ein: 

| Komponente | Beschreibung |
|------------|----------------------------|
| `Aktion`   | Die Aktion ist die Operation bzw. die Aktivität, die ein Initiator ausführt, auszuführen versucht oder bald ausführen wird. |
| `Initiator`| Der Initiator ist die Ressource, die einen API-Aufruf startet und ein CADF-Ereignis generiert. Welches Ereignis ausgelöst wird, hängt von der Aktion ab, die vom dem API-Aufruf angefordert wird. |
| `Observer` | Der Observer ist die Ressource, die einen CADF-Datensatz aus im CADF-Ereignis verfügbaren Informationen erstellt und speichert. |
| `Ergebnis`  | Das Ergebnis ist der Status der Aktion, die für ein Ziel ausgeführt wird. |
| `Ziel`   | Das Ziel ist die Ressource, in der die Aktion ausgeführt wird, auszuführen versucht wird oder bald ausgeführt werden soll. |
{: caption="Tabelle 2. In einem CADF-Ereignismodell verfügbare Komponenten" caption-side="top"} 

[Weitere Informationen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-event#event). 

## Nächste Schritte
{: #gs_next_steps}

Führen Sie ein Upgrade für den {{site.data.keyword.at_full_notm}}-Serviceplan auf einen bezahlten Plan aus, um [Ereignisse zu filtern](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views.md#views_step1), [nach Ereignissen zu suchen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views.md#views_step2), [Ansichten zu definieren](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views.md#views_step3) und [Alerts zu konfigurieren](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-alerts.md#alerts.md).  

Weitere Informationen zu {{site.data.keyword.at_full_notm}}-Serviceplänen finden Sie unter [Servicepläne](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan#service_plan). 

