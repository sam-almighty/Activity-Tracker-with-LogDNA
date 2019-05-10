---

copyright:
  years: 2019
lastupdated: "2019-04-04"

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


# Criando visualizações customizadas
{: #views.md}

Por meio da UI da web do {{site.data.keyword.at_full_notm}}, é possível aplicar critérios de procura e filtragem para definir os eventos que são exibidos por meio de uma visualização customizada.
{:shortdesc}


## Pré-requisitos
{: #views_prereqs}

Antes de iniciar, verifique se seu ID do usuário tem permissões para ativar a UI da web e visualizar eventos. Em seguida, [acesse a UI da web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).

**Nota:** deve-se ser um administrador do serviço {{site.data.keyword.at_full_notm}}, um administrador da instância do {{site.data.keyword.at_full_notm}} ou ter permissões de conta do IAM para gerenciar as políticas.

A tabela a seguir lista as políticas mínimas que um usuário deve ter para poder ativar a UI da web do {{site.data.keyword.at_full_notm}} e visualizar, procurar e filtrar eventos:

| Atribuição                      | Permissão concedida            |
|---------------------------|-------------------------------|  
| Função de plataforma: `Viewer`   | Permite que o usuário visualize a lista de instâncias de serviço no painel Observabilidade. |
| Função de serviço: `Reader`      | Permite que o usuário ative a UI da web e visualize eventos na UI da web. |
{: caption="Tabela 1. Políticas do IAM" caption-side="top"} 

Para obter mais informações sobre como configurar essas políticas para um usuário, consulte [Concedendo permissões de usuário a um usuário ou ID de serviço](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events).



## Etapa 1. Filtrar eventos
{: #views_step1}

É possível filtrar eventos por nível de origem, aplicativo e log. 

* Uma origem pode ser um host, um computador, uma máquina virtual ou um app Heroku.
* Um aplicativo representa um arquivo de log, um programa ou um contêiner.
* Exemplos de níveis de log são: INFO, DEBUG e ERROR

Conclua as etapas a seguir para filtrar os logs:

1. Na UI da web, clique no ícone **Visualizações** ![Ícone Configuração](images/views.png "Ícone Configuração").
2. Selecione  ** Tudo **  ou uma visualização.
3. Expanda **Todas as tags** para ver a lista de tags que estão disponíveis. Em seguida, escolha os que você deseja.
4. Expanda **Todas as origens** para ver a lista de origens que estão disponíveis. Em seguida, escolha os que você deseja.
5. Expanda **Todos os apps** para ver a lista de apps que estão disponíveis. Em seguida, escolha os que você deseja.
6. Expanda **Todos os níveis** para ver a lista de níveis que estão disponíveis. Em seguida, escolha os que você deseja.

À medida que você aplicar filtros, observe que o nome da visualização muda para **Visualização não salva**.

**Nota:** em cada seção, é possível múltiplas opções em um grupo. Agrupe tags, origens, apps e níveis para reutilizar esses agrupamentos quando você filtrar dados em outras visualizações customizadas.

Para criar um grupo, selecione múltiplos valores. Em seguida, clique em **Salvar como grupo**. Insira um nome para o grupo e salve-o.


## Etapa 2. Procurar eventos
{: #views_step2}

Quando você procura eventos, a procura aplica quaisquer filtros e consultas de tempo que são configurados nessa visualização.

É possível fazer procuras simples (procura de sequência de termo único), procura composta (múltiplos termos de procura e operadores), procuras de campo se a linha de log puder ser analisada e outras. Para obter mais informações, consulte [Como pesquisar logs em docs do LogDNA ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://docs.logdna.com/docs/search){:new_window}.

**Nota:** os operadores AND e OR fazem distinção entre maiúsculas e minúsculas e devem estar em letras maiúsculas.

À medida que você aplicar critérios de procura, observe que o nome da visualização muda para **Visualização não salva**.



## Etapa 3. Criar uma visualização customizada
{: #views_step3}

Depois de aplicar critérios de prazo, filtros e procura à visualização **Tudo** ou a uma visualização customizada existente, conclua as etapas a seguir para salvar o resultado como uma visualização customizada:

1. Na UI da web, clique em **Visualização não salva**.
2. Selecione **Salvar como nova visualização/alerta**. A página  * Criar nova visualização *  é aberta.
3. Insira um nome para a visualização no campo *Nome*.
4. Opcionalmente, inclua uma categoria. Insira um nome e, em seguida, clique em **Incluí-lo isso como uma nova categoria de visualização**.
5. Opcionalmente, anexe um alerta. Uma nova seção é exibida para que você configure o alerta.
6. Clique em  ** Salvar visualização **




