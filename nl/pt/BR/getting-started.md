---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: IBM Cloud, LogDNA, Activity Tracker, getting started

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


# Tutorial Introdução
{: #getting-started}

Use o serviço do {{site.data.keyword.at_full}} para controlar como os aplicativos interagem com os serviços do {{site.data.keyword.cloud_notm}}. É possível usar esse serviço para investigar atividades anormais e ações críticas e preencher os requisitos de auditoria regulamentares. Além disso, é possível ser alertado sobre as ações conforme elas acontecem. Os eventos que são coletados obedecem ao padrão Cloud Auditing Data Federation (CADF).
{:shortdesc}

![O serviço {{site.data.keyword.at_full_notm}}](images/atov.png "O serviço {{site.data.keyword.at_full_notm}}")


O {{site.data.keyword.at_full_notm}} coleta e armazena registros de auditoria para chamadas da API feitas para recursos que são executados no {{site.data.keyword.cloud_notm}}. É possível arquivar esses eventos no {{site.data.keyword.cloud_notm}} para armazenamento de longo prazo.
{: note}



## Sobre o {{site.data.keyword.at_full}}
{: #ov}

Conformidade com políticas internas e regulamentações da indústria é um requisito importante na estratégia
de qualquer organização, independentemente de onde os aplicativos são executados: no local, em uma nuvem híbrida ou em
uma nuvem pública. O serviço do {{site.data.keyword.at_full_notm}} fornece a estrutura e a funcionalidade para monitorar chamadas da API para serviços no {{site.data.keyword.cloud_notm}} e produz a evidência para estar em conformidade com as políticas corporativas e regulamentos específicos do segmento de mercado.

Ao trabalhar em um ambiente de nuvem, como o {{site.data.keyword.cloud_notm}}, deve-se planejar a estratégia de nuvem para auditoria e monitoramento de cargas de trabalho e dados de acordo com suas políticas internas e com os requisitos de conformidade baseados no segmento de mercado e no país. É possível usar as informações que são registradas por meio do serviço {{site.data.keyword.at_full_notm}} para
identificar incidentes de segurança, detectar acesso não autorizado e obedecer aos requisitos de auditoria
regulamentares e internos.

* O {{site.data.keyword.at_full_notm}} suporta o controle de segurança de alto nível para seus recursos de TI na nuvem.
* O {{site.data.keyword.at_full_notm}} fornece uma solução para que os administradores capturem, armazenem, visualizem, procurem e monitorem a atividade da API em um único local. Ele também oferece um recurso de notificações para alertá-lo usando qualquer um dos canais de notificação suportados.
* O {{site.data.keyword.at_full_notm}} fornece recursos para exportar eventos que podem ser usados para gerar um relatório de trilha de auditoria. É possível requerer
esses relatórios para que sua organização obedeça às regulamentações internas e às regulamentações externas da
indústria e do país.

![Recursos principais oferecidos pelo serviço do {{site.data.keyword.at_full_notm}}](images/features.png "Recursos principais oferecidos pelo serviço {{site.data.keyword.at_full_notm}}")

Por exemplo, é possível usar os eventos do {{site.data.keyword.at_full_notm}} para identificar as informações a seguir:
* os usuários que fizeram chamadas de API para serviços de nuvem;
* o registro de data e hora de quando as chamadas de API foram feitas;
* o status da chamada de API;
* a criticidade da ação.


Considere as informações a seguir sobre segurança ao trabalhar com o serviço do {{site.data.keyword.at_full_notm}}:

* Os serviços IBM que geram eventos do {{site.data.keyword.at_full_notm}} seguem a política de segurança do {{site.data.keyword.IBM_notm}} Cloud. Para obter mais informações, veja [Confiar na segurança e privacidade do IBM Cloud ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://www.ibm.com/cloud/security){: new_window}.
* O serviço {{site.data.keyword.at_full_notm}} captura ações iniciadas pelo usuário que mudam o estado de serviços de nuvem. As informações não fornecem acesso direto a bancos de dados ou aplicativos.
* Somente usuários autorizados podem visualizar e monitorar os logs de eventos do {{site.data.keyword.at_full_notm}}. Cada usuário é identificado por seu ID exclusivo no {{site.data.keyword.cloud_notm}}.


## Objetivos
{: #gs_objectives}

Conclua este tutorial para aprender como provisionar um serviço no {{site.data.keyword.cloud_notm}}. Descubra quais dados comuns estão disponíveis em cada evento e como eles podem ajudá-lo a monitorar seu ambiente de nuvem. Aprenda a navegar na UI da web. 


## Pré-requisitos
{: #gs_prereq}

* Você precisa de um ID do usuário que seja um membro ou um proprietário de uma conta do {{site.data.keyword.cloud_notm}}. Para obter um ID do usuário do {{site.data.keyword.cloud_notm}}, acesse: [Registro ![Ícone de link externo](../../../icons/launch-glyph.svg "Ícone de link externo")](https://cloud.ibm.com/login){:new_window}.

* Seu ID do {{site.data.keyword.IBM_notm}} deve ter designado políticas do IAM para trabalhar no {{site.data.keyword.cloud_notm}} com o serviço {{site.data.keyword.at_full_notm}}. A tabela a seguir lista as permissões mínimas que você precisa para concluir este tutorial: 

| Recurso                             | Escopo da política de acesso | Atribuição    | Região    | Informações                  |
|--------------------------------------|----------------------------|---------|-----------|------------------------------|
| Grupo de recursos **Padrão**           |  Grupo de recursos            | Editor  | us-south  | Essa política é necessária para permitir que o usuário veja instâncias de serviço no grupo de recursos Padrão.    |
| Serviço {{site.data.keyword.at_full_notm}} |  Grupo de recursos            | Editor  | us-south  | Essa política é necessária para permitir que o usuário provisione e administre o serviço {{site.data.keyword.at_full_notm}} no grupo de recursos Padrão.   |
{: caption="Tabela 1. Lista de políticas do IAM necessárias para concluir o tutorial" caption-side="top"} 

* Se você preferir trabalhar com a linha de comandos, deverá instalar a CLI do {{site.data.keyword.cloud_notm}}. Para obter mais informações, consulte [Instalando a CLI do {{site.data.keyword.cloud_notm}}](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli).


## Etapa 1. Provisionar uma instância do serviço do {{site.data.keyword.at_full_notm}}
{: #gs_step1}

Conclua as etapas a seguir para provisionar uma instância:

1. [Efetue login em sua conta do {{site.data.keyword.cloud_notm}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://cloud.ibm.com/login){:new_window}.

	Após você efetuar login com o seu ID do usuário e senha, a UI do {{site.data.keyword.cloud_notm}} será aberta.

2. Acesse o ícone de menu ![Ícone de menu](../../icons/icon_hamburger.svg). Em seguida, selecione **Observabilidade** para acessar o painel *Observabilidade*.

3. Selecione **Activity Tracker** e, em seguida, clique em **Criar instância**. 

4. Insira um nome para a instância de serviço.

5. Selecione a região na qual você planeja provisionar a instância.

6. Selecione um grupo de recursos. 

    Por padrão, o grupo de recursos **Padrão** é configurado.

    **Nota:** se você não puder selecionar um grupo de recursos, verifique se tem permissões de edição no grupo de recursos no qual você deseja provisionar a instância.

7. Selecione o plano de serviço `Lite`. 

    Por padrão, o plano Lite é configurado.

8. Clique em **Criar**.

Depois de provisionar uma instância, o painel *Activity Tracker* será aberto. 


## Etapa 2. Gerenciar acesso ao serviço
{: #gs_step2}

**Uma política de acesso com uma função de usuário do IAM definida deve ser designada a cada usuário que acessa o serviço {{site.data.keyword.at_full_notm}} em sua conta.** A política determina quais ações o usuário pode executar no contexto do serviço ou da instância selecionada. As ações permitidas são customizadas e definidas como operações que têm permissão para serem executadas no serviço. As ações são, então, mapeadas para funções de usuário do IAM. 

Neste tutorial, você aprenderá como conceder a um usuário permissões de gerenciamento para trabalhar com o serviço do {{site.data.keyword.at_full_notm}} dentro do contexto de um grupo de recursos. [ Saiba mais ](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam#iam).


### 1. Criar um grupo de acesso
{: #gs_step2_step1}

Conclua as etapas a seguir para criar um grupo de acesso:

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **Grupos de acesso**.
2. Clique em **Criar**.
3. Insira um nome e uma descrição opcional para seu grupo e clique em **Criar**.

### 2. Incluir permissões para gerenciar eventos
{: #gs_step2_step2}

Após configurar seu grupo, será possível designar uma política de acesso comum ao grupo.

Para conceder a um usuário a função de administrador para gerenciar instâncias dentro de um grupo de recursos na conta, o usuário deve ter uma política do IAM para o serviço {{site.data.keyword.at_full_notm}} com a função da plataforma **Administrador** dentro do contexto do grupo de recursos. 

Conclua as etapas a seguir para designar uma política a um grupo de acesso por meio da UI:

1. Na barra de menus, clique em **Gerenciar** &gt; **Acessar (IAM)**.
2. Selecione **Grupos de acesso**.
3. Selecione o nome do grupo ao qual você deseja designar acesso. 
4. Clique em **Políticas de acesso**.
5. Clique em **Designar acesso**.
6. Selecione **Designar acesso em um grupo de recursos**.
7. Selecione um grupo de recursos.
8. Se o usuário não tiver uma função que já tenha sido concedida para o grupo de recursos selecionado, escolha uma função para o campo **Designar acesso a um grupo de recursos**. 

    Dependendo da função que você selecionar, o usuário poderá visualizar o grupo de recursos em seu painel, editar o nome do grupo de recursos ou gerenciar o acesso de usuário ao grupo. 
    
    Será possível selecionar **Sem acesso**, se você desejar que o usuário tenha acesso somente ao serviço do {{site.data.keyword.at_full_notm}} no grupo de recursos.

9. Selecione **IBM Cloud Activity Tracker with LogDNA**.
10. Selecione a função da plataforma **Administrador**.
11. Selecione a função de serviço  ** Gerenciador **.
12. Clique em  ** Designar **.


### 3. Incluir o usuário no grupo
{: #gs_step2_step3}

Conclua as etapas a seguir para incluir o usuário no grupo de acesso:
1. Clique em **Incluir usuários** na guia **Usuários**.
2. Selecione o usuário que você deseja incluir da lista e clique em **Incluir no grupo**.



## Etapa 3. Gerar eventos do {{site.data.keyword.at_full_notm}}
{: #gs_step3}

Conclua as etapas a seguir para gerar um evento quando você criar um grupo de acesso:


1. No [catálogo do {{site.data.keyword.cloud_notm}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://cloud.ibm.com/catalog){:new_window}, selecione **Gerenciar** &gt; **Segurança e identidade**.

2. Selecione **Grupos de acesso**.

3. Selecione **Criar**. Em seguida, insira um nome para o grupo de acesso.

4. Clique em **Criar**.

Um grupo de acesso é criado.

## Etapa 4. Ativar a UI da web 
{: #gs_step4}

Conclua as etapas a seguir para ativar a IU da web:

1. [Efetue login em sua conta do {{site.data.keyword.cloud_notm}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://cloud.ibm.com/login){:new_window}.

	Depois de efetuar login com seu ID do usuário e senha, o painel do {{site.data.keyword.cloud_notm}} se abre.

2. No menu de navegação, selecione  ** Observabilidade **. 

3. Selecione **Activity Tracker**. 

    A lista de instâncias disponíveis no {{site.data.keyword.cloud_notm}} é exibida.

4. Selecione uma instância. Em seguida, clique em  ** Visualizar LogDNA **.

A UI da web é aberta. 




## Etapa 5. Visualizando eventos
{: #gs_step5}


O serviço do {{site.data.keyword.at_full_notm}} captura dados de atividade que estão relacionados a chamadas de API e outras ações que são feitas para os serviços de nuvem selecionados no {{site.data.keyword.cloud_notm}}. 

* Os eventos são coletados automaticamente. 
* Os eventos que são coletados no {{site.data.keyword.at_full_notm}} estão em conformidade com o padrão **Cloud Auditing Data Federation (CADF)**. O padrão CADF define um modelo de evento completo que inclui as informações necessárias para
certificar, gerenciar e auditar a segurança de aplicativos em ambientes de nuvem.
* O {{site.data.keyword.at_full_notm}} armazena e agrupa eventos por região. 
* Os eventos que relatam as ações de conta global do {{site.data.keyword.cloud_notm}} são coletados e armazenados na região **US-South**.
* O plano de serviço que você seleciona para sua instância do {{site.data.keyword.at_full_notm}} determina o número de dias que os eventos estão disponíveis para procura por meio da UI da web. 


A qualquer momento, é possível visualizar cada linha de eventos no contexto. Conclua as etapas a seguir para visualizar um evento no contexto: 

1. Na UI da web, clique no ícone **Visualizações** ![Ícone Configuração](images/views.png "Ícone Configuração").
2. Selecione **Tudo**.
3. Identifique uma linha que você deseja explorar.
4. Expanda a linha de eventos. 

    Informações sobre identificadores de linha, tags e rótulos são exibidas.

5. Clique em **Visualizar no contexto** para ver a linha de eventos no contexto de outras entradas desse host, do app ou de ambos.

Quando você concluir a exploração do evento, clique em **Fechar** para fechar a linha.


[ Saiba mais ](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-view_events.md#view_events.md).




## Etapa 6. Aprender sobre a estrutura de um evento
{: #gs_step6}

Os eventos estão em conformidade com o **padrão Cloud Auditing Data Federation (CADF)**. O padrão CADF define um modelo de evento completo que inclui as informações necessárias para
certificar, gerenciar e auditar a segurança de aplicativos em ambientes de nuvem.

O modelo de evento CADF inclui os componentes a seguir:

| Componente | Descrição |
|------------|----------------------------|
| `Action`   | A ação é a operação ou a atividade que um inicializador executa, tenta executar ou está aguardando para concluir. |
| `Initiator`| O inicializador é o recurso que faz uma chamada API e gera um evento CADF. O evento que é acionado depende da ação solicitada pela chamada
API. |
| `Observer` | O observador é o recurso que cria e armazena um registro CADF das informações disponíveis em um evento CADF. |
| `Outcome`  | O resultado é o status da ação com relação ao destino. |
| `Target`   | O destino é o recurso com relação ao qual a ação é executada, a execução é tentada ou cuja conclusão está pendente. |
{: caption="Tabela 2. Componentes que estão disponíveis em um modelo de evento CADF" caption-side="top"} 

[ Saiba mais ](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-event#event).

## Etapas Seguintes
{: #gs_next_steps}

Faça upgrade do plano de serviço do {{site.data.keyword.at_full_notm}} para um plano pago para poder [filtrar eventos](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views.md#views_step1), [procurar eventos](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views.md#views_step2), [definir visualizações](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views.md#views_step3) e [configurar alertas](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-alerts.md#alerts.md). 

Para obter mais informações sobre os planos de serviços do {{site.data.keyword.at_full_notm}}, consulte [Planos de serviço](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-service_plan#service_plan).

