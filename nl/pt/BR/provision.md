---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, provision instance

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

# Provisionando uma instância
{: #provision}

Antes que seja possível monitorar e gerenciar dados do evento com o {{site.data.keyword.at_full_notm}}, deve-se primeiro provisionar uma instância do serviço no {{site.data.keyword.cloud_notm}}.
{:shortdesc}

Para fornecer uma instância do {{site.data.keyword.at_full_notm}} em uma região do Cloud Public, deve-se selecionar o plano de serviço que está associado à instância, a região em que seus logs são coletados e o plano que determina o período de retenção para os logs. É possível escolher entre os períodos de retenção de 7, 14 ou 30 dias.

Como alternativa, o {{site.data.keyword.at_full_notm}} oferece um plano `Lite` que é possível usar para visualizar seus eventos à medida que eles passam pelo sistema. É possível visualizar eventos usando tailing de eventos. Também é possível projetar filtros para se preparar para fazer upgrade para um plano de período de retenção mais longo. Esse plano tem um período de retenção de 0 dias.

Para fornecer uma instância de serviço, seu ID do usuário deve ter permissões para provisionar um serviço em um grupo de recursos. [ Saiba mais ](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam#groups).
{: tip}


## Fornecendo uma instância por meio do painel Observabilidade
{: #provision_ui}

Para fornecer uma instância por meio do painel Observabilidade no {{site.data.keyword.cloud_notm}}, conclua as etapas a seguir:

1. [Efetue login em sua conta do {{site.data.keyword.cloud_notm}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://cloud.ibm.com/login){:new_window}.

	Após você efetuar login com o seu ID do usuário e senha, a UI do {{site.data.keyword.cloud_notm}} será aberta.

2. Acesse o ícone de menu ![Ícone de menu](../../icons/icon_hamburger.svg). Em seguida, selecione **Observabilidade** para acessar o painel *Observabilidade*.

3. Selecione **Activity Tracker** e, em seguida, clique em **Criar instância**. 

4. Insira um nome para a instância de serviço.

5. Selecione a região na qual você planeja provisionar a instância.

6. Selecione um grupo de recursos. 

    Por padrão, o grupo de recursos **Padrão** é configurado.

    **Nota:** se você não puder selecionar um grupo de recursos, verifique se tem permissões de edição no grupo de recursos no qual você deseja provisionar a instância.

7. Selecione o plano de serviço `Lite`. 

    Por padrão, o plano Lite é configurado.

8. Clique em **Criar**.

Depois de provisionar uma instância, o painel *Activity Tracker* será aberto. 

Em seguida, acesse a UI da web para gerenciar eventos em sua conta. [ Saiba mais ](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-view_events.md#view_events.md).



## Provisionando uma instância por meio do catálogo
{: #provision_catalog}

Para provisionar uma instância do {{site.data.keyword.at_full_notm}} por meio do catálogo do {{site.data.keyword.cloud_notm}}, conclua as etapas a seguir:

1. [Efetue login em sua conta do {{site.data.keyword.cloud_notm}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://cloud.ibm.com/login){:new_window}.

	Após você efetuar login com o seu ID do usuário e senha, a UI do {{site.data.keyword.cloud_notm}} será aberta.

2. Clique em **Catálogo**. A lista dos serviços disponíveis no {{site.data.keyword.cloud_notm}} é aberta.

3. Para filtrar a lista de serviços que são exibidos, selecione a categoria **Ferramentas do desenvolvedor**.

4. Clique no tile **{{site.data.keyword.at_full_notm}}**. 

5. Insira um nome para a instância de serviço.

6. Selecione um grupo de recursos. 

    Por padrão, o grupo de recursos **Padrão** é configurado.

    **Nota:** se você não puder selecionar um grupo de recursos, verifique se tem permissões de edição no grupo de recursos no qual você deseja provisionar a instância.

7. Selecione o plano de serviço `Lite`. 

    Por padrão, o plano Lite é configurado.

8. Clique em **Criar**.

Depois de provisionar uma instância, o painel *Activity Tracker* será aberto. 

Em seguida, acesse a UI da web para gerenciar eventos em sua conta. [ Saiba mais ](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).


## Provisionando uma instância por meio da CLI
{: #provision_cli}

Para provisionar uma instância do {{site.data.keyword.at_full_notm}} por meio da linha de comandos, conclua as etapas a seguir:

1. [ Pré-requisito ] Instalação da CLI do  {{site.data.keyword.cloud_notm}} . [ Saiba mais ](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli).

   Se a CLI estiver instalada, continue com a próxima etapa.

2. Efetue login na região no {{site.data.keyword.cloud_notm}} na qual você deseja provisionar a instância. Execute o comando a seguir: [`ibmcloud login`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_login)

3. Configure o grupo de recursos no qual você deseja provisionar a instância. Execute o comando a seguir:  [ ` ibmcloud target ` ](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_target)

    Por padrão, o grupo de recursos `default` é configurado.

4. Crie a instância. Execute o comando  [ ` ibmcloud resource service-instance-create ` ](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_resource#ibmcloud_resource_service_instance_create) :

    ```
    ibmcloud resource service-instance-create NAME logdnaat SERVICE_PLAN_NAME LOCATION
    ```
    {: codeblock}

    Em que

    * NAME é o nome da instância

    * O valor *logdnaat* é o nome do serviço {{site.data.keyword.at_full_notm}} no {{site.data.keyword.cloud_notm}}

    * SERVICE_PLAN_NAME é o tipo de plano. Os valores válidos são *lite*, *7-days*, *14-days* e *30-days*
    
    * LOCATION é a região em que a instância de LogDNA é criada. Por exemplo, um valor válido é *us-south*

    
Por exemplo, para fornecer uma instância com o plano de retenção de 7 dias, execute o comando a seguir:

```
ibmcloud resource service-instance-create logdna-instance-01 logdnaat 7-day us-south
```
{: codeblock}



