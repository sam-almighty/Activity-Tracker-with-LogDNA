---

copyright:
  years: 2019
lastupdated: "2019-06-03"

keywords: IBM Cloud, LogDNA, Activity Tracker, monitor events

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


# Aktivitäten in Ihrem Konto überwachen
{: #monitor_events}

Sie können Aktivitäten in Ihrem Konto über die Webbenutzerschnittstelle von {{site.data.keyword.at_full_notm}} überwachen. Sie können auch Gruppen von Ereignissen exportieren, um sie in einem anderen Kontext zu analysieren.
{:shortdesc}

Sie können nur 1 Instanz des {{site.data.keyword.at_full_notm}}-Service pro Position bereitstellen. Um die Aktivität in Ihrem Konto zu überwachen, müssen Sie daher möglicherweise Ereignisse über unterschiedliche {{site.data.keyword.at_full_notm}}-Instanzen ansehen und analysieren. 

In der {{site.data.keyword.cloud_notm}} können Sie auf das **Menüsymbol** ![Menüsymbol](../icons/icon_hamburger.svg) > **Beobachtbarkeit** > **Activity Tracker** klicken, um das Dashboard anzuzeigen, in dem alle Instanzen aufgelistet sind, die in dem Konto bereitgestellt werden. 
{: tip}

Um Ereignisse anzuzeigen, müssen Sie [die Webbenutzerschnittstelle an der Position starten](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch), an der Ereignisse zur Verfügung stehen. Sie können dann mit Ansichten arbeiten, um diese Ereignisse zu überwachen. Sie können Ereignisse in Ihrer Ortszeit anzeigen.

Sie können die Ereignisse auswählen, die in einer Ansicht angezeigt werden, indem Sie eine Zeitmarke und/oder eine Suchabfrage anwenden.

* Sie können eine Suchabfrage anwenden und als benutzerdefinierte Ansicht speichern. 
* Sie können eine Zeitmarke anwenden, um zu einer bestimmten Uhrzeit in Ihrem Ereignisprotokoll zu springen. 

Wenn Sie eine Suchabfrage anwenden, können Sie diese Ansicht für eine spätere Wiederverwendung speichern. Zeitmarken werden jedoch nicht gespeichert.

Beachten Sie, dass Instanzen unterschiedliche Servicepläne und folglich unterschiedliche Datenaufbewahrungszeiten aufweisen können, durch die die Anzahl an Tagen festgelegt wird, die Ihnen die Daten für die Suche über die Webbenutzerschnittstelle zur Verfügung stehen. Es ist nur möglich, Ereignisse innerhalb Ihrer Aufbewahrungsdauer zu überwachen. Unterschiedliche [Servicepläne](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan) weisen unterschiedliche Aufbewahrungsdauern auf.


## Globale und standortbezogene Ereignisse überwachen
{: #mon_def_event_type}

Ereignisse können als globale oder standortbezogene Ereignisse klassifiziert werden. Der Typ von Ereignis bestimmt, wo Sie Ereignisse überwachen müssen.

Das allgemeine Motiv für globale Ereignisse ist eine einzelne, synchronisierte Position, an der Kontoadministratoren bestimmte Typen von Aktivitäten in der Cloud überwachen können. Standortbezogene Ereignisse hingegen bleiben für die Position lokal, an der ein abonnierter Cloud-Service gehostet wird.
{: note}

### Globale Ereignisse
{: #mon_def_global}

**Globale Ereignisse** melden Aktivitäten in Ihrem Konto, die sich auf Daten und Ressourcen beziehen, die im Allgemeinen über alle Regionen hinweg synchronisiert werden.
{: note}

Die Services, mit denen Benutzer interagieren, sind in den zentralen Bestandteil der globalen {{site.data.keyword.cloud_notm}}-Funktionalität integriert.

Die globale Domäne ist auf **Frankfurt** festgelegt. Globale Ereignisse werden erfasst und über die in Frankfurt konfigurierte {{site.data.keyword.at_full_notm}}-Instanz zur Verfügung gestellt.

Beispiel: Wenn ein Kontoadministrator Benutzer zur Teilnahme an dem Konto einlädt, kann dies von jeder Position in der Cloud aus geschehen. Es kann ein Benutzer aus der Position Frankfurt eingeladen werden, der Berechtigungen für die Arbeit mit einem Service erhält, der in Dallas bereitgestellt wird. Was ist das Ziel des Ereignisses? Das Ziel ist eine globale Domäne, die von Herkunft oder Position her agnostisch ist und an der die Informationen regionsübergreifend synchronisiert werden.
    
Ein weiteres Beispiel sind Ressourcencontrollerereignisse; diese werden in IBM Cloud ebenfalls als globale Ereignisse betrachtet. Diese Ereignisse melden die Bereitstellung und Löschung von Serviceinstanzen in der Cloud. Zwar wird eine Serviceinstanz an einer bestimmten Position erstellt, doch werden Ressourcencontrolleraktionen als globale Ereignisse gemeldet, um eine Einzelansicht aller Serviceinstanzen anzubieten, die in dem Konto bereitgestellt werden.


### Standortbezogene Ereignisse
{: #mon_def_location}

**Standortbezogene Ereignisse** melden Aktivitäten in Ihrem Konto, die von {{site.data.keyword.cloud_notm}}-Services generiert werden, die an einer {{site.data.keyword.IBM_notm}}-Rechenzentrumsposition wie Dallas oder Frankfurt gehostet werden.
{: note}


Wenn Kunden und Anwendungen mit Cloud-Services interagieren, die an einer Position gehostet werden, werden standortbezogene Ereignisse erfasst und über die an dieser Position konfigurierte {{site.data.keyword.at_full_notm}}-Instanz zur Verfügung gestellt. Sie zeigen diese Ereignisse durch [Starten der Webbenutzerschnittstelle](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch) an dieser Position an.
    
Durch standortbezogene Ereignisse wird die Datenlokalität für diese Services gepflegt, die an dieser Cloud-Position ausgeführt werden.

Wenn Sie beispielsweise den {{site.data.keyword.cloudcerts_short}}-Service an der Position 'Frankfurt' bereitstellen, werden Ereignisse dieser Instanz an die {{site.data.keyword.at_full_notm}}-Instanz gesendet, die in Frankfurt bereitgestellt wird. Wenn Sie den {{site.data.keyword.cloudcerts_short}}-Service an der Position 'Dallas' bereitstellen, werden Ereignisse dieser Instanz an die {{site.data.keyword.at_full_notm}}-Instanz gesendet, die in Dallas bereitgestellt wird. In beiden Fällen werden Ereignisse in Bezug auf die Region und Position des abonnierten Cloud-Service als lokal behandelt.




## Ereignisse über die Standardansicht überwachen
{: #mon_def_view}

Der Name der Standardansicht lautet **Alles**.  

Sobald Sie die Webbenutzerschnittstelle an einer Position öffnen, ist dies die Ansicht, die Sie sehen. 

Alle Ereignisse in Ihrer Instanz werden über diese Ansicht angezeigt.

Informationen zum Anzeigen von Ereignissen über diese Ansicht finden Sie im Abschnitt zum [Anzeigen von Ereignissen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-view_events#view_events_step1).

## Ereignisse über benutzerdefinierte Ansichten überwachen
{: #mon_cus_view}

Sie möchten möglicherweise eine Reihe von Ereignissen in Ihrem Konto überwachen. Zur Analyse einer Teilmenge von Ereignissen können Sie benutzerdefinierte Ansichten erstellen. 

Zur Erstellung einer benutzerdefinierten Ansicht müssen Sie eine Suchabfrage anwenden, in der definiert wird, welche Ereignisse über die Ansicht angezeigt werden sollen. [Weitere Informationen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-view_events#view_events_step2).

Sie können [Alerts anhängen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-alerts), und zwar an eine benutzerdefinierte Ansicht. 

Sie können [Daten exportieren](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-export), und zwar aus einer benutzerdefinierten Ansicht. 

Sie können [die Ansicht umbenennen und die Beschreibung einer Ansicht hinzufügen oder ändern](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_step5). 

Sie können [eine Zeilenvorlage auf eine Ansicht anwenden](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_step4), um die Art und Weise der Anzeige der Daten anzupassen. 

Sie können Ansichten organisieren, indem Sie sie in **Kategorien** zusammenfassen.


## Ereignisse anhand eines Zeitrahmens überwachen
{: #mon_time_view}

Sie können Ereignisse innerhalb eines bestimmten Zeitrahmens überwachen.

Sie können die Ereignisse auswählen, die in einer Ansicht angezeigt werden, indem Sie [einen Zeitrahmen anwenden](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-view_events#view_events_step3).

Sie können eine Zeitmarke anwenden, indem Sie eine absolute Zeit, eine relative Zeit oder einen Zeitbereich angeben.

* Durch eine absolute Zeit wird ein genauer Zeitpunkt in Ihrem Ereignisprotokoll angegeben, z. B. `May 20 7:00pm` (20. Mai, 19 Uhr).
    
* Durch eine relative Zeit wird ein nicht genauer Zeitrahmen angegeben, z. B. `2 days ago` (vor 2 Tagen).

* Durch einen Zeitraum wird ein Zeitintervall angegeben, z. B. `yesterday 10am to yesterday 11am` (gestern 10 Uhr bis gestern 11 Uhr).



## Alerts konfigurieren
{: #mon_alerts}

Es gibt Szenarios, in denen Sie benachrichtigt werden möchten, wenn bestimmte Ereignisse in Ihrem Konto generiert werden. Sie möchten z. B. benachrichtigt werden, wenn die Anzahl der fehlgeschlagenen Aktionen einen von Ihnen angegebenen Schwellenwert überschreitet. 

In der {{site.data.keyword.at_full_notm}}-Webbenutzerschnittstelle können Sie Suchkriterien anwenden, um die Ereignisse zu definieren, die in einer angepassten Ansicht angezeigt werden. Anschließend können Sie einen Alert an diese Ansicht anhängen, um benachrichtigt zu werden, falls es zu dieser Bedingung kommt. Ein Klingelsymbol wird mit der Ansicht angezeigt, um darauf hinzuweisen, dass dieser Ansicht ein Alert angehängt ist.

* Sie können [einen einzigen Alert anhängen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-alerts#alerts_step4), und zwar pro Ansicht.
* Sie können Bedingungen konfigurieren, die von der Anzahl der Ereigniszeilen abhängig sind, die mit der Suchabfrage in der Ansicht und/oder einer Frequenz übereinstimmen.
* Sie können mehrere Benachrichtigungskanäle für einen Alert definieren. Informationen zu den unterstützten Kanälen finden Sie unter [Alertbenachrichtigungskanäle](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-channels).
* Sie können eine [**Voreinstellung** definieren](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-alerts#alerts_step3). Eine Voreinstellung ist eine Alertvorlage, die Sie an eine Reihe von Ansichten anhängen können. Mithilfe von Voreinstellungen können Sie Vorlagen definieren, die Benutzer wiederverwenden können, wenn sie einen Alert an eine Ansicht anhängen. 
* Sie können Alerts stumm schalten. 
* Sie können [einen Alert von einer Ansicht abhängen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-alerts#alerts_delete_view). 


### Alerttypen
{: #mon_alerts_types}

Sie können die folgenden Typen von Alerts konfigurieren:

* **Alerttyp für das Vorhandensein**: Sie können diesen Typ von Alert verwenden, um eine Benachrichtigung zu erhalten, wenn die Anzahl der in einer Ansicht angezeigten Ereignisse die erwartete Anzahl überschreitet. 
* **Alerttyp für das Vorhandensein**: Sie können diesen Typ von Alert verwenden, um eine Benachrichtigung zu erhalten, wenn die Anzahl der in einer Ansicht angezeigten Ereignisse die erwartete Anzahl unterschreitet oder null ist. 

Sie verfügen z. B. möglicherweise über eine Ansicht, in der Ereignisse zu sehen sind, die die Löschung von Serviceinstanzen in Ihrem Konto melden. Für Sie ist die Löschung der Serviceinstanzen unerwartet. Sie können einen *Alert für das Vorhandensein* konfigurieren, durch den ein Alert ausgelöst wird, wenn in der Ansicht ein oder mehrere Ereignisse zu sehen sind.

Der Alert für das Nichtvorhandensein wird aktiviert, nachdem ein Ereignis in der Ansicht angezeigt wird.
{: note}


### Alertbedingungen
{: #mon_alerts_conditions}

Sie können alle folgenden Bedingungen für einen Alert konfigurieren:

* **Frequenz**: Diese Bedingung legen Sie fest, um anzugeben, wie oft ein Alert ausgelöst werden soll. Gültige Werte sind: 30 Sekunden, 1 Minute, 5 Minuten, 15 Minuten, 30 Minuten, 1 Stunde, 6 Stunden, 12 Stunden, 24 Stunden
* **Ereigniszeilenzähler**: Diese Bedingung legen Sie fest, um die Anzahl von Ereigniszeilen anzugeben, die mit den Filter- und Suchkriterien der Ansicht übereinstimmen. Wenn die angegebene Anzahl von Ereigniszeilen erreicht wird, wird ein Alert ausgelöst.

Sie können entscheiden, ob beide Bedingungen geprüft werden sollen oder nur eine. Falls beide Bedingungen festgelegt sind, wird ein Alert ausgelöst, wenn einer der Schwellenwerte erreicht wird. 

Wenn Sie den *Ereigniszeilenzähler* so festlegen, dass dies die einzige Bedingung ist, durch die ein Alert ausgelöst wird, beachten Sie, dass die von Ihnen bei der Konfiguration der Bedingung festgelegte Frequenz die Zeit bestimmt, die es dauert, bis die Alertbedingung nach dem ausgelösten Alert zurückgesetzt wird.
{: note}

Sie können beispielsweise einen Alert konfigurieren, der nach 30 Sekunden ausgelöst wird oder wenn 100 Ereigniszeilen erreicht wurden, die mit den Filter- und Suchkriterien der Ansicht übereinstimmen.



## Ereignisse exportieren
{: #mon_export}

Sie benötigen möglicherweise Zugriff auf eine Reihe von Ereignissen außerhalb der Webbenutzerschnittstelle, um ein Problem detaillierter zu untersuchen. 

Sie können Daten im JSONL-Format aus einer {{site.data.keyword.at_full_notm}}-Instanz in eine lokale Datei exportieren. 

Sie können Ereignisse über eine Ansicht in der Webbenutzerschnittstelle oder programmgesteuert über eine REST-API exportieren.

Berücksichtigen Sie die folgenden Informationen, wenn Sie Ereignisse exportieren:
* Sie exportieren einen Satz von Ereigniseinträgen. 
* Um den Datensatz, den Sie exportieren möchten, zu definieren, können Sie Filter und Suchen anwenden. Sie können auch den Zeitraum angeben. 
* Sie können maximal 20.000 Zeilen exportieren.

### Über die REST-API
{: #mon_export_api}

Sie können Ereignisse programmgesteuert über die REST-API von LogDNA exportieren. [Weitere Informationen](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-export#export_api).

Beachten Sie beim programmgesteuerten Exportieren von Ereignissen die folgenden Informationen:

* Sie können auswählen, ob eine E-Mail gesendet werden soll oder ob Ereignisse in Ihr Terminal gestreamt werden sollen.
* Sie müssen einen Serviceschlüssel verwenden, der für die Übergabe der Berechtigungsnachweise genutzt wird, die wiederum für einen REST-API-Aufruf für den Export verwendet werden. 

    Sie müssen die Rolle **Manager** für die {{site.data.keyword.at_full_notm}}-Instanz oder den Service innehaben, um Serviceschlüssel in der Webbenutzerschnittstelle anzuzeigen und zu generieren.


### Über eine Ansicht in der Webbenutzerschnittstelle
{: #mon_export_ui}

Sie können Ereignisse über eine Ansicht in der Webbenutzerschnittstelle exportieren. 

In der Webbenutzerschnittstelle können Sie eine Ansicht auswählen, in der die Daten angezeigt werden, die Sie exportieren möchten. Für diese Ansicht müssen Sie die Task zum **Exportieren von Zeilen** auswählen. Sie müssen einen Zeitraum angeben und angeben, ob neuere oder ältere Zeilen exportiert werden sollen. Anschließend können Sie den Export anfordern. 

Nachdem Sie eine Anforderung eingereicht haben, erhalten Sie eine E-Mail an Ihre E-Mail-Adresse mit einem Link zu einer komprimierten Datei, die die Daten enthält. 
* Um diese Daten abzurufen, müssen Sie auf den Link klicken und die komprimierte Datei herunterladen. 
* Die komprimierte Datei mit den Daten, die Sie exportieren möchten, ist maximal 48 Stunden verfügbar. 

[Weitere Informationen zum Exportieren von Ereignissen über die Webbenutzerschnittstelle](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-export#export_ui).








