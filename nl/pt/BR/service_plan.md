---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, service plan, price
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

# Planos de serviço
{: #service_plan}

É possível escolher diferentes planos de precificação disponíveis para uma instância do {{site.data.keyword.at_full_notm}}. Cada plano define o número de dias que os dados são retidos para procura, o número de usuários com permissão para gerenciar os dados e os recursos de LogDNA que são ativados.
{:shortdesc}


| Plano                     | 
|--------------------------|
| `30 days log search`  |
| `14 days log search`  |
| `7-day log search`   |
| `Lite`                  |
{: caption="Tabela 1. Lista de planos de serviços" caption-side="top"} 

O {{site.data.keyword.at_full_notm}} oferece um plano `Lite` que pode ser usado para visualizar seus logs à medida que eles passam pelo sistema. É possível visualizar logs usando o registro de log mais recente. Também é possível projetar filtros para se preparar para fazer upgrade para um plano de período de retenção mais longo. Esse plano tem um período de retenção de 0 dias.


## Recursos por plano
{: #svcplan_features}

As tabelas a seguir destacam os diferentes recursos que são incluídos em cada plano de serviço:

| Recurso                          | Plano `30 day log search` | Plano `14 days log search`    | Plano `7 days log search     | Plano `Lite` | 
|----------------------------------|-------------------------|-------------------------------|-----------------------------|--------------|
| `Logs are stored and searchable` | Sim-por 30 dias       | Sim-por 14 dias             | Sim-por 7 dias            | Nenhuma           |
| `Live streaming tail`            | Sim                     | Sim                           | Sim                         | Sim          |
| `Archiving`                      | Sim                     | Sim                           | Sim                         | Nenhuma           |
| `Multi-channel Alerting`         | Sim                     | Sim                           | Sim                         | Nenhuma           | 
{: caption="Tabela 2. Lista de recursos disponíveis para cada plano de serviço" caption-side="top"} 


