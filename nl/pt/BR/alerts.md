---

copyright:
  years: 2019
lastupdated: "2019-05-25"

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
{: #alerts}

Por meio da IU da web do {{site.data.keyword.at_full_notm}}, é possível aplicar consultas de procura para definir os eventos exibidos por meio de uma visualização customizada. Em seguida, é possível conectar um alerta a essa visualização para ser notificado quando uma condição ocorrer. É possível anexar um ou mais alertas a uma visualização. É possível definir múltiplos canais de notificação para um alerta. É possível silenciar alertas. É possível remover alertas de uma visualização.
{:shortdesc}


## Pré-requisitos
{: #alerts_prereqs}

* [Saiba mais sobre alertas](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-monitor_events#mon_alerts).

* **Deve-se ter um plano de serviço pago** para o serviço do {{site.data.keyword.at_full_notm}}. [ Saiba mais ](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan#service_plan).

* Verifique se seu ID de usuário tem permissões para iniciar a IU da web e visualizar eventos. A tabela a seguir lista as funções mínimas necessárias para que um usuário possa iniciar a IU da web do {{site.data.keyword.at_full_notm}}, visualizar, procurar e filtrar eventos:

| Atribuição                      | Permissão concedida            |
|---------------------------|-------------------------------|  
| Função de plataforma: `Viewer`     | Permite que o usuário visualize a lista de instâncias de serviço no painel Observabilidade. |
| Função de serviço: `Reader`      | Permite que o usuário ative a UI da web e visualize eventos na UI da web.  |
{: caption="Tabela 1. Funções do IAM" caption-side="top"} 

Para obter mais informações sobre como configurar políticas para um usuário, consulte [Concedendo permissões de usuário para um usuário ou ID de serviço](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events).

 


## Etapa 1. Acessar a UI da web
{: #alerts_step1}

[Acessar a UI da web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).


## Etapa 2. Criar uma visualização
{: #alerts_step2}

[Criar uma visualização](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views).



## Etapa 3. [Opcional] Configurar uma pré-configuração (modelo de alerta)
{: #alerts_step3}

Para reutilizar uma configuração de alerta com diferentes visualizações, configure uma **pré-configuração de alerta**.
{: note}

Conclua as etapas a seguir para definir uma pré-configuração:

1. Na UI da web, selecione o ícone **Configuração** ![Ícone Administrador](images/admin.png "Ícone Administrador").
2. Selecione  ** Alertas **.
3. Selecione  ** Incluir um alerta de pré-configuração **.
4. Escolha um canal de notificação. Para obter a lista de canais suportados, consulte [Canais de notificação de alerta](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-channels).
5. Selecione o tipo de alerta. Escolha o tipo **Alerta de presença** para obter notificações quando o número de eventos mostrados em uma visualização for maior do que o esperado. Escolha o tipo **Alerta de ausência** para obter notificações quando o número de eventos exibidos em uma visualização for menor do que o esperado ou for ausente. 
5. Escolha um canal de notificação. Para obter a lista de canais suportados, consulte [Canais de notificação de alerta](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-channels).
6. Defina as condições de limite.

    1. Selecione uma frequência de tempo. Por exemplo, 12 horas.

    2. Insira o número de linhas de eventos após o qual deseja que o alerta seja acionado.

    3. Selecione se deseja que ambas as condições sejam verificadas ou apenas uma.

7. Inclua os detalhes para o canal de notificação que você escolheu.

    Por exemplo, para o canal de notificação por e-mail, inclua um ou mais destinatários e, opcionalmente, um fuso horário.

8. Clique em  ** Salvar alerta **.



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
5. Selecione o tipo de alerta. Escolha o tipo **Alerta de presença** para obter notificações quando o número de eventos mostrados em uma visualização for maior do que o esperado. Escolha o tipo **Alerta de ausência** para obter notificações quando o número de eventos exibidos em uma visualização for menor do que o esperado ou for ausente. 
6. Defina as condições de limite.

    1. Selecione uma frequência de tempo. Por exemplo, 12 horas.

    2. Insira o número de linhas de eventos após o qual deseja que o alerta seja acionado.

    3. Selecione se deseja que ambas as condições sejam verificadas ou apenas uma.

7. Inclua os detalhes para o canal de notificação que você escolheu.

    Por exemplo, para o canal de notificação por e-mail, inclua um ou mais destinatários e, opcionalmente, um fuso horário.

8. Clique em  ** Salvar alerta **.



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












