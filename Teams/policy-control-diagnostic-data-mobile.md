---
title: Dados de diagnóstico móvel necessários para o Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: majaisin
description: Uma lista de eventos e propriedades móveis para os controles de política do Microsoft Teams.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 91203a9e35954e695bea5482c41674137320b487
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674233"
---
# <a name="required-mobile-diagnostic-data-for-microsoft-teams"></a>Dados de diagnóstico móvel necessários para o Microsoft Teams

O artigo a seguir contém uma lista de eventos do Microsoft Teams para dispositivos móveis e listas de propriedades que cada evento coleta.

Para saber mais sobre dados de diagnóstico, incluindo como controlar quais dados de diagnóstico são enviados à Microsoft, consulte [Dados de diagnóstico enviados do aplicativo Teams para o Microsoft](policy-control-overview.md#diagnostic-data-sent-from-the-teams-app-to-microsoft). Para exibir os dados de diagnóstico que estão sendo enviados à Microsoft, você pode usar o [Visualizador de Dados de Diagnóstico](https://support.microsoft.com/topic/cf761ce9-d805-4c60-a339-4e07f3182855).

## <a name="events"></a>Eventos

> [!NOTE]
> Existem propriedades comuns para todos os eventos listados abaixo, para revisá-los, consulte [Propriedades enviadas com todos os eventos](#properties-sent-with-all-events).

### <a name="panelaction"></a>PanelAction

> [!NOTE]
> Para obter informações sobre as propriedades de eventos PanelAction, consulte [Propriedades enviadas com os eventos panelaction](#properties-sent-with-panelaction-events).

- **acceptUser** – o usuário aceitou um chat 1:1.
- **accessibilityUserConfiguration** - Quando um usuário alterna um recurso de acessibilidade.
- **acknowledgeSettingChange** - reconhece uma atualização no diálogo de configuração Nós atualizamos uma configuração. Esse é um recurso de métricas de sucesso usado para reconhecer as notificações de atualização e determinar a confiança geral da notificação.
- **actionComposeMenu**
  - Criar o uso da extensão da mensagem.
  - Uso da extensão da mensagem de ação.
- **active_session_banner_dismissed** - a faixa de lembrete ativa do compartilhamento de localização foi ignorada.
- **activityChatClicked** - acionado quando o chat que não está ao vivo é selecionado na guia **Atividade** ou o modo divisão é mostrado.
- **activityContextMenu** - ações excedentes no feed de atividades.
- **activityFeedClick** - um item do feed de atividades é tocado e um bot do chat o acessa.
- **activityFeedLongPress** - captura gestos de pressionar prolongados nos itens de feed.
- **activityFeedSwipe** - captura gestos de passar o dedo em itens do feed.
- **activityFilterClick** - captura o uso do filtro de atividade.
- **activityFilterOptionsClick** - captura o uso do filtro de atividade.
- **activityFilterOptionsClicked** - captura o uso do filtro de atividade.
- **activityLiveChatClicked** - acionado quando o chat é selecionado em uma reunião ao vivo na guia **Atividade**.
- **activityLiveDetailsClicked** - acionado quando **Detalhes** é selecionado em uma reunião ao vivo na guia **Atividade**.
- **activityTabClicked** - ajuda a determinar se:
  - A guia **Atividade** é exibida.
  - O Teams captura um evento na guia **Atividade**.
- **activityTypeDropdown** - captura o uso do filtro de atividades para alternar entre **Minha atividade** e **Feeds**.
- **addChannel** - adicionar um canal. Esse item fornece dados de sucesso em torno da criação bem-sucedida de um canal.
- **AddMember** - acionado quando o botão **Convidar pessoas** é selecionado no menu **Mais**.
- **addMembers** - adiciona membros a uma equipe ou canal privado.
- **addToCalendar** - marca o botão **Adicionar ao calendário** para eventos de calendário ausentes no calendário particular.
- **addToList** - um contato é adicionado a uma lista de contatos.
- **addToMeeting** - selecionar o botão **Adicionar à reunião** na lista de participantes de uma reunião (para participantes que fazem parte do chat).
- **addUserAsContact** - um contato pode ser adicionado selecionando o ícone **Adicionar contato** do cartão de perfil do contato.
- **admitAll** - o número de vezes que o botão **Admitir todos** é selecionado na seção de lobby.
- **admitParticipant** - o número de vezes que alguém é admitido em uma reunião a partir da lista de reuniões.
- **alertsNavAlert** - tocar em um item do feed.
- **aliasDiscoverabilitySettingOpened** – Ponto de entrada para configurações de discoverabaility.
- **Android: null** - ativar ou desativar o som de um chat de bot. Esse aperfeiçoamento de telemetria existente em conversas só adiciona informações sobre o aplicativo.
- **anonymousMeetingJoin** - **Participar da reunião** é selecionado em uma página fornecer nome de reunião anônimo ou **OK** é tocado na caixa de diálogo nome.
- **anonymousMeetingJoinWelcome** - **Ingressar como convidado** é selecionada em uma página de aterrissagem de reunião anônima.
- **anonymousMeetingPostMeetingChat** - o número da exibição do usuário do chat na tela final da chamada.
- **anonymousMeetingPostMeetingRejoin** - o número de vezes que um usuário anônimo tenta se reintegrar a uma reunião.
- **anonymousMeetingSignIn** - o número de vezes que um usuário navegou para entrar da tela de entrada do nome.
- **anonymousMeetingJoinWelcome**- o **entrar e ingressar** é selecionado em uma página de aterrissagem de reunião anônima.
- **anonymousMeetingToggleMuted** - o número de vezes que o botão de alternância de mudo foi selecionado.
- **anonymousMeetingToggleVideo** - o número de vezes que o botão de alternância de vídeo foi selecionado.
- **appKilled** - o aplicativo foi encerrado.
- **approveTimeOffRequest** -  Quando um gerente do Trabalhador na Linha de frente (FLW) aprova uma solicitação do Trabalhador na Linha de frente para tirar uma folga.
- **assigneeChange** - acionado quando um novo destinatário é adicionado a um item de tarefa.
- **assignmentPickerClicked** - o botão **Atribuir à** é selecionado, abrindo uma página seletor de destinatário.
- **assignmentRemoved** - acionado quando um destinatário é removido de um item de tarefa selecionando o **x** (que é a única maneira de remover um destinatário).
- **attachmentAdded** - confirma que um anexo em uma tarefa foi adicionado com êxito.
- **attachmentDeleted** - confirma que um anexo em uma tarefa foi excluído com êxito.
- **attachmentUpdated** - confirma que um anexo em uma tarefa foi atualizado com êxito.
- **audioOnlyLowBatteryBanner** - a opção **Somente áudio** é selecionada devido a uma faixa de bateria fraca.
- **audioOnlyPoorNetworkBanner** - a opção **Vídeo desativado** é selecionada devido a uma faixa de conexão ruim.
- **audioUserDoubleTap** - toque duas vezes em um participante de áudio.
- **autoReconnectCallmebackCallDrop** - o número de vezes que o botão **Callmeback** foi selecionado na tela final da chamada.
- **autoReconnectDialIn**
  - O botão **Discar** é selecionado na UFD reconectar.
  - O número de vezes que o botão **Discar** foi selecionado enquanto uma reconexão está em andamento.
- **autoReconnectDialInonCallDrop** - o botão **Discagem** é selecionado na UFD da chamada desconectada.
- **autoReconnectDialOut** - o botão **Telefonar-me novamente** é selecionado na UFD reconectar.
- **autoReconnectRejoinonCallDrop** - o número de vezes que o botão **Reingressar** ou **Rediscar** foi selecionado na tela final da chamada.
- **backFromCallMePSTN** - o fluxo do número PSTN Telefonar-me novamente não foi concluído.
- **backToPhotoShare** - retornando para uma câmera.
- **backToStageFromWhiteboard** - retornando a uma tela de chamada de um quadro de comunicações digital.
- **backToWhiteboardFromStage** - indo de um quadro de comunicações digital para uma tela de chamada.
- **blockAnonymous** - quando:
  - Habilita a configuração da chamada a bloquear chamadas sem a ID do chamador das configurações.
  - Desabilita a configuração da chamada a bloquear chamadas sem a ID do chamador das configurações.
  - Habilita a configuração da chamada a bloquear chamadas sem a ID do chamador na folha de ações.
  - Desabilita a configuração da chamada a bloquear chamadas sem a ID do chamador na folha de ações.
- **blockCaller** - bloqueia:
  - Um número e um contato da folha de ações de novas chamadas iOS.
  - Um contato e um número do cartão de visita.
  - Números das configurações.
- **blockChat** - bloqueia um bot do chat. Esse aperfeiçoamento de telemetria existente em conversas só adiciona informações sobre o aplicativo.
- **botClickCardAction** - uso do cartão do conector.
- **brbFormOpened** - O usuário solicitou o envio de comentários.
- **brbFormSubmit** – O usuário enviou comentários.
- **breakStartEndClicked** - na tela registrar entrada, o botão **Iniciar** ou **Terminar intervalo** é selecionado.
- **breakStartEndTriggered** - registro que um usuário decide para usar o início ou o fim do intervalo.
- **bucketSelected** - confirma que um bucket foi selecionado com êxito.
- **bucketUnselected** - confirma que um bucket foi cancelado com êxito.
- **bucketPickerClicked** - confirma que o seletor de buckets foi iniciado com êxito.
- **BYOELiveEventJoin** - evento ao vivo BYOE (transmita seu próprio evento) é ingressado por um usuário.
- **calendarLiveChatClicked** - conversa da reunião ao vivo na guia **Agendar**.
- **calendarMeetingJoin** - **botão Ingressar reunião** selecionado em um calendário.
- **calendarTab** - Selecione a guia **Reuniões** no trilho inferior. Útil para compreender o uso do calendário e comparar com outros aplicativos no trilho inferior, ou determinar se ocorreu uma falha ao processar a postagem de calendário depois de selecioná-la na barra inferior.
- **calendarTabClicked** - nas circunstâncias listadas abaixo, isso mostrará o uso do calendário e permitirá que você compare com outros aplicativos de navegação na barra inferior. Pode ser usado para determinar se ocorreu uma falha quando:
  - A guia **Agendar** é exibida.
  - A guia **Reuniões** é selecionada no canto inferior.
- **calendarLiveChatClicked** - conversa de uma reunião ao vivo iminente na guia **Agendar**.
- **callAccepted** - chamada aceita.
- **callAcceptedSFB** - chamada aceita.
- **callAppPreference** - um aplicativo de chamada preferencial é selecionado.
- **callControlsManualDismiss** - controles de chamada são ignorados manualmente.
- **callControlsManualInvoke** - controles de chamada são invocados manualmente.
- **callHistoryItemExpand** - item do histórico de chamadas expandido.
- **callHistoryTab** - **guia** CallHistory é selecionada em chamadas.
- **callInProgressShown** - Um * banner de *_chamada em andamento_* é mostrado.
- **callMePSTNConnected** - **Telefonar-me** é bem-sucedida.
- **callOrMeetUpAddParticipants** - acionado quando:
  - O botão Adicionar participante é tocado em uma tela de chamada 1:1.
  - Selecionar pessoa (VoIP) em adicionar participantes.
  - Selecionar PSTN em adicionar participantes.
  - Adicionar pessoas em uma reunião particular ao vivo.
  - Selecionar PSTN em uma reunião particular ao vivo.
  - Selecionar o contato da empresa em uma reunião particular ao vivo.
  - Selecionar o contato do dispositivo em uma reunião particular ao vivo.
  - Adição de participantes concluída em uma reunião particular ao vivo.
  - Adicionar pessoas em uma reunião de canal ao vivo.
  - Selecionar PSTN em uma reunião de canal ao vivo.
  - Selecionar membro da equipe em uma reunião ao vivo no canal.
  - Selecionar o contato do dispositivo em uma reunião ao vivo no canal.
  - Adição de participantes concluída em uma reunião ao vivo no canal.
- **callOrMeetUpAddParticipantsDone** - um usuário finaliza a adição de participantes.
- **callOrMeetUpAddRoom** - acionado quando:
  - **Adicionar sala** - é selecionada na lista.
  - Um resultado de pesquisa é selecionado em adicionar sala.
  - **Dispensar** está selecionado para próximo.
  - **Habilitar BT** ou **Localização** é selecionado para próximo.
  - Um resultado sala próxima é selecionado em adicionar sala.
  - Uma sugestão de sala é selecionada em adicionar sala.
  - **Concluído** - é selecionada em adicionar sala.
- **callOrMeetUpAudioOffSwitch** - inverter o botão **Áudio desativado** enquanto estiver no modo de ingresso complementar em uma chamada ao vivo ou encontro.
- **callOrMeetUpAutoReconnect** - o desempenho de rede ruim causa o dispositivo de um usuário entrar no modo AutoReconnect.
- **callOrMeetUpCallAccepted** - acionado quando:
  - Uma chamada é aceita.
  - Uma chamada PSTN é aceita.
- **callOrMeetUpCallEnded** - acionado quando:
  - Um botão **Terminar chamada** é tocado.
  - Um botão **Chamada finalizada** é tocado durante callOrMeetupLive.
  - Um botão **Chamada finalizada** é tocado durante lockScreen.
  - Um botão **Chamada finalizada** é tocado durante notificação.
  - Um botão **Chamada finalizada** é tocado durante inApp.
  - Um botão **Chamada finalizada** é tocado durante callKit.
  - Um botão **Chamada finalizada** para PSTN é tocado.
- **callOrMeetUpChatWithParticipants** - alterne o chat durante uma reunião ao vivo ou chamada.
- **callOrMeetUpDeviceAudioSwitch** - acionado quando:
  - Alternar a fonte de áudio para o orador.
  - Alternar a fonte de áudio para o dispositivo.
  - Alternar a fonte de áudio para o Bluetooth.
  - Alternar a fonte de áudio para o áudio desativado.
  - Alterne o alto-falante durante uma reunião ao vivo ou uma chamada.
  - Alterne o alto-falante para áudio desativado durante uma reunião ao vivo ou uma chamada.
  - Inverter o botão **Áudio desativado** enquanto estiver no modo de ingresso complementar em uma chamada ao vivo ou encontro.
  - Mudança de áudio do dispositivo durante a PSTN.
- **callOrMeetUpEnterDriveMode** - alterna manualmente para o modo de condução no menu **...**.
- **callOrMeetupExitDriveMode** - **botão sair do modo de condução tocado**.
- **callOrMeetUpHold** - acionado quando:
  - O botão **Reter** é tocado durante uma reunião ao vivo ou uma chamada.
  - Chamada em espera na PSTN.
- **callOrMeetUpIncomingVideoSwitch** - desative o IncomingVideo enquanto estiver em uma reunião ao vivo ou uma chamada.
- **callOrMeetUpInvitedParticipants** - acionado quando:
  - Clicar em **Ver todos** na parte inferior de um grupo de participantes **Outras pessoas convidadas** durante uma reunião particular ao vivo.
  - Clicar em **Ver todos** na parte inferior de um grupo de participantes **Outros convidados** durante uma reunião particular ao vivo no canal.
- **callOrMeetUpJoinedParticipants** - acionado quando:
  - Clicar em **Ver todos** na parte inferior de um grupo de participantes **Na reunião** durante uma reunião particular ao vivo.
  - Clicar em **Ver todos** na parte inferior de um grupo de participantes **Na reunião** durante uma reunião ao vivo no canal.
- **callOrMeetUpLobbyParticipants** - acionado quando:
  - Clicar em **Ver todos** na parte inferior do **Lobby** de um grupo de participantes durante uma reunião particular ao vivo.
  - Clicar em **Ver todos** na parte inferior do **Lobby** de um grupo de participantes durante uma reunião ao vivo no canal.
- **callOrMeetUpMicrophoneSwitch** - acionado quando:
  - Ativar microfone.
  - Desativar microfone.
  - O botão do **Microfone** é selecionado durante uma reunião ao vivo ou uma chamada.
  - Alternância do microfone durante PSTN.
- **callOrMeetUpMuteParticipant** - um participante remoto está mudo.
- **callOrMeetUpMuteParticipants** - ativar o mudo para todos os participantes durante uma reunião ao vivo ou uma chamada.
- **callOrMeetUpParticipants** - os participantes alternam durante uma reunião ao vivo ou uma chamada.
- **callOrMeetUpRemoteMuteUFD** - você teve o mudo ativado para UFD.
- **callOrMeetUpResume** - acionado quando:
  - O botão **Retomar** é selecionado durante uma reunião ao vivo ou uma chamada.
  - Retomar chamada na PSTN.
- **callOrMeetUpSearchParticipants** - acionado quando:
  - Clicar em **Pesquisar** nos participantes da reunião durante uma reunião particular ao vivo.
  - Clicar em **Pesquisar** após exibir o **Lobby** do grupo participante durante uma reunião particular.
  - Clicar em **Pesquisar** após exibir o grupo de participantes **Na reunião** durante uma reunião particular.
  - Clicar em **Pesquisar** após exibir o grupo de participantes **Outros convidados** durante uma reunião particular.
  - Clicar em **Pesquisar** nos participantes da reunião durante uma reunião ao vivo no canal.
  - Clicar em **Pesquisar** após exibir o **Lobby** do grupo participante durante uma reunião ao vivo no canal.
  - Clicar em **Pesquisar** após exibir o grupo participante **Na reunião** durante uma reunião ao vivo no canal.
  - Clicar em **Pesquisar** após exibir o grupo de participantes **Outros convidados** durante uma reunião ao vivo no canal.
- **callOrMeetUpDeviceVideoSwitch** - acionado quando:
  - Ativar o vídeo.
  - Desativar o vídeo.
  - Botão do vídeo selecionado durante uma reunião ao vivo ou uma chamada.
- **callPark** - acionado quando:
  - **A Chamada de** Estacionamento está selecionada no menu **...** .
  - O botão **Recuperar** está selecionado.
  - **Atender** está selecionado na caixa de diálogo recuperar.
  - **Cancelar** está selecionado na caixa de diálogo recuperar.
- **callPreferenceSetting** - a configuração do aplicativo de preferência de chamada.
- **callsTabNewCall** - **Nova chamada** está selecionada na guia **Chamadas**.
- **callTransfer** - é iniciada uma transferência de chamada.
- **callVoicemailTab** - **guia da Caixa de correio** selecionada em chamadas.
- **cameraPermissionCancel** - **Cancelar** está selecionado na caixa de diálogo de permissão da câmera.
- **cameraPermissionGoToSettings** - **as Configurações** são acessadas da caixa de diálogo de permissões da câmera.
- **cancelEditMeeting** - marcar o botão **Fechar** enquanto estiver na página Agendador de reunião, depois de selecionar **Editar reunião**. Isso registra quando um usuário abandonar a seleção editar reunião.
- **cancelFileShare** - **Cancelar** está selecionada na caixa de diálogo de confirmação.
- **cancelFileUpload** - **x** está selecionado na caixa de diálogo para upload.
- **cancelMeeting** - marcar **Cancelar evento** na página de detalhes da reunião. Utilizado para obter dados agregados sobre o número de reuniões canceladas.
- **cancelNavigationToLink** - o cancelamento da navegação foi escolhido.
- **cancelRequestToJoinTeam** - cancelar solicitação para entrar em uma equipe.
- **cancelRequestToJoinTeamError** - erro com uma solicitação de cancelamento de ingresso.
- **cancelNewMeeting** - para registrar seleções abandonadas de Criar reunião e verificar o que as causou quando:
  - O botão **Fechar** é selecionado na página Agendador de reunião.
  - O botão **Fechar** é selecionado na página Agendador de reunião depois de selecionar **Editar reunião**.
- **cardView - No AS assigned** - exibição e renderização do cartão. Os cartões são construções essenciais da plataforma, e a medição do uso e do padrão são necessários para compreender o uso da plataforma e ficar de olho nos possíveis problemas no lado do cliente. Esse item é necessário para medir qualquer erro ao ingressar a uma equipe.
- **castPpt** - o evento é disparado quando:
  - Uma opção do PowerPoint é selecionada.
  - Um determinado PowerPoint é selecionado.
  - A pasta Teams e Canais é selecionada na página do seletor de arquivos.
  - Selecionar uma pasta do OneDrive na página de seletor de arquivos.
  - Interromper a sessão de conversão.
  - Toca no PiP multitarefa.
  - Selecionar uma opção de exibição do modo de exibição de arquivo.
- **castScreen** - refere-se a:
  - Tocar na opção compartilhar tela.
  - Parar a sessão de compartilhamento de tela.
  - Selecionar uma opção de exibição do modo de exibição de arquivo.
- **center_on_team_clicked** - um usuário centraliza o mapa em grupos com êxito.
- **channelFollow** - ativar as notificações de um canal.
- **channelUnfollow** - desativar as notificações de um canal.
- **channelsActiveSetting** - a configuração de notificação **notifique-me quando estiver ativo na área de trabalho** é alterada.
- **chatCreation** - criação bem-sucedida de chat.
- **changeIsActiveSetting** - alterar a notificação baseada na atividade da área de trabalho.
- **canal** - botão de nova mensagem ou caixa de texto no chat.
- **channelDetails** - informações de navegação de canal para quando:
  - Um cabeçalho de canal é selecionado.
  - A página de detalhes do canal é acessada.
- **channelFollow/channelUnfollow** - seguir ou deixar de seguir um canal.
- **channelNav** - acessar um canal de praticamente qualquer lugar.
- **channelNavTab** - fornece dados de sucesso e de capacidade de descoberta para arquivos no Teams quando:
  - A guia **Arquivos** está selecionada no canal.
  - Há uma resposta do cartão de conector.
- **channelNotificationSettings** - acionado quando:
  - A caixa de diálogo **Nova configuração de notificação** é selecionada.
  - O botão configurações de notificação do canal é selecionado na exibição do canal.
  - Uma configuração de notificação de canal é selecionada.
- **channelSelected** - confirma que um canal foi selecionado com êxito para um novo plano.
- **channelSendMessage** - acionado quando:
  - Uma mensagem de canal é enviada.
  - Um bot é @mencionado em uma caixa redigir.
- **channelTabOverflow** - seleciona a guia **Mais** em um canal.
- **chat** - refere-se a:
  - Um botão de nova mensagem ou caixa de texto do chat.
  - Chat 1:1 selecionado em um item callHistory.
  - Uma seleção de chat 1:1 na lista de chamadas.
- **chat - No AS assigned** - exibir o chat não lido ou editar a lista de chat, especificamente:
  - Selecionando o botão **Concluído** ao adicionar um usuário a um chat.
  - Um filtro de lista de chat é selecionado para filtrar por não lido.
- **chatAddChat** - adicionar um membro ao botão de chat tocado (isso será o mesmo para chat 1:1 e chat em grupo).
- **chatAllowJoinViaLink** - ativa ou desativa os recursos de link de ingresso na página de detalhes do chat.
- **chatAvatarEdit** - controla quantos grupos alteram o avatar na página de detalhes do chat.
- **chatAvatarEditCamera** - acionado quando um usuário edita o avatar a partir de um feed de câmera ao vivo.
- **chatAvatarEditGallery** - acionado quando um usuário edita o avatar a partir da galeria do telefone.
- **chatAvatarEditView** - acionado quando um usuário exibe a imagem de avatar existente.
- **chatListNavConversations** - quando um usuário toca em um item da lista de chat.
- **chatCancelAudioCall** - cancelar uma chamada de áudio do grupo - confirmar diálogo.
- **chatCancelVideoCall** - cancelar uma chamada de vídeo do grupo - confirmar diálogo.
- **chatCM_CopyText** - tocar em **Copiar texto** em um menu contextual do chat.
- **chatCM_DeleteMessage** - tocar em **Excluir mensagem** em um menu contextual do chat.
- **chatCM_edit** - tocar em **Editar** em um menu contextual do chat.
- **chatCM_Forward** - tocar em **Encaminhar** em um menu contextual do chat.
- **chatCM_markUnread** - tocar em **Marcar como não lida** em um menu contextual do chat.
- **chatCM_save** - tocar em **Salvar** em um menu contextual do chat.
- **chatCM_SeenBy** - tocar em **Visto** em uma opção do menu contextual. Confirmações de leitura, como lidas por (readby).
- **chatContactsEnter** - a guia **Contatos de chat** for entrada.
- **chatDetails** - fornece dados de sucesso e de descoberta para uma página de detalhes do chat quando:
  - Um cabeçalho de chat é selecionado.
  - Uma página de detalhes do chat for acessada.
- **chatRecentEnter** - a guia **Chat recente** for entrada.
- **chatSendMessage** - enviar uma mensagem de chat.
- **chatShareLink** - controla quantos usuários enviam um link de convite para o grupo.
- **chatStartAudioCall** - acionado quando:
  - O botão de chamada de áudio 1:1 for tocado.
  - Tocar no botão **Áudio** em um resultado de pesquisa.
  - Tocar no botão **Iniciar chamada** à direita.
  - Chamada de áudio 1:1 tocada de um item callHistory.
  - Chamada de áudio 1:1 tocada de um item da caixa postal.
  - Posicionar uma chamada de áudio de grupo - confirmar diálogo.
- **chatStartAudioCallOnBehalfOf** - o representante iniciar uma chamada na folha de ações como Chefe.
- **chatStartAudioCallOnBehalfOf** - o representante iniciar uma chamada na folha de ações como Eu mesmo.
- **chatStartAudioCallSFB** - o botão de chamada de áudio1:1 for tocado.
- **chatStartVideoCallCall** - acionado quando:
  - O botão de chamada de vídeo 1:1 é tocado.
  - Tocar no botão de vídeo	em um resultado de pesquisa.
  - Chamada de vídeo 1:1 tocada de um item callHistory.
  - Posicionar uma chamada de vídeo de grupo - confirmar diálogo.
- **chatStartVideoCallSFB** - o botão de chamada de vídeo 1:1 é tocado.
- **chatWithMeetingParticipants** - selecionar a guia **Chat** na página de detalhes da reunião.
- **checkListAddClicked** - **Adicionar um item** está selecionado no modo de exibição de detalhes da tarefa para a seção da lista de verificação.
- **checkListItemAdded** - um item da lista de verificação é criado em uma tarefa.
- **checkListItemDeleted** - um item da lista de verificação é excluído de uma tarefa.
- **checkListItemUpdated** - um item da lista de verificação é atualizado em uma tarefa.
- **channelPickerClicked** - confirma que o seletor de canal foi iniciado com êxito.
- **checklistSeeAllClicked** quando o botão **Ver todos os** é selecionado dentro de detalhes da tarefa para exibir todos os itens da lista de verificação.
- **chicletExpand** - entenda como os cartões são visualizados em dispositivos móveis e o comportamento da visualização do fechamento.
- **clearFilter** - quando todos os filtros são limpos durante a exibição de uma lista de tarefas.
- **clickPhotoOfficeLens** - selecionar **Tirar foto** - Iniciar câmera (somente Android).
- **clockInEntryTeamSelectionShown** - um usuário seleciona uma equipe para o relógio de ponto sem ter batido ponto.
- **clockInOutClicked** - na tela de registro de entrada, os registros **Registrar entrada** ou **Registrar saída** estão selecionados.
- **clockInOutTriggered** - registre a entrada ou saída do usuário. Isso não será acionado até que você tenha verificado a localização, considerando que a localização seja obrigatória.
- **closedBannerMessage** - acionado quando a mensagem de faixa de uma notificação é fechada.
- **closeLobbyBanner** - número de vezes em que a notificação de lobby é fechada usando o botão **Fechar**.
- **commentAdded** - confirma que um comentário foi adicionado a uma tarefa.
- **commentsClicked** - confirma que o modo de exibição de comentários foi inicializado com êxito.
- **commentUpdated** - Confirma que um comentário foi atualizado com êxito em uma tarefa.
- **companionBannerJoin** - selecionar **Ingressar** na faixa de nível superior.
- **companionDismiss** - ignore a faixa complementar.
- **companionDismissProximity** - ignore a faixa complementar.
- **companionJoin** - a opção ingressar como um complemento está selecionada na folha.
- **companionJoinProximity** - Ingressou pela faixa complementar.
- **completeVaultFRE** - o usuário conclui o processo de geração de uma chave mestra que é usada para criptografar seus dados do Cofre.
- **completionStateChange** - acionado quando um botão de filtro concluído ou não concluído é selecionado no modo de exibição de filtro a partir da lista de tarefas.
- **composeExpandComposer** - botão **Formatar** tocado.
- **composeFilePick** - o seletor de arquivo nativo é iniciado.
- **composeImagePicker** - botão **Imagem** tocado.
- **composeLocation** - **botão de Localização** tocado em redigir.
- **composeMention** - @menção.
- **composeOpenEmoticonPicker** - seletor de smiley tocado.
- **composeOpenFunPicker** - o seletor divertido tocado.
- **composeParticipantAdded** - quando um participante é adicionado ao aplicativo Turnos.
- **composeSearchResult** - seleção de resultado da extensão da mensagem, o que é útil para entender a relevância dos resultados da pesquisa do aplicativo. Também melhora a telemetria de envio de mensagens com dados de aplicativos.
- **composeSelectExtension** - toque em um aplicativo ME.
- **composeSendSmartReply** - um item de resposta inteligente é clicado.
- **composeSendMessage** - melhora a telemetria de envio de mensagens com dados de aplicativos.
- **confirmAudioOn** - um usuário confirma que eles querem o áudio ativado.
- **confirmFileShare** - **Compartilhar** está selecionado na caixa de diálogo de confirmação.
- **consultTransfer** - acionado quando:
  - Selecionar **Transferência** > **Consultar primeiro**
  - Destino de transferência definido como Pessoa
  - Destino de transferência definido como Número de telefone.
- **consultTransferCall** - acionado quando:
  - Uma chamada de consulta é iniciada.
  - Confirmar está selecionado na caixa de diálogo confirmar a transferência.
  - Cancelar está selecionado na caixa de diálogo confirmar a transferência.
  - O botão **Transferência de faixa** é selecionado.
  - O botão **Resumo de faixa** é selecionado.
- **consultTransferChat** acionado quando:
  - Uma chat de consulta é iniciado.
  - Confirmar está selecionado na caixa de diálogo confirmar a transferência.
  - Confirmar está selecionado na caixa de diálogo confirmar a transferência.
  - Um botão **Transferência de faixa** ou **Resumo da faixa** é selecionado.
- **consumeVoiceMessage** - mensagem de voz reproduzida.
- **ContactCard_SeeMoreOOF** - ver mais de uma mensagem de ausência temporária.
- **contactOrganizer** - **Organizador de contatos** selecionado.
- **conversation, tabs** - guia selecionada.
- **copyLink** - copiar um link para uma postagem de canal.
- **contactActivity** - quando o botão para exibir a atividade de um usuário do cartão de visita for selecionado.
- **conversation** - quando um usuário navegar até a guia **Chat** ou **Postagens**.
- **cortanaClose** – quando um usuário descarta manualmente a tela Cortana.
- **cortanaEduCategorySelect** : quando um usuário clica em um item de categoria de dicas de educação.
- **cortanaEduOpen** : quando a página educação exibe uma tela Cortana.
- **cortanaInvoke** - quando a Cortana começa a ouvir.
- **cortanaKWSSwitchToggle** – quando um usuário tocar na opção KWS na página de configurações da Cortana.
- **cortanaMicPermissionDialogButtonClick** - quando um usuário concede ou recusa a permissão de microfone na tela Cortana.
- **cortanaOpen** - quando um usuário abre a tela Cortana.
- **cortanaOptionsApen** - quando o usuário toca no botão opções na tela Cortana.
- **cortanaSafetyFirstActions** - quando o usuário aceita a primeira declaração de segurança.
- **cortanaSafetyFirstLaunch** - quando o usuário abre a Cortana pela primeira vez após a conclusão do TDA.
- **cortanaSettingsOpen** - quando um usuário abre a página de configurações da Cortana clicando no botão de configurações da Cortana na tela Cortana.
- **cortanaStopResponding** : quando um usuário clica no botão cancelar na tela Cortana.
- **cortanaUserSettingsLaunch** - quando o usuário abre as configurações da Cortana nas configurações do Teams.
- **cortanaVoiceSelect** - quando um usuário seleciona a fonte de voz da Cortana na página de configurações da Cortana.
- **createChannel** - fornece dados de sucesso em relação à criação bem-sucedida ou ignorada da criação de um novo canal, quando:
  - O botão **Concluído** é selecionado na página **Criar canal**.
  - O botão **Cancelado** é selecionado na página **Criar canal**.
- **createComposeExtension** - criar o uso da extensão da mensagem ou o uso da ação ME.
- **createConversationClicked** - quando uma conversa é criada com outros funcionários.
- **createDefaultPlannerPlan** - uma lista compartilhada será criada automaticamente quando o aplicativo Tarefas for aberto pela primeira vez por qualquer pessoa desse grupo e verificará automaticamente a lista criada com o serviço Planner. Confirma que a lista de tarefas compartilhadas padrão foi criada com êxito no Planner na primeira vez que um usuário tenta criar uma lista de tarefas compartilhadas.
- **createOrJoinTeam** - o botão **+** é selecionado para criar ou entrar em uma equipe.
- **createPersonalPlan** - uma lista pessoal é criada, verifica a lista criada com o serviço ToDo. Confirma que uma nova lista de tarefas pessoais é criada em ToDo.
- **createPersonalSubtask** - confirma que uma subtarefa pessoal foi criada com êxito.
- **createPersonalTask** - confirma que uma tarefa pessoal foi criada com êxito.
- **createPlan** - confirma que uma lista de tarefas compartilhada foi criada com êxito. Confirma se um plano compartilhado foi criado com êxito na camada intermediária.
- **createPlannerPlan** - uma lista compartilhada é criada, e a lista de verificação criada com o serviço Planner. Confirma que uma nova lista de tarefas compartilhada é criada no Planner.
- **createPlannerTask** - verifica uma chamada para o serviço Planner. Confirma que uma tarefa foi criada com êxito em uma lista de tarefas compartilhadas.
- **createShiftClicked** - quando um gerente seleciona **Criar um turno**.
- **createShiftOrTimeOffClicked** acionado se você selecionar **Criar um turno** ou **Folga**.
- **createTask** - usado para quando a ação de criação falha, e para verificar a chamada para o serviço do Planner. Confirma se uma operação para criar tarefa falhou.
- **createTaskList** - quando um usuário acessa o modo de exibição criar plano da exibição da página inicial.
- **createTeam** - fornece dados de sucesso em relação à criação bem-sucedida ou ignorada da criação de uma nova equipe, quando:
  - O botão **Concluído** é selecionado na página **Criar equipe**.
  - O botão **Cancelar** é selecionado na página **Criar equipe**.
- **createTeam, createChannel** - fornece dados de sucesso ao redor do sucesso da inclusão de membros em uma equipe e a criação bem-sucedida de uma nova equipe quando:
  - O botão **Ignorar** é selecionado na página **Adicionar membros** (primeiro marque o existente).
  - O botão **Concluído** é selecionado na página **Adicionar membros** (primeiro marque o existente).
  - Mostra a confirmação da criação da equipe ou do canal.
- **crossCloudDialogCancel** - **Cancelar** está selecionada para um diálogo entre nuvens.
- **crossCloudDialogCancel** - **Ingressar como convidado** está selecionada para um diálogo entre nuvens.
- **dashboardNav** - um usuário acessa um bloco no painel de chat.
- **dateChanged** - um usuário alterou uma data de turno.
- **datePickerLaunch** - confirma que o seletor de data foi inicializado com êxito.
- **dayClicked** - selecionar o modo de exibição de dia quando o usuário estiver vendo seus turnos.
- **daySaved** - um usuário salva a disponibilidade de dia, salva um dia de turnos.
- **declineTimeOffRequest** - quando um usuário recusar a solicitação de folga. É uma funcionalidade fundamental para a folga, para que o gerente rejeite a solicitação de folga.
- **deleteClicked** - quando **Excluir** estiver selecionado nos detalhes da tarefa, o que exibirá a caixa de diálogo de confirmação.
- **deleteContact** - um usuário exclui um contato particular existente.
- **deleteMeeting** - selecionar o botão **Excluir** na página de detalhes da reunião.
- **deletePersonalTask** - confirma que uma tarefa pessoal foi excluída com êxito.
- **deletePersonalSubtask** - confirma que uma subtarefa pessoal foi excluída com êxito.
- **deletePersonalVaultItem** - o usuário solicita a exclusão de seu Cofre pessoal.
- **deletePlannerTask** - confirma que uma operação de exclusão de tarefa compartilhada foi concluída com êxito.
- **deleteShift** - exclusão de turnos.
- **duration_picker_dismissed** - quando o seletor de duração é ignorado.
- **deleteTask** - verifica com o serviço Planner se uma ação de exclusão teve êxito ou não foi bem-sucedida. Confirma se a exclusão de uma tarefa falhou, ou seja, a exclusão de uma tarefa não teve êxito.
- **deleteVoicemail** - excluir item de caixa postal tocado.
- **demotedToAttendee** - um usuário rebaixa um botão do apresentador - **Alterar** na caixa de diálogo.
- **denyParticipant** - número de vezes que um usuário nega a entrada de alguém da lista.
- **descriptionChanged** - confirma que a descrição de uma tarefa compartilhada foi alterada com êxito.
- **descriptionClicked** - quando um usuário seleciona **Exibir descrição** nos detalhes da tarefa.
- **detailsTabClicked** - a guia **Detalhes** é selecionada na reunião.
- **deviceAddressBookSync** - acionado quando a sincronização do catálogo de endereços é habilitada na página de configurações.
- **deviceAddressBookUnsync** - acionado quando a sincronização do catálogo de endereços é desabilitada na página de configurações.
- **deviceSyncEnabled** – Sincronização de dispositivo habilitada.
- **deviceSyncDisabled** – Sincronização de dispositivo desabilitada.
- **dialIn** - um usuário opta por participar por telefone em uma reunião (vários locais).
- **dialInBadNetworkBanner** - **Participar por telefone** está selecionada para uma faixa de conexão ruim.
- **dialInBadNetworkBannerCancel** - a opção **Participar por telefone** é cancelada na caixa de diálogo nativo.
- **dialInBadNetworkBannerConfirm** - a opção **Participar por telefone** é confirmada na caixa de diálogo nativo.
- **dialInCall** - **Chamada** é selecionada na janela pop-up **Participar por telefone**.
- **dialInCancel** - **Cancelar** é selecionada na janela pop-up **Participar por telefone**.
- **dialOutCall** - acionado quando um usuário:
  - Ingressa no Modo de condução.
  - Seleciona **Chamada** na janela pop-up **Telefonar-me novamente**.
- **dialOutCallAAD** - quando um número é selecionado do **Meus números** na folha de ações.
- **dialOutCallRecent** - quando um número é selecionado dos números recentes anteriores na folha de ações.
- **dialOutCancel** - **Cancelar** está selecionado na janela pop-up **Telefonar-me novamente**.
- **dialOutDialog** - **Novo número** é selecionado na folha de ação.
- **dialOutFailRetry** - **Repetir** é selecionado a partir de uma faixa de falha.
- **DialPad** - o botão de **Teclado de discagem** é selecionado na lista de chamadas.
- **directShare** : Compartilhou o link de um convite por um aplicativo Sms/e-mail.
- **disableCategory** - desabilita um tipo de notificação ou desabilita as notificações de chamadas de entrada.
- **disabled** - **Ignorar as notificações** está selecionado na OOBE (FRE). Isso fornece dados de sucesso importantes para ignorar a notificação no fluxo FRE.
- **disableQuietDays** - Dias silenciosos desativados. Contém telemetria de sucesso para dias silenciosos.
- **disableQuietHours** - horas silenciosas desabilitadas.
- **discoverTeams** - acesse a página Procurar e Ingressar às equipes.
- **Dismiss_earlycancelledCQF** - o formulário CQF de chamada cancelada anteriormente é ignorado.
- **Dismiss_ratemycallCQF** - o formulário CQF classifique a minha chamada é ignorado.
- **Dismiss_ratemyliveeventCQF** - o formulário CQF classifique meu evento ao vivo é ignorado.
- **dismissBadNetworkBanner** - **Ignorar** está selecionado para uma faixa de conexão ruim.
- **dismissFlyout** - **o botão Ignorar** é selecionado.
- **dismissModality** - o seletor de modalidade é encerrado sem compartilhamento.
- **dismissModalityPicker** - o botão **Seletor de modalidade** é selecionado.
- **dismissReadReceiptsNotice** - **Entendi** é selecionado em uma notificação de recursos.
- **dismissStartRecording** - ignora erro ao iniciar a gravação.
- **dismissStopRecording** - ignora erro ao interromper a gravação.
- **dismissUseWifiForVideoBanner** - acionado quando um usuário descarta uma faixa:
  - Isso informa ao usuário que o vídeo do participante remoto está bloqueado e que os usuários têm que mudar para o WiFi para vê-lo.
  - Isso informa ao usuário que os usuários têm que mudar para o WiFi para compartilhar o vídeo.
- **DLPDelete** - um usuário excluiu uma mensagem bloqueada.
- **DLPEdit** - um usuário editou uma mensagem bloqueada.
- **DLPOverride** - um usuário anulou uma mensagem bloqueada.
- **DLPOverrideReport** - um usuário relatou falso positivo e anulou a mensagem.
- **DLPReport** - um usuário relatou falso positivo.
- **DLPResolve** - um usuário tentou resolver uma mensagem DLP.
- **DLPSeeOriginal** - um usuário tocou para ver uma mensagem original.
- **downloadFile** - ajuda a:
  - Determinar se uma operação de download foi iniciada.
  - Determinar se um arquivo foi baixado com êxito.
- **dragDatePickerHandle**
- **dtmfPSTNCall** - o botão DTMF no teclado discagem é tocado.
- **dueDateChanged** - acionado quando um usuário atribui uma duedate a uma tarefa.
- **dueDatePickerClicked** - acionado quando o botão **Data de conclusão** é selecionado nos detalhes da tarefa, abrindo a página do seletor duedate.
- **dueDateSelected** - acionado quando um usuário aplica um filtro por duedate enquanto exibe uma lista de tarefas.
- **dueDateUnselected** - acionado quando um usuário desaplica um filtro por dueddate enquanto exibe uma lista de tarefas.
- **edit** - **botão Editar** em uma mensagem de chat.
- **editChannel** - um usuário seleciona um botão para editar um canal possuído ou administrado por ele.
- **editContact** - um usuário edita um contato particular existente, isso pode ser feito acessando o cartão de visita.
- **editMeetingResponse** - edite a resposta da reunião na página de detalhes da reunião.
- **editNavigation** - **Reordenar** é selecionada no menu **Mais** para editar a ordem dos aplicativos na barra inferior.
- **editRsvpMeetingOptions** - selecionar **RSVP** para alterar da seleção anterior.
- **editShiftClicked** - edite um turno.
- **editSmartReply** - um item de resposta inteligente é editado.
- **editTeam** - um usuário toca em um botão para editar uma equipe que possui ou administra.
- **editTeam, editChannel** - relacionados ao sucesso na adição de membros de uma equipe e à criação bem-sucedida de uma equipe existente quando:
  - O botão **Cancelar** é selecionado na página **Adicionar membros** (equipe ou canal existente).
  - O botão **Concluído** é selecionado na página **Adicionar membros** (equipe ou canal existente).
- **emergencyCall** - plano de chamadas para chamada de emergência.
- **emergencyCallDirectRouting** - roteamento direto da chamada de emergência.
- **emergencyCallLocationPolicyBased** - DialEmergency usando o teclado de discagem.
- **emergencycallSecurityDeskNotify** - chamada de emergência, suporte de segurança informado.
- **enableCategory** - relacionados às configurações de notificação ao habilitar:
  - Um tipo de notificação.
  - Notificações de chamadas recebidas.
- **enabled** - relacionado à habilitação da notificação no fluxo da OOBE (FRE):
  - **Habilitar notificações** é selecionada na OOBE (FRE).
  - Habilitar está selecionado em um lembrete.
- **enabled/disabled** - permissões de chamada ou permissões de contato (somente Android).
- **enabled, notNow** - botão de solicitação de permissão de notificação **Aceitar**, permissão de notificações da OOBE (FRE) (iOS). Isso mostra quantas pessoas habilitaram o recurso de notificação e fornece informações.
- **enablediOSPrompt** - um usuário realmente ativa notificações na solicitação de permissões de notificações do iOS. Isso fornece informações sobre os usuários que realmente habilitam as notificações no iOS a partir da solicitação de permissão de notificações.
- **enabledQuietDays** - dias de silêncio habilitados.
- **enableLocationPermission** - quando um usuário habilita permissões de localização para o recurso de compartilhamento de localização.
- **enableQuietDays** -um usuário ativa os dias de silêncio.
- **enableQuietHours** - horas silenciosas habilitadas.
- **endEditing** - **botão Salvar** pressionado.
- **endFileShare** - **Voltar** é selecionada em um diálogo compartilhamento de arquivos.
- **endMyShift** - número de dispositivos no modo compartilhado ou número de vezes desconectado.
- **endPhotoShare** - **x** fora do compartilhamento de fotos.
- **entryPointClicked** - Selecionando **Solicitações** na guia **Agenda**. As solicitações são para quando um funcionário da linha de frente (FLW) está solicitando um turno de trabalho, etc.
- **endPSTNCallSelected** - um usuário termina uma PSTN e uma chamada de conteúdo.
- **endPSTNCallShown** - um usuário é instruído a finalizar uma chamada PSTN ou uma chamada de conteúdo.
- **endVideoShare** - **x** fora do compartilhamento de vídeo.
- **errorShown** - um erro é exibido.
- **expand/collapse** - seção dos contatos do dispositivo ou contatos da empresa.
- **expandCollapseSection** - toque em um cabeçalho da seção para expandir ou recolher uma seção.
- **Expected: atMention - Android: chatSendMessage - iOS: sendMsg** - @menciona um bot em uma caixa de texto.
- **Expected: botClickCardAction - Android: showCard - iOS: missing** - tocar nos botões de cartão. Os cartões são construções essenciais da plataforma, e a medição do uso e do padrão são necessários para compreender o uso da plataforma e ficar de olho nos possíveis problemas no lado do cliente.
- **Expected: chatSendMessage - iOS: composeSendMessage** - tocar em **Responder** e responder a um bot do chat em um canal.
- **Expected: composeSendMessage - Android: replyChannel - iOS: missing** - tocar em **Responder** e responder a um bot do chat em um canal.
- **Expected: messageLike - Android: reactLike_CM** - curtir uma mensagem do bot.
- **Expected: messageUnread - Android: markAsLastUnread** - opções do menu de contexto de mensagem para uma mensagem do bot.
- **federatedUpgradeNewChat** - o chat herdado é atualizado para nativo.
- **files** - controla se a listagem de arquivos foi feita com êxito na guia arquivos de chat e de canal.
- **fileSelected** - uma apresentação do PowerPoint é selecionada.
- **fileThumbnailPreviewDownloaded** - ajuda a identificar se uma miniatura foi renderizada com êxito para um arquivo.
- **fileThumbnailPreviewFromCache** - captura se a miniatura do cache foi bem-sucedida e ajuda a identificar se a miniatura foi renderizada com êxito para um arquivo.
- **fileThumbnailPreviewNotAvailable** - ajuda a identificar se a miniatura foi renderizada com êxito para um arquivo.
- **fillFrameVideo** - preenche o quadro na folha de ações.
- **firstTimeSignedIn** - evento de entrar ou inscrever acionado por:
  - Êxito na entrada.
  - Primeira entrada bem-sucedida.
  - Os erros de entrada são vistos por um usuário.
  - Registro da telemetria das políticas MAM/MDM implementadas no primeiro logon.
  - Registro dos parâmetros referenciais de instalação do aplicativo após a primeira entrada bem-sucedida.
- **fitToFrameVideo** - ajusta-se ao quadro da folha de ações.
- **flipCamera** - inverter a câmera.
- **forcedUpdateAccept** - um usuário aceita a atualização da versão do aplicativo na caixa de diálogo forçar atualização.
- **forcedUpdateExit** - um usuário fecha o aplicativo, em vez de atualizar a versão do aplicativo na caixa de diálogo forçar atualização.
- **forcedUpdatePrompt**- usado em situações em que os usuários em versões mais antigas, que podem não ter as últimas correções de segurança e privacidade, precisam ser acessados.
- **formattingBold** - um usuário seleciona a formatação em negrito.
- **formattingHighlight** - um usuário seleciona a formatação em destaque.
- **formattingImportant** - um usuário seleciona a prioridade.
- **formattingItatlics** - um usuário seleciona itálico.
- **formattingTextColor** - um usuário seleciona a formatação de cor de texto.
- **formattingUnderline** - um usuário seleciona sublinhado.
- **FRE - No AS assigned** - registro de telemetria das políticas MAM/MDM no lançamento do aplicativo. Telemetria para a integração do Intune para MAM e MDM. Fornece dados de sucesso em caso de falha durante a OOBE (FRE).
- **freActionClicked** - **Comece**, **Tente mais tarde**, ou **Feche** (GPS) é selecionado na OOBE (FRE).
- **freDone** - a experiência OOBE (FRE) foi concluída.
- **freTriggered** - um usuário exibe o relógio de ponto na OOBE (FRE).
- **funSearchQueryEntered** - consulta de Giphy inserida. Os dados de sucesso do recurso de anexo do giphy no Teams.
- **funSelectItem** - imagem Giphy escolhida. Os dados de sucesso do recurso de anexo do giphy no Teams.
- **galleryImage** - imagem carregada - galeria.
- **get_directions_clicked** - o botão **Obter instruções** é selecionado.
- **giphyUserDisabled** - O usuário seleciona para recusar os termos/condições do Giphy.
- **giphyUserEnabled** - O usuário seleciona para aceitar os termos/condições do Giphy.
- **goToNotificationSettings** - acesse a página de configurações de notificação na caixa de diálogo **atualizamos as configurações de notificação**.
- **GPSPromptClicked** - a opção **Permitir** ou **Não Permitir** é selecionada em uma solicitação do sistema operacional. Permintido GPS ou não.
- **group_map_closed** - Um usuário abre a exibição do mapa do chat.
- **group_map_open** - o usuário fecha o modo de exibição do mapa.
- **groupCallJoin** - um usuário une-se a uma chamada de grupo.
- **groupClicked** - controla quando um usuário seleciona o grupo de turno.
- **guideMe** - os usuários selecionam uma faixa que os informa sobre aplicativo 3P que bloqueia notificações e oferece diretrizes para a solução de problemas.
- **hamburgerMenu** - navegar no menu hamburger. O menu hamburger contém ações importantes, como opções de conta, configurações de notificação, configuração de dados e configurações de perfil.
- **handoffComplete** - uma reunião ou chamada foi entregue nesse dispositivo.
- **handoffJoin** uma opção de entrega de reunião é selecionada na folha de ações.
- **hardwareAudioOff** - desative o áudio por meio dos botões de hardware.
- **hardwareAudioOn** - ative o áudio por meio dos botões de hardware.
- **hide** - ocultar o chat.
- **hideChannel** - ocultar um canal da lista de equipes e canais.
- **image** - imagem.
- **inAppNotification** - acionada quando uma notificação é tocada enquanto o usuário está ativo no aplicativo.
- **immediateCallForward** - o destino de encaminhamento imediato de chamadas está definido ou permite o encaminhamento imediato de chamadas (chamadas de toque estão desabilitadas).
- **importanceToggleClicked** - acionado quando o **!** campo é alternado nos detalhes dos itens de tarefa.
- **importantMessage_select** - Um usuário seleciona uma mensagem importante no menu de contexto de prioridade.
- **importantMessageSend** - um usuário envia uma mensagem importante.
- **inCallDialOut** - um usuário seleciona o botão **Telefonar-me novamente** no botão mais opções.
- **initiatePhotoShare** - iniciar o compartilhamento de fotos.
- **initiateVideoShare** - iniciar compartilhamento de vídeo.
- **install** - Instalação ou Evento de instalação.
- **installReferrer** - registro dos parâmetros referenciais de instalação do aplicativo após a primeira instalação bem-sucedida.
- **invisionWhiteboardClicked** - o quadro de comunicações Invision está selecionado:
  - O guia **Arquivos de canal**.
  - O guia de reunião **Arquivos de chat**.
- **inviteFreemium** - tocar no botão **+** na tela Convidar.
- **inviteGuest** - tocar no botão **+** na tela Convidar.
- **joinFromDeeplinkInTeams** - um usuário ingressou por meio de um deep link no aplicativo Teams.
- **joinFromDeeplinkInTeams** - um usuário ingressou por meio de um deep link no aplicativo Teams.
- **joinFromJoinLauncher** - um usuário ingressou de um Iniciador de Ingresso.
- **joinFromNudge** - um usuário que ingressou de uma sugestão.
- **joinFromStore** - um usuário ingressou depois de baixar o aplicativo da App Store.
- **joinMeeting** - detecta o êxito ou a falha de ingressar em reuniões do calendário nas seguintes circunstâncias:
  - Ingressar na reunião por meio do Participar por telefone.
  - Ingressar na reunião por meio do Telefonar-me novamente.
  - Ingressar somente no conteúdo da reunião.
  - Marcar o botão **Ingressar reunião** no modo de exibição da agenda.
- **joinOptionsEdu** - um usuário EDU seleciona opções para ingressar em uma reunião agendada e mostra as opções adequadas.
- **joinTeam** - o botão **Ingressar** é pressionado.
- **joinViaCode** - um usuário participa de uma reunião por meio de um código.
- **labelPickerClicked** - confirma que o seletor de rótulo foi iniciado com êxito.
- **labelSelected** - confirma que um rótulo foi selecionado com êxito.
- **labelUnselected** - confirma que um rótulo foi desassociado com êxito.
- **launchLinksGallery** -quando um usuário entra na galeria de links no painel de controle.
- **launchSlideshow** - o usuário inicializa o visualizador de imagens em tela cheia do Apresentação de Slides a partir de um dos três possíveis locais de recurso do aplicativo. 
- **Fonte de inicialização, como direct, link, appShortcut** - inicia diretamente ou por meio de um link (gravação de gerenciamento de aplicativo móvel (MAM) ou telemetria de gerenciamento de dispositivo móvel (MDM) na inicialização do aplicativo para coletar dados para usuários ativos).
- **lastSearchableAliasTurnedOff** – o usuário desabilitou todos os aliases pesquisáveis para a conta.
- **leaveChat** - confirmar a saída do chat.
- **legacyChatLink** - um link é selecionado para um chat herdado.
- **link** - O usuário iniciou o resgate do link de convite inserindo o aplicativo do Teams.
- **likeAppDismiss** - quando a solicitação pergunta se um usuário gosta do aplicativo ou não e é ignorada sem uma resposta.
- **likeAppNo** - quando a solicitação pergunta se o usuário gosta do aplicativo e recebe uma resposta não.
- **likeAppYes** - quando a solicitação pergunta se o usuário gosta do aplicativo e recebe uma resposta sim.
- **likeMsg** - selecionar **Curtir**.
- **linkPreviewCancel** - entenda o comportamento do fechamento de visualização.
- **listUserClicked** - quando um usuário seleciona um usuário no Trabalhando agora.
- **liveCaptions** - as legendas ao vivo são ativadas ou desativadas.
- **liveEventAdditonalLink** - um link adicional é selecionado.
- **liveEventInfo** - o botão **Informações** é selecionado.
- **liveEventJoin** - um usuário entra em um evento ao vivo.
- **liveEventLeave** - o botão **Sair** é pressionado.
- **liveEventPresenterJoin** - um evento ao vivo é ingressado por um apresentador.
- **liveEventPresenterJoinAsAttendee** - um apresentador de eventos ao vivo ingressa como um participante.
- **liveEventQnA** - o ícone **P e R** é selecionado.
- **liveEventYammer** - o ícone de **Yammer** é selecionado.
- **liveMeetingPushNotificationClicked** - a notificação por push está selecionada.
- **liveMeetingToastClicked** - a notificação do sistema no aplicativo é selecionada.
- **live_location_in_chats_from_profile_clicked** - **Localização ao vivo** é selecionada no modo de exibição de perfil.
- **lobbyPickAudio** - número de vezes que um usuário alterna a saída de áudio do lobby.
- **lobbyToggleMuted** - número de vezes que um usuário ativou ou desativou o microfone do lobby.
- **lobbyToggleVideo** - número de vezes que um usuário ativou ou desativou o vídeo do lobby.
- **logOutClicked** - quando um usuário faz logoff.
- **location_active_tracking** - o dispositivo de um usuário é alternado para o acompanhamento ativo.
- **locationCard** - selecionar um cartão de localização.
- **location_family_sync** - exibir membros de um grupo de Família que foram criados no aplicativo família MSA. Confirma que todos os membros da família que podem receber consentimento estão sendo exibidos.
- **location_data_use_privacy_denied** - O usuário negou a aceitação dos termos de privacidade.
- **location_group_map_sync** - o modo de exibição de mapa é exibido.
- **location_map_load** - carregar modo de exibição do mapa.
- **location_map_markers_load** - carregamento do modo de exibição de mapa. Confirma que os marcadores de localização para todos os usuários que compartilham ativamente são exibidos corretamente no modo de exibição de mapa.
- **location_message_send** - um usuário inicia uma sessão de compartilhamento de local.
- **location_data_use_privacy_denied** - o usuário ignora ou seleciona **Agora não** em um pop-up explicando o uso dos dados do local por TFL.
- **location_data_use_privacy_granted** - Um usuário seleciona **Permitir** em um pop-up explicando o uso dos dados de local pelo TFL.
- **location_settings_open** - um usuário abre as configurações de local.
- **location_sharing_start** - um usuário compartilha seu local em um chat.
- **location_sharing_stop** - um usuário interrompe o compartilhamento de seu local ao vivo em um chat.
- **loginFailed** - o usuário não conseguiu fazer login.
- **loginSuccess** - o usuário conseguiu fazer login.
- **logoutVault** - o usuário sai do aplicativo e, por sua vez, sai do Cofre. 
- **manageBlockedNumbers** - acessar números bloqueados em Configurações.
- **manageVaultKey** - o usuário altera sua escolha de gerenciamento da chave do Cofre (MSA versus auto rastreado).
- **manualSendMessage** - uma mensagem é enviada manualmente.
- **mapAppPicker** - quando um usuário seleciona o aplicativo de mapeamento a ser usado quando eles tocam em um cartão de local.
- **markAsRead** - marcar como lida.
- **markAsUnread** - marcar como não lida.
- **markChannelRead** - um usuário marca uma leitura de canal.
- **messageBookmarkMessage** - salva cartão do conector. Usa a telemetria existente com os dados específicos do aplicativo. Ou salva uma mensagem de bot.
- **markAsLastUnread** - menu de contexto da placa do conector.
- **maskCallerId** - um usuário habilita ou desabilita a configuração de chamada para ocultar a ID de chamada.
- **meetingAttachmentFileClick** : um item de anexo de reunião foi clicado.
- **meetingAttachmentFileOptions** : uma opção de item de anexo de reunião foi clicado.
- **meetingAttachmentSeeMoreClick** : um botão ver mais de um anexo de reunião foi clicado.
- **meetingDetailCalendarList** - página de Detalhes da reunião selecionada na lista de calendário, ou marque a guia **Detalhes** na página de Detalhes da reunião.
- **meetingDetailChatWithParticipants** - conversar com os participantes na página de Detalhes da reunião.
- **meetingDetailDeleteMeetingforSelf** - excluir uma reunião da página de Detalhes da reunião para si mesmo.
- **meetingDetailJoin** - o botão **Ingressar reunião** é selecionado na página de Detalhes da reunião.
- **meetingDetailParticipants** - exibir todos os participantes na página de Detalhes da reunião.
- **meetingDetailScheduledMeeting** - Página de detalhes da reunião selecionada do objeto de reunião agendada (**...**) ou selecione a guia Detalhes de uma reunião agendada.
- **meetingDetailSearchParticipants** - selecionou **Pesquisar** nos participantes da reunião na agenda da reunião.
- **meetingInsightFileClick** - um item de arquivo relacionado a reunião foi clicado.
- **meetingInsightFileLocatorClick** - um botão de dica de locador de conteúdo relacionado a reunião foi clicado.
- **meetingInsightFileOptions** - um item de arquivo relacionado a reunião foi clicado.
- **meetingInsightSeeMoreClick** - um botão ver mais de um anexo de reunião foi clicado.
- **meetingJoinLeave** - deixe tocado-> **x** é tocado depois que o botão **Ingressar** for tocado.
- **meetingJoinNow** - **Entrar agora para VOIP** selecionada.
- **meetingJoinNowWithCallMe** - um usuário participa de uma reunião com **Telefonar-me**.
- **meetingJoinNowWithPSTN** - um usuário participa de uma reunião com Participar por telefone.
- **meetingLeaveChat** - deixar o chat.
- **meetingMuteChat** - ativar o mudo para o chat.
- **meetingNotesCreatedInChatLink** - o chiclet **Anotações de reunião criadas** é selecionada no chat de reunião particular ou no chat no canal de reunião.
- **meetingNotesMentionCharLink** - o link da @menção é selecionado no chat de reunião particular.
- **meetingNotesMentionChartLink** - o link da @menção é selecionado no chat de reunião do canal.
- **meetingNotesTabEntryPoint** - a guia **Anotações da reunião** é selecionada na reunião particular ou em um canal.
- **meetingNotificationSettingsAccepted** - a opção de configurações de notificação foi alterada para Somente aceita.
- **meetingNotificationSettingsAll** - a opção de configurações de notificação foi alterada para Todas.
- **meetingNotificationSettingsNone** - a opção de configurações de notificação foi alterada para Nenhuma.
- **messagePriority_select** - o ponto de entrada de prioridade da mensagem é selecionado.
- **messageSeeOriginal** - um usuário reverte a mensagem traduzida para a original.
- **meetingSeeParticipantsChatDetails** - ver todos os participantes.
- **memberListLoadMore** - rolar para baixo para carregar mais.
- **messagedEditMessage** - um usuário edita uma mensagem.
- **messageShareMessage** - compartilhar uma mensagem.
- **messageTranslate** - um usuário traduz uma mensagem.
- **messageUnabletoEdit** - um usuário não pode editar uma mensagem.
- **meetingUserAnonB2B** - a B2B anônima entrou na reunião.
- **meetingUserAnonB2C** - a B2C anônima entrou na reunião.
- **meetingUserDialIn** - o usuário PSTN (participar por telefone) ingressou na reunião.
- **meetingUserDialOut** - o usuário PSTN Telefonar-me entrou na reunião.
- **meetingUserFederated** - um usuário federado entrou na reunião.
- **meetingUserFreemium** - um usuário freemium entrou na reunião.
- **meetingUserGuest** - um usuário convidado entrou na reunião.
- **meetingUserTenant** - um usuário do locatário entrou na reunião.
- **memeGenerated** - quando um meme é gerado devido a entrada do usuário de dados de imagem e de texto. 
- **meProfileFetch** – indica uma busca e criação de perfil bem-sucedidas.
- **messageCopyMessage** - copiar a mensagem.
- **messageDelete** - excluir a mensagem.
- **messageEditMessage** - editar a mensagem.
- **messageForwardMessage** - um usuário seleciona um ponto de entrada de encaminhamento no menu de contexto da mensagem.
- **messageLike/messageUnlike** - curtir ou descurtir a mensagem.
- **messageMuteSender** - ativar ou desativar mudo para o remetente.
- **messageLike** - curtir o cartão do conector. Usa a telemetria existente com os dados específicos do aplicativo.
- **messageScheduledMeeting** - objeto de reunião no canal selecionado (não apenas para os agendados).
- **messageTriggered** - esse é o momento em que uma notificação é acionada em uma mensagem.
- **micPermissionCancel** - **Cancelar** está selecionado na caixa de diálogo de permissão do microfone.
- **micPermissionGoToSettings** - um usuário navega para as configurações da caixa de diálogo permissões do microfone.
- **MicrosoftWhiteboardClicked** - o quadro de comunicações da Microsoft está selecionado na guia **Arquivos do canal** ou na guia **Arquivos do chat de reunião**.
- **moreOptionsClicked** - acionados quando o menu **...** no canto superior direito é selecionado na tela do editor de itens da tarefa.
- **moveTaskClicked** - opção dentro da lista de mais opções do item da tarefa.
- **msaAddDeleteAliasLinkClicked** - Link para configurar um alias na página perfil do MSA.
- **multiCallEndFromUFD** - número de vezes que um usuário termina a chamada em espera em um cenário de várias chamadas.
- **multiCallResumeFromUFD** - número de vezes que um usuário seleciona para retomar uma chamada a partir da espera.
- **multiCallSwitch** - número de vezes que um usuário seleciona uma opção para alternar a chamada e a lista de chamadas em suspensão é exibida.
- **multipleAccounts** - número de contas do usuário.
- **multipleTenants** - número de locatários por conta.
- **mute** - ativar mudo de um chat.
- **muteOnWhiteboard** - um usuário ativa ou desativa o mudo na tela do quadro de comunicações.
- **muteParticipant** - ativar o mudo para o participante (mover para a folha de ação).
- **my_location_button_clicked** - o usuário centraliza o mapa em sua localização selecionando o botão **Meu local**.
- **my_location_clicked** - o usuário centraliza o mapa em sua localização selecionando o **ponto azul** no mapa.
- **myShiftPickerClicked** - somente registro de log se a solicitação enviada for uma troca ou oferta. O seletor **Meu Turno** é selecionado.
- **nameGroupChat** - nome do chat em grupo.
- **nativeTimeClockBreak** - uma interrupção no relógio de ponto.
- **nativeChatLink** - um link para o chat nativo é selecionado.
- **navActivity** - navegue para a página dos feeds de atividade.

- **navBookmark** - um usuário navega para a guia ou aplicativo **Salvos** na barra inferior ou na bandeja do aplicativo.
- **navCalendar** - mede se um usuário navega para um calendário.
- **navCallingSettings** - um usuário navega para as configurações de chamada.
- **navCalls** - **a guia Chamadas** é tocada.
- **navCamera** - um usuário navega para a guia ou aplicativo **Câmera** na barra inferior ou na bandeja do aplicativo.
- **navChat** - um usuário navega para a guia ou aplicativo **Chat** na barra inferior ou na bandeja do aplicativo.
- **navContacts** - um usuário navega para a guia ou aplicativo **Contatos** ou **Pessoas** na barra inferior ou na bandeja do aplicativo.
- **navDashboardTab** - um usuário navega para a guia **Painel** dentro de uma conversa.
- **navDynamics365** - acionado quando o aplicativo Dynamics365 é aberto.
- **navFiles** - o aplicativo Arquivos é selecionado, controla se um usuário pode iniciar o aplicativo Arquivos na bandeja de aplicativos (iOS).
- **navFilesTab** - o aplicativo Arquivos é selecionado, controla se um usuário pode iniciar o aplicativo Arquivos na barra de navegação inferior (iOS).
- **navMeetings** - **a guia Calendário** é tocada.
- **navNotes** - acionado quando o aplicativo Anotações é aberto.
- **navOrganization** - acionado quando o aplicativo Organização é aberto.
- **navOrgChart** - acionado quando o aplicativo OrgChart é aberto.
- **navPeople** - o evento é acionado quando o aplicativo Pessoas é aberto.
- **navPeopleSettings** - acionado quando você navega até a categoria **Pessoas** no menu Configurações.
- **navPersonalFiles** - o aplicativo Arquivos é selecionado, controla se um usuário pode iniciar o aplicativo Arquivos na barra de navegação inferior (Android).
- **navPhotoTab** - **a guia Foto**.
- **navSaved** - um usuário navega para a guia ou aplicativo **Salvos** na barra inferior ou na bandeja do aplicativo.
- **navSelectPlan** - quando um usuário seleciona um plano compartilhado para navegar do modo de exibição início.
- **navSelectPersonalList** - quando um usuário seleciona um plano pessoal para navegar do modo de exibição início.
- **navSelectSmartList** - quando um usuário seleciona um plano inteligente para navegar do modo de exibição início.
- **navTasks** - acionado quando o aplicativo Tarefas é aberto.
- **navTeams** - tocar em **Ver todas**.
- **navVideocamera** - um usuário navega para a guia ou aplicativo **Câmera** na barra inferior ou na bandeja do aplicativo.
- **navVideoTab** - **guia de Vídeo**.
- **navVoicemail** - um usuário navega para a página de caixa postal.
- **navWalkieTalkie** - um usuário abriu o aplicativo walkie talkie.
- **navWiki** - acionado quando o aplicativo Wiki é aberto.
- **newChat** - um usuário cria um chat.
- **newCall** - toca o botão **Nova chamada**.
- **newCallDialPad** - toca no botão ou guia **Teclado discagem** botão.
- **newCallPeople** - toca no botão ou guia **Pessoas**.
- **noBGActivityDetected** - ultrapassa o limite de falhas de atividades em segundo plano.
- **notBlockedDevice** - um usuário não atinge o limite de falhas de atividades em segundo plano em 30 dias.
- **notNow** - **Agora não** é selecionada no lembrete.
- **notNowUpdate** - UpdateDefer.
- **notification/notification_clicked** - acionada quando uma notificação é tocada.
- **notificationNavChannelConversation** - inicie o aplicativo usando uma notificação para uma conversa de canal.
- **notificationNavChannelThreadConversation** - inicie o aplicativo usando uma notificação para uma mensagem específica em uma conversa de canal.
- **notificationSettingTurnedOff** - desabilite as notificações por push para o aplicativo Teams para Android.
- **notificationNavPreCall** - um usuário recebe uma notificação de início de uma reunião que os direciona para uma tela antes da chamada conforme seleção.
- **ocvFeedback** - relacionados ao desempenho do formulário de comentários OCV.
- **ocvFormCancelled** - um evento enviado quando o formulário de comentários OCV é cancelado e o usuário retorna para o aplicativo.
- **ocvFormOpened** - um evento enviado quando o formulário OCV é aberto.
- **ocvFormSubmit** - um evento enviado quando o usuário seleciona Enviar no formulário de comentários OCV.
- **offerRecipientClicked** - registrado somente se a solicitação sendo enviada é uma oferta. O usuário entra no seletor de membro da equipe para oferecer um turno. Oferecer significa oferecer uma folga do turno.
- **offerSwapShiftFromL1** - o tipo de turno que um usuário tenta oferecer ou trocar em uma lista de turnos. A ação do iOS é **SwipedRight** e a ação do Android é **LongedPressed**.
- **offerSwapShiftFromL1Triggered** - um usuário se oferece para trocar um turno com um outro usuário.
- **officeLens** - acionado quando o aplicativo inicia o recurso de câmera officeLens, quando:
  - Um usuário tenta anexar uma foto à sua mensagem
  - Um usuário tenta tirar uma foto e carregar diretamente na galeria.
- **officeLens ou cameraImage** -imagem da câmera selecionada-câmera padrão ou Office Lens.
- **onBackClicked** - sempre que a seta para voltar está selecionada para voltar a uma página.
- **oneNote** - quando um usuário abre o aplicativo OneNote.
- **open** - tocas as Configurações de notificação.
- **open edit** - a telemetria de uso do wiki - o usuário seleciona para editar o wiki.
- **openApp** - abrir um aplicativo pessoal.
- **openAppDrawer** - **Mais** é selecionada na barra inferior para abrir a gaveta de aplicativos.
- **openEditMeetingForm**- o botão **Editar** é selecionado na página de Detalhes da reunião.
- **openFile** - ajuda a:
  - Identificar um arquivo que pôde ser aberto no chat com êxito.
  - Identificar um arquivo que pôde ser aberto em uma listagem de arquivos.
  - Para verificar se os arquivos podem ser abertos em uma lista do OneDrive.
  - Para identificar arquivos abertos que podem ser abertos a partir de uma lista de canais.
  - Determinar se os arquivos podem ser abertos no chat em grupo.
  - Determinar se um arquivo pode ser aberto com êxito a partir do aplicativo Arquivos.
  - Determinar se um arquivo de mensagem pode ser aberto no chiclet com êxito.
  - Determinar se os arquivos de uma lista recente podem ser abertos com êxito.
  - Determinar se os arquivos de uma lista de arquivos podem ser abertos com êxito.
  - Determinar se um arquivo pode ser aberto a partir de um arquivo de mensagem chiclet.
  - Determinar se os arquivos podem ser abertos com êxito em uma lista de arquivos.
- **openInAppClicked** - opção dentro da lista de Mais opções de um item de tarefa, disponível somente para tarefas pessoais.
- **opensCalendarView** - tocar em **Abrir turnos** na guia **Agenda**.
- **openContactCard** - um usuário toca em um ícone de **Contato** ou um contato no aplicativo Pessoas para iniciar o cartão de perfil desse contato.
- **openContactCard_ReactionSummary** - navegar até o cartão de visita da página de resumo da reação.
- **openFileInApp** - ajuda a identificar se o usuário optou por abrir arquivos fora do Teams versus dentro do Teams.
- **openHamburgerMenu**- o ícone de **Hamburger** (topo à esquerda) é selecionado para abrir o menu lateral para o acesso às configurações, presença e seletor de locatário.
- **openInStream** - abrir um vídeo no Stream.
- **openMeetingDetails** - abrir a página de detalhes da reunião ou Abrir reunião de uma reunião em particular.
- **openModalityPicker** - X = ChatsAndChannels para chats e canais.
- **openNewMeetingForm** - confirma que uma subtarefa pessoal foi atualizada com êxito.
- **openNewMeetingForm** - abrir o agendador ao configurar uma nova reunião.
- **openPhotoLibrary** - selecionar uma biblioteca de fotos.
- **openQuietDays** - navegue até a página de dias silenciosos.
- **openQuietHours** - navegue até a página de horas silenciosas.
- **openReactionHoverBubble** - pressione o botão **Adicionar reação** na página de resumo da reação.
- **openReactionSummary** - invocar a gaveta de resumo da reação.
- **openSettingsSetUpInstructions** - abrir **Configurações** das instruções.
- **openSharedLink** - quando um usuário abre um link do bloco de links do painel ou da galeria de links.
- **openShiftsClicked** - quantas pessoas tocam no ícone **Calendário**.
- **orgChart - No AS assigned** - uso básico de telemetria para o organograma.
- **pageEntered** - um usuário inseriu uma página.
- **parental_consent_grant** - um usuário concede permissão para um secundário em sua MSFamily para usar o recurso de localização dinâmica no TFL.
- **parental_consent_remove** - um usuário revoga permissão para um secundário em sua MSFamily para usar o recurso de localização dinâmica no TFL.
- **pauseVoicemail** - **Pausar** tocado em um item da caixa postal.
- **peoplePickerDismissed** – indica que o Pessoas seletor foi ignorado.
- **peoplePickerInvoked** - os seletores de pessoas são usados em todos os sete lugares no Teams móveis, incluindo (mas não limitados a):
  - Novo seletor de chat.
  - Encaminhar uma mensagem.
  - adicionar participante a uma reunião.
- **personalAppNavBotChat** - navegar até o bot no aplicativo pessoal.
- **personalAppNavBotChat** - navegar até as guias no aplicativo pessoal.
- **photoLibraryPicker** - **abrir a biblioteca de fotos** tocado no seletor de imagem.
- **pickGalleryPhoto** - escolher uma foto na galeria.
- **pickParticipantChatDetails** - escolher um usuário na lista.
- **pickRecentPhoto** - escolher uma imagem recente para compartilhar.
- **pinChannel** - fixar o canal para mostrá-lo acima da lista de equipes e canais.
- **pinSelf** - fixar-me na folha de ações.
- **pinUser** - fixar um usuário na folha de ações.
- **place_created** - O usuário criou um local compartilhado.
- **place_deleted** - O usuário excluiu um local compartilhado.
- **place_edited** : O usuário editou um local compartilhado.
- **play** - reproduzir a gravação.
- **playVoicemail** - **Reproduzir** tocado no item de caixa postal.
- **plusButtonClicked** - selecionar o **botão de adição** (**+**).
- **pptNextSlide** - próximo slide como um apresentador ou na exibição particular.
- **pptPreviousSlide** - slide anterior como um apresentador ou na exibição particular.
- **pptReturnToPresenter** - vá para o slide **Ao vivo** slide (aquele em que o apresentador e todos os outros se encontram).
- **pptStopPresenting** - parar a apresentação.
- **pptTakeControl** - assumir o controle.
- **preJoinAddRoom** - o botão **Adicionar sala** é selecionado na lista suspensa de pré-logon, **Ingressar** é selecionado no cenário **Adicionar sala**.
- **preJoinAudioOff** - o botão **Áudio desativado** é selecionado na lista suspensa de pré-logon.
- **preJoinAutoAddRoom** - **Entrar agora** é selecionado quando uma sala está próxima.
- **preJoinBack** - **o botão Voltar** ou **Fechar** é selecionado.
- **preJoinDenied** - um usuário não consegue ingressar em uma reunião.
- **preJoinDeviceAudio** - **Ingressar com o áudio do dispositivo** é selecionado na lista suspensa.
- **preJoinDialIn** - o botão **participar por telefone** é selecionado na lista suspensa de pré-logon.
- **preJoinDialInCall** - um usuário confirma a solicitação **participar por telefone** no pré-logon.
- **preJoinDialInCancel** - um usuário cancela a solicitação **participar por telefone** no pré-logon.
- **preJoinDialOut** - o botão **Telefonar-me novamente** é selecionado na lista suspensa de pré-logon.
- **preJoinDialOutCall** - um usuário confirma a solicitação **Telefonar-me novamente** no pré-logon.
- **preJoinDialOutCancel** - um usuário cancela a solicitação **Telefonar-me novamente** no pré-logon.
- **preJoinPSTNOptions** - um usuário seleciona uma lista suspensa para outras opções de ingresso.
- **priorityChange** - acionado quando o filtro de prioridade é aplicado ao exibir uma lista de tarefas.
- **priorityPickerClicked** - acionado quando um usuário navega para um seletor de filtro de prioridade na tela de filtro de lista de tarefas.
- **privateMeetingJoin** - **botão de Ingressar reunião** tocado no chat da reunião particular.
- **processInBG** - processa notificações de entrada em segundo plano (Android).
- **processInBG** - processa notificações de entrada em primeiro plano (Android).
- **profileNameSaved** - O nome do perfil foi atualizado.
- **progressItemClicked** - confirma que um usuário abriu com êxito o seletor de andamento de uma tarefa.
- **promotedToPresenter** - o usuário promove um participante - botão **Alterar** na caixa de diálogo.
- **provideFeedbackDismiss** - ignorar a solicitação que pergunta se o usuário deseja enviar comentários sobre o motivo pelo qual não gostou do aplicativo.
- **provideFeedbackNo** - responder não à solicitação que pergunta se o usuário deseja enviar comentários sobre o motivo pelo qual não gostou do aplicativo.
- **provideFeedbackYes** - responder sim à solicitação que pergunta se o usuário deseja enviar comentários sobre o motivo pelo qual não gostou do aplicativo.
- **provideRatingDismiss** - ignorar a solicitação que pergunta se o usuário deseja avaliar o aplicativo na App Store após dizer que gostou do aplicativo.
- **provideRatingNo** - responder não à solicitação que pergunta se o usuário deseja avaliar o aplicativo na App Store após dizer que gostou do aplicativo.
- **provideRatingYes** - responder sim à solicitação que pergunta se o usuário deseja avaliar o aplicativo na App Store após dizer que gostou do aplicativo.
- **proximityPermissionDismissed** - a faixa de permissão é ignorada.
- **proximityPermissionGranted** - a permissão é fornecida na janela pop-up.
- **proximityPermissionViewed** - a faixa de permissão é tocada.
- **pushNotification** - os eventos de acionamento são:
  - Iniciar via notificação.
  - Serviço de notificação por push selecionado.
  - Reconectar-se à notificações por push.
  - **Falha na reconexão** a notificação por push é tocada.
- **quickNotificationAction** - quando um usuário interage com uma das respostas de ações rápidas em uma notificação (como a capacidade de curtir uma mensagem diretamente da notificação por push).
- **quickSelectImagePicker** - seleção rápida.
- **quickStartLiveEventJoin** - o evento de início rápido é ingressado por um usuário.
- **quietHoursValues** - capturar o estado de horas de silêncio no botão de navegação voltar.
- **quotedReplySent** - um usuário enviou uma mensagem de resposta com o tipo de contexto.
- **reactAngry_CM** - reagir com irritado no menu de contexto.
- **reactAngry_HB** - reagir com irritado na bolha hover.
- **reactHeart_CM** - reagir com coração no menu de contexto.
- **reactHeart_HB** - reagir com coração na bolha hover.
- **reactLaugh_CM** - reagir com gargalhada no menu de contexto.
- **reactLaugh_HB** - reagir com gargalhada na bolha hover.
- **reactLike_CM** – reagir com curtir a partir do menu de contexto ou curtir uma mensagem de bot.
- **reactLike_doubleTap** - reagir com curtir a partir do toque duplo.
- **reactLike_HB** - reagir com curtir na bolha hover.
- **reactSad_CM** - reagir com triste no menu de contexto.
- **reactSad_HB** - reagir com triste na bolha hover.
- **reactSurprised_CM** - reagir com surpresa no menu de contexto.
- **reactSurprised_HB** - reagir com surpresa no na bolha hover.
- **reactRemoved_HB** - quando um usuário remove uma reação por meio da experiência de página de resumo da reação.
- **readReceipts** - o usuário habilitou o recurso.
- **redeemInvite** - redenção no aplicativo.
- **resgateLinkInAppStart** - O usuário iniciou o resgate do link de convite a partir do aplicativo do Teams.
- **refreshCalendarList** - puxe para baixo para atualizar o modo de exibição agenda.
- **refreshLinksGallery** - quando um usuário desliza para baixo para atualizar a galeria de links.
- **removeAssignee** - confirma que um destinatário é removido do modo de exibição do seletor de atribuições (em vez de *assignmentRemoved* que é acionado ao selecionar **x** fora do modo de exibição do seletor de atribuições).
- **removeMeeting** - selecionar **Remover do calendário** na página de detalhes da reunião de uma reunião cancelada.
- **removeParticipantFromEditMeeting** - remover um participante depois de selecionar **Editar reunião** na página de detalhes da reunião.
- **removeParticipantFromNewMeeting** - remover um participante da página agenda ao configurar uma nova reunião.
- **removeReplyObject** - um usuário removeu um objeto de resposta do redigir.
- **removeUser** - confirma que um destinatário é removido dentro da exibição do seletor de atribuições (em vez de *assignmentRemoved* que é acionado ao selecionar **x** fora do modo de exibição do seletor de atribuições).
- **removeUser_CM** - quando um usuário remove uma pessoa na lista de participantes do chat.
- **removeUserConfirm** - um usuário confirmou a caixa de diálogo remover usuário.
- **removeUserContextMenu** - um usuário removeu um participante por meio do menu de contexto.
- **removeUserSwipe** - um usuário removeu um participante via deslize.
- **reorderChannelItem** - um usuário reordena os canais fixados.
- **reportAbuseConfirmation** - quando um usuário seleciona o botão **Concluído** na tela de confirmação.
- **reportAbuseOpen** o número de vezes que o botão **Relatar um problema** é selecionado no menu de contexto.
- **reportAbuseSend** - quando um usuário seleciona o botão **Relatar**, a telemetria deve armazenar o tipo de relatório selecionado.
- **replyChain** - botão **Nova mensagem** ou caixa de texto na cadeia de respostas (thread) selecionado.
- **replyChannel** - botão **Responder** selecionado nos canais.
- **replyNavigation** - objeto Responder foi selecionado para navegar até a postagem referenciada.
- **replySendMessage** - enviar resposta do canal.
- **replyViaMsgOptions** - o usuário começou a responder por meio do menu de contexto.
- **replyViaSwipe** - o usuário começou a responder via deslize.
- **requestActedOn** - acionado quando um gerente atua em solicitações de turno aberto.
- **requestActionClicked** - Quando um usuário solicita uma ação, como quando a solicitação de um turno é selecionada (visualização de gerente do Trabalhador na linha de frente (FLW) ou Trabalhador na linha de frente.
- **requestDetailsClicked** - Quando a solicitação de um turno é selecionada (visualização do gerente do Trabalhador na linha de frente (FLW) ou Trabalhador na linha de frente).
- **requestJoinTeam** - **botão Solicitar** pressionado.
- **requestSent** - registra caso tenha sido enviada uma solicitação.
- **requestToJoinTeam** - solicitar ingresso na equipe (pública ou privada).
- **requestRequestToJoinTeamError** - erro com a solicitação de ingresso.
- **requestTypeClicked** - determinar o tipo de solicitação que as pessoas selecionam no seletor de solicitações.
- **resetLocalVault** - o usuário redefine e limpa todos os dados do Cofre de seu dispositivo.
- **resolveIssue** - **Resolver** é selecionado no submenu do solucionador de problemas de notificação para navegar até o aplicativo bloqueador.
- **responseClicked** - um usuário seleciona uma página de resposta.
- **retryButtonClicked** - o botão **Repetir** é selecionado.
- **returnToMessage** - o botão **Retornar** é selecionado para navegar para a mensagem.
- **runningLate** - o usuário está atrasado.
- **safeLink** - link verificado como seguro.
- **saveEditMeeting** - selecionar o botão **Salvar** enquanto estiver na página agendador de reunião após a atualização de uma reunião.
- **saveNewMeeting** - seleciona o botão **Salvar** enquanto estiver na página agendador de reunião. Para registrar as reuniões salvas com êxito e o percentual de reuniões que falharam ao ser criadas devido a um erro no lado do cliente ou serviço.
- **savePlanClicked** - aciona **Criar** é selecionado no novo criador de planos da abertura padrão do aplicativo.
- **dashboardNav** - Um usuário acessa um bloco no dashboard.
- **scenarioDashboardNav** - O usuário navega para a guia do painel dentro de uma conversa (irmã da guia de bate papo).
- **scheduledMeetingJoin** - o botão **Ingressar reunião** é selecionado no objeto da reunião agendada.
- **scrollCalendarList** - mede as rolagens no calendário.
- **scrollDatePicker** - percorre o controle do selecionador de data do calendário.
- **searchAbandoned** - determina se a pesquisa foi abandonada.
- **searchCancelled** - determina se:
  - A pesquisa teve êxito ou se o usuário abandonou a pesquisa.
  - Uma consulta de pesquisa teve êxito.
- **searchContacts** - pesquisa na lista de chamadas.
- **searchInitiated** - determina se a pesquisa pode ser acionada e a fonte de gatilho da pesquisa.
- **searchMeetingParticipants** - pesquisa os participantes para adicionar dentro do formulário do agendador. Para diferenciar o número de compromissos criados versus o número de reuniões criadas.
- **searchResultsClicked** - determina:
  - Se resultados relevantes podem ser encontrados com êxito.
  - Se os resultados da pesquisa forem da guia Todos em vez de um domínio individual.
- **searchTabClicked** - determina:
  - Informações de domínio do resultado da pesquisa: para pessoas, chat, mensagens e arquivos.
  - Se os resultados relevantes foram encontrados com êxito.
- **seeAllMeetingParticipants** - seleciona **Ver todos** na página de detalhes da reunião ou exibe todos os participantes. Registra dados do usuário no funil do calendário, onde os detalhes da reunião do calendário desempenham um papel importante, isso ajuda a validar as seleções para chamadas telefônicas, reuniões do Teams, RSVPs etc..
- **seeMeetingDescription** - abrir a página de Detalhes da reunião ou selecionar **Ver mais** na descrição da reunião na página de Detalhes da reunião. Os dados são registrados no funil do calendário, onde os detalhes da reunião do calendário desempenham um papel importante, isso ajuda a validar as seleções para chamadas telefônicas, reuniões do Teams, RSVPs etc..
- **seeRsvpMeetingOptions** - selecionar **Notifique o organizador** a partir da página pop-up RSVP ou selecionar as opções de **RSVP** na página de Detalhes da reunião.
- **selectActivityType** - captura um gesto de seleção no item do feed.
- **selectCalendarDate** - selecionar uma data específica no controle do seletor de data do calendário.
- **selectDevice** - selecionar um determinado dispositivo no display do aplicativo.
- **selectGeneralSetting** - vá para as configurações gerais.
- **selection** - o contato do dispositivo selecionado ou o contato da empresa selecionado.
- **selectMeetingChicklet** | Reunião.
- **selectMeetingRsvpOption** - selecionar o botão **RSVP** para escolher uma opção.
- **selectMeetingRsvpOptions** - selecionar o botão **RSVP** para escolher uma opção.
- **selectPersonalList** - confirma que o usuário navegou com êxito para uma lista de tarefas pessoais tocando nela.
- **selectPlannerList** - confirma que o usuário navegou com êxito para uma lista de tarefas compartilhadas tocando nela.
- **selectSettingOption** - vá para a guia **Configurações** no menu hamburger.
- **selectTheme** - habilita o tema escuro.
- **selectUser** - confirma que um destinatário foi selecionado com êxito para uma tarefa.
- **selfLongPress** - longa pressão em mim mesmo.
- **Send_earlycancelledCQF** - um usuário envia comentários sobre formulário CQF de chamada cancelada precocemente.
- **send_map_pin_clicked** - um usuário envia um local estático.
- **Send_ratemycallCQF** - um usuário envia comentários sobre o formulário CQF Classifique a minha chamada.
- **Send_ratemyliveeventCQF** - um usuário envia comentários sobre o formulário CQF Classifique a minha chamada.
- **sendForward** - um usuário confirma o envio de uma mensagem de encaminhamento no seletor de encaminhamento.
- **sendImage** - enviar imagem.
- **sendLocation** - enviar localização.
- **sendMsg** - selecionar **Enviar** em responder.
- **sendRequestBulkClicked** - isso é registrado uma vez para cada envio de solicitação em massa.
- **sendRequestClicked** - **Solicitação de turno enviada** é selecionada.
- **sendVoiceMessage** - **botão Registrar** é solto.
- **Setting/Dismiss** - configuração de contatos do dispositivo.
- **settingsNavReadReceiptNotice** - o usuário acessou configurações passando pelo aviso de recursos.
- **settingsOpened** - isso é acionado quando o fuso horário do dispositivo do usuário não corresponde ao fuso horário da equipe e o usuário vai para as Configurações.
- **setupPinVault** – o usuário salva um pin do Cofre para a sua conta. 
- **shareCharmCompleted** – O usuário concluiu o compartilhamento de um link de convite por meio do recurso compartilhamento do aplicativo.
- **shareCharmOpened** – O usuário concluiu o compartilhamento de um link de convite por meio do recurso compartilhamento do aplicativo. 
- **sharefile** - acionado quando **Compartilhar o arquivo** é selecionado. Também ajuda a verificar se:
  - O usuário conseguiu iniciar a operação de compartilhamento de arquivo.
  - O usuário pode compartilhar um arquivo com êxito.
- **shareHistory** - o seletor de histórico de compartilhamento é selecionado.
- **shareInto** - um usuário compartilha algo de outro aplicativo no Teams.
- **sharePlanToChat** - uma lista compartilhada é compartilhada manualmente do aplicativo Tarefas para o chat de grupo como um chiclet, verificar chiclet enviado por meio do serviço de mensagem de back-end.
- **sharePPTFromChannels** - **Teams e canais** é selecionada.
- **sharePPTFromOneDrive** - **OneDrive** está selecionado.
- **shareRecording** - compartilhar uma gravação.
- **shareScreen** - inicia ou interrompe um compartilhamento de tela.
- **shareShift** - as informações que são fornecidas quando um turno é compartilhado.
- **shareShiftsClicked** - os detalhes de um turno aberto.
- **shareTray** -  **Compartilhar...** é selecionado na planilha de ações.
- **shiftAssigneeClicked** - o modo de exibição Calendário de turnos mostrando os detalhes específicos dos turnos.
- **shiftDetails** - permite ver os detalhes de um turno.
- **shiftDetailsCalendar** - o usuário vai para os detalhes de turno.
- **shiftDetailsMyShifts** - tocar em **Calendário** na guia **Agendamentos**.
- **shiftDetailsTodaysCoworkers** - na tela registrar entrada, o botão **Iniciar** ou **Terminar intervalo** é selecionado.
- **shortCircuitContactCount** - o número do catálogo de endereços correspondeu aos contatos recebidos pela busca por contatos.
- **showBanner** - número de vezes que a faixa **Wi-Fi conectado, ausência de internet** aparece.
- **showCard** - tocar nos botões de cartão. Os cartões são construções essenciais da plataforma, e a medição do uso e do padrão são necessários para compreender o uso da plataforma e ficar de olho nos possíveis problemas no lado do cliente.
- **shownReadReceiptNotice** - ao usuário foi mostrado um aviso sobre as opções de configurações.
- **signIn** - **Entrar** é selecionado na página de boas-vindas ou o botão **Entrar** é tocado.
- **SignInWithOTP** - o usuário seleciona a opção para entrar como convidado com uma senha de uso único (OTP). 
- **signUp** - **Criar uma conta gratuita** ou **Inscrever-se gratuitamente** é selecionado.
- **SignUpFromSignIn**- o usuário toca na opção **Criar uma nova conta** na entrada.
- **simultaneousCallForward** - acionado quando:
  - O destino de encaminhamento de chamada simultânea está definido.
  - O encaminhamento de chamadas simultâneas está habilitado (Telefonar-me está habilitado e o toque é definido).
- **skipVerificationForLink** - o usuário optou por ignorar a verificação.
- **smartReply** - botão de alternância para resposta inteligente é clicado.
- **SMSSendMessage** - o usuário envia uma mensagem SMS.
- **sortChanged** - acionado quando o usuário altera a ordem de classificação enquanto exibe uma lista de tarefas.
- **SSOAccountListItem**: acionada quando o usuário toca em uma conta de SSO para entrar.
- **startEditing** - **o botão Editar** é selecionado.
- **startPresentPhoto** - comece a apresentação de fotos.
- **startPresentVideo** - comece a apresentação de vídeos.
- **startPSTNCall** - acionado devido a:
  - PSTN resulta em pesquisa global (pessoas).
  - Chamada PSTN inserida a partir do contactCard do dispositivo.
  - Chamada PSTN inserida a partir da callList.
  - Número DialPSTN usando o teclado de discagem.
- **startRecording** - iniciar gravação.
- **startVoicemailCall** - **Alterar a saudação de caixa postal** selecionada.
- **static_place_selected** - um usuário arrasta o mapa para selecionar um local estático.
- **statusCheckBoxClicked** - acionado quando o item da tarefa é concluído ou não.
- **statusMsgCancel** - um usuário cancela a alteração da mensagem de status.
- **statusMsgExpiry** - um usuário define o tempo de expiração.
- **statusMsgSet** - um usuário define uma nova mensagem de status.
- **statusPageViaContactCard** - um usuário entra na experiência de redação de status por meio de um cartão de visita.
- **statusPageViaHamburger** - um usuário entra na experiência de redação de status por meio do hamburger.
- **stop_location_sharing_logout** - o usuário faz logoff do aplicativo.
- **stopMeetingButton** - o número de vezes que um usuário deixa o lobby sem ser admitido na reunião.
- **stopPresentPhoto** - interromper a apresentação de fotos.
- **stopPresentVideo** - interromper a apresentação de vídeos.
- **stopRecording** - interromper a gravação.
- **structuredMeetingsBannerDismiss** - um usuário ignora a faixa que informa sobre a sua função na reunião.
- **stuckOnConnectingDialInSelected** - **Participar por telefone** está selecionado na gaveta.
- **stuckOnConnectingRetrySelected** - **Repetir** está selecionado na gaveta.
- **stuckOnConnectingShownDismissed** - um usuário ignorou a gaveta.
- **suggested_place_selected** - um usuário compartilha um local estático selecionando um local sugerido.
- **Switching**- o locatário ou a conta é alternado no aplicativo. Isso é necessário para medir problemas de troca de conta/locatário proativamente e fornece uma experiência suave de troca de conta/locatário.
- **switchTeamAction** - um usuário alterna as equipes no relógio de ponto. Isso deverá ser acionado após o usuário selecionar a equipe para a qual deseja mudar.
- **switchTeamsDialogTriggered** - um usuário exibe a guia **Turnos**.
- **tabActionCopyLink** - como os usuários detectam e usam a aba copiar link em dispositivos móveis.
- **tabActionMoreOptions** - entende reticências (**...**) de dentro de uma guia.
- **tabActionOpenInBrowser** - abrir no navegador usado. Isso é necessário para compreender se os usuários preferem abrir uma guia fora do Teams.
- **tabActionOpenInBrowserFromTab** - entender o uso do navegador em uma guia para obter mais opções: capacidade de detecção e uso.
- **tabActionOpenInTeams** - abrir no uso. Isso é essencial para entender se a guia pode ser definida por padrão para ser aberta no Teams.
- **tabActionRemove** - entenda o quão detectável é a opção excluir e o uso do recurso.
- **tabActionRename** - entenda o quão detectável é a opção renomear e o uso do recurso.
- **tabActionSetting, Android - fix** - como os usuários descobrem e usam a guia configuração em dispositivos móveis.
- **table** - selecionar uma tabela.
- **tabListMoreOptions** - entenda o uso das opções mais para uma guia.
- **tabOpen** - observa o sucesso das guias de abertura ou se há problemas com a maneira a qual as guias são abertas.
- **tabViewed** - registrado somente se a solicitação sendo enviada é uma troca, para as entradas no seletor de **Turno da equipe**.
- **takePhoto** - tirar uma foto.
- **takePhotoPicker** - **Tirar foto** selecionado no seletor de imagens.
- **tapChicletExpand** - como os usuários visualizam os cartões no celular.
- **tapDatePickerHandle** - expandir o controle do seletor de data do calendário.
- **tapSettings** - o número de usuários reconfigurando aplicativos no celular.
- **tasksAppLaunchAdaptiveCard** - o aplicativo Tarefas é aberto a partir de um adaptivecard em um chat de grupo, verificar a inicialização do aplicativo por meio da URL do serviço IC3.
- **tasksAppLaunchComposeExtension** - o aplicativo Tarefas é aberto a partir da extensão de redação em um chat de grupo, verificar a inicialização do aplicativo pelo serviço MT.
- **tasksAppLaunchDashboard** - o aplicativo Tarefas é aberto a partir do bloco do painel ou plano específico, verificar a inicialização do aplicativo pelo serviço MT.
- **tasksAppLaunchDashboardSeeAll** - o aplicativo Tarefas é aberto a partir do botão do painel **Ver todas**, verificar a inicialização do aplicativo pelo serviço MT.
- **tasksAppLaunchDefault** - o aplicativo Tarefas é aberto a partir da gaveta inferior, verificar a inicialização do aplicativo pelo serviço MT.
- **tabCalendarClicked** - um usuário escolheu uma equipe no seletor de equipe.
- **teamChannelChanged** - acionado quando um usuário seleciona e navega para um plano da lista de planos. Somente enviado para appInsights, não para Aria.
- **teamCreate** - um usuário seleciona a opção para criar uma nova equipe.
- **teamEdit** - um usuário edita algum aspecto de uma equipe que possui ou administra.
- **teamNav** - opções do menu Exibir para uma equipe.
- **teamsDeviceCallResumed** - um usuário com um periférico conectado Bluetooth (encaixe no celular) reativa uma chamada a partir da espera.
- **teamSelectedClicked** - quando um usuário seleciona **Equipe selecionada** para um quadro de horários.
- **teamShiftPickerClicked** - quando um usuário adiciona uma nova entrada de intervalo. O evento é registrado depois que o usuário salva as alterações.
- **tenantSwitch** - em Alternar Locatário. Inclui métricas de sucesso para o recurso MTMA (vários locatários e várias contas), isso ajuda a identificar e corrigir problemas de forma proativa e oferecer uma experiência de mudança suave.
- **tenantSwitchUnsupportedError** - Erro sem suporte de locatário (quando um usuário vê o erro). Inclui métricas de sucesso para o recurso MTMA (vários locatários e várias contas), oferece telemetria para os erros de conta ou troca de locatário, para que possamos identificar e corrigir problemas de forma proativa e oferecer uma experiência de mudança suave.
- **timeClockClicked** - um usuário seleciona o botão **Relógio de ponto** na guia Meus turnos.
- **timeOffReasonClicked** - determinar se um motivo para a folga está citado.
- **timesheetAddClicked** - quando um usuário adiciona uma anotação às suas edições de intervalo. O evento é registrado depois que o usuário salva as alterações.
 **timesheetBreakAdded** - adicionar uma nova entrada no relógio. O evento é registrado depois que as mudanças são salvas.
- **timesheetBreakEdited** - quando um usuário confirma seu quadro de horários. O evento é registrado quando o usuário clica aceitar na caixa de diálogo restrita.
- **timesheetBreakNoteAdded** - quando um usuário exclui seu quadro de horários. O evento é registrado quando o usuário confirma a exclusão na caixa de diálogo restrita.
- **timesheetClockAdded** - quando um usuário seleciona editar em um quadro de horários.
- **timesheetClockEdited** - Quando um usuário seleciona Salvar em um quadro de horários editado.
- **timesheetConfirmed** - quando um usuário adiciona uma anotação às suas edições do quadro de horários. O evento é registrado depois que o usuário salva as alterações.
- **timesheetDeleted** - se um usuário possuir ou não um conjunto de lembretes de turnos e a quantidade de minutos antes de um turno que um usuário deseja ser alertado sobre.
- **timesheetEditClicked** - telemetria de configuração do usuário.
- **timesheetEditSaved** - um usuário toca em uma folha de ponto do perfil de um usuário para abrir a folha de ponto desse usuário.
- **timesheetNoteAdded** - para exibir uma solicitação de folga aprovada.
- **titlechanged** - acionado quando o título de um item de tarefa é alterado, aciona em cada alteração de caractere.
- **toast** - a notificação do sistema no aplicativo é selecionada.
- **toggleChannelsInChat** - ativar ou desativar o recurso. Inclui métricas de sucesso para conversas unificadas e experiência de canal.
- **toggleClicked** - um botão de alternância é selecionado.
- **transferNow** - acionado quando:
  - Um usuário seleciona **Transferir** > **Transferir agora**.
  - Destino de transferência está definido como uma Pessoa.
  - Destino de transferência está definido como uma Número de telefone.
- **translateFailed** - a tradução falhou (excluindo offline). Inclui métricas de sucesso para o recurso de tradução de mensagens.
- **place_created** - O usuário criou uma cerca geográfica.
- **place_deleted** - O usuário excluiu uma cerca geográfica.
- **unansweredCallForward** - um destino de encaminhamento de chamada não respondida está definido. Também habilita o encaminhamento de chamadas não respondidas (chamadas Telefonar-me estão habilitadas e Se não respondida é habilitada).
- **unblockCaller** - desbloquear:
  - Contato ou número na folha de ações.
  - Contato ou número de um cartão de visita.
  - Número das configurações.
- **unblockChat** - desbloquear um chat no bot.
- **unpinChannel** - desafixar um canal.
- **unpinSelf** - desafixar-se da folha de ações.
- **unpinUser** - desafixar um usuário da folha de ações.
- **unsafeLink** - um link foi determinado inseguro.
- **updatePersonalTask** - confirma que uma tarefa pessoal foi atualizada com êxito.
- **updatePlaybackSpeedVoicemail** - o valor de velocidade de reprodução da caixa postal é alterado.
- **updateTask** - confirma falha na ação da atualização de tarefas.
- **updateTaskState** - confirma que o estado da tarefa foi atualizado. Ação.
- **upgrade** - selecionar o botão **Atualizar** no menu **Mais**.
- **uploadFile** - um usuário seleciona **Carregar do dispositivo**.
- **uploadSelectedFile** - acionado sob essas circunstâncias:
  - Carregar arquivos no canal com êxito.
  - Carregar arquivos no chat com êxito.
  - Carregar arquivos na janela de resposta.
  - Carregar arquivos no chat em grupo com êxito.
  - O uso do cenário principal.
  - O início do cenário de carregamento no canal.
  - O início do cenário de carregamento no chat.
  - O início do fim do cenário de carregamento no canal.
  - Carregar um arquivo na guia **Arquivos** com êxito.
  - Se uma solicitação for acionada durante o carregamento do arquivo.
  - Se um arquivo selecionado for carregado com êxito.
- **uploadSelectFile** - selecionar um arquivo com êxito; Selecionar o botão **Carregar o arquivo** com êxito.
- **urgentMessageSelect** - seleciona uma mensagem urgente no menu de contexto de prioridade.
- **urgentMessageSend** - envia uma mensagem urgente.
- **url** - URL.
- **urlPreview** - visualização da URL.
- **urlPreviewAdd** - adicionar a visualização da URL.
- **urlPreviewOpen** - a visualização da URL é aberta.
- **urlPreviewRemove** - a visualização de URL é removida.
- **userconfiguration** - para exibir uma solicitação de folga pendente.
- **userJoinedViaShareLink** - um usuário ingressou em uma reunião a partir de um link.
- **userLongPress** - um pressionamento longo em um participante.
- **userProfileOpened** - um usuário seleciona um ícone de **Usuário** para abrir um perfil de usuário.
- userTimesheetOpened** - um usuário seleciona um quadro de horários de um perfil de usuário para abrir o quadro de horários dessa pessoa.
- **useWifiForAudioDialog** - um usuário seleciona **OK** enquanto o sistema solicita, enquanto um administrador tiver bloqueado chamadas de áudio e vídeo no celular.
- **useWifiForVideoDialog** acionado quando:
  - **OK** é selecionado enquanto o sistema solicitar, enquanto um administrador tiver bloqueado as chamadas de vídeo no celular.
  - Tentativa de habilitar o vídeo na reunião, enquanto um administrador o bloqueou no celular.
  - **OK** é selecionado enquanto o sistema solicitar, enquanto um administrador tiver bloqueado o vídeo em reuniões no celular.
- **videoUserDoubleTap** - tocar duas vezes em um participante de vídeo.
- **viewChannelMembers** - exibir uma lista de membros do canal.
- **viewContactCard** - ContactCard selecionado de:
  - Um item do callHistory.
  - Um item da caixa postal.
  - Uma lista de chamadas.
- **viewed** - um usuário exibiu uma página.
- **viewFullAllDayMeetingList** - modo de exibição agenda em dispositivos móveis.
- **viewLobbyFromBanner** - o número de vezes que um usuário seleciona **Exibir o lobby** em uma faixa de notificação.
- **viewMeetingDetails** - selecionar o menu **...** na página de Detalhes da reunião. Que se refere ao uso do menu **Mais** nos calendários móveis.
- **viewMeetingOccurrence** - abrir os detalhes da reunião de uma instância de uma reunião recorrente. Telemetria para registrar os dados do usuário no funil do calendário, onde os detalhes da reunião do calendário desempenham um papel importante, isso ajuda a validar as Seleções para chamadas telefônicas, reuniões do Teams, RSVPs, e muito mais.
- **viewMeetingSeries** - para registrar o êxito na renderização de uma série de reuniões nas seguintes circunstâncias:
  - Ao migrar de uma instância para a página de detalhes da reunião de série.
  - Ao selecionar **Exibir série** na página de detalhes da reunião.
- **viewOrgChart** - uso básico de telemetria para um organograma.
- **viewRequests** - o botão **Exibir solicitações** é pressionado.
- **voiceDataCollectionOptOut** - um usuário opta por uma gravação fora do celular clicando na faixa.
- **voicemail - No AS assigned** - um orador toca em um item da caixa postal.
- **whiteboardUsed** - um usuário anota em um quadro de comunicações (qualquer ação no WebView).
- **wiki - No AS assigned** - telemetria de uso do wiki.
- **poorNetworkBanner** - faixa de rede ruim mostrada.
- **poorNetworkBanner** - faixa de rede inválida mostrada.

### <a name="panelview"></a>Panelview

> [!NOTE]
> Para obter informações sobre as propriedades de eventos PanelView, consulte [Propriedades enviadas com os eventos PanelView](#properties-sent-with-panelview-events).

- **appInstall**: acionada quando um usuário abre o aplicativo pela primeira vez após a instalação.
- **fileDeleteF** - Acionanda quando uma operação de exclusão de arquivo falha.
- **fileDeleteSucces** - Acionada quando uma operação de exclusão de arquivo é bem-sucedida.
- **filePreview** - Acionada nos seguintes cenários:
  - Quando a opção de compartilhamento é mapeada na tela de visualização de arquivo.
  - Quando a opção Copiar é mapeada na tela de visualização de arquivo.
  - Quando a opção de download é mapeada na tela de visualização de arquivo.
  - Quando uma visualização de arquivo é carregada com êxito.
- **files** - Acionada nos seguintes cenários:
  - Quando um arquivo é visualizado no aplicativo do Teams.
  - Quando a opção de carregamento de arquivo é mapeada na tela de arquivos do OneDrive.
  - Quando a opção "Copiar Link" é mapeada na tela de visualização de arquivo.
  - Quando a tela de compartilhamento de arquivos for descartada.
  - Quando o menu de opções de arquivos é aberto ou quando uma das opções nesse menu é mapeada.
  - Quando a tela de arquivos "in-call" é aberta.
  - Quando um arquivo é mapeado para abrir.
- **filesChannel** - Acionada quando a tela de arquivos de canal é aberta.
- **fileSources** - Acionada quando o menu de opções de arquivos é aberto ou quando uma das opções nesse menu é mapeada.
- **filesPersonal** – Acionada quando um lote de arquivos é carregado na tela de arquivos recentes ou do OneDrive.
- **fileUploadDeleteTried** - Acionada quando um anexo de arquivo é excluído ou desgastado da área da mensagem.
- **fileUploadFloadFload** - Acionada quando uma operação de carregamento de arquivo falha.
- **fileUploadIndividualNotification** - Acionada quando o conteúdo da notificação de upload de arquivo é alterado ou quando há interação com a notificação. As interações podem incluir gestos como deslizar a tela para descartar a notificação ou tocar na notificação, etc.
- **fileUploadSuccess** - Acionada quando uma operação de carregamento de arquivo é bem-sucedida.
- **fileUploadSummaryNotification** – Acionada quando o conteúdo da notificação de resumo de upload de arquivo é alterado ou quando há interação com a notificação. As interações podem incluir gestos como deslizar a tela para descartar a notificação ou tocar na notificação, etc.
- **meetingFiles** - Acionada quando a tela de arquivos de reunião é aberta.
- **meetCtionSheet** – Acionada quando o usuário cria uma reunião do Meet Now.
- **navPersonalFiles** - Acionada quando a navegação para a tela de arquivos é executada.
- **signInSSOPage**: acionada quando o usuário exibe uma página de logon único enquanto estiver conectado.
-- **signInError**: acionada quando o usuário encontra qualquer erro enquanto estiver conectado. Isso é necessário para identificar e corrigir proativamente os problemas que os usuários enfrentam durante a entrada. 
-- **TfLSignInSuccessful**: acionada quando o usuário entra com êxito em uma conta Microsoft pessoal. Isso é necessário para entender a confiabilidade de entrada e inscrição e identificar e corrigir problemas proativamente.
-- **TfWFreemiumSignInSuccessful**: acionada quando o usuário entra com êxito em uma conta freemium. Isso é necessário para entender a confiabilidade de entrada e inscrição e identificar e corrigir problemas proativamente.
-- **TfWSignInSuccessful**: acionada quando o usuário entra com êxito em uma conta corporativa ou de estudante. Isso é necessário para entender a confiabilidade de entrada e inscrição e identificar e corrigir problemas proativamente.
- **appDrawer** - Disparado quando a gaveta de aplicativos é aberta com êxito.
- **appPolicyChange** - Disparado quando um usuário redefine e salva a ordem de novas guias localmente.
- **app_stageview** - Disparado quando uma exibição estendida é renderizada com êxito.

### <a name="scenario"></a>Cenário

> [!NOTE]
> Para obter informações sobre as propriedades de eventos PanelAction, consulte [Propriedades enviadas com os eventos de cenário](#properties-sent-with-scenario-events).
> 
- **acquire_resource_token_interactive**- chamada de serviço necessária que é acionada quando um token de autenticação é adquirido por entrada interativa. 
- **acquire_resource_token_silent**- chamada de serviço necessária que é acionada quando um token de autenticação é adquirido por entrada silenciosa.
- **add_buddy** - Captura o status da adição de um contato.
- **app_crash2** - acionada quando o aplicativo falha inesperadamente. Fornece informações sobre a frequência com que o aplicativo Teams está falhando. 
- **app_incremental_sync_launch** - confirma se a contagem de dados foi atualizada com êxito para inicialização fria.
- **app_incremental_sync_resume** - confirma se a contagem de dados foi atualizada com êxito para inicialização suave/quente.
- **app_start_cold** - para monitorar inicialização fria de aplicativo (somente para Android).
- **app_start_hot** - para monitorar inicialização quente de aplicativo (somente para Android).
- **app_start_warm** - para monitorar inicialização suave de aplicativo (somente para Android).
- **auth_adal_tokens**- chamada de serviço necessária para fazer autenticação silenciosa. Acionada quando um usuário inicia o aplicativo ou o token é atualizado na expiração.
- **chat_add_giphy** - confirma se a ação de renderização do GIF Giphy foi bem-sucedida ou falhou.
- **chat_send_message_sfc**- acionada quando uma mensagem de chat é enviada no chat de interoperabilidade do SfC.
- **cortanaError** - para monitorar o erro ocorrido da Cortana.
- **cortanaView** - para monitorar o aparecimento da tela da Cortana.
- **cortanaRestart** - para monitorar a reinicialização da Cortana.
- **cortanaSetNewConversation** para monitorar a Cortana define uma nova conversa.
- **cortanaSpeechRecognization** para monitorar a latência de reconhecimento de fala da Cortana.
- **cortanaStart** para monitorar o início do back-end da Cortana.
- **cortanaStartListening** para monitorar iniciar ouvir a Cortana.
- **cortanaStopListening** para monitorar para de ouvir a Cortana.
- **cortanaThinking** para monitorar a mudança de estado da Cortana para pensar (aguardando a resposta do serviço).
- **cortanaTokenRefresh** para monitorar a atualização do token da Cortana em primeiro plano.
- **cortanaWarmingUp** para monitorar a inicialização da Cortana (a Cortana está aberta, mas o token ainda está em busca).
- **cortana_admin_policy_refresh** : para monitorar a atualização da política de administração da Cortana.
- **cortana_background_token_refresh** - para monitorar a atualização do token da Cortana.
- **cortana_initialization** : para monitorar as etapas de inicialização da Cortana.
- **cortana_sdk_events** - para monitorar a Cortana e transformar eventos relacionados.
- **cortana_skill_action_execution** – para monitorar a execução da ação da Cortana.
- **cortana_skill_action_delay** – confirma o início da ação de atraso.
- **cortana_watchdog** - para monitorar o processo de recuperação do watchdog da Cortana.
- **create_default_plan_and_nav_to_view** - confirma a criação bem-sucedida de uma lista de tarefas compartilhadas padrão e quanto tempo demora para um usuário chegar na exibição resultante após a ação.
- **create_new_chat_thread_sfc**- acionada quando um novo tópico de chat é criado para um chat de interoperabilidade do SfC.
- **create_personal_plan_and_nav_to_view** - confirma a criação bem-sucedida de uma lista de tarefas pessoais padrão e quanto tempo demora para um usuário chegar na exibição resultante após a ação.
- **create_personal_task** - confirma a criação bem-sucedida de um item de tarefa pessoal.
- **create_planner_plan_and_nav_to_view** - confirma a criação bem-sucedida de uma lista de tarefas compartilhadas e quanto tempo demora para um usuário chegar na exibição resultante após a ação.
- **create_planner_task** - confirma a criação bem-sucedida de um item de tarefa compartilhada.
- **forwardExistingAmsObject** Confirma se a ação de encaminhamento de mídia foi bem-sucedida ou falhou.
- **delete_personal_plan** - confirma a exclusão bem-sucedida de uma lista pessoal de tarefas.
- **delete_personal_task** - confirma a exclusão bem-sucedida de um item de tarefas pessoais.
- **delete_planner_plan** - confirma a exclusão bem-sucedida de uma lista de tarefas compartilhada.
- **delete_planner_plan** - confirma a exclusão bem-sucedida de uma lista de tarefas compartilhada.
- **json_parse_failure**- fornece informações sobre a frequência de problemas de análise JSON.
- **fetch_me_profile** - o status de criação do perfil dos usuários.
- **getProfilePicture**- chamada de serviço necessária para obter a imagem do perfil do usuário. 
- **get_resource_token_async**: chamada de serviço necessária para adquirir tokens para recursos do Azure Active Directory de forma assíncrona.
- **get_resource_token_sync**: chamada de serviço necessária para adquirir tokens para recursos do Azure Active Directory de forma síncrona.
- **get_sender_sub_scenario** - obter o subcenário do remetente na atividade.
- **interactiveAuthNopa2** - acionada quando nenhum usuário de senha é interrompido para fazer autenticação interativa.
- **load_chat_plans_list** - confirma a busca bem-sucedida de planos do Planner para o modo de exibição plano de chat.
- **load_home_page** - confirma a busca bem-sucedida das listas de tarefas pessoais e compartilhadas no modo de exibição de início principal.
- **load_personal_task_list** - confirma a busca bem-sucedida das tarefas de uma lista de tarefas pessoais no modo de exibição da lista de tarefa.
- **load_shared_task_list** - confirma a busca bem-sucedida das tarefas de uma lista de tarefas compartilhada no modo de exibição da lista de tarefa.
- **load_smart_task_list** - confirma a busca bem-sucedida de tarefas de uma lista de tarefas inteligente na exibição da lista de tarefa.
- **meetingAttachmentRender** - confirma a renderização de anexos de reunião.
- **meetingInsightFetch** - confirma a busca de conteúdo relacionado à reunião.
- **meetingInsightLocatorRender** - confirma a renderização da dica de locador de conteúdo relacionado à reunião.
- **meetingInsightRender** - confirma a renderização do conteúdo relacionado à reunião.
- **meetingInsightVisible** - confirma a visibilidade do conteúdo relacionado à reunião.
- **open_image** Confirma se o processamento de imagem em tela inteira foi bem-sucedido ou falhou.
- **rename_personal_plan** - confirma a renomeação bem-sucedida de uma lista pessoal de tarefas.
- **rename_planner_plan** - confirma a renomeação bem-sucedida de uma lista de tarefas compartilhada.
- **save_image** Confirma se a ação de salvar imagem foi bem-sucedida ou falhou.
- **saveMeProfile**- chamada de serviço necessária que é acionada quando o usuário salva o perfil
- **share_image** - confirma se a ação de compartilhamento de imagem foi bem-sucedida ou falhou.
- **smart_reply_enabled** - confirma que a resposta inteligente está habilitada para o usuário atual.
- **smart_reply_received** - confirma que uma sugestão de resposta inteligente foi recebida.
- **smart_reply_banned** - confirma que a resposta inteligente não pode ser exibida para o usuário atual.
- **park_call_for_hold_v2** - Confirma que colocar uma chamada em espera foi bem sucedido ou falhou ao utilizar o call park.
- **unpark_call_for_hold_v2** - Confirma que o recomeço da chamada foi bem sucedido ou falhou, utilizando atender chamada estacionada. 
- **update_planner_task_and_nav_to_view** - confirma a atualização bem-sucedida de um item de tarefa compartilhada e quanto tempo demora para um usuário chegar à exibição resultante após a ação.
- **update_personal_task_and_nav_to_view** - confirma a atualização bem-sucedida de um item de tarefa pessoal e quanto tempo demora para um usuário chegar à exibição resultante após 
- **updatePlannerTask** - Confirma se um usuário atualizou com êxito uma tarefa em uma lista de contatos compartilhados.
- **upload_images** Confirma se a ação de carregamento de imagem foi bem-sucedida ou falhou.
- **upload_voice_messages** Confirma se a ação de carregamento de mensagem de voz foi bem-sucedida ou falhou.
- **voiceMessageUpload** Confirma se a ação de carregamento da mensagem de voz foi bem-sucedida ou falhou.
- **cancel_channel_meeting** Confirma se o cancelamento de uma reunião de canal foi bem-sucedida ou falhou.
- **cancel_meeting** Confirma se o cancelamento de uma reunião foi bem-sucedida ou falhou.
- **cancel_private_meeting** Confirma se o cancelamento de uma reunião foi bem-sucedida ou falhou.
- **edit_channel_meeting** Confirma se a operação de edição de uma reunião de canal foi bem-sucedida ou falhou.
- **edit_meeting** Confirma se a operação de edição de uma reunião foi bem-sucedida ou falhou.
- **server_fetch_agenda_view** Confirma se a sincronização de eventos do calendário usando a API de Camada Central foi bem-sucedida ou falhou.
- **server_fetch_date_picker_view** Confirma se a sincronização de eventos do calendário usando a API REST do Outlook foi bem-sucedida ou falhou.
- **server_fetch_agenda_view_group** Confirma se a sincronização de eventos do calendário usando a API de Camada Central para o grupo TFL foi bem-sucedida ou falhou.
- **server_fetch_date_picker_view_incremental** Confirma se a sincronização incremental de eventos do calendário usando a API REST do Outlook foi bem-sucedida ou falhou.
- **meeting_details** - confirma se a sincronização de detalhes da reunião foi bem-sucedida ou falhou.
- **show_meeting_participants** - confirma se a exibição da lista de participantes da reunião foi bem-sucedida ou falhou.
- **search** - confirma se toda a sessão de pesquisa foi bem-sucedida ou falhou.
- **time_based_retention_shared_channel** - captura dados de desempenho para remover o banco de dados.
- **toggle_searchability** - Captura o status da chamada de rede para carimbar/desmarcar um alias.
- **sync_user_entitlements_and_app_definitions** - Chamada de serviço necessária para buscar aggregatedEntitlements.
- **bots_load_mediacards** - Instâncias de capturas quando os cartões Conector são configurados no chat e no canal.
- **bots_load_one_card**- Captura se pelo menos um cartão estiver presente e carregado ao conversar com um bot.
- **load_assignments** - Captura manipulação excepcional para o aplicativo de atribuição de carregamento.
- **load_channel_tab** - Captura o carregamento da guia do canal. (Só  Android)
- **load_messaging_extension_results** - Captura o carregamento do resultado da pesquisa/consulta de extensão de mensagem. (Só  Android)
- **load_static_tab** - Captura o carregamento da guia estática. (Só  Android)
- **app_authenticated** - Confirma se a autenticação teve êxito e se um token foi obtido. (Só  Android)
- **Block_by_conditional_access** - Ao receber o código de erro de bloqueio de acesso condicional na autenticação. (tentamos forçar a atualização do token primário nesse caso). (Só  Android)
- **get_resource_token_sync** - Disparado quando tentamos buscar token para recursos do aplicativo de forma síncrona. (Só  Android)
- **get_resource_token_async** - Disparado quando tentamos buscar token para recursos do aplicativo de forma assíncrona. (Só  Android)

## <a name="oneplayer-events"></a>Eventos do OnePlayer
> [!NOTE]
> Para eventos OnePlayer, apenas as propriedades listadas nas [Listas de propriedades para eventos OnePlayer](#property-lists-for-oneplayer-events) se aplicam.
### <a name="oneplayer-user-action-events"></a>Eventos de ação do usuário OnePlayer
- **PlayerPlay** - Confirma se o usuário toca no botão play na exibição do OnePlayer.
- **PlayerPause** - Confirma se o usuário toca no botão de pausa na exibição do OnePlayer.
- **PlayerSeek** - Confirma se o usuário busca o vídeo usando a barra de busca ou os botões avançar/retroceder na exibição OnePlayer (só iOS).
- **VideoPlayerSeekForward** - Confirma se o usuário busca o vídeo usando a barra de busca ou os botões de avanço na exibição OnePlayer (só Android).
- **VideoPlayerSeekBackward** - Confirma se o usuário busca o vídeo usando a barra de busca ou os botões de retrocesso na exibição do OnePlayer (só Android).
- **ChangePlaybackSpeed** - Confirma se o usuário selecionou uma nova velocidade de reprodução.
- **changePlaybackQuality** - Confirma se o usuário selecionou uma nova qualidade de vídeo para reprodução.
- **ShareVideo** - Confirma se o usuário tocou no ícone de compartilhamento.
- **PlayerClose** - Confirma se o usuário tocou no ícone de fechamento.
- **VideoCaptionsOn** - Confirma se o usuário ativou as legendas.
- **VideoCaptionsOff** - Confirma se o usuário desligou as legendas.
- **ChangePlayerOrientation** - Confirma se o usuário alterou a orientação do dispositivo.
- **OpenPlayerSettingsMenu** - Confirma se o usuário abriu o menu de configurações.
- **OpenPlaybackSpeedMenu** - Confirma se o usuário abriu o menu de velocidade de reprodução.
- **PlayerAction** - Ação personalizada fornecida pelo aplicativo host.

### <a name="oneplayer-playback-events"></a>Eventos de reprodução de OnePlayer
- **PlayerHeartbeat** - Este é um evento recorrente que envia o status atual do player e a reprodução para um log.

## <a name="property-lists"></a>Listas de propriedades

### <a name="properties-sent-with-all-events"></a>Propriedades enviadas com todos os eventos

| Nome da propriedade                    | Descrição                                                          |
|----------------------------------|----------------------------------------------------------------------|
| EventInfo_Time                   | Tempo de geração do evento                                                |
| EventInfo_Name                   | Nome do evento - usado para diferenciar os tipos de eventos               |
| EventInfo_BaseType/name          | Nome do evento - usado para diferenciar os tipos de eventos em um evento   |
| EventInfo_Source                 | A origem da geração do evento.                                       |
| AppInfo_Language                 | Idioma do aplicativo                                                         |
| AppInfo_ETag                     | ID de experimento atribuída a um usuário                                     |
| DeviceInfo_OsBuild               | Versão do build do sistema operacional                                              |
| UserInfo_Mri                     | Digite uma ID de usuário                                                       |
| Session_RunId                    | Tipo de ID de sessão                                                 |
| DeviceInfo_DetailModel           | Modelo do dispositivo                                                  |
| UserInfo_TimeZone                | Fuso horário do usuário                                                |
| DeviceInfo_OsName                | Nome do sistema operacional                                                       |
| DeviceInfo_NetworkProvider       | Provedor de rede do dispositivo                                              |
| DeviceInfo_Model                 | Modelo do dispositivo                                                         |
| DeviceInfo_NetworkType           | Tipo de rede do dispositivo                                                  |
| UserInfo_Language                | Idioma do usuário – semelhante ao idioma do aplicativo                              |
| client_ring/UserInfo_Ring        | Sinalização de usuário que ajuda a liberar recursos para os pioneiros           |
| UserInfo_Id                      | ID do Usuário                                                              |
| UserInfo_TenantId                | ID do locatário                                                            |
| EventInfo_SdkVersion             | Versão do SDK usada para gerar o evento                               |
| DeviceInfo_Id                    | ID do dispositivo fornecido pelo sistema operacional                                      |
| eventpriority                    | Prioridade de um evento                                                 |
| DeviceInfo_Make                  | Fabricante do dispositivo                                                  |
| AppInfo_Version                  | Versão do aplicativo                                                   |
| DeviceInfo_OsVersion             | Versão do sistema operacional                                                    |
| Session_Id/SessionId             | ID da sessão da solicitação                                            |
| Session_Environment              | Ambiente de sessão                                                  |
| isNetworkIssue                   | Captura informações se houver um problema de rede ao servir a solicitação |
| UserRole                         | Função de usuário em um locatário                                                |
| Tenant_Model                     | Captura se a conta é uma freemium ou uma conta corporativa          |
| licenseType/UserInfo_LicenseType | Tipo de licença atribuída ao usuário                                    |
| UserLocale                       | Localidade em que o aplicativo está sendo acessado                                |
| Intune_sdkVersion                | Versão do SDK do Intune                                            |
| Intune_sdkBundleVersion          | Versão detalhada do SDK do Intune                                   |
| AppInfo_Environment              | Ambiente no qual o aplicativo está sendo acessado                         |

### <a name="properties-sent-with-panelaction-events"></a>Propriedades enviadas com eventos panelaction

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
| Module_Summary        | Resumo do módulo que hospedou a ação do usuário                      |
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

### <a name="properties-sent-with-panelview-events"></a>Propriedades enviadas com eventos panelview

| Panel_Uri          | URI do painel entregue ao usuário                   |
|--------------------|----------------------------------------------------------|
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

### <a name="properties-sent-with-scenario-events"></a>Propriedades enviadas com os eventos de cenário

| Nome da propriedade        | Descrição |
|----------------------|-------------|
| Scenario_Status      | Status de um cenário - abandonar/OK/ERRO |
| Scenario_Step        | Quando um cenário contém várias etapas com diferentes pontos de falha, esta propriedade captura detalhes da etapa |
| Scenario_StatusCode  | A propriedade registra o código do status com base no sucesso ou na falha do cenário |

### <a name="properties-sent-with-trace-events"></a>Propriedades enviadas com eventos de rastreamento

| Nome da propriedade | Descrição                                                                                    |
|---------------|------------------------------------------------------------------------------------------------|
| Trace_message | Contém uma cadeia de caracteres de erro e detalhes sobre os motivos devido ao tipo de falha ocorrido |

## <a name="property-lists-for-oneplayer-events"></a>Listas de propriedades para eventos OnePlayer

### <a name="1-properties-sent-with-all-oneplayer-events"></a>1. Propriedades enviadas com todos os eventos OnePlayer
##### <a name="11-standard-properties"></a>1.1 Propriedades padrão
| Nome da propriedade | Descrição                                                                                    |
|---------------|------------------------------------------------------------------------------------------------|
| eventType | Tipo de evento (AppLogic, ErrorAlert, Performance, UserAction) |
| accountType   | Tipo de conta de usuário (por exemplo, empresa) |
| componente     | OnePlayer |
| idioma      | Local/linguagem do aplicativo |
| plataforma      | Plataforma do OnePlayer (iOS/Android) |
| tenantId      | ID do locatário|
| versão       | Versão do OnePlayer em uso |
| aadUserId     | ID do Usuário |                                

##### <a name="12-player-properties"></a>1.2 Propriedades do jogador
| Nome da propriedade | Descrição                                                                                    |
|---------------|------------------------------------------------------------------------------------------------|
| engineName    | Nome do jogador subjacente (AVFoundation para iOS/ExoPlayer para Android) |
| engineVersion | Versão do sistema operacional |
| loadMode      | Modo de carregamento do player |
| playbackSessionId | ID da sessão para reprodução |

##### <a name="13-host-properties"></a>1.3 Propriedades do host 
| Nome da propriedade | Descrição                                                                                    |
|---------------|------------------------------------------------------------------------------------------------|
| hostIntegrationType | Tipo de integração de host (por exemplo, Pacote e OneUp) |
| hostPlatform  | Plataforma para aplicativo host |
| hostProperties| Propriedades do host, se houver (só iOS) |
| hostApp       | Nome do aplicativo host |
| hostVersion   | Versão do aplicativo host |

##### <a name="14-experimentation-properties"></a>1.4 Propriedades de experimentação
| Nome da propriedade | Descrição                                                                                    |
|---------------|------------------------------------------------------------------------------------------------|
| tocar          | Toque ao qual o usuário pertence |
| hostSettings  | Atributos definidos pelo aplicativo host (moreOptionsEnabled, shareFeatureEnabled, playbackQualityFeatureEnabled, playbackSpeedFeatureEnabled) |
| flightFilters | Descrição |
| flightsOverridden | Bool para voos substituídos ou não |

##### <a name="15-service-properties"></a>1.5 Propriedades do serviço
| Nome da propriedade | Descrição                                                                                    |
|---------------|------------------------------------------------------------------------------------------------|
| contentType   | Tipo de conteúdo sendo veiculado |
| ambiente   | Nome do ambiente  |
| mediaService  | Qual serviço de mídia está sendo usado (SPO, ODB, ODC, IC3-AMS, Desconhecido) |
| mediaType     | Tipo de mídia sendo reproduzida  |
| playbackTech  | Tecnologia de reprodução da mídia  |
| correlationId | ID de correlação para a mídia, se houver |

### <a name="2-properties-sent-with-all-oneplayer-user-action-events"></a>2. Propriedades enviadas com todos os eventos de ação do usuário OnePlayer 
| Nome da propriedade | Descrição                                                                                    |
|---------------|------------------------------------------------------------------------------------------------|
| actionType    | Tipo de ação executada, como tocar, arrastar e deslizar (só iOS)|
| isIntentional | Valor booleano se a ação for intencional ou não (só iOS) |

#### <a name="21-properties-sent-with-changeplaybackquality-event"></a>2.1 Propriedades enviadas com o evento changePlaybackQuality
| Nome da propriedade | Descrição                                                                                    |
|---------------|------------------------------------------------------------------------------------------------|
| currentPlaybackQuality | qualidade de reprodução atual |

#### <a name="22-properties-sent-with-changeplaybackspeed-event"></a>2.2 Propriedades enviadas com o evento ChangePlaybackSpeed
| Nome da propriedade | Descrição |
|---------------|------------------------------------------------------------------------------------------------|
| previousPlaybackRate  | Taxa de reprodução anterior do vídeo (só iOS) |
| currentPlaybackRate   | Taxa de reprodução atual do vídeo |

#### <a name="23-properties-sent-with-playerseek-event-ios-only"></a>2.3 Propriedades enviadas com o evento PlayerSeek (só iOS)
| Nome da propriedade | Descrição |
|---------------|------------------------------------------------------------------------------------------------|
| seekSource    | Fonte de busca (barra de busca, forwardButton, backwardButton) |
| seekValue     | Buscar posição |

### <a name="3-properties-sent-with-oneplayer-heartbeat-event"></a>3. Propriedades enviadas com o evento OnePlayer Heartbeat
| Nome da propriedade | Descrição |
|---------------|------------------------------------------------------------------------------------------------|
| mediaCurrentTime | Tempo de reprodução atual da mídia (só iOS)|
| isLoaded | A mídia está carregada |
| loadTimeMs | Tempo de carregamento em milissegundos |
| numberOfStalls | Número de paradas durante a reprodução (só iOS) |
| bufferingCount | Número de paradas durante a reprodução (só Android) |
| observedBitrate | Taxa de bits observada durante a reprodução (só iOS) |
| avgBitrateBitsPerSecond | Taxa de bits observada durante a reprodução (só Android) |
| playedSeconds | Segundos jogados até o evento |
| rebufferingSeconds | Rebuffering segundos durante a reprodução |
| timeSinceSourceSetMs | Tempo desde que a fonte foi definida (ms) |
| triggerType | Tipo de acionador (buffer, erro, errorLog, canPlayThrough, intervalHeartbeat, conjunto de fontes, descarregar) |
| errorId | ID do erro para o erro, se houver |
| errorCorrelationId | ID de correlação de erro para o erro, se houver |
| errorLog | Log de erros para o erro, se houver |
| errorType | Tipo de erro para o erro, se houver |
| errorMessage | Mensagem de erro para o erro, se houver |
| errorStack | Informações de erro estendidas para o erro, se houver |
| metaUrl | Url meta para mídia |
| odspDocId | ODSP doc ID para mídia |
| siteId | ID do site para mídia |
| teamsCallId | ID de chamada do Teams para mídia, se houver |
