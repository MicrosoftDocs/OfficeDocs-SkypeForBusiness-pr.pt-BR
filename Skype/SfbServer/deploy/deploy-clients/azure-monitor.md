---
title: Implantar o gerenciamento de salas de equipes da Microsoft com o Monitor do Azure
ms.author: jambirk
author: jambirk
ms.reviewer: Turgayo
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: Este artigo discute como implantar o gerenciamento de dispositivos de salas de equipes da Microsoft de forma integrada e de ponta a ponta, usando o Monitor do Azure.
ms.openlocfilehash: 599cbb7abce2b20dac27ffebacb041062a254905
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219488"
---
# <a name="deploy-microsoft-teams-rooms-management-with-azure-monitor"></a>Implantar o gerenciamento de salas de equipes da Microsoft com o Monitor do Azure

Este artigo discute como configurar e implantar o gerenciamento integrado de ponta a ponta de dispositivos de salas de equipes da Microsoft usando o Monitor do Azure.

Você pode configurar o Log de análise no Monitor do Windows Azure para fornecer Telemetria básica e alertas que ajudarão você a gerenciar salas de equipes de Microsoft dispositivos de sala de reunião. Como sua solução de gerenciamento for envelhecendo, talvez você decida implantar recursos de gerenciamento para criar uma visão mais detalhada de desempenho e disponibilidade de dispositivo e dados adicionais.

Seguindo este guia, você pode usar um painel semelhante ao seguinte exemplo para obter o status detalhado de relatórios para disponibilidade de dispositivo, aplicativo e integridade de hardware e o aplicativo de salas de equipes da Microsoft e distribuição de versão do sistema operacional.

![Modo de exibição de análise de Log de amostra para salas de equipes da Microsoft] (../../media/Deploy-Azure-Monitor-1.png "Modo de exibição de análise de Log de amostra para salas de equipes da Microsoft")

Em um nível superior, é necessário executar as seguintes tarefas:


1.  [Validar a configuração da análise de Log](azure-monitor.md#validate_LogAnalytics)
2.  [Configurar dispositivos de teste de configuração de gerenciamento de análise de Log](azure-monitor.md#configure_test_devices)
3.  [Mapear os campos personalizados](azure-monitor.md#Custom_fields)
4.  [Definir os modos de exibição de salas de equipes da Microsoft na análise de Log](azure-monitor.md#Define_Views)
5.  [Definir alertas](azure-monitor.md#Alerts)
6.  [Configurar todos os dispositivos para monitoramento](azure-monitor.md#configure_all_devices)
7.  [Configurar soluções adicionais do Monitor do Windows Azure](azure-monitor.md#Solutions)

> [!IMPORTANT]
> Embora com a configuração mínima, análise de Log do Windows Azure Monitor pode monitorar a um computador que executa um sistema operacional Windows, ainda há algumas etapas Teams Microsoft salas – específicos que precisam ser executadas antes de começar a implantar agentes para todos os Teams da Microsoft Dispositivos de salas.
> Portanto, é altamente recomendável que executar todas as etapas de configuração na ordem correta para um controlado de instalação e configuração. A qualidade do resultado final depende muito a qualidade da configuração inicial.

## <a name="validate-log-analytics-configuration"></a>Validar a configuração da análise de Log
<a name="validate_LogAnalytics"> </a>

Você precisa ter um espaço de trabalho de análise de Log para iniciar a coleta de logs de dispositivos de salas de equipes da Microsoft. Um espaço de trabalho é um ambiente de análise de Log exclusivo com seu próprio repositório de dados, fontes de dados e soluções. Se você já tiver um espaço de trabalho de análise de Log existente, você pode usá-lo para monitorar sua implantação do Microsoft equipes salas ou como alternativa, você pode criar um espaço de trabalho de análise de Log dedicado específica para suas salas de equipes da Microsoft necessidades de monitoramento.

Se você precisar criar um novo espaço de trabalho de análise de Log, siga as instruções no artigo [criar um espaço de trabalho de análise de Log no portal do Azure](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)

> [!NOTE]
> Para usar a análise de Log com Monitor do Azure, você precisa ter uma assinatura do Azure active. Se você não tiver uma assinatura do Windows Azure, você pode criar [uma assinatura de avaliação gratuita](https://azure.microsoft.com/free) como ponto de partida.

### <a name="configure-log-analytics-to-collect-microsoft-teams-rooms-event-logs"></a>Configurar o Log de análise para coletar logs de eventos de salas de equipes da Microsoft

Análise de log coleta somente eventos de logs de eventos do Windows que são especificados nas configurações do. Para cada log, somente os eventos a severidades selecionadas são coletados.

Você precisa configurar o Log de análise para coletar os logs necessários para monitorar o status de dispositivo e o aplicativo de salas de equipes da Microsoft. Dispositivos de salas de equipes da Microsoft usam o log de eventos do **Sistema do Skype sala** .

Para configurar o Log de análise para coletar os eventos de salas de equipes da Microsoft, consulte [fontes de dados de log de eventos do Windows no Monitor do Azure](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)

![Configurações de log de eventos] (../../media/Deploy-Azure-Monitor-2.png "Configurações de log de eventos")

> [!IMPORTANT]
> Definir configurações de Log de eventos do Windows e insira o **Sistema de sala Skype** como nome do log de eventos e, em seguida, marque as caixas de seleção de **erro**, **Aviso**e **informações** .

## <a name="configure-test-devices-for-azure-monitoring"></a>Configurar dispositivos de teste para o monitoramento do Azure
<a name="configure_test_devices"> </a>

Você precisará preparar a análise de Log para poder monitorar eventos relacionados ao Microsoft equipes salas. Iniciar com, você precisa implantar o Microsoft Monitoring agentes a apenas um ou dois dispositivos de salas de equipes da Microsoft que você tem acesso físico ao e obter os dispositivos de teste gerar alguns dados e push-lo no espaço de trabalho de análise de Log.

### <a name="install-microsoft-monitoring-agents-to-test-devices"></a>Instalar o Microsoft Monitoring agentes para dispositivos de teste

Implante o agente Microsoft Monitoring os dispositivos de teste usando as instruções fornecidas em [computadores com Windows se conectar ao serviço de Log de análise no Windows Azure](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows). Este artigo fornece informações detalhadas sobre as etapas de implantação do Microsoft Monitoring Agent para Windows, instruções para a obtenção a análise de Log de ***ID de espaço de trabalho*** e a ***chave primária*** para obter os dispositivos de salas de equipes da Microsoft conectados à sua implantação do Azure Monitor e etapas para verificar a conectividade do agente à instância de análise de Log.

### <a name="generate-sample-microsoft-teams-rooms-events"></a>Gerar eventos de salas de equipes da Microsoft de amostra

Depois que o agente Microsoft Monitoring é implantado nos dispositivos de teste, verifique se que os dados de log de eventos necessários são coletados pelo Monitor do Azure.

> [!NOTE]
> Reinicializar o dispositivo após a instalação do Microsoft Monitoring agent e certifique-se de que o aplicativo Microsoft equipes salas Meeting for iniciado, para que ele possa gerar novos eventos no Log de eventos.

1.  Entrar no [portal do Microsoft Azure](https://portal.azure.com) e vá para a análise de Log e selecione sua área de trabalho.

2.  Liste os eventos de pulsação gerados por um dispositivo de salas de equipes da Microsoft:
    1.  Selecione sua área de trabalho e vá para **Logs** e usar uma consulta para recuperar os registros de pulsação que terão os campos personalizados para salas de equipes da Microsoft.
    2.  Consulta de exemplo:`Event | where Source == "SRS-App" and EventID == 2000`

3.  Certifique-se de que a consulta retorna registros de log que incluem os eventos gerados pelo Microsoft equipes salas reuniões app.

4.  Gerar um problema de hardware e validar que os eventos necessários são registrados na análise de Log do Windows Azure.
    1.  Desconecte um dos dispositivos periféricos no teste do sistema de salas de equipes da Microsoft. Isso poderia ser a câmera, viva-voz, microfone ou exibição da sala de frente
    2.  Aguarde 10 minutos para que o log de eventos sejam preenchidos na análise de Log do Windows Azure.
    3.  Use uma consulta para listar eventos de erro de hardware:`Event | where Source == "SRS-App" and EventID == 3001`

5.  Gerar um problema de aplicativo e validar que os eventos necessários são registrados.
    1.  Modificar a configuração do aplicativo de salas de equipes da Microsoft e, em seguida, digite um par de endereço/senha incorreta do protocolo de iniciação de sessão (SIP).
    2.  Aguarde 10 minutos para que o log de eventos sejam preenchidos na análise de Log do Windows Azure.
    3.  Use uma consulta para listar eventos de erro do aplicativo:`Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> Esses logs de eventos de amostra são necessários antes de campos personalizados podem ser configurados. Não prossiga para a próxima etapa, até que você coletou os logs de evento necessários.

## <a name="map-custom-fields"></a>Mapear os campos personalizados
<a name="Custom_fields"> </a>

Você pode usar campos personalizados para extrair dados específicos de logs de eventos. Você precisará definir os campos personalizados que serão usados posteriormente com seu lado a lado, modos de exibição do painel e alertas. Consulte [campos personalizados na análise de Log](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields) e se familiarizar com os conceitos antes de começar a criar seus campos personalizados.

Para extrair seus campos personalizados sem os logs de eventos capturados, siga estas etapas:

1.  Entrar no [portal do Microsoft Azure](https://portal.azure.com) e vá para a análise de Log e selecione sua área de trabalho.

2. Liste os eventos gerados por um dispositivo de salas de equipes da Microsoft:
   1.  Vá para **Logs** e usar uma consulta para recuperar os registros que terão o campo personalizado.
   2.  Consulta de exemplo:`Event | where Source == "SRS-App" and EventID == 2000`

3. Selecione um dos registros, selecione o botão à esquerda e iniciar o Assistente de extração de campo.
4. Realce os dados que você deseja extrair o RenderedDescription e forneça o título de um campo. Os nomes de campo que você deve usar são fornecidos na tabela 1.

   ![Definição do campo personalizado] (../../media/Deploy-Azure-Monitor-4.png "Definição do campo personalizado")

5. Use os mapeamentos mostrados na *tabela 1*. Análise de log serão acrescentar automaticamente o ** \_CF** quando você definir o novo campo de cadeia de caracteres.

> [!IMPORTANT]
> Lembre-se de que todos os campos de análise de Log e JSON diferenciam maiusculas de minúsculas.
> 
> Preste atenção às consultas necessários para cada campo personalizado na tabela a seguir. Você precisa usar as consultas corretas para a análise de Log para extrair com sucesso os valores do campo personalizado.
> 
 ![Definição do campo personalizado] (../../media/Deploy-Azure-Monitor-5.png "Definição do campo personalizado")

**Tabela 1**

| **Campo JSON**                   | **Campo personalizado de análise de log** | **ID do evento** | **Consulta a ser usada com a extração**                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| Descrição                      | SRSEventDescription         | **2000**     | Evento \| onde de origem = = "SRS-App" e EventID = = 2000 |
| ResourceState                    | SRSResourceState            | **2000**     | Evento \| onde de origem = = "SRS-App" e EventID = = 2000 |
| OperationName                    | SRSOperationName            | **2000**     | Evento \| onde de origem = = "SRS-App" e EventID = = 2000 |
| OperationResult                  | SRSOperationResult          | **2000**     | Evento \| onde de origem = = "SRS-App" e EventID = = 2000 |
| Sistema operacional                               | SRSOSVersion                | **2000**     | Evento \| onde de origem = = "SRS-App" e EventID = = 2000 |
| Versão do sistema operacional                        | SRSOSLongVersion            | **2000**     | Evento \| onde de origem = = "SRS-App" e EventID = = 2000 |
| Alias                            | SRSAlias                    | **2000**     | Evento \| onde de origem = = "SRS-App" e EventID = = 2000 |
| DisplayName                      | SRSDisplayName              | **2000**     | Evento \| onde de origem = = "SRS-App" e EventID = = 2000 |
| AppVersion                       | SRSAppVersion               | **2000**     | Evento \| onde de origem = = "SRS-App" e EventID = = 2000 |
| IPv4Address                      | SRSIPv4Address              | **2000**     | Evento \| onde de origem = = "SRS-App" e EventID = = 2000 |
| IPv6Address                      | SRSIPv6Address              | **2000**     | Evento \| onde de origem = = "SRS-App" e EventID = = 2000 |
| Status do microfone de conferência     | SRSConfMicrophoneStatus     | **3001**     | Evento \| onde de origem = = "SRS-App" e EventID = = 3001 |
| Status de alto-falante de conferência        | SRSConfSpeakerStatus        | **3001**     | Evento \| onde de origem = = "SRS-App" e EventID = = 3001 |
| Status de alto-falante do padrão           | SRSDefaultSpeakerStatus     | **3001**     | Evento \| onde de origem = = "SRS-App" e EventID = = 3001 |
| Status da câmera                    | SRSCameraStatus             | **3001**     | Evento \| onde de origem = = "SRS-App" e EventID = = 3001 |
| Parte frontal da sala Exibir status     | SRSFORDStatus               | **3001**     | Evento \| onde de origem = = "SRS-App" e EventID = = 3001 |
| Status do Sensor de movimento             | SRSMotionSensorStatus       | **3001**     | Evento \| onde de origem = = "SRS-App" e EventID = = 3001 |
| Status da inclusão HDMI               | SRSHDMIIngestStatus         | **3001**     | Evento \| onde de origem = = "SRS-App" e EventID = = 3001 |


## <a name="define-the-microsoft-teams-rooms-views-in-log-analytics"></a>Definir os modos de exibição de salas de equipes da Microsoft na análise de Log
<a name="Define_Views"> </a>

Depois que os dados são coletados e campos personalizados são mapeados, você pode usar o Designer de modo de exibição para desenvolver um painel que contém vários blocos para monitorar eventos de salas de equipes da Microsoft. Use o Designer de modo de exibição para criar os seguintes blocos. Para obter mais informações, consulte [criar modos de exibição personalizados usando o Designer de modo de exibição na análise de Log](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> As etapas anteriores neste guia foram concluídas para os blocos de dashboard funcione corretamente.

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a>Criar um painel de salas de equipes da Microsoft usando o método de importação

Você pode importar um painel de salas de equipes da Microsoft e iniciar rapidamente seus dispositivos de monitoramento. Siga as etapas a seguir para importar o painel:

1.  Obtenha o arquivo de painel [SkypeRoomSystems_v2.omsview](https://go.microsoft.com/fwlink/?linkid=835675) .
2.  Entrar no [portal do Microsoft Azure](https://portal.azure.com) e vá para a análise de Log e selecione sua área de trabalho.
3.  Abra o **Designer de modo de exibição**.
4.  Selecione **Importar**e selecione o arquivo **SkypeRoomSystems_v2.omsview** .
5.  Selecione **Salvar**.

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>Criar um painel de salas de equipes da Microsoft manualmente

Como alternativa, você pode criar seu próprio painel e adicionar somente os blocos que você deseja monitorar.

#### <a name="configure-the-overview-tile"></a>Configurar os blocos de visão geral

1.  Abra o **Designer de modo de exibição**.
2.  Selecione **Os blocos de visão geral**e selecione **dois números** da Galeria.
3.  Nome de blocos de **Salas de equipes da Microsoft**.
4.  Defina o **primeira lado a lado**:<br>
    **Legenda:** Dispositivos que enviou uma pulsação pelo menos uma vez no último mês<br>
    **Consulta:**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  Defina o **segunda lado a lado**:<br>
    **Legenda:** Dispositivos ativos que enviou uma pulsação na última hora<br>
    **Consulta:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  Selecione **Aplicar**.

### <a name="create-a-tile-that-displays-active-devices"></a>Criar um lado que exibe os dispositivos ativos

1.  Selecione **Painel de exibição** para iniciar a adição de seu lado a lado.
2.  Selecione o **número & lista** da Galeria
3.  Defina as propriedades **gerais** :<br>
    **Título de grupo:** Pulsação Status<br>
    **Novo grupo:** Selecionado
4.  Defina as propriedades de **lado a lado** :<br>
    **Legenda:** Dispositivos ativos (pulsação enviada nos últimos 20 minutos)<br>
    **Consulta de bloco: ** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  Defina as propriedades de **lista** :<br>
    **Listar consulta:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  Defina **os títulos de coluna**:<br>
    **Nome:** Nome do computador<br>
    **Valor:** Pulsação última
7.  Defina a **consulta de navegação**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Selecione **Aplicar**e em seguida **Fechar**.

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>Criar um lado que exibe os dispositivos que têm problemas de conectividade

1.  Selecione o **número & lista** da galeria e, em seguida, adicionar um novo quadro.
2.  Defina as propriedades **gerais** :<br>
    **Título de grupo:** Deixe em branco<br>
    **Novo grupo:** Não selecionado
3.  Defina as propriedades de **lado a lado** :<br>
    **Legenda:** Dispositivos inativos (nenhuma mensagem pulsação enviada nos últimos 20 minutos)<br>
    **Consulta de bloco: ** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  Defina as propriedades de **lista** :<br>
    **Listar consulta:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  Defina **os títulos de coluna**:<br>
    **Nome:** Nome do computador<br>
    **Valor:** Pulsação última
6.  Defina a **consulta de navegação**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Selecione **Aplicar**e em seguida **Fechar**.

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>Criar um lado que exibe os dispositivos que têm um erro de hardware

1.  Selecione o **número & lista** da galeria e, em seguida, adicionar um novo quadro.
2.  Defina as propriedades **gerais** :<br>
    **Título de grupo:** Status de hardware<br>
    **Novo grupo:** Selecionado
3.  Defina as propriedades de **lado a lado** :<br>
    **Legenda:** Dispositivos que ocorreu um erro de hardware na última hora<br>
    **Consulta de bloco: ** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Defina as propriedades de **lista** :<br>
    **Listar consulta:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Defina **os títulos de coluna**:<br>
    **Nome:** Nome do computador<br>
    **Valor:** Último erro
6.  Defina a **consulta de navegação**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Selecione **Aplicar**e em seguida **Fechar**.

### <a name="create-a-tile-that-displays-microsoft-teams-rooms-operating-system-versions"></a>Criar um lado que exibe as versões de sistema operacional do Microsoft equipes salas

1.  Selecione a **lista de & de rosca** da galeria e, em seguida, adicionar um novo quadro.
2.  Defina as propriedades **gerais** :<br>
    **Título de grupo:** Detalhes do sistema operacional<br>
    **Novo grupo:** Selecionado
3.  Defina as propriedades de **cabeçalho** :<br>
    **Título:** Versões de sistema operacional<br>
    **Subtítulo:** Dispositivos que executam versões específicas do sistema operacional
4.  Defina as propriedades de **rosca** :<br>
    **Consulta:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **Centraliza o texto:** Dispositivos<br>
    **Operação:** Soma
5.  Defina as propriedades da **lista** .<br>
    **Listar consulta:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **Ocultar gráfico:** Selecionado<br>
    **Habilitar minigráficos:** Não selecionado
6.  Defina **os títulos de coluna**.<br>
    **Nome:** Nome do computador<br>
    **Valor:** Deixe em branco
7.  Defina a **consulta de navegação**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Selecione **Aplicar** e em seguida **Fechar**.

### <a name="create-a-tile-that-displays-microsoft-teams-rooms-application-versions"></a>Criar um lado que exibe as versões de aplicativo de salas de equipes da Microsoft

1.  Selecione a **lista de & de rosca** da galeria e, em seguida, adicionar um novo quadro.
2.  Defina as propriedades **gerais** :<br>
    **Título de grupo:** Detalhes do aplicativo de salas de equipes da Microsoft<br>
    **Novo grupo:** Selecionado
3.  Defina as propriedades de **cabeçalho** :<br>
    **Título:** Versões de aplicativo<br>
    **Subtítulo:** Dispositivos que executam versões de aplicativo específico
4.  Defina as propriedades de **rosca** :<br>
    **Consulta:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **Centraliza o texto:** Dispositivos<br>
    **Operação:** Soma
5.  Defina as propriedades da **lista** .<br>
    **Listar consulta:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **Ocultar gráfico:** Selecionado<br>
    **Habilitar minigráficos:** Não selecionado
6.  Defina **os títulos de coluna**.<br>
    **Nome:** Nome do computador<br>
    **Valor:** Deixe em branco
7.  Defina a **consulta de navegação**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Selecione **Aplicar** e em seguida **Fechar**.

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>Criar um lado que exibe os dispositivos que têm um erro de aplicativo

1.  Selecione o **número & lista** da galeria e, em seguida, adicionar um novo quadro.
2.  Defina as propriedades **gerais** .<br>
    **Título de grupo:** Deixe em branco<br>
    **Novo grupo:** Não selecionado
3.  Defina as propriedades de **lado a lado** .<br>
    **Legenda:** Dispositivos que houve um erro de aplicativo na última hora<br>
    **Consulta de bloco: ** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Defina as propriedades da **lista** .<br>
    **Listar consulta:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Defina **os títulos de coluna**.<br>
    **Nome:** Nome do computador<br>
    **Valor:** Último erro
6.  Defina a **consulta de navegação**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Selecione **Aplicar** e em seguida **Fechar**.

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>Criar um lado que exibe os dispositivos que tenham sido reiniciados

1.  Selecione o **número & lista** da galeria e, em seguida, adicionar um novo quadro.
2.  Defina as propriedades **gerais** .<br>
    **Título de grupo:** Deixe em branco<br>
    **Novo grupo:** Não selecionado
3.  Defina as propriedades de **lado a lado** .<br>
    **Legenda:** Onde o aplicativo foi reiniciado na última 24 horas e número de reinicializações de dispositivos<br>
    **Consulta de bloco: ** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  Defina as propriedades da **lista** .<br>
    **Listar consulta:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  Defina **os títulos de coluna**.<br>
    **Nome:** Nome do computador<br>
    **Valor:** Número de reinicializações
6.  Defina a **consulta de navegação**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Selecione **Aplicar** e em seguida **Fechar**.
8.  Selecione **Salvar** para salvar o seu painel.

Agora você concluiu a criação de seus modos de exibição.

## <a name="configure-alerts-in-azure-monitor"></a>Configurar alertas no Azure Monitor
<a name="Alerts"> </a>

Monitor Azure pode disparar alertas para notificar os administradores, quando um console do Microsoft equipes salas encontra um problema.

Monitor Azure inclui um mecanismo de alerta interno que é executado por meio de pesquisas de log agendada em intervalos regulares. Se os resultados da pesquisa log coincidir com alguns critérios específicos, um alerta registro é criado.

A regra pode executar automaticamente uma ou mais ações para notificá-lo do alerta proativamente ou invocar outro processo. As opções possíveis com os alertas são:
-   Enviar um email
-   Chamando um processo externo por meio de uma solicitação HTTP POST
-   Iniciando uma runbook no serviço de automação do Windows Azure

Consulte [registram alertas no Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log) para saber mais sobre os alertas do Monitor do Windows Azure.

> [!NOTE]
> Os exemplos a seguir enviam alertas de email quando um dispositivo Microsoft equipes salas gera um hardware ou um erro de aplicativo.

### <a name="configure-an-email-alert-for-microsoft-teams-rooms-hardware-issues"></a>Configurar um alerta de email para problemas de hardware de salas de equipes da Microsoft

Configure uma regra de alerta que verifica os dispositivos de salas de equipes da Microsoft que foram encontrados problemas de hardware na última hora.
1.  Entrar no [portal do Microsoft Azure](https://portal.azure.com) e vá para a análise de Log e selecione sua área de trabalho.

2. Navegue até seu espaço de trabalho de análise de Log e selecione **alertas** , selecione **nova regra de alerta**

3. Selecione **Adicionar condição** e, em seguida, **pesquisa de log personalizada**

4.  Insira a seguinte consulta para a caixa de texto de consulta de pesquisa.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  Configure as definições de alerta de lógica:<br>
    **Com base em:** Número de resultados<br>
    **Condição:** Em seguida, maior<br>
    **Limite:** 0<br>

6. Definir configurações de avaliação e selecione **concluído**: <br>
    **Período (em minutos):** 60<br>
    **Frequência (em minutos):** 60<br>

7. Configure grupos de ação:
    1.  Selecione **Criar novo**
    2.  Fornecer nomes adequados para os campos *nome do grupo de ação* e *Nome curto* .
    3.  Especifique um *Nome da ação* de exclusivo e selecione **Email/SMS/Push/voz**e selecione **Editar detalhes**.
    4.  Selecione a caixa de seleção de Email e forneça o endereço de email da pessoa ou grupo que receberá os alertas.
    5.  Você também pode fornecer o número do seu telefone para receber uma notificação com o SMS, uma chamada de voz ou ambos.
    6. Selecione **Okey**.

8. **Personalizar ações** se deseja substituir a linha de assunto de emails de alerta.

9. Especifique um nome da regra e uma descrição.<br>
    **Nome da regra:** Alertas de falha de Hardware de salas de equipes da Microsoft<br>
    **Descrição:** Lista de dispositivos que enfrentaram um problema de hardware na última hora<br>

10. Selecione a gravidade pretendida e certificar-se de que a regra está habilitada.

11. Selecione **Criar regra de alerta**.

### <a name="configure-an-email-alert-for-microsoft-teams-rooms-application-issues"></a>Configurar um alerta de email para problemas de aplicativos de salas de equipes da Microsoft

Repita o mesmo procedimento, mas usar a seguinte consulta à lista de dispositivos que foram encontrados problemas de aplicativo na última hora.

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

Agora você concluiu definindo alertas. É possível definir alertas adicionais usando os exemplos acima.

Quando um alerta é gerado, você receberá um email que lista os dispositivos que encontraram um problema na última hora.

![Email de alerta de amostra do Azure Monitor] (../../media/Deploy-Azure-Monitor-6.png "Email de alerta de amostra do Azure Monitor")

## <a name="configure-all-devices-for-azure-monitoring"></a>Configure todos os dispositivos para monitoramento do Azure
<a name="configure_all_devices"></a> Após os painéis e os alertas são configuradas, você pode configurar e configurar o Microsoft Monitoring agent em todos os dispositivos de salas de equipes da Microsoft para concluir sua implantação de monitoramento.

Embora você possa instalar e configurar o agente Microsoft Monitoring manualmente em cada dispositivo, é altamente recomendável que você aproveitar os métodos e as ferramentas de implantação de software existente.

Se você estiver criando seus dispositivos de salas de equipes da Microsoft pela primeira vez, convém incluir as etapas de instalação e configuração de agente Monitoring Microsoft como parte do seu processo de criação. Para obter mais informações, consulte [instalar o agente usando a linha de comando](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).

### <a name="deploying-microsoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>Implantando o Microsoft Monitoring agent usando-se um objeto de diretiva de grupo (GPO)

Se você já implantou os dispositivos de salas de equipes da Microsoft antes de implementar o monitoramento do Azure, você pode usar o script fornecido para instalar e configurar os agentes usando objetos de diretiva de grupo do Active Directory.

1.  Criar um caminho de rede compartilhado e conceder acesso de leitura ao grupo de **Computadores de domínio** .

2.  Baixe a versão de 64 bits do Microsoft Monitoring Agent for Windows de<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  Extraia o conteúdo do pacote de instalação em compartilhamento de rede.
    1.  Abra uma janela de Prompt de comando e, em seguida, executar **MMASetup-AMD64.exe /c**
    2.  Especifique o compartilhamento que você acabou de criar e extrair o conteúdo.

4.  Criar um novo objeto de diretiva de grupo e atribuí-lo à unidade organizacional em que as contas de máquina de salas de equipes da Microsoft estão localizadas.

5.  Configure a diretiva de execução do PowerShell:
    1.  Edite o objeto de diretiva de grupo recém-criado e navegue até configuração do computador \\ políticas \\ modelos administrativos \\ componentes do Windows \\ do Windows PowerShell
    2.  Habilite o **ativem a execução do Script** e definir **A diretiva de execução** para **Permitir Scripts locais**.

6.  Configure o script de inicialização:
    1.  Copie o script a seguir e salve-o como Install-MMAgent.ps1.
    2.  Modifica os parâmetros WorkspaceId, WorkspaceKey e SetupPath para coincidir com sua configuração.
    3.  Editar o mesmo objeto de diretiva de grupo e navegue até configuração do computador \\ políticas \\ configurações do Windows \\ Scripts (inicialização/encerramento)
    4.  Clique duas vezes para selecionar a **inicialização**e selecione **Scripts do PowerShell**.
    5.  Selecione **Mostrar arquivos**e copie o arquivo **Install-MMAgent.ps1** dessa pasta.
    6.  Selecione **Adicionar**e, em seguida, **Navegue**.
    7.  Selecione o script ps1 que você acabou de copiar.

7.  Dispositivos de salas de equipes da Microsoft devem instalar e configurar o agente Monitoring Microsoft com a segunda reinicialização.

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
> Você pode consultar o artigo [Gerenciando e mantendo o agente de análise de Log](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage) quando você precisar reconfigurar um operador, movê-la para outro espaço de trabalho ou modificar as configurações de proxy após a instalação inicial.

## <a name="additional-solutions"></a>Soluções adicionais
<a name="Solutions"> </a>

Monitor Azure oferece soluções de gerenciamento internas por meio de sua [Galeria de soluções](https://docs.microsoft.com/azure/azure-monitor/insights/solutions) para ajudar ainda mais a monitorar o ambiente. É altamente recomendável que você adicione soluções de [Gerenciamento de alerta](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution) e [Integridade do agente de análise do Azure Log](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth) para seu espaço de trabalho.

> [!NOTE]
> A solução de integridade do agente pode ajudá-lo a identificar os agentes de Microsoft Monitoring desatualizados ou quebrados dentro do seu ambiente e a solução de gerenciamento de alerta fornece detalhes sobre os alertas que foram gerados em um determinado período.

## <a name="see-also"></a>Confira também

[Planejar o gerenciamento de salas de equipes da Microsoft com o Monitor do Azure](../../plan-your-deployment/clients-and-devices/azure-monitor.md)

[Gerencia dispositivos de salas de equipes da Microsoft com Monitor do Azure](../../manage/skype-room-systems-v2/azure-monitor.md)