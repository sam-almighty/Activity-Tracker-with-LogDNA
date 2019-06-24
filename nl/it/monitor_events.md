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


# Monitoraggio dell'attività nel tuo account
{: #monitor_events}

Puoi monitorare l'attività nel tuo account tramite l'IU web {{site.data.keyword.at_full_notm}}. Puoi anche esportare insiemi di eventi per analizzarli in un contesto diverso.
{:shortdesc}

Esiste 1 istanza del servizio {{site.data.keyword.at_full_notm}} per ogni ubicazione. Pertanto, per monitorare l'attività nel tuo account, potresti dover visualizzare e analizzare gli eventi attraverso le diverse istanze {{site.data.keyword.at_full_notm}}. 

In {{site.data.keyword.cloud_notm}}, puoi fare clic sull'icona **Menu** ![Icona Menu](../icons/icon_hamburger.svg) > **Osservabilità** > **Activity Tracker** per visualizzare il dashboard in cui sono elencate tutte le istanze di cui è stato eseguito il provisioning nell'account.
{: tip}

Per visualizzare gli eventi, devi [avviare l'IU web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch) nell'ubicazione in cui sono disponibili gli eventi. Quindi, puoi utilizzare le viste per monitorare quegli eventi. Gli eventi vengono visualizzati nella tua ora locale.

Puoi selezionare gli eventi visualizzati tramite una vista applicando una data/ora, una query di ricerca o entrambe.

* Puoi applicare una query di ricerca e salvarla come vista personalizzata. 
* Puoi applicare una data/ora per passare a un'ora specifica nel tuo log eventi. 

Quando applichi una query di ricerca, puoi salvare tale vista per riutilizzarla in seguito. Tuttavia, le date/ore non vengono salvate.

Tieni presente che le istanze potrebbero avere piani di servizio diversi e, di conseguenza, diversi periodi di conservazione dei dati che determinano il numero di giorni in cui hai dati disponibili per la ricerca attraverso l'IU web. Puoi monitorare solo gli eventi nel tuo periodo di conservazione. [Piani di servizio](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan) diversi hanno diversi periodi di conservazione.


## Monitoraggio di eventi globali e basati sull'ubicazione
{: #mon_def_event_type}

Gli eventi possono essere classificati come globali o basati sull'ubicazione. Il tipo di evento determina dove devi monitorare gli eventi.

Il tema comune per gli eventi globali è un'unica ubicazione sincronizzata in cui gli amministratori degli account possono monitorare determinati tipi di attività nel cloud. Al tempo stesso, gli eventi basati sull'ubicazione rimangono locali nell'ubicazione in cui è ospitato un servizio cloud sottoscritto.
{: note}

### Eventi globali
{: #mon_def_global}

Gli **eventi globali** segnalano le attività nel tuo account relative a dati e risorse generalmente sincronizzati in tutte le regioni.
{: note}

I servizi con cui gli utenti interagiscono sono integrati nel nucleo dell'esperienza {{site.data.keyword.cloud_notm}} globale.

Il dominio globale è impostato a **Francoforte**. Gli eventi globali vengono acquisiti e resi disponibili tramite l'istanza {{site.data.keyword.at_full_notm}} configurata a Francoforte.

Ad esempio, quando gli amministratori dell'account invitano gli utenti a unirsi all'account, possono farlo da qualsiasi ubicazione nel cloud. Potrebbero invitare un utente che si trova a Francoforte e concedergli le autorizzazioni per lavorare con un servizio di cui è stato eseguito il provisioning a Dallas. Dove devono essere inviati gli eventi? La risposta è un dominio globale che è indipendente dall'origine o dall'ubicazione e in cui le informazioni sono sincronizzate in tutte le regioni.
    
Come altro esempio, gli eventi del controller delle risorse sono considerati eventi globali in IBM Cloud. Questi eventi segnalano il provisioning e l'eliminazione di istanze del servizio in tutto il cloud. Anche se un'istanza del servizio viene creata in'ubicazione specifica, le azioni del controller delle risorse vengono segnalate come eventi globali per offrire un'unica vista di tutte le istanze del servizio di cui viene eseguito il provisioning nell'account.


### Eventi basati sull'ubicazione
{: #mon_def_location}

Gli **eventi basati sull'ubicazione** segnalano l'attività nel tuo account generata dai servizi {{site.data.keyword.cloud_notm}} che sono ospitati in un'ubicazione del data center {{site.data.keyword.IBM_notm}}, come Dallas o Francoforte.
{: note}


Quando i client e le applicazioni interagiscono con i servizi cloud ospitati in un'ubicazione, gli eventi basati sull'ubicazione vengono acquisiti e resi disponibili tramite l'istanza {{site.data.keyword.at_full_notm}} configurata in tale ubicazione. Visualizzi questi eventi [avviando l'IU web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch) in quella ubicazione.
    
Gli eventi basati sull'ubicazione mantengono la località dei dati nei servizi che vengono eseguiti in quella ubicazione cloud.

Ad esempio, se esegui il provisioning del servizio {{site.data.keyword.cloudcerts_short}} nell'ubicazione di Francoforte, gli eventi provenienti da tale istanza verranno inviati all'istanza {{site.data.keyword.at_full_notm}} di cui si è eseguito il provisioning a Francoforte. Se esegui il provisioning del servizio {{site.data.keyword.cloudcerts_short}} nell'ubicazione di Dallas, gli eventi provenienti da tale istanza verranno inviati all'istanza {{site.data.keyword.at_full_notm}} di cui si è eseguito il provisioning a Dallas. In entrambi i casi, gli eventi vengono mantenuti locali nella regione e nell'ubicazione del servizio cloud sottoscritto.




## Monitoraggio degli eventi tramite la vista predefinita
{: #mon_def_view}

La vista predefinita è denominata **Everything**. 

Non appena apri l'IU web in una ubicazione, questa è la vista che vedi. 

Tutti gli eventi nella tua istanza vengono visualizzati attraverso questa vista.

Per informazioni su come visualizzare gli eventi attraverso questa vista, vedi [Visualizzazione degli eventi](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-view_events#view_events_step1).

## Monitoraggio degli eventi tramite le viste personalizzate
{: #mon_cus_view}

Potresti voler monitorare un insieme di eventi nel tuo account. Per analizzare un sottoinsieme di eventi, puoi creare delle viste personalizzate. 

Per creare una vista personalizzata, devi applicare una query di ricerca che definisce quali eventi visualizzare attraverso la vista. [Ulteriori informazioni](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-view_events#view_events_step2).

Puoi [collegare avvisi](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-alerts) a una vista personalizzata. 

Puoi [esportare dati](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-export) da una vista personalizzata. 

Puoi [ridenominare e aggiungere o modificare la descrizione di una vista](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_step5). 

Puoi [applicare un template di riga](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_step4) a una vista per personalizzare il modo in cui i dati vengono visualizzati. 

Puoi organizzare le viste raggruppandole in **categorie*.


## Monitoraggio degli eventi applicando un periodo di tempo
{: #mon_time_view}

Potresti voler visualizzare gli eventi all'interno di uno specifico periodo di tempo.

Puoi selezionare gli eventi visualizzati tramite una vista [applicando un periodo di tempo](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-view_events#view_events_step3).

Puoi applicare una data/ora specificando un tempo assoluto, un tempo relativo o un intervallo di tempo.

* Un tempo assoluto specifica un punto preciso nel tempo nel tuo log eventi, ad esempio `May 20 7:00pm`.
    
* Un tempo relativo specifica un periodo di tempo non preciso, ad esempio `2 days ago`.

* Un intervallo di tempo specifica un lasso temporale, ad esempio `yesterday 10am to yesterday 11am`.



## Configurazione degli avvisi
{: #mon_alerts}

Esistono degli scenari in cui potresti voler ricevere una notifica se nel tuo account vengono generati eventi specifici. Ad esempio, potresti voler ricevere una notifica se il numero di azioni che hanno esito negativo supera una soglia che hai specificato. 

Attraverso l'IU web {{site.data.keyword.at_full_notm}}, puoi applicare query di ricerca per definire gli eventi che vengono visualizzati tramite una vista personalizzata. Quindi, puoi collegare un avviso a tale vista per ricevere una notifica quando si verifica una condizione. Con la vista viene visualizzata un'icona a forma di campana per indicare che a questa vista è collegato un avviso.

* Puoi [collegare un avviso](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-alerts#alerts_step4) per ogni vista.
* Puoi configurare condizioni basate sul numero di righe evento che soddisfano la query di ricerca nella vista, su una frequenza temporale o su entrambi.
* Puoi definire più canali di notifica per un avviso. Per informazioni sui canali supportati, vedi [Canali di notifica degli avvisi](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-channels).
* Puoi [definire una **preimpostazione**](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-alerts#alerts_step3). Una preimpostazione è un template di avviso che puoi collegare a qualsiasi numero di viste. Puoi utilizzare le preimpostazioni per definire i template che gli utenti possono riutilizzare quando collegano un avviso a una vista. 
* Puoi disattivare la notifica degli avvisi. 
* Puoi [scollegare un avviso](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-alerts#alerts_delete_view) da una vista. 


### Tipi di avviso
{: #mon_alerts_types}

Puoi configurare i seguenti tipi di avviso:

* **Avviso di presenza**: puoi utilizzare questo tipo di avviso per ricevere una notifica quando il numero di eventi visualizzati in una vista è superiore a quello previsto. 
* **Avviso di assenza**: puoi utilizzare questo tipo di avviso per ricevere una notifica quando il numero di eventi visualizzati in una vista è inferiore a quello previsto o non ci sono eventi visualizzati. 

Ad esempio, potresti avere una vista che mostra degli eventi che segnalano l'eliminazione di istanze del servizio nel tuo account. Non prevedi eliminazioni di istanze del servizio. Puoi configurare un *avviso di presenza** che attiva un avviso quando 1 o più eventi vengono mostrati nella vista.

L'avviso di assenza viene abilitato dopo che un evento è stato mostrato nella vista.
{: note}


### Condizioni di avviso
{: #mon_alerts_conditions}

Puoi configurare le seguenti condizioni per un avviso:

* **Frequenza temporale**: imposti questa condizione per specificare la frequenza con cui attivare un avviso. I valori validi sono: 30 secondi, 1 minuto, 5 minuti, 15 minuti, 30 minuti, 1 ora, 6 ore, 12 ore, 24 ore
* **Contatore righe evento**: imposti questa condizione per specificare il numero di righe evento che corrispondono ai criteri di filtro e ricerca della vista. Quando il numero di righe evento viene raggiunto, viene attivato un avviso.

Puoi decidere se vengono controllate entrambe le condizioni oppure solo una. Se sono impostate entrambe le condizioni, viene attivato un avviso quando viene raggiunta una qualsiasi delle soglie. 

Se imposti il *Contatore righe evento* come unica condizione che attiva un avviso, tieni presente che la frequenza temporale che viene impostata quando configuri la condizione determina il tempo necessario per la reimpostazione della condizione di avviso dopo che l'avviso è stato attivato.
{: note}

Ad esempio, puoi configurare un avviso che viene attivato dopo 30 secondi o quando vengono raccolte 100 righe evento che corrispondono ai criteri di filtro e ricerca della vista.



## Esportazione degli eventi
{: #mon_export}

Potresti dover accedere a un insieme di eventi al di fuori dell'IU web per esaminare un problema in modo più dettagliato. 

Puoi esportare i dati in formato JSONL da un'istanza {{site.data.keyword.at_full_notm}} in un file locale. 

Puoi esportare gli eventi tramite una vista nell'IU web o in modo programmatico utilizzando un'API REST.

Quando esporti gli eventi, tieni conto delle seguenti informazioni:
* Esporti un insieme di voci di evento. 
* Per definire l'insieme di dati che desideri esportare, puoi applicare filtri e ricerche. Puoi anche specificare l'intervallo di tempo. 
* Il numero massimo di righe che puoi esportare è 20.000.

### Utilizzando l'API REST
{: #mon_export_api}

Puoi esportare gli eventi in modo programmatico utilizzando l'API REST LogDNA. [Ulteriori informazioni](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-export#export_api).

Quando esporti gli eventi in modo programmatico, tieni conto delle seguenti informazioni:

* Puoi scegliere di inviare un'email o di inviare in streaming gli eventi al tuo terminale.
* Devi utilizzare una chiave di servizio che viene utilizzata per passare le credenziali necessarie per effettuare una chiamata API REST di esportazione. 

    Per visualizzare e generare le chiavi di servizio nell'IU web, devi disporre del ruolo **gestore** per l'istanza o il servizio {{site.data.keyword.at_full_notm}}.


### Tramite una vista nell'IU web
{: #mon_export_ui}

Puoi esportare gli eventi tramite una vista nell'IU web. 

Nell'IU web, puoi selezionare una vista che mostra i dati che desideri esportare. Per questa vista, devi scegliere l'attività per esportare le righe (**Export Lines**). Devi specificare un intervallo di tempo e se esportare le righe più recenti o quelle meno recenti. Quindi, puoi richiedere l'esportazione. 

Dopo aver inviato una richiesta, ricevi un'email che viene inviata al tuo indirizzo email, con un link a un file compresso che include i dati. 
* Per ottenere i dati, devi fare clic sul link e scaricare il file compresso. 
* Il file compresso che contiene i dati che desideri esportare è disponibile per un massimo di 48 ore. 

[Ulteriori informazioni sull'esportazione di eventi tramite l'IU web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-export#export_ui).








