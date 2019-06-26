---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, iam, manage user access

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

 
# Gerenciando o acesso de usuário com o IAM
{: #iam}

O {{site.data.keyword.iamlong}} (IAM) permite que você autentique com segurança os usuários e controle o acesso a todos os recursos em nuvem de forma consistente no {{site.data.keyword.cloud_notm}}. 
{:shortdesc}

**Uma política de acesso com uma função de usuário do IAM definida deve ser designada a cada usuário que acessa o serviço {{site.data.keyword.at_full_notm}} em sua conta.** A política determina quais ações o usuário pode executar no contexto do serviço ou da instância selecionada. As ações permitidas são customizadas e definidas como operações que têm permissão para serem executadas no serviço. As ações são, então, mapeadas para funções de usuário do IAM.

*Políticas* permitem que o acesso seja concedido em níveis diferentes. Algumas das opções incluem o seguinte: 

* Acesso a todos os serviços ativados pelo IAM em sua conta
* Acesso a todas as instâncias do serviço em uma única região em sua conta
* Acesso a uma instância de serviço individual em sua conta
* Acesso a todas as instâncias do serviço dentro do contexto de um grupo de recursos
* Acesso a todas as instâncias do serviço em uma única região dentro do contexto de um grupo de recursos
* Acesso a todos os serviços ativados pelo IAM dentro do contexto de um grupo de recursos

As *Funções* definem as ações que um usuário ou serviceID pode executar. Há diferentes tipos de funções no {{site.data.keyword.cloud_notm}}:

* As *Funções de gerenciamento de plataforma* permitem que os usuários executem tarefas em recursos de serviço no nível de plataforma, por exemplo, designar acesso de usuário para o serviço, criar ou excluir IDs de serviço, criar instâncias, designar políticas para seu serviço a outros usuários e ligar instâncias a aplicativos.
* *Funções de acesso de serviço* permitem que níveis variados de permissão sejam designados aos usuários para que eles chamem a API do serviço.

**Para organizar um conjunto usuários e IDs serviço em uma única entidade que facilite o gerenciamento das permissões do IAM, use *access groups*.** É possível designar uma política única ao grupo em vez
de designar o mesmo acesso múltiplas vezes por usuário ou ID de serviço individual.
{: tip}

Saiba mais por meio dos tutoriais a seguir:
* [Concedendo permissões de administração a um usuário ou ID de serviço](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_manage_events#iam_manage_events)
* [Concedendo permissões de usuário a um usuário ou ID de serviço](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events)

## Gerenciando o acesso usando grupos de acesso
{: #groups}

Para gerenciar o acesso ou designar um novo acesso para os usuários usando grupos de acesso, deve-se ser o proprietário da conta, o administrador ou o editor em todos os serviços ativados de Identidade e Acesso na conta ou o administrador ou editor designado para o Serviço de grupos de acesso do IAM. 

Escolha qualquer uma das ações a seguir para gerenciar os grupos de acesso no {{site.data.keyword.cloud_notm}}:

* [ Criando um grupo de acesso ](/docs/iam?topic=iam-groups#create_ag).
* [ Designando acesso a um grupo ](/docs/iam?topic=iam-groups#access_ag).


## Gerenciando o acesso designando políticas diretamente aos usuários
{: #users}

Para gerenciar o acesso ou designar um novo acesso para usuários usando políticas do IAM, deve-se ser o proprietário da conta, o administrador em todos os serviços na conta ou um administrador para o serviço ou a instância de serviço específica. 

Escolha qualquer uma das ações a seguir para gerenciar as políticas do IAM no {{site.data.keyword.cloud_notm}}:

* Para modificar as permissões de um usuário, consulte [Editando o acesso existente](/docs/iam?topic=iam-iammanidaccser#edit_existing).
* Para conceder permissões a um usuário, consulte [Designar novo acesso](/docs/iam?topic=iam-iammanidaccser#assign_new_access).
* Para revogar permissões, consulte  [ Removendo o acesso ](/docs/iam?topic=iam-iammanidaccser#removing_access).
* Para revisar as permissões de um usuário, consulte [Revisando seu acesso designado](/docs/iam?topic=iam-iammanidaccser#review_your_access).



## {{site.data.keyword.cloud_notm}}  funções da plataforma
{: #platform}

Use a tabela a seguir para identificar a função da plataforma que é possível conceder a um usuário no {{site.data.keyword.cloud_notm}} para executar qualquer uma das ações da plataforma a seguir:

| Ações da plataforma                                                        | Funções da plataforma {{site.data.keyword.cloud_notm}}    | 
|-------------------------------------------------------------------------|------------------------------------------------------|
| `Conceder acesso aos outros membros da conta para que trabalhem com o serviço`           | Administrador                                        | 
| `Fornecer uma instância de serviço`                                          | Editor                            | 
| `Excluir uma instância de serviço`                                             | Administrador </br>Editor                            | 
| `Criar um ID de serviço`                                                   | Administrador </br>Editor                            |
| `Visualizar detalhes de uma instância de serviço`                                    | Administrador </br>Editor </br>Operador </br>Visualizador  | 
| `Visualizar instâncias de serviço no painel Criação de log de observabilidade`         | Administrador </br>Editor </br>Operador </br>Visualizador  | 
| `Visualize a chave de ingestão no console do {{site.data.keyword.cloud_notm}}` | Administrador                                        | 
{: caption="Tabela 1. Funções e ações do usuário do IAM" caption-side="top"}



## Funções de serviço do {{site.data.keyword.cloud_notm}}
{: #service}

Use a tabela a seguir para identificar as funções de serviço que você pode conceder a um usuário para executar qualquer uma das ações de serviço a seguir:

| Ações                                                                 | Funções de serviço do {{site.data.keyword.cloud_notm}}     | 
|-------------------------------------------------------------------------|------------------------------------------------------|
| `Manage ingestion keys through the logDNA web UI`                       | Gerente                                              |
| `Gerenciar chaves de serviço`                                                   | Gerente                                              |
| `Archive events`                                                        | Gerente                                              |
| `Define exclusion rules`                                                | Gerente                                              |
| `Configure alerts`                                                      | Gerenciador </br>Leitor                                  | 
| `Filter and search data`                                                | Gerenciador </br>Leitor                                  |
| `Create views`                                                          | Gerenciador </br>Leitor                                  |
| `Gerenciar visualizações`                                                          | Gerenciador </br>Leitor                                  |
| `Exportar dados do log`                                                       | Gerenciador </br>Leitor                                  |
| `Configure user preferences in the LogDNA web UI`                       | Gerenciador </br>Leitor                                  |
| `View events through the LogDNA web UI`                                 | Gerenciador </br>Leitor                                  | 
{: caption="Tabela 2. Funções e ações do usuário do IAM" caption-side="top"}


**Nota:** a função de serviço **gerenciador** é mapeada diretamente para a função de administrador de LogDNA.






