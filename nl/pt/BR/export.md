---

copyright:
  years: 2019
lastupdated: "2019-05-25"

keywords: IBM Cloud, LogDNA, Activity Tracker, export

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

 
# Exportando eventos
{: #export}

É possível exportar dados no formato JSONL de uma instância do {{site.data.keyword.at_full_notm}} para um arquivo local. É possível exportar logs programaticamente usando a API de REST do LogDNA ou meio da IU da web.
{:shortdesc}


## Pré-requisitos
{: #export_prereqs}

* [Saiba mais sobre a exportação de eventos](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-monitor_events#mon_export).

* **Deve-se ter um plano de serviço pago** para o serviço do {{site.data.keyword.at_full_notm}}. [ Saiba mais ](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan#service_plan). 

* Verifique se seu ID de usuário tem permissões para iniciar a IU da web e visualizar eventos. A tabela a seguir lista as funções mínimas necessárias para que um usuário possa iniciar a IU da web do {{site.data.keyword.at_full_notm}}, visualizar, procurar e filtrar eventos:

| Atribuição                      | Permissão concedida            |
|---------------------------|-------------------------------|  
| Função de plataforma: `Viewer`     | Permite que o usuário visualize a lista de instâncias de serviço no painel Observabilidade. |
| Função de serviço: `Reader`      | Permite que o usuário ative a UI da web e visualize eventos na UI da web.  |
{: caption="Tabela 1. Funções do IAM" caption-side="top"} 

Para obter mais informações sobre como configurar políticas para um usuário, consulte [Concedendo permissões de usuário para um usuário ou ID de serviço](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events).


## Etapa 1. Acessar a UI da web
{: #export_step1}

[Acessar a UI da web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).


## Etapa 2. Criar uma visualização
{: #export_step2}

[Criar uma visualização](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views).


## Etapa 3. Exportar dados
{: #export_step3}

Escolha uma das opções a seguir para exportar eventos:

### Opção 1. Exportando eventos por meio da UI da web
{: #export_ui}

Conclua as etapas a seguir para exportar dados:

1. Clique no ícone  ** Visualizações **   ![Configuration icon](images/views.png).
2. Selecione  ** Tudo **  ou uma visualização.
3. Aplique critérios de prazo, filtros e procura até que você veja as entradas que deseja exportar.
4. Clique em **Visualização não salva** se você estiver iniciando por meio da visualização **Tudo**. Clique em seu nome de visualização se você selecionou uma visualização na etapa anterior.
5. Selecione  ** Exportar linhas **. Uma nova janela é aberta.
6. Verifique o intervalo de tempo. Se você precisar mudá-lo, clique no intervalo de tempo predefinido no campo *Mudar o intervalo de tempo para exportação*.
7. Selecione **Preferir linhas mais novas** ou **Preferir linhas mais antigas** no caso de a solicitação de exportação exceder o limite de linha.
8. Verifique seu e-mail. Você recebe um e-mail do **LogDNA** com um link para fazer download de suas linhas exportadas.


### Opção 2. Exportando eventos programaticamente usando a API
{: #export_api}

Conclua as etapas a seguir para exportar eventos programaticamente:

1. Gere uma chave de serviço. 

    **Nota:** deve-se ter a função de **gerenciador** para a instância ou o serviço do {{site.data.keyword.at_full_notm}} para concluir essa etapa.

    1. [Ative a IU da web do {{site.data.keyword.at_full_notm}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch_step2).

    2. Selecione o ícone  ** Configuração **   ![Configuration icon](images/admin.png). Em seguida, selecione  ** Organização **. 

    3. Selecione  ** Chaves API **.

        É possível ver as chaves de serviço que foram criadas. 

    4. Clique em  ** Gerar chave de serviço **. Uma nova chave é incluída na lista. Copie essa chave.

2. Exportar eventos. Execute o comando cURL a seguir:

    ```
    curl "ENDPOINT/v1/export?QUERY_PARAMETERS" -u SERVICE_KEY:
    ```
    {: codeblock}

    Em que 

    * ENDPOINT representa o ponto de entrada para o serviço. Cada região possui uma URL diferente. [ Saiba mais ](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-endpoints#endpoints).
    * QUERY_PARAMETERS são parâmetros que definem os critérios de filtragem que são aplicados à solicitação de exportação.
    * SERVICE_KEY é a chave de serviço que você criou na etapa anterior.

A tabela a seguir lista os parâmetros de consulta que podem ser configurados:

| Parâmetro de consulta | Tipo       | Status     | Descrição |
|-----------|------------|------------|-------------|
| `from`      | `int32`      | Necessário   | Horário de início. Configure como registro de data e hora do UNIX em segundos ou milissegundos. |
| `to`        | `int32`      | Necessário   | Horário de encerramento. Configure como registro de data e hora do UNIX em segundos ou milissegundos.    |
| `size`      | `string`     | Opcional   | Número de linhas de log a serem incluídas na exportação.  | 
| `hosts`     | `string`     | Opcional   | Lista separada por vírgulas de hosts. |
| `apps`      | `string`     | Opcional   | Lista separada por vírgulas de aplicativos. |
| `levels`    | `string`     | Opcional   | Lista separada por vírgulas de níveis de log. |
| `query`     | `string`     | Opcional   | Procurar consulta. Para obter mais informações, consulte  [ Logs de procura ](/docs/services/Log-Analysis-with-LogDNA?topic=LogDNA-view_logs#view_logs_step6). |
| `prefer`    | `string`     | Opcional   | Define as linhas de log que você deseja exportar. Os valores válidos são `head`, as primeiras linhas do log, e `tail`, as últimas linhas do log. Se não especificado, o padrão será padronizado.  |
| `email`     | `string`     | Opcional   | Especifica o e-mail com o link transferível por download de sua exportação. Por padrão, as linhas do log são transmitidas.|
| `emailSubject` | `string`     | Opcional   | Use para configurar o assunto do e-mail. </br>Use `%20` para representar um espaço. Por exemplo, um valor de amostra é `Export%20logs`. |
{: caption="Parâmetros de consulta" caption-side="top"} 

Por exemplo, para transmitir eventos para o terminal, é possível executar o comando a seguir:

```
curl "https://api.us-south.logging.cloud.ibm.com/v1/export?to=$(date +%s)000&from=$(($(date +%s)-86400))000" -u e08c0c759663491880b0d61712346789:
```
{: codeblock}

Para enviar um e-mail com o link para fazer download dos eventos que são especificados na exportação, é possível executar o comando a seguir:

```
curl "https://api.us-south.logging.cloud.ibm.com/v1/export?to=$(date +%s)000&from=$(($(date +%s)-86400))000&email=joe@ibm.com" -u e08c0c759663491880b0d61712346789:
```
{: codeblock}


Para enviar um e-mail com um assunto customizado, é possível executar o comando a seguir:

```
curl "https://api.us-south.logging.cloud.ibm.com/v1/export?to=$(date +%s)000&from=$(($(date +%s)-86400))000&email=joe@ibm.com&emailSubject=Export%20test" -u e08c0c759663491880b0d61712346789:
```
{: codeblock}

