---
title: Monitor Cloud Connector using Operations Management Suite (OMS).
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
description: Leia este tópico para saber como monitorar sua implantação do Cloud Connector versão 2,1 e posterior usando o Microsoft Operations Management Suite (OMS).
ms.openlocfilehash: eca2f56bf564e376717a42bd8d297710905f8dc6
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359087"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>Monitor Cloud Connector using Operations Management Suite (OMS).

> [!Important]
> O Cloud Connector Edition vai retirar 31 de julho de 2021 junto com o Skype for Business online. Depois que sua organização tiver atualizado para o Microsoft Teams, saiba como conectar sua rede de telefonia local ao Microsoft Teams usando o [Roteamento direto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).

Leia este tópico para saber como monitorar sua implantação do Cloud Connector versão 2,1 e posterior usando o Microsoft Operations Management Suite (OMS).

Agora você pode monitorar sua implantação do Cloud Connector versão 2,1 e posterior usando o Operations Management Suite (OMS), uma solução de gerenciamento de ti do Microsoft Cloud. A análise de logs do OMS permite monitorar e analisar a disponibilidade e o desempenho de recursos, incluindo máquinas físicas e virtuais. Para obter mais informações sobre o OMS e a análise de logs, consulte [o que é o Operations Management Suite (OMS)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)

Este tópico contém as seguintes seções:

- Pré-requisitos

- Configurar o Cloud Connector para usar o OMS

- Configurar o OMS

- Analisar os alertas no repositório de análise de logs

- Conjunto de monitoramento recomendado

## <a name="prerequisites"></a>Pré-requisitos

Antes de poder usar o OMS para monitorar a implantação do Cloud Connector, você precisará do seguinte:

- **Uma conta do Azure e um espaço de trabalho do OMS.** Se você ainda não tiver uma conta do Azure, será necessário criar uma para usar a análise de logs do OMS. Para obter informações sobre como criar uma conta do Azure e configurar um espaço de trabalho do OMS, confira [introdução a um espaço de trabalho da análise de logs](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).

- **Cloud Connector versão 2,1 ou posterior**

- **Análise de logs o novo log Search** é necessário para o monitoramento do Cloud Connector. Para saber mais, confira [atualizar seu espaço de trabalho da análise de logs do Azure para a nova pesquisa de log](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).

## <a name="configure-cloud-connector-to-use-oms"></a>Configurar o Cloud Connector para usar o OMS

Você precisará configurar o ambiente local do Cloud Connector para usar o OMS. Para fazer isso, você precisará da ID e da chave do espaço de trabalho do OMS, que pode ser encontrada usando o portal do OMS da seguinte maneira: configurações-- \> origens conectadas-- \> servidores Windows:

![Captura de tela para OMS do Cloud Connector](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

O modo como você configura o Cloud Connector para usar o OMS depende do seu cenário:

- **Se você estiver instalando um novo dispositivo do Cloud Connector ou quiser reimplantar um dispositivo**, siga estas etapas antes de executar install-CcAppliance:

    1. Na seção CloudConnector.ini arquivo [comum], defina o parâmetro OMSEnabled como true.

        Cada vez que o Cloud Connector é implantado ou atualizado, ele tentará instalar o agente do OMS automaticamente nas VMs. Habilite esse recurso para que o agente do OMS possa sobreviver à atualização automática do Cloud Connector.

    2. Para configurar a chave e a ID do OMS, execute Set-CcCredential-AccountType OMSWorkspace. 

- **Se você estiver instalando um agente do OMS em um dispositivo do Cloud Connector existente**, siga estas etapas:

    1. Na seção CloudConnector.ini arquivo [comum], defina OMSEnabled = true. 

    2. Execute Import-CcConfiguration. 

    3. Execute install-CcOMSAgent. 

        > [!NOTE]
        > Se a credencial OMSWorkspace nunca tiver sido definida, você será solicitado a fornecer a credencial ao executar install-CcOMSAgent. 

- **Se você deseja atualizar a chave ou ID do espaço de trabalho do OMS em um dispositivo do Cloud Connector que já instalou um agente do OMS:**

    1. Para configurar a chave e a ID do OMS, execute Set-CcCredential-AccountType OMSWorkspace. 

    2. Para aplicar as atualizações, execute install-CcOMSAgent. 

- **Para todos os cenários, verifique se os agentes estão conectados da seguinte maneira:**

    No portal do OMS, vá para configurações- \> fontes conectadas- \> Windows Servers. Você verá uma lista de máquinas conectadas. 

## <a name="configure-oms"></a>Configurar o OMS

Em seguida, será necessário especificar a configuração do OMS usando o portal do OMS. Especificamente, você precisará:

- Especifique informações sobre logs de eventos e contadores de desempenho.

- Criar alertas. 

### <a name="specify-information-about-event-logs-and-performance-counters"></a>Especificar informações sobre logs de eventos e contadores de desempenho

No portal do OMS, você deve especificar informações sobre os logs de eventos e os contadores de desempenho da seguinte maneira:

1. Vá até configurações- \> Data- \> logs de eventos do Windows e adicione logs de eventos para: 

   - Lync Server

   - Aplicativo

     > [!NOTE]
     > Você deve inserir manualmente o Lync Server na caixa de texto. Ela não aparece como uma opção na lista suspensa. 

     Para saber mais, confira [fontes de dados de log de eventos do Windows na análise de logs](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)

2. Vá até configurações- \> Data- \> contadores de desempenho do Windows e adicione contadores de desempenho para: 

   - **Contadores no nível do sistema operacional**. Você pode adicionar contadores de nível de sistema operacional, como uso de processador, uso de memória, uso de rede ou pode usar soluções existentes, como capacidade e desempenho, monitor de desempenho de rede sem adicionar contadores explicitamente. Não importa como você decida monitorar, a Microsoft recomenda que você monitore esses contadores de so.

   - **Contadores do Skype for Business**. Há vários contadores fornecidos pelo Skype for Business. Você pode encontrar esses contadores fazendo logon em qualquer servidor de mediação e abrindo o monitor de desempenho. Esses contadores começam com "LS:". A Microsoft recomenda que você comece com os seguintes contadores de capacidade, no mínimo, e adicione outros que sejam de interesse:

     Total de chamadas ativas:

       - LS: MediationServer-atual chamadas de entrada (_Total) \- 

       - LS: atual MediationServer-chamadas de saída (_Total) \- 

     Total de chamadas de bypass de mídia ativas:

       - LS: chamadas de desvio de mídia MediationServer (_Total) \- ativas 

       - LS: chamadas de desvio de mídia MediationServer (_Total) \- ativas 

     > [!NOTE]
     > Você deve inserir manualmente os contadores de desempenho na caixa de texto. Eles não aparecem como opções na lista suspensa. 

     Para obter mais informações, consulte [Windows and Linux performance Data Sources in log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)

### <a name="create-alerts"></a>Criar alertas

Há dois tipos de alertas no OMS: número de alertas de resultados e alertas de medição métricas. Para obter mais informações sobre como criar alertas, confira [trabalhar com regras de alerta na análise de logs](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).

Você deve considerar o seguinte ao criar alertas:

- Certifique-se de que o alerta é um alerta de número de resultados, que é a seleção padrão. 

- As consultas de demonstração exigem que "número de resultados" seja definido como "maior que 0". 

- É recomendável que você defina a freqüência de alerta e a janela de tempo como 5 minutos. 

- É recomendável não habilitar "suprimir alertas" para alertas de demonstração. 

- Para cenários de alerta típicos, a Microsoft recomenda a criação de um par de alertas: um alerta de erro e um alerta de redefinição. Para o alerta de erro, selecione nível de severidade crítico; para o alerta de redefinição, selecione nível de gravidade Informational.

As seções a seguir descrevem como criar alertas de amostra.

 **Criar um par de alerta: "o RTCMEDSRV não está sendo executado nos servidores de mediação" e "RTCMEDSRV está novamente em execução nos servidores de mediação"**

Para criar este par de alertas:

- A consulta para o alerta de erro é:

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    A consulta usa o filtro computador  *onde computador contém "MediationServer"*  . O filtro seleciona apenas o computador cujo nome contém a cadeia de caracteres "MediationServer".

     Substitua o filtro pelo seu próprio filtro de computador ou simplesmente remova-o. Você pode criar filtros de cadeia de caracteres complexos sem expressões regulares. Para mais informações, consulte [operadores de cadeia de caracteres](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators). Você também pode optar por usar expressões regulares. Além disso, você pode criar um grupo de computadores salvando uma consulta de pesquisa e usando esse grupo como filtro de computador na consulta de alerta. Para obter mais informações, consulte [grupos de computadores nas pesquisas de log de análise de logs](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).

    Para cada computador, a consulta de erro receberá o último log de eventos para o início do serviço RTCMEDSRV e para o serviço de parada. Ele retornará um log se o último evento for o evento de parada do serviço; Ele retornará Nothing se o último evento for o evento de início do serviço. Em suma, a consulta retornaria uma lista de servidores cujo RTCMEDSRV está parado na janela de tempo. 

- A consulta para o alerta de redefinição é:

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    A consulta de redefinição faz exatamente o oposto da consulta de erro. Para cada computador, ele retornará um se o último evento for o evento de início do serviço; Ele retornará Nothing se o último evento for o evento Stop do serviço.

**Criar um par de alerta: "muitas chamadas simultâneas em servidores de mediação" e "chamadas simultâneas retornam à carga normal"**

Para criar esse alerta:

- A consulta para o alerta de erro é:

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    Para cada computador, a consulta receberá os últimos contadores para chamadas de entrada e de saída e somará esses dois valores. Ele retornará um log se o valor SUM exceder 500; Ele retornará nada se isso não acontecer. Em suma, a consulta retornaria uma lista de servidores cujas chamadas simultâneas são muitas na janela de tempo.

- A consulta para o alerta de redefinição é:

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    A consulta de redefinição faz exatamente o oposto da consulta de erro. Para cada computador, a consulta receberá os últimos contadores para chamadas de entrada e de saída e somará esses dois valores. Ele retornará um log se o valor SUM for menor que 500; no entanto, ele não retornará nada.

**Criar um alerta: \> alerta de uso de CPU 90 ou RTCMEDIARELAY parado nos servidores**

Para criar esse alerta, a consulta é:

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

A consulta receberá todos os eventos do contador de uso do processador e do serviço de parada de todos os computadores e retornará um log se o uso do processador exceder 90% ou serviço for interrompido. 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>Analisar os alertas no repositório de análise de logs

Para analisar os alertas em seu repositório, use a solução de gerenciamento de alerta. Para obter mais informações, consulte [Alert Management Solution in Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)

## <a name="recommended-minimal-monitoring-set"></a>Conjunto de monitoramento mínimo recomendado

Para identificar problemas com os logs de eventos e contadores de desempenho: 

- **Logs de eventos.** Para qualquer problema, deve haver um par de eventos, com um conjunto de eventos para indicar que algo está errado, enquanto o outro indica que tudo é bem. Para um determinado período de tempo, é o último evento registrado que indicará se algo está aMiss para esse período de tempo.

- **Contadores de desempenho.** Deve haver um limite para os contadores monitorados.

A tabela a seguir lista os serviços que a Microsoft recomenda para o monitoramento, listando as IDs de evento stop e start:

|Nome do Serviço  <br/> |Função de servidor de destino  <br/> |Parar ID do evento  <br/> |ID do evento inicial  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |Servidor de Mediação  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |Servidor de Borda  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |Servidor de Borda  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |Servidor de Borda  <br/> |22003  <br/> |22002  <br/> |

A tabela a seguir lista os problemas de rede que a Microsoft recomenda monitorar:


| Nome do monitor  <br/>                                        | Função de servidor de destino  <br/> | Expressão de ID do evento Success  <br/> | Expressão de ID de evento de erro  <br/> | Exemplo de falha  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| Falha no servidor de mediação para conectividade de gateway  <br/>    | Servidor de Mediação  <br/>   | 25062                              |                                  | 25002  <br/>           |
| Falha na conclusão da chamada do gateway para servidor de mediação  <br/> | Servidor de Mediação  <br/>   | 25064                              |                                  | 25002  <br/>           |
| Problemas de rede críticos  <br/>                           | Servidor de Borda  <br/>        | 14353                              |                                  | 12288  <br/>           |

O seguinte lista os contadores de capacidade de chamada que devem ser monitorados. Esses números devem ser inferiores a 500 para o Cloud Connector Standard Edition; menos de 50 para a edição mínima do Cloud Connector.

- LS: MediationServer-atual chamadas de entrada (_Total) \- 

- LS: atual MediationServer-chamadas de saída (_Total) \- 

- LS: chamadas de desvio de mídia MediationServer (_Total) \- ativas

- LS: chamadas de desvio de mídia MediationServer (_Total) \- ativas

## <a name="see-also"></a>Confira também

Para obter mais informações sobre como trabalhar com o OMS, confira o seguinte:

- [Localizar dados usando pesquisas de log na análise de logs](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [Referência da linguagem de análise de logs do Azure](https://docs.loganalytics.io/docs/Language-Reference)

- [Noções básicas sobre alertas na análise de logs](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [Conectar computadores Windows ao serviço análise de logs no Azure](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


