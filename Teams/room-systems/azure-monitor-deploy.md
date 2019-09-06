---
title: Implantar o gerenciamento de salas do Microsoft Teams com o Azure monitor
ms.author: v-lanac
author: lanachin
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: Este artigo discute como implantar o gerenciamento de dispositivos de salas do Microsoft Teams de maneira integrada e de ponta a ponta usando o Azure monitor.
ms.openlocfilehash: 4be57f97ef3b0813afef2aefd70c551ee50422ee
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/06/2019
ms.locfileid: "36774679"
---
# <a name="deploy-microsoft-teams-rooms-management-with-azure-monitor"></a>Implantar o gerenciamento de salas do Microsoft Teams com o Azure monitor

Este artigo descreve como configurar e implantar o gerenciamento completo e integrado dos dispositivos de salas do Microsoft Teams usando o Azure monitor.

Você pode configurar a análise de logs no Azure monitor para fornecer telemetria básica e alertas que o ajudarão a gerenciar salas de reunião de sala de reuniões do Microsoft Teams. À medida que sua solução de gerenciamento amadurece, você pode decidir implantar recursos adicionais de gerenciamento e dados para criar uma visão mais detalhada da disponibilidade e do desempenho do dispositivo.

Seguindo este guia, você pode usar um painel como o exemplo a seguir para obter relatórios de status detalhados de disponibilidade do dispositivo, integridade do aplicativo e do hardware e distribuição de versão do sistema operacional e do aplicativo de salas do Microsoft Teams.

![Captura de tela do modo de exibição análise de log de amostra para salas do Microsoft Teams] (../media/Deploy-Azure-Monitor-1.png "Exemplo de exibição de análise de log para salas do Microsoft Teams")

Em um nível superior, é necessário executar as seguintes tarefas:


1. [Validar configuração da análise de logs](azure-monitor-deploy.md#validate_LogAnalytics)
2. [Configurar dispositivos de teste para configuração de gerenciamento de análise de log](azure-monitor-deploy.md#configure_test_devices)
3. [Mapear os campos personalizados](azure-monitor-deploy.md#Custom_fields)
4. [Definir os modos de exibição de salas do Microsoft Teams em análises de logs](azure-monitor-deploy.md#Define_Views)
5. [Definir alertas](azure-monitor-deploy.md#Alerts)
6. [Configurar todos os dispositivos para monitoramento](azure-monitor-deploy.md#configure_all_devices)
7. [Configurar soluções adicionais do Azure monitor](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> Embora com a configuração mínima, a análise de log do Azure monitor pode monitorar um computador que executa um sistema operacional Windows, ainda há algumas salas do Microsoft Teams que você precisa tomar antes de começar a implantar agentes em todas as Microsoft Teams Dispositivos de salas.
> Portanto, é altamente recomendável executar todas as etapas de configuração na ordem certa para uma configuração e configuração controlada. A qualidade do resultado final depende muito da qualidade da configuração inicial.

## <a name="validate-log-analytics-configuration"></a>Validar configuração da análise de logs
<a name="validate_LogAnalytics"> </a>

Você precisa ter um espaço de trabalho de análise de log para começar a coletar logs de dispositivos de salas do Microsoft Teams. Um espaço de trabalho é um ambiente de análise de logs exclusivo com seu próprio repositório de dados, fontes de dados e soluções. Se já tiver um espaço de trabalho de análise de logs existente, você pode usá-lo para monitorar a implantação de salas do Microsoft Teams ou também pode criar um espaço de trabalho de análise de log exclusivo específico para as suas salas do Microsoft Teams monitorar suas necessidades.

Se você precisar criar um novo espaço de trabalho de análise de logs, siga as instruções no artigo [criar um espaço de trabalho de análise de logs no portal do Azure](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)

> [!NOTE]
> Para usar a análise de logs com o Azure monitor, você precisa ter uma assinatura ativa do Azure. Se você não tiver uma assinatura do Azure, poderá criar [uma assinatura de avaliação gratuita](https://azure.microsoft.com/free) como ponto de partida.

### <a name="configure-log-analytics-to-collect-microsoft-teams-rooms-event-logs"></a>Configurar a análise de logs para coletar logs de eventos de salas do Microsoft Teams

A análise de logs coleta apenas eventos dos logs de eventos do Windows que são especificados nas configurações. Para cada log, somente os eventos com as severidades selecionadas são coletados.

Você precisa configurar a análise de logs para coletar os logs necessários para monitorar o dispositivo e o status do aplicativo salas do Microsoft Teams. Dispositivos de salas do Microsoft Teams usam o log de eventos do **sistema de sala do Skype** .

Para configurar a análise de logs para coletar os eventos de salas do Microsoft Teams, consulte [fontes de dados de log de eventos do Windows no Azure monitor](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)

![Captura de tela das configurações do log de eventos] (../media/Deploy-Azure-Monitor-2.png "Configurações do log de eventos")

> [!IMPORTANT]
> Defina as configurações do log de eventos **do** Windows e insira o sistema de salas da Skype como nome do log de eventos e marque as caixas de seleção **erro**, **aviso**e **informações** .

## <a name="configure-test-devices-for-azure-monitoring"></a>Configurar dispositivos de teste para o Azure Monitoring
<a name="configure_test_devices"> </a>

Você precisa preparar a análise de logs para poder monitorar os eventos relacionados a salas do Microsoft Teams. Para começar, você precisa implantar os agentes de monitoramento da Microsoft para apenas um ou dois dispositivos de salas do Microsoft Teams com acesso físico e obter esses dispositivos de teste geram alguns dados e empurre-os para o espaço de trabalho de análise de logs.

### <a name="install-microsoft-monitoring-agents-to-test-devices"></a>Instalar os agentes de monitoramento da Microsoft para dispositivos de teste

Implante o Microsoft Monitoring Agent nos dispositivos de teste usando as instruções fornecidas em [conectar computadores Windows ao serviço analítico de logs no Azure](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows). Este artigo fornece informações detalhadas sobre as etapas para implantar o Microsoft Monitoring Agent para Windows, instruções para obter a ***ID do espaço de trabalho*** da análise de logs e a ***chave primária*** para obter dispositivos de salas do Microsoft Teams conectados a sua implantação do Azure monitor e etapas para verificar a conectividade do agente para a instância de análise de log.

### <a name="generate-sample-microsoft-teams-rooms-events"></a>Gerar exemplos de eventos de salas do Microsoft Teams

Depois que o Microsoft Monitoring Agent é implantado nos dispositivos de teste, verifique se os dados necessários do log de eventos são coletados pelo Azure monitor.

> [!NOTE]
> Reinicie o dispositivo após a instalação do Microsoft Monitoring Agent e verifique se o aplicativo de reunião de salas do Microsoft Teams foi iniciado, para que ele possa gerar novos eventos para o log de eventos.

1.  Entre no portal do [Microsoft Azure](https://portal.azure.com) e vá para análise de logs e selecione seu espaço de trabalho.

2.  Listar os eventos de pulsação gerados por um dispositivo de salas do Microsoft Teams:
    1.  Selecione seu espaço de trabalho e vá para **logs** e use uma consulta para recuperar os registros de pulsação que terão os campos personalizados para as salas do Microsoft Teams.
    2.  Consulta de exemplo:`Event | where Source == "SRS-App" and EventID == 2000`

3.  Certifique-se de que a consulta retorne registros de log que incluam eventos gerados pelo aplicativo reuniões de salas do Microsoft Teams.

4.  Gere um problema de hardware e valide se os eventos necessários estão registrados na análise de logs do Azure.
    1.  Desconecte um dos dispositivos periféricos do sistema de teste de salas do Microsoft Teams. Pode ser a tela câmera, viva-voz, microfone ou sala frontal
    2.  Aguarde 10 minutos para que o log de eventos seja preenchido na análise de logs do Azure.
    3.  Use uma consulta para listar eventos de erro de hardware:`Event | where Source == "SRS-App" and EventID == 3001`

5.  Gere um problema de aplicativo e valide se os eventos necessários estão registrados.
    1.  Modifique a configuração do aplicativo salas do Microsoft Teams e digite um par de endereço/senha SIP (protocolo de iniciação de sessão) incorreto.
    2.  Aguarde 10 minutos para que o log de eventos seja preenchido na análise de logs do Azure.
    3.  Use uma consulta para listar eventos de erro do aplicativo:`Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> Estes registros de eventos de exemplo são necessários para que os campos personalizados possam ser configurados. Não vá para a próxima etapa até que você tenha coletado os logs de eventos necessários.

## <a name="map-custom-fields"></a>Mapear os campos personalizados
<a name="Custom_fields"> </a>

Use campos personalizados para extrair dados específicos dos logs de eventos. Você precisa definir campos personalizados que serão usados posteriormente com seus blocos, exibições de painel e alertas. Veja [campos personalizados na análise de logs](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields) e familiarize-se com os conceitos antes de começar a criar seus campos personalizados.

Para extrair seus campos personalizados dos logs de eventos capturados, siga estas etapas:

1.  Entre no portal do [Microsoft Azure](https://portal.azure.com) e vá para análise de logs e selecione seu espaço de trabalho.

2. Listar os eventos gerados por um dispositivo de salas do Microsoft Teams:
   1.  Vá para **logs** e use uma consulta para recuperar os registros que terão o campo personalizado.
   2.  Consulta de exemplo:`Event | where Source == "SRS-App" and EventID == 2000`

3. Selecione um dos registros, selecione o botão à esquerda e inicie o assistente de extração de campos.
4. Realce os dados que você deseja extrair do RenderedDescription e forneça um título de campo. Os nomes de campo que você deve usar são fornecidos na tabela 1.

   ![Definição de campo personalizado] (../media/Deploy-Azure-Monitor-4.png "Definição de campo personalizado")

5. Use os mapeamentos mostrados na *tabela 1*. A análise de log acrescentará automaticamente a cadeia de caracteres do ** \_CF** quando você definir o novo campo.

> [!IMPORTANT]
> Lembre-se de que todos os campos JSON e analítico de log diferenciam maiúsculas de minúsculas.
> 
> Preste atenção às consultas necessárias para cada campo personalizado na tabela abaixo. Você precisa usar as consultas corretas para análise de log para extrair com êxito valores de campos personalizados.
> 
 ![Definição de campo personalizado] (../media/Deploy-Azure-Monitor-5.png "Definição de campo personalizado")

**Tabela 1**

| **Campo JSON**                   | **Campo personalizado de análise de logs** | **ID do evento** | **Consulta a ser usada com a extração**                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| Descrição                      | SRSEventDescription         | **2000**     | Evento \| em que Source = = "SRS-app" e EventID = = 2000 |
| ResourceState                    | SRSResourceState            | **2000**     | Evento \| em que Source = = "SRS-app" e EventID = = 2000 |
| OperationName                    | SRSOperationName            | **2000**     | Evento \| em que Source = = "SRS-app" e EventID = = 2000 |
| OperationResult                  | SRSOperationResult          | **2000**     | Evento \| em que Source = = "SRS-app" e EventID = = 2000 |
| Sistema operacional                               | SRSOSVersion                | **2000**     | Evento \| em que Source = = "SRS-app" e EventID = = 2000 |
| Versão do sistema operacional                        | SRSOSLongVersion            | **2000**     | Evento \| em que Source = = "SRS-app" e EventID = = 2000 |
| Alias                            | SRSAlias                    | **2000**     | Evento \| em que Source = = "SRS-app" e EventID = = 2000 |
| DisplayName                      | SRSDisplayName              | **2000**     | Evento \| em que Source = = "SRS-app" e EventID = = 2000 |
| AppVersion                       | SRSAppVersion               | **2000**     | Evento \| em que Source = = "SRS-app" e EventID = = 2000 |
| IPv4Address                      | SRSIPv4Address              | **2000**     | Evento \| em que Source = = "SRS-app" e EventID = = 2000 |
| IPv6Address                      | SRSIPv6Address              | **2000**     | Evento \| em que Source = = "SRS-app" e EventID = = 2000 |
| Status do microfone da conferência     | SRSConfMicrophoneStatus     | **3001**     | Evento \| em que Source = = "SRS-app" e EventID = = 3001 |
| Status do palestrante da conferência        | SRSConfSpeakerStatus        | **3001**     | Evento \| em que Source = = "SRS-app" e EventID = = 3001 |
| Status padrão do alto-falante           | SRSDefaultSpeakerStatus     | **3001**     | Evento \| em que Source = = "SRS-app" e EventID = = 3001 |
| Status da câmera                    | SRSCameraStatus             | **3001**     | Evento \| em que Source = = "SRS-app" e EventID = = 3001 |
| Status de exibição da frente do espaço     | SRSFORDStatus               | **3001**     | Evento \| em que Source = = "SRS-app" e EventID = = 3001 |
| Status do sensor de movimento             | SRSMotionSensorStatus       | **3001**     | Evento \| em que Source = = "SRS-app" e EventID = = 3001 |
| Status de inclusão de HDMI               | SRSHDMIIngestStatus         | **3001**     | Evento \| em que Source = = "SRS-app" e EventID = = 3001 |


## <a name="define-the-microsoft-teams-rooms-views-in-log-analytics"></a>Definir os modos de exibição de salas do Microsoft Teams em análises de logs
<a name="Define_Views"> </a>

Depois que os dados são coletados e os campos personalizados são mapeados, você pode usar o View Designer para desenvolver um painel contendo vários blocos para monitorar os eventos de salas do Microsoft Teams. Use o designer de exibição para criar os blocos a seguir. Para obter mais informações, consulte [criar modos de exibição personalizados usando o designer de exibição na análise de logs](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> As etapas anteriores deste guia devem ter sido concluídas para que os blocos do painel funcionem corretamente.

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a>Criar um painel de salas do Microsoft Teams usando o método de importação

Você pode importar um painel de salas do Microsoft Teams e começar a monitorar seus dispositivos rapidamente. Siga as etapas a seguir para importar o painel:

1.  Obtenha o arquivo de painel [SkypeRoomSystems_v2. omsview](https://go.microsoft.com/fwlink/?linkid=835675) .
2.  Entre no portal do [Microsoft Azure](https://portal.azure.com) e vá para análise de logs e selecione seu espaço de trabalho.
3.  Abrir o **Designer de exibição**.
4.  Selecione **importar**e, em seguida, selecione o arquivo **SkypeRoomSystems_v2. omsview** .
5.  Selecione **salvar**.

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>Criar um painel de salas do Microsoft Teams manualmente

Você também pode criar seu próprio painel e adicionar apenas os blocos que deseja monitorar.

#### <a name="configure-the-overview-tile"></a>Configurar o bloco de visão geral

1.  Abrir o **Designer de exibição**.
2.  Selecione **bloco visão geral**e, em seguida, selecione **dois números** na galeria.
3.  Nomeie as **salas do Microsoft Teams**em blocos.
4.  Defina o **primeiro bloco**:<br>
    **Legenda:** Dispositivos que enviaram uma pulsação pelo menos uma vez no mês passado<br>
    **Consulta:**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  Defina o **segundo bloco**:<br>
    **Legenda:** Dispositivos ativos que enviaram uma pulsação na última hora<br>
    **Consulta:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  Selecione **aplicar**.

### <a name="create-a-tile-that-displays-active-devices"></a>Criar um bloco que exiba dispositivos ativos

1.  Selecione **exibir painel** para começar a adicionar blocos.
2.  Selecionar **número & lista** da Galeria
3.  Defina as propriedades **gerais** :<br>
    **Título do Grupo:** Status do Heartbeat<br>
    **Novo grupo:** Selecionado
4.  Defina as propriedades do **bloco** :<br>
    **Legenda:** Dispositivos ativos (pulsação enviada nos últimos 20 minutos)<br>
    **Consulta de bloco: ** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  Defina as propriedades da **lista** :<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  Definir **títulos de coluna**:<br>
    **Nome:** Nome do computador<br>
    **Valor:** Última pulsação
7.  Definir uma **consulta de navegação**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Selecione **aplicar**e **fechar**.

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>Criar um bloco que exiba dispositivos com problemas de conectividade

1.  Selecione **número & lista** da galeria e, em seguida, adicione um novo bloco.
2.  Defina as propriedades **gerais** :<br>
    **Título do Grupo:** Deixar vazio<br>
    **Novo grupo:** Não selecionada
3.  Defina as propriedades do **bloco** :<br>
    **Legenda:** Dispositivos inativos (nenhuma mensagem de pulsação enviada nos últimos 20 minutos)<br>
    **Consulta de bloco: ** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  Defina as propriedades da **lista** :<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  Definir **títulos de coluna**:<br>
    **Nome:** Nome do computador<br>
    **Valor:** Última pulsação
6.  Definir **consulta de navegação**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Selecione **aplicar**e **fechar**.

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>Criar um bloco que exiba dispositivos com um erro de hardware

1.  Selecione **número & lista** da galeria e, em seguida, adicione um novo bloco.
2.  Defina as propriedades **gerais** :<br>
    **Título do Grupo:** Status do hardware<br>
    **Novo grupo:** Selecionado
3.  Defina as propriedades do **bloco** :<br>
    **Legenda:** Dispositivos que tiveram um erro de hardware na última hora<br>
    **Consulta de bloco: ** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Defina as propriedades da **lista** :<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Definir **títulos de coluna**:<br>
    **Nome:** Nome do computador<br>
    **Valor:** Último erro
6.  Definir **consulta de navegação**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Selecione **aplicar**e **fechar**.

### <a name="create-a-tile-that-displays-microsoft-teams-rooms-operating-system-versions"></a>Criar um bloco que exiba as versões do sistema operacional das salas do Microsoft Teams

1.  Selecione **rosca & lista** da galeria e, em seguida, adicione um novo bloco.
2.  Defina as propriedades **gerais** :<br>
    **Título do Grupo:** Detalhes do sistema operacional<br>
    **Novo grupo:** Selecionado
3.  Defina as propriedades do **cabeçalho** :<br>
    **Título:** Versões do sistema operacional<br>
    **Subtítulo:** Dispositivos executando versões específicas do sistema operacional
4.  Defina as propriedades da **rosca** :<br>
    **Consulta:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **Centralizar texto:** Vice<br>
    **Operação:** Soma
5.  Defina as propriedades da **lista** .<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **Ocultar gráfico:** Selecionado<br>
    **Habilitar minigráficos:** Não selecionada
6.  Definir **títulos de coluna**.<br>
    **Nome:** Nome do computador<br>
    **Valor:** Deixar vazio
7.  Definir uma **consulta de navegação**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Selecione **aplicar** e **fechar**.

### <a name="create-a-tile-that-displays-microsoft-teams-rooms-application-versions"></a>Criar um bloco que exibe as versões do aplicativo de salas do Microsoft Teams

1.  Selecione **rosca & lista** da galeria e, em seguida, adicione um novo bloco.
2.  Defina as propriedades **gerais** :<br>
    **Título do Grupo:** Detalhes do aplicativo salas do Microsoft Teams<br>
    **Novo grupo:** Selecionado
3.  Defina as propriedades do **cabeçalho** :<br>
    **Título:** Versões do aplicativo<br>
    **Subtítulo:** Dispositivos executando versões específicas do aplicativo
4.  Defina as propriedades da **rosca** :<br>
    **Consulta:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **Centralizar texto:** Vice<br>
    **Operação:** Soma
5.  Defina as propriedades da **lista** .<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **Ocultar gráfico:** Selecionado<br>
    **Habilitar minigráficos:** Não selecionada
6.  Definir **títulos de coluna**.<br>
    **Nome:** Nome do computador<br>
    **Valor:** Deixar vazio
7.  Definir uma **consulta de navegação**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Selecione **aplicar** e **fechar**.

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>Criar um bloco que exiba dispositivos com um erro de aplicativo

1.  Selecione **número & lista** da galeria e, em seguida, adicione um novo bloco.
2.  Defina as propriedades **gerais** .<br>
    **Título do Grupo:** Deixar vazio<br>
    **Novo grupo:** Não selecionada
3.  Defina as propriedades do **bloco** .<br>
    **Legenda:** Dispositivos que tiveram um erro de aplicativo na última hora<br>
    **Consulta de bloco: ** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Defina as propriedades da **lista** .<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Definir **títulos de coluna**.<br>
    **Nome:** Nome do computador<br>
    **Valor:** Último erro
6.  Definir uma **consulta de navegação**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Selecione **aplicar** e **fechar**.

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>Criar um bloco que exiba os dispositivos que foram reiniciados

1.  Selecione **número & lista** da galeria e, em seguida, adicione um novo bloco.
2.  Defina as propriedades **gerais** .<br>
    **Título do Grupo:** Deixar vazio<br>
    **Novo grupo:** Não selecionada
3.  Defina as propriedades do **bloco** .<br>
    **Legenda:** Dispositivos em que o aplicativo foi reiniciado nas últimas 24 horas e número de reinicializações<br>
    **Consulta de bloco: ** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  Defina as propriedades da **lista** .<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  Definir **títulos de coluna**.<br>
    **Nome:** Nome do computador<br>
    **Valor:** Número de reinicializações
6.  Definir uma **consulta de navegação**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Selecione **aplicar** e **fechar**.
8.  Selecione **salvar** para salvar seu painel.

Agora que você concluiu a criação de suas exibições.

## <a name="configure-alerts-in-azure-monitor"></a>Configurar alertas no Azure monitor
<a name="Alerts"> </a>

O Azure monitor pode disparar alertas para notificar os administradores quando um console de salas do Microsoft Teams encontra um problema.

O Azure monitor inclui um mecanismo de alerta interno que é executado por meio de pesquisas de log agendadas em intervalos regulares. Se os resultados da pesquisa de log corresponderem a alguns critérios específicos, um registro de alerta será criado.

A regra pode executar automaticamente uma ou mais ações para notificá-lo proativamente sobre o alerta ou invocar outro processo. As opções possíveis com alertas são:
-   Enviar um email
-   Invocar um processo externo por meio de uma solicitação HTTP POST
-   Iniciando um runbook no serviço de automação do Azure

Consulte [registrar alertas no Azure monitor](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log) para saber mais sobre os alertas no Azure monitor.

> [!NOTE]
> Os exemplos a seguir enviam alertas por email quando um dispositivo de salas do Microsoft Teams gera um erro de hardware ou de aplicativo.

### <a name="configure-an-email-alert-for-microsoft-teams-rooms-hardware-issues"></a>Configurar um alerta de email para as salas do Microsoft Teams problemas de hardware

Configure uma regra de alerta que verifique os dispositivos de salas do Microsoft Teams que encontraram problemas de hardware na última hora.
1.  Entre no portal do [Microsoft Azure](https://portal.azure.com) e vá para análise de logs e selecione seu espaço de trabalho.

2. Navegue até o espaço de trabalho da análise de logs e selecione **alertas** e selecione **nova regra de alerta**

3. Selecione **Adicionar condição** e **Pesquisar log personalizado**

4.  Digite a seguinte consulta à caixa de texto consulta de pesquisa.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  Defina as configurações de lógica de alerta:<br>
    **Com base em:** Número de resultados<br>
    **Condição:** Maior em seguida<br>
    **Treshold:** 0<br>

6. Defina as configurações de avaliação e selecione **concluído**: <br>
    **Período (em minutos):** 60<br>
    **Frequência (em minutos):** 60<br>

7. Configurar grupos de ações:
    1.  Selecione **criar novo**
    2.  Forneça nomes adequados para os campos *nome do grupo de ação* e *nome curto* .
    3.  Especifique um *nome de ação* exclusivo e selecione **email/SMS/Push/voz**e, em seguida, selecione **Editar detalhes**.
    4.  Marque a caixa de seleção email e forneça o endereço de email da pessoa ou do grupo que receberá os alertas.
    5.  Você também pode fornecer seu número de telefone para ser notificado com SMS, uma chamada de voz ou ambos.
    6. Selecione **OK**.

8. **Personalize ações** se desejar substituir a linha de assunto dos emails de alerta.

9. Especifique o nome e a descrição de uma regra.<br>
    **Nome da regra:** Microsoft Teams Alert falha de hardware de salas<br>
    **Descrição:** Lista de dispositivos que encontraram um problema de hardware na última hora<br>

10. Selecione a gravidade pretendida e verifique se a regra está habilitada.

11. Selecione **criar regra de alerta**.

### <a name="configure-an-email-alert-for-microsoft-teams-rooms-application-issues"></a>Configurar um alerta de email para os problemas do aplicativo salas do Microsoft Teams

Repita o mesmo procedimento, mas use a consulta a seguir para listar os dispositivos que encontraram problemas de aplicativo na última hora.

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

Agora, você concluiu a definição de alertas. Você pode definir alertas adicionais usando os exemplos acima.

Quando um alerta é gerado, você receberá um email que lista os dispositivos que encontraram um problema na última hora.

![Exemplo de email de alerta do Azure monitor] (../media/Deploy-Azure-Monitor-6.png "Exemplo de email de alerta do Azure monitor")

## <a name="configure-all-devices-for-azure-monitoring"></a>Configurar todos os dispositivos do Azure Monitoring
<a name="configure_all_devices"></a> Depois que os painéis e alertas estiverem configurados, você poderá configurar e configurar o Microsoft Monitoring Agent em todos os dispositivos de salas do Microsoft Teams para concluir a implantação do monitoramento.

Embora você possa instalar e configurar o Microsoft Monitoring Agent manualmente em cada dispositivo, é altamente recomendável aproveitar ferramentas e métodos de implantação de software existentes.

Se você estiver criando seus dispositivos de salas do Microsoft Teams pela primeira vez, talvez queira incluir as etapas de configuração e configuração do Microsoft Monitoring Agent como parte do processo de compilação. Para obter mais informações, consulte [instalar o agente usando a linha de comando](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).

### <a name="deploying-microsoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>Implantando o Microsoft Monitoring Agent usando um objeto de política de grupo (GPO)

Se você já implantou seus dispositivos de salas do Microsoft Teams antes de implementar o Azure Monitoring, você pode usar o script fornecido para configurar e configurar os agentes usando objetos de política de grupo do Active Directory.

1.  Crie um caminho de rede compartilhado e conceda acesso de leitura ao grupo **computadores do domínio** .

2.  Baixe a versão de 64 bits do Microsoft Monitoring Agent para Windows de<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  Extraia o conteúdo do pacote de instalação para o compartilhamento de rede.
    1.  Abra uma janela do prompt de comando e execute **MMASetup-AMD64. exe/c**
    2.  Especifique o compartilhamento que você acabou de criar e extraia o conteúdo.

4.  Crie um novo objeto de política de grupo e atribua-o à unidade organizacional onde as contas do Microsoft Teams salas do computador estão localizadas.

5.  Configurar a política de execução do PowerShell:
    1.  Editar o objeto de política de grupo recém criado e navegar para \\ políticas \\ de configuração \\ do computador \\ modelos administrativos do Windows PowerShell
    2.  Habilite a política **ativar a execução de scripts** e definir a **execução** para **Permitir scripts locais**.

6.  Configurar o script de inicialização:
    1.  Copie o script a seguir e salve-o como Install-MMAgent. ps1.
    2.  Modifique os parâmetros Workspaceid, WorkspaceKey e SetupPath para corresponderem à sua configuração.
    3.  Editar o mesmo objeto de política de grupo e navegar para \\ políticas \\ de configuração \\ do computador scripts de configurações do Windows (inicialização/desligamento)
    4.  Clique duas vezes para selecionar **inicialização**e, em seguida, selecione **scripts do PowerShell**.
    5.  Selecione **Mostrar arquivos**e copie o arquivo **install-MMAgent. ps1** para essa pasta.
    6.  Selecione **Adicionar**e, em seguida, **procurar**.
    7.  Selecione o script ps1 que você acabou de copiar.

7.  Os dispositivos de salas do Microsoft Teams devem instalar e configurar o Microsoft Monitoring Agent com a segunda reinicialização.

```
# Install-MMAgent.ps1
<#
Date:        04/20/2018
Script:      Install-MMAgent.ps1
Version:     1.0
#>

# Set the parameters
$WorkspaceId = "<your workspace id>"
$WorkspaceKey = "<your workspace key>"
$SetupPath = "\\Server\Share"

$SetupParameters = "/qn NOAPM=1 ADD_OPINSIGHTS_WORKSPACE=1 OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE=0 OPINSIGHTS_WORKSPACE_ID=$WorkspaceId OPINSIGHTS_WORKSPACE_KEY=$WorkspaceKey AcceptEndUserLicenseAgreement=1"

# $SetupParameters = $SetupParameters + " OPINSIGHTS_PROXY_URL=<Proxy server URL> OPINSIGHTS_PROXY_USERNAME=<Proxy server username> OPINSIGHTS_PROXY_PASSWORD=<Proxy server password>"

# Start PowerShell logging
Start-Transcript -Path C:\Temp\MMA-Install.Log

# Check if the Microsoft Monitoring Agent is installed
$mma = New-Object -ComObject 'AgentConfigManager.MgmtSvcCfg'

# Check if the Microsoft Monitoring agent is installed
if (!$mma)
{
    #Install agent
    Start-Process -FilePath "$SetupPath\Setup.exe" -ArgumentList $SetupParameters -ErrorAction Stop -Wait
}

# Check if the agent has a valid configuration
$CheckMMA = $mma.GetCloudWorkspace($WorkspaceId).AgentId
if (!$CheckMMA)
{
    # Apply new configuration
    $mma.AddCloudWorkspace($WorkspaceId, $WorkspaceKey)
    $mma.ReloadConfiguration()
}

Stop-Transcript
```

> [!NOTE]
> Você pode consultar o artigo sobre como [gerenciar e manter o agente analítico de logs](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage) quando precisa reconfigurar um agente, movê-lo para um espaço de trabalho diferente ou modificar as configurações de proxy após a instalação inicial.

## <a name="additional-solutions"></a>Soluções adicionais
<a name="Solutions"> </a>

O Azure monitor fornece soluções de gerenciamento internas por meio da [Galeria de soluções](https://docs.microsoft.com/azure/azure-monitor/insights/solutions) para ajudar você a monitorar seu ambiente. É altamente recomendável que você também adicione soluções de [Gerenciamento de alertas](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution) e de [integridade do agente do Azure log Analytics](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth) ao seu espaço de trabalho.

> [!NOTE]
> A solução de integridade do agente pode ajudá-lo a identificar agentes de monitoramento da Microsoft desatualizados ou desfeitos em seu ambiente, e a solução de gerenciamento de alertas fornece detalhes sobre os alertas que foram lançados dentro de um determinado período.

## <a name="see-also"></a>Confira também

[Planejar o gerenciamento de salas do Microsoft Teams com o Azure monitor](azure-monitor-plan.md)

[Gerenciar dispositivos de salas do Microsoft Teams com o Azure monitor](azure-monitor-manage.md)
