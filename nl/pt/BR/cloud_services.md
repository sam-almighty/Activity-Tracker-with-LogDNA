---

copyright:
  years: 2019
lastupdated: "2019-05-25"

keywords: IBM Cloud, LogDNA, Activity Tracker, services

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


# Serviços de nuvem
{: #cloud_services}

Use o serviço do {{site.data.keyword.at_full}} para monitorar atividades iniciadas pelo usuário que mudam o estado de qualquer um dos serviços a seguir no {{site.data.keyword.cloud_notm}}.
{:shortdesc}


## Serviços integrados principais de plataforma
{: #platform_core_integrated}


Os serviços principais de plataforma geram eventos que podem ser visualizados por meio da IU da web do {{site.data.keyword.at_full_notm}} na região **Frankfurt (eu-de)**. Para visualizar esses eventos, deve-se [provisionar uma instância](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision) do serviço {{site.data.keyword.at_full_notm}} na região **Frankfurt (eu-de)**.
{: note}

A tabela a seguir lista as ações da plataforma principal que enviam eventos para o {{site.data.keyword.at_full_notm}}:

| Ação                           | Descrição | Eventos do {{site.data.keyword.at_full_notm}} |
|----------------------------------|-------------|-------------------------------------------|
| [Gerenciando uma conta](/docs/account?topic=account-accounts#accounts) | É possível inscrever-se para uma conta do {{site.data.keyword.IBM_notm}} usando um IBMid existente, criando um novo IBMid ou usando um ID federado. | [Eventos que são gerados quando você gerencia uma conta](/docs/services/cloud-activity-tracker/services?topic=cloud-activity-tracker-at_events_acc_mgt#at_events_acc_mgt_account) |
| [Gerenciando usuários](/docs/iam?topic=iam-iamuserinv#iamusermanage) | É possível visualizar e gerenciar usuários na conta ou nas organizações que você possui ou gerencia.  | [Eventos que são gerados quando você gerencia usuários ](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_acc_mgt#at_events_acc_mgt_users) |
| [Gerenciando organizações](/docs/account?topic=account-orgsspacesusers#orgsspacesusers) | Como um proprietário da conta, é possível incluir e gerenciar organizações na conta. | [Eventos que são gerados quando você gerencia organizações ](/docs/services/cloud-activity-tracker/services?topic=cloud-activity-tracker-at_events_acc_mgt#at_events_acc_mgt_org) |
| [Provisionando e gerenciando serviços de catálogo ativados pelo {{site.data.keyword.iamshort}} (IAM)](/docs/overview?topic=overview-ui#catalogcreate) | É possível provisionar uma instância de serviço, renomear uma instância de serviço, mudar o plano de uma instância de serviço e remover uma instância de serviço. | [Eventos que são gerados quando você interage com serviços de catálogo ](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#at_events_rc) | 
| [Trabalhando com aliases de serviço](/docs/resources?topic=resources-connect_app#what_is_alias) | Um alias é uma conexão entre o serviço gerenciado pelo IAM em um grupo de recursos e um aplicativo dentro de uma organização ou um espaço. | [Eventos para gerenciar aliases que estão associados a uma instância de serviço](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#rc_alias) | 
| [Trabalhando com credenciais de serviço](/docs/resources?topic=resources-service_credentials#service_credentials) | Uma credencial de serviço fornece as informações necessárias para conectar um aplicativo a uma instância de serviço. | [Eventos para gerenciar credenciais de serviço que estão associadas a uma instância de serviço](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#rc_keys) | 
| [Ligando uma instância de serviço a um app](/docs/resources?topic=resources-s2s_binding#s2s_binding) | É possível gerar uma instância ou um alias do Cloud Foundry (CF) de uma instância de serviço com o mesmo nome em um espaço. | [Eventos para ligar uma instância de serviço a um app e desvinculá-la dele](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#rc_bind) |
| [Gerenciando tags](/docs/resources?topic=resources-tag) | Uma tag é um rótulo que você designa a um recurso para filtragem fácil de recursos em sua lista de recursos. | [Eventos para gerenciar tags](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_acc_mgt#at_events_acc_mgt_resources) |
{: caption="Lista de ações da plataforma principal" caption-side="top"} 






## Serviços de segurança integrada da plataforma
{: #platform_integrated_security}

Os serviços de segurança integrados geram eventos que podem ser visualizados por meio da IU da web do {{site.data.keyword.at_full_notm}} na região **Frankfurt (eu-de)**. Para visualizar esses eventos, deve-se [provisionar uma instância](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-provision#provision) do serviço {{site.data.keyword.at_full_notm}} na região **Frankfurt (eu-de)**.
{: note}

A tabela a seguir lista as ações da plataforma de segurança principal que enviam eventos para o {{site.data.keyword.at_full_notm}}:

| Ações                                                     | Descrição | Eventos do {{site.data.keyword.at_full_notm}} |
|-------------------------------------------------------------|-------------|-------------------------------------------|
| [Gerenciando grupos de acesso](/docs/iam?topic=iam-groups#groups) | É possível definir grupos de acesso para organizar um conjunto de usuários e IDs de serviço em uma única entidade que torna mais fácil para você designar permissões. | [Eventos que são gerados quando você gerencia grupos de acesso](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_access) |
| [Gerenciando políticas](/docs/iam?topic=iam-userroles#userroles) | É possível usar o IAM para gerenciar usuários e funções nos serviços de Plataforma e Infraestrutura do {{site.data.keyword.cloud_notm}}. | [Eventos que são gerados quando você gerencia políticas do IAM](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_policies) |
| [Efetue login no {{site.data.keyword.cloud_notm}}](/docs/iam?topic=iam-iamoverview#iamoverview)| É possível efetuar login no {{site.data.keyword.cloud_notm}} usando uma senha, uma chave API ou um código de autorização. Como um usuário federado, é possível efetuar login por meio da interface da linha de comandos (CLI) usando uma senha descartável ou uma chave API. | [Eventos gerados quando um usuário ou um app efetua login no {{site.data.keyword.cloud_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_login) |
| [Gerenciando chaves API da plataforma](/docs/iam?topic=iam-manapikey#platform-api-keys) | É possível definir as chaves API da plataforma no {{site.data.keyword.IBM_notm}} Cloud que estão associadas a um usuário ou a um ID de serviço. | [Eventos que são gerados quando você gerencia as chaves de API da plataforma](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_apikeys) |
| [Gerenciando IDs de serviço](/docs/iam?topic=iam-serviceids#serviceids) | É possível definir IDs de serviço no nível de conta no {{site.data.keyword.IBM_notm}} Cloud. | [Eventos que são gerados quando você gerencia IDs de serviço](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_serviceids) |
{: caption="Lista de serviços de plataforma de segurança principal" caption-side="top"} 



## Serviços de integração da plataforma
{: #integration}

A tabela a seguir lista os serviços de integração que enviam eventos para o {{site.data.keyword.cloudaccesstrailshort}}:

| Serviço     | Descrição | Eventos do {{site.data.keyword.cloudaccesstrailshort}} |
|-------------|-------------|-------------|
| [{{site.data.keyword.messagehub}}](/docs/services/EventStreams?topic=eventstreams-about#about)| O {{site.data.keyword.messagehub}} é um barramento de mensagem de alto rendimento que é construído com o Apache Kafka. Ele é otimizado para a ingestão de eventos no {{site.data.keyword.IBM_notm}} e para a distribuição de fluxo de eventos entre os seus serviços e os seus aplicativos. | [Eventos que são gerados pelo {{site.data.keyword.messagehub}} ](/docs/services/EventStreams?topic=eventstreams-at_events#at_events) |  
{: caption="Lista de serviços de integração de Nuvem que enviam eventos para o {{site.data.keyword.cloudaccesstrailshort}}" caption-side="top"} 



## Serviços de rede da plataforma
{: #network}

A tabela a seguir lista os serviços de rede que enviam eventos para o {{site.data.keyword.at_full_notm}}:

| Serviço     | Descrição | Eventos do {{site.data.keyword.at_full_notm}} |
|-------------|-------------|-------------|
| [IBM Cloud Internet Services (CIS)](/docs/infrastructure/cis?topic=cis-about-ibm-cloud-internet-services-cis#about-ibm-cloud-internet-services-cis)| O IBM Cloud Internet Services (CIS) fornece um serviço de Internet rápido, altamente eficaz, confiável e seguro. | [Eventos que são gerados pelo IBM Cloud Internet Services](/docs/infrastructure/cis?topic=cis-at_events#at_events) |  
{: caption="Lista de serviços de rede" caption-side="top"} 



## Serviços de segurança da plataforma
{: #security}

A tabela a seguir lista os serviços de segurança de Nuvem que enviam eventos para o {{site.data.keyword.cloudaccesstrailshort}}:


| Serviço     | Descrição | Eventos do {{site.data.keyword.at_full_notm}}          |
|-------------|-------------|----------------------------------------------------|
| [{{site.data.keyword.cloudcerts_full_notm}}](/docs/services/certificate-manager?topic=certificate-manager-about-certificate-manager#about-certificate-manager) | É possível usar o {{site.data.keyword.cloudcerts_short}} para gerenciar os certificados SSL para seus apps e serviços baseados no {{site.data.keyword.cloud_notm}}.  | [Eventos que são gerados pelo serviço do {{site.data.keyword.cloudcerts_short}}](/docs/services/certificate-manager?topic=certificate-manager-at_events#at_events) |
{: caption="Lista de serviços de segurança de Nuvem que enviam eventos para o {{site.data.keyword.cloudaccesstrailshort}}" caption-side="top"} 


