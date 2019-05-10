---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, archive logs, COS, cloud object storage

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

 
# Ereignisse in IBM Cloud Object Storage archivieren
{: #archiving}

Sie können Ereignisse aus einer {{site.data.keyword.at_full_notm}}-Instanz in einem Bucket in einer {{site.data.keyword.cos_full_notm}}-Instanz (COS) archivieren.
{:shortdesc}

Um die Archivierung zu konfigurieren, müssen Sie über eine IAM-Richtlinie mit der Plattformrolle **Anzeigeberechtigter** und der Servicerolle **Manager** für den {{site.data.keyword.at_full_notm}}-Service verfügen. 

Sie archivieren Ereignisse aus einer {{site.data.keyword.at_full_notm}}-Instanz in einem Bucket in einer {{site.data.keyword.cos_full_notm}}-Instanz (COS).
Jede {{site.data.keyword.at_full_notm}}-Instanz hat ihre eigene Archivierungskonfiguration.  

Ereignisse werden automatisch einmal pro Tag in einem komprimierten Format **(.json.gz)** archiviert. Jede Zeile behält ihre Metadaten bei. 

Ereignisse werden innerhalb von 24 - 48 Stunden archiviert, nachdem Sie die Konfiguration gespeichert haben.  

Die {{site.data.keyword.cos_full_notm}}-Instanz wird im Kontext einer Ressourcengruppe bereitgestellt. Die {{site.data.keyword.at_full_notm}}-Instanz wird ebenfalls im Kontext einer Ressourcengruppe bereitgestellt. Beide Instanzen können unter derselben Ressourcengruppe oder in verschiedenen Ressourcengruppen gruppiert werden.  

{{site.data.keyword.at_full_notm}} verwendet eine Service-ID für die Kommunikation mit dem {{site.data.keyword.cos_full_notm}}-Service. 

* Die Service-ID, die Sie für eine {{site.data.keyword.cos_full_notm}}-Instanz erstellen, wird von {{site.data.keyword.at_full_notm}} zur Authentifizierung und für den Zugriff auf die {{site.data.keyword.cos_full_notm}}-Instanz verwendet.  
* Sie können der Service-ID spezifische Zugriffsrichtlinien zuweisen, die Berechtigungen für die {{site.data.keyword.cos_full_notm}}-Instanz beschränken. Beschränken Sie die Service-ID insofern, als dass sie nur über Schreibberechtigungen für das Bucket verfügt, in dem Sie die Ereignisse archivieren möchten. 

In der folgenden Abbildung sehen Sie eine abstrakte Ansicht der verschiedenen Komponenten, die beim Archivieren von Ereignissen involviert sind: 

![Abstrakte Ansicht der Archivierung von Ereignissen](images/archive.png "Abstrakte Ansicht der Archivierung von Ereignissen")


Führen Sie die folgenden Schritte aus, um eine {{site.data.keyword.at_full_notm}}-Instanz in einem Bucket in einer {{site.data.keyword.cos_full_notm}}-Instanz zu archivieren: 


## Schritt 1. Einem Benutzer IAM-Richtlinien für die Arbeit mit {{site.data.keyword.cos_full_notm}} zuweisen 
{: #archiving_step1}

**Hinweis:** Dieser Schritt muss vom Kontoeigner oder einem Administrator des {{site.data.keyword.cos_full_notm}}-Service in der {{site.data.keyword.cloud_notm}} ausgeführt werden. 

Als Administrator des {{site.data.keyword.cos_full_notm}}-Service müssen Sie in der Lage sein, Instanzen des Service bereitzustellen, anderen Benutzern Berechtigungen für die Arbeit mit diesen Instanzen zu erteilen und Service-IDs zu erstellen.  

Es gibt verschiedene Möglichkeiten, einem Benutzer die Berechtigung zu erteilen, Editor des {{site.data.keyword.cos_full_notm}}-Service zu werden: 

* Als Administrator des Service in dem Konto muss der Benutzer über eine IAM-Richtlinie für den {{site.data.keyword.cos_full_notm}}-Service mit der Plattformrolle *Administrator* verfügen. Sie müssen diesem Benutzer Zugriff auf eine einzelne Ressource in dem Konto zuweisen.  

* Als Administrator des Service im Kontext einer Ressourcengruppe muss der Benutzer über eine IAM-Richtlinie für den {{site.data.keyword.cos_full_notm}}-Service mit der Plattformrolle *Administrator* im Kontext der Ressourcengruppe verfügen.  


In der folgenden Tabelle sind die Rollen aufgeführt, die ein Benutzer innehaben kann, um die Aktionen auszuführen, die für den {{site.data.keyword.cos_full_notm}}-Service aufgelistet sind: 

| Service                    | Plattformrollen    | Aktion                                                                                        | 
|----------------------------|-------------------|-----------------------------------------------------------------------------------------------|       
| `Cloud Object Storage`     | Administrator     | Ermöglicht dem Benutzer, anderen Benutzern in dem Konto Richtlinien für die Arbeit mit dem {{site.data.keyword.cos_full_notm}}-Service zuzuweisen. |
| `Cloud Object Storage`     | Administrator </br>Editor | Ermöglicht dem Benutzer, eine Instanz des {{site.data.keyword.cos_full_notm}}-Service bereitzustellen.    |
| `Cloud Object Storage`     | Administrator </br>Editor </br>Operator | Ermöglicht dem Benutzer, eine Service-ID zu erstellen.    | 
{: caption="Tabelle 1. Rollen und Aktionen" caption-side="top"} 


Führen Sie die folgenden Schritte aus, um einem Benutzer die Administratorrolle für den {{site.data.keyword.cos_full_notm}}-Service im Kontext einer Ressourcengruppe zuzuweisen.  

1. [Melden Sie sich bei Ihrem {{site.data.keyword.cloud_notm}}-Konto ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://cloud.ibm.com/login){:new_window} an. 

	Nachdem Sie sich mit Ihrer Benutzer-ID und Ihrem Kennwort angemeldet haben, wird die {{site.data.keyword.cloud_notm}}-Benutzerschnittstelle geöffnet. 
    
2. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie dann **Benutzer** aus. 
3. Wählen Sie in der Zeile für den Benutzer, dem Sie Zugriff zuweisen möchten, das Menü **Aktionen** aus und klicken Sie dann auf **Zugriff zuweisen**. 
4. Wählen Sie **Zugriff in einer Ressourcengruppe zuweisen** aus. 
5. Wählen Sie eine Ressourcengruppe aus. 
6. Wenn dem Benutzer noch keine Rolle für die ausgewählte Ressourcengruppe zugewiesen wurde, wählen Sie eine Rolle für das Feld **Zugriff für eine Ressourcengruppe zuweisen** aus.  

    Abhängig von der ausgewählten Rolle kann der Benutzer die Ressourcengruppe im Dashboard anzeigen, den Ressourcengruppennamen bearbeiten oder den Benutzerzugriff auf die Gruppe verwalten.  
    
    Sie können **Kein Zugriff** auswählen, wenn der Benutzer nur auf den {{site.data.keyword.at_full_notm}}-Service in der Ressourcengruppe zugreifen soll. 

7. Wählen Sie **Cloud Object Storage** aus. 
8. Wählen Sie die Plattformrolle **Administrator** aus. 
9. Klicken Sie auf **Zuweisen**. 



## Schritt 2. Instanz von {{site.data.keyword.cos_full_notm}} bereitstellen
{: #archiving_step2}

**Hinweis:** Dieser Schritt muss von einem Editor oder einem Administrator des {{site.data.keyword.cos_full_notm}}-Service in der {{site.data.keyword.cloud_notm}} ausgeführt werden. Führen Sie die folgenden Schritte aus, um eine {{site.data.keyword.cos_full_notm}}-Instanz bereitzustellen: 

1. Klicken Sie in der Menüleiste auf **Katalog**. Die Liste von Services, die in der {{site.data.keyword.cloud_notm}} verfügbar sind, wird geöffnet. 

2. Um die angezeigte Liste von Services zu filtern, wählen Sie die Kategorie **Speicher** aus. 

3. Klicken Sie auf die Kachel **Objektspeicher**. 

4. Geben Sie einen Namen für die Serviceinstanz ein. 

5. Wählen Sie eine Ressourcengruppe aus.  

    Standardmäßig ist die Ressourcengruppe **Standard** festgelegt. 

6. Wählen Sie einen Serviceplan aus.  

    Standardmäßig ist der Plan **Lite** festgelegt. 

7. Klicken Sie auf **Erstellen**. 



## Schritt 3. Bucket erstellen 
{: #archiving_step3}

Buckets sind eine Möglichkeit, Ihre Daten in einer {{site.data.keyword.cos_full_notm}}-Instanz zu organisieren.  

Um Buckets zu verwalten, müssen Ihrem Benutzer Berechtigungen für die Arbeit mit Buckets in der {{site.data.keyword.cos_full_notm}}-Instanz erteilt werden. In der folgenden Tabelle sind die verschiedenen Aktionen und Rollen aufgeführt, die ein Benutzer für die Arbeit mit Buckets innehaben kann. 

| Service                    | Rollen                   | Aktion                             | 
|----------------------------|-------------------------|------------------------------------|       
| `Cloud Object Storage`     | Plattformrolle: Anzeigeberechtigter   | Ermöglicht dem Benutzer, über die {site.data.keyword.Bluemix_notm}}-Benutzerschnittstelle alle Buckets anzuzeigen und die Objekte in diesen Buckets aufzulisten. |
| `Cloud Object Storage`     | Servicerolle: Manager   | Ermöglicht dem Benutzer, Objekte öffentlich zu machen.                                                       |
| `Cloud Object Storage`     | Servicerollen: Manager </br>Schreibberechtigter | Ermöglicht dem Benutzer, Buckets und Objekte zu erstellen und zu löschen.                         | 
| `Cloud Object Storage`     | Servicerolle: Leseberechtigter    | Ermöglicht dem Benutzer, Objekte aufzulisten und herunterzuladen.                                                 |
{: caption="Tabelle 1. Rollen und Aktionen für die Arbeit mit Buckets" caption-side="top"} 

**Hinweis:** Um ein Bucket zu erstellen, muss Ihr Benutzer über die Berechtigungen eines Managers oder Schreibberechtigten für die {{site.data.keyword.cos_full_notm}}-Instanz verfügen. 

Führen Sie die folgenden Schritte aus, um ein Bucket zu erstellen: 

1. Wählen Sie im Navigationsmenü den Eintrag **Ressourcenliste** aus. 

2. Wählen Sie die {{site.data.keyword.cos_full_notm}}-Instanz aus, in der Sie das Bucket erstellen möchten. 

3. Wählen Sie **Buckets** aus. Klicken Sie dann auf **Bucket erstellen**. 

4. Geben Sie einen Bucketnamen für das Feld *Eindeutiger Bucketname* ein. 

    **Hinweis:** Alle Buckets in allen Regionen weltweit teilen sich einen einzigen Namensbereich.  

    Sie können als Teil Ihres Bucketnamens Ihren {{site.data.keyword.at_full_notm}}-Instanznamen verwenden. Für eine Instanz namens *logdna-1* können Sie beispielsweise *accountN-logdna-1* als Ihren Bucketnamen verwenden. 

    Sie brauchen diesen Namen für die Konfiguration der Archivierung über die {{site.data.keyword.at_full_notm}}-Webbenutzerschnittstelle. 

5. Wählen Sie den Typ von Ausfallsicherheit und einen Standort aus, an dem Ihre Daten physisch gespeichert werden sollen. 

    Ausfallsicherheit bezieht sich auf den Umfang und den Maßstab des geografischen Bereichs, über den Ihre Daten verteilt werden.  
    
    Eine regionsübergreifende Ausfallsicherheit verteilt Ihre Daten über verschiedene Ballungsräume. 
    
    Eine regionale Ausfallsicherheit verteilt Daten über einen einzelnen Ballungsraum.  
    
    Ein einzelnes Rechenzentrum verteilt Daten nur über Geräte innerhalb eines einzelnen Standorts. 

    Weitere Informationen finden Sie unter [Regionen und Endpunkte auswählen](/docs/services/cloud-object-storage?topic=cloud-object-storage-endpoints#endpoints). 

6. Wählen Sie den Typ von *Speicherklasse* aus. 

    Sie können Buckets mit verschiedenen Speicherklassen erstellen. Wählen Sie die Speicherklasse für Ihr Bucket basierend auf Ihren Anforderungen an das Abrufen von Daten aus. Weitere Informationen finden Sie unter [Speicherklassen verwenden](/docs/services/cloud-object-storage?topic=cloud-object-storage-use-storage-classes#use-storage-classes). 

    **Hinweis:** Es ist nicht möglich, die Speicherklasse eines Buckets zu ändern, sobald das Bucket erstellt wurde. Wenn Objekte erneut klassifiziert werden müssen, ist es notwendig, die Daten in ein anderes Bucket mit der gewünschten Speicherklasse zu verschieben. 

7. Fügen Sie optional einen Key Protect-Schlüssel zum Verschlüsseln der ruhenden Daten hinzu. 

    Alle Objekte werden standardmäßig mit zufällig generierten Schlüsseln und einer All-or-nothing-Transformation (AONT) verschlüsselt. Während dieses Standardverschlüsselungsmodell Sicherheit für ruhende Daten bietet, müssen manche Workloads über die verwendeten Verschlüsselungsschlüssel verfügen können. Weitere Informationen finden Sie unter [Verschlüsselung verwalten](/docs/services/cloud-object-storage?topic=cloud-object-storage-manage-encryption#manage-encryption). 



## Schritt 4. Service-ID für die {{site.data.keyword.cos_full_notm}}-Instanz erstellen
{: #archiving_step4}

Eine Service-ID gibt einen Service an, ähnlich wie eine Benutzer-ID einen Benutzer angibt. Service-IDs sind nicht an einen bestimmten Benutzer gebunden. Wenn der Benutzer, der die Service-ID erstellt, Ihr Unternehmen verlässt und aus dem Konto gelöscht wird, bleibt die Service-ID bestehen. 

Sie müssen eine Service-ID für Ihre {{site.data.keyword.cos_full_notm}}-Instanz erstellen. Diese Service-ID wird von der {{site.data.keyword.at_full_notm}}-Instanz zur Authentifizierung mit Ihrer {{site.data.keyword.cos_full_notm}}-Instanz verwendet.  

Sie müssen der Service-ID spezifische Zugriffsrichtlinien zuweisen, die Berechtigungen für bestimmte Services einschränken oder sogar Berechtigungen für den Zugriff auf verschiedene Services kombinieren. Um beispielsweise den Zugriff auf ein einzelnes Bucket zu beschränken, müssen Sie sicherstellen, dass die Service-ID keine Richtlinien auf Instanzebene hat, entweder mithilfe der Konsole oder über die Befehlszeilenschnittstelle. 


Führen Sie die folgenden Schritte aus, um eine Service-ID mit Schreibberechtigungen für die {{site.data.keyword.cos_full_notm}}-Instanz zu erstellen: 

1. Wählen Sie im Dashboard die {{site.data.keyword.cos_full_notm}}-Instanz aus, in der Sie das Bucket erstellen möchten. 

2. Wählen Sie **Serviceberechtigungsnachweise** aus. Wählen Sie dann **Neuer Berechtigungsnachweis** aus. 

3. Geben Sie einen Namen ein, der einfach zuzuordnen ist. Sie können die Service-ID beispielsweise `activity-tracker-cos-serviceID` nennen.  

4. Wählen Sie die Rolle **Schreibberechtigter** aus. 

5. Klicken Sie auf **Hinzufügen**. 

    Eine neue Service-ID wird erstellt und zur Liste hinzugefügt.  

    **Hinweis:** Die Service-ID, die in der {{site.data.keyword.cloud_notm}} erstellt und in der IAM-Benutzerschnittstelle aufgelistet wird, hat einen generischen Namen. Der Name der Service-ID in der IAM-Benutzerschnittstelle wird dem Wert des Felds **iam_apikey_name** zugeordnet, das Sie in diesem Schritt über die Benutzerschnittstelle der COS-Service-ID erstellt haben. 
    
6. [Optional] Um die Service-ID zu sperren, sodass sie nicht gelöscht werden kann, klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)**. Suchen Sie nach der Service-ID. Wählen Sie dann die Aktion **Sperren** aus. 


Klicken Sie für die eben erstellte Service-ID auf **Berechtigungsnachweise anzeigen**. Es werden Informationen zur Service-ID angezeigt.  

* Kopieren Sie den API-Schlüssel. Dies ist der für das Feld **apikey** festgelegte Wert. 
* Kopieren Sie die Ressourceninstanz-ID. Dies ist der für das Feld **resource_instance_id** festgelegte Wert. 
* Kopieren Sie den Wert des Felds **iam_apikey_name**. 


## Schritt 5. Service-ID auf Schreibberechtigungen nur für das Bucket beschränken 
{: #archiving_step5}

Wenn Sie die Service-ID so beschränken möchten, dass sie nur über Schreibberechtigungen für ein Bucket verfügt, führen Sie die folgenden Schritte aus: 

1. Wählen Sie in der COS-Benutzerschnittstelle das Bucket aus. 

2. Wählen Sie im Bucketmenü den Eintrag **Richtlinien** aus. Die Seite *Bucketzugriffsrichtlinien* wird geöffnet. 

3. Wählen Sie **Service-IDs** aus. 

4. Suchen Sie im Feld **Service-ID auswählen** nach einer Service-ID namens '**auto-generated-serviceId-<ID, die Teil des iam_apikey_name-Werts ist>'. 

5. Wählen Sie die Service-ID aus. Wählen Sie dann in **Zugriffsrichtlinien** die Option **Schreibberechtigter** aus. 

6. Klicken Sie auf **Zugriffsrichtlinie erstellen**. 



## Schritt 6. Endpunkt auswählen
{: #archiving_step6}

Ein Endpunkt definiert, wo nach einem Bucket gesucht werden soll. Es gibt verschiedene Endpunkte, abhängig von der Region und dem Typ von Ausfallsicherheit. Weitere Informationen finden Sie unter [Regionen und Endpunkte auswählen](/docs/services/cloud-object-storage?topic=cloud-object-storage-endpoints#endpoints). 

Führen Sie die folgenden Schritte aus, um den Endpunkt für Ihr Bucket abzurufen. 

1. Melden Sie sich bei Ihrem {{site.data.keyword.cloud_notm}}-Konto an. 

    Klicken Sie auf [{{site.data.keyword.cloud_notm}}-Dashboard ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://cloud.ibm.com/login){:new_window}, um das {{site.data.keyword.cloud_notm}}-Dashboard zu starten. 

	Nachdem Sie sich mit Ihrer Benutzer-ID und Ihrem Kennwort angemeldet haben, wird das {{site.data.keyword.cloud_notm}}-Dashboard geöffnet. 

2. Wählen Sie im Dashboard die {{site.data.keyword.cos_full_notm}}-Instanz aus, in der Sie das Bucket erstellen möchten. 

3. Wählen Sie **Buckets** aus. Wählen Sie dann das Bucket aus, das Sie erstellt haben und in dem Sie Ereignisse archivieren möchten. 

4. Wählen Sie **Konfiguration** aus. 

5. Kopieren Sie einen der privaten Endpunkte.  



## Schritt 7. Einem Benutzer IAM-Richtlinien für die Archivierung von Ereignissen zuweisen
{: #archiving_step7}

In der folgenden Tabelle sind die Richtlinien aufgelistet, über die ein Benutzer verfügen muss, um das Archivieren von Ereignissen aus der {{site.data.keyword.at_full_notm}}-Webbenutzerschnittstelle in einem Bucket in einer {{site.data.keyword.cos_full_notm}}-Instanz zu konfigurieren: 

| Service                              | Rolle                      | Erteilte Berechtigung                  | 
|--------------------------------------|---------------------------|-------------------------------------|  
| `{{site.data.keyword.at_full_notm}}` | Plattformrolle: Anzeigeberechtigter   | Ermöglicht dem Benutzer, die Liste von Serviceinstanzen im Dashboard 'Beobachtbarkeit' anzuzeigen. |
| `{{site.data.keyword.at_full_notm}}` | Servicerolle: Manager   | Ermöglicht dem Benutzer, die Webbenutzerschnittstelle zu starten und Ereignisse in der Webbenutzerschnittstelle anzuzeigen.                             |
{: caption="Tabelle 2. IAM-Richtlinien" caption-side="top"} 

[Weitere Informationen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam#iam). 

Führen Sie die folgenden Schritte aus, um eine Benutzerberechtigung zum Archivieren von Ereignissen zuzuweisen.  

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie dann **Benutzer** aus. 
2. Wählen Sie in der Zeile für den Benutzer, dem Sie Zugriff zuweisen möchten, das Menü **Aktionen** aus und klicken Sie dann auf **Zugriff zuweisen**. 
3. Wählen Sie **Zugriff in einer Ressourcengruppe zuweisen** aus. 
4. Wählen Sie eine Ressourcengruppe aus. 
5. Wenn dem Benutzer noch keine Rolle für die ausgewählte Ressourcengruppe zugewiesen wurde, wählen Sie eine Rolle für das Feld **Zugriff für eine Ressourcengruppe zuweisen** aus.  

    Abhängig von der ausgewählten Rolle kann der Benutzer die Ressourcengruppe im Dashboard anzeigen, den Ressourcengruppennamen bearbeiten oder den Benutzerzugriff auf die Gruppe verwalten.  
    
    Sie können **Kein Zugriff** auswählen, wenn der Benutzer nur auf den {{site.data.keyword.at_full_notm}}-Service in der Ressourcengruppe zugreifen soll. 

6. Wählen Sie **IBM Log Analysis mit LogDNA** aus. 
7. Wählen Sie die Plattformrolle **Anzeigeberechtigter** aus. 
8. Wählen Sie die Servicerolle **Manager** aus. 
9. Klicken Sie auf **Zuweisen**. 



## Schritt 8. Archivierung für Ihre {{site.data.keyword.at_full_notm}}-Instanz konfigurieren
{: #archiving_step8}


Führen Sie die folgenden Schritte aus, um die Archivierung Ihrer {{site.data.keyword.at_full_notm}}-Instanz in einem COS-Bucket zu konfigurieren: 

1. Starten Sie die {{site.data.keyword.at_full_notm}}-Webbenutzerschnittstelle. [Weitere Informationen](/docs/services/Log-Analysis-with-LogDNA/view_logs.html#view_logs_step2). 

2. Wählen Sie das Symbol **Konfiguration** aus. Wählen Sie dann **Archivierung** aus.  

3. Wählen Sie **IBM Cloud Object Storage** aus. 

4. Wählen Sie das Bucket, den Endpunkt, den API-Schlüssel und die Instanz-ID für die Archivierung von Ereignissen aus. 

    <table>
      <caption>Tabelle 3. COS-Felder</caption>
      <tr>
         <th>Feld</th>
         <th>Wert</th>
      </tr>
      <tr>
         <td>Bucket</td>
         <td>Auf COS-Bucketnamen festlegen. </td>
      </tr>
      <tr>
         <td>Endpunkt</td>
         <td>Auf privaten Endpunkt des COS-Buckets festlegen. </td>
      </tr>
      <tr>
         <td>API-Schlüssel</td>
         <td>Auf den API-Schlüssel festlegen, der der COS-Service-ID zugeordnet ist. </td>
      </tr>
      <tr>
         <td>Instanz-ID</td>
         <td>Auf die COS-Instanz-ID festlegen. </td>
      </tr>
    </table>

5. Klicken Sie auf **Speichern**. 


Nachdem Sie die Konfiguration gespeichert haben, werden Ereignisse einmal pro Tag archiviert. 



