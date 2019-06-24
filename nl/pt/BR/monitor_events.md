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


# Monitorando a atividade em sua conta
{: #monitor_events}

É possível monitorar a atividade em sua conta por meio da IU da web do {{site.data.keyword.at_full_notm}}. Também é possível exportar conjuntos de eventos para analisá-los em um contexto diferente.
{:shortdesc}

Há uma instância do serviço {{site.data.keyword.at_full_notm}} por local. Portanto, para monitorar a atividade em sua conta, você pode precisar visualizar e analisar eventos por meio de instâncias do {{site.data.keyword.at_full_notm}} diferentes. 

No {{site.data.keyword.cloud_notm}}, é possível clicar no ícone **Menu** ![Ícone Menu](../icons/icon_hamburger.svg) > **Observabilidade** > **Activity Tracker** para ver o painel no qual todas as instâncias provisionadas na conta são listadas. 
{: tip}

Para visualizar eventos, deve-se [ativar a IU da web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch) no local em que os eventos estão disponíveis. Em seguida, é possível trabalhar com visualizações para monitorar esses eventos. Você visualiza eventos em seu horário local.

É possível selecionar os eventos que são exibidos por meio de uma visualização, aplicando um registro de data e hora, uma consulta de procura ou ambos.

* É possível aplicar uma consulta de procura e salvá-la como uma visualização customizada. 
* É possível aplicar um registro de data e hora para ir para um horário específico em seu log de eventos. 

Quando você aplica uma consulta de procura, é possível salvar essa visualização para reutilizar posteriormente. No entanto, os registros de data e hora não são salvos.

Observe que as instâncias podem ter planos de serviço diferentes e, consequentemente, períodos de retenção de dados diferentes que determinam o número de dias que você tem dados disponíveis para procura por meio da IU da web. É possível monitorar eventos somente dentro de seu período de retenção. Diferentes [planos de serviço](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan) têm períodos de retenção diferentes.


## Monitorando eventos globais e baseados em localização
{: #mon_def_event_type}

Os eventos podem ser classificados como globais ou baseados em localização. O tipo de evento determina o local em que se deve monitorar os eventos.

O tema comum para eventos globais é um local único e sincronizado no qual os administradores de conta podem monitorar determinados tipos de atividade através da Nuvem. Enquanto isso, os eventos baseados em localização permanecem locais para o local no qual um serviço de nuvem inscrito está hospedado.
{: note}

### Eventos globais
{: #mon_def_global}

**Eventos globais** relatam sobre a atividade em sua conta que se relaciona a dados e recursos que são geralmente sincronizados em todas as regiões.
{: note}

Os serviços com os quais os usuários interagem são integrados ao núcleo da experiência global do {{site.data.keyword.cloud_notm}}.

O domínio global é configurado em **Frankfurt**. Os eventos globais são capturados e disponibilizados por meio da instância do {{site.data.keyword.at_full_notm}} que está configurada em Frankfurt.

Por exemplo, quando um administrador de conta convida os usuários a ingressarem na conta, eles podem fazer isso por meio de qualquer local na Nuvem. Eles podem convidar um usuário que está localizado em Frankfurt e conceder a ele permissões para trabalhar com um serviço que é provisionado em Dallas. Em que local o evento deve ir? A resposta é um domínio global que é agnóstico de origem ou local e no qual as informações são sincronizadas em todas as regiões.
    
Outro exemplo, os eventos do controlador de recurso também são considerados eventos globais no IBM Cloud. Esses eventos relatam o provisionamento e a exclusão de instâncias de serviço na Nuvem. Embora uma instância de serviço seja criada em um local específico, as ações do controlador de recurso são relatadas como eventos globais para oferecer uma única visualização de todas as instâncias de serviço que são provisionadas ao longo da conta.


### Eventos baseados em localização
{: #mon_def_location}

**Eventos baseados em localização** relatam a atividade em sua conta que é gerada pelos serviços do {{site.data.keyword.cloud_notm}} que estão hospedados dentro de um local do data center do {{site.data.keyword.IBM_notm}}, como Dallas ou Frankfurt.
{: note}


Quando os clientes e os aplicativos interagirem com serviços de nuvem hospedados em um local, os eventos baseados em localização serão capturados e disponibilizados por meio da instância do {{site.data.keyword.at_full_notm}} que está configurada nesse local. Você visualiza esses eventos [ativando a IU da web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch) nesse local.
    
Eventos baseados em localização mantêm a localidade de dados para os serviços que são executados nesse local da Nuvem.

Por exemplo, se você provisionar o serviço {{site.data.keyword.cloudcerts_short}} no local Frankfurt, os eventos dessa instância serão enviados para a instância do {{site.data.keyword.at_full_notm}} que é provisionada em Frankfurt. Se você provisionar o serviço {{site.data.keyword.cloudcerts_short}} no local Dallas, os eventos dessa instância serão enviados para a instância do {{site.data.keyword.at_full_notm}} que é provisionada em Dallas. Em ambos os casos, os eventos são mantidos locais para a região e o local do Serviço de Nuvem assinado.




## Monitorando eventos por meio da visualização padrão
{: #mon_def_view}

A visualização padrão é denominada **Tudo**. 

Assim que você abrir a IU da web em uma localização, essa será a visualização que verá. 

Todos os eventos em sua instância são exibidos por meio dessa visualização.

Para saber como visualizar eventos por meio dessa visualização, consulte [Visualizando eventos](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-view_events#view_events_step1).

## Monitorando eventos por meio de visualizações customizadas
{: #mon_cus_view}

Você pode desejar monitorar um conjunto de eventos em sua conta. Para analisar um subconjunto de eventos, é possível criar visualizações customizadas. 

Para criar uma visualização customizada, deve-se aplicar uma consulta de procura que defina quais eventos serão exibidos por meio da visualização. [ Saiba mais ](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-view_events#view_events_step2).

É possível [anexar alertas](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-alerts) a uma visualização customizada. 

É possível [exportar dados](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-export) de uma visualização customizada. 

É possível [renomear e incluir ou modificar a descrição de uma visualização](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_step5). 

É possível [aplicar um modelo de linha](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_step4) a uma visualização para customizar como os dados são exibidos. 

É possível organizar visualizações agrupando-as em **categorias*.


## Monitorando eventos aplicando um intervalo de tempo
{: #mon_time_view}

É possível que você queira ver eventos dentro de um intervalo de tempo específico.

É possível selecionar os eventos que são exibidos por meio de uma visualização [aplicando um intervalo de tempo](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-view_events#view_events_step3).

É possível aplicar um registro de data e hora especificando um tempo absoluto, um tempo relativo ou um intervalo de tempo.

* Um horário absoluto especifica um horário específico exato em seu log de eventos, como `May 20 7:00pm`.
    
* Um tempo relativo especifica um intervalo de tempo que não é preciso, como `2 days ago`.

* Um intervalo de tempo especificou um intervalo de tempo, como `yesterday 10am to yesterday 11am`.



## Configurar alertas
{: #mon_alerts}

Há cenários nos quais você poderá querer ser notificado se eventos específicos forem gerados em sua conta. Por exemplo, talvez você queira ser notificado se o número de ações que falharem ficar acima de um limite que você especificar. 

Por meio da IU da web do {{site.data.keyword.at_full_notm}}, é possível aplicar consultas de procura para definir os eventos exibidos por meio de uma visualização customizada. Em seguida, é possível conectar um alerta a essa visualização para ser notificado quando uma condição ocorrer. Um ícone de sino é exibido com a visualização para indicar que ela tem um alerta anexado.

* É possível [anexar um alerta](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-alerts#alerts_step4) por visualização.
* É possível configurar condições que são baseadas no número de linhas de evento que atendem à consulta de procura na visualização, em uma frequência de tempo ou ambas.
* É possível definir múltiplos canais de notificação para um alerta. Para obter informações sobre os canais suportados, consulte [Canais de notificação de alerta](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-channels).
* É possível [definir uma **pré-configuração**](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-alerts#alerts_step3). Uma pré-configuração é um modelo de alerta que pode ser anexado a qualquer número de visualizações. Será possível usar as pré-configurações para definir modelos que os usuários poderão reutilizar quando anexarem um alerta a uma visualização. 
* É possível silenciar alertas. 
* É possível [desanexar um alerta](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-alerts#alerts_delete_view) de uma visualização. 


### Tipos de alerta
{: #mon_alerts_types}

É possível configurar os tipos de alertas a seguir:

* **Alerta de presença**: é possível usar esse tipo de alerta para notificar quando o número de eventos que são mostrados em uma visualização é maior do que o esperado. 
* **Alerta de ausência**: é possível usar esse tipo de alerta para notificar quando o número de eventos que são mostrados em uma visualização é menor do que o esperado ou nenhum. 

Por exemplo, você pode ter uma visualização que mostre eventos que relatam a exclusão de instâncias de serviço em sua conta. Você não está esperando a exclusão de instâncias de serviço. É possível configurar um *alerta de presença** que aciona um alerta quando um ou mais eventos são mostrados na visualização.

O alerta de ausência é ativado após um evento ser mostrado na visualização.
{: note}


### Condições de alerta
{: #mon_alerts_conditions}

É possível configurar qualquer uma das condições a seguir para um alerta:

* **Frequência de tempo**: você configura essa condição para especificar com que frequência acionar um alerta. Os valores válidos são: 30 segundos, 1 minuto, 5 minutos, 15 minutos, 30 minutos, 1 hora, 6 horas, 12 horas, 24 horas
* **Contador de linhas de evento**: você configura essa condição para especificar o número de linhas de evento que correspondem aos critérios de filtragem e de procura da visualização. Quando o número de linhas de eventos é atingido, um alerta é acionado.

É possível decidir se as duas condições são verificadas ou apenas uma. Se ambas as condições forem configuradas, um alerta será acionado quando qualquer um dos limites for atingido. 

Caso você configure o *Contador de linhas de evento* para ser a única condição que aciona um alerta, observe que a frequência de tempo que é definida quando você configura a condição determina o tempo que leva para que a condição de alerta seja reconfigurada após o alerta ser acionado.
{: note}

Por exemplo, é possível configurar um alerta que é acionado após 30 segundos ou quando 100 linhas de eventos que correspondem aos critérios de filtragem e procura da visualização são coletadas.



## Exportando eventos
{: #mon_export}

Você pode precisar de acesso a um conjunto de eventos fora da IU da web para investigar um problema com mais detalhes. 

É possível exportar dados no formato JSONL de uma instância do {{site.data.keyword.at_full_notm}} para um arquivo local. 

É possível exportar eventos por meio de uma visualização na IU da web ou programaticamente usando uma API de REST.

Considere as informações a seguir ao exportar eventos:
* Você exporta um conjunto de entradas de eventos. 
* Para definir o conjunto de dados que você deseja exportar, é possível aplicar filtros e procuras. Também é possível especificar o intervalo de tempo. 
* O número máximo de linhas que podem ser exportadas é 20.000.

### Usando a API de REST
{: #mon_export_api}

É possível exportar eventos programaticamente usando a API de REST do LogDNA. [ Saiba mais ](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-export#export_api).

Quando você exportar eventos programaticamente, considere as informações a seguir:

* É possível optar por enviar um e-mail ou transmitir eventos para o seu terminal.
* Deve-se usar uma chave de serviço que é usada para passar as credenciais que devem ser usadas quando você faz uma chamada da API de REST de exportação. 

    Deve-se ter a função **de gerenciador** para a instância ou serviço do {{site.data.keyword.at_full_notm}} para visualizar e gerar chaves de serviço na IU da web.


### Por meio de uma visualização na IU da web
{: #mon_export_ui}

É possível exportar eventos por meio de uma visualização na IU da web. 

Na IU da web, é possível selecionar uma visualização que exibe os dados que você deseja exportar. Para essa visualização, deve-se escolher a tarefa para **Exportar linhas**. Deve-se especificar um intervalo de tempo e se as linhas mais novas ou as linhas mais antigas devem ser exportadas. Em seguida, será possível solicitar a exportação. 

Depois de enviar uma solicitação, você obterá um e-mail que será enviado para o seu endereço de e-mail, com um link para um arquivo compactado que incluirá os dados. 
* Para obter os dados, deve-se clicar no link e fazer download do arquivo compactado. 
* O arquivo compactado que contém os dados que você deseja exportar está disponível por um máximo de 48 horas. 

[Saiba mais sobre como exportar eventos por meio da IU da web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-export#export_ui).








