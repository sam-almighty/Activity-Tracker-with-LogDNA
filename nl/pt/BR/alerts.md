---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, alerts, events

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


# Configurar alertas
{: #alerts.md}

Por meio da UI da web do {{site.data.keyword.at_full_notm}}, é possível aplicar critérios de procura e filtragem para definir os eventos que são exibidos por meio de uma visualização customizada. Em seguida, é possível anexar um alerta a uma visualização a ser notificada. É possível anexar um ou mais alertas a uma visualização. É possível definir múltiplos canais de notificação para um alerta. É possível silenciar alertas. É possível remover alertas de uma visualização.
{:shortdesc}


É possível configurar qualquer uma das condições a seguir para um alerta:

* *Frequência de tempo*: especifique com que frequência acionar um alerta. Os valores válidos são: 30 segundos, 1 minuto, 5 minutos, 15 minutos, 30 minutos, 1 hora, 6 horas, 12 horas, 24 horas
* *contador de linhas de eventos*: especifique o número de linhas de eventos que correspondem aos critérios de filtragem e procura da visualização. Quando o número de linhas de eventos é atingido, um alerta é acionado.

É possível decidir se as duas condições são verificadas ou apenas uma. Se ambas as condições forem configuradas, um alerta será acionado quando qualquer um dos limites for atingido. 

Por exemplo, é possível configurar um alerta que é acionado após 30 segundos ou quando 100 linhas de eventos que correspondem aos critérios de filtragem e procura da visualização são coletadas.

É possível configurar diversos canais de notificação. Os canais válidos são: `email`, `Slack`, `PagerDuty`, `Webhook`, `OpsGenie`, `Datadog`, `AppOptics`, `VictorOps`

Também será possível definir uma **pré-configuração**. Uma pré-configuração é um modelo de alerta que pode ser anexado a qualquer número de visualizações. 

Um ícone de sino é exibido com a visualização para indicar que ela tem um alerta anexado.


## Pré-requisitos
{: #views_prereqs}

Antes de iniciar, verifique se seu ID do usuário tem permissões para ativar a UI da web e visualizar eventos. 

**Nota:** deve-se ser um administrador do serviço {{site.data.keyword.at_full_notm}}, um administrador da instância do {{site.data.keyword.at_full_notm}} ou ter permissões de conta do IAM para gerenciar as políticas.

A tabela a seguir lista as políticas mínimas que um usuário deve ter para poder ativar a UI da web do {{site.data.keyword.at_full_notm}} e visualizar, procurar e filtrar eventos:

| Atribuição                      | Permissão concedida            |
|---------------------------|-------------------------------|  
| Função de plataforma: `Viewer`     | Permite que o usuário visualize a lista de instâncias de serviço no painel Observabilidade. |
| Função de serviço: `Reader`        | Permite que o usuário ative a UI da web e visualize eventos na UI da web. |
{: caption="Tabela 1. Políticas do IAM" caption-side="top"} 

Para obter mais informações sobre como configurar essas políticas para um usuário, consulte [Concedendo permissões de usuário a um usuário ou ID de serviço](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events).

**Deve-se ter um plano de serviço pago** para o serviço do {{site.data.keyword.at_full_notm}}. [ Saiba mais ](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan#service_plan). 


## Etapa 1. Acessar a UI da web
{: #alerts_step1}

[Acessar a UI da web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).


## Etapa 2. Criar uma visualização
{: #alerts_step2}

[Criar uma visualização](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views.md#views.md).



## Etapa 3. [Opcional] Configurar uma pré-configuração (modelo de alerta)
{: #alerts_step3}

Para reutilizar uma configuração de alerta com diferentes visualizações, configure uma **pré-configuração de alerta**.
{: note}

Conclua as etapas a seguir para definir uma pré-configuração:

1. Na UI da web, selecione o ícone **Configuração** ![Ícone Administrador](images/admin.png "Ícone Administrador").
2. Selecione  ** Alertas **.
3. Selecione  ** Incluir um alerta de pré-configuração **.
4. Escolha um canal de notificação. 
5. Defina as condições de limite.

    1. Selecione uma frequência de tempo. Por exemplo, 12 horas.

    2. Insira o número de linhas de eventos após o qual deseja que o alerta seja acionado.

    3. Selecione se deseja que ambas as condições sejam verificadas ou apenas uma.

6. Inclua os detalhes para o canal de notificação que você escolheu.

    Por exemplo, para o canal de notificação por e-mail, inclua um ou mais destinatários e, opcionalmente, um fuso horário.

7. Clique em  ** Salvar alerta **.



## Etapa 4. Configurar um alerta
{: #alerts_step4}

Escolha qualquer uma das opções a seguir para conectar um alerta a uma visualização:

### Opção 1. Configurar um alerta usando uma pré-configuração
{: #alerts_step4_preset}

Conclua as etapas a seguir para anexar uma pré-configuração a uma visualização:

1. Na UI da web, clique no ícone **Visualizações** ![Ícone Configuração](images/views.png).
2. Clique no nome da visualização para o qual você deseja anexar um alerta. Em seguida, selecione  ** Anexar um alerta **.
3. Escolha uma pré-configuração para reutilizar uma definição de alerta. 
4. Clique em  ** Salvar alerta **. 




### Opção 2. Configurar um alerta específico de visualização
{: #alerts_step4_view}

Conclua as etapas a seguir para anexar um alerta a uma visualização:

1. Na UI da web, clique no ícone **Visualizações** ![Ícone Configuração](images/views.png).
2. Clique no nome da visualização. Em seguida, selecione  ** Anexar um alerta **.
3. Escolha  ** Alerta Específico da Visualização **.
4. Escolha um canal de notificação. 
5. Defina as condições de limite.

    1. Selecione uma frequência de tempo. Por exemplo, 12 horas.

    2. Insira o número de linhas de eventos após o qual deseja que o alerta seja acionado.

    3. Selecione se deseja que ambas as condições sejam verificadas ou apenas uma.

6. Inclua os detalhes para o canal de notificação que você escolheu.

    Por exemplo, para o canal de notificação por e-mail, inclua um ou mais destinatários e, opcionalmente, um fuso horário.

7. Clique em  ** Salvar alerta **.



## Excluir uma pré-configuração (modelo de alerta)
{: #alerts_delete_preset}

Conclua as etapas a seguir para excluir uma pré-configuração:

1. Na UI da web, selecione o ícone **Configuração** ![Ícone Administrador](images/admin.png "Ícone Administrador").
2. Selecione  ** Alertas **.
3. Passe o mouse sobre o botão *editar* da pré-configuração que você deseja excluir. A opção  * delete *  é mostrada.
4. Selecione  ** Excluir **.
5. Confirme se você deseja excluir a pré-configuração. Clique em **Excluir**.

## Remova de uma visualização um alerta específico
{: #alerts_delete_view}

Conclua as etapas a seguir para remover uma pré-configuração:

1. Na UI da web, selecione o ícone **Configuração** ![Ícone Administrador](images/admin.png "Ícone Administrador").
2. Selecione  ** Alertas **.
3. Passe o mouse sobre o botão *editar* do alerta que você deseja excluir. A opção  * delete *  é mostrada.
4. Selecione  ** Desanexar **.
5. Confirme que deseja excluir o alerta. Clique em  ** Desanexar **.












