---

copyright:
  years: 2019
lastupdated: "2019-06-03"

keywords: IBM Cloud, LogDNA, Activity Tracker, search, filter, events

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


# Criando visualizações customizadas
{: #views}

Por meio da UI da web do {{site.data.keyword.at_full_notm}}, é possível aplicar critérios de procura e filtragem para definir os eventos que são exibidos por meio de uma visualização customizada.
{:shortdesc}


## Pré-requisitos
{: #views_prereqs}

Antes de iniciar, verifique se seu ID do usuário tem permissões para ativar a UI da web e visualizar eventos. A tabela a seguir lista as funções mínimas necessárias para que um usuário possa iniciar a IU da web do {{site.data.keyword.at_full_notm}}, visualizar, procurar e filtrar eventos:

| Atribuição                      | Permissão concedida            |
|---------------------------|-------------------------------|  
| Função de plataforma: `Viewer`     | Permite que o usuário visualize a lista de instâncias de serviço no painel Observabilidade. |
| Função de serviço: `Reader`      | Permite que o usuário ative a UI da web e visualize eventos na UI da web.  |
{: caption="Tabela 1. Funções do IAM" caption-side="top"} 

Para obter mais informações sobre como configurar políticas para um usuário, consulte [Concedendo permissões de usuário para um usuário ou ID de serviço](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-iam_view_events#iam_view_events).



## Etapa 1. Acesse a IU da web e selecione uma visualização
{: #views_step1}

Conclua as etapas a seguir:

1. [Acessar a UI da web](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-launch#launch).
2. Clique no ícone  ** Visualizações **   ![Configuration icon](images/views.png).
3. Selecione  ** Tudo **  ou uma visualização. 


## Etapa 2. Selecione o conjunto de eventos a ser exibido por meio de uma visualização aplicando uma consulta de procura
{: #views_step2}

Para procurar eventos específicos, é possível aplicar uma consulta de procura. 

* É possível fazer procuras simples (procura de sequência de termo único), procura composta (múltiplos termos de procura e operadores), procuras de campo se a linha de log puder ser analisada e outras. Para obter mais informações, consulte [Como pesquisar logs em docs do LogDNA ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://docs.logdna.com/docs/search){:new_window}.
* Os operadores AND e OR fazem distinção entre maiúsculas e minúsculas e devem ficar em letras maiúsculas.

É possível procurar somente eventos para o número de dias que é especificado por meio do plano de serviço da instância.
{: important}


Conclua as etapas a seguir:
1. Insira uma consulta de procura. 
2. Clique em **Enter**. 

À medida que você aplica uma consulta, observe que o nome da visualização muda para **Visualização não salva**.


### Consulta para eventos que são gerados por um serviço
{: #views_step1_1}

Para filtrar eventos para um serviço específico, é necessário inserir a consulta a seguir:

```
_supertenant:SERVICENAME
```
{: codeblock}

Em que `SERVICENAME` é o nome do serviço no {{site.data.keyword.cloud_notm}}.

A tabela a seguir lista os serviços principais:

| Eventos gerados por               | Value                         | Consulta de amostra                     |
|--------------------------------------------|-------------------------------|----------------------------------|
| [Serviço de gerenciamento de acesso do IAM](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_policies)  | `iam-am`  | `_supertenant:iam-am`    |
| [Serviço de identidade do IAM](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_login)   | `iam-identity`    | `_supertenant:iam-identity`  |
| [Serviço de grupos de acesso do IAM](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_access)   | `iam-groups`  | `_supertenant:iam-groups`     |
| [Serviço do controlador de recurso](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-cloud_services#platform_core_integrated)   | `BSS`  | `_supertenant:BSS`  |            
{: caption="Tabela 2. Consultar por nome do serviço" caption-side="top"}

### Consulta para conjuntos de eventos que são gerados por um serviço
{: #views_step1_2}

Quando um serviço gera tipos diferentes de eventos, é possível inserir a consulta a seguir:

```
_supertenant:SERVICENAME [(action TYPEOFACTION)] 
```
{: codeblock}

Em que 

* `SERVICENAME` é o nome do serviço no {{site.data.keyword.cloud_notm}}
* `TYPEOFACTION` é uma consulta composta em que é possível usar operadores AND e OR e também usar o `-` para excluir dados. Observe que os operadores `AND` e `OR` fazem distinção entre maiúsculas e minúsculas e devem ficar em letras maiúsculas.


A tabela a seguir mostra exemplos de como consultar um grupo de eventos que é gerado por um serviço:

| Eventos gerados por               | Tipo de eventos     | Consulta de amostra                     |
|--------------------------------------------|--------------------|---------------------------------|
| `IAM Identity service`                     | [Eventos de login](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_login) | `_supertenant:iam-identity (action login)`  |
| `IAM Identity service`                     | [Eventos de chave de API](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_apikeys) | `_supertenant:iam-identity (action user-apikey) -(action login)`  |
| `IAM Identity service`                     | [Eventos do ID do serviço de conta](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam#at_events_iam_serviceids) | `_supertenant:iam-identity (action account-serviceid)`  |
| `Resource controller`                      | [Provisionando e gerenciando instâncias de serviço](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_rc#rc_provision)   | `_supertenant:BSS (action instance)`  | 
| `Resource controller`                      | [Gerenciando usuários na conta](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_acc_mgt#at_events_acc_mgt_users)   |  `_supertenant:BSS (action user-management.user)`  |                   |
{: caption="Tabela 3. Amostras de consultas mais complexas" caption-side="top"}


### Consulta para eventos que têm uma ação específica
{: #views_step1_3}

Cada evento tem um campo de **ação** que informa sobre a ação que acionou o evento. É possível inserir a consulta a seguir para procurar todos os eventos que tenham a mesma ação:

```
action ACTIONVALUE
```
{: codeblock}

Em que `ACTIONVALUE` é o valor do campo de ação ou parte do valor.

A tabela a seguir mostra exemplos de consultas para diferentes ações:

| Ação                 | Consulta de amostra                     |
|------------------------|----------------------------------|
| Provisionar um serviço | `action instance.create`         |
| Remover uma instância  | `action instance.delete`         |
| Incluir um usuário             | `action user-management.user.create` |
{: caption="Tabela 4. Amostras de consultas por tipo de ação" caption-side="top"}



### Consulta para eventos cuja ação falha
{: #views_step1_4}

Quando uma ação solicitada falha, o campo **resultado** é configurado como **falha**. É possível inserir a seguinte consulta para procurar esse tipo de evento:

```
outcome failure
```
{: codeblock}


### Consulta por criticalidade de evento
{: #views_step1_5}

Cada evento tem um campo **severidade** que define o nível de ameaça que uma ação pode ter sobre a Nuvem. 

Os valores válidos são *normal*, *warning* e *critical*. 
* **Normal** é configurado para ações de rotina na Nuvem. Por exemplo, iniciar uma instância ou atualizar um token. 
* **Warning** é configurado para ações em que um recurso em nuvem é atualizado ou seus metadados são modificados. Por exemplo, atualizar a versão de um nó do trabalhador, renomear um certificado ou renomear uma instância de serviço. 
* **Critical** é configurado para ações que afetam a segurança na Nuvem. Por exemplo, mudar as credenciais de um usuário, excluir dados, acesso não autorizado para trabalhar com um recurso em Nuvem.

É possível inserir a seguinte consulta para procurar esse tipo de evento:

```
severity VALUE
```
{: codeblock}

Em que `VALUE` pode ser configurado como *normal*, *aviso* ou *crítico*

Por exemplo, para consultar eventos críticos, é possível executar a consulta a seguir:

```
severity critical
```
{: codeblock}



## Etapa 3. Criar uma visualização customizada
{: #views_step3}

Depois de aplicar a consulta de procura à visualização **Tudo** ou a uma visualização customizada existente, conclua as etapas a seguir para salvar o resultado como uma visualização customizada:

1. Na UI da web, clique em **Visualização não salva**.
2. Selecione **Salvar como nova visualização/alerta**. A página  * Criar nova visualização *  é aberta.
3. Insira um nome para a visualização no campo *Nome*.
4. Opcionalmente, inclua uma categoria. Insira um nome e, em seguida, clique em **Incluí-lo isso como uma nova categoria de visualização**.
5. Opcionalmente, anexe um alerta. Uma nova seção é exibida para que você configure o alerta.
6. Clique em  ** Salvar visualização **


## Etapa 4. Customizar como as linhas de evento são exibidas por meio de uma visualização
{: #views_step4}

Há opções diferentes para customizar como você vê dados em uma visualização:
* É possível modificar as propriedades de uma visualização. É possível renomear uma visualização, incluir ou modificar a sua descrição e aplicar um formato de linha específico.
* É possível mudar o `log format` na seção *USER PREFERENCES*.
* É possível aplicar um modelo de linha por meio da seção *Ferramentas*. Observe que isso substitui qualquer outra configuração de linha. Se você selecionar **Persistir essas configurações**, todas as visualizações na IU mostrarão dados de acordo com o formato de linha que é especificado nessa seção.
* É possível aplicar cores a termos ou sequências configurando **Destacar termos** na seção **Ferramentas**.



### Mude o formato de linha por meio da página de propriedades da visualização
{: #views_step4_1}

Conclua as etapas a seguir para modificar o formato de uma linha de evento em uma única visualização:

1. Em sua visualização, selecione **Editar propriedades de visualização**. A página *Editar propriedades de visualização* é aberta.

2. Insira um formato de linha customizado na seção **Modelo %LINE customizado**. O padrão é configurado como `{{line}}`.

    Para obter mais informações sobre as diretrizes de modelo de linha, consulte [Diretrizes](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_line).

3. Clique em **Salvar propriedades*.



### Mude o formato de linha por meio da seção de preferências do usuário
{: #views_step4_2}

Na seção **PREFERÊNCIAS DO USUÁRIO**, é possível modificar a ordem dos campos de dados que são exibidos por linha.

Conclua as etapas a seguir para modificar o formato de uma linha de eventos:

1. Na UI da web, clique no ícone **Configuração** ![Ícone Configuração](images/admin.png "Ícone Administrador").
2. Selecione  ** PREFERÊNCIAS DO USUÁRIO **. Uma nova janela é aberta.
3. Selecione  ** Formato de log **.
4. Modifique a seção *Formato de linha* para corresponder aos seus requisitos. Caixas de arrasto.


### Mude o formato de linha por meio do modelo de linha na seção de ferramentas
{: #views_step4_3}

Conclua as etapas a seguir para modificar o formato de uma linha de eventos:

1. Na visualização, clique no ícone **Ferramentas** ![Ícone Ferramentas](images/tool.png "Ícone Ferramentas").
2. No campo **Modelo de linha**, insira o seu formato de linha customizado. Para obter mais informações sobre as diretrizes de modelo de linha, consulte [Diretrizes](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-views#views_line).
3. Opcionalmente, clique em **Persistir essas configurações** para aplicar o formato de linha a todas as visualizações.



### Destacar termos
{: #view_events_step4_4}

Conclua as etapas a seguir para destacar termos em uma visualização:

1. Na visualização, clique no ícone **Ferramentas** ![Ícone Ferramentas](images/tool.png "Ícone Ferramentas").
2. No campo **Modelo de linha**, insira uma palavra ou sequência na seção **Destacar termos**.
3. Opcionalmente, clique em **Persistir essas configurações** para aplicar essas configurações a todas as visualizações.



## Mude o nome e a descrição de uma visualização customizada
{: #views_step5}

É possível renomear uma visualização. É possível incluir ou modificar a descrição de uma visualização.


Conclua as etapas a seguir:

1. Em sua visualização, selecione **Editar propriedades de visualização**. A página *Editar propriedades de visualização* é aberta.

    É possível renomear a visualização, incluir ou modificar a descrição da visualização e aplicar um formato de linha customizado.

2. Insira um novo nome na seção **Renomear visualização** para renomear a visualização.

3. Insira ou modifique a descrição na seção **Descrição**.

4. Clique em **Salvar propriedades**.



## Diretrizes que definem modelos de linha
{: #views_line}

Considere as diretrizes a seguir que devem ser aplicadas ao definir um modelo de linha:
* Use o estilo bigode `{{field.name}}` ou as variáveis de estilo bash `${field.name}` para construir o seu modelo. 
* Use `{{line}}` ou `$@` para referenciar a linha original. 
* Todos os outros caracteres ou as sequências são interpretadas como literal de texto. 


Por exemplo, é possível definir um modelo de linha como `{{initiator.id}} -- {{action}} -- {{message}}` para ver esses campos para cada evento em uma visualização.


