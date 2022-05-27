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
ms.openlocfilehash: c10eac34e065ab76cb570a21752838c308b6afd8
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676503"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>Monitor Cloud Connector utilizando Operations Management Suite (OMS).

> [!Important]
> O Cloud Connector Edition será desativado em 31 de julho de 2021 junto com o Skype for Business Online. Depois que sua organização tiver atualizado para o Teams, saiba como conectar sua rede de telefonia local ao Teams usando o [Roteamento Direto](/MicrosoftTeams/direct-routing-landing-page).

Leia este tópico para saber como monitorar sua implantação do Cloud Connector versão 2.1 e posterior usando o Microsoft Operations Management Suite (OMS).

Agora você pode monitorar sua implantação do Cloud Connector versão 2.1 e posterior usando o OMS (Operations Management Suite), uma solução de gerenciamento de TI na nuvem da Microsoft. O Log Analytics do OMS permite monitorar e analisar a disponibilidade e o desempenho de recursos, incluindo máquinas físicas e virtuais. Para obter mais informações sobre o OMS e o Log Analytics, consulte [O que é o OMS (Operations Management Suite)?](/azure/operations-management-suite/operations-management-suite-overview)

Este tópico contém as seguintes seções:

- Pré-requisitos

- Configurar o Cloud Connector para usar o OMS

- Configurar o OMS

- Analisar os alertas em seu repositório do Log Analytics

- Conjunto de monitoramento recomendado

## <a name="prerequisites"></a>Pré-requisitos

Antes de usar o OMS para monitorar a implantação do Cloud Connector, você precisará do seguinte:

- **Uma conta do Azure e um workspace do OMS.** Se você ainda não tiver uma conta do Azure, precisará criar uma para usar o Log Analytics do OMS. Para obter informações sobre como criar uma conta do Azure e configurar um workspace do OMS, consulte [Introdução com um workspace do Log Analytics](/azure/log-analytics/log-analytics-get-started).

- **Cloud Connector versão 2.1 ou posterior**

- **A nova pesquisa de logs do Log Analytics** é necessária para o monitoramento do Cloud Connector. Para obter mais informações, consulte [Atualizar seu workspace do Azure Log Analytics para a nova pesquisa de logs](/azure/log-analytics/log-analytics-log-search-upgrade).

## <a name="configure-cloud-connector-to-use-oms"></a>Configurar o Cloud Connector para usar o OMS

Você precisará configurar seu ambiente local do Cloud Connector para usar o OMS. Para fazer isso, você precisará da ID e da chave do workspace do OMS, que você pode encontrar usando o portal do OMS da seguinte maneira: Configurações --\>Connected Sources --\> Windows Servers:

![Captura de tela do Cloud Connector OMS.](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

A maneira como você configura o Cloud Connector para usar o OMS depende do seu cenário:

- **Se você estiver instalando um novo dispositivo do Cloud Connector** ou quiser implantar novamente um dispositivo, siga estas etapas antes de executar Install-CcAppliance:

  1. Na seção CloudConnector.ini arquivo [Comum], defina o parâmetro OMSEnabled como True.

     Sempre que o Cloud Connector for implantado ou atualizado, ele tentará instalar o agente do OMS automaticamente nas VMs. Habilite esse recurso para que o agente do OMS possa sobreviver à atualização automática do Cloud Connector.

  2. Para configurar a ID e a chave do OMS, execute Set-CcCredential -AccountType OMSWorkspace.

- **Se você estiver instalando um agente do OMS em um dispositivo existente do Cloud Connector**, siga estas etapas:

  1. Na seção CloudConnector.ini arquivo [Comum], defina OMSEnabled=true.

  2. Execute Import-CcConfiguration.

  3. Execute Install-CcOMSAgent.

     > [!NOTE]
     > Se a credencial do OMSWorkspace nunca tiver sido definida, você será solicitado a fornecer a credencial ao executar install-CcOMSAgent.

- **Se você quiser atualizar a ID ou a chave do workspace do OMS em um dispositivo do Cloud Connector que já instalou um agente do OMS:**

  1. Para configurar a ID e a chave do OMS, execute Set-CcCredential -AccountType OMSWorkspace.

  2. Para aplicar as atualizações, execute Install-CcOMSAgent.

- **Para todos os cenários, verifique se os agentes estão conectados da seguinte maneira:**

    No portal do OMS, vá para Configurações -\> Fontes Conectadas -\> Windows Servidores. Você verá uma lista de computadores conectados.

## <a name="configure-oms"></a>Configurar o OMS

Em seguida, você precisará especificar sua configuração do OMS usando o portal do OMS. Especificamente, você precisará:

- Especifique informações sobre logs de eventos e contadores de desempenho.

- Criar alertas.

### <a name="specify-information-about-event-logs-and-performance-counters"></a>Especificar informações sobre logs de eventos e contadores de desempenho

No portal do OMS, você deve especificar informações sobre os logs de eventos e os contadores de desempenho da seguinte maneira:

1. Vá para Configurações-Data-Windows\>\> Eventos e adicione logs de eventos para:

   - Lync Server

   - Aplicativo

     > [!NOTE]
     > Você deve inserir manualmente o Lync Server na caixa de texto. Ele não aparece como uma opção na lista suspensa.

     Para obter mais informações, [consulte Windows de dados do log de eventos no Log Analytics](/azure/log-analytics/log-analytics-data-sources-windows-events)

2. Vá para Configurações contadores de\> desempenho\> Windows dados e adicione contadores de desempenho para:

   - **Contadores no nível do sistema operacional**. Você pode adicionar contadores de nível de sistema operacional, como uso do processador, uso de memória, uso de rede ou pode usar soluções existentes, como Capacidade e Desempenho, Rede Monitor de Desempenho sem adicionar contadores explicitamente. Não importa como você decida monitorá-los, a Microsoft recomenda que você monitore esses contadores do sistema operacional.

   - **Skype for Business contadores**. Há vários contadores fornecidos pelo Skype for Business. Você pode encontrar esses contadores fazendo logon em qualquer Servidor de Mediação e abrindo o Monitor de Desempenho. Esses contadores começam com "LS:". A Microsoft recomenda que você comece com os seguintes contadores de capacidade no mínimo e adicione outros que sejam de interesse:

     Total de chamadas ativas:

     - LS:MediationServer – Chamadas de entrada (_Total)\- Atual

     - LS:MediationServer – Chamadas de saída (_Total)\- Atual

     Total de chamadas de bypass de mídia ativa:

     - LS:MediationServer – Chamadas de entrada (_Total) Chamadas\- de bypass de mídia ativa

     - LS:MediationServer – Chamadas de saída (_Total) Chamadas\- de bypass de mídia ativa

     > [!NOTE]
     > Você deve inserir manualmente os contadores de desempenho na caixa de texto. Elas não aparecem como opções na lista suspensa.

     Para obter mais informações, [consulte Windows de dados de desempenho do Linux no Log Analytics](/azure/log-analytics/log-analytics-data-sources-performance-counters)

### <a name="create-alerts"></a>Criar alertas

Há dois tipos de alertas no OMS: número de alertas de resultados e alertas de medição de métrica. Para obter mais informações sobre como criar alertas, consulte [Trabalhando com regras de alerta no Log Analytics](/azure/log-analytics/log-analytics-alerts-creating).

Você deve considerar o seguinte ao criar alertas:

- Verifique se o alerta é um alerta número de resultados, que é a seleção padrão.

- As consultas de demonstração exigem que "Número de resultados" seja definido como "Maior que 0".

- É recomendável que você defina a janela De tempo e a frequência de alerta como 5 minutos.

- É recomendável que você não habilite "Suprimir alertas" para alertas de demonstração.

- Para cenários de alerta típicos, a Microsoft recomenda criar um par de alertas: um alerta de erro e um alerta de redefinição. Para o alerta de erro, selecione o nível de severidade Crítico; para o alerta de redefinição, selecione nível de severidade Informativo .

As seções a seguir descrevem como criar alertas de exemplo.

#### <a name="create-an-alert-pair-rtcmedsrv-is-not-running-in-mediation-servers-and-rtcmedsrv-is-back-in-running-in-mediation-servers"></a>Criar um par de alertas: "RTCMEDSRV NÃO está em execução nos Servidores de Mediação" e "RTCMEDSRV está de volta em execução nos Servidores de Mediação"

Para criar esse par de alertas:

- A consulta para o alerta de erro é:

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    A consulta usa o filtro de computador  *em que o computador contém "MediationServer"*  . O filtro seleciona apenas o computador cujo nome contém a cadeia de caracteres "MediationServer".

     Você substituiria o filtro pelo seu próprio filtro de computador ou simplesmente o removeria. Você pode criar filtros de cadeia de caracteres complexos sem expressões regulares. Você também pode optar por usar expressões regulares. Além disso, você pode criar um grupo de computadores salvando uma consulta de pesquisa e usando esse grupo como filtro de computador na consulta de alerta. Para obter mais informações, consulte [Grupos de computadores em pesquisas de log do Log Analytics](/azure/log-analytics/log-analytics-computer-groups).

    Para cada computador, a consulta de erro obterá o último log de eventos para a inicialização do serviço RTCMEDSRV e a parada de serviço. Ele retornará um log se o último evento for o evento de parada de serviço; ele não retornará nada se o último evento for o evento de início do serviço. Em resumo, a consulta retornaria uma lista de servidores cujo RTCMEDSRV é interrompido na janela de tempo.

- A consulta para o alerta de redefinição é:

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    A consulta de redefinição faz exatamente o oposto da consulta de erro. Para cada computador, ele retornará um se o último evento for o evento de início do serviço; ele não retornará nada se o último evento for o evento de parada de serviço.

#### <a name="create-an-alert-pair--too-many-concurrent-calls-in-mediation-servers-and-concurrent-calls-fall-back-to-normal-load"></a>Crie um par de alertas: " Muitas chamadas simultâneas nos Servidores de Mediação" e "Chamadas simultâneas retornam ao carregamento normal"

Para criar este alerta:

- A consulta para o alerta de erro é:

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    Para cada computador, a consulta obterá os últimos contadores para chamada de entrada e chamada de saída e somará esses dois valores. Ele retornará um log se o valor da soma exceder 500; não retornará nada se não retornar. Em resumo, a consulta retornaria uma lista de servidores cujas chamadas simultâneas são muitas na janela de tempo.

- A consulta para o alerta de redefinição é:

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    A consulta de redefinição faz exatamente o oposto da consulta de erro. Para cada computador, a consulta obterá os últimos contadores para chamada de entrada e chamada de saída e somará esses dois valores. Ele retornará um log se o valor da soma for menor que 500; não retornará nada de outra forma.

#### <a name="create-an-alert-cpu-usage--90-or-rtcmediarelay-stopped-in-servers-alert"></a>Criar um alerta: alerta "Uso da \> CPU 90 ou RTCMEDIARELAY parado em servidores"

Para criar esse alerta, a consulta é:

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

A consulta obterá todo o contador de uso do processador e o evento de parada de serviço de todos os computadores e retornará um log se o uso do processador exceder 90% ou se o serviço for interrompido.

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>Analisar os alertas em seu repositório do Log Analytics

Para analisar os alertas em seu repositório, use a solução de Gerenciamento de Alertas. Para obter mais informações, consulte [a solução de Gerenciamento de Alertas no OMS (Operations Management Suite)](/azure/log-analytics/log-analytics-solution-alert-management)

## <a name="recommended-minimal-monitoring-set"></a>Conjunto de monitoramento mínimo recomendado

Para identificar problemas com logs de eventos e contadores de desempenho:

- **Logs de eventos.** Para qualquer problema, deve haver um par de eventos, com um conjunto de eventos para indicar que algo está errado, enquanto o outro indica que tudo está bem. Para qualquer período de tempo determinado, é o último evento gravado que indicará se algo está errado para esse período.

- **Contadores de desempenho.** Deve haver um limite para os contadores monitorados.

A tabela a seguir lista os serviços que a Microsoft recomenda monitorar listando as IDs de evento de parada e início:

|Nome do Serviço  <br/> |Função de Servidor de Destino  <br/> |ID do evento Stop  <br/> |Iniciar A ID do Evento  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |Servidor de Mediação  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |Servidor de Borda  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |Servidor de Borda  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |Servidor de Borda  <br/> |22003  <br/> |22002  <br/> |

A tabela a seguir lista os problemas de rede que a Microsoft recomenda monitorar:


| Nome do Monitor  <br/>                                        | Função de Servidor de Destino  <br/> | Expressão de ID de evento de êxito  <br/> | Expressão de ID de evento de erro  <br/> | Exemplo de falha  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| Servidor de Mediação para falha de conectividade do gateway  <br/>    | Servidor de Mediação  <br/>   | 25062                              |                                  | 25002  <br/>           |
| Falha de conclusão de chamada do Servidor de Mediação para gateway  <br/> | Servidor de Mediação  <br/>   | 25064                              |                                  | 25002  <br/>           |
| Problemas críticos de rede  <br/>                           | Servidor de Borda  <br/>        | 14353                              |                                  | 12288  <br/>           |

O exemplo a seguir lista os contadores de capacidade de chamada que devem ser monitorados. Esses números devem ser menos de 500 para a edição padrão do Cloud Connector; menos de 50 para a edição mínima do Cloud Connector.

- LS:MediationServer – Chamadas de entrada (_Total)\- Atual

- LS:MediationServer – Chamadas de saída (_Total)\- Atual

- LS:MediationServer – Chamadas de entrada (_Total) Chamadas\- de bypass de mídia ativa

- LS:MediationServer – Chamadas de saída (_Total) Chamadas\- de bypass de mídia ativa

## <a name="see-also"></a>Confira também

Para obter mais informações sobre como trabalhar com o OMS, consulte o seguinte:

- [Localizar dados usando pesquisas de log no Log Analytics](/azure/log-analytics/log-analytics-log-searches)

- [Noções básicas sobre alertas no Log Analytics](/azure/log-analytics/log-analytics-alerts)

- [Conexão Windows para o serviço Log Analytics no Azure](/azure/log-analytics/log-analytics-windows-agents)