---
title: Implantar o gerenciamento do Skype Room Systems v2 com OMS
ms.author: jambirk
author: Turgayo
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: Este artigo discute como implantar o gerenciamento de sistemas de sala Skype v2 dispositivos de forma integrada e de ponta a ponta, usando o pacote de gerenciamento de operações do Microsoft.
ms.openlocfilehash: 4e52c416f9f35aaee1ccb3b5e8c75c29246a1c5d
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2018
ms.locfileid: "23891245"
---
# <a name="deploy-skype-room-systems-v2-management-with-oms"></a>Implantar o gerenciamento do Skype Room Systems v2 com OMS

Este artigo discute como configurar e implantar o gerenciamento integrado de ponta a ponta de dispositivos do Skype sala sistemas v2 usando o pacote de gerenciamento de operações do Microsoft.

Você pode configurar o Microsoft Operations Management Suite para fornecer Telemetria básica e alertas que ajudarão você a gerenciar Skype dispositivos de sala de reunião. Como sua solução de gerenciamento for envelhecendo, talvez você decida implantar recursos de gerenciamento para criar uma visão mais detalhada de desempenho e disponibilidade de dispositivo e dados adicionais.

Seguindo este guia, você pode usar um painel semelhante ao seguinte exemplo para obter o status detalhado de relatórios para disponibilidade de dispositivo, aplicativo e integridade de hardware e a distribuição de versão de aplicativo do Skype sala sistemas v2.

![Modo de exibição de amostra OMS para v2 SRS] (../../media/Deploy_OMS_1.png "Modo de exibição de amostra OMS para v2 SRS")

Em um nível superior, é necessário executar as seguintes tarefas:


1.  [Validar a configuração do pacote de gerenciamento de operações](with-oms.md#validate_OMS)
2.  [Configurar dispositivos de teste de configuração de gerenciamento do pacote de gerenciamento de operações](with-oms.md#configure_test_devices)
3.  [Mapear os campos personalizados](with-oms.md#Custom_fields)
4.  [Definir os modos de exibição do Skype sala sistemas v2 no pacote de gerenciamento de operações](with-oms.md#Define_Views)
5.  [Definir alertas](with-oms.md#Alerts)
6.  [Configurar todos os dispositivos para o pacote de gerenciamento de operações](with-oms.md#configure_all_devices)
7.  [Configurar soluções adicionais do pacote de gerenciamento de operações](with-oms.md#Solutions)

> [!IMPORTANT]
> Embora com a configuração mínima, o pacote de gerenciamento de operações pode monitorar a um computador que executa um sistema operacional Windows, ainda há algumas etapas v2 específica Skype sala sistemas que precisam ser executadas antes de começar a implantar agentes para todas as salas do Skype Dispositivos de sistemas.
> Portanto, é altamente recomendável que executar todas as etapas de configuração na ordem correta para um controlado de instalação e configuração. A qualidade do resultado final depende muito a qualidade da configuração inicial.

## <a name="validate-operations-management-suite-configuration"></a>Validar a configuração do pacote de gerenciamento de operações
<a name="validate_OMS"> </a>

Você precisa ter um espaço de trabalho do pacote de gerenciamento de operações para iniciar a coleta de logs de dispositivos do Skype sala sistemas v2. Um espaço de trabalho é um ambiente de análise de Log exclusivo com seu próprio repositório de dados, fontes de dados e soluções. Se você já tiver um espaço de trabalho de análise de Log existente, você pode usá-lo para monitorar sua implantação do Skype sala sistemas v2 ou você pode criar um dedicado Log Analytics espaço de trabalho específico para o monitoramento de sistemas de sala Skype v2 precisa.

Se você precisar criar um novo espaço de trabalho de análise de Log, siga as instruções no artigo [criar um espaço de trabalho de análise de Log no portal do Azure](https://docs.microsoft.com/azure/log-analytics/log-analytics-quick-create-workspace)

> [!NOTE]
> Para usar a análise de Log com pacote de gerenciamento de operações, você precisa ter uma assinatura do Azure active. Se você não tiver uma assinatura do Windows Azure, você pode criar [uma assinatura de avaliação gratuita](https://azure.microsoft.com/free) como ponto de partida.


### <a name="configure-operations-management-suite-to-collect-skype-room-systems-v2-event-logs"></a>Configurar o pacote de gerenciamento de operações para coletar logs de eventos do Skype sala sistemas v2

Análise de log coleta somente eventos de logs de eventos do Windows que são especificados nas configurações do. Para cada log, somente os eventos a severidades selecionadas são coletados.

Você precisará configurar o pacote de gerenciamento de operações para coletar os logs necessários para monitorar o status de dispositivo e aplicativo v2 Skype sistemas de sala. Dispositivos de v2 de sistemas de sala Skype usam o log de eventos do **Sistema do Skype sala** .

Para configurar o pacote de gerenciamento de operações para coletar os eventos de sistemas de sala Skype v2, consulte [fontes de dados de log de eventos do Windows na análise de Log](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)

![Configurações de log de eventos] (../../media/Deploy_OMS_2.png "Configurações de log de eventos")


> [!IMPORTANT]
> Selecione o log de eventos do **Sistema do Skype sala** e marque as caixas de seleção de **erro**, **Aviso**e **informações** .

## <a name="configure-test-devices-for-operations-management-suite-setup"></a>Configurar dispositivos de teste para a instalação do pacote de gerenciamento de operações
<a name="configure_test_devices"> </a>

É necessário preparar o pacote de gerenciamento de operações para poder monitorar eventos relacionados ao v2 de sistemas de sala do Skype. Para começar com, você precisa implantar agentes do pacote de gerenciamento de operações para apenas um ou dois sistemas de sala Skype v2 os dispositivos que possuem acesso físico ao e têm os dispositivos de teste gerar alguns dados e push-lo no espaço de trabalho de análise de Log.

### <a name="install-operations-management-suite-agents-to-test-devices"></a>Instale os agentes de pacote de gerenciamento de operações para dispositivos de teste

Implante o agente do pacote de gerenciamento de operações para os dispositivos de teste usando as instruções fornecidas em [computadores com Windows se conectar ao serviço de Log de análise no Windows Azure](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-windows). Este artigo oferece informações detalhadas sobre as etapas de implantação do Microsoft Monitoring Agent para Windows, instruções para obter a *ID do espaço de trabalho* do pacote de gerenciamento de operações e a *chave primária* para obter os dispositivos de v2 de sistemas de sala do Skype conectado à sua implantação do pacote de gerenciamento de operações e etapas para verificar a conectividade do agente para análise de Log.

### <a name="generate-sample-skype-room-systems-events"></a>Gerar eventos de sistemas de sala Skype de amostra

Depois que o agente do pacote de gerenciamento de operações é implantado nos dispositivos de teste, verifique se que os dados de log de eventos necessários são coletados pela análise de Log.

1.  Entrar no [portal do pacote de gerenciamento de operações do Microsoft](https://aka.ms/omsportal).

2.  Liste os eventos gerados por um dispositivo do Skype sala sistemas v2:
    1.  Vá para a **Pesquisa de Log** e usar uma consulta para recuperar os registros que terão o campo personalizado.
    2.  Consulta de exemplo:`Event | where Source == "SRS-App"`

3.  Certifique-se de que a consulta retorna registros de log que incluam eventos pulsação bem-sucedida.

4.  Gerar um problema de hardware e validar que os eventos necessários são registrados no pacote de gerenciamento de operações.
    1.  Desconecte um dos dispositivos periféricos no teste do sistema do Skype sala sistemas v2. Isso poderia ser a câmera, viva-voz, microfone ou exibição da sala de frente
    2.  Aguarde 10 minutos para que o log de eventos a serem preenchidos no pacote de gerenciamento de operações.
    3.  Use uma consulta para listar eventos de erro de hardware:`Event | where EventID == 3001`

5.  Gerar um problema de aplicativo e validar que os eventos necessários são registrados.
    1.  Modificar a configuração de aplicativo do Skype sala sistemas v2 e digite um par de endereço/senha incorreta do protocolo de iniciação de sessão (SIP).
    2.  Aguarde 10 minutos para que o log de eventos a serem preenchidos no pacote de gerenciamento de operações.
    3.  Use uma consulta para listar eventos de erro do aplicativo:`Event | where EventID == 2001`

> [!IMPORTANT]
> Esses logs de eventos de amostra são necessários antes de campos personalizados podem ser configurados. Não prossiga para a próxima etapa, até que você coletou os logs de evento necessários.

## <a name="map-custom-fields"></a>Mapear os campos personalizados
<a name="Custom_fields"> </a>

Você pode usar campos personalizados para extrair dados específicos de logs de eventos. Você precisará definir os campos personalizados que serão usados posteriormente com seu lado a lado, modos de exibição do painel e alertas. Consulte [campos personalizados na análise de Log](https://docs.microsoft.com/azure/log-analytics/log-analytics-custom-fields) e se familiarizar com os conceitos antes de começar a criar seus campos personalizados.

Para extrair seus campos personalizados sem os logs de eventos capturados, siga estas etapas:

1.  Entrar no [portal do pacote de gerenciamento de operações do Microsoft](https://aka.ms/omsportal).

2.  Liste os eventos gerados por um dispositivo do Skype sala sistemas v2:
    1.  Vá para a **Pesquisa de Log** e usar uma consulta para recuperar os registros que terão o campo personalizado.
    2.  Consulta de exemplo:`Event | where Source == "SRS-App"`

3.  Selecione um dos registros, selecione o botão à esquerda e iniciar o Assistente de extração de campo.

   ![Assistente de extração de campo] (../../media/Deploy_OMS_3.png "Assistente de extração de campo")

4.  Realce os dados que você deseja extrair o RenderedDescription e forneça o título de um campo. Os nomes de campo que você deve usar são fornecidos na tabela 1.

   ![Definição do campo personalizado] (../../media/Deploy_OMS_4.png "Definição do campo personalizado")

5.  Use os mapeamentos mostrados na *tabela 1*. Pacote de gerenciamento de operações adicionará automaticamente o ** \_CF** quando você definir o novo campo de cadeia de caracteres.

> [!IMPORTANT]
> Lembre-se de que todos os campos JSON e o pacote de gerenciamento de operações diferenciam maiusculas de minúsculas.

> Preste atenção ao estado da caixa de seleção EventID na tabela a seguir. Certifique-se de que você confirme o estado dessa caixa de seleção para o pacote de gerenciamento de operações extrair com êxito os valores de campo personalizado.
>
> ![Definição do campo personalizado] (../../media/Deploy_OMS_5.png "Definição do campo personalizado")

**Tabela 1**

| Campo JSON                   | Campo personalizado OMS           | ID do evento        |
|:-----------------------------|:---------------------------|:----------------|
| Descrição                  | SRSEventDescription_CF     | Não selecionado    |
| ResourceState                | SRSResourceState_CF        | Não selecionado    |
| Nomedaoperação                | SRSOperationName_CF        | Não selecionado    |
| OperationResult              | SRSOperationResult_CF      | Não selecionado    |
| Sistema operacional                           | SRSOSVersion_CF            | Não selecionado    |
| Versão do sistema operacional                    | SRSOSLongVersion_CF        | Não selecionado    |
| Alias                        | SRSAlias_CF                | Não selecionado    |
| DisplayName                  | SRSDisplayName_CF          | Não selecionado    |
| AppVersion                   | SRSAppVersion_CF           | Não selecionado    |
| IPv4Address                  | SRSIPv4Address_CF          | Não selecionado    |
| IPv6Address                  | SRSIPv6Address_CF          | Não selecionado    |
| Parte frontal da sala Exibir status | SRSFORDStatus_CF           | 3001            |
| Status da câmera                | SRSCameraStatus_CF         | 3001            |
| Status do microfone de conferência | SRSConfMicrophoneStatus_CF | 3001            |
| Status de alto-falante de conferência    | SRSConfSpeakerStatus_CF    | 3001            |
| Status de alto-falante do padrão       | SRSDefaultSpeakerStatus_CF | 3001            |
| Status do Sensor de movimento         | SRSMotionSensorStatus_CF   | 3001            |
| Status da inclusão HDMI           | SRSHDMIIngestStatus_CF     | 3001            |


## <a name="define-the-skype-room-systems-v2-views-in-operations-management-suite"></a>Definir os modos de exibição do Skype sala sistemas v2 no pacote de gerenciamento de operações
<a name="Define_Views"> </a>

Depois que os dados são coletados e campos personalizados são mapeados, você pode usar o Designer de modo de exibição do pacote de gerenciamento de operações para desenvolver um painel que contém vários blocos para monitorar sistemas de sala Skype v2 eventos. Use o Designer de Exibição para criar os blocos a seguir. Para obter mais informações, consulte [Use o Designer de modo de exibição para criar exibições personalizadas na análise de Log](https://docs.microsoft.com/azure/log-analytics/log-analytics-view-designer)

> [!NOTE]
> As etapas anteriores neste guia foram concluídas para os blocos de dashboard funcione corretamente.


### <a name="create-a-skype-room-systems-v2-dashboard-by-using-the-import-method"></a>Criar um painel de v2 de sistemas de sala Skype usando o método de importação

Você pode importar um painel do pacote de gerenciamento de operações e iniciar o monitoring seus dispositivos imediatamente. Siga as etapas a seguir para importar o painel:

1.  Obtenha o arquivo de painel [SkypeRoomSystems_v2.omsview](https://download.microsoft.com/download/9/0/D/90D4826A-9FD2-47D2-B911-97BF1737F4F7/SkypeRoomSystems_v2.omsview) .
2.  Entrar no [portal do pacote de gerenciamento de operações do Microsoft](https://aka.ms/omsportal).
3.  Abra o **Designer de modo de exibição**.
4.  Selecione **Importar**e selecione o arquivo **SkypeRoomSystems_v2.omsview** .
5.  Selecione **Salvar**.

### <a name="create-a-skype-room-systems-v2-dashboard-manually"></a>Criar um painel de v2 de sistemas de sala Skype manualmente

Como alternativa, você pode criar seu próprio painel e adicionar somente os blocos que você deseja monitorar.

#### <a name="configure-the-overview-tile"></a>Configurar os blocos de visão geral
1.  Abra o **Designer de modo de exibição**.
2.  Selecione **Os blocos de visão geral**e selecione **dois números** da Galeria.
3.  Nomeie a **sistemas de sala Skype v2**lado a lado.
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
    **Nome:** Nome para exibição<br>
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
    **Nome:** Nome para exibição<br>
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
    **Legenda:** Dispositivos que ocorreu um erro de hardware na última hora <br>
    **Consulta de bloco: ** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Defina as propriedades de **lista** :<br>
    **Listar consulta:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer```
5.  Defina **os títulos de coluna**:<br>
    **Nome:** Nome para exibição<br>
    **Valor:** Último erro
6.  Defina a **consulta de navegação**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Selecione **Aplicar**e em seguida **Fechar**.

### <a name="create-a-tile-that-displays-skype-room-systems-v2-operating-system-versions"></a>Criar um lado que exibe as versões de sistema operacional v2 de sistemas de sala do Skype

1.  Selecione **rosca & lista** da galeria e, em seguida, adicionar um novo quadro.
2.  Defina as propriedades **gerais** :<br>
    **Título de grupo:** Detalhes do sistema operacionais <br>
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
    **Nome:** Nome para exibição<br>
    **Valor:** Deixe em branco
7.  Defina a **consulta de navegação**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Selecione **Aplicar** e em seguida **Fechar**.

### <a name="create-a-tile-that-displays-skype-room-systems-v2-application-versions"></a>Criar um lado que exibe as versões de aplicativo v2 de sistemas de sala do Skype

1.  Selecione **rosca & lista** da galeria e, em seguida, adicionar um novo quadro.
2.  Defina as propriedades **gerais** :<br>
    **Título de grupo:** Detalhes do aplicativo de v2 de sistemas de sala do Skype <br>
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
    **Nome:** Nome para exibição<br>
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
    **Nome:** Nome para exibição<br>
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
    **Nome:** Nome para exibição<br>
    **Valor:** Número de reinicializações
6.  Defina a **consulta de navegação**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Selecione **Aplicar** e em seguida **Fechar**.
8.  Selecione **Salvar** para salvar o seu painel.

Agora você concluiu a criação de seus modos de exibição.

Você pode usar o portal do pacote de gerenciamento de operações do Microsoft ou clientes móveis do pacote de gerenciamento de operações para [Windows Phone](https://www.microsoft.com/en-us/store/p/microsoft-operations-management-suite/9wzdncrfjz2r), [iOS](https://itunes.apple.com/us/app/microsoft-operations-management-suite/id1042424859)ou [Android](https://play.google.com/store/apps/details?id=com.microsoft.operations.AndroidPhone) para acessar seus modos de exibição.

## <a name="configure-alerts-in-operations-management-suite"></a>Configurar alertas no pacote de gerenciamento de operações
<a name="Alerts"></a> Dispositivo de v2 quando um Skype sala sistemas encontra um problema, o pacote de gerenciamento de operações do Microsoft pode gerar alertas para notificar os administradores com os detalhes do problema.

Pacote de gerenciamento de operações inclui um mecanismo de alerta interno que é executado por meio de pesquisas de log agendada em intervalos regulares. Se os resultados da pesquisa log coincidir com alguns critérios específicos, um alerta registro é criado.

![Mecanismo de alerta OMS] (../../media/Deploy_OMS_6.png "Mecanismo de alerta OMS")

A regra pode executar automaticamente uma ou mais ações para notificá-lo do alerta proativamente ou invocar outro processo. As opções possíveis com alertas do pacote de gerenciamento de operações são:
-   Enviar um email
-   Chamando um processo externo por meio de uma solicitação HTTP POST
-   Iniciando uma runbook no serviço de automação do Windows Azure

Consulte [compreensão dos alertas na análise de Log](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts) para saber mais sobre os alertas do pacote de gerenciamento de operações.

> [!NOTE]
> Os exemplos a seguir enviam alertas de email quando um dispositivo de sistemas de sala Skype v2 gera um hardware ou um erro de aplicativo.


### <a name="configure-an-email-alert-for-skype-room-systems-v2-hardware-issues"></a>Configurar um alerta de email para problemas de hardware do Skype sala sistemas v2

Configure uma regra de alerta que verifica os sistemas de sala Skype v2 dispositivos que tiveram problemas de hardware na última hora.
1.  Entrar no [portal do pacote de gerenciamento de operações do Microsoft](https://aka.ms/omsportal).

2.  Selecione a **pesquisa de Log**.

3.  Insira a seguinte consulta e selecione **Executar**.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

4.  Depois que a consulta é executada, selecione **alerta**. Esse procedimento abrirá a página **Adicionar regra de alerta** .

5.  Definir configurações de alerta usando as informações a seguir:<br>
    **Nome da regra:** Alertas de falha de Hardware do Skype sala sistemas v2<br>
    **Descrição:** Lista de dispositivos que enfrentaram um problema de hardware na última hora<br>
    **Gravidade:** Crítico<br>
    **Consulta:** Usar a consulta de pesquisa preenchidos<br>
    **Janela de tempo:** 1 hora<br>
    **Frequência de alerta:** 1 hora<br>
    **Número de resultados:** Maior do que 0<br>
    **Assunto de email:** Alertas de falha de Hardware do Skype sala sistemas v2<br>
    **Destinatários:** Incluir os endereços de email, vírgula como separadores<br>

6.  Selecione **Salvar**.

### <a name="configure-an-email-alert-for-skype-room-systems-v2-application-issues"></a>Configurar um alerta de email para problemas de aplicativo v2 de sistemas de sala do Skype

Configure uma regra de alerta, que procura Skype sala sistemas v2 dispositivos que tiveram problemas de aplicativo na última hora.
1.  Selecione a **pesquisa de Log**.

2.  Insira a seguinte consulta e selecione **Executar**.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(10h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

3.  Depois que a consulta é executada, selecione **alerta**. Esse procedimento abrirá a página **Adicionar regra de alerta** .

4.  Definir configurações de alerta usando as informações a seguir:<br>
    **Nome da regra:** Alerta de falha de aplicativo do Skype sala sistemas v2<br>
    **Descrição:** Lista de dispositivos que enfrentaram um problema de aplicativo na última hora<br>
    **Gravidade:** Crítico<br>
    **Consulta:** Usar a consulta de pesquisa preenchidos<br>
    **Janela de tempo:** 1 hora<br>
    **Frequência de alerta:** 1 hora<br>
    **Número de resultados:** Maior do que 0<br>
    **Assunto de email:** Alerta de falha de aplicativo do Skype sala sistemas v2<br>
    **Destinatários:** Incluir os endereços de email, vírgula como separadores

5.  Selecione **Salvar**.

Agora você concluiu definindo alertas. É possível definir alertas adicionais usando os exemplos acima.

Quando um alerta é gerado, você receberá um email que lista os dispositivos que encontraram um problema na última hora.

![Email de alerta de amostra OMS] (../../media/Deploy_OMS_7.png "Email de alerta de amostra OMS")

Você pode usar uma página de configurações de alerta para modificar uma configuração existente de alerta, ou para desabilitar ou remover um alerta.

![Configurações de alerta OMS] (../../media/Deploy_OMS_8.png "Configurações de alerta OMS")

> [!NOTE]
> Você pode precisar usar o portal do Windows Azure para adicionar ou modificar os alertas do pacote de gerenciamento de operações se seu espaço de trabalho do pacote de gerenciamento de operações estiver configurado para estender os alertas do pacote de gerenciamento de operações no Windows Azure. Para obter mais detalhes, consulte [Extend alertas do portal OMS no Windows Azure](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-alerts-extend).

## <a name="configure-all-devices-for-operations-management-suite"></a>Configurar todos os dispositivos para o pacote de gerenciamento de operações
<a name="configure_all_devices"></a> Após os painéis e os alertas são configuradas, você pode configurar e configurar agentes de pacote de gerenciamento de operações em todos os dispositivos de sistemas de sala Skype v2 para concluir sua implantação de monitoramento.

Embora você possa instalar e configurar os agentes de pacote de gerenciamento de operações manualmente em cada dispositivo, é altamente recomendável que você aproveitar os métodos e as ferramentas de implantação de software existente.

Se você estiver criando seus dispositivos de sistemas de sala Skype v2 pela primeira vez, convém incluir as etapas de instalação e configuração de agente do pacote de gerenciamento de operações como parte do processo de compilação. Para obter mais informações, consulte [instalar o agente usando a linha de comando](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-windows#install-the-agent-using-the-command-line).

### <a name="deploying-operations-management-suite-agents-by-using-a-group-policy-object"></a>Implantação de agentes de pacote de gerenciamento de operações por meio de um objeto de diretiva de grupo

Se você já implantou os dispositivos do Skype sala sistemas v2 antes de implementar o pacote de gerenciamento de operações, você pode usar o script fornecido para instalar e configurar os agentes usando diretivas de grupo do Active Directory.

1.  Criar um caminho de rede compartilhado e conceder acesso de leitura ao grupo de **Computadores de domínio** .

2.  Baixe a versão de 64 bits do Operations Management Suite agente for Windows de<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  Extraia o conteúdo do pacote de instalação em compartilhamento de rede.
    1.  Abra uma janela de Prompt de comando e, em seguida, executar **MMASetup-AMD64.exe /c**
    2.  Especifique o compartilhamento que você acabou de criar e extrair o conteúdo.

4.  Criar um novo objeto de diretiva de grupo e atribuí-lo à unidade organizacional onde as contas de máquina do Skype sala sistemas v2 estão localizadas.

5.  Configure a diretiva de execução do PowerShell:
    1.  Edite o objeto de diretiva de grupo recém-criado e navegue até configuração do computador \\ políticas \\ modelos administrativos \\ componentes do Windows \\ do Windows PowerShell
    2.  Habilite o **ativem a execução do Script** e definir **A diretiva de execução** para **Permitir Scripts locais**.

6.  Configure o script de inicialização:
    1.  Copie o script a seguir e salve-o como Install-OMSAgent.ps1.
    2.  Modifica os parâmetros WorkspaceId, WorkspaceKey e SetupPath para coincidir com sua configuração.
    3.  Editar o mesmo objeto de diretiva de grupo e navegue até configuração do computador \\ políticas \\ configurações do Windows \\ Scripts (inicialização/encerramento)
    4.  Clique duas vezes para selecionar a **inicialização**e selecione **Scripts do PowerShell**.
    5.  Selecione **Mostrar arquivos**e copie o arquivo **Install-OMSAgent.ps1** dessa pasta.
    6.  Selecione **Adicionar**e, em seguida, **Navegue**.
    7.  Selecione o script ps1 que você acabou de copiar.

7.  Dispositivos de v2 de sistemas de sala do Skype devem instalar e configurar o agente Monitoring Microsoft com a segunda reinicialização.


    ```
    # Install-OMSAgent.ps1
    <#
    Date:        04/20/2018
    Script:      Install-OMSAgent.ps1
    Version:     1.0
    #>

    # Set the parameters
    $WorkspaceId = "<your workspace id>"
    $WorkspaceKey = "<your workspace key>"
    $SetupPath = "\\Server\Share"

    $SetupParameters = "/qn NOAPM=1 ADD_OPINSIGHTS_WORKSPACE=1 OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE=0 OPINSIGHTS_WORKSPACE_ID=$WorkspaceId OPINSIGHTS_WORKSPACE_KEY=$WorkspaceKey AcceptEndUserLicenseAgreement=1"

    # $SetupParameters = $SetupParameters + " OPINSIGHTS_PROXY_URL=<Proxy server URL> OPINSIGHTS_PROXY_USERNAME=<Proxy server username> OPINSIGHTS_PROXY_PASSWORD=<Proxy server password>"

    # Start PowerShell logging
    Start-Transcript -Path C:\OMSAgentInstall.Log

    # Check if the Microsoft Monitoring Agent is installed
    $mma = New-Object -ComObject 'AgentConfigManager.MgmtSvcCfg'

    # Check if the Microsoft Monitoring agent is installed
    if (!$mma)
    {
        #Install agent
        Start-Process -FilePath "$SetupPath\Setup.exe" -ArgumentList $SetupParameters -ErrorAction Stop -Wait
    }

    # Check if the agent has a valid configuration
    $CheckOMS = $mma.GetCloudWorkspace($WorkspaceId).AgentId
    if (!$CheckOMS)
    {
        # Apply new configuration
        $mma.AddCloudWorkspace($WorkspaceId, $WorkspaceKey)
        $mma.ReloadConfiguration()
    }

    Stop-Transcript

    ```

> [!NOTE]
> Você pode consultar o artigo [Gerenciando e mantendo o agente de análise de Log](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-manage) quando você precisar reconfigurar um operador, movê-la para outro espaço de trabalho ou modificar as configurações de proxy após a instalação inicial.

## <a name="additional-solutions"></a>Soluções adicionais
<a name="Solutions"> </a>

Pacote de gerenciamento de operações oferece soluções internas com sua [Galeria de soluções](https://docs.microsoft.com/azure/log-analytics/log-analytics-add-solutions) para ajudar ainda mais a monitorar o ambiente. É altamente recomendável que você adicione soluções de [Gerenciamento de alerta](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management) e [Integridade do agente do](https://docs.microsoft.com/azure/operations-management-suite/oms-solution-agenthealth) seu espaço de trabalho pacote de gerenciamento de operações.

![Modos de exibição OMS] (../../media/Deploy_OMS_9.png "Modos de exibição OMS")

> [!NOTE]
> A solução de integridade do agente pode ajudá-lo a identificar os agentes de pacote de gerenciamento de operações desatualizados ou quebrados dentro do seu ambiente e a solução de gerenciamento de alerta fornece detalhes sobre os alertas que foram gerados em um determinado período.

## <a name="see-also"></a>Consulte também

[Planejar o gerenciamento do Skype Room Systems versão 2 com o OMS](../../plan-your-deployment/clients-and-devices/oms-management.md)

[Gerenciar dispositivos do Skype Room Systems v2 com o OMS](../../manage/skype-room-systems-v2/oms.md)
