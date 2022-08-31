---
title: Dados necessários de diagnóstico de cliente da área de trabalho do Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: majaisin
description: Uma lista de eventos e propriedades da área de trabalho para os controles de política do Microsoft Teams.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5bb9e4dfd604728ea1714d3ab2e663dab3b5c3c6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58608918"
---
# <a name="required-desktop-diagnostic-data-for-microsoft-teams"></a>Dados necessários de diagnóstico da área de trabalho para o Microsoft Teams

O artigo a seguir contém uma lista de eventos da área de trabalho do Microsoft Teams e listas de propriedades que cada evento coleta.

Para saber mais sobre dados de diagnóstico, incluindo como controlar quais dados de diagnóstico são enviados à Microsoft, consulte [Dados de diagnóstico enviados do aplicativo Teams para o Microsoft](policy-control-overview.md#diagnostic-data-sent-from-the-teams-app-to-microsoft). Para exibir os dados de diagnóstico que estão sendo enviados à Microsoft, você pode usar o [Visualizador de Dados de Diagnóstico](https://support.microsoft.com/topic/cf761ce9-d805-4c60-a339-4e07f3182855).

## <a name="events"></a>Eventos

> [!NOTE]
> Existem propriedades comuns para todos os eventos listados abaixo, para revisá-los, consulte [Propriedades enviadas com todos os eventos](#properties-sent-with-all-events).

### <a name="logging"></a>Registro em log

> [!NOTE]
> Para obter informações sobre as propriedades de Registro em log, consulte [Propriedades enviadas com os eventos de Registro em log](#properties-sent-with-logging-events).

- **adal-anonymous-mac.ts:this.logger.logError** - Registra que ocorreu um erro genérico de SSO ao fazer logon anonimamente em um dispositivo Mac.
- **adalAnonymousUtil.ts:loggingService.getInstance** - Registra instrução de erro que o aplicativo não conseguiu iniciar a autenticação de usuário anônimo.
- **adal-anonymous-windows.ts:this.logger.logError** - Registra que um erro genérico de SSO ocorreu ao fazer logon anonimamente em um dispositivo Windows.
- **adalBase.ts:this.loggingService.logError** - Registra informações necessárias para determinar se o perfil de usuário é nulo ou vazio.
- **adal-impl-mac.ts:this.loggingService.logError** - Registra a ocorrência de um problema durante a análise de telemetria recebida durante a autenticação ou erro genérico de SSO durante o logon em um dispositivo Mac.
- **adal-rigel-windows.ts:this.logger.logError** - Instrução de registro em log geral indicando um erro genérico de SSO que ocorreu ao entrar em nosso dispositivo de sala de reunião.
- **adal-sso-windows.ts:this.loggingService.logError** - Registra que um erro genérico de SSO durante o logon em um dispositivo Windows, erros ao iniciar o serviço de chat ou login em informações de falha.
- **appOnlineService.ts:loggingService.getInstance** - Registra a ocorrência de um erro devido a configurações que não puderam ser analisadas durante a inicialização ou por meio da autenticação anterior ao usuário e configurações pré-configuradas.
- **appStart.ts:loggingService.logError** - Registra a ocorrência de um erro quando o aplicativo não conseguiu iniciar, erro de espaço em disco, erro de validação de certificado ou falha em encontrar o certificado correto e reiniciar o aplicativo.
- **browserWindowHttp.ts:this.loggingService.logError** - Registra informações para indicar que o aplicativo não pôde ser atualizado devido a problemas com o sistema de arquivos.
- **contextInstallService.ts:loggingService.getInstance** - Registra a ocorrência de um erro quando:
  - tentativa de analisar ou ler um arquivo ou resolver uma URL crítica para o recurso de instalação contextual.
  - tentativas de encurtar a URL para executar o recurso de instalação contextual.
- **crashManager.ts:loggingService.logError** - Registra informações para determinar a causa de um erro quando o aplicativo falha.
- **localStorageService.ts:loggingService.getInstance** - Registra a ocorrência de um erro quando dados de inicialização essenciais não são carregados corretamente para executar o aplicativo.
- **logProviders\pageDumpProvider.ts:loggingService.getInstance** - Registra informações de erro quando o aplicativo falha.
- **multiWindowManager.ts:this.logError** - Registra a ocorrência de um erro quando dados de inicialização essenciais não são carregados corretamente para executar o aplicativo.
- **nativeElectronNotifications\osNotificationService.ts:this.loggingService.logError** - Esse evento registra a ocorrência de um erro ao tentar iniciar uma notificação sobre uma falha.
- **OutlookMeetingAddinHelper.ts:loggingService.getInstance** - Registra a ocorrência de um erro ao tentar se conectar a uma reunião usando o suplemento de reunião do Outlook.
- **recoveryManager.ts:loggingService.getInstance** - Registra a ocorrência de um erro durante rollbacks de atualização.
- **renderer\startPage\startPage.ts:this.logger.logError** - Registra a ocorrência de um erro com a página inicial do aplicativo.
- **settingsService.ts:loggingService.getInstance** - Registra a ocorrência de um erro com as configurações do aplicativo.
- **updateInfo.ts:loggingService.getInstance** - Registra a ocorrência de um erro com a transmissão de atualizações.
- **updatenotification.js:this._loggingService.logError** - Registra a ocorrência de problemas de espaço em disco.
- **utility.ts:loggingService.logError** - Registra um erro ao acessar um arquivo local (um arquivo no aplicativo).
- **utility.ts:loggingService.getInstance** - Registra um erro no espaço em disco disponível, problemas de exibição, problemas de URL, problemas de cookie, protocolos ou problemas de regkey no computador para carregar o aplicativo.
- **windowmanager.js:this._loggingService.logError** - Registra a ocorrência de problemas de cookie, problemas com tela branca, problemas entre a comunicação da área de trabalho e o shell, problemas de URL, erros com carregamento de mensagens da página, erros com renderização de processos e problemas com conectividade de rede.
- **windowmanager.js:loggingService.getInstance** - Registra informações para indicar quando a janela de recuperação não é exibida.

### <a name="outlook-addin"></a>Suplemento do Outlook

> [!NOTE]
> Para obter informações sobre as propriedades de eventos de suplemento do Outlook, consulte [Propriedades enviadas com os eventos do suplemento do Outlook](#properties-sent-with-outlook-addin-events).

- **joinmeetingoperation** - Registra as informações necessárias para integrar um usuário a uma reunião.
- **meetingaddinapplifecycle** - Registra informações sobre o estado do aplicativo, como Iniciar ou Sair.
- **meetingaddinloadtime** - Registra o tempo necessário para carregar as informações da reunião do Outlook.
- **openmeetingoperation** - Registra informações necessárias para abrir uma reunião agendada.
- **savemeetingoperation** - Registra informações necessárias para salvar a reunião ao agendar.

### <a name="scenario"></a>Cenário

> [!NOTE]
> Para obter informações sobre as propriedades de eventos de Cenário, consulte [Propriedades enviadas com eventos de cenário](#properties-sent-with-scenario-events).

- **desktop_app_load** - Registra as informações necessárias para determinar se o aplicativo da área de trabalho foi inicializado, se o serviço deve ser inicializado e se ele pode ser inicializado.
- **desktop_app_not_ready** - Registra as informações necessárias para determinar se o aplicativo da área de trabalho não está pronto para funcionar.
- **desktop_install** - Registra as informações necessárias para determinar se o aplicativo da área de trabalho foi instalado com êxito, ou se ele falhou na instalação.
- **desktop_previous_lifecycle_invalid** - Registra as informações necessárias para determinar se o aplicativo da área de trabalho foi reiniciado depois de ter sido executado anteriormente e falhou.

### <a name="tracking"></a>Acompanhamento

> [!NOTE]
> Para obter informações sobre as propriedades de eventos de Acompanhamento, consulte [Propriedades enviadas com os eventos de acompanhamento](#properties-sent-with-tracking-events).

- **deeplink_scenario_missing** - Teams foi iniciado por meio de um deeplink, mas a telemetria/diagnóstico não está presente.
- **desktop_app_initialized** - Registra informações necessárias para determinar se o aplicativo começou a ser iniciado com êxito quando o aplicativo da área de trabalho é inicializado.
- **desktop_app_quit_exception** - O aplicativo falhou durante tentativa de fechamento.
- **desktop_blankScreenDetected** - Registra as informações necessárias para determinar erros quando o aplicativo da área de trabalho processa uma tela em branco.
- **desktop_blankScreenDetectedAfterRepaint** - Detecção que uma página está em branco durante a detecção de tentativa de renderização.
- **desktop_blankScreenRecoveredAfterRepaint** - Recuperou-se de um problema de renderização em que a tela não foi renderizada anteriormente.
- **desktop_configuration_failed_to_save** - Coleta as informações necessárias para determinar erros de configuração quando as configurações da área de trabalho não são salvas.
- **desktop_navigation_error_recovery** - Coleta as informações necessárias para determinar erros de navegação na área de trabalho quando uma página não consegue ser carregada após cinco tentativas.
- **desktop_previous_gpu_crashed** - Registra as informações necessárias para determinar erros de unidade de processamento de gráficos quando a área de trabalho falha.
- **desktop_previous_plugin_host_crashed** - Coleta as informações necessárias para determinar problemas de pilha de mídia associados com falha do aplicativo da área de trabalho.
- **desktop_recovery_cleared_user_data** - Registra que o aplicativo falhou várias vezes e que o aplicativo teve que limpar o cache local para se recuperar.
- **desktop_settings_blank_on_load** - Esse é um erro informando que as configurações do aplicativo não estão presentes.
- **desktop_settings_failed_to_load** - Coleta as informações necessárias para determinar a causa da falha no carregamento das configurações da área de trabalho.
- **desktop_silent_restart** – A atualização do cliente é preparada e o cliente é atualizado sem interrupção do usuário.
- **desktop_terminated** - Registra informações necessárias para determinar se a comunicação entre processos foi desconectada quando o usuário fecha o aplicativo da área de trabalho.
- **desktop_uncaught_exception** Chamada de função em um objeto indefinido. Resultará em um reinício de falha/aplicativo.
- **desktop_write_storage_failed** - Registra as informações necessárias para determinar erros de disco quando o aplicativo da área de trabalho não consegue gravar no armazenamento.
- **registration_failed** - Registra as informações necessárias para resolver falhas no registro de suplementos.
- **registration_success** - Registra as informações necessárias para determinar se os registros do suplemento foram bem-sucedidos.
- **security_unsupported_ipc_channel** - Mensagem de interprocessamento não permitida foi recebida.
- **sfb_running_not_connected** - Detectado que o aplicativo Skype for Business não está em execução.
- **sfb_not_running** - Registra que a "espera pela resposta" da chamada para o Skype for Business expirou.
- **sfb_never_replied** - Controla se não houve nenhuma resposta da API durante a comunicação com o Skype for Business.
- **server_error_hit** - Controla se um erro de pipes de CPI se comunica com o Skype for Business.
- **unexpected_sfb_ipc_disconnection** - Registra informações necessárias para determinar uma falha de conexão com o serviço.
- **unregister_failed** - Registra as informações necessárias para determinar os erros de cancelamento de registro do suplemento de reunião do Outlook.

## <a name="userbi-panelaction"></a>Panelaction UserBI

> [!NOTE]
> Para obter informações sobre as propriedades de eventos panelaction, consulte [Propriedades enviadas com os eventos panelaction UserBI](#properties-sent-with-userbi-panelaction-events).

- **inlinereply** - Registra informações se um usuário respondeu a partir da notificação.
- **toastclick** - Registra o clique de um usuário para navegar até a entrada da mensagem para as notificações do sistema para monitorar o SLA do serviço e para carregar a resposta adequada à notificação do sistema.
- **toastdismiss** - Registra as informações necessárias para determinar os erros e atrasos quando o usuário descarta a renderização de uma notificação do sistema.

- **toast_skip** - Registra informações necessárias para evitar a transmissão de uma notificação atrasada do sistema.
- **toasttimeout** - Registra as informações necessárias para determinar os erros e atrasos quando a renderização de uma notificação do sistema expirou.

### <a name="userbi-panelview"></a>Panelview UserBI

> [!NOTE]
> Para obter informações sobre as propriedades de eventos panelview UserBI, consulte [Propriedades enviadas com os eventos panelview UserBI](#properties-sent-with-userbi-panelview-events).

- **toastshow** - Registra as informações necessárias para determinar se um caso de notificação foi renderizado.

## <a name="property-lists"></a>Listas de propriedades

### <a name="properties-sent-with-all-events"></a>Propriedades enviadas com todos os eventos

| Nome da propriedade                              | Descrição                                                        |
|--------------------------------------------|--------------------------------------------------------------------|
| EventInfo_Time                             | Tempo de geração do evento                                              |
| EventInfo_Name                             | Nome do evento - usado para diferenciar os tipos de eventos             |
| EventInfo_BaseType/name                    | Nome do evento - usado para diferenciar os tipos de eventos em um evento |
| EventInfo_Sequence                         | Sequência do evento                                              |
| userAgent                                  | Cadeia de caracteres de agente do navegador                                               |
| userpdclevel                               | Configuração do controle de dados de privacidade do usuário                           |
| eventpdclevel                              | Nível de categorização do controle dos dados de privacidade do evento             |
| AppInfo_Language                           | Idioma do aplicativo                                                       |
| clientType/AppInfo_ClientType              | Tipo de cliente em que o aplicativo está em execução                               |
| environment/AppInfo_Environment            | Ambiente de engenharia que serviu a solicitação de usuário               |
| clientVersion/appversion/AppInfo_Version/desktopBuildVersion | Versão do aplicativo                               |
| buildtime                                  | carimbo de data/hora de criação do aplicativo em sistemas de engenharia            |
| osversion/DeviceInfo_OsVersion             | Versão do sistema operacional.                                                         |
| AppInfo_ProcessArchitecture                | Arquitetura de sistema (32bit/64bit)                                  |
| preferredLocales                           | localidade preferencial para o usuário                                      |
| locale/AppInfo_Locale                      | Local do aplicativo                                                         |
| os/DeviceInfo_OsName                       | Nome do sistema operacional                                                            |
| UserInfo_Language                          | Idioma selecionado do usuário                                             |
| UserInfo_Id                                | ID do Usuário                                                            |
| UserInfo_TenantId/TenantId                 | ID do locatário                                                          |
| ring/UserInfo_Ring                         | Conceito que ajuda a entregar aplicativos em fases          |
| região                                     | Região do Data Center que atuou pela solicitação do usuário                       |
| UserInfo_ConfigIds/UserInfo_Etag           | ID que ajuda a identificar os usuários em diferentes experiências/implementações     |
| DeviceInfo_BrowserName                     | ID do navegador                                                       |
| DeviceInfo_BrowserVersion                  | Versão do navegador                                                    |
| DeviceInfo_Id/machineId/DeviceInfo_IdV2    | ID que ajuda a identificar o dispositivo                                  |
| totalMemory                                | Memória de hardware do dispositivo                                      |
| núcleos                                      | Núcleos de hardware do dispositivo                                       |
| cpuspeed                                   | Velocidade de hardware da CPU do dispositivo                                   |
| DeviceInfo_CpuArchitecture/cpuarchitecture | Arquitetura de CPU do dispositivo                                     |
| UserRole                                   | Ajuda a identificar a função do usuário em um locatário                               |
| DeviceInfo_WindowsMode                     | Ajuda a identificar o modo de segurança do Windows                               |
| desktopSession/Session_Id                  | Ajuda a identificar uma sessão                                           |
| dbOpen                                     | Captura o estado do banco de dados local                               |
| UserInfo_Upn                               | Um hash de um lado do identificador de usuário                                  |

### <a name="properties-sent-with-logging-events"></a>Propriedades enviadas com todos os eventos de registro em log

| Nome da propriedade         | Descrição                                                        |
|-----------------------|--------------------------------------------------------------------|
| mensagem               | Captura uma mensagem detalhada sobre o log                          |

### <a name="properties-sent-with-scenario-events"></a>Propriedades enviadas com os eventos de cenário

| Nome da Propriedade                     | Descrição                                                                        |
|-----------------------------------|------------------------------------------------------------------------------------|
| Scenario_Status                   | Status de um cenário                                                               |
| Scenario_Step                     | Etapa em um cenário                                                                 |
| sequência                          | Número de sequência do cenário                                                    |
| delta                             | Tempo necessário para concluir etapas diferentes em um cenário                               |
| decorrido                           | Tempo desde o início do cenário                                                    |
| cenário                          | Identifique exclusivamente um cenário                                                       |
| Scenario_Name                     | Nome do cenário                                                               |
| errorInfo                         | Informações do erro que pode ter ocorrido durante um cenário                       |
| seção                           | ID de sessão exclusiva                                                                  |
| freeMemory                        | Captura a memória livre disponível                                                     |
| processMemory                     | Captura a memória do processo                                                            |
| scenarioDelta                     | Captura tempo diferente entre duas etapas do cenário                                   |
| Session_DesktopId                 | ID de sessão exclusiva                                                                  |
| machineLocked                     | Captura se o computador foi bloqueado ou não                                          |
| windowIsVisible                   | Captura se a janela do aplicativo estava visível para usar                                      |
| appStates/webAppStates            | registra uma lista de estado de aplicativos que o aplicativo passou. Isso ajuda com a investigação de falhas porque podemos ver em que estado o aplicativo estava |
| crashDesktopSession               | Captura a ID da sessão falhada                                                 |
| appRuntime                        | Captura o tempo de execução do aplicativo                                                        |
| diagnosticEvents                  | Últimos 50 eventos de diagnóstico do aplicativo Web antes do aplicativo falhar                                 |
| atividades                        | Últimos 50 nomes de cenário de usuário que ocorreram antes do travamento                            |
| crashSession                      | Captura a ID da sessão falhada                                                 |
| crashId                           | Captura a ID da sessão falhada                                                 |
| isPreviousLifecycleValid          | Se o aplicativo anterior foi totalmente inicializado e encerrado com êxito             |
| isSettingValid                    | Se as configurações de preautenticação são válidas                                                 |
| rollbackReason                    | Motivo da reversão do aplicativo                                            |
| deeplinkType                      | Tipo de deeplink                                                               |
| watchdogCrash                     | Se o aplicativo falhou devido a um travamento                                                    |
| protocolos                         | Protocolo usado para iniciar o aplicativo                                                    |
| electronBuild                     | Versão de compilação do aplicativo electron                                                      |
| distribuição                      |  se o Teams foi instalado via exe ou msi ou dmg ou pkg, etc.                    |
| updateTimeOfDay                   | Hora em que o aplicativo foi atualizado                                                           |
| launchPath                        | se o Teams está instalado em % LOCALAPPDATA%,% PROGRAMfiles% ou outros locais   |
| loggedIn                          | Se o usuário tiver entrado em                                                          |
| envType/complianceEnvironmentType | Nuvem comercial ou particular (por exemplo, DoD, GCC-High, etc.)                              |
| cpuusage                          | Uso da CPU                                                                          |
| installationSource                | Tipo de instalação do usuário                                                      |
| adalVersion                       | Versão da biblioteca de autenticação                                                        |
| asyncStart                        | O aplicativo está usando o início síncrono ou assíncrono                                 |
| tentativas                          | Número de tentativas de verificação online feitas para o usuário antes de mostrar uma tela de bloqueio |

### <a name="properties-sent-with-tracking-events"></a>Propriedades enviadas com todos os eventos de acompanhamento

| Nome da propriedade                      | Descrição                                                                      |
|------------------------------------|----------------------------------------------------------------------------------|
| nome2                              | Captura o nome do evento de acompanhamento                                              |
| numVisibleNotifications            | Número de notificações de aplicativos visíveis                                      |
| giphyEnabled                       | Se o serviço giphy foi habilitado                                                |
| erro                              | Captura detalhes do erro relacionados ao evento de acompanhamento                             |
| método                             | Método de protocolo GET ou POST                                                      |
| canal                            | Captura o canal de comunicação entre processos no aplicativo                      |
| windowTitle                        | Tipo de janela de exibição associada ao evento                                     |
| mensagem                            | O tipo de mensagem de erro                                                        |
| crashSession/crashDesktopSession/crashId/Session_DesktopId/Session_DesktopBackgroundId | Captura a ID exclusiva para fins de depuração de sessão |
| responseCode                       | Captura o código de resposta da chamada de serviço                                      |
| errorUrl                           | A URL que não pôde ser carregada                                                      |
| errorCode                          | Captura o código de erro                                                              |
| ssoEventData                       | Status e estado de autenticação                                                  |
| correlationId                      | ID para correlacionar eventos com o lado do serviço para fins de depuração                      |
| errorDescription                   | Captura a descrição do errorcode                                            |
| origem                             | Método para obter o aplicativo Teams e quais tipos de pacote do Teams foram instalados       |
| windowIsDestroyed                  | Estado verdadeiro/falso do aplicativo Windows durante o evento                             |
| windowIsFocused                    | Estado verdadeiro/falso do aplicativo Windows durante o evento                             |
| windowIsVisible                    | O aplicativo ficou visível quando ocorreu um evento                                  |
| windowIsMinimized                  | Estado verdadeiro/falso do aplicativo Windows durante o evento                             |
| windowIsMaximized                  | Estado verdadeiro/falso do aplicativo Windows durante o evento                             |
| windowIsFullscreen                 | Estado verdadeiro/falso do aplicativo Windows durante o evento                             |
| distSrc                            | Captura a origem de distribuição da aterrissagem do usuário no aplicativo                    |
| retries                            | Repetir a contagem ao tentar se conectar a um ponto de extremidade                            |
| uses_slimcore                      | Verdadeiro ou falso se chamada da Web estiver usando o slimcore                                      |
| persistCookieExpiresIn             | Tempo restante na validade do cookie de aplicativo Web                             |
| tenantName                         | Nome do locatário para o usuário do aplicativo                                       |
| appStartReason                     | Como a sessão do aplicativo começou, como iniciado pelo usuário, após a atualização, etc. |
| machineLocked                      | Se a máquina estava bloqueada ou não foi bloqueada durante o evento                        |
| dados                               | Captura dados técnicos de investigação de cenário                               |
| appRuntime                         | Captura o tempo de execução do aplicativo                                                      |
| atividades                         | Últimos 50 nomes de cenário de usuário que ocorreram antes do travamento                          |
| timeSinceActivity                  | Tempo desde a última atividade do usuário                                                    |
| appStates                          | Registra uma lista de estados do aplicativo para os quais o aplicativo da área de trabalho passou, o que ajuda com investigações de falha porque mostra em qual estado o aplicativo da área de trabalho estava |
| timeSinceAppState                  | Tempo decorrido desde que o estado do aplicativo foi alterado                                                 |
| webAppStates                       | Registra uma lista de estados do aplicativo pelos quais o cliente web passou, o que ajuda com investigações de falha porque mostra em qual estado o aplicativo do cliente web estava |
| timeSinceWebAppState               | Tempo decorrido desde que o estado do aplicativo web foi alterado                                             |
| diagnosticEvents                   | Últimos 50 eventos de diagnóstico do aplicativo Web antes do aplicativo falhar                               |
| timeSinceLastDiagnosticEvent       | Tempo desde que o último evento de diagnóstico foi enviado                                            |
| timeSinceSecondLastDiagnosticEvent | Tempo desde que o segundo último evento de diagnóstico foi enviado                                     |
| appInitialized                     | Se o WebApplication começou                                               |
| targetVersion                      | O aplicativo de versão será atualizado para                                    |
| porta                               | Número da porta da mensagem de Internet                                                     |
| originalUrl                        | Local original da página que está sendo renderizada                                         |
| deeplinkId                         | GUID para o tipo de destino do link do Teams                                          |
| appSessionEnd                      | Se ocorreu o evento no fim da sessão do aplicativo                             |
| eventData                          | Captura o estado do computador e a configuração de aplicativos para ajudar na depuração no caso de problemas        |
| deeplinkType                       | Tipo de deeplink (chat, reunião, canal)                                    |
| previousUpdateUrl                  | Local de onde o aplicativo recuperou sua atualização                        |
| previousUpdateVersion              | A última versão do aplicativo foi atualizada para                                          |
| previousUpdateTime                 | Quando os binários do aplicativo foram atualizados pela última vez                                      |
| protocolo                           | Tipo de manipulador para link, como arquivo ou imagem                                     |
| arquivos                              | Tipo de arquivo associado a um evento, como o cache de aplicativos ou o cache da GPU    |
| Perf_WorkingSetSizeKB              | Tamanho do cache da memória                                                             |
| isTimeboxingWebAppInitialize       | Se o aplicativo foi inicializado antes do contador de caixa de hora ter sido executado                          |
| isExp                              | Se a versão do aplicativo em uso faz parte de um experimento                          |
| deviceType                         | Captura o tipo do dispositivo                                                      |
| sanitizedErr                       | Captura a versão limpa das informações de erro                              |
| rigelVersion                       | Captura a versão do dispositivo rigel                                                 |
| DeviceInfo_OsSku                   | Captura informações de SKU do sistema operacional                                                      |
| isLoggedOut                        | Captura se o usuário está desconectado                                               |
| complianceEnvironmentType          | Nuvem comercial ou particular (por exemplo, DoD, GCC-High, etc.)                           |
| restartTimes                       | Vezes exatas das reinicializações anteriores                                                 |
| Skype_ResultCode                   | Captura o resultado da comunicação de interoperabilidade entre o Skype e o Teams                 |
| cpumodel                           | Captura o modelo de CPU                                                            |
| isSlimCoreRunningOutproc           | Se o componente Slimcore está sendo executado em seu próprio processo                         |
| isSlimCoreStartedAsync             | Tipo de lançamento da pilha interna de áudio/vídeo (A/V)                               |
| networkState                       | Captura o estado da rede                                                    |
| desktopBuildAge                    | Qual a idade do Build do aplicativo em tempo de evento                                   |
| vdiMode                            | Captura se o aplicativo estiver em execução no modo VDI                                       |

### <a name="properties-sent-with-userbi-panelview-events"></a>Propriedades enviadas com eventos panelview UserBI

| Propriedade           | Descrição                                              |
|--------------------|----------------------------------------------------------|
| Panel_Uri          | URI do painel entregue ao usuário                   |
| Panel_Type         | Tipo de painel acessado pelo usuário                          |
| Team_Id            | ID da equipe na qual a ação foi realizada pelo usuário |
| Thread_Id          | ID da conversa que foi acessada pelo usuário               |
| Panel_PreviousUri  | URI do painel anterior                                |
| Panel_Region       | Região na qual o painel foi hospedado no aplicativo             |
| Panel_LaunchMethod | Método pelo qual o painel foi iniciado              |
| Panel_PreviousType | Tipo do painel anterior                               |
| Thread_Type        | Tipo de conversa acessada pelo usuário                          |
| Panel_LaunchSource | Informações da fonte do painel iniciado        |
| Tab_Type           | Tipo da guia acessada pelo usuário                         |
| Team_Type          | Tipo de equipe acessada pelo usuário                            |

### <a name="properties-sent-with-userbi-panelaction-events"></a>Propriedades enviadas com eventos panelaction UserBI

| Nome da propriedade         | Descrição                                                        |
|-----------------------|--------------------------------------------------------------------|
| Action_DestinationUri | URI do recurso que está sendo acessado por ação do usuário                  |
| Panel_Uri             | URI do painel entregue ao usuário                             |
| Action_Gesture        | Tipo de gesto executado pelo usuário no aplicativo                       |
| Action_ScenarioType   | Agrupamento de recursos que se relaciona à métrica de negócios para o recurso       |
| Panel_Type            | Tipo de painel acessado pelo usuário                                    |
| Action_Outcome        | Resultado da ação realizada pelo usuário                            |
| Team_Id               | ID da equipe na qual a ação foi realizada pelo usuário           |
| Module_Type           | Tipo de módulo que hospeda a ação do usuário                        |
| Module_Name           | Nome do módulo que hospeda a ação do usuário                        |
| Module_Summary        | Resumo do módulo que hospedou a ação do usuário                       |
| Thread_Id             | ID da conversa que foi acessada pelo usuário                         |
| Panel_PreviousUri     | URI do painel anterior                                          |
| Panel_Region          | Região na qual o painel foi hospedado no aplicativo                       |
| Panel_LaunchMethod    | Método pelo qual o painel foi iniciado                        |
| Panel_PreviousType    | Tipo do painel anterior                                         |
| Thread_Type           | Tipo de conversa acessada pelo usuário                                    |
| Module_State          | Estado do módulo acessado pelo usuário                               |
| Action_Scenario       | Recurso dentro de um grupo de recursos relacionados à métrica comercial |
| Panel_LaunchSource    | Informações da fonte do painel iniciado                  |
| Tab_Type              | Tipo da guia acessada pelo usuário                                   |
| Team_Type             | Tipo de equipe acessada pelo usuário                                      |

### <a name="properties-sent-with-outlook-addin-events"></a>Propriedades enviadas com os eventos de suplemento do Outlook

| Nome da Propriedade                   | Descrição                                                              |
|---------------------------------|--------------------------------------------------------------------------|
| AccountComparisonFailedReason   | O suplemento compara a conta com a conta do Teams para ver se a criação é permitida. Este evento será enviado se a comparação falhar |
| AccountComparisonSuccessful     | O suplemento compara a conta com a conta do Teams para ver se a criação é permitida. Este evento será enviado se a comparação for bem-sucedida |
| AdalVersion                     | Versão da biblioteca de autenticação usada                               |
| AddinBitness                    | Versão do suplemento                                                         |
| AddinLanguage                   | Linguagem de cadeias de caracteres de suplemento sendo usadas                                     |
| AggregatorSetupCompletedTime    | Tempo de preparação para o carregador de suplemento                                              |
| AppDomainCreatedTime            | Hora em que o carregador de suplemento Inicializa o domínio de aplicativo                            |
| AppointmentDisplayTime          | Hora em que o item de compromisso foi exibido durante a criação de uma reunião |
| AuthenticationCompletedTime     | Hora em que a autenticação foi fornecida para uma determinada solicitação            |
| ConnectionMode                  | Indica o modo de conexão da conta principal do Exchange do usuário     |
| ConnectionStartedTime           | Hora em que o Outlook chama o OnConnection                                     |
| ErrorDetails                    | Captura detalhes do erro                                            |
| ErrorName                       | Captura o nome do erro                                               |
| ExchangeVersion                 | Captura a versão do Exchange                                             |
| IsSmtpFormatError               | Erro no endereço SMTP                                                    |
| IsTeamsRunning                  | Captura se há um processo do Teams em execução                             |
| IsTeamsUserLoggedOut            | Captura se o usuário está desconectado do Teams                              |
| LanguageSetupCompletedTime      | Hora em que a instalação do idioma foi concluída                               |
| ManagedConnectTime              | Hora em que o suplemento gerenciado recebeu o retorno de chamada de conexão               |
| ManagedOnStartupTime            | Hora em que o gerenciado iniciou a inicialização                                    |
| MTFetchCompleted                | Hora de conclusão da solicitação de opções de reunião MT                        |
| NetFrameworkVersion             | .NET Framework usado                                                      |
| NetworkAvailable                | Se a rede está disponível                                                     |
| OperationStartTime              |  Hora de início de operações diferentes                                  |
| OsBitness                       | Bits do sistema operacional                                                            |
| OutlookLanguage                 | Captura o idioma do aplicativo Outlook                                     |
| OutlookVersion                  | Captura a versão do Outlook                                          |
| OwnerResolutionTime             | Hora para resolver o proprietário da reunião                                        |
| ParseResponseCompletedTime      | Hora da conclusão da análise da resposta                                  |
| RecipientResolutionError        | Detalhes do erro ao resolver um destinatário                                 |
| RecipientsResolutionTime        | Tempo total para resolver todos os destinatários                                     |
| RehydrateCompletedTime          | Hora em que as propriedades são lidas no Outlook                               |
| SaveToOutlookCompletedTime      | Hora em que as propriedades são salvas no Outlook                                |
| ServiceRequestStartTime         | Hora de início da solicitação de serviço                                        |
| ServiceResponseReceiveTime      | Tempo de resposta do serviço                                        |
| SettingsInitializeCompletedTime | Hora de inicialização das configurações                                           |
| SetupLoggingCompletedTime       | Hora em que o registro em log foi configurado                                             |
| ShutdownBeginTime               | Hora de início do encerramento do suplemento                                       |
| ShutdownCompletedTime           | Hora do término do encerramento                                             |
| StartupBeginTime                | Hora de início da inicialização do suplemento                                        |
| StartupCompletedTime            | Hora em que a inicialização é concluída                                              |
| TeamsDeployment                 | Implantação do cliente do Teams (Dev, Prod)                                   |
| TeamsRing                       | Sinal de usuário atual conectado ao cliente do Teams                            |
| TeamsVersion                    | Captura a versão do aplicativo do Teams                                            |
| TelemetrySetupCompletedTime     | Hora de conclusão da configuração de telemetria                                   |
| UpnMismatch                     | Se há uma incompatibilidade entre o Outlook e o Teams                  |
| UserDomain                      | Domínio do usuário                                                       |
| ViewUpdatedTime                 | Hora em que o modo de exibição foi atualizado                                           |
