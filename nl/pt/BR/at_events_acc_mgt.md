---

copyright:
  years: 2019
lastupdated: "2019-05-25"

keywords: IBM Cloud, LogDNA, Activity Tracker, account events

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

# Eventos de gerenciamento de conta  
{: #at_events_acc_mgt}

Como um responsável pela segurança, auditor ou gerenciador, é possível usar o serviço {{site.data.keyword.at_full_notm}} para controlar como os usuários e aplicativos interagem com a conta do {{site.data.keyword.cloud_notm}}. 
{:shortdesc}

O serviço {{site.data.keyword.at_full_notm}} registra atividades iniciadas pelo usuário que mudam o estado de um serviço no {{site.data.keyword.cloud_notm}}. Para começar a usar, consulte [{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started). 



## Eventos para gerenciar contas
{: #at_events_acc_mgt_account}

A tabela a seguir lista as ações que geram um evento:

| Ação                               | Descrição |
|--------------------------------------|-------------|
| `billing.account.create`             | Um evento é gerado quando você provisiona uma conta depois que o ID da conta é designado a ela. |
| `billing.account.update`             | Um evento é gerado quando você atualiza informações sobre a conta.  |
| `billing.account.active`             | Um evento é gerado quando você verifica a conta, ou seja, um evento é gerado quando a conta se torna ativa. |
| `billing.account.subscription.create` | Um evento é gerado quando você cria uma <a href="/docs/account?topic=account-accounts#subscription-account">Conta da assinatura</a>. |
{: caption="Tabela 1. Ações que geram eventos" caption-side="top"} 




## Eventos para gerenciar usuários
{: #at_events_acc_mgt_users}

A tabela a seguir lista as ações que geram um evento:

| Ação                               | Descrição |
|--------------------------------------|-------------|
| `user-management.user.create`        | Um evento é gerado quando você envia um convite para um usuário participar de uma conta. |
| `user-management.user.active`        | Um evento é gerado quando você ativa o usuário na conta. Quando o usuário verificar o endereço de e-mail, o evento será gerado. |
| `user-management.user.delete`        | Um evento é gerado quando você remove um usuário da conta. |
{: caption="Tabela 2. Ações que geram eventos" caption-side="top"} 




## Eventos para gerenciar organizações
{: #at_events_acc_mgt_org}

A tabela a seguir lista as ações que geram um evento:

| Ação                               | Descrição |
|--------------------------------------|-------------|
| `billing.account.org.create`         | Um evento é gerado quando você inclui uma organização na conta. |
{: caption="Tabela 3. Ações que geram eventos" caption-side="top"} 


## Eventos para gerenciar tags
{: #at_events_acc_mgt_resources}

A tabela a seguir lista as ações que geram um evento:

| Ação                               | Descrição |
|--------------------------------------|-------------|
| `ghost-tags.tag.attach-tag`          | Um evento será gerado quando você incluir uma tag em um recurso. |
| `ghost-tags.tag.detach-tag`          | Um evento será gerado quando você remover uma tag de um recurso. |
{: caption="Tabela 4. Ações que geram eventos" caption-side="top"} 


## Onde procurar os eventos
{: #at_events_acc_mgt_ui}

Os eventos estão disponíveis na região **Frankfurt (eu-de)**. 

Para visualizar esses eventos, deve-se [provisionar uma instância](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision) do serviço {{site.data.keyword.at_full_notm}} na região **Frankfurt (eu-de)**. Em seguida, deve-se [abrir a UI do {{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2). 












