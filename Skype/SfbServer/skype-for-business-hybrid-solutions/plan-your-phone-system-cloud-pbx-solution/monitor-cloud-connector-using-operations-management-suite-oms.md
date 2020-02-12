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
description: Leia este tópico para aprender a monitorar a versão 2,1 do conector de nuvem e posterior usando o Microsoft Operations Management Suite (OMS).
ms.openlocfilehash: 6c63baf078dc865a4e3aef574cff30bedabf3819
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888630"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>Monitor Cloud Connector using Operations Management Suite (OMS).

Leia este tópico para aprender a monitorar a versão 2,1 do conector de nuvem e posterior usando o Microsoft Operations Management Suite (OMS).

Agora você pode monitorar a implantação do conector de nuvem versão 2,1 e posterior usando o Operations Management Suite (OMS), uma solução de gerenciamento de ti da nuvem da Microsoft. A análise de logs do OMS permite que você monitore e analise a disponibilidade e o desempenho de recursos, incluindo máquinas físicas e virtuais. Para obter mais informações sobre OMS e análise de logs, consulte [o que é o OMS (Operations Management Suite)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)

Este tópico inclui as seguintes seções:

- Pré-requisitos

- Configurar o conector de nuvem para usar o OMS

- Configurar o OMS

- Analisar os alertas no repositório de análises de logs

- Conjunto de monitoramento recomendado

## <a name="prerequisites"></a>Pré-requisitos

Antes de usar o OMS para monitorar a implantação do conector de nuvem, será necessário o seguinte:

- **Uma conta do Azure e um espaço de trabalho do OMS.** Se ainda não tiver uma conta do Azure, será necessário criar uma para usar a análise de logs do OMS. Para obter informações sobre como criar uma conta do Azure e configurar um espaço de trabalho do OMS, consulte [introdução a um espaço de trabalho de análise de logs](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).

- **Cloud Connector versão 2,1 ou posterior**

- **Análise de log a pesquisa de novo log** é necessária para o monitoramento do conector de nuvem. Para obter mais informações, consulte [atualizar o espaço de trabalho do Microsoft Azure log Analytics para a nova pesquisa de log](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).

## <a name="configure-cloud-connector-to-use-oms"></a>Configurar o conector de nuvem para usar o OMS

Você precisará configurar seu ambiente local do conector de nuvem para usar o OMS. Para fazer isso, você precisará da ID e da chave do espaço de trabalho do OMS, que pode ser encontrado usando o portal do OMS da\>seguinte maneira: configurações\> -fontes conectadas – Windows Servers:

![Captura de tela para OMS do conector da nuvem](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

A maneira como você configura o conector de nuvem para usar o OMS depende do seu cenário:

- **Se você estiver instalando um novo dispositivo de conector de nuvem ou se quiser reimplantar um dispositivo**, siga estas etapas antes de executar o Install-CcAppliance:

    1. Na seção arquivo CloudConnector. ini [Common], defina o parâmetro OMSEnabled como true.

        Toda vez que o conector da nuvem é implantado ou atualizado, ele tenta instalar o agente do OMS automaticamente nas VMs. Habilite esse recurso para que o agente do OMS possa sobreviver à atualização automática do conector de nuvem.

    2. Para configurar a chave e a ID do OMS, execute Set-CcCredential-AccountType OMSWorkspace. 

- **Se você estiver instalando um agente do OMS em um dispositivo de conexão de nuvem existente**, siga estas etapas:

    1. Na seção arquivo CloudConnector. ini [Common], defina OMSEnabled = true. 

    2. Execute Import-CcConfiguration. 

    3. Execute install-CcOMSAgent. 

        > [!NOTE]
        > Se a credencial OMSWorkspace nunca tiver sido definida, você será solicitado a fornecer uma credencial quando executar instalar-CcOMSAgent. 

- **Se você deseja atualizar a chave ou ID do espaço de trabalho do OMS em um aparelho de conector de nuvem que já instalou um agente do OMS:**

    1. Para configurar a chave e a ID do OMS, execute Set-CcCredential-AccountType OMSWorkspace. 

    2. Para aplicar as atualizações, execute install-CcOMSAgent. 

- **Para todos os cenários, verifique se os agentes estão conectados da seguinte maneira:**

    No portal do OMS, vá para configurações-\> fontes conectadas\> – Windows Servers. Você verá uma lista de máquinas conectadas. 

## <a name="configure-oms"></a>Configurar o OMS

Em seguida, você precisará especificar a configuração do OMS usando o portal do OMS. Especificamente, será necessário:

- Especifique informações sobre logs de eventos e contadores de desempenho.

- Criar alertas. 

### <a name="specify-information-about-event-logs-and-performance-counters"></a>Especificar informações sobre logs de eventos e contadores de desempenho

No portal do OMS, você deve especificar informações sobre os logs de eventos e os contadores de desempenho da seguinte maneira:

1. Vá para configurações-\>dados –\>logs de eventos do Windows e adicione logs de eventos para: 

   - Servidor Lync

   - Aplicativo

     > [!NOTE]
     > Você deve inserir manualmente o Lync Server na caixa de texto. Ele não aparece como uma opção na lista suspensa. 

     Para obter mais informações, consulte [fontes de dados de log de eventos do Windows em análises de logs](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)

2. Vá para configurações-\>dados-\> contadores de desempenho do Windows e adicionar contadores de desempenho para: 

   - **Contadores de nível do sistema operacional**. Você pode adicionar contadores de nível do sistema operacional, como uso do processador, uso da memória, uso da rede ou usar soluções existentes, como capacidade e desempenho, monitor de desempenho de rede sem adicionar contadores explicitamente. Não importa como você decida monitorá-los, a Microsoft recomenda que você monitore esses contadores do sistema operacional.

   - **Contadores do Skype for Business**. Há vários contadores fornecidos pelo Skype for Business. Você pode encontrar esses contadores fazendo logon em qualquer servidor de mediação e abrindo o monitor de desempenho. Estes contadores começam com "LS:". A Microsoft recomenda que você comece com os seguintes contadores de capacidade no mínimo e adicione outros que sejam de interesse:

     Total de chamadas ativas:

       - LS: MediationServer-chamadas de entrada (_Total)\- atuais 

       - LS: MediationServer-chamadas de saída (_Total\- ) atuais 

     Total de chamadas bypass de mídia ativas:

       - LS: MediationServer-chamadas de chamadas de entrada do\- active media (_Total) 

       - LS: MediationServer (_Total)\- chamadas de bypass de mídia ativas 

     > [!NOTE]
     > Você deve inserir manualmente os contadores de desempenho na caixa de texto. Elas não aparecem como opções na lista suspensa. 

     Para obter mais informações, consulte [fontes de dados de desempenho do Windows e Linux em análises de logs](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)

### <a name="create-alerts"></a>Criar alertas

Há dois tipos de alertas no OMS: número de alertas de resultados e alertas de medição métrica. Para obter mais informações sobre a criação de alertas, consulte [trabalhando com regras de alerta na análise de logs](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).

Você deve considerar o seguinte ao criar alertas:

- Verifique se o alerta é um alerta de número de resultados, que é a seleção padrão. 

- As consultas de demonstração exigem que "número de resultados" seja definido como "maior que 0". 

- É recomendável que você defina a frequência da janela de tempo e do alerta como 5 minutos. 

- É recomendável que você não habilite "suprimir alertas" para alertas de demonstração. 

- Para cenários de alerta típicos, a Microsoft recomenda a criação de um par de alertas: um alerta de erro e um alerta de redefinição. Para o alerta de erro, selecione nível de gravidade crítico; para o alerta de redefinição, selecione nível de gravidade informativo.

As seções a seguir descrevem como criar alertas de exemplo.

 **Criar um par de alertas: "RTCMEDSRV não está em execução nos servidores de mediação" e "RTCMEDSRV está em execução nos servidores de mediação"**

Para criar este par de alertas:

- A consulta do alerta de erro é:

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    A consulta usa o filtro do computador *onde o computador contém "MediationServer"* . O filtro seleciona apenas o computador cujo nome contém a cadeia de caracteres "MediationServer".

     Você substituiria o filtro pelo seu próprio filtro de computador ou simplesmente o removerá. Você pode criar filtros de cadeia de caracteres complexas sem expressões regulares. Para obter mais informações, consulte [operadores de cadeia de caracteres](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators). Você também pode optar por usar expressões regulares. Além disso, você pode criar um grupo de computador salvando uma consulta de pesquisa e usando esse grupo como filtro do computador na sua consulta de alerta. Para obter mais informações, consulte [grupos de computadores nas pesquisas de log de análise de logs](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).

    Para cada computador, a consulta de erro obterá o último log de eventos para o início do serviço RTCMEDSRV e o término do serviço. Será retornado um log se o último evento for o evento de parada do serviço; será retornado nada se o último evento for o evento de início do serviço. Em resumo, a consulta retornaria uma lista de servidores cujo RTCMEDSRV está parado na janela de tempo. 

- A consulta para o alerta de redefinição é:

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    A consulta redefinir faz exatamente a coisa oposta da consulta de erro. Para cada computador, ele retornará um se o último evento for o evento de início do serviço; Ele não retornará nada se o último evento for o evento Stop do serviço.

**Criar um par de alertas: "muitas chamadas simultâneas nos servidores de mediação" e "chamadas simultâneas retornam à carga normal"**

Para criar este alerta:

- A consulta do alerta de erro é:

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    Para cada computador, a consulta obterá os últimos contadores de chamadas de entrada e de saída e somará esses dois valores. Será retornado um log se o valor da soma exceder 500; Ele não retornará nada se isso não acontecer. Em resumo, a consulta retornaria uma lista de servidores cujas chamadas simultâneas são muito diferentes na janela de tempo.

- A consulta para o alerta de redefinição é:

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    A consulta redefinir faz exatamente a coisa oposta da consulta de erro. Para cada computador, a consulta obterá os últimos contadores de chamadas de entrada e de saída e somará esses dois valores. Ele retornará um log se o valor soma for menor que 500; Isso não retornará nada do contrário.

**Criar um alerta: alerta "uso \> da CPU 90 ou RTCMEDIARELAY interrompido nos servidores"**

Para criar esse alerta, a consulta é:

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

A consulta receberá todo o contador de uso do processador e evento de parada do serviço de todos os computadores e retornará um log se o uso do processador exceder 90% ou serviço for interrompido. 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>Analisar os alertas no repositório de análises de logs

Para analisar os alertas no repositório, use a solução de gerenciamento de alertas. Para obter mais informações, consulte [solução de gerenciamento de alertas no OMS (Operations Management Suite)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)

## <a name="recommended-minimal-monitoring-set"></a>Conjunto de monitoramento mínimo recomendado

Para identificar problemas com os logs de eventos e os contadores de desempenho: 

- **Logs de eventos.** Em caso de problemas, deve haver um par de eventos, com um conjunto de eventos para indicar que algo está errado, enquanto o outro indica que tudo está bem. Para qualquer período de tempo específico, é o último evento registrado que indicará se algo está inadequado para esse período de tempo.

- **Contadores de desempenho.** Deve haver um limiar para os contadores monitorados.

A tabela a seguir lista os serviços que a Microsoft recomenda monitorar ao listar as IDs de evento stop e start:

|Nome do serviço  <br/> |Função de servidor de destino  <br/> |Parar ID do evento  <br/> |Iniciar ID do evento  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |Servidor de Mediação  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |Servidor de Borda  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |Servidor de Borda  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |Servidor de Borda  <br/> |22003  <br/> |22002  <br/> |

A tabela a seguir lista os problemas de rede que a Microsoft recomenda monitorar:


| Nome do monitor  <br/>                                        | Função de servidor de destino  <br/> | Expressão de ID do evento de sucesso  <br/> | Expressão de ID de evento de erro  <br/> | Exemplo de falha  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| Falha no servidor de mediação para conectividade de gateway  <br/>    | Servidor de Mediação  <br/>   | 25062                              |                                  | 25002  <br/>           |
| Falha na conclusão da chamada do servidor de mediação para gateway  <br/> | Servidor de Mediação  <br/>   | 25064                              |                                  | 25002  <br/>           |
| Problemas críticos na rede  <br/>                           | Servidor de Borda  <br/>        | 14353                              |                                  | 12288  <br/>           |

O seguinte lista os contadores de capacidade de chamada que devem ser monitorados. Esses números devem ser inferiores ao 500 para a edição padrão do conector de nuvem; menor que 50 para a edição mínima do conector de nuvem.

- LS: MediationServer-chamadas de entrada (_Total)\- atuais 

- LS: MediationServer-chamadas de saída (_Total\- ) atuais 

- LS: MediationServer-chamadas de chamadas de entrada do\- active media (_Total)

- LS: MediationServer (_Total)\- chamadas de bypass de mídia ativas

## <a name="see-also"></a>Confira também

Para obter mais informações sobre como trabalhar com o OMS, consulte o seguinte:

- [Localizar dados usando pesquisas de log na análise de logs](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [Referência da linguagem do Azure log Analytics](https://docs.loganalytics.io/docs/Language-Reference)

- [Noções básicas sobre alertas em análises de logs](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [Conectar computadores Windows ao serviço analítico de logs no Azure](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


