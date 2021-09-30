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
ms.localizationpriority: medium
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: Leia este tópico para saber como monitorar sua implantação do Cloud Connector versão 2.1 e posterior usando o Microsoft Operations Management Suite (OMS).
ms.openlocfilehash: cf8a79b9b504b5a98592a169d3a507eb938353b9
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012305"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>Monitor Cloud Connector utilizando Operations Management Suite (OMS).

> [!Important]
> O Cloud Connector Edition se aposentará em 31 de julho de 2021 junto com Skype for Business Online. Depois que sua organização tiver sido atualizada para Teams, saiba como conectar sua rede de telefonia local ao Teams usando [Roteamento Direto.](/MicrosoftTeams/direct-routing-landing-page)

Leia este tópico para saber como monitorar sua implantação do Cloud Connector versão 2.1 e posterior usando o Microsoft Operations Management Suite (OMS).

Agora você pode monitorar sua implantação do Cloud Connector versão 2.1 e posterior usando o Operations Management Suite (OMS), uma solução de gerenciamento de TI na nuvem da Microsoft. O OMS Log Analytics permite monitorar e analisar a disponibilidade e o desempenho de recursos, incluindo máquinas físicas e virtuais. Para obter mais informações sobre OMS e Análise de Log, consulte [O que é Operations Management Suite (OMS)?](/azure/operations-management-suite/operations-management-suite-overview)

Este tópico contém as seguintes seções:

- Pré-requisitos

- Configurar o Cloud Connector para usar o OMS

- Configurar OMS

- Analisar os alertas no repositório do Log Analytics

- Conjunto de monitoramento recomendado

## <a name="prerequisites"></a>Pré-requisitos

Antes de usar o OMS para monitorar a implantação do Cloud Connector, você precisará do seguinte:

- **Uma conta do Azure e um espaço de trabalho OMS.** Se você ainda não tiver uma conta do Azure, precisará criar uma para usar o OMS Log Analytics. Para obter informações sobre como criar uma conta do Azure e configurar um espaço de trabalho OMS, consulte [Get started with a Log Analytics workspace](/azure/log-analytics/log-analytics-get-started).

- **Cloud Connector versão 2.1 ou posterior**

- **A nova pesquisa de log do Log Analytics** é necessária para monitoramento do Cloud Connector. Para obter mais informações, [consulte Upgrade your Azure Log Analytics workspace to new log search](/azure/log-analytics/log-analytics-log-search-upgrade).

## <a name="configure-cloud-connector-to-use-oms"></a>Configurar o Cloud Connector para usar o OMS

Você precisará configurar seu ambiente local do Cloud Connector para usar o OMS. Para fazer isso, você precisará da ID e da chave do espaço de trabalho OMS, que você pode encontrar usando o portal OMS da seguinte forma: Configurações - Fontes Conectadas - servidores \> \> Windows:

![Captura de tela para OMS do Cloud Connector.](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

A forma como você configura o Cloud Connector para usar o OMS depende do cenário:

- **Se você estiver instalando um** novo dispositivo do Cloud Connector ou quiser implantar um dispositivo de novo, siga estas etapas antes de executar Install-CcAppliance:

    1. Na seção CloudConnector.ini arquivo [Common], de definir o parâmetro OMSEnabled como True.

        Sempre que o Cloud Connector for implantado ou atualizado, ele tentará instalar o agente OMS automaticamente nas VMs. Habilita esse recurso para que o agente OMS possa sobreviver à atualização automática do Cloud Connector.

    2. Para configurar a ID e a chave do OMS, execute Set-CcCredential -AccountType OMSWorkspace. 

- **Se você estiver instalando um agente OMS em um dispositivo do Cloud Connector** existente, siga estas etapas:

    1. Na seção CloudConnector.ini arquivo [Common], de definir OMSEnabled=true. 

    2. Execute Import-CcConfiguration. 

    3. Execute Install-CcOMSAgent. 

        > [!NOTE]
        > Se a credencial OMSWorkspace nunca tiver sido definida, você será solicitado a solicitar a credencial ao executar install-CcOMSAgent. 

- **Se você quiser atualizar a ID ou a chave do espaço de trabalho OMS em um dispositivo do Cloud Connector que já instalou um agente OMS:**

    1. Para configurar a ID e a chave do OMS, execute Set-CcCredential -AccountType OMSWorkspace. 

    2. Para aplicar as atualizações, execute Install-CcOMSAgent. 

- **Para todos os cenários, verifique se os agentes estão conectados da seguinte forma:**

    No portal OMS, vá para Configurações - \> Fontes Conectadas - \> Windows Servidores. Você verá uma lista de máquinas conectadas. 

## <a name="configure-oms"></a>Configurar OMS

Em seguida, você precisará especificar sua configuração OMS usando o portal OMS. Especificamente, você precisará:

- Especifique informações sobre logs de eventos e contadores de desempenho.

- Criar alertas. 

### <a name="specify-information-about-event-logs-and-performance-counters"></a>Especificar informações sobre logs de eventos e contadores de desempenho

No portal OMS, você deve especificar informações sobre os logs de eventos e os contadores de desempenho da seguinte forma:

1. Vá para Configurações- Logs de eventos Windows dados e \> adicione logs de eventos \> para: 

   - Lync Server

   - Aplicativo

     > [!NOTE]
     > Você deve inserir manualmente o Lync Server na caixa de texto. Ele não aparece como uma opção na listada. 

     Para obter mais informações, [consulte Windows de dados do log de eventos no Log Analytics](/azure/log-analytics/log-analytics-data-sources-windows-events)

2. Vá para Configurações- Contadores de desempenho Windows dados e \> \> adicione contadores de desempenho para: 

   - **Contadores de nível do sistema operacional**. Você pode adicionar contadores de nível de sistema operacional, como uso do processador, uso de memória, uso de rede ou pode usar soluções existentes, como Capacidade e Desempenho, Monitor de Desempenho de Rede sem adicionar contadores explicitamente. Não importa como você decida monitorá-los, a Microsoft recomenda que você monitore esses contadores do sistema operacional.

   - **Skype for Business contadores**. Há vários contadores fornecidos por Skype for Business. Você pode encontrar esses contadores fazendo logo em qualquer Servidor de Mediação e abrindo o Monitor de Desempenho. Esses contadores começam com "LS:". A Microsoft recomenda que você comece com os seguintes contadores de capacidade no mínimo e adicione outros que são de interesse:

     Total de chamadas ativas:

       - LS:MediationServer - Chamadas de entrada(_Total) \- Atual 

       - LS:MediationServer - Chamadas de saída(_Total) \- Atual 

     Total de chamadas de bypass de mídia ativa:

       - LS:MediationServer - Chamadas de entrada(_Total) Chamadas de bypass de \- mídia ativas 

       - LS:MediationServer - Chamadas de saída(_Total) Chamadas de bypass de \- mídia ativas 

     > [!NOTE]
     > Você deve inserir manualmente os contadores de desempenho na caixa de texto. Eles não aparecem como opções na lista lista listada. 

     Para obter mais informações, [consulte Windows e fontes de dados de desempenho do Linux no Log Analytics](/azure/log-analytics/log-analytics-data-sources-performance-counters)

### <a name="create-alerts"></a>Criar alertas

Há dois tipos de alertas no OMS: número de alertas de resultados e alertas de medida métrica. Para obter mais informações sobre como criar alertas, consulte [Working with alert rules in Log Analytics](/azure/log-analytics/log-analytics-alerts-creating).

Você deve considerar o seguinte ao criar alertas:

- Certifique-se de que o alerta seja um alerta número de resultados, que é a seleção padrão. 

- As consultas de demonstração exigem que "Número de resultados" seja definido como "Maior que 0". 

- É recomendável definir a janela Hora e a frequência de alerta como 5 minutos. 

- É recomendável que você não habilita "Suprimir alertas" para alertas de demonstração. 

- Para cenários de alerta típicos, a Microsoft recomenda a criação de um par de alertas: um alerta de erro e um alerta de redefinição. Para o alerta de erro, selecione nível de gravidade Crítico; para o alerta de redefinição, selecione nível de gravidade Informacional .

As seções a seguir descrevem como criar alertas de exemplo.

 **Crie um par de alertas: "RTCMEDSRV NÃO está sendo executado em Servidores de Mediação" e "RTCMEDSRV está de volta em execução em Servidores de Mediação"**

Para criar esse par de alertas:

- A consulta para o alerta de erro é:

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    A consulta usa o filtro do computador  *onde Computer contém "MediationServer"*  . O filtro seleciona apenas o computador cujo nome contém a cadeia de caracteres "MediationServer".

     Você substituiria o filtro por seu próprio filtro de computador ou simplesmente o removeria. Você pode criar filtros de cadeia de caracteres complexos sem expressões regulares. Você também pode optar por usar expressões regulares. Além disso, você pode criar um grupo de computadores salvando uma consulta de pesquisa e usando esse grupo como filtro de computador na consulta de alerta. Para obter mais informações, consulte [Grupos de computadores em Pesquisas de log do Log Analytics.](/azure/log-analytics/log-analytics-computer-groups)

    Para cada computador, a consulta de erro obterá o último log de eventos para o início do serviço RTCMEDSRV e a parada de serviço. Ele retornará um log se o último evento for o evento de parada de serviço; ele não retornará nada se o último evento for o evento de início do serviço. Em resumo, a consulta retornaria uma lista de servidores cujo RTCMEDSRV é interrompido na janela de tempo. 

- A consulta para o alerta de redefinição é:

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    A consulta de redefinição faz exatamente o oposto da consulta de erro. Para cada computador, ele retornará um se o último evento for o evento de início do serviço; ele não retornará nada se o último evento for o evento de parada de serviço.

**Crie um par de alertas: " Muitas chamadas simultâneas em Servidores de Mediação" e "Chamadas simultâneas voltam à carga normal"**

Para criar esse alerta:

- A consulta para o alerta de erro é:

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    Para cada computador, a consulta receberá os últimos contadores para chamada de entrada e chamada de saída e soma esses dois valores. Ele retornará um log se o valor da soma exceder 500; ele não retornará nada se não retornar. Em resumo, a consulta retornaria uma lista de servidores cujas chamadas simultâneas são muitas na janela de tempo.

- A consulta para o alerta de redefinição é:

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    A consulta de redefinição faz exatamente o oposto da consulta de erro. Para cada computador, a consulta receberá os últimos contadores para chamada de entrada e chamada de saída e soma esses dois valores. Ele retornará um log se o valor da soma for menor que 500; ele não retornará nada caso contrário.

**Criar um alerta: alerta "Uso da CPU \> 90 ou RTCMEDIARELAY interrompido em Servidores"**

Para criar esse alerta, a consulta é:

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

A consulta obterá todo o contador de uso do processador e o evento de parada de serviço de todos os computadores e retornará um log se o uso do processador exceder 90% ou se o serviço for interrompido. 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>Analisar os alertas no repositório do Log Analytics

Para analisar os alertas em seu repositório, use a solução gerenciamento de alertas. Para obter mais informações, consulte [Solução de Gerenciamento de Alertas no Operations Management Suite (OMS)](/azure/log-analytics/log-analytics-solution-alert-management)

## <a name="recommended-minimal-monitoring-set"></a>Conjunto de monitoramento mínimo recomendado

Para identificar problemas com logs de eventos e contadores de desempenho: 

- **Logs de eventos.** Para qualquer problema, deve haver um par de eventos, com um conjunto de eventos para indicar que algo está errado, enquanto o outro indica que tudo está bem. Para qualquer determinado período de tempo, é o último evento registrado que indicará se algo está errado para esse período.

- **Contadores de desempenho.** Deve haver um limite para os contadores monitorados.

A tabela a seguir lista os serviços que a Microsoft recomenda monitoramento listando as IDs do evento stop and start:

|Nome do Serviço  <br/> |Função de servidor de destino  <br/> |ID do evento Stop  <br/> |ID do evento Start  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |Servidor de Mediação  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |Servidor de Borda  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |Servidor de Borda  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |Servidor de Borda  <br/> |22003  <br/> |22002  <br/> |

A tabela a seguir lista os problemas de rede que a Microsoft recomenda monitoramento:


| Nome do Monitor  <br/>                                        | Função de servidor de destino  <br/> | Expressão de ID do Evento de Sucesso  <br/> | Expressão de ID do Evento de Erro  <br/> | Exemplo de falha  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| Falha de conectividade do Servidor de Mediação para gateway  <br/>    | Servidor de Mediação  <br/>   | 25062                              |                                  | 25002  <br/>           |
| Falha de conclusão de chamada do Servidor de Mediação para gateway  <br/> | Servidor de Mediação  <br/>   | 25064                              |                                  | 25002  <br/>           |
| Problemas críticos de rede  <br/>                           | Servidor de Borda  <br/>        | 14353                              |                                  | 12288  <br/>           |

O seguinte lista os contadores de capacidade de chamada que devem ser monitorados. Esses números devem ter menos de 500 para a edição padrão do Cloud Connector; menos de 50 para a edição mínima do Cloud Connector.

- LS:MediationServer - Chamadas de entrada(_Total) \- Atual 

- LS:MediationServer - Chamadas de saída(_Total) \- Atual 

- LS:MediationServer - Chamadas de entrada(_Total) Chamadas de bypass de \- mídia ativas

- LS:MediationServer - Chamadas de saída(_Total) Chamadas de bypass de \- mídia ativas

## <a name="see-also"></a>Confira também

Para obter mais informações sobre como trabalhar com OMS, consulte o seguinte:

- [Encontrar dados usando pesquisas de log no Log Analytics](/azure/log-analytics/log-analytics-log-searches)

- [Noções básicas sobre alertas no Log Analytics](/azure/log-analytics/log-analytics-alerts)

- [Conectar computadores Windows ao serviço de Análise de Log no Azure](/azure/log-analytics/log-analytics-windows-agents)