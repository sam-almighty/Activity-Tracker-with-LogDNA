---

copyright:
  years: 2019
lastupdated: "2019-05-21"

keywords: IBM Cloud, LogDNA, Activity Tracker, resource controller events

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

# Eventos de instância de serviço  
{: #at_events_rc}

Como um responsável pela segurança, auditor ou gerenciador, é possível usar o serviço {{site.data.keyword.at_full_notm}} para controlar como os usuários e aplicativos interagem com os serviços do {{site.data.keyword.cloud_notm}}. 
{:shortdesc}

O serviço {{site.data.keyword.at_full_notm}} registra atividades iniciadas pelo usuário que mudam o estado de um serviço no {{site.data.keyword.cloud_notm}}. Para começar a monitorar as ações do usuário, veja [{{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started). 


## Eventos para provisão e gerenciamento de instâncias de serviço
{: #rc_provision}

A tabela a seguir lista as ações que geram um evento:

| Ação                         | Descrição |
|--------------------------------|---------|
| `service_name.instance.create` | Um evento é gerado quando você provisiona uma instância de serviço. |
| `service_name.instance.update` | Um evento é gerado quando você renomeia uma instância de serviço ou quando você muda o plano de serviço. |
| `service_name.instance.delete` | Um evento é gerado quando uma instância de serviço é excluída. |
{: caption="Tabela 1. Ações que geram eventos" caption-side="top"} 


##  Eventos para gerenciar aliases que estão associados a uma instância de serviço
{: #rc_alias}

Um alias é uma conexão entre o serviço gerenciado pelo IAM em um grupo de recursos e um aplicativo dentro de uma organização ou um espaço.

A tabela a seguir lista as ações que geram um evento:

| Ação                         | Descrição |
|--------------------------------|---------|
| `service_name.alias.create` | Um evento será gerado quando um alias para uma instância for criado. |
| `service_name.alias.update` | Um evento será gerado quando um alias para uma instância for atualizado. |
| `service_name.alias.delete` | Um evento será gerado quando um alias para uma instância for excluído. |
{: caption="Tabela 2. Ações que geram eventos" caption-side="top"} 


##  Eventos para gerenciar credenciais de serviço que estão associadas a uma instância de serviço
{: #rc_keys}

Uma credencial de serviço fornece as informações necessárias para conectar um aplicativo a uma instância de serviço. 

A tabela a seguir lista as ações que geram um evento:

| Ação                         | Descrição |
|--------------------------------|---------|
| `service_name.key.create` | Um evento é gerado quando uma chave API é criada para uma instância de serviço por meio da seção *Credenciais de serviço* da IU da instância de serviço. |
| `service_name.key.delete` | Um evento é gerado quando uma chave API que está associada a uma instância de serviço é excluída da seção *Credenciais de serviço* da IU da instância de serviço. |
{: caption="Tabela 3. Ações que geram eventos" caption-side="top"} 



##  Eventos para ligar uma instância de serviço a um app e desvinculá-la dele 
{: #rc_bind}

A tabela a seguir lista as ações que geram um evento:

| Ação                         | Descrição |
|--------------------------------|---------|
| `service_name.binding.create` | Um evento é gerado quando você liga uma instância de serviço a um aplicativo. |
| `service_name.binding.delete` | Um evento é gerado quando você desvincula uma instância de serviço de um aplicativo. |
{: caption="Tabela 4. Ações que geram eventos" caption-side="top"} 



## Onde procurar os eventos
{: #rc_ui}

Os eventos estão disponíveis na região **Frankfurt (eu-de)**. 

Para visualizar esses eventos, deve-se [provisionar uma instância](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision) do serviço {{site.data.keyword.at_full_notm}} na região **Frankfurt (eu-de)**. Em seguida, deve-se [abrir a UI do {{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2). 



## Analisando eventos
{: #rc_analyze}

**Ação: service_name.instance.delete**

Quando uma instância de serviço for excluída, considere as informações a seguir:
* Outras ações são acionadas automaticamente para limpar as permissões do IAM. Essas ações removem políticas configuradas para usuários e IDs de serviço na conta na qual trabalhar com a instância de serviço. 
* O iniciador dessas ações é um ID de serviço {{site.data.keyword.IBM_notm}}.


Quando a instância de serviço que for excluída não tiver políticas do IAM configuradas para usuários e IDs de serviço, os eventos que forem gerados automaticamente para qualquer um desses recursos relatarão um resultado de `failure` com um código de resultado `404`. A amostra a seguir mostra os eventos que serão gerados quando uma instância de serviço que não tiver políticas configuradas na conta for excluída:

```
Apr 30 09:04:16 cloudcerts: delete instance Certificate Manager-v1
Apr 30 09:41:20 IAM Access Management: delete policy -failure
Apr 30 09:41:20 IAM Access Management: delete policy -failure
```
{: screen}



