---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, web UI, browser

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

# Navegando para a IU da web
{: #launch}

Depois de provisionar uma instância do serviço do {{site.data.keyword.at_full_notm}} no {{site.data.keyword.cloud_notm}}, é possível visualizar, monitorar e gerenciar eventos por meio da UI da web do {{site.data.keyword.at_full_notm}}.
{:shortdesc}


## Etapa 1. Concedendo políticas do IAM a um usuário para visualizar dados 
{: #step1}

**Nota:** deve-se ser um administrador do serviço do {{site.data.keyword.at_full_notm}}, um administrador de uma instância do {{site.data.keyword.at_full_notm}} ou ter permissões de IAM da conta para conceder outras políticas de usuários.

A tabela a seguir lista a política mínima que um usuário deve ter para poder ativar a UI da web e visualizar dados por meio da UI da web do {{site.data.keyword.at_full_notm}}:

| Atribuição                      | Permissão concedida       |
|---------------------------|---------------------|
| Função de plataforma: `Viewer` | Permite que o usuário visualize a lista de instâncias de serviço no painel Observabilidade. |
| Função de serviço: `Reader`    | Permite que o usuário visualize eventos por meio da UI da web. | 
{: caption="Tabela 1. Políticas do IAM" caption-side="top"} 

Para obter mais informações, consulte [Concedendo permissões de usuário a um usuário ou ID de serviço](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events).


## Etapa 2. Ativando a UI da web por meio da UI do {{site.data.keyword.cloud_notm}}
{: #launch_step2}

Você ativa a IU da web dentro do contexto de uma instância do {{site.data.keyword.at_full_notm}} por meio da IU do {{site.data.keyword.cloud_notm}}. 

Conclua as etapas a seguir para ativar a IU da web:

1. [Efetue login em sua conta do {{site.data.keyword.cloud_notm}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://cloud.ibm.com/login){:new_window}.

	Depois de efetuar login com seu ID do usuário e senha, o painel do {{site.data.keyword.cloud_notm}} se abre.

2. No menu de navegação, selecione  ** Observabilidade **. 

3. Selecione **Activity Tracker**. 

    A lista de instâncias disponíveis no {{site.data.keyword.cloud_notm}} é exibida.

4. Selecione uma instância. Em seguida, clique em  ** Visualizar LogDNA **.

A UI da web é aberta.


## Obtendo a URL da IU da web por meio do {{site.data.keyword.cloud_notm}}
{: #launch_get}

Para obter a URL da IU da web, conclua as etapas a seguir por meio de um terminal:

1. Configure o grupo de recursos no qual a instância do {{site.data.keyword.at_full_notm}} é fornecida.

    ```
    export logdna_rg_name=<Resource_Group_Name_Where_LogDNA_Instance_Is_Created>
    ```
    {: codeblock}

2. Configure o nome da instância do  {{site.data.keyword.at_full_notm}} .

    ```
    export logdna_instance_name=<Your_LogDNA_Instance_Name>
    ```
    {: codeblock}

3. Configure o terminal.

    ```
    export rc_endpoint=resource-controller.cloud.ibm.com
    ```
    {: codeblock}

4. Configure o token do IAM.

    ```
    export iam_token=$(ibmcloud iam oauth-tokens | grep IAM | grep -oP  "eyJ.*")
    ```
    {: codeblock}

    **Nota:** se você estiver trabalhando em um terminal MacOS, o comando será como a seguir: `export iam_token=$(ibmcloud iam oauth-tokens | grep IAM | grep -o  "eyJ.*")`

5. Configure o ID do grupo de recursos.

    ```
    export resource_group_id=$(ibmcloud resource groups | grep "^$logdna_rg_name" | awk '{print $2}')
    ```
    {: codeblock}

6. Configure a URL da IU da web em uma variável.

    ```
    export dashboard_url=$(curl -H "Accept: application/json" -H "Authorization: Bearer $iam_token" "https://$rc_endpoint/v1/resource_instances?resource_group_id=$resource_group_id&type=service_instance" | jq ".resources[] | select(.name==\"$logdna_instance_name\") | .dashboard_url")
    ```
    {: codeblock}

7. Obtenha a URL da IU da web.

    ```
    echo $dashboard_url
    ```
    {: codeblock}

    

