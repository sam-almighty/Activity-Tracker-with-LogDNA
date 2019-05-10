---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, delete instance

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

# Removendo uma Instância
{: #remove}

É possível remover uma instância do serviço do {{site.data.keyword.at_full_notm}} por meio da IU do {{site.data.keyword.cloud_notm}} ou da linha de comandos.
{:shortdesc}



## Removendo uma instância por meio da IU do  {{site.data.keyword.cloud_notm}}
{: #remove_ui}

Para remover uma instância do {{site.data.keyword.at_full_notm}} usando a IU do {{site.data.keyword.cloud_notm}}, conclua as etapas a seguir:

1. [Efetue login em sua conta do {{site.data.keyword.cloud_notm}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://cloud.ibm.com/login){:new_window}.

	Após você efetuar login com o seu ID do usuário e senha, a UI do {{site.data.keyword.cloud_notm}} será aberta.

2. Acesse o ícone de menu ![Ícone Menu](../../icons/icon_hamburger.svg) &gt; **Observabilidade** para acessar o Painel de *Observabilidade*.

3. Selecione **Activity Tracker**. A lista de instâncias é exibida.

4. Selecione a instância que você deseja excluir.

5. A partir do menu  * Ação * , selecione  ** Remover **.

Em seguida, remova as permissões que são concedidas aos usuários para trabalhar com a instância que você excluiu.

## Removendo uma instância por meio da CLI
{: #remove_cli}

Para remover uma instância do {{site.data.keyword.at_full_notm}} por meio da linha de comandos, conclua as etapas a seguir:

1. [ Pré-requisito ] Instalação da CLI do  {{site.data.keyword.cloud_notm}} .

   Para obter mais informações, consulte [Instalando a CLI do {{site.data.keyword.cloud_notm}}](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli).

   Se a CLI estiver instalada, continue com a próxima etapa.

2. Efetue login na região no {{site.data.keyword.cloud_notm}} na qual você deseja provisionar a instância. Execute o comando a seguir: [`ibmcloud login`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_login)

3. Configure o grupo de recursos no qual a instância é fornecida. Execute o comando a seguir:  [ ` ibmcloud target ` ](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_target)

    Por padrão, o grupo de recursos *default* é configurado.

4. Remova a instância. Execute o comando  [ ` ibmcloud resource service-instance-delete ` ](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_resource#ibmcloud_resource_service_instance_delete) :

    ```
    ibmcloud resource service-instance-delete NAME 
    ```
    {: codeblock}

    Em que NAME é o nome da instância

    Para listar todas as instâncias que estão disponíveis no grupo de recursos no qual você efetuou login, execute o comando a seguir:

    ```
    ibmcloud resource service-instances
    ```
    {: codeblock}
    
    
Por exemplo, para remover uma instância, execute o comando a seguir:

```
ibmcloud resource service-instance-delete logdna-instance-01
```
{: codeblock}

Em seguida, remova as permissões que são concedidas aos usuários para trabalhar com a instância que você excluiu.


