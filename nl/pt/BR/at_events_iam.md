---

copyright:
  years: 2019
lastupdated: "2019-04-04"

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

O serviço {{site.data.keyword.at_full_notm}} registra atividades iniciadas pelo usuário que mudam o estado de um serviço no {{site.data.keyword.cloud_notm}}. Para começar a monitorar as ações do usuário, veja [{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started). 

Um inicializador pode ser um usuário, um serviço ou um aplicativo.
{: tip}

## Gerenciando eventos de grupos de acesso
{: #at_events_iam_access}

A tabela a seguir lista as ações que geram um evento:

| Ação | Descrição |
|----------|---------|
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




## Visualizando eventos
{: #at_events_iam_ui}

Os eventos estão disponíveis na região **US-South**. 

Para visualizar esses eventos, deve-se [provisionar uma instância](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision) do serviço {{site.data.keyword.at_full_notm}} na região **US-South**. Em seguida, deve-se [abrir a UI do {{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2). 


