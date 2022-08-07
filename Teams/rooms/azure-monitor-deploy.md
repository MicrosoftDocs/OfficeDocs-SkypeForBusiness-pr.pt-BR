---
title: Implantar Salas do Microsoft Teams monitoramento com o Azure Monitor
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: Este artigo discute como implantar o monitoramento de Salas do Microsoft Teams de maneira integrada e de ponta a ponta usando o Azure Monitor.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2b6d1931b0a1818b5146f6ac0e02c225fea3af52
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267446"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-monitoring-with-no-loc-textazure-monitor"></a>Implantar :::no-loc text="Microsoft Teams Rooms"::: o monitoramento com :::no-loc text="Azure Monitor":::

Este artigo discute como configurar e implantar o monitoramento integrado de ponta a ponta de :::no-loc text="Microsoft Teams Rooms"::: dispositivos usando .:::no-loc text="Azure Monitor":::

Você pode configurar para :::no-loc text="Log Analytics"::: :::no-loc text="Azure Monitor"::: fornecer telemetria básica e alertas que ajudarão você a gerenciar :::no-loc text="Microsoft Teams Rooms":::. À medida que sua solução de gerenciamento amadurece, você pode decidir implantar recursos adicionais de gerenciamento e dados para criar uma exibição mais detalhada da disponibilidade e do desempenho do dispositivo.

Seguindo este guia, você pode usar um painel como o exemplo a seguir para obter relatórios de status detalhados sobre disponibilidade do dispositivo, integridade do aplicativo e hardware :::no-loc text="Microsoft Teams Rooms"::: e distribuição de versão do aplicativo e do sistema operacional.

![Captura de tela da exibição de exemplo do Log Analytics para Salas do Microsoft Teams.](../media/Deploy-Azure-Monitor-1.png "Exibição do Log Analytics de exemplo para Salas do Microsoft Teams")

Em um nível superior, é necessário executar as seguintes tarefas:


1. [Validar configuração :::no-loc text="Log Analytics":::](azure-monitor-deploy.md#validate_LogAnalytics)
2. [Configurar dispositivos de teste para a configuração :::no-loc text="Log Analytics"::: de gerenciamento](azure-monitor-deploy.md#configure_test_devices)
3. [Mapear os campos personalizados](azure-monitor-deploy.md#Custom_fields)
4. [Definir os modos :::no-loc text="Microsoft Teams Rooms"::: de exibição em :::no-loc text="Log Analytics":::](azure-monitor-deploy.md#Define_Views)
5. [Definir alertas](azure-monitor-deploy.md#Alerts)
6. [Configurar todos os dispositivos para monitoramento](azure-monitor-deploy.md#configure_all_devices)
7. [Configurar soluções adicionais :::no-loc text="Azure Monitor":::](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> Embora com configuração mínima, :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: possa monitorar um computador que executa um sistema operacional, :::no-loc text="Microsoft Teams Rooms":::ainda há algumas etapas específicas :::no-loc text="Microsoft Teams Rooms"::: que você precisa executar antes de começar a :::no-loc text="Windows"::: implantar agentes em todos os dispositivos.
> Portanto, é altamente recomendável que você execute todas as etapas de configuração na ordem certa para uma configuração e configuração controladas. A qualidade do resultado final depende muito da qualidade da configuração inicial.

## <a name="validate-no-loc-textlog-analytics-configuration"></a>Validar configuração :::no-loc text="Log Analytics":::
<a name="validate_LogAnalytics"> </a>

Você precisa ter um :::no-loc text="Log Analytics"::: workspace do qual começar a coletar logs :::no-loc text="Microsoft Teams Rooms":::. Um workspace é um ambiente exclusivo :::no-loc text="Log Analytics"::: com seu próprio repositório de dados, fontes de dados e soluções. Se você já tiver :::no-loc text="Log Analytics"::: um workspace existente, :::no-loc text="Microsoft Teams Rooms"::: poderá usá-lo para monitorar sua :::no-loc text="Log Analytics"::: implantação ou, como alternativa, criar um workspace :::no-loc text="Microsoft Teams Rooms"::: dedicado específico às suas necessidades de monitoramento.

Se você precisar criar um novo :::no-loc text="Log Analytics"::: workspace, siga as instruções no artigo [:::no-loc text="Log Analytics"::: Criar um workspace no :::no-loc text="Azure"::: portal](/azure/azure-monitor/learn/quick-create-workspace)

> [!NOTE]
> Para usar :::no-loc text="Log Analytics"::: com :::no-loc text="Azure Monitor":::, você precisa ter uma assinatura :::no-loc text="Azure"::: ativa. Se você não tiver uma assinatura :::no-loc text="Azure"::: , poderá criar uma assinatura de avaliação [gratuita](https://azure.microsoft.com/free) como ponto de partida.

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a>Configurar para :::no-loc text="Log Analytics"::: coletar logs :::no-loc text="Microsoft Teams Rooms"::: de eventos

:::no-loc text="Log Analytics"::: coleta apenas eventos dos :::no-loc text="Windows"::: logs de eventos especificados nas configurações. Para cada log, somente os eventos com as severidades selecionadas são coletados.

Você precisa configurar para :::no-loc text="Log Analytics"::: coletar os logs necessários para monitorar o status :::no-loc text="Microsoft Teams Rooms"::: do dispositivo e do aplicativo. :::no-loc text="Microsoft Teams Rooms"::: use o **:::no-loc text="Skype Room System":::** log de eventos.

Para configurar para :::no-loc text="Log Analytics"::: coletar os eventos :::no-loc text="Microsoft Teams Rooms"::: , consulte as fontes [:::no-loc text="Windows"::: de dados do log de eventos em :::no-loc text="Azure Monitor":::](/azure/azure-monitor/platform/data-sources-windows-events)

![Captura de tela das configurações do log de eventos.](../media/Deploy-Azure-Monitor-2.png "Configurações do log de eventos")

> [!IMPORTANT]
> Defina :::no-loc text="Windows"::: as configurações do Log de Eventos **:::no-loc text="Skype Room System":::** e insira como nome do log de eventos e marque as caixas de seleção **Erro, Aviso** **e Informações**.

## <a name="configure-test-devices-for-azure-monitoring"></a>Configurar dispositivos de teste para o Monitoramento do Azure
<a name="configure_test_devices"> </a>

Você precisa se preparar :::no-loc text="Log Analytics"::: para poder monitorar eventos :::no-loc text="Microsoft Teams Rooms":::relacionados. Para começar, você :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: precisa implantar agentes em um ou dois dispositivos aos qual você tem acesso físico e fazer com que esses dispositivos de teste gerem alguns dados e os enviem por push :::no-loc text="Log Analytics"::: para o workspace.

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a>Instalar agentes :::no-loc text="Microsoft Monitoring"::: para testar dispositivos

Implante o :::no-loc text="Microsoft Monitoring"::: agente nos dispositivos de teste usando as instruções fornecidas em [Conectar :::no-loc text="Windows"::: computadores ao :::no-loc text="Log Analytics"::: serviço em :::no-loc text="Azure":::](/azure/azure-monitor/platform/agent-windows). :::no-loc text="Microsoft Monitoring"::: Este artigo fornece informações detalhadas sobre as etapas de implantação do Agent :::no-loc text="Windows":::para , *:::no-loc text="Log Analytics"::: instruções para obter a **ID do Workspace** _ e a _ *_chave_* primária* :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: para conectar dispositivos à sua implantação e etapas para verificar a conectividade do agente com a instância.

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a>Gerar eventos de :::no-loc text="Microsoft Teams Rooms"::: exemplo

Depois que :::no-loc text="Microsoft Monitoring"::: o agente for implantado nos dispositivos de teste, verifique se os dados de log de eventos necessários são coletados por :::no-loc text="Azure Monitor":::.

> [!NOTE]
> Reinicialize o dispositivo após a :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: instalação do agente e verifique se o aplicativo de reunião foi iniciado, para que ele possa gerar novos eventos no Log de Eventos.

1.  Entre no [portal e:::no-loc text="Microsoft Azure":::](https://portal.azure.com) acesse e :::no-loc text="Log Analytics"::: selecione seu workspace.

2.  Liste os eventos de pulsação gerados por um :::no-loc text="Microsoft Teams Rooms"::: dispositivo:
    1.  Selecione seu workspace e vá para **Logs** e use uma consulta para recuperar os registros de pulsação que terão os campos personalizados para :::no-loc text="Microsoft Teams Rooms":::.
    2.  Consulta de exemplo: `Event | where Source == "SRS-App" and EventID == 2000`

3.  Verifique se a consulta retorna registros de log que incluem eventos gerados pelo aplicativo :::no-loc text="Microsoft Teams Rooms"::: de reuniões.

4.  Gere um problema de hardware e valide se os eventos necessários estão conectados :::no-loc text="Azure Log Analytics":::.
    1.  Desconecte um dos dispositivos periféricos no sistema de :::no-loc text="Microsoft Teams Rooms"::: teste. Pode ser a câmera, o alto-falante, o microfone ou a tela frontal da sala
    2.  Aguarde 10 minutos para que o log de eventos seja preenchido em :::no-loc text="Azure Log Analytics":::.
    3.  Use uma consulta para listar eventos de erro de hardware: `Event | where Source == "SRS-App" and EventID == 3001`

5.  Gere um problema de aplicativo e valide se os eventos necessários estão registrados.
    1.  Modifique :::no-loc text="Microsoft Teams Rooms"::: a configuração da conta e digite um par de Email/senha incorreto.
    2.  Aguarde 10 minutos para que o log de eventos seja preenchido em :::no-loc text="Azure Log Analytics":::.
    3.  Use uma consulta para listar eventos de erro do aplicativo: `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> Esses logs de eventos de exemplo são necessários antes que os campos personalizados possam ser configurados. Não prossiga para a próxima etapa até ter coletado os logs de eventos necessários.

## <a name="map-custom-fields"></a>Mapear os campos personalizados
<a name="Custom_fields"> </a>

Você usa campos personalizados para extrair dados específicos dos logs de eventos. Você precisa definir campos personalizados que serão usados posteriormente com seus blocos, exibições de painel e alertas. Veja [os campos Personalizados e :::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/custom-fields) familiarize-se com os conceitos antes de começar a criar seus campos personalizados.

Para extrair seus campos personalizados dos logs de eventos capturados, siga estas etapas:

1.  Entre no [portal e:::no-loc text="Microsoft Azure":::](https://portal.azure.com) acesse e :::no-loc text="Log Analytics"::: selecione seu workspace.

2. Liste os eventos gerados por um :::no-loc text="Microsoft Teams Rooms"::: dispositivo:
   1.  Vá para **Logs** e use uma consulta para recuperar os registros que terão o campo personalizado.
   2.  Consulta de exemplo: `Event | where Source == "SRS-App" and EventID == 2000`

3. Selecione um dos registros, selecione o botão à esquerda e inicie o assistente de extração de campo.
4. Realce os dados que você deseja extrair do RenderedDescription e forneça um Título de Campo. Os nomes de campo que você deve usar são fornecidos na Tabela 1.
5. Use os mapeamentos mostrados *na Tabela 1*. :::no-loc text="Log Analytics":::acrescentará automaticamente a cadeia **de\_ caracteres CF** quando você definir o novo campo.

> [!IMPORTANT]
> Lembre-se de que todos os JSON e :::no-loc text="Log Analytics"::: campos diferenciam maiúsculas de minúsculas.
> 
> Preste atenção às consultas necessárias para cada campo personalizado na tabela abaixo. Você precisa usar as consultas corretas para :::no-loc text="Log Analytics"::: extrair com êxito valores de campo personalizados.
> 
**Tabela 1**

| **Campo JSON**                   | **:::no-loc text="Log Analytics"::: campo personalizado** | **ID do evento** | **Consulta a ser usada com a extração**                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| Descrição                      | SRSEventDescription         | **2000**     | Evento \| em que Source == "SRS-App" e EventID == 2000 |
| ResourceState                    | SRSResourceState            | **2000**     | Evento \| em que Source == "SRS-App" e EventID == 2000 |
| OperationName                    | SRSOperationName            | **2000**     | Evento \| em que Source == "SRS-App" e EventID == 2000 |
| OperationResult                  | SRSOperationResult          | **2000**     | Evento \| em que Source == "SRS-App" e EventID == 2000 |
| Sistema operacional                               | SRSOSVersion                | **2000**     | Evento \| em que Source == "SRS-App" e EventID == 2000 |
| OSVersion                        | SRSOSLongVersion            | **2000**     | Evento \| em que Source == "SRS-App" e EventID == 2000 |
| Alias                            | SRSAlias                    | **2000**     | Evento \| em que Source == "SRS-App" e EventID == 2000 |
| DisplayName                      | SRSDisplayName              | **2000**     | Evento \| em que Source == "SRS-App" e EventID == 2000 |
| AppVersion                       | SRSAppVersion               | **2000**     | Evento \| em que Source == "SRS-App" e EventID == 2000 |
| IPv4Address                      | SRSIPv4Address              | **2000**     | Evento \| em que Source == "SRS-App" e EventID == 2000 |
| IPv6Address                      | SRSIPv6Address              | **2000**     | Evento \| em que Source == "SRS-App" e EventID == 2000 |
| Status do microfone de conferência     | SRSConfMicrophoneStatus     | **3001**     | Evento \| em que Source == "SRS-App" e EventID == 3001 |
| Status do Locutor de Conferência        | SRSConfSpeakerStatus        | **3001**     | Evento \| em que Source == "SRS-App" e EventID == 3001 |
| Status padrão do Locutor           | SRSDefaultSpeakerStatus     | **3001**     | Evento \| em que Source == "SRS-App" e EventID == 3001 |
| Status da câmera                    | SRSCameraStatus             | **3001**     | Evento \| em que Source == "SRS-App" e EventID == 3001 |
| Status de exibição frontal da sala     | SRSFORDStatus               | **3001**     | Evento \| em que Source == "SRS-App" e EventID == 3001 |
| Status do Sensor de Movimento             | SRSMotionSensorStatus       | **3001**     | Evento \| em que Source == "SRS-App" e EventID == 3001 |
| Status de ingestão do HDMI               | SRSHDMIIngestStatus         | **3001**     | Evento \| em que Source == "SRS-App" e EventID == 3001 |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a>Definir os modos :::no-loc text="Microsoft Teams Rooms"::: de exibição em :::no-loc text="Log Analytics":::
<a name="Define_Views"> </a>

Depois que os dados são coletados e os campos personalizados são mapeados, você pode usar o Designer de Exibição para desenvolver um painel contendo vários blocos para monitorar eventos :::no-loc text="Microsoft Teams Rooms"::: . Use o Designer de Exibição para criar os blocos a seguir. Para obter mais informações, consulte [Criar exibições personalizadas usando o Designer de Exibição no :::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> As etapas anteriores neste guia devem ter sido concluídas para que os blocos do painel funcionem corretamente.
>
> [!IMPORTANT]
> [O Designer de Exibição no Azure Monitor](https://azure.microsoft.com/updates/view-designer-in-azure-monitor-is-retiring-on-31-august-2023/) será desativado em 31 de agosto de 2023 e as funcionalidades de criação e clonagem foram desabilitadas em 30 de novembro de 2020. Em vez disso, as pastas de trabalho podem ser usadas. Para obter mais informações sobre o guia de transição do designer de exibição para pastas de trabalho, consulte [Início Rápido com modelos de designer de exibição predefinidos](/azure/azure-monitor/visualize/view-designer-conversion-tasks#quickstart-with-preset-view-designer-templates).

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>Criar um Salas do Microsoft Teams manualmente

Como alternativa, você pode criar seu próprio painel e adicionar apenas os blocos que deseja monitorar.

#### <a name="configure-the-overview-tile"></a>Configurar o bloco visão geral

1.  Abra **o Designer de Exibição**.
2.  Selecione **Bloco de Visão Geral** e, em seguida, **selecione Dois números** na galeria.
3.  Nomeie o bloco **:::no-loc text="Microsoft Teams Rooms":::**.
4.  Defina **o primeiro bloco**:<br>
    **Lenda:** Dispositivos que enviaram uma pulsação pelo menos uma vez no último mês<br>
    **Consulta:** ```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  Defina **o segundo bloco**:<br>
    **Lenda:** Dispositivos ativos que enviaram uma pulsação na última hora<br>
    **Consulta:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  Selecione **Aplicar**.

### <a name="create-a-tile-that-displays-active-devices"></a>Criar um bloco que exibe dispositivos ativos

1.  Selecione **Exibir Painel** para começar a adicionar seus blocos.
2.  Selecione **a lista & número** na galeria
3.  Defina **as propriedades** Gerais:<br>
    **Título do Grupo:** Status da Pulsação<br>
    **Novo Grupo:** Selecionado
4.  Defina **as propriedades do** bloco:<br>
    **Lenda:** Dispositivos ativos (pulsação enviada nos últimos 20 minutos)<br>
    **Consulta de bloco:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  Defina as **propriedades da** lista:<br>
    **Consulta de lista:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  Definir **títulos de coluna**:<br>
    **Nome:** Nome do Computador<br>
    **Valor:** Última Pulsação
7.  **Defina a consulta de navegação**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Selecione **Aplicar** e, em **seguida, Fechar**.

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>Criar um bloco que exibe dispositivos que têm problemas de conectividade

1.  Selecione **Número & lista** da galeria e, em seguida, adicione um novo bloco.
2.  Defina **as propriedades** Gerais:<br>
    **Título do Grupo:** Deixar vazio<br>
    **Novo Grupo:** Não Selecionado
3.  Defina **as propriedades do** bloco:<br>
    **Lenda:** Dispositivos inativos (nenhuma mensagem de pulsação enviada nos últimos 20 minutos)<br>
    **Consulta de bloco:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  Defina as **propriedades da** lista:<br>
    **Consulta de lista:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  Definir **títulos de coluna**:<br>
    **Nome:** Nome do Computador<br>
    **Valor:** Última Pulsação
6.  Definir **consulta de navegação**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Selecione **Aplicar** e, em **seguida, Fechar**.

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>Criar um bloco que exibe dispositivos que têm um erro de hardware

1.  Selecione **Número & lista** da galeria e, em seguida, adicione um novo bloco.
2.  Defina **as propriedades** Gerais:<br>
    **Título do Grupo:** Hardware Status<br>
    **Novo Grupo:** Selecionado
3.  Defina **as propriedades do** bloco:<br>
    **Lenda:** Dispositivos que tiveram um erro de hardware na última hora<br>
    **Consulta de bloco:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Defina as **propriedades da** lista:<br>
    **Consulta de lista:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Definir **títulos de coluna**:<br>
    **Nome:** Nome do Computador<br>
    **Valor:** Último Erro
6.  Definir **consulta de navegação**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Selecione **Aplicar** e, em **seguida, Fechar**.

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a>Criar um bloco que exibe versões do :::no-loc text="Microsoft Teams Rooms"::: sistema operacional

1.  Selecione **& de rosca** na galeria e, em seguida, adicione um novo bloco.
2.  Defina **as propriedades** Gerais:<br>
    **Título do Grupo:** Detalhes do sistema operacional<br>
    **Novo Grupo:** Selecionado
3.  Defina as **propriedades de** cabeçalho:<br>
    **Título:** Versões do sistema operacional<br>
    **Legendas:** Dispositivos que executam versões específicas do sistema operacional
4.  Defina as **propriedades de rosca** :<br>
    **Consulta:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **Texto central:** Dispositivos<br>
    **Operação:** Soma
5.  Defina as **propriedades da** lista.<br>
    **Consulta de lista:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **Ocultar Grafo:** Selecionado<br>
    **Habilitar Minigráficos:** Não selecionado
6.  Definir **títulos de coluna**.<br>
    **Nome:** Nome do Computador<br>
    **Valor:** Deixar Vazio
7.  **Defina a consulta de navegação**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Selecione **Aplicar** e **, em seguida, Fechar**.

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a>Criar um bloco que exibe as versões :::no-loc text="Microsoft Teams Rooms"::: do aplicativo

1.  Selecione **& de rosca** na galeria e, em seguida, adicione um novo bloco.
2.  Defina **as propriedades** Gerais:<br>
    **Título do Grupo:** :::no-loc text="Microsoft Teams Rooms"::: detalhes do aplicativo<br>
    **Novo Grupo:** Selecionado
3.  Defina as **propriedades de** cabeçalho:<br>
    **Título:** Versões do aplicativo<br>
    **Legendas:** Dispositivos que executam versões específicas do aplicativo
4.  Defina as **propriedades de rosca** :<br>
    **Consulta:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **Texto central:** Dispositivos<br>
    **Operação:** Soma
5.  Defina as **propriedades da** lista.<br>
    **Consulta de lista:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **Ocultar Grafo:** Selecionado<br>
    **Habilitar Minigráficos:** Não selecionado
6.  Definir **títulos de coluna**.<br>
    **Nome:** Nome do Computador<br>
    **Valor:** Deixar Vazio
7.  **Defina a consulta de navegação**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Selecione **Aplicar** e **, em seguida, Fechar**.

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>Criar um bloco que exibe dispositivos que têm um erro de aplicativo

1.  Selecione **Número & lista** da galeria e, em seguida, adicione um novo bloco.
2.  Defina as **propriedades** Gerais.<br>
    **Título do Grupo:** Deixar vazio<br>
    **Novo Grupo:** Não Selecionado
3.  Defina **as propriedades do** bloco.<br>
    **Lenda:** Dispositivos que tiveram um erro de aplicativo na última hora<br>
    **Consulta de bloco:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Defina as **propriedades da** lista.<br>
    **Consulta de lista:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Definir **títulos de coluna**.<br>
    **Nome:** Nome do Computador<br>
    **Valor:** Último Erro
6.  **Defina a consulta de navegação**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Selecione **Aplicar** e **, em seguida, Fechar**.

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>Criar um bloco que exibe os dispositivos que foram reiniciados

1.  Selecione **Número & lista** da galeria e, em seguida, adicione um novo bloco.
2.  Defina as **propriedades** Gerais.<br>
    **Título do Grupo:** Deixar vazio<br>
    **Novo Grupo:** Não Selecionado
3.  Defina **as propriedades do** bloco.<br>
    **Lenda:** Dispositivos em que o aplicativo foi reiniciado nas últimas 24 horas e o número de reinicializações<br>
    **Consulta de bloco:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  Defina as **propriedades da** lista.<br>
    **Consulta de lista:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  Definir **títulos de coluna**.<br>
    **Nome:** Nome do Computador<br>
    **Valor:** Número de reinicializações
6.  **Defina a consulta de navegação**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Selecione **Aplicar** e **, em seguida, Fechar**.
8.  Selecione **Salvar** para salvar seu painel.

Agora você concluiu a criação de seus modos de exibição.

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a>Configurar alertas em :::no-loc text="Azure Monitor":::
<a name="Alerts"> </a>

:::no-loc text="Azure Monitor"::: pode gerar alertas para notificar os administradores quando um :::no-loc text="Microsoft Teams Rooms"::: console encontrar um problema.

:::no-loc text="Azure Monitor"::: inclui um mecanismo de alerta interno que é executado por meio de pesquisas de log agendadas em intervalos regulares. Se os resultados da pesquisa de log corresponderem a alguns critérios específicos, um registro de alerta será criado.

A regra pode executar automaticamente uma ou mais ações para notificá-lo proativamente sobre o alerta ou invocar outro processo. As opções possíveis com alertas são:
-   Enviar um email
-   Invocando um processo externo por meio de uma solicitação HTTP POST
-   Iniciando um runbook no :::no-loc text="Azure Automation"::: serviço

Consulte [alertas de log para :::no-loc text="Azure Monitor":::](/azure/azure-monitor/platform/alerts-unified-log) saber mais sobre os alertas em :::no-loc text="Azure Monitor":::.

> [!NOTE]
> Os exemplos a seguir enviam alertas por email quando um :::no-loc text="Microsoft Teams Rooms"::: dispositivo gera um hardware ou um erro de aplicativo.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a>Configurar um alerta de email para problemas :::no-loc text="Microsoft Teams Rooms"::: de hardware

Configure uma regra de alerta que verifica dispositivos :::no-loc text="Microsoft Teams Rooms"::: que encontraram problemas de hardware na última hora.
1.  Entre no [portal e:::no-loc text="Microsoft Azure":::](https://portal.azure.com) acesse e :::no-loc text="Log Analytics"::: selecione seu workspace.

2. Navegue até o :::no-loc text="Log Analytics"::: workspace, selecione **Alertas** e, em seguida, **selecione Nova regra de alerta**

3. Selecione **Adicionar condição e** , em seguida **, Pesquisa de log personalizada**

4.  Insira a consulta a seguir na caixa de texto Pesquisar consulta.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  Defina as configurações de lógica de alerta:<br>
    **Com base em:** Número de resultados<br>
    **Condição:** Maior que<br>
    **Limite:** 0<br>

6. Defina as configurações de Avaliação e selecione **Concluído**: <br>
    **Período (em minutos):** 60<br>
    **Frequência (em minutos):** 60<br>

7. Configurar grupos de ações:
    1.  Selecione **Criar Novo**
    2.  Forneça nomes adequados para os campos *Nome do grupo de ações* e *Nome Curto* .
    3.  Especifique um *Nome de Ação* exclusivo **, selecione Email/SMS/Push/Voz** e, em seguida, selecione **Editar detalhes**.
    4.  Marque a **Email** caixa de seleção e forneça o endereço de email da pessoa ou grupo que receberá os alertas.
    5.  Você também pode fornecer seu número de telefone para ser notificado com SMS, uma chamada de voz ou ambos.
    6. Selecione **OK**.

8. **Personalize ações** se você quiser substituir a linha de assunto dos emails de alerta.

9. Especifique um nome de regra e uma descrição.<br>
    **Nome da regra:** :::no-loc text="Microsoft Teams Rooms"::: Alerta de falha de hardware<br>
    **Descrição:** Lista de dispositivos que encontraram um problema de hardware na última hora<br>

10. Selecione a severidade pretendida e verifique se a regra está habilitada.

11. Selecione **Criar regra de alerta**.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a>Configurar um alerta de email para problemas :::no-loc text="Microsoft Teams Rooms"::: de aplicativo

Repita o mesmo procedimento, mas use a consulta a seguir para listar os dispositivos que encontraram problemas de aplicativo na última hora.

 ```
 Event
 | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
 | summarize arg_max(TimeGenerated, *) by Computer
 | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
 | sort by TimeGenerated desc
 ```

Agora você concluiu a definição de alertas. Você pode definir alertas adicionais usando os exemplos acima.

Quando um alerta é gerado, você receberá um email que lista os dispositivos que encontraram um problema na última hora.

! [Exemplo de :::no-loc text="Azure Monitor"::: email de alerta](.. /media/Deploy-Azure-Monitor-6.png "Email de :::no-loc text="Azure Monitor"::: alerta de exemplo")

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a>Configurar todos os dispositivos para :::no-loc text="Azure Monitoring":::
<a name="configure_all_devices"> </a> Depois que os painéis e alertas forem configurados, :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: você poderá configurar o agente em todos os dispositivos para concluir a implantação de monitoramento.

Embora você possa instalar e configurar o :::no-loc text="Microsoft Monitoring"::: agente manualmente em cada dispositivo, é altamente recomendável aproveitar os métodos e ferramentas de implantação de software existentes.

Se você estiver criando seus dispositivos :::no-loc text="Microsoft Teams Rooms"::: pela primeira vez, :::no-loc text="Microsoft Monitoring"::: convém incluir as etapas de configuração e configuração do agente como parte do processo de build. Para obter mais informações, [consulte Instalar o agente usando a linha de comando](/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>Implantando :::no-loc text="Microsoft Monitoring"::: o agente usando um GPO (Política de Grupo)

Se você já implantou seus :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitoring":::dispositivos antes de implementar, poderá usar o script fornecido para configurar e configurar os agentes usando objetos :::no-loc text="Active Directory"::: de política de grupo.

1.  Crie um caminho de rede compartilhado e conceda acesso de leitura ao **grupo Computadores de** Domínio.

2.  Baixar a versão de 64 bits do :::no-loc text="Microsoft Monitoring"::: Agente de :::no-loc text="Windows":::<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  Extraia o conteúdo do pacote de instalação para o compartilhamento de rede.
    1.  Abra uma janela do Prompt de Comando e execute **MMASetup-AMD64.exe /c**
    2.  Especifique o compartilhamento que você acabou de criar e extraia o conteúdo.

4.  Crie um novo objeto Política de Grupo e atribua-o à unidade organizacional em que as contas :::no-loc text="Microsoft Teams Rooms"::: de computador estão localizadas.

5.  Configurar a política de execução do PowerShell:
    1.  Edite o objeto Política de Grupo recém-criado e navegue até Componentes \\ \\ de Modelos Administrativos das Políticas de Configuração do \\ :::no-loc text="Windows"::: Computador \\ :::no-loc text="Windows PowerShell":::
    2.  Habilite **a execução de script ativado e** defina **a política de execução** para **permitir scripts locais**.

6.  Configure o script de inicialização:
    1.  Copie o script a seguir e salve-o como Install-MMAgent.ps1.
    2.  Modifique os parâmetros WorkspaceId, WorkspaceKey e SetupPath para corresponder à sua configuração.
    3.  Edite o mesmo objeto Política de Grupo e navegue até Scripts \\ de \\ \\ :::no-loc text="Windows"::: Configurações de Políticas de Configuração do Computador (Inicialização/Desligamento)
    4.  Clique duas vezes para selecionar **Inicialização** e, em seguida, selecione **Scripts do PowerShell**.
    5.  Selecione **Mostrar Arquivos** e copie o arquivo **Install-MMAgent.ps1** para essa pasta.
    6.  Selecione **Adicionar** e, em **seguida, Procurar**.
    7.  Selecione o script ps1 que você acabou de copiar.

7.  :::no-loc text="Microsoft Teams Rooms"::: deve instalar e configurar o agente :::no-loc text="Microsoft Monitoring"::: com a segunda reinicialização.

```PowerShell
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
> Você pode consultar [:::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/agent-manage) o artigo Gerenciando e mantendo o agente quando precisar reconfigurar um agente, movê-lo para um workspace diferente ou modificar as configurações de proxy após a instalação inicial.

## <a name="additional-solutions"></a>Soluções adicionais
<a name="Solutions"> </a>

:::no-loc text="Azure Monitor"::: fornece soluções de gerenciamento internas por meio de [sua galeria de soluções](/azure/azure-monitor/insights/solutions) para ajudá-lo a monitorar seu ambiente. É altamente recomendável que você adicione soluções de [Gerenciamento de](/azure/azure-monitor/platform/alert-management-solution) [Alertas:::no-loc text="Azure Log Analytics":::](/azure/azure-monitor/insights/solution-agenthealth) e Integridade do Agente ao seu workspace também.

> [!NOTE]
> A solução de Integridade :::no-loc text="Microsoft Monitoring"::: do Agente pode ajudá-lo a identificar agentes desatualizados ou desfeitos em seu ambiente, e a solução de Gerenciamento de Alertas fornece detalhes sobre os alertas que foram gerados dentro de um determinado período.

## <a name="see-also"></a>Confira também

[Planejar o :::no-loc text="Microsoft Teams Rooms"::: gerenciamento com :::no-loc text="Azure Monitor":::](azure-monitor-plan.md)

[Gerenciar dispositivos :::no-loc text="Microsoft Teams Rooms"::: com :::no-loc text="Azure Monitor":::](azure-monitor-manage.md)
