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


# Angepasste Ansichten erstellen
{: #views}

In der {{site.data.keyword.at_full_notm}}-Webbenutzerschnittstelle können Sie Such- und Filterkriterien anwenden, um die Ereignisse zu definieren, die in einer angepassten Ansicht angezeigt werden.
{:shortdesc}


## Voraussetzungen
{: #views_prereqs}

Prüfen Sie zunächst, dass Ihre Benutzer-ID über die Berechtigungen zum Starten der Webbenutzerschnittstelle und zum Anzeigen von Ereignissen verfügt. In der folgenden Tabelle sind die mindestens erforderlichen Rollen aufgeführt, die ein Benutzer aufweisen muss, um die {{site.data.keyword.at_full_notm}}-Webbenutzerschnittstelle zu starten und um Ereignisse anzuzeigen, zu suchen und zu filtern. 

| Rolle                      | Erteilte Berechtigung            |
|---------------------------|-------------------------------|  
| Plattformrolle: `Anzeigeberechtigter`     | Ermöglicht dem Benutzer, die Liste von Serviceinstanzen im Dashboard 'Beobachtbarkeit' anzuzeigen. |
| Servicerolle: `Leseberechtigter`      | Ermöglicht dem Benutzer, die Webbenutzerschnittstelle zu starten und Ereignisse in der Webbenutzerschnittstelle anzuzeigen.  |
{: caption="Tabelle 1. IAM-Rollen" caption-side="top"} 

Weitere Informationen zum Konfigurieren von Richtlinien für einen Benutzer finden Sie unter [Einem Benutzer oder einer Service-ID Benutzerberechtigungen erteilen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events).



## Schritt 1. Webbenutzerschnittstelle öffnen und Ansicht auswählen
{: #views_step1}

Führen Sie die folgenden Schritte aus:

1. [Zur Webbenutzerschnittstelle wechseln](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch)
2. Klicken Sie auf das Symbol **Ansichten** ![Konfigurationssymbol](images/views.png).
3. Wählen Sie **Alles** oder eine Ansicht aus. 


## Schritt 2. Menge von Ereignissen, die über eine Ansicht angezeigt werden sollen, mittels Anwenden einer Suchabfrage auswählen
{: #views_step2}

Zum Suchen nach bestimmten Ereignissen können Sie eine Suchabfrage anwenden. 

* Sie können einfache Suchen (einzelner Begriff), Verbundsuchen (mehrere Suchbegriffe und Operatoren), Feldsuchen, falls die Protokollzeile geparst werden kann, und mehr ausführen. Weitere Informationen finden Sie in der LogDNA-Dokumentation unter [How to Search Logs ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://docs.logdna.com/docs/search){:new_window}.
* Bei AND- und OR-Operatoren muss die Groß-/Kleinschreibung beachtet und sie müssen großgeschrieben werden.

Sie können nur Ereignisse für die Anzahl der Tage durchsuchen, die über den Serviceplan der Instanz angegeben wurden.
{: important}


Führen Sie die folgenden Schritte aus:
1. Geben Sie eine Suchabfrage ein. 
2. Drücken Sie die Eingabetaste. 

Beachten Sie beim Anwenden einer Abfrage, dass sich der Name der Ansicht in **Nicht gespeicherte Ansicht** ändert.


### Abfrage nach Ereignissen, die von einem Service generiert werden
{: #views_step1_1}

Zum Herausfiltern von Ereignissen für einen bestimmten Service müssen Sie die folgende Abfrage eingeben:

```
_supertenant:SERVICENAME
```
{: codeblock}

Dabei ist `SERVICENAME` der Name des Service in {{site.data.keyword.cloud_notm}}.

In der folgenden Tabelle sind die Basisservices aufgelistet:

| Ereignisse, die generiert werden durch               | Wert                         | Beispielabfrage                     |
|--------------------------------------------|-------------------------------|----------------------------------|
| [IAM-Zugriffs-Management-Service](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_policies)  | `iam-am`  | `_supertenant:iam-am`    |
| [IAM-Identitätsservice](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_login)   | `iam-identity`    | `_supertenant:iam-identity`  |
| [IAM-Zugriffsgruppenservice](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_access)  | `iam-groups`  | `_supertenant:iam-groups`     |
| [Ressourcencontrollerservice](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-cloud_services#platform_core_integrated)   | `BSS`  | `_supertenant:BSS`  |            
{: caption="Tabelle 2. Abfrage nach Servicename" caption-side="top"}

### Abfrage nach Menge von Ereignissen, die von einem Service generiert werden
{: #views_step1_2}

Wenn durch einen Service unterschiedliche Typen von Ereignissen generiert werden, können Sie die folgende Abfrage eingeben:

```
_supertenant:SERVICENAME [(action TYPEOFACTION)] 
```
{: codeblock}

Dabei gilt: 

* `SERVICENAME` ist der Name des Service in {{site.data.keyword.cloud_notm}}.
* `TYPEOFACTION` ist eine zusammengesetzte Abfrage, bei der Sie AND- und OR-Operatoren sowie `-` zum Ausschluss von Daten verwenden können. Achtung: Bei den `AND`- und `OR`-Operatoren muss die Groß-/Kleinschreibung beachtet und sie müssen großgeschrieben werden.


Die folgende Tabelle zeigt Beispiele zum Abfragen einer Gruppe von Ereignissen, die von einem Service generiert werden:

| Ereignisse, die generiert werden durch               | Art der Ereignisse     | Beispielabfrage                     |
|--------------------------------------------|--------------------|---------------------------------|
| `IAM-Identitätsservice`   | [Anmeldeereignisse](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_login) | `_supertenant:iam-identity (action login)`  |
| `IAM-Identitätsservice`   | [Ereignisse für API-Schlüssel](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_apikeys) | `_supertenant:iam-identity (action user-apikey) -(action login)`  |
| `IAM-Identitätsservice`   | [Ereignisse für Kontoservice-ID](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_serviceids) | `_supertenant:iam-identity (action account-serviceid)`  |
| `Ressourcencontroller`                      | [Bereitstellung und Verwaltung von Serviceinstanzen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#rc_provision)   | `_supertenant:BSS (action instance)`  | 
| `Ressourcencontroller`                      | [Benutzer im Konto verwalten](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_acc_mgt#at_events_acc_mgt_users)   |  `_supertenant:BSS (action user-management.user)`  |                   |
{: caption="Tabelle 3. Beispiele komplexerer Abfragen" caption-side="top"}


### Abfrage nach Ereignissen mit einer bestimmten Aktion
{: #views_step1_3}

Jedes Ereignis verfügt über ein Feld **Aktion** mit Informationen zu der Aktion, die das Ereignis ausgelöst hat. Sie können die folgende Abfrage eingeben, um nach allen Ereignissen mit der gleichen Aktion zu suchen:

```
action ACTIONVALUE
```
{: codeblock}

Dabei steht `ACTIONVALUE` für den Wert des Aktionsfelds oder einen Teil des Werts.

In der folgenden Tabelle sind Beispiele für Abfragen unterschiedlicher Aktionen zu sehen:

| Aktion                 | Beispielabfrage                     |
|------------------------|----------------------------------|
| Service bereitstellen    | `action instance.create`         |
| Instanz entfernen      | `action instance.delete`         |
| Benutzer hinzufügen             | `action user-management.user.create` |
{: caption="Tabelle 4. Beispiele von Abfragen nach Aktionstyp" caption-side="top"}



### Abfrage nach Ereignissen, deren Aktion fehlschlägt
{: #views_step1_4}

Wenn eine angeforderte Aktion fehlschlägt, wird das Feld **outcome** auf **failure** gesetzt. Sie können die folgende Abfrage eingeben, um nach dieser Art von Ereignissen zu suchen:

```
outcome failure
```
{: codeblock}


### Abfrage nach Ereigniskritikalität
{: #views_step1_5}

Jedes Ereignis verfügt über ein Feld **severity**, in dem die Bedrohung definiert ist, die eine Aktion für eine Cloud bedeuten könnte. 

Gültige Werte sind *normal*, *warning* und *critical*. 
* **normal** ist für Routineaktionen in der Cloud festgelegt. Dazu zählt beispielsweise das Starten einer Instanz oder das Aktualisieren eines Tokens. 
* **warning** ist für Aktionen festgelegt, bei denen eine Cloudressource aktualisiert wird oder ihre Metadaten geändert werden. Dazu zählt beispielsweise das Aktualisieren der Version eines Workerknotens, das Umbenennen von Zertifikaten oder das Umbenennen einer Serviceinstanz. 
* **critical** ist für Aktionen festgelegt, die die Sicherheit in der Cloud betreffen. Dazu zählt beispielsweise das Ändern der Berechtigungsnachweise eines Benutzers, das Löschen von Daten oder der unbefugte Zugriff für die Arbeit mit einer Cloudressource.

Sie können die folgende Abfrage eingeben, um nach dieser Art von Ereignissen zu suchen:

```
severity VALUE
```
{: codeblock}

Dabei kann `VALUE` auf *normal*, *warning* oder *critical* gesetzt werden.

Wenn Sie beispielsweise kritische Ereignisse abfragen möchten, können Sie die folgende Abfrage ausführen:

```
severity critical
```
{: codeblock}



## Schritt 3. Angepasste Ansicht erstellen
{: #views_step3}

Nachdem Sie die Suchabfrage auf die Ansicht **Alles** oder auf eine vorhandene angepasste Ansicht angewendet haben, führen Sie die folgenden Schritte aus, um die Ausgabe als angepasste Ansicht zu speichern: 

1. Klicken Sie in der Webbenutzerschnittstelle auf **Nicht gespeicherte Ansicht**.
2. Wählen Sie **Als neue Ansicht speichern/Als neuen Alert speichern** aus. Die Seite *Neue Ansicht erstellen* wird geöffnet.
3. Geben Sie einen Namen für die Ansicht im Feld *Name* ein.
4. Fügen Sie optional eine Kategorie hinzu. Geben Sie einen Namen ein und klicken Sie dann auf **Als neue Ansichtskategorie hinzufügen**.
5. Hängen Sie optional einen Alert an. Ein neuer Abschnitt wird angezeigt, in dem Sie den Alert konfigurieren können.
6. Klicken Sie auf **Ansicht speichern**.


## Schritt 4. Anzeige von Ereignislinien über eine Ansicht anpassen
{: #views_step4}

Es gibt verschiedene Optionen zum Anpassen der Anzeige von Daten in einer Ansicht:
* Sie können die Eigenschaften einer Ansicht ändern, Sie können eine Ansicht umbenennen, ihre Beschreibung hinzufügen oder ändern und ein bestimmtes Zeilenformat anwenden.
* Sie können das `Protokollformat` im Abschnitt mit den Benutzervorgaben ändern.
* Sie können eine Zeilenvorlage aus dem Abschnitt *Tools* anwenden. Beachten Sie, dass dies eine andere Zeilenkonfiguration überschreibt. Wenn Sie **Diese Einstellungen beibehalten** auswählen, werden in allen Ansichten in der Benutzerschnittstelle Daten pro Zeilenformat angezeigt, das in diesem Abschnitt angegeben ist.
* Sie können auf Begriffe oder Zeichenfolgen eine Farbe anwenden, indem Sie **Begriffe hervorheben** im Abschnitt **Tools** festlegen.



### Zeilenformat über die Seite mit den Ansichtseigenschaften ändern
{: #views_step4_1}

Führen Sie die folgenden Schritte aus, um das Format einer Ereigniszeile in einer einzelnen Ansicht zu ändern:

1. Wählen Sie in Ihrer Ansicht die Option **Ansichtseigenschaften bearbeiten** aus. Die Seite *Ansichtseigenschaften bearbeiten* wird geöffnet.

2. Geben Sie im Abschnitt **Angepasste %LINE Vorlage** ein angepasstes Zeilenformat ein. Die Standardeinstellung ist `{{line}}`.

    Weitere Informationen zu den Richtlinien für Zeilenvorlagen finden Sie im Abschnitt zu den [Richtlinien](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_line).

3. Klicken Sie auf ** Eigenschaften speichern*.



### Zeilenformat über den Abschnitt für die Benutzervorgaben ändern
{: #views_step4_2}

Im Abschnitt **BENUTZERVORGABEN** können Sie die Reihenfolge der Datenfelder ändern, die in einer Zeile angezeigt werden.

Führen Sie die folgenden Schritte aus, um das Format einer Ereigniszeile zu ändern:

1. Klicken Sie in der Webbenutzerschnittstelle auf das Symbol **Konfiguration** ![Konfigurationssymbol](images/admin.png "Administratorsymbol").
2. Wählen Sie **BENUTZERVORGABEN** aus. Ein neues Fenster wird geöffnet.
3. Wählen Sie **Protokollformat** aus.
4. Ändern Sie den Abschnitt *Zeilenformat* Ihren Anforderungen entsprechend. Ziehen Sie die Felder.


### Zeilenformat über die Zeilenvorlage im Abschnitt 'Tools' ändern
{: #views_step4_3}

Führen Sie die folgenden Schritte aus, um das Format einer Ereigniszeile zu ändern:

1. Klicken Sie in der Ansicht auf das Symbol für **Tools** ![Symbol für 'Tools'](images/tool.png "Symbol für 'Tools'").
2. Geben Sie im Feld **Zeilenvorlage** Ihr benutzerdefiniertes Zeilenformat ein. Weitere Informationen zu den Richtlinien für Zeilenvorlagen finden Sie im Abschnitt zu den [Richtlinien](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_line).
3. Klicken Sie optional auf **Diese Einstellungen beibehalten**, um das Zeilenformat auf alle Ansichten anzuwenden.



### Begriffe hervorheben
{: #view_events_step4_4}

Führen Sie die folgenden Schritte aus, um Begriffe in einer Ansicht hervorzuheben:

1. Klicken Sie in der Ansicht auf das Symbol für **Tools** ![Symbol für 'Tools'](images/tool.png "Symbol für 'Tools'").
2. Geben Sie im Feld **Zeilenvorlage** ein Wort oder eine Zeichenfolge im Abschnitt **Begriffe hervorheben** ein.
3. Klicken Sie optional auf **Diese Einstellungen beibehalten**, um diese Einstellungen auf alle Ansichten anzuwenden.



## Name und Beschreibung einer angepassten Ansicht ändern
{: #views_step5}

Sie können eine Ansicht umbenennen. Sie können die Beschreibung einer Ansicht hinzufügen oder ändern.


Führen Sie die folgenden Schritte aus:

1. Wählen Sie in Ihrer Ansicht die Option **Ansichtseigenschaften bearbeiten** aus. Die Seite *Ansichtseigenschaften bearbeiten* wird geöffnet.

    Sie können die Ansicht umbenennen, die Beschreibung der Ansicht hinzufügen oder ändern und ein benutzerdefiniertes Zeilenformat anwenden.

2. Geben Sie im Abschnitt **Ansicht umbenennen** einen neuen Namen ein, um die Ansicht umzubenennen.

3. Geben Sie die Beschreibung im Abschnitt **Beschreibung** ein oder ändern Sie sie dort.

4. Klicken Sie auf **Eigenschaften speichern**.



## Richtlinien, die Zeilenvorlagen definieren
{: #views_line}

Beachten Sie die folgenden Richtlinien, die Sie beim Definieren einer Zeilenvorlage anwenden müssen:
* Verwenden Sie die Variablen des Typs Mustache-Stil `{{field.name}}` oder Bash-Stil `${field.name}`, um Ihre Vorlage zu erstellen. 
* Verwenden Sie `{{line}}` oder `$@`, um auf die ursprüngliche Zeile zu verweisen. 
* Alle anderen Zeichen oder Zeichenfolgen werden als Textliteral interpretiert. 


Sie können beispielsweise eine Zeilenvorlage wie folgt definieren, um diese Felder für die einzelnen Ereignisse in einer Ansicht zu sehen: `{{initiator.id}} -- {{action}} -- {{message}}`.


