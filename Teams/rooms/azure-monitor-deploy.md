---
title: Implantar o gerenciamento de salas do Microsoft Teams com o Azure monitor
ms.author: v-lanac
author: lanachin
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: Este artigo discute como implantar o gerenciamento de dispositivos de salas do Microsoft Teams de maneira integrada e de ponta a ponta usando o Azure monitor.
ms.openlocfilehash: 54268676eadab25599d4f8b6e415ff373717943f
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826259"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-management-with-no-loc-textazure-monitor"></a>Implantar :::no-loc text="Microsoft Teams Rooms"::: gerenciamento com:::no-loc text="Azure Monitor":::

Este artigo descreve como configurar e implantar o gerenciamento completo de :::no-loc text="Microsoft Teams Rooms"::: dispositivos integrados usando :::no-loc text="Azure Monitor":::o.

Você pode configurar :::no-loc text="Log Analytics"::: dentro :::no-loc text="Azure Monitor"::: para fornecer telemetria e alertas básicos que ajudarão você :::no-loc text="Microsoft Teams Rooms"::: a gerenciar os dispositivos da sala de reunião. À medida que sua solução de gerenciamento amadurece, você pode decidir implantar recursos adicionais de gerenciamento e dados para criar uma visão mais detalhada da disponibilidade e do desempenho do dispositivo.

Ao seguir este guia, você pode usar um painel como o exemplo a seguir para obter relatórios detalhados sobre o status de disponibilidade de dispositivos, integridade :::no-loc text="Microsoft Teams Rooms"::: de aplicativo e hardware e distribuição de versão do sistema operacional e do aplicativo.

! [Captura de tela do :::no-loc text="Log Analytics"::: modo de :::no-loc text="Microsoft Teams Rooms":::exibição de amostra para] (.. /media/Deploy-Azure-Monitor-1.png "exemplo :::no-loc text="Log Analytics"::: de exibição :::no-loc text="Microsoft Teams Rooms":::para")

Em um nível superior, é necessário executar as seguintes tarefas:


1. [Validar :::no-loc text="Log Analytics"::: configuração](azure-monitor-deploy.md#validate_LogAnalytics)
2. [Configurar dispositivos de teste :::no-loc text="Log Analytics"::: para a configuração de gerenciamento](azure-monitor-deploy.md#configure_test_devices)
3. [Mapear os campos personalizados](azure-monitor-deploy.md#Custom_fields)
4. [Definir os :::no-loc text="Microsoft Teams Rooms"::: modos de exibição no:::no-loc text="Log Analytics":::](azure-monitor-deploy.md#Define_Views)
5. [Definir alertas](azure-monitor-deploy.md#Alerts)
6. [Configurar todos os dispositivos para monitoramento](azure-monitor-deploy.md#configure_all_devices)
7. [Configurar soluções :::no-loc text="Azure Monitor"::: adicionais](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> Embora :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: com a configuração mínima possa monitorar um computador que esteja :::no-loc text="Windows"::: executando um sistema operacional, ainda há :::no-loc text="Microsoft Teams Rooms":::algumas etapas específicas que você precisa tomar antes de começar a implantar agentes em todos os :::no-loc text="Microsoft Teams Rooms"::: dispositivos.
> Portanto, é altamente recomendável executar todas as etapas de configuração na ordem certa para uma configuração e configuração controlada. A qualidade do resultado final depende muito da qualidade da configuração inicial.

## <a name="validate-no-loc-textlog-analytics-configuration"></a>Validar :::no-loc text="Log Analytics"::: configuração
<a name="validate_LogAnalytics"> </a>

Você precisa ter um :::no-loc text="Log Analytics"::: espaço de trabalho para começar a coletar :::no-loc text="Microsoft Teams Rooms"::: logs de dispositivos. Um espaço de trabalho é :::no-loc text="Log Analytics"::: um ambiente exclusivo com seu próprio repositório de dados, fontes de dados e soluções. Se você já tiver um espaço :::no-loc text="Log Analytics"::: de trabalho existente, pode usá-lo para :::no-loc text="Microsoft Teams Rooms"::: monitorar a implantação ou, se preferir, criar um :::no-loc text="Log Analytics"::: espaço de trabalho dedicado :::no-loc text="Microsoft Teams Rooms"::: específico às suas necessidades de monitoramento.

Se você precisar criar um novo :::no-loc text="Log Analytics"::: espaço de trabalho, siga as instruções no artigo [criar um :::no-loc text="Log Analytics"::: espaço de trabalho :::no-loc text="Azure"::: no portal](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)

> [!NOTE]
> Para usar :::no-loc text="Log Analytics"::: com :::no-loc text="Azure Monitor":::o, você precisa ter uma assinatura :::no-loc text="Azure"::: ativa. Se você não tiver uma :::no-loc text="Azure"::: assinatura, poderá criar [uma assinatura de avaliação gratuita](https://azure.microsoft.com/free) como ponto de partida.

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a>Configurar :::no-loc text="Log Analytics"::: para coletar :::no-loc text="Microsoft Teams Rooms"::: logs de eventos

:::no-loc text="Log Analytics":::coleta apenas eventos dos logs de :::no-loc text="Windows"::: eventos especificados nas configurações. Para cada log, somente os eventos com as severidades selecionadas são coletados.

Você precisa configurar :::no-loc text="Log Analytics"::: o para coletar os logs necessários para monitorar :::no-loc text="Microsoft Teams Rooms"::: o status do aplicativo e do aplicativo. :::no-loc text="Microsoft Teams Rooms":::dispositivos usam o **:::no-loc text="Skype Room System":::** log de eventos.

Para configurar :::no-loc text="Log Analytics"::: o :::no-loc text="Microsoft Teams Rooms"::: para coletar eventos, consulte [ :::no-loc text="Windows"::: fontes de dados de log :::no-loc text="Azure Monitor"::: de eventos em](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)

![Captura de tela das configurações do log de eventos](../media/Deploy-Azure-Monitor-2.png "Configurações do log de eventos")

> [!IMPORTANT]
> Defina :::no-loc text="Windows"::: as configurações do log de **:::no-loc text="Skype Room System":::** eventos e insira como nome do log de eventos e, em seguida, marque as caixas de seleção **erro**, **aviso**e **informações** .

## <a name="configure-test-devices-for-azure-monitoring"></a>Configurar dispositivos de teste para o Azure Monitoring
<a name="configure_test_devices"> </a>

Você precisa se preparar :::no-loc text="Log Analytics"::: para poder monitorar :::no-loc text="Microsoft Teams Rooms":::eventos relacionados. Para começar, você precisa implantar :::no-loc text="Microsoft Monitoring"::: agentes em apenas um ou dois :::no-loc text="Microsoft Teams Rooms"::: dispositivos com o qual você tem acesso físico e obter esses dispositivos de teste para gerar alguns dados e enviá-los para :::no-loc text="Log Analytics"::: o espaço de trabalho.

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a>Instalar :::no-loc text="Microsoft Monitoring"::: agentes para dispositivos de teste

Implante o :::no-loc text="Microsoft Monitoring"::: agente nos dispositivos de teste usando as instruções fornecidas em [conectar :::no-loc text="Windows"::: computadores ao :::no-loc text="Log Analytics"::: serviço :::no-loc text="Azure"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows). Este artigo fornece informações detalhadas sobre as etapas para implantar o :::no-loc text="Microsoft Monitoring"::: agente para :::no-loc text="Windows":::, instruções para obter a :::no-loc text="Log Analytics"::: ***ID do espaço de trabalho*** e a ***chave primária*** para obter :::no-loc text="Microsoft Teams Rooms"::: dispositivos :::no-loc text="Azure Monitor"::: conectados à sua implantação e etapas para verificar a :::no-loc text="Log Analytics"::: conectividade do agente para a instância.

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a>Gerar eventos :::no-loc text="Microsoft Teams Rooms"::: de exemplo

Depois que :::no-loc text="Microsoft Monitoring"::: o agente for implantado nos dispositivos de teste, verifique se os dados necessários do log :::no-loc text="Azure Monitor":::de eventos são coletados.

> [!NOTE]
> Reinicie o dispositivo após a instalação do :::no-loc text="Microsoft Monitoring"::: agente e certifique-se de :::no-loc text="Microsoft Teams Rooms"::: que o aplicativo de reunião seja iniciado, para que ele possa gerar novos eventos no log de eventos.

1.  Entre no [ :::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) e vá para :::no-loc text="Log Analytics"::: e selecione seu espaço de trabalho.

2.  Listar os eventos de pulsação :::no-loc text="Microsoft Teams Rooms"::: gerados por um dispositivo:
    1.  Selecione seu espaço de trabalho e vá para **logs** e use uma consulta para recuperar os registros de pulsação que terão os :::no-loc text="Microsoft Teams Rooms":::campos personalizados.
    2.  Consulta de exemplo:`Event | where Source == "SRS-App" and EventID == 2000`

3.  Certifique-se de que a consulta retorne registros de log que incluam eventos gerados pelo aplicativo :::no-loc text="Microsoft Teams Rooms"::: reuniões.

4.  Gere um problema de hardware e valide se os eventos necessários estão conectados :::no-loc text="Azure Log Analytics":::.
    1.  Desconecte um dos dispositivos periféricos do sistema de :::no-loc text="Microsoft Teams Rooms"::: teste. Pode ser a tela câmera, viva-voz, microfone ou sala frontal
    2.  Aguarde 10 minutos para que o log de eventos seja preenchido :::no-loc text="Azure Log Analytics":::.
    3.  Use uma consulta para listar eventos de erro de hardware:`Event | where Source == "SRS-App" and EventID == 3001`

5.  Gere um problema de aplicativo e valide se os eventos necessários estão registrados.
    1.  Modifique :::no-loc text="Microsoft Teams Rooms"::: a configuração do aplicativo e digite um par de endereço/senha SIP (protocolo de iniciação de sessão) incorreto.
    2.  Aguarde 10 minutos para que o log de eventos seja preenchido :::no-loc text="Azure Log Analytics":::.
    3.  Use uma consulta para listar eventos de erro do aplicativo:`Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> Estes registros de eventos de exemplo são necessários para que os campos personalizados possam ser configurados. Não vá para a próxima etapa até que você tenha coletado os logs de eventos necessários.

## <a name="map-custom-fields"></a>Mapear os campos personalizados
<a name="Custom_fields"> </a>

Use campos personalizados para extrair dados específicos dos logs de eventos. Você precisa definir campos personalizados que serão usados posteriormente com seus blocos, exibições de painel e alertas. Veja os [campos :::no-loc text="Log Analytics"::: personalizados](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields) e familiarize-se com os conceitos antes de começar a criar seus campos personalizados.

Para extrair seus campos personalizados dos logs de eventos capturados, siga estas etapas:

1.  Entre no [ :::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) e vá para :::no-loc text="Log Analytics"::: e selecione seu espaço de trabalho.

2. Listar os eventos gerados por :::no-loc text="Microsoft Teams Rooms"::: um dispositivo:
   1.  Vá para **logs** e use uma consulta para recuperar os registros que terão o campo personalizado.
   2.  Consulta de exemplo:`Event | where Source == "SRS-App" and EventID == 2000`

3. Selecione um dos registros, selecione o botão à esquerda e inicie o assistente de extração de campos.
4. Realce os dados que você deseja extrair do RenderedDescription e forneça um título de campo. Os nomes de campo que você deve usar são fornecidos na tabela 1.

   ![Definição de campo personalizado](../media/Deploy-Azure-Monitor-4.png "Definição de campo personalizado")

5. Use os mapeamentos mostrados na *tabela 1*. :::no-loc text="Log Analytics":::adicionará automaticamente a cadeia de caracteres do ** \_CF** quando você definir o novo campo.

> [!IMPORTANT]
> Lembre-se de que :::no-loc text="Log Analytics"::: todos os campos JSON e diferenciam maiúsculas de minúsculas.
> 
> Preste atenção às consultas necessárias para cada campo personalizado na tabela abaixo. Você precisa usar as consultas corretas para :::no-loc text="Log Analytics"::: extrair com êxito os valores de campos personalizados.
> 
 ![Definição de campo personalizado](../media/Deploy-Azure-Monitor-5.png "Definição de campo personalizado")

**Tabela 1**

| **Campo JSON**                   | **:::no-loc text="Log Analytics":::campo personalizado** | **ID do evento** | **Consulta a ser usada com a extração**                   |
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


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a>Definir os :::no-loc text="Microsoft Teams Rooms"::: modos de exibição no:::no-loc text="Log Analytics":::
<a name="Define_Views"> </a>

Depois que os dados são coletados e os campos personalizados são mapeados, você pode usar o designer de exibição para desenvolver :::no-loc text="Microsoft Teams Rooms"::: um painel contendo vários blocos para monitorar eventos. Use o designer de exibição para criar os blocos a seguir. Para obter mais informações, consulte [criar modos de exibição personalizados usando o :::no-loc text="Log Analytics"::: designer de exibição no](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> As etapas anteriores deste guia devem ter sido concluídas para que os blocos do painel funcionem corretamente.

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a>Criar um painel de salas do Microsoft Teams usando o método de importação

Você pode importar um :::no-loc text="Microsoft Teams Rooms"::: painel e começar a monitorar seus dispositivos rapidamente. Siga as etapas a seguir para importar o painel:

1.  Obtenha o arquivo de painel [SkypeRoomSystems_v2. omsview](https://go.microsoft.com/fwlink/?linkid=835675) .
2.  Entre no [ :::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) e vá para :::no-loc text="Log Analytics"::: e selecione seu espaço de trabalho.
3.  Abrir o **Designer de exibição**.
4.  Selecione **importar**e, em seguida, selecione o arquivo **SkypeRoomSystems_v2. omsview** .
5.  Selecione **salvar**.

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>Criar um painel de salas do Microsoft Teams manualmente

Você também pode criar seu próprio painel e adicionar apenas os blocos que deseja monitorar.

#### <a name="configure-the-overview-tile"></a>Configurar o bloco de visão geral

1.  Abrir o **Designer de exibição**.
2.  Selecione **bloco visão geral**e, em seguida, selecione **dois números** na galeria.
3.  Nomeie o bloco **:::no-loc text="Microsoft Teams Rooms":::**.
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

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a>Criar um bloco que exiba :::no-loc text="Microsoft Teams Rooms"::: versões do sistema operacional

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

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a>Criar um bloco que exiba :::no-loc text="Microsoft Teams Rooms"::: versões do aplicativo

1.  Selecione **rosca & lista** da galeria e, em seguida, adicione um novo bloco.
2.  Defina as propriedades **gerais** :<br>
    **Título do Grupo:** :::no-loc text="Microsoft Teams Rooms"::: detalhes do aplicativo<br>
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

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a>Configurar alertas no:::no-loc text="Azure Monitor":::
<a name="Alerts"> </a>

:::no-loc text="Azure Monitor":::pode disparar alertas para notificar os administradores quando um :::no-loc text="Microsoft Teams Rooms"::: console encontra um problema.

:::no-loc text="Azure Monitor":::inclui um mecanismo de alerta interno que é executado por meio de pesquisas de log agendadas em intervalos regulares. Se os resultados da pesquisa de log corresponderem a alguns critérios específicos, um registro de alerta será criado.

A regra pode executar automaticamente uma ou mais ações para notificá-lo proativamente sobre o alerta ou invocar outro processo. As opções possíveis com alertas são:
-   Enviar um email
-   Invocar um processo externo por meio de uma solicitação HTTP POST
-   Iniciando um runbook no :::no-loc text="Azure Automation"::: serviço

Consulte [log de :::no-loc text="Azure Monitor"::: alertas](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log) para saber mais sobre os alertas no :::no-loc text="Azure Monitor":::.

> [!NOTE]
> Os exemplos a seguir enviam alertas por :::no-loc text="Microsoft Teams Rooms"::: email quando um dispositivo gera um erro de hardware ou de aplicativo.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a>Configurar um alerta por email :::no-loc text="Microsoft Teams Rooms"::: para problemas de hardware

Configure uma regra de alerta que verifique :::no-loc text="Microsoft Teams Rooms"::: se há dispositivos que encontraram problemas de hardware na última hora.
1.  Entre no [ :::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) e vá para :::no-loc text="Log Analytics"::: e selecione seu espaço de trabalho.

2. Navegue até seu :::no-loc text="Log Analytics"::: espaço de trabalho e selecione **alertas** e selecione **nova regra de alerta**

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
    **Nome da regra:** :::no-loc text="Microsoft Teams Rooms"::: alerta de falha de hardware<br>
    **Descrição:** Lista de dispositivos que encontraram um problema de hardware na última hora<br>

10. Selecione a gravidade pretendida e verifique se a regra está habilitada.

11. Selecione **criar regra de alerta**.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a>Configurar um alerta por email :::no-loc text="Microsoft Teams Rooms"::: para os problemas do aplicativo

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

! [Exemplo :::no-loc text="Azure Monitor"::: de email de alerta] (.. /media/Deploy-Azure-Monitor-6.png "exemplo :::no-loc text="Azure Monitor"::: de email de alerta")

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a>Configurar todos os dispositivos para:::no-loc text="Azure Monitoring":::
<a name="configure_all_devices"></a> Depois que os painéis e alertas estiverem configurados, você poderá configurar e :::no-loc text="Microsoft Monitoring"::: configurar o agente :::no-loc text="Microsoft Teams Rooms"::: em todos os dispositivos para concluir a implantação do monitoramento.

Embora você possa instalar e configurar o :::no-loc text="Microsoft Monitoring"::: agente manualmente em cada dispositivo, é altamente recomendável aproveitar ferramentas e métodos de implantação de software existentes.

Se você estiver criando seus :::no-loc text="Microsoft Teams Rooms"::: dispositivos pela primeira vez, talvez queira incluir as :::no-loc text="Microsoft Monitoring"::: etapas de configuração e configuração do agente como parte do processo de compilação. Para obter mais informações, consulte [instalar o agente usando a linha de comando](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>Implantando o :::no-loc text="Microsoft Monitoring"::: agente usando um objeto de política de grupo (GPO)

Se você já implantou seus :::no-loc text="Microsoft Teams Rooms"::: dispositivos antes :::no-loc text="Azure Monitoring":::de implementar, pode usar o script fornecido para configurar e configurar os agentes usando :::no-loc text="Active Directory"::: objetos de política de grupo.

1.  Crie um caminho de rede compartilhado e conceda acesso de leitura ao grupo **computadores do domínio** .

2.  Baixe a versão de 64 bits do :::no-loc text="Microsoft Monitoring"::: agente para de :::no-loc text="Windows":::<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  Extraia o conteúdo do pacote de instalação para o compartilhamento de rede.
    1.  Abra uma janela do prompt de comando e execute **MMASetup-AMD64. exe/c**
    2.  Especifique o compartilhamento que você acabou de criar e extraia o conteúdo.

4.  Crie um novo objeto de política de grupo e atribua-o à unidade :::no-loc text="Microsoft Teams Rooms"::: organizacional onde as contas do computador estão localizadas.

5.  Configurar a política de execução do PowerShell:
    1.  Editar o objeto de política de grupo recém criado e navegar para \\ políticas \\ de configuração \\ :::no-loc text="Windows"::: do \\ computador componentes de modelos administrativos:::no-loc text="Windows PowerShell":::
    2.  Habilite a política **ativar a execução de scripts** e definir a **execução** para **Permitir scripts locais**.

6.  Configurar o script de inicialização:
    1.  Copie o script a seguir e salve-o como Install-MMAgent. ps1.
    2.  Modifique os parâmetros Workspaceid, WorkspaceKey e SetupPath para corresponderem à sua configuração.
    3.  Editar o mesmo objeto de política de grupo e navegar para \\ configurações \\ :::no-loc text="Windows"::: \\ de políticas de configuração do computador scripts (inicialização/desligamento)
    4.  Clique duas vezes para selecionar **inicialização**e, em seguida, selecione **scripts do PowerShell**.
    5.  Selecione **Mostrar arquivos**e copie o arquivo **install-MMAgent. ps1** para essa pasta.
    6.  Selecione **Adicionar**e, em seguida, **procurar**.
    7.  Selecione o script ps1 que você acabou de copiar.

7.  :::no-loc text="Microsoft Teams Rooms":::os dispositivos devem instalar e configurar :::no-loc text="Microsoft Monitoring"::: o agente com a segunda reinicialização.

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
> Você pode consultar o artigo sobre como [gerenciar e manter :::no-loc text="Log Analytics"::: o agente](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage) quando precisar reconfigurar um agente, movê-lo para um espaço de trabalho diferente ou modificar as configurações de proxy após a instalação inicial.

## <a name="additional-solutions"></a>Soluções adicionais
<a name="Solutions"> </a>

:::no-loc text="Azure Monitor":::fornece soluções de gerenciamento internas por meio da [Galeria de soluções](https://docs.microsoft.com/azure/azure-monitor/insights/solutions) para ajudar você a monitorar seu ambiente. É altamente recomendável que você também adicione soluções de [Gerenciamento de alertas](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution) e [ :::no-loc text="Azure Log Analytics"::: integridade do agente](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth) ao seu espaço de trabalho.

> [!NOTE]
> A solução de integridade do agente pode ajudá-lo a :::no-loc text="Microsoft Monitoring"::: identificar agentes desatualizados ou quebrados em seu ambiente, e a solução de gerenciamento de alertas fornece detalhes sobre os alertas que foram lançados dentro de um determinado período.

## <a name="see-also"></a>Confira também

[Gerenciamento :::no-loc text="Microsoft Teams Rooms"::: de planos com:::no-loc text="Azure Monitor":::](azure-monitor-plan.md)

[Gerenciar :::no-loc text="Microsoft Teams Rooms"::: dispositivos com:::no-loc text="Azure Monitor":::](azure-monitor-manage.md)
