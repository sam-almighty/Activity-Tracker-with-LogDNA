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


# Visualizando eventos
{: #view_events}

Depois de provisionar uma instância do serviço do {{site.data.keyword.at_full_notm}} no {{site.data.keyword.cloud_notm}}, é possível visualizar eventos por meio da UI da web do {{site.data.keyword.at_full_notm}}. Você visualiza eventos em seu horário local.
{:shortdesc}


## Visualizar eventos
{: #view_events_step1}

Conclua as etapas a seguir para visualizar eventos:

1. Verifique se seu ID de usuário tem permissões para iniciar a IU da web e visualizar eventos. 

    A tabela a seguir lista as funções mínimas necessárias para que um usuário possa iniciar a IU da web do {{site.data.keyword.at_full_notm}}, visualizar, procurar e filtrar eventos:

    <table>
      <caption>Tabela 1. Funções do IAM</caption>
      <tr>
        <th>Atribuição</th>
        <th>Permissão concedida</th>
      </tr>
      <tr>
        <td>Função de plataforma: `Viewer`</td>
        <td>Permite que o usuário visualize a lista de instâncias de serviço no painel *Observabilidade*.</td>
      </tr>
      <tr>
        <td>Função de serviço: `Reader`</td>
        <td>Permite que o usuário ative a IU da web e visualize, procure e filtre eventos na IU da web.</td>
      </tr>
    </table>

    Para obter mais informações sobre como configurar políticas para um usuário, consulte [Concedendo permissões de usuário para um usuário ou ID de serviço](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events).

2. [Acessar a UI da web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).

3. Clique no ícone  ** Visualizações **   ![Configuration icon](images/views.png).

4. Selecione **Tudo** para ver todos os eventos ou uma visualização. 

É possível visualizar eventos por meio da visualização que você selecionou.



## Visualizar um subconjunto dos eventos aplicando uma consulta de procura
{: #view_events_step2}

É possível selecionar os eventos que são exibidos por meio de uma visualização aplicando uma consulta de procura. É possível salvar essa visualização para reutilizar posteriormente. [ Saiba mais ](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_step2).

 


## Visualizar um subconjunto dos eventos aplicando um intervalo de tempo
{: #view_events_step3}

É possível selecionar os eventos que são exibidos por meio de uma visualização aplicando um intervalo de tempo.

É possível aplicar um registro de data e hora especificando um tempo absoluto, um tempo relativo ou um intervalo de tempo.

Conclua as etapas a seguir para ir para um horário específico:
1. [Acessar a UI da web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).
2. Clique no ícone  ** Visualizações **   ![Configuration icon](images/views.png).
3. Selecione  ** Tudo **  ou uma visualização.
4. Insira uma consulta de tempo. Escolha qualquer uma das opções a seguir:

    * Insira um tempo absoluto para ir para um horário específico em seus eventos como `May 20 7:00pm`.
    
    * Insira um tempo relativo, como `2 days ago`, `today at 12am` ou `an hour ago`.

    * Insira um intervalo de tempo como `yesterday 10am to yesterday 11am`, `last fri 4:30pm to 11/12 1 AM`, `last wed 4:30pm to 23/05 1 AM` ou `May 20 10am to May 22 10am`. Certifique-se de incluir `to` para separar o registro de data e hora inicial do registro de data e hora de encerramento.

5. Clique em **ENTER**.

    Você pode obter a mensagem de erro: `Your request is taking longer than expected, try refreshing your browser in a bit as we try to catch up. Retry.` Você poderá ver esse erro quando o intervalo de tempo que você especificou não tiver nenhum evento disponível a ser mostrado. Mude a consulta de tempo e tente novamente.



## Visualizar um evento no contexto
{: #view_events_step4}

A qualquer momento, é possível visualizar cada linha de eventos no contexto.

Conclua as etapas a seguir: 

1. Na UI da web, clique no ícone **Visualizações** ![Ícone Configuração](images/views.png "Ícone Configuração").
2. Selecione **Tudo** ou uma visualização customizada.
3. Identifique uma linha que você deseja explorar.
4. Expanda a linha de eventos. 

    Informações sobre identificadores de linha, tags e rótulos são exibidas.

5. Clique em **Visualizar no contexto** para ver a linha de eventos no contexto de outras entradas desse host, do app ou de ambos.

Quando você concluir a exploração do evento, clique em **Fechar** para fechar a linha.



## Copiar um evento para a área de transferência
{: #view_events_step5}


Conclua as etapas a seguir para copiar um evento para a área de transferência: 

1. Na UI da web, clique no ícone **Visualizações** ![Ícone Configuração](images/views.png "Ícone Configuração").
2. Selecione **Tudo** ou uma visualização customizada.
3. Identifique uma linha que você deseja explorar.
4. Expanda a linha de eventos. 

    Informações sobre identificadores de linha, tags e rótulos são exibidas.

5. Clique em **Copiar na área de transferência** para copiar o evento na área de transferência.

Quando você concluir a exploração do evento, clique em **Fechar** para fechar a linha.




