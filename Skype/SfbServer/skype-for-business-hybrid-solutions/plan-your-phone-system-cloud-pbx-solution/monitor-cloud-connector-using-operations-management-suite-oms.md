---
title: Monitor Cloud Connector utilizando Operations Management Suite (OMS).
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: Leia este tópico para saber como monitorar sua implantação do Cloud Connector versão 2.1 e posterior usando o Microsoft Operations Management Suite (OMS).
ms.openlocfilehash: eca2f56bf564e376717a42bd8d297710905f8dc6
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359087"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>Monitor Cloud Connector utilizando Operations Management Suite (OMS).

> [!Important]
> O Cloud Connector Edition será destivado em 31 de julho de 2021 junto com o Skype for Business Online. Depois que sua organização atualizou para o Teams, saiba como conectar sua rede de telefonia local ao Teams usando o [Roteamento Direto.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

Leia este tópico para saber como monitorar sua implantação do Cloud Connector versão 2.1 e posterior usando o Microsoft Operations Management Suite (OMS).

Agora você pode monitorar sua implantação do Cloud Connector versão 2.1 e posterior usando o Operations Management Suite (OMS), uma solução de gerenciamento de TI na nuvem da Microsoft. A Análise de Log do OMS permite monitorar e analisar a disponibilidade e o desempenho de recursos, incluindo máquinas físicas e virtuais. Para obter mais informações sobre o OMS e a Análise de Log, consulte [OMS (Operations Management Suite)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)

Este tópico contém as seguintes seções:

- Pré-requisitos

- Configurar o Cloud Connector para usar o OMS

- Configurar o OMS

- Analisar os alertas em seu repositório de Análise de Log

- Conjunto de monitoramento recomendado

## <a name="prerequisites"></a>Pré-requisitos

Antes de usar o OMS para monitorar a implantação do Cloud Connector, você precisará do seguinte:

- **Uma conta do Azure e um espaço de trabalho do OMS.** Se você ainda não tiver uma conta do Azure, precisará criar uma para usar a Análise de Log do OMS. Para obter informações sobre como criar uma conta do Azure e configurar um espaço de trabalho do OMS, consulte [Get started with a Log Analytics workspace](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).

- **Cloud Connector versão 2.1 ou posterior**

- **A nova pesquisa de log do Log Analytics** é necessária para o monitoramento do Cloud Connector. Para obter mais informações, consulte Atualizar seu espaço de trabalho [do Azure Log Analytics para uma nova pesquisa de log.](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade)

## <a name="configure-cloud-connector-to-use-oms"></a>Configurar o Cloud Connector para usar o OMS

Você precisará configurar seu ambiente local do Cloud Connector para usar o OMS. Para fazer isso, você precisará da ID e da chave do espaço de trabalho do OMS, que você pode encontrar usando o portal do OMS da seguinte forma: Configurações – Fontes Conectadas -- Servidores \> \> do Windows:

![Captura de tela do Cloud Connector OMS](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

A maneira como você configura o Cloud Connector para usar o OMS depende do seu cenário:

- **Se você estiver instalando** um novo dispositivo do Cloud Connector ou quiser implantar um dispositivo outra vez, siga estas etapas antes de executar Install-CcAppliance:

    1. Na seção CloudConnector.ini arquivo [Comum], de definir o parâmetro OMSEnabled como True.

        Sempre que o Cloud Connector for implantado ou atualizado, ele tentará instalar o agente OMS automaticamente nas VMs. Habilita esse recurso para que o agente OMS possa sobreviver à atualização automática do Cloud Connector.

    2. Para configurar a ID e a chave do OMS, execute Set-CcCredential -AccountType OMSWorkspace. 

- **Se você estiver instalando um agente OMS em um dispositivo existente do Cloud Connector,** siga estas etapas:

    1. Na seção CloudConnector.ini arquivo [Comum], de definida OMSEnabled=true. 

    2. Execute Import-CcConfiguration. 

    3. Execute Install-CcOMSAgent. 

        > [!NOTE]
        > Se a credencial OMSWorkspace nunca tiver sido definida, você será solicitado a solicitar a credencial ao executar install-CcOMSAgent. 

- **Se você quiser atualizar a ID ou a chave do espaço de trabalho do OMS em um dispositivo do Cloud Connector que já tenha instalado um agente OMS:**

    1. Para configurar a ID e a chave do OMS, execute Set-CcCredential -AccountType OMSWorkspace. 

    2. Para aplicar as atualizações, execute Install-CcOMSAgent. 

- **Para todos os cenários, verifique se os agentes estão conectados da seguinte forma:**

    No portal do OMS, vá para Configurações - \> Fontes Conectadas - \> Servidores do Windows. Você verá uma lista de máquinas conectadas. 

## <a name="configure-oms"></a>Configurar o OMS

Em seguida, você precisará especificar sua configuração do OMS usando o portal do OMS. Especificamente, você precisará:

- Especifique informações sobre logs de eventos e contadores de desempenho.

- Criar alertas. 

### <a name="specify-information-about-event-logs-and-performance-counters"></a>Especificar informações sobre logs de eventos e contadores de desempenho

No portal do OMS, você deve especificar informações sobre os logs de eventos e contadores de desempenho da seguinte forma:

1. Vá para Configurações - Dados - Logs de \> eventos do Windows e adicione logs de eventos \> para: 

   - Lync Server

   - Aplicativo

     > [!NOTE]
     > Você deve inserir manualmente o Lync Server na caixa de texto. Ele não aparece como uma opção na lista lista listada. 

     Para obter mais informações, consulte fontes [de dados do log de eventos do Windows no Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)

2. Vá para Configurações – Dados – Contadores de Desempenho do \> Windows e adicione \> contadores de desempenho para: 

   - **Contadores de nível de sistema operacional.** Você pode adicionar contadores de nível de sistema operacional, como uso de processador, uso de memória, uso de rede ou pode usar soluções existentes, como Capacidade e Desempenho, Monitor de Desempenho de Rede sem adicionar contadores explicitamente. Não importa como você decida monitorá-los, a Microsoft recomenda que você monitore esses contadores do sistema operacional.

   - **Contadores do Skype for Business.** Há vários contadores fornecidos pelo Skype for Business. Você pode encontrar esses contadores fazendo logom em qualquer Servidor de Mediação e abrindo o Monitor de Desempenho. Esses contadores começam com "LS:". A Microsoft recomenda que você comece com os seguintes contadores de capacidade no mínimo e adicione outros que sejam de interesse:

     Total de chamadas ativas:

       - LS:MediationServer - Chamadas de Entrada(_Total) \- Atual 

       - LS:MediationServer - Chamadas de Saída (_Total) \- Atual 

     Total de chamadas de bypass de mídia ativas:

       - LS:MediationServer - Chamadas de Entrada(_Total) Chamadas de bypass de \- mídia ativas 

       - LS:MediationServer - Chamadas de saída (_Total) Chamadas de bypass de \- mídia ativas 

     > [!NOTE]
     > Você deve inserir manualmente os contadores de desempenho na caixa de texto. Elas não são exibidas como opções na lista lista listada. 

     Para obter mais informações, consulte fontes de dados de [desempenho do Windows e linux no Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)

### <a name="create-alerts"></a>Criar alertas

Há dois tipos de alertas no OMS: número de alertas de resultados e alertas de medida métrica. Para obter mais informações sobre como criar alertas, consulte [Trabalhando com regras de alerta no Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).

Você deve considerar o seguinte ao criar alertas:

- Certifique-se de que o alerta seja um alerta número de resultados, que é a seleção padrão. 

- As consultas de demonstração exigem que "Número de resultados" seja definido como "Maior que 0". 

- É recomendável definir a frequência de tempo e de alerta como 5 minutos. 

- É recomendável que você não habilita "Suprimir alertas" para alertas de demonstração. 

- Para cenários de alerta típicos, a Microsoft recomenda criar um par de alertas: um alerta de erro e um alerta de redefinição. Para o alerta de erro, selecione o nível de severidade Crítico; para o alerta de redefinição, selecione o nível de severidade Informacional .

As seções a seguir descrevem como criar alertas de exemplo.

 **Crie um par de alertas: "RTCMEDSRV NÃO está em execução nos Servidores de Mediação" e "RTCMEDSRV está novamente em execução nos Servidores de Mediação"**

Para criar esse par de alertas:

- A consulta para o alerta de erro é:

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    A consulta usa o filtro de computador  *onde Computer contém "MediationServer"*  . O filtro seleciona apenas o computador cujo nome contém a cadeia de caracteres "MediationServer".

     Você substituiria o filtro pelo filtro do seu próprio computador ou simplesmente o removeria. Você pode criar filtros de cadeia de caracteres complexos sem expressões regulares. Para obter mais informações, consulte Operadores [de cadeia de caracteres.](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators) Você também pode optar por usar expressões regulares. Além disso, você pode criar um grupo de computadores salvando uma consulta de pesquisa e usando esse grupo como filtro de computador na consulta de alerta. Para obter mais informações, consulte [Grupos de computadores nas pesquisas de log do Log Analytics.](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups)

    Para cada computador, a consulta de erro obterá o último log de eventos para o início e a parada do serviço RTCMEDSRV. Ele retornará um log se o último evento for o evento de parada de serviço; ele não retornará nada se o último evento for o evento de início do serviço. Em resumo, a consulta retornaria uma lista de servidores cujo RTCMEDSRV está parado na janela de tempo. 

- A consulta para o alerta de redefinição é:

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    A consulta de redefinição faz exatamente o oposto da consulta de erro. Para cada computador, ele retornará um se o último evento for o evento de início do serviço; ele não retornará nada se o último evento for o evento de parada de serviço.

**Crie um par de alertas: " Muitas chamadas simultâneas nos Servidores de Mediação" e "Chamadas simultâneas reacorrem à carga normal"**

Para criar esse alerta:

- A consulta para o alerta de erro é:

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    Para cada computador, a consulta obterá os últimos contadores para chamada de entrada e chamada de saída e somará esses dois valores. Ele retornará um log se o valor da soma exceder 500; ele não retornará nada se não retornar. Em resumo, a consulta retornaria uma lista de servidores cujas chamadas simultâneas são muitas na janela de tempo.

- A consulta para o alerta de redefinição é:

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    A consulta de redefinição faz exatamente o oposto da consulta de erro. Para cada computador, a consulta obterá os últimos contadores para chamada de entrada e chamada de saída e somará esses dois valores. Ele retornará um log se o valor da soma for menor que 500; caso contrário, ele não retornará nada.

**Criar um alerta: alerta "Uso da CPU \> 90 ou RTCMEDIARELAY interrompido em Servidores"**

Para criar esse alerta, a consulta é:

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

A consulta obterá todo o contador de uso do processador e o evento de parada de serviço de todos os computadores e retornará um log se o uso do processador exceder 90% ou o serviço nunca for interrompido. 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>Analisar os alertas em seu repositório de Análise de Log

Para analisar os alertas em seu repositório, use a solução de Gerenciamento de Alertas. Para obter mais informações, consulte [a solução de Gerenciamento de Alertas no Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)

## <a name="recommended-minimal-monitoring-set"></a>Conjunto de monitoramento mínimo recomendado

Para identificar problemas com logs de eventos e contadores de desempenho: 

- **Logs de eventos.** Para qualquer problema, deve haver um par de eventos, com um conjunto de eventos para indicar que algo está errado, enquanto o outro indica que tudo está bem. Por um determinado período de tempo, é o último evento registrado que indicará se algo está errado para esse período.

- **Contadores de desempenho.** Deve haver um limite para os contadores monitorados.

A tabela a seguir lista os serviços que a Microsoft recomenda monitorar listando as IDs de evento de parar e iniciar:

|Nome do Serviço  <br/> |Função de servidor de destino  <br/> |ID do Evento Stop  <br/> |ID do Evento Start  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |Servidor de Mediação  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |Servidor de Borda  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |Servidor de Borda  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |Servidor de Borda  <br/> |22003  <br/> |22002  <br/> |

A tabela a seguir lista os problemas de rede que a Microsoft recomenda monitorar:


| Nome do Monitor  <br/>                                        | Função de servidor de destino  <br/> | Expressão da ID do Evento de Sucesso  <br/> | Expressão de ID do Evento de Erro  <br/> | Exemplo de falha  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| Falha de conectividade do Servidor de Mediação para gateway  <br/>    | Servidor de Mediação  <br/>   | 25062                              |                                  | 25002  <br/>           |
| Falha de conclusão de chamada do Servidor de Mediação para gateway  <br/> | Servidor de Mediação  <br/>   | 25064                              |                                  | 25002  <br/>           |
| Problemas críticos de rede  <br/>                           | Servidor de Borda  <br/>        | 14353                              |                                  | 12288  <br/>           |

A lista a seguir lista os contadores de capacidade de chamada que devem ser monitorados. Esses números devem ser menos de 500 para a edição padrão do Cloud Connector; menos de 50 para a edição mínima do Cloud Connector.

- LS:MediationServer - Chamadas de Entrada(_Total) \- Atual 

- LS:MediationServer - Chamadas de Saída (_Total) \- Atual 

- LS:MediationServer - Chamadas de Entrada(_Total) Chamadas de bypass de \- mídia ativas

- LS:MediationServer - Chamadas de saída (_Total) Chamadas de bypass de \- mídia ativas

## <a name="see-also"></a>Confira também

Para obter mais informações sobre como trabalhar com OMS, consulte o seguinte:

- [Encontrar dados usando pesquisas de log no Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [Referência da linguagem de análise de log do Azure](https://docs.loganalytics.io/docs/Language-Reference)

- [Noções básicas sobre alertas no Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [Conectar computadores Windows ao serviço Log Analytics no Azure](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


