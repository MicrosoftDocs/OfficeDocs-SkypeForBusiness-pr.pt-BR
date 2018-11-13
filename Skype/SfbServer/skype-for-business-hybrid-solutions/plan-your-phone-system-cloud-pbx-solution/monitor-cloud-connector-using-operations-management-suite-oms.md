---
title: Monitorar o conector de nuvem usando o pacote de gerenciamento de operações (OMS)
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: Leia este tópico para saber como monitorar sua versão do conector de nuvem 2.1 e a implantação posterior usando o pacote de gerenciamento de operações da Microsoft (OMS).
ms.openlocfilehash: 19946c0d7701d2fd31c1b41cae58e08cfdf4c52d
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295068"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>Monitorar o conector de nuvem usando o pacote de gerenciamento de operações (OMS)

Leia este tópico para saber como monitorar sua versão do conector de nuvem 2.1 e a implantação posterior usando o pacote de gerenciamento de operações da Microsoft (OMS).

Agora você pode monitorar sua versão do conector de nuvem 2.1 e a implantação posterior usando o pacote de gerenciamento de operações (OMS), uma solução de gerenciamento de TI de nuvem da Microsoft. Análise de Log OMS permite monitorar e analisar a disponibilidade e o desempenho dos recursos, incluindo físicos e máquinas virtuais. Para obter mais informações sobre OMS e análise de Log, consulte [o que é o pacote de gerenciamento de operações (OMS)?](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-overview).

Este tópico inclui as seguintes seções:

- Pré-requisitos

- Configure o conector de nuvem para usar o OMS

- Configurar OMS

- Analisar os alertas no seu repositório de análise de Log

- Conjunto de monitoramento recomendado

## <a name="prerequisites"></a>Pré-requisitos

Antes de poder usar OMS para monitorar sua implantação do conector de nuvem, você precisará do seguinte:

- **Uma conta do Windows Azure e um espaço de trabalho do OMS.** Se você ainda não tiver uma conta do Windows Azure, você precisará criar um para usar a análise de Log OMS. Para obter informações sobre como criar uma conta do Windows Azure e configurar um espaço de trabalho do OMS, consulte [Introdução a um espaço de trabalho de análise de Log](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-get-started).

- **Conector de nuvem versão 2.1 ou posterior**

- **Nova pesquisa de log de análise de log** é necessária para monitoramento de conector de nuvem. Para obter mais informações, consulte [atualizar seu espaço de trabalho de análise de Log do Windows Azure para a nova pesquisa de log](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-log-search-upgrade).

## <a name="configure-cloud-connector-to-use-oms"></a>Configure o conector de nuvem para usar o OMS

Você precisará configurar seu ambiente do local do conector de nuvem para usar o OMS. Para fazer isso, você precisará sua ID de espaço de trabalho do OMS e a chave, que pode ser encontrado usando o portal OMS da seguinte maneira: configurações--\>fontes conectado –\> servidores Windows:

![Captura de tela do Cloud Connector OMS](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

Como configurar o conector de nuvem para usar o OMS depende do seu cenário:

- **Se você estiver instalando um novo dispositivo de conector de nuvem ou você deseja implantar um aparelho de novamente**, siga estas etapas antes de executar Install-CcAppliance:

1. No arquivo CloudConnector.ini seção [comuns], defina o parâmetro OMSEnabled como True.

    Sempre que o conector de nuvem é implantado ou atualizado, ele tentará instalar o agente OMS automaticamente nas VMs. Habilite esse recurso para que o agente OMS pode sobreviver a atualização automática do conector de nuvem.

2. Para configurar o OMS ID e a chave, execute Set-CcCredential - AccountType OMSWorkspace. 

- **Se você estiver instalando um operador OMS em um aparelho de conector de nuvem existente**, siga estas etapas:

1. No arquivo CloudConnector.ini seção [comuns], defina OMSEnabled = true. 

2. Execute Import-CcConfiguration. 

3. Execute Install-CcOMSAgent. 

    > [!NOTE]
    > Se a credencial de OMSWorkspace nunca tiver sido definida, você será solicitado da credencial ao se executar install-CcOMSAgent. 

- **Se você deseja atualizar a ID de espaço de trabalho do OMS ou a chave em um aparelho de conector de nuvem que já tenha instalado um operador OMS:**

1. Para configurar o OMS ID e a chave, execute Set-CcCredential - AccountType OMSWorkspace. 

2. Para aplicar as atualizações, execute o Install-CcOMSAgent. 

- **Para todos os cenários, verifique se os operadores estão conectados da seguinte maneira:**

    No portal do OMS, vá para configurações -\> fontes conectado -\> servidores do Windows. Você verá uma lista de máquinas conectadas. 

## <a name="configure-oms"></a>Configurar OMS

Em seguida, você precisará especificar sua configuração de OMS usando o portal do OMS. Especificamente, você precisará:

- Especifique as informações sobre logs de eventos e contadores de desempenho.

- Crie alertas. 

### <a name="specify-information-about-event-logs-and-performance-counters"></a>Especifique as informações sobre logs de eventos e contadores de desempenho

No portal do OMS, você deve especificar informações sobre os logs de eventos e contadores de desempenho da seguinte maneira:

1. Vá para configurações -\>dados -\>logs de eventos do Windows e adicione os logs de eventos para: 

   - Servidor Lync

   - Aplicativo

     > [!NOTE]
     > Você deve inserir manualmente o Lync Server na caixa de texto. Ela não é exibida como uma opção na lista suspensa. 

     Para obter mais informações, consulte [fontes de dados de log de eventos do Windows na análise de Log](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events)

2. Vá para configurações -\>dados -\> contadores de desempenho do Windows, e adicionar contadores de desempenho para: 

   - **Contadores de nível do sistema operacional**. Você pode adicionar contadores de nível do sistema operacional, como o uso do processador, o uso da memória, o uso da rede, ou você pode usar as soluções existentes, como desempenho e capacidade, Monitor de desempenho de rede sem adicionar contadores explicitamente. Independentemente de como você decide monitorá-los, a Microsoft recomenda que você monitore esses contadores do sistema operacional.

   - **Skype para contadores de negócios**. Existem diversos contadores fornecidos pelo Skype para negócios. Você pode encontrar esses contadores fazendo logon em qualquer servidor de mediação e abrindo o Monitor de desempenho. Esses contadores começam com "LS:". A Microsoft recomenda que você inicie com os seguintes contadores de capacidade no mínimo e adicionar outras pessoas de interesse:

     Total de chamadas ativas:

   - LS:MediationServer - entrada Calls(_Total)\- atual 

   - LS:MediationServer - saída Calls(_Total)\- atual 

     Chamadas de desvio de mídia ativa total:

   - LS:MediationServer - entrada Calls(_Total)\- chamadas de desvio de mídia ativa 

   - LS:MediationServer - saída Calls(_Total)\- chamadas de desvio de mídia ativa 

     > [!NOTE]
     > Você deve inserir manualmente os contadores de desempenho na caixa de texto. Eles não aparecem como opções na lista suspensa. 

     Para obter mais informações, consulte [Windows e Linux fontes de dados de desempenho na análise de Log](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-performance-counters)

### <a name="create-alerts"></a>Criar alertas

Existem dois tipos de alertas no OMS: número de alertas de resultados e os alertas de medida métrico. Para obter mais informações sobre como criar alertas, consulte [Trabalhando com as regras de alerta na análise de Log](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-alerts-creating).

Ao criar alertas, você deve considerar o seguinte:

- Verifique se que o alerta é um alerta de número de resultados, que é a seleção padrão. 

- As consultas de demonstração exigem que o "Número de resultados" é definido como "maior que 0". 

- É recomendável que você defina janela de tempo e frequência de alerta para 5 minutos. 

- É recomendável que você não ative "Suprimir alertas" para alertas de demonstração. 

- Para cenários típicos de alerta, a Microsoft recomenda a criação de um par de alertas: alerta de um erro e a redefinição de um alerta. O alerta de erro, selecione o nível de severidade crítico; o alerta de redefinição, selecione o nível de severidade informativa.

As seções a seguir descrevem como criar alertas de amostra.

 **Criar um par de alerta: "RTCMEDSRV não está em execução em servidores de mediação" e "RTCMEDSRV está em execução em servidores de mediação"**

Para criar esse par de alerta:

- A consulta para o alerta de erro é:

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    A consulta usa o filtro de computador *em que o computador contém "MediationServer"* . O filtro seleciona apenas o computador cujo nome contém a cadeia de caracteres "MediationServer".

     Você faria substitua o filtro filtro seu próprio computador ou simplesmente removê-lo. Você pode criar filtros de cadeia de caracteres complexos sem expressões regulares. Para obter mais informações, consulte [operadores de cadeia de caracteres](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators). Você também pode optar por usar expressões regulares. Além disso, você pode criar um grupo de computadores salvar uma consulta de pesquisa e usando esse grupo como seu filtro do computador em sua consulta de alerta. Para obter mais informações, consulte [grupos de computadores na análise de Log pesquisas de log](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-computer-groups).

    Para cada computador, a consulta de erro será Obtenha o último log de eventos para o início do serviço RTCMEDSRV e parada de serviço. Ele retornará um logon se o último evento é o evento de parada do serviço; ele não retornará nada se o último evento é o evento de inicialização do serviço. Em resumo, a consulta retornará uma lista de servidores cuja RTCMEDSRV for interrompido na janela de tempo. 

- A consulta para o alerta de redefinição é:

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    A consulta reset faz exatamente a oposto coisa da consulta de erro. Para cada computador, ele retornará um se o último evento for o serviço iniciado evento; ele não retornará nada se o último evento é o evento de parada do serviço.

  **Criar um par de alerta: "demais várias chamadas simultâneas em servidores de mediação" e "chamadas simultâneas reverterá para carga normal"**

Para criar esse alerta:

- A consulta para o alerta de erro é:

  ```
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    Para cada computador, a consulta obterá os contadores de últimos de chamada de entrada e chamadas de saída e soma esses dois valores. Ele retornará um log se o valor de soma exceder 500; ele não retornará nada se isso não acontecer. Em resumo, a consulta retornará uma lista de servidores cujas chamadas simultâneas são muitos na janela de tempo.

- A consulta para o alerta de redefinição é:

  ```
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    A consulta reset faz exatamente a oposto coisa da consulta de erro. Para cada computador, a consulta obterá os contadores de últimos de chamada de entrada e chamadas de saída e soma esses dois valores. Ele retornará um log se o valor de soma for menor do que 500; ele retornará nothing caso contrário.

  **Criar um alerta: "uso da CPU \> 90 ou RTCMEDIARELAY interrompido em servidores" alerta**

Para criar esse alerta, a consulta é:

```
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

A consulta receberá todos os contadores de uso do processador e evento de parada do serviço de todos os computadores e o retorno de um log se o uso do processador exceder 90% ou serviço nunca foi interrompido. 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>Analisar os alertas no seu repositório de análise de Log

Para analisar os alertas no seu repositório, use a solução de gerenciamento de alerta. Para obter mais informações, consulte [solução de gerenciamento de alerta no pacote de gerenciamento de operações (OMS)](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-solution-alert-management)

## <a name="recommended-minimal-monitoring-set"></a>Conjunto de monitoramento mínimo recomendado

Para identificar problemas com os logs de eventos e contadores de desempenho: 

- **Logs de eventos.** Para qualquer problema, deve haver um par de eventos, com um conjunto de eventos para indicar que algo está errado, enquanto a outra indica que tudo bem. Para qualquer período de tempo determinado, ele é o último evento gravado que indicará se algo é anormal para esse período de tempo.

- **Contadores de desempenho.** Deve haver um limite para os contadores monitorados.

A tabela a seguir lista os serviços que a Microsoft recomenda monitoring, listando as identificações de evento parar e iniciar:

|Nome do serviço  <br/> |Função de servidor de destino  <br/> |Parar a ID do evento  <br/> |ID do evento de iniciar  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |Servidor de Mediação  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |Servidor de Borda  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |Servidor de Borda  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |Servidor de Borda  <br/> |22003  <br/> |22002  <br/> |

A tabela a seguir lista os problemas de rede que a Microsoft recomenda monitoramento:


| Nome do monitor  <br/>                                        | Função de servidor de destino  <br/> | Expressão de ID do evento de sucesso  <br/> | Expressão de ID do evento de erro  <br/> | Exemplo de falha  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| Servidor de mediação falha de conectividade de gateway  <br/>    | Servidor de Mediação  <br/>   | 25062                              |                                  | 25002  <br/>           |
| Falha na conclusão de chamada do servidor de mediação para gateway  <br/> | Servidor de Mediação  <br/>   | 25064                              |                                  | 25002  <br/>           |
| Problemas críticos de rede  <br/>                           | Servidor de Borda  <br/>        | 14353                              |                                  | 12288  <br/>           |

O exemplo a seguir lista os contadores de capacidade de chamada que devem ser monitorados. Esses números devem ser menor do que 500 para o standard edition de conector de nuvem; menor que 50 Edition mínima do conector de nuvem.

- LS:MediationServer - entrada Calls(_Total)\- atual 

- LS:MediationServer - saída Calls(_Total)\- atual 

- LS:MediationServer - entrada Calls(_Total)\- chamadas de desvio de mídia ativa

- LS:MediationServer - saída Calls(_Total)\- chamadas de desvio de mídia ativa

## <a name="see-also"></a>Consulte também

Para obter mais informações sobre como trabalhar com OMS, consulte o seguinte:

- [Localizar dados usando as pesquisas de log na análise de Log](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-log-searches)

- [Referência de linguagem de análise de Log do Windows Azure](https://docs.loganalytics.io/docs/Language-Reference)

- [Compreensão dos alertas na análise de Log](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-alerts)

- [Conectar computadores Windows para o serviço de Log de análise no Windows Azure](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents)


