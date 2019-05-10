---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, iam, manage user access, viewer

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

 
# Concedendo permissões de usuário a um usuário ou ID de serviço
{: #iam_view_events}

O {{site.data.keyword.iamlong}} (IAM) permite que você autentique com segurança os usuários e controle o acesso a todos os recursos em nuvem de forma consistente no {{site.data.keyword.cloud_notm}}. Conclua as etapas a seguir para conceder a um usuário ou ID de serviço as permissões mínimas para trabalhar com o serviço do {{site.data.keyword.at_full_notm}}:
{:shortdesc}

Por exemplo, se você tiver um plano pago, será possível configurar essas permissões mínimas para conceder a um usuário acesso para visualizar, procurar e filtrar eventos, exportar dados e configurar alertas.
[ Saiba mais ](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam#iam).


## Etapa 1. Criar um grupo de acesso
{: #iam_view_events_step1}

Conclua as etapas a seguir para criar um grupo de acesso:

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **Grupos de acesso**.
2. Clique em **Criar**.
3. Insira um nome e uma descrição opcional para seu grupo e clique em **Criar**.

É possível excluir um grupo selecionando a opção **Remover grupo**. Ao remover um grupo da conta, você está removendo todos os usuários e IDs de serviço do grupo e todo o acesso que é designado ao grupo.
{: note}

Para criar um grupo de acesso usando a CLI, é possível usar o comando [ibmcloud iam access-group-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_create).
```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION]
```
{: codeblock}



## Etapa 2. Incluir permissões para visualizar eventos
{: #iam_view_events_step2}

Após configurar seu grupo, será possível designar uma política de acesso comum ao grupo. 

Qualquer política que você configura para um grupo de acesso se aplica a todas as entidades, usuários e IDs de serviço, dentro do grupo.
{: note}

É possível designar a política usando a UI ou por meio da linha de comandos.

Para criar uma política de grupo de acesso usando a CLI, é possível usar o comando [ibmcloud iam access-group-policy-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_policy_create).

```
ibmcloud iam access-group-policy-create GROUP_NAME {-f, --file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```
{: codeblock}

Conclua as etapas a seguir para designar uma política a um grupo de acesso por meio da UI:

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **Grupos de acesso**.
2. Selecione o nome do grupo ao qual você deseja designar acesso. 
3. Clique em **Políticas de acesso**.
4. Clique em **Designar acesso**.
5. Escolha para designar acesso por recursos dentro de um grupo de recursos, recursos individuais disponíveis dentro da conta ou serviços de gerenciamento de conta. Por exemplo, é possível escolher qualquer uma das opções a seguir para conceder a um usuário uma função de administrador para gerenciar uma instância do {{site.data.keyword.at_full_notm}}:


### Opção 1. Conceda permissões a um usuário para se tornar um administrador do serviço na conta do {{site.data.keyword.cloud_notm}}
{: #user_opt1}

Para conceder a um usuário a função de administrador para gerenciar o serviço na conta, o usuário deve ter uma política do IAM para o serviço {{site.data.keyword.at_full_notm}} com a função da plataforma **Administrador**. Deve-se designar esse acesso de usuário a um recurso individual na conta. 

Conclua as etapas a seguir para designar uma função de administrador de usuário para o serviço {{site.data.keyword.at_full_notm}} na conta: 

1. Selecione **Designar acesso a recursos**.
2. Selecione **IBM Cloud Activity Tracker with LogDNA**.
3. Selecione  ** Todas as regiões atuais **.
4. Selecione  ** Todas as instâncias de serviço atuais **.
5. Selecione a função de plataforma  ** Visualizador **.
6. Selecione a função de serviço **Leitor**.
7. Clique em  ** Designar **.

### Opção 2. Conceda permissões a um usuário para se tornar um administrador do serviço dentro de um grupo de recursos
{: #user_opt2}

Para conceder a um usuário a função de administrador para gerenciar instâncias dentro de um grupo de recursos na conta, o usuário deve ter uma política do IAM para o serviço {{site.data.keyword.at_full_notm}} com a função da plataforma **Administrador** dentro do contexto do grupo de recursos. 

Conclua as etapas a seguir para designar a um usuário a função de administrador para o serviço {{site.data.keyword.at_full_notm}} dentro do contexto de um grupo de recursos: 

1. Selecione **Designar acesso em um grupo de recursos**.
2. Selecione um grupo de recursos.
3. Se o usuário não tiver uma função que já tenha sido concedida para o grupo de recursos selecionado, escolha uma função para o campo **Designar acesso a um grupo de recursos**. 

    Dependendo da função que você selecionar, o usuário poderá visualizar o grupo de recursos em seu painel, editar o nome do grupo de recursos ou gerenciar o acesso de usuário ao grupo. 
    
    Será possível selecionar **Sem acesso**, se você desejar que o usuário tenha acesso somente ao serviço do {{site.data.keyword.at_full_notm}} no grupo de recursos.

4. Selecione **IBM Cloud Activity Tracker with LogDNA**.
5. Selecione a função de plataforma  ** Visualizador **.
6. Selecione a função de serviço **Leitor**.
7. Clique em  ** Designar **.

### Opção 3. Conceda permissões a um usuário para se tornar um administrador de uma única instância do serviço no {{site.data.keyword.cloud_notm}}
{: #user_opt3}

Conclua as etapas a seguir para designar uma função de administrador de usuário em uma instância do serviço do {{site.data.keyword.at_full_notm}}: 

1. Selecione **Designar acesso a recursos**.
2. Selecione **IBM Cloud Activity Tracker with LogDNA**.
3. Selecione a instância.
4. Selecione a função de plataforma  ** Visualizador **.
5. Selecione a função de serviço **Leitor**.
6. Clique em  ** Designar **.


## Etapa 3. Incluir um usuário no grupo de acesso
{: #iam_view_events_step3}

Continue a configurar seu grupo, incluindo usuários ou IDs de serviço.

### Incluir um usuário no grupo de acesso
{: #iam_manage_events_step3_user}

Conclua as etapas a seguir para incluir um usuário:

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **Grupos de acesso**.
2. Selecione o nome do grupo ao qual você deseja designar acesso. 
3. Clique em **Incluir usuários** na guia **Usuários**.
4. Selecione os usuários que deseja incluir na lista e clique em **Incluir no grupo**.


### Incluir um ID de serviço no grupo de acesso
{: #iam_manage_events_step3_svcid}

Conclua as etapas a seguir para incluir um ID de serviço:

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **Grupos de acesso**.
2. Selecione o nome do grupo ao qual você deseja designar acesso. 
3. Clique na guia **IDs de serviço** e clique em **Incluir ID de serviço**.
4. Selecione os IDs que deseja incluir na lista e clique em **Incluir no grupo**.


