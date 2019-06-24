---

copyright:
  years: 2019
lastupdated: "2019-05-21"

keywords: IBM Cloud, LogDNA, Activity Tracker, IAM events

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


# Eventos do IAM
{: #at_events_iam}

Como um responsável pela segurança, auditor ou gerenciador, é possível usar o serviço {{site.data.keyword.at_full_notm}} para controlar como os usuários e aplicativos interagem com o serviço do {{site.data.keyword.iamlong}} (IAM) no {{site.data.keyword.cloud_notm}}. 
{:shortdesc}

O IAM permite que você autentique os usuários com segurança para ambos os serviços de plataforma e controle o acesso aos recursos de forma consistente no {{site.data.keyword.cloud_notm}}. [ Saiba mais ](/docs/iam?topic=iam-iamoverview).


O serviço {{site.data.keyword.at_full_notm}} registra atividades iniciadas pelo usuário que mudam o estado de um serviço no {{site.data.keyword.cloud_notm}}. Para começar a monitorar as ações do usuário, veja [{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started). Um inicializador pode ser um usuário, um serviço ou um aplicativo.


## Eventos de grupos de acesso
{: #at_events_iam_access}

A tabela a seguir lista as ações que geram um evento:

| Ação                      | Descrição |
|-----------------------------|---------|
| `iam-groups.group.create`   | Um evento é gerado quando um inicializador cria um grupo de acesso. | 
| `iam-groups.group.read`     | Um evento é gerado quando um inicializador consulta informações que estão relacionadas a grupos de acesso. |
| `iam-groups.group.update`   | Um evento é gerado quando um inicializador atualiza um nome de grupo ou uma descrição. |
| `iam-groups.group.delete`   | Um evento é gerado quando um inicializador exclui um grupo de acesso. |
| `iam-groups.member.add`     | Um evento é gerado quando um inicializador inclui um membro em um grupo de acesso. |
| `iam-groups.member.delete`  | Um evento é gerado quando um inicializador remove um membro de um grupo de acesso. |
| `iam-groups.member.read`    | Um evento é gerado quando um inicializador verifica a associação de um membro. |
| `iam-groups.rule.read`      | Um evento é gerado quando um inicializador visualiza uma regra em um grupo de acesso. |
| `iam-groups.rule.create`    | Um evento é gerado quando um inicializador inclui uma regra em um grupo de acesso. |
| `iam-groups.rule.update`    | Um evento é gerado quando um inicializador modifica o nome da regra. |
| `iam-groups.rule.delete`    | Um evento é gerado quando um inicializador exclui uma regra de um grupo de acesso. |
{: caption="Tabela 1. Gerenciar ações de grupos de acesso" caption-side="top"} 



## Eventos de política
{: #at_events_iam_policies}

A tabela a seguir lista as ações que geram um evento:

| Ação                 | Descrição |
|------------------------|---------|
| `iam-am.policy.create` | Um evento é gerado quando um inicializador inclui uma política em um usuário ou grupo de acesso. |
| `iam-am.policy.delete` | Um evento é gerado quando um inicializador modifica permissões para uma política de um usuário ou grupo de acesso.|
| `iam-am.policy.update` | Um evento é gerado quando um inicializador exclui uma política que é designada a um usuário ou grupo de acesso. |
{: caption="Tabela 5. Gerenciando ações de política" caption-side="top"} 



## Eventos de ID de serviço
{: #at_events_iam_serviceids}

A tabela a seguir lista as ações que geram um evento:

| Ação | Descrição |
|----------|---------|
| `iam-identity.account-serviceid.create` | Um evento é gerado quando um inicializador cria um ID de serviço.  | 
| `iam-identity.account-serviceid.update` | Um evento é gerado quando um inicializador renomeia um ID de serviço ou modifica sua descrição. | 
| `iam-identity.account-serviceid.delete` | Um evento é gerado quando um inicializador exclui um ID de serviço. | 
{: caption="Tabela 2. Trabalhando com ações de IDs de serviço" caption-side="top"} 


## Eventos de chave de API
{: #at_events_iam_apikeys}

A tabela a seguir lista as ações que geram um evento:

| Ação | Descrição |
|----------|---------|
| `iam-identity.user-apikey.create`      | Um evento é gerado quando um inicializador cria uma chave API. | 
| `iam-identity.user-apikey.update`      | Um evento é gerado quando um inicializador renomeia uma chave API ou modifica sua descrição. |  
| `iam-identity.user-apikey.delete`      | Um evento é gerado quando um inicializador exclui uma chave API. |  
| `iam-identity.serviceid-apikey.create` | Um evento é gerado quando um inicializador cria uma chave API para um ID de serviço. |  
| `iam-identity.serviceid-apikey.delete` | Um evento é gerado quando um inicializador exclui uma chave API para um ID de serviço. |  
{: caption="Tabela 3. Trabalhando com ações de chaves API" caption-side="top"} 


## Eventos de login
{: #at_events_iam_login}

A tabela a seguir lista as ações que geram um evento:

| Ação                                   | Descrição |
|------------------------------------------|---------|
| `iam-identity.user-apikey.login`         | Um evento é gerado quando um usuário efetua login no {{site.data.keyword.cloud_notm}} usando uma chave API. |  
| `iam-identity.serviceid-apikey.login`    | Um evento é gerado quando um inicializador efetua login no {{site.data.keyword.cloud_notm}} usando uma chave API que está associada a um ID de serviço. |  
| `iam-identity.user-identitycookie.login` | Esse é um evento que será gerado quando um inicializador solicitar que um cookie de identidade execute uma ação. |
| `iam-identity.user-refreshtoken.login`   | Esse é um evento que é gerado quando o inicializador efetua login no IBM Cloud ou quando um inicializador que já efetuou login no IBM Cloud solicita um novo token de atualização para executar uma ação. |
{: caption="Tabela 4. Ações de login do usuário" caption-side="top"} 


## Visualizando eventos
{: #at_events_iam_ui}

Os eventos estão disponíveis na região **Frankfurt (eu-de)**. Para visualizar esses eventos, deve-se [provisionar uma instância](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision) do serviço {{site.data.keyword.at_full_notm}} na região **Frankfurt (eu-de)**. Em seguida, deve-se [abrir a UI do {{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2). 


## Analisando eventos
{: #at_events_iam_analyze}


### Excluir um grupo de acesso
{: #an_del_ag}

Quando você excluir um grupo de acesso, o evento que for acionado terá um campo `action` configurado como `iam-groups.group.delete`.

Quando um grupo de acesso for excluído, considere as informações a seguir:
* Outras ações são acionadas automaticamente para limpar outros recursos associados ao grupo. Algumas ações que são acionadas relatam eventos relacionados à exclusão de membros em um grupo de acesso, à exclusão de políticas e à exclusão de regras dinâmicas. 
* O iniciador dessas ações é um ID de serviço {{site.data.keyword.IBM_notm}}.


Quando o grupo de acesso que for excluído não tiver regras, políticas e membros designados, os eventos que forem gerados para qualquer um desses recursos relatarão um resultado de `failure` com um código de resultado `404`. A amostra a seguir mostrará os eventos que serão gerados quando um grupo de acesso que não tiver regras dinâmicas, políticas ou membros designados for excluído:

```
Apr 29 14:11:22 IAM Access Groups: delete group test5
Apr 29 14:11:24 IAM Access Groups: delete members -failure
Apr 29 14:11:24 IAM Access Groups: delete rules -failure
Apr 29 14:11:24 IAM Access Management: delete policy -failure
```
{: screen}

