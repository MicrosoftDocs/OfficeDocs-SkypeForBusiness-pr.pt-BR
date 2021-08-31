---
title: Implantar Salas do Microsoft Teams gerenciamento com o Azure Monitor
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
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: Este artigo discute como implantar o gerenciamento de dispositivos Salas do Microsoft Teams de forma integrada e de ponta a ponta usando o Azure Monitor.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6713b8651432766e6858f3376ff9804d638babcc
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726110"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-management-with-no-loc-textazure-monitor"></a>Implantar :::no-loc text="Microsoft Teams Rooms"::: o gerenciamento com :::no-loc text="Azure Monitor":::

Este artigo discute como configurar e implantar o gerenciamento integrado e de ponta a ponta de :::no-loc text="Microsoft Teams Rooms"::: dispositivos usando :::no-loc text="Azure Monitor"::: .

Você pode configurar dentro para fornecer telemetria básica e :::no-loc text="Log Analytics"::: :::no-loc text="Azure Monitor"::: alertas que o ajudarão a gerenciar dispositivos :::no-loc text="Microsoft Teams Rooms"::: de sala de reunião. À medida que sua solução de gerenciamento amadurece, você pode optar por implantar recursos adicionais de gerenciamento e dados para criar uma visão mais detalhada da disponibilidade e do desempenho do dispositivo.

Seguindo este guia, você pode usar um painel como o exemplo a seguir para obter relatórios detalhados de status para disponibilidade do dispositivo, a saúde do aplicativo e do hardware e a distribuição de versão do aplicativo e do sistema :::no-loc text="Microsoft Teams Rooms"::: operacional.

![Captura de tela do exemplo de exibição do Log Analytics para Salas do Microsoft Teams.](../media/Deploy-Azure-Monitor-1.png "Exemplo de exibição de Análise de Log para Salas do Microsoft Teams")

Em um nível superior, é necessário executar as seguintes tarefas:


1. [Validar :::no-loc text="Log Analytics"::: configuração](azure-monitor-deploy.md#validate_LogAnalytics)
2. [Configurar dispositivos de teste para :::no-loc text="Log Analytics"::: configuração de gerenciamento](azure-monitor-deploy.md#configure_test_devices)
3. [Mapear os campos personalizados](azure-monitor-deploy.md#Custom_fields)
4. [Definir os :::no-loc text="Microsoft Teams Rooms"::: exibições em :::no-loc text="Log Analytics":::](azure-monitor-deploy.md#Define_Views)
5. [Definir alertas](azure-monitor-deploy.md#Alerts)
6. [Configurar todos os dispositivos para Monitoramento](azure-monitor-deploy.md#configure_all_devices)
7. [Configurar soluções :::no-loc text="Azure Monitor"::: adicionais](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> Embora com configuração mínima, possa monitorar um computador executando um sistema operacional, ainda há algumas etapas específicas que você precisa executar antes de começar a implantar agentes em todos :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: :::no-loc text="Windows"::: :::no-loc text="Microsoft Teams Rooms"::: os :::no-loc text="Microsoft Teams Rooms"::: dispositivos.
> Portanto, é altamente recomendável que você execute todas as etapas de configuração na ordem correta para uma configuração e configuração controladas. A qualidade do resultado final depende muito da qualidade da configuração inicial.

## <a name="validate-no-loc-textlog-analytics-configuration"></a>Validar :::no-loc text="Log Analytics"::: configuração
<a name="validate_LogAnalytics"> </a>

Você precisa ter um espaço de trabalho para começar a :::no-loc text="Log Analytics"::: coletar logs de :::no-loc text="Microsoft Teams Rooms"::: dispositivos. Um espaço de trabalho é um ambiente exclusivo com seu próprio repositório de :::no-loc text="Log Analytics"::: dados, fontes de dados e soluções. Se você já tiver um espaço de trabalho existente, poderá usá-lo para monitorar sua implantação ou, como alternativa, criar um espaço de trabalho dedicado específico às suas necessidades :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: de :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: monitoramento.

Se você precisar criar um novo espaço de trabalho, siga as instruções :::no-loc text="Log Analytics"::: no artigo Criar um espaço de trabalho no [ :::no-loc text="Log Analytics"::: :::no-loc text="Azure"::: portal](/azure/azure-monitor/learn/quick-create-workspace)

> [!NOTE]
> Para usar :::no-loc text="Log Analytics"::: com , você precisa ter uma assinatura :::no-loc text="Azure Monitor"::: :::no-loc text="Azure"::: ativa. Se você não tiver uma assinatura, poderá criar uma assinatura de :::no-loc text="Azure"::: [avaliação gratuita](https://azure.microsoft.com/free) como ponto de partida.

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a>Configurar :::no-loc text="Log Analytics"::: para coletar logs de :::no-loc text="Microsoft Teams Rooms"::: eventos

:::no-loc text="Log Analytics"::: coleta apenas eventos dos :::no-loc text="Windows"::: logs de eventos especificados nas configurações. Para cada log, apenas os eventos com as gravidades selecionadas são coletados.

Você precisa configurar para :::no-loc text="Log Analytics"::: coletar os logs necessários para monitorar o status :::no-loc text="Microsoft Teams Rooms"::: do dispositivo e do aplicativo. :::no-loc text="Microsoft Teams Rooms"::: os dispositivos usam **:::no-loc text="Skype Room System":::** o log de eventos.

Para configurar :::no-loc text="Log Analytics"::: para coletar os eventos, consulte fontes de dados :::no-loc text="Microsoft Teams Rooms"::: do log de eventos [ :::no-loc text="Windows"::: em :::no-loc text="Azure Monitor"::: ](/azure/azure-monitor/platform/data-sources-windows-events)

![Captura de tela das configurações do log de eventos.](../media/Deploy-Azure-Monitor-2.png "Configurações de log de eventos")

> [!IMPORTANT]
> Configure as configurações do Log de Eventos e insira como nome do log de eventos e selecione as caixas de seleção :::no-loc text="Windows"::: **:::no-loc text="Skype Room System":::** **Erro,** **Aviso** e **Informações.**

## <a name="configure-test-devices-for-azure-monitoring"></a>Configurar dispositivos de teste para Monitoramento do Azure
<a name="configure_test_devices"> </a>

Você precisa se :::no-loc text="Log Analytics"::: preparar para poder monitorar eventos :::no-loc text="Microsoft Teams Rooms"::: relacionados. Para começar, você precisa implantar agentes em apenas um ou dois dispositivos aos qual você tem acesso físico, e fazer com que esses dispositivos de teste gerem alguns dados e os pressionem para :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: o espaço de :::no-loc text="Log Analytics"::: trabalho.

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a>Instalar :::no-loc text="Microsoft Monitoring"::: agentes para testar dispositivos

Implante o agente nos dispositivos de teste usando as instruções fornecidas :::no-loc text="Microsoft Monitoring"::: [Conexão :::no-loc text="Windows"::: computadores para o serviço :::no-loc text="Log Analytics"::: em :::no-loc text="Azure"::: ](/azure/azure-monitor/platform/agent-windows). Este artigo fornece informações detalhadas sobre as etapas de implantação do Agente para , instruções para obter a ID do Workspace _ e a _ chave primária * para conectar dispositivos à sua implantação e etapas para verificar a conectividade do agente com a :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Windows"::: :::no-loc text="Log Analytics":::  * ** :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: instância.

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a>Gerar eventos de :::no-loc text="Microsoft Teams Rooms"::: exemplo

Depois que :::no-loc text="Microsoft Monitoring"::: o agente for implantado nos dispositivos de teste, verifique se os dados de log de eventos necessários são coletados por :::no-loc text="Azure Monitor"::: .

> [!NOTE]
> Reinicie o dispositivo após a instalação do agente e certifique-se de que o aplicativo de reunião foi iniciado, para que ele possa gerar novos eventos :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: no Log de Eventos.

1.  Entre no [ :::no-loc text="Microsoft Azure"::: portal e](https://portal.azure.com) vá para :::no-loc text="Log Analytics"::: e selecione seu espaço de trabalho.

2.  Listar os eventos de pulsação gerados por um :::no-loc text="Microsoft Teams Rooms"::: dispositivo:
    1.  Selecione seu espaço de trabalho e vá para **Logs** e use uma consulta para recuperar os registros de pulsação que terão os campos personalizados para :::no-loc text="Microsoft Teams Rooms"::: .
    2.  Consulta de exemplo: `Event | where Source == "SRS-App" and EventID == 2000`

3.  Certifique-se de que a consulta retorna registros de log que incluem eventos gerados pelo :::no-loc text="Microsoft Teams Rooms"::: aplicativo de reuniões.

4.  Gere um problema de hardware e valide se os eventos necessários estão conectados :::no-loc text="Azure Log Analytics"::: em .
    1.  Desconectar um dos dispositivos periféricos no sistema de :::no-loc text="Microsoft Teams Rooms"::: teste. Isso pode ser a câmera, o viva-voz, o microfone ou a tela da sala frontal
    2.  Aguarde 10 minutos para que o log de eventos seja preenchido em :::no-loc text="Azure Log Analytics"::: .
    3.  Use uma consulta para listar eventos de erro de hardware: `Event | where Source == "SRS-App" and EventID == 3001`

5.  Gere um problema de aplicativo e valide se os eventos necessários estão registrados.
    1.  Modifique a configuração do aplicativo e digite um par de endereço/senha SIP (Protocolo de :::no-loc text="Microsoft Teams Rooms"::: Iniciação de Sessão) incorreto.
    2.  Aguarde 10 minutos para que o log de eventos seja preenchido em :::no-loc text="Azure Log Analytics"::: .
    3.  Use uma consulta para listar eventos de erro do aplicativo: `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> Esses logs de eventos de exemplo são necessários antes que os campos personalizados possam ser configurados. Não prossiga para a próxima etapa até coletar os logs de eventos necessários.

## <a name="map-custom-fields"></a>Mapear os campos personalizados
<a name="Custom_fields"> </a>

Você usa campos personalizados para extrair dados específicos dos logs de eventos. Você precisa definir campos personalizados que serão usados posteriormente com seus blocos, exibições de painel e alertas. Consulte [Campos :::no-loc text="Log Analytics"::: personalizados em](/azure/azure-monitor/platform/custom-fields) e familiarizar-se com os conceitos antes de começar a criar seus campos personalizados.

Para extrair seus campos personalizados dos logs de eventos capturados, siga estas etapas:

1.  Entre no [ :::no-loc text="Microsoft Azure"::: portal e](https://portal.azure.com) vá para :::no-loc text="Log Analytics"::: e selecione seu espaço de trabalho.

2. Listar os eventos gerados por um :::no-loc text="Microsoft Teams Rooms"::: dispositivo:
   1.  Vá para **Logs** e use uma consulta para recuperar os registros que terão o campo personalizado.
   2.  Consulta de exemplo: `Event | where Source == "SRS-App" and EventID == 2000`

3. Selecione um dos registros, selecione o botão à esquerda e inicie o assistente de extração de campo.
4. Realça os dados que você gostaria de extrair do RenderizadoDescription e fornecer um Título de Campo. Os nomes de campo que você deve usar são fornecidos na Tabela 1.
5. Use os mapeamentos mostrados na *Tabela 1*. :::no-loc text="Log Analytics":::anexarão automaticamente a **\_ cadeia de caracteres CF** quando você definir o novo campo.

> [!IMPORTANT]
> Lembre-se de que todos os campos e JSON :::no-loc text="Log Analytics"::: são sensíveis a minúsculas.
> 
> Preste atenção às consultas necessárias para cada campo personalizado na tabela abaixo. Você precisa usar as consultas corretas para extrair com êxito valores :::no-loc text="Log Analytics"::: de campo personalizados.
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
| Status do alto-falante de conferência        | SRSConfSpeakerStatus        | **3001**     | Evento \| em que Source == "SRS-App" e EventID == 3001 |
| Status padrão do alto-falante           | SRSDefaultSpeakerStatus     | **3001**     | Evento \| em que Source == "SRS-App" e EventID == 3001 |
| Status da câmera                    | SRSCameraStatus             | **3001**     | Evento \| em que Source == "SRS-App" e EventID == 3001 |
| Status de exibição frontal da sala     | SRSFORDStatus               | **3001**     | Evento \| em que Source == "SRS-App" e EventID == 3001 |
| Status do sensor de movimento             | SRSMotionSensorStatus       | **3001**     | Evento \| em que Source == "SRS-App" e EventID == 3001 |
| Status de Ingestão HDMI               | SRSHDMIIngestStatus         | **3001**     | Evento \| em que Source == "SRS-App" e EventID == 3001 |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a>Definir os :::no-loc text="Microsoft Teams Rooms"::: exibições em :::no-loc text="Log Analytics":::
<a name="Define_Views"> </a>

Depois que os dados são coletados e os campos personalizados são mapeados, você pode usar o Designer de Exibição para desenvolver um painel contendo vários blocos para monitorar :::no-loc text="Microsoft Teams Rooms"::: eventos. Use o Designer de Exibição para criar os seguintes blocos. Para obter mais informações, consulte [Create :::no-loc text="Log Analytics"::: custom views by using View Designer in](/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> As etapas anteriores neste guia devem ter sido concluídas para que os blocos do painel funcionem corretamente.
>
> [!IMPORTANT]
> View Designer no Azure Monitor está se retirando em 31 de agosto de [2023](https://azure.microsoft.com/updates/view-designer-in-azure-monitor-is-retiring-on-31-august-2023/) e as funcionalidades de criação e clonagem foram desabilitadas em 30 de novembro de 2020. Em vez disso, as guias de trabalho podem ser usadas. Para obter mais informações sobre o guia de transição do designer de exibição para as planilhas, consulte Início rápido com modelos de designer de exibição [predefinidos.](/azure/azure-monitor/visualize/view-designer-conversion-tasks#quickstart-with-preset-view-designer-templates)

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>Criar um painel Salas do Microsoft Teams manualmente

Como alternativa, você pode criar seu próprio painel e adicionar apenas os blocos que deseja monitorar.

#### <a name="configure-the-overview-tile"></a>Configurar o Conjunto de Visão Geral

1.  Open **View Designer**.
2.  Selecione **Azulejo de** Visão Geral e selecione **Dois números** na galeria.
3.  Nomeia o **:::no-loc text="Microsoft Teams Rooms":::** azulejo .
4.  Defina **o Primeiro Tile**:<br>
    **Legenda:** Dispositivos que enviaram uma pulsação pelo menos uma vez no último mês<br>
    **Consulta:**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  Definir o **Segundo Tile**:<br>
    **Legenda:** Dispositivos ativos que enviaram uma pulsação na última hora<br>
    **Consulta:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  Selecione **Aplicar**.

### <a name="create-a-tile-that-displays-active-devices"></a>Criar um azulejo que exibe dispositivos ativos

1.  Selecione **Exibir Painel** para começar a adicionar seus blocos.
2.  Selecione **Número & lista** na galeria
3.  Defina as **propriedades** Gerais:<br>
    **Título do grupo:** Status da pulsação<br>
    **Novo Grupo:** Selected
4.  Defina **as propriedades de tile:**<br>
    **Legenda:** Dispositivos ativos (pulsação enviada nos últimos 20 minutos)<br>
    **Consulta de bloco:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  Defina as **propriedades List:**<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  Definir **títulos de coluna:**<br>
    **Nome:** Nome do computador<br>
    **Valor:** Last Heartbeat
7.  Definir **Consulta de Navegação**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Selecione **Aplicar** e, em **seguida, Fechar**.

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>Criar um azulejo que exibe dispositivos com problemas de conectividade

1.  Selecione **Número & lista** na galeria e adicione um novo azulejo.
2.  Defina as **propriedades** Gerais:<br>
    **Título do grupo:** Deixar vazio<br>
    **Novo Grupo:** Não Selecionado
3.  Defina **as propriedades de tile:**<br>
    **Legenda:** Dispositivos Inativos (nenhuma mensagem de pulsação enviada nos últimos 20 minutos)<br>
    **Consulta de bloco:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  Defina as **propriedades List:**<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  Definir **títulos de coluna:**<br>
    **Nome:** Nome do computador<br>
    **Valor:** Last Heartbeat
6.  Definir **Consulta de Navegação**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Selecione **Aplicar** e, em **seguida, Fechar**.

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>Criar um azulejo que exibe dispositivos com um erro de hardware

1.  Selecione **Número & lista** na galeria e adicione um novo azulejo.
2.  Defina as **propriedades** Gerais:<br>
    **Título do grupo:** Hardware Status<br>
    **Novo Grupo:** Selected
3.  Defina **as propriedades de tile:**<br>
    **Legenda:** Dispositivos que sofreram um erro de hardware na última hora<br>
    **Consulta de bloco:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Defina as **propriedades List:**<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Definir **títulos de coluna:**<br>
    **Nome:** Nome do computador<br>
    **Valor:** Último Erro
6.  Definir **Consulta de Navegação**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Selecione **Aplicar** e, em **seguida, Fechar**.

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a>Criar um azulejo que exibe :::no-loc text="Microsoft Teams Rooms"::: versões do Sistema Operacional

1.  Selecione **& lista de &** na galeria e, em seguida, adicione um novo azulejo.
2.  Defina as **propriedades** Gerais:<br>
    **Título do grupo:** Detalhes do sistema operacional<br>
    **Novo Grupo:** Selected
3.  Defina as **propriedades do Header:**<br>
    **Título:** Versões do sistema operacional<br>
    **Subtítulo:** Dispositivos que executam versões específicas do sistema operacional
4.  Defina as **propriedades do Donut:**<br>
    **Consulta:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **Texto central:** Dispositivos<br>
    **Operação:** Soma
5.  Defina as **propriedades List.**<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **Ocultar Graph:** Selected<br>
    **Habilitar Sparklines:** Não selecionado
6.  Definir **títulos de coluna**.<br>
    **Nome:** Nome do computador<br>
    **Valor:** Deixar Vazio
7.  Definir **Consulta de Navegação**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Selecione **Aplicar** **e,** em seguida, Fechar .

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a>Criar um azulejo que exibe :::no-loc text="Microsoft Teams Rooms"::: versões de aplicativos

1.  Selecione **& lista de &** na galeria e, em seguida, adicione um novo azulejo.
2.  Defina as **propriedades** Gerais:<br>
    **Título do grupo:** :::no-loc text="Microsoft Teams Rooms"::: detalhes do aplicativo<br>
    **Novo Grupo:** Selected
3.  Defina as **propriedades do Header:**<br>
    **Título:** Versões do aplicativo<br>
    **Subtítulo:** Dispositivos que executam versões de aplicativos específicas
4.  Defina as **propriedades do Donut:**<br>
    **Consulta:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **Texto central:** Dispositivos<br>
    **Operação:** Soma
5.  Defina as **propriedades List.**<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **Ocultar Graph:** Selected<br>
    **Habilitar Sparklines:** Não selecionado
6.  Definir **títulos de coluna**.<br>
    **Nome:** Nome do computador<br>
    **Valor:** Deixar Vazio
7.  Definir **Consulta de Navegação**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Selecione **Aplicar** **e,** em seguida, Fechar .

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>Criar um azulejo que exibe dispositivos com um erro de aplicativo

1.  Selecione **Número & lista** na galeria e adicione um novo azulejo.
2.  Defina as **propriedades** Gerais.<br>
    **Título do grupo:** Deixar vazio<br>
    **Novo Grupo:** Não Selecionado
3.  Defina **as propriedades do Tile.**<br>
    **Legenda:** Dispositivos que sofreram um erro de aplicativo na última hora<br>
    **Consulta de bloco:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Defina as **propriedades List.**<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Definir **títulos de coluna**.<br>
    **Nome:** Nome do computador<br>
    **Valor:** Último Erro
6.  Definir **Consulta de Navegação**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Selecione **Aplicar** **e,** em seguida, Fechar .

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>Criar um azulejo que exibe dispositivos que foram reiniciados

1.  Selecione **Número & lista** na galeria e adicione um novo azulejo.
2.  Defina as **propriedades** Gerais.<br>
    **Título do grupo:** Deixar vazio<br>
    **Novo Grupo:** Não Selecionado
3.  Defina **as propriedades do Tile.**<br>
    **Legenda:** Dispositivos em que o aplicativo foi reiniciado nas últimas 24 horas e número de reinicializações<br>
    **Consulta de bloco:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  Defina as **propriedades List.**<br>
    **Consulta de lista:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  Definir **títulos de coluna**.<br>
    **Nome:** Nome do computador<br>
    **Valor:** Número de Reinicializações
6.  Definir **Consulta de Navegação**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Selecione **Aplicar** **e,** em seguida, Fechar .
8.  Selecione **Salvar** para salvar seu painel.

Agora você concluiu a criação de seus exibições.

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a>Configurar alertas em :::no-loc text="Azure Monitor":::
<a name="Alerts"> </a>

:::no-loc text="Azure Monitor"::: pode levantar alertas para notificar os administradores, quando um :::no-loc text="Microsoft Teams Rooms"::: console encontrar um problema.

:::no-loc text="Azure Monitor"::: inclui um mecanismo de alerta integrado que é executado por meio de pesquisas de log agendadas em intervalos regulares. Se os resultados da pesquisa de log corresponderem a alguns critérios específicos, um registro de alerta será criado.

A regra pode executar automaticamente uma ou mais ações para notificar proativamente o alerta ou invocar outro processo. As opções possíveis com alertas são:
-   Enviando um email
-   Invocar um processo externo por meio de uma solicitação HTTP POST
-   Iniciando um runbook no :::no-loc text="Azure Automation"::: serviço

Consulte [Os alertas de log para :::no-loc text="Azure Monitor"::: ](/azure/azure-monitor/platform/alerts-unified-log) saber mais sobre os alertas em :::no-loc text="Azure Monitor"::: .

> [!NOTE]
> Os exemplos a seguir enviam alertas de email quando um :::no-loc text="Microsoft Teams Rooms"::: dispositivo gera um hardware ou um erro de aplicativo.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a>Configurar um alerta de email para :::no-loc text="Microsoft Teams Rooms"::: problemas de hardware

Configure uma regra de alerta que verifica dispositivos que encontraram :::no-loc text="Microsoft Teams Rooms"::: problemas de hardware na última hora.
1.  Entre no [ :::no-loc text="Microsoft Azure"::: portal e](https://portal.azure.com) vá para :::no-loc text="Log Analytics"::: e selecione seu espaço de trabalho.

2. Navegue até seu :::no-loc text="Log Analytics"::: espaço de trabalho, selecione **Alertas** e selecione **Nova regra de alerta**

3. Selecione **Adicionar condição** e, em **seguida, Pesquisa de log personalizada**

4.  Insira a seguinte consulta na caixa de texto Pesquisar consulta.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  Configure as configurações de lógica de alerta:<br>
    **Com base em:** Número de resultados<br>
    **Condição:** Maior, em seguida,<br>
    **Limite:** 0<br>

6. Configurar configurações de Avaliação e selecione **Feito**: <br>
    **Ponto (em minutos):** 60<br>
    **Frequência (em minutos):** 60<br>

7. Configurar grupos de ações:
    1.  Selecione **Criar Novo**
    2.  Forneça nomes adequados para os campos *Nome do grupo ação* e Nome *curto.*
    3.  Especifique um *Nome de Ação exclusivo* e selecione **Email/SMS/Push/Voice** e selecione **Editar detalhes**.
    4.  Marque a **caixa de** seleção Email e forneça o endereço de email da pessoa ou grupo que receberá os alertas.
    5.  Você também pode fornecer seu número de telefone para ser notificado com SMS, uma chamada de voz ou ambos.
    6. Selecione **OK**.

8. **Personalize Ações** se você quiser substituir a linha de assunto dos emails de alerta.

9. Especifique um nome de regra e uma descrição.<br>
    **Nome da regra:** :::no-loc text="Microsoft Teams Rooms"::: Alerta de Falha de Hardware<br>
    **Descrição:** Lista de dispositivos que encontraram um problema de hardware na última hora<br>

10. Selecione a gravidade pretendido e certifique-se de que a regra está habilitada.

11. Selecione **Criar regra de alerta**.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a>Configurar um alerta de email para problemas :::no-loc text="Microsoft Teams Rooms"::: de aplicativo

Repita o mesmo procedimento, mas use a seguinte consulta para listar dispositivos que encontraram problemas de aplicativo na última hora.

 ```
 Event
 | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
 | summarize arg_max(TimeGenerated, *) by Computer
 | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
 | sort by TimeGenerated desc
 ```

Agora você concluiu a definição de alertas. Você pode definir alertas adicionais usando os exemplos acima.

Quando um alerta é gerado, você obterá um email que lista os dispositivos que encontraram um problema na última hora.

! [Exemplo :::no-loc text="Azure Monitor"::: de email de alerta](.. /media/Deploy-Azure-Monitor-6.png "Exemplo de :::no-loc text="Azure Monitor"::: email de alerta")

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a>Configurar todos os dispositivos para :::no-loc text="Azure Monitoring":::
<a name="configure_all_devices"></a> Depois que os painéis e alertas são configurados, você pode configurar e configurar o agente em todos os dispositivos para concluir sua :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: implantação de monitoramento.

Embora você possa instalar e configurar o agente manualmente em cada dispositivo, é altamente recomendável utilizar ferramentas e métodos de implantação de :::no-loc text="Microsoft Monitoring"::: software existentes.

Se você estiver criando seus dispositivos pela primeira vez, talvez queira incluir as etapas de configuração e configuração do agente como parte do processo :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Microsoft Monitoring"::: de com build. Para obter mais informações, [consulte Install the agent using the command line](/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>Implantando :::no-loc text="Microsoft Monitoring"::: o agente usando um Objeto de Política de Grupo (GPO)

Se você já tiver implantado seus dispositivos antes de implementar , poderá usar o script fornecido para configurar e configurar os agentes usando :::no-loc text="Microsoft Teams Rooms"::: objetos de política de :::no-loc text="Azure Monitoring"::: :::no-loc text="Active Directory"::: grupo.

1.  Crie um caminho de rede compartilhado e conceda acesso de leitura ao **grupo Computadores de** Domínio.

2.  Baixar a versão de 64 bits do :::no-loc text="Microsoft Monitoring"::: Agente para a partir :::no-loc text="Windows"::: de <https://go.microsoft.com/fwlink/?LinkID=517476>

3.  Extraia o conteúdo do pacote de instalação para o compartilhamento de rede.
    1.  Abra uma janela prompt de comando e execute **MMASetup-AMD64.exe /c**
    2.  Especifique o compartilhamento que você acabou de criar e extraia o conteúdo.

4.  Crie um novo Objeto de Política de Grupo e atribua-o à unidade organizacional onde as contas :::no-loc text="Microsoft Teams Rooms"::: de máquina estão localizadas.

5.  Configurar a política de execução do PowerShell:
    1.  Edite o objeto de Política de Grupo recém-criado e navegue até Configuração do Computador \\ \\ Componentes de Modelos \\ :::no-loc text="Windows"::: Administrativos \\:::no-loc text="Windows PowerShell":::
    2.  **Habilita a Execução de Script Ativado e** de definir a Política de **Execução** como **Permitir Scripts Locais.**

6.  Configure o script de inicialização:
    1.  Copie o script a seguir e salve-o como Install-MMAgent.ps1.
    2.  Modifique os parâmetros WorkspaceId, WorkspaceKey e SetupPath para corresponder à configuração.
    3.  Edite o mesmo Objeto de Política de Grupo e navegue até Políticas de Configuração do \\ \\ :::no-loc text="Windows"::: Computador Configurações \\ Scripts (Inicialização/Desligamento)
    4.  Clique duas vezes para selecionar **Inicialização** e selecione **Scripts do PowerShell.**
    5.  Selecione **Mostrar Arquivos** e, em seguida, copie o arquivo **Install-MMAgent.ps1** para essa pasta.
    6.  Selecione **Adicionar** e, em seguida, **Procurar**.
    7.  Selecione o script ps1 que você acabou de copiar.

7.  :::no-loc text="Microsoft Teams Rooms"::: os dispositivos devem instalar e configurar o :::no-loc text="Microsoft Monitoring"::: agente com a segunda reinicialização.

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
> Você pode consultar [ :::no-loc text="Log Analytics"::: ](/azure/azure-monitor/platform/agent-manage) o artigo Gerenciando e mantendo o agente quando precisar reconfigurar um agente, movê-lo para um espaço de trabalho diferente ou modificar configurações de proxy após a instalação inicial.

## <a name="additional-solutions"></a>Soluções adicionais
<a name="Solutions"> </a>

:::no-loc text="Azure Monitor"::: fornece soluções de gerenciamento integradas por meio de sua galeria [de soluções](/azure/azure-monitor/insights/solutions) para ajudar você a monitorar seu ambiente. É altamente recomendável adicionar soluções de Gerenciamento [de Alertas](/azure/azure-monitor/platform/alert-management-solution) e [ :::no-loc text="Azure Log Analytics"::: Saúde](/azure/azure-monitor/insights/solution-agenthealth) do Agente ao seu espaço de trabalho.

> [!NOTE]
> A solução de Saúde do Agente pode ajudá-lo a identificar agentes desatualizados ou desfeitos em seu ambiente, e a solução de Gerenciamento de Alertas fornece detalhes sobre os alertas que foram gerados em um :::no-loc text="Microsoft Monitoring"::: determinado período.

## <a name="see-also"></a>Confira também

[Planejar :::no-loc text="Microsoft Teams Rooms"::: o gerenciamento com :::no-loc text="Azure Monitor":::](azure-monitor-plan.md)

[Gerenciar :::no-loc text="Microsoft Teams Rooms"::: dispositivos com :::no-loc text="Azure Monitor":::](azure-monitor-manage.md)
