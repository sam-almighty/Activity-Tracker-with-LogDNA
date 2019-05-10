---

copyright:
  years: 2019
lastupdated: "2019-04-04"

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
{: #view_events.md}

Depois de provisionar uma instância do serviço do {{site.data.keyword.at_full_notm}} no {{site.data.keyword.cloud_notm}}, é possível visualizar eventos por meio da UI da web do {{site.data.keyword.at_full_notm}}.
{:shortdesc}


## Pré-requisitos
{: #view_events_prereqs}

Antes de iniciar, verifique se seu ID do usuário tem permissões para ativar a UI da web e visualizar eventos. 

**Nota:** deve-se ser um administrador do serviço {{site.data.keyword.at_full_notm}}, um administrador da instância do {{site.data.keyword.at_full_notm}} ou ter permissões de conta do IAM para gerenciar as políticas.

A tabela a seguir lista as políticas mínimas que um usuário deve ter para poder ativar a UI da web do {{site.data.keyword.at_full_notm}} e visualizar eventos:

| Atribuição                      | Permissão concedida            |
|---------------------------|-------------------------------|  
| Função de plataforma: `Viewer`     | Permite que o usuário visualize a lista de instâncias de serviço no painel Observabilidade. |
| Função de serviço: `Reader`        | Permite que o usuário ative a UI da web e visualize eventos na UI da web. |
{: caption="Tabela 1. Políticas do IAM" caption-side="top"} 

Para obter mais informações sobre como configurar essas políticas para um usuário, consulte [Concedendo permissões de usuário a um usuário ou ID de serviço](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events).


## Visualizar eventos por meio da UI da web
{: #view_events_step1}

Para ativar a UI da web do {{site.data.keyword.at_full_notm}}, conclua as etapas a seguir:

1. [Efetue login em sua conta do {{site.data.keyword.cloud_notm}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://cloud.ibm.com/login){:new_window}.

	Depois de efetuar login com seu ID do usuário e senha, o *Painel* do {{site.data.keyword.cloud_notm}} se abre.

2. Acesse o ícone de menu ![ícone menu](../../icons/icon_hamburger.svg) e selecione **Observabilidade**. 

3. Selecione **Activity Tracker**. 

    A lista de instâncias do {{site.data.keyword.at_full_notm}} é exibida.

    **Nota:** há 1 instância por região.

4. Selecione a instância na região na qual você deseja visualizar eventos. Em seguida, clique em  ** Visualizar LogDNA **.

A UI da web do {{site.data.keyword.at_full_notm}} é aberta e mostra a visualização **Tudo**. Por meio dessa visualização, é possível ver os eventos em sua conta para a região que você selecionou.

**Nota:** se você tiver um plano `Lite` e não puder ver os eventos que você estiver procurando, talvez seja necessário fazer upgrade para um plano pago para ativar os recursos de procura em eventos mais antigos. O número de dias que os eventos estão disponíveis para procura depende do plano que você escolher. [ Saiba mais ](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan#service_plan).


## Customizar sua visualização padrão
{: #view_events_step2}

Na seção **PREFERÊNCIAS DO USUÁRIO**, é possível modificar a ordem dos campos de dados que são exibidos por linha.

Conclua as etapas a seguir para modificar o formato de uma linha de eventos:

1. Na UI da web, clique no ícone **Configuração** ![Ícone Configuração](images/admin.png "Ícone Administrador").
2. Selecione  ** PREFERÊNCIAS DO USUÁRIO **. Uma nova janela é aberta.
3. Selecione  ** Formato de log **.
4. Modifique a seção *Formato de linha* para corresponder aos seus requisitos. Caixas de arrasto.




## Visualizar um evento no contexto
{: #view_events_step3}

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
{: #view_events_step4}


Conclua as etapas a seguir para copiar um evento para a área de transferência: 

1. Na UI da web, clique no ícone **Visualizações** ![Ícone Configuração](images/views.png "Ícone Configuração").
2. Selecione **Tudo** ou uma visualização customizada.
3. Identifique uma linha que você deseja explorar.
4. Expanda a linha de eventos. 

    Informações sobre identificadores de linha, tags e rótulos são exibidas.

5. Clique em **Copiar na área de transferência** para copiar o evento na área de transferência.

Quando você concluir a exploração do evento, clique em **Fechar** para fechar a linha.




