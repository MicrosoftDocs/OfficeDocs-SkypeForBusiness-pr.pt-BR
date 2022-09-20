---
title: Pesquisar o log de auditoria de eventos no Microsoft Teams
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.reviewer: anwara
search.appverid: MET150
description: Saiba como recuperar dados do Microsoft Teams do log de auditoria no portal de conformidade do Microsoft Purview.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f7d94411132b575aa4754aae993f070a36718a2d
ms.sourcegitcommit: 6754f2d11da0afff067f0872acf778a83fd1595e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2022
ms.locfileid: "67808442"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a>Pesquisar o log de auditoria de eventos no Microsoft Teams

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

O log de auditoria pode ajudá-lo a investigar atividades específicas nos serviços do Microsoft 365. Para o Microsoft Teams, aqui estão algumas das atividades auditadas:

- Criação de equipes
- Exclusão de equipes
- Canal adicionado
- Canal excluído
- Configuração de canal alterada

Para obter uma lista completa das atividades do Teams auditadas, consulte [atividades do Teams](#teams-activities) e [Turnos nas atividades do Teams](#shifts-in-teams-activities).

> [!NOTE]
> Eventos de auditoria de canais privados também são registrados como são para equipes e canais padrão.

## <a name="turn-on-auditing-in-teams"></a>Ativar a auditoria no Microsoft Teams

Antes de examinar os dados de auditoria, você precisa primeiro ativar a auditoria no portal de conformidade do Microsoft Purview. Para obter mais informações, [consulte Ativar ou desativar a auditoria](/microsoft-365/compliance/turn-audit-log-search-on-or-off).

> [!IMPORTANT]
> Os dados de auditoria só estão disponíveis a partir do ponto em que você ativou a auditoria.

## <a name="retrieve-teams-data-from-the-audit-log"></a>Recuperar dados do Microsoft Teams a partir do log de auditoria

1. Para recuperar logs de auditoria para atividades do Teams, acesse e <https://compliance.microsoft.com> selecione **Auditoria**.

2. Na página **Pesquisar** , filtre as atividades, as datas e os usuários que você deseja auditar.

3. Exporte os resultados para o Excel para analisá-los melhor.

Para obter instruções passo a passo, consulte [Pesquisar o log de auditoria no centro de conformidade](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#search-the-audit-log).

> [!IMPORTANT]
> Os dados de auditoria só serão visíveis no log de auditoria se a auditoria estiver ativada.

O período em que um registro de auditoria é retido e pesquisável no log de auditoria depende da sua assinatura do Microsoft 365 ou Office 365 e, especificamente, do tipo de licença atribuída aos usuários. Para saber mais, confira a [descrição do serviço & Centro de Conformidade.](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)

## <a name="tips-for-searching-the-audit-log"></a>Dicas para pesquisar o log de auditoria

Aqui estão dicas para pesquisar atividades do Teams no log de auditoria.

:::image type="content" alt-text="Captura de tela da página de pesquisa de log de auditoria no centro de conformidade" source="media/audit-log-search-page.png" lightbox="media/audit-log-search-page.png":::

- Você pode selecionar atividades específicas para pesquisar clicando na caixa de seleção ao lado de uma ou mais atividades. Se uma atividade estiver selecionada, você poderá clicar nela para cancelar a seleção. Você também pode usar a caixa de pesquisa para exibir as atividades que contêm a palavra-chave digitada.

  ![Captura de tela da lista suspensa de atividades na página de pesquisa de log de auditoria](media/audit-log-search.png)

- Para exibir eventos para atividades executadas usando cmdlets, selecione **Mostrar resultados de todas as atividades** na **lista Atividades** . Se você souber o nome da operação para essas atividades, digite-a na caixa de pesquisa para exibir a atividade e selecione-a.

- Para limpar os critérios de pesquisa atuais, clique **em Limpar tudo**. O intervalo de datas retorna ao padrão dos últimos sete dias.

- Se 5.000 resultados forem encontrados, você provavelmente poderá supor que há mais de 5.000 eventos que atenderam aos critérios de pesquisa. Você pode refinar os critérios de pesquisa e executar novamente a pesquisa para retornar menos resultados ou exportar todos os resultados da pesquisa selecionando **Exportar** > **Baixar todos os resultados**. Para obter instruções passo a passo para exportar logs de auditoria, consulte [Exportar os resultados da pesquisa para um arquivo](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#step-3-export-the-search-results-to-a-file).

Confira este [vídeo para usar](https://www.youtube.com/embed/UBxaRySAxyE) a pesquisa de log de áudio. Junte-se a Ansuman Acharya, gerente de programa do Teams, pois ele demonstra como fazer uma pesquisa de log de auditoria para o Teams.

## <a name="teams-activities"></a>Atividades do Teams

Aqui está uma lista de todos os eventos registrados para atividades de usuário e administrador no Teams no log de auditoria do Microsoft 365. A tabela inclui o nome amigável exibido na coluna Atividades e o nome da  operação correspondente que aparece nas informações detalhadas de um registro de auditoria e no arquivo CSV quando você exporta os resultados da pesquisa.

|Nome amigável|Operação|Descrição|
|---|---|---|
|Bot adicionado à equipe|BotAddedToTeam|Um usuário adiciona um bot a uma equipe.|
|Canal adicionado|ChannelAdded|Um usuário adiciona um canal a uma equipe.|
|Conector adicionado|ConnectorAdded|Um usuário adiciona um conector a um canal.|
|Detalhes adicionados sobre a reunião <sup>2 do</sup> Teams|MeetingDetail|O Teams adicionou informações sobre uma reunião, incluindo a hora de início, a hora de término e a URL para ingressar na reunião.|
|Adicionadas informações sobre os participantes <sup>da reunião 2</sup>|MeetingParticipantDetail|O Teams adicionou informações sobre os participantes de uma reunião, incluindo a ID de usuário de cada participante, a hora em que um participante ingressou na reunião e a hora em que um participante saiu da reunião.|
|Membros adicionados|MemberAdded|Um proprietário de equipe adiciona membros a uma equipe, canal ou chat em grupo.|
|Guia Adicionada|TabAdded|Um usuário adiciona uma guia a um canal.|
|Configuração de canal alterada|ChannelSettingChanged|A operação ChannelSettingChanged é registrada quando as atividades a seguir são executadas por um membro da equipe. Para cada uma dessas atividades, uma descrição da configuração que foi alterada (mostrada entre parênteses é exibida na coluna **Item** nos resultados da pesquisa de log de auditoria. <ul><li>Altera o nome de um canal de equipe (**nome do canal**)</li><li>Altera a descrição de um canal de equipe (**descrição do canal**)</li> </ul>|
|Configuração da organização alterada|TeamsTenantSettingChanged|A operação TeamsTenantSettingChanged é registrada quando as atividades a seguir são executadas por um administrador global no Centro de administração do Microsoft 365. Essas atividades afetam as configurações do Teams em toda a organização. Para saber mais, confira [Gerenciar configurações do Teams para sua organização](enable-features-office-365.md). <br>Para cada uma dessas atividades, uma descrição da configuração que foi alterada (mostrada entre parênteses) é exibida na coluna **Item** nos resultados da pesquisa de log de auditoria.<ul><li>Habilita ou desabilita o Teams para a organização (**Microsoft Teams**).</li><li>Habilita ou desabilita a interoperabilidade entre o Microsoft Teams e Skype for Business para a organização (**Skype for Business interoperabilidade**).</li><li>Habilita ou desabilita a exibição de organograma nos clientes do Microsoft Teams (**modo de exibição de organograma**).</li><li>Habilita ou desabilita a capacidade dos membros da equipe de agendar reuniões privadas (**agendamento de reunião privada**).</li><li>Habilita ou desabilita a capacidade dos membros da equipe de agendar reuniões de canal (**agendamento de reunião do canal**).</li><li>Habilita ou desabilita chamadas de vídeo em reuniões do Teams (**vídeo para reuniões do Skype**).</li><li>Habilita ou desabilita o compartilhamento de tela em reuniões do Microsoft Teams para a organização (**Compartilhamento de tela para reuniões do Skype**).</li><li>Habilita ou desabilita essa capacidade de adicionar imagens animadas (chamadas Giphys) às conversas do Teams (**imagens animadas**).</li><li>Altera a configuração de classificação de conteúdo para a organização (**classificação de conteúdo**). A classificação de conteúdo restringe o tipo de imagem animada que pode ser exibida em conversas.</li><li>Habilita ou desabilita a capacidade dos membros da equipe de adicionar imagens personalizáveis (chamadas de memes personalizados) da Internet às conversas da equipe (imagens **personalizáveis da Internet**).</li><li>Habilita ou desabilita a capacidade dos membros da equipe de adicionar imagens editáveis (chamadas de adesivos) às conversas da equipe (**imagens editáveis**).</li><li>Habilita ou desabilita essa capacidade para os membros da equipe usarem bots em chats e canais do Microsoft Teams (**bots em toda a organização)**.</li><li>Habilita bots específicos para o Microsoft Teams. Isso não inclui o T-Bot, que é o bot de ajuda do Teams que está disponível quando os bots estão habilitados para a organização (**bots individuais**).</li><li>Habilita ou desabilita a capacidade dos membros da equipe de adicionar extensões ou guias (**extensões ou guias**).</li><li>Habilita ou desabilita o sideload de bots proprietários para o Microsoft Teams (**sideload de bots**).</li><li>Habilita ou desabilita a capacidade de os usuários enviarem mensagens de email para um canal do Microsoft Teams (**email do canal**).</li></ul>|
|Função alterada de membros na equipe|MemberRoleChanged|Um proprietário de equipe altera a função de membros em uma equipe. Os valores a seguir indicam o tipo de função atribuído ao usuário. <br><br>**1** - Indica a função Membro.<br>**2** – Indica a função Proprietário.<br>**3** - Indica a função Convidado.<br><br>A propriedade Members também inclui o nome da sua organização e o endereço de email do membro.|
|Configuração da equipe alterada|TeamSettingChanged|A operação TeamSettingChanged é registrada quando as atividades a seguir são executadas por um proprietário de equipe. Para cada uma dessas atividades, uma descrição da configuração que foi alterada (mostrada entre parênteses) é exibida na coluna **Item** nos resultados da pesquisa de log de auditoria.<ul><li>Altera o tipo de acesso de uma equipe. As equipes podem ser definidas como privadas ou públicas (**tipo de acesso de equipe**). Quando uma equipe é privada (a configuração padrão), os usuários podem acessar a equipe somente por convite. Quando uma equipe é pública, ela é detectável por qualquer pessoa.</li><li>Altera a classificação de informações de uma equipe (**classificação de equipe**). Por exemplo, os dados da equipe podem ser classificados como alto impacto nos negócios, impacto médio nos negócios ou baixo impacto nos negócios.</li><li>Altera o nome de uma equipe (**nome da equipe**).</li><li>Altera a descrição da equipe (**descrição da equipe**).</li><li>Alterações feitas nas configurações da equipe. Para acessar essas configurações, um proprietário da equipe pode clicar com o botão direito do mouse em uma equipe, selecionar Gerenciar equipe **e, em** seguida, clicar na **guia Configurações** . Para essas atividades, o nome da configuração que foi alterada é exibido na coluna **Item** nos resultados da pesquisa de log de auditoria.</li></ul>|
|Criou um chat <sup>1, </sup> <sup>2</sup>|ChatCreated|Um chat do Teams foi criado.|
|Equipe criada|TeamCreated|Um usuário cria uma equipe.|
|Uma mensagem excluída|MessageDeleted|Uma mensagem em um chat ou canal foi excluída.|
|Todos os aplicativos da organização excluídos|DeletedAllOrganizationApps|Todos os aplicativos da organização foram excluídos do catálogo.|
|Aplicativo excluído|AppDeletedFromCatalog|Um aplicativo foi excluído do catálogo.|
|Canal excluído|ChannelDeleted|Um usuário exclui um canal de uma equipe.|
|Equipe excluída|TeamDeleted|Um proprietário de equipe exclui uma equipe.|
|Editou uma mensagem com um link de URL no Teams|MessageEditedHasLink|Um usuário edita uma mensagem e adiciona um link de URL a ela no Teams.|
|Mensagens exportadas <sup>1, </sup> <sup>2</sup>|MessagesExported|Mensagens de chat ou canal foram exportadas.|
|Falha ao validar o convite para o canal<sup>compartilhado 3</sup>|FailedValidation|Um usuário responde a um convite para um canal compartilhado, mas a validação do convite falhou.|
|Chat buscado <sup>1, </sup> <sup>2</sup>|ChatRetrieved|Um chat do Microsoft Teams foi recuperado.|
|Buscado todo o conteúdo hospedado de uma mensagem<sup>1, </sup> <sup>2</sup>|MessageHostedContentsListed|Todo o conteúdo hospedado em uma mensagem, como imagens ou snippets de código, foi recuperado.|
|Aplicativo instalado|AppInstalled|Um aplicativo foi instalado.|
|Ação executada no cartão|PerformedCardAction|Um usuário tomou medidas em um cartão adaptável dentro de um chat. Cartões adaptáveis normalmente são usados por bots para permitir a exibição avançada de informações e interação em chats. <br/><br/>**Nota:** Somente ações de entrada embutidas em um cartão adaptável dentro de um chat estarão disponíveis no log de auditoria. Por exemplo, quando um usuário envia uma resposta de votação em uma conversa de canal em um cartão adaptável gerado por um bot de Votação. Ações do usuário, como "Exibir resultado", que abrirão uma caixa de diálogo ou ações do usuário dentro de caixas de diálogo não estarão disponíveis no log de auditoria.|
|Postou uma nova mensagem <sup>1, </sup> <sup>2</sup>|MessageSent|Uma nova mensagem foi postada em um chat ou canal.|
|Aplicativo publicado|AppPublishedToCatalog|Um aplicativo foi adicionado ao catálogo.|
|Ler uma mensagem <sup>1, </sup> <sup>2</sup>|MessageRead|Uma mensagem de um chat ou canal foi recuperada.|
|Ler o conteúdo hospedado de uma mensagem <sup>1, </sup> <sup>2</sup>|MessageHostedContentRead|O conteúdo hospedado em uma mensagem, como uma imagem ou um snippet de código, foi recuperado.|
|Bot removido da equipe|BotRemovedFromTeam|Um usuário remove um bot de uma equipe.|
|Conector removido|ConnectorRemoved|Um usuário remove um conector de um canal.|
|Membros removidos|MemberRemoved|Um proprietário da equipe remove membros de uma equipe, canal ou chat em grupo.|
|Compartilhamento removido do canal<sup>de equipe 3</sup>|Compartilhamento Encerrado|Um proprietário de equipe ou canal desabilitou o compartilhamento de um canal compartilhado.|
|Compartilhamento restaurado do canal<sup>de equipe 3</sup>|SharingRestored|Um proprietário de equipe ou canal reabilitou o compartilhamento para um canal compartilhado.|
|Guia Removida|TabRemoved|Um usuário remove uma guia de um canal.|
|Resposta ao convite para o canal<sup>compartilhado 3</sup>|InviteeResponded|Um usuário respondeu a um convite de canal compartilhado.|
|Resposta à resposta do convidado para o canal<sup>compartilhado 3</sup>|ChannelOwnerResponded|Um proprietário do canal respondeu a uma resposta de um usuário que respondeu a um convite de canal compartilhado.|
|Mensagens recuperadas <sup>1, </sup> <sup>2</sup>|MessagesListed|As mensagens de um chat ou canal foram recuperadas.|
|Enviou uma mensagem com um link de URL no Teams|MessageCreatedHasLink|Um usuário envia uma mensagem contendo um link de URL no Teams.|
|Notificação de alteração enviada para criação <sup>de mensagem 1, </sup> <sup>2</sup>|MessageCreatedNotification|Uma notificação de alteração foi enviada para notificar um aplicativo ouvinte inscrito de uma nova mensagem.|
|Notificação de alteração enviada para exclusão <sup>de mensagem 1, </sup> <sup>2</sup>|MessageDeletedNotification|Uma notificação de alteração foi enviada para notificar um aplicativo ouvinte inscrito de uma mensagem excluída.|
|Notificação de alteração enviada para atualização <sup>de mensagem 1, </sup> <sup>2</sup>|MessageUpdatedNotification|Uma notificação de alteração foi enviada para notificar um aplicativo ouvinte inscrito de uma mensagem atualizada.|
|Convite enviado para o canal<sup>compartilhado 3</sup>|InviteSent|Um proprietário ou membro do canal envia um convite para um canal compartilhado. Os convites para canais compartilhados poderão ser enviados para pessoas de fora da sua organização se a política de canal estiver configurada para compartilhar o canal com usuários externos.|
|Assinar notificações de alteração de <sup>mensagem 1, </sup> <sup>2</sup>|SubscribedToMessages|Uma assinatura foi criada por um aplicativo ouvinte para receber notificações de alteração para mensagens.|
|Aplicativo desinstalado|AppUninstalled|Um aplicativo foi desinstalado.|
|Aplicativo atualizado|AppUpdatedInCatalog|Um aplicativo foi atualizado no catálogo.|
|Atualização de um chat <sup>1, </sup> <sup>2</sup>|ChatUpdated|Um chat do Teams foi atualizado.|
|Atualização de uma <sup>mensagem 1, </sup> <sup>2</sup>|MessageUpdated|Uma mensagem de um chat ou canal foi atualizada.|
|Conector atualizado|ConnectorUpdated|Um usuário modificou um conector em um canal.|
|Guia Atualizado|TabUpdated|Um usuário modificou uma guia em um canal.|
|Aplicativo atualizado|AppUpgraded|Um aplicativo foi atualizado para sua versão mais recente no catálogo.|
|Usuário conectado ao Teams|TeamsSessionStarted|Um usuário entra em um cliente do Microsoft Teams. Esse evento não captura atividades de atualização de token.|

> [!NOTE]
> <sup>1</sup> Um registro de auditoria para esse evento é registrado somente quando a operação é executada chamando um microsoft API do Graph. Se a operação for executada no cliente do Teams, um registro de auditoria não será registrado<br/><sup>2</sup> Este evento só está disponível em Auditoria (Premium). Isso significa que os usuários devem receber a licença apropriada antes que esses eventos sejam registrados no log de auditoria. Para obter mais informações sobre as atividades disponíveis somente em Auditoria (Premium), consulte [Auditoria (Premium) no Microsoft Purview](/microsoft-365/compliance/advanced-audit#advanced-audit-events). Para requisitos de licenciamento de Auditoria (Premium), consulte [Soluções de auditoria no Microsoft 365](/microsoft-365/compliance/auditing-solutions-overview#licensing-requirements). <br/> <sup>3</sup> Este evento está em versão prévia pública.

## <a name="shifts-in-teams-activities"></a>Turnos nas atividades do Teams

**(em visualização)**

Se sua organização estiver usando o aplicativo Turnos no Teams, você poderá pesquisar no log de auditoria atividades relacionadas ao aplicativo Shifts. Aqui está uma lista de todos os eventos registrados para atividades de Turnos no Teams no log de auditoria do Microsoft 365.

|Nome amigável|Operação|Descrição|
|---|---|---|
|Grupo de agendamento adicionado|ScheduleGroupAdded|Um usuário adiciona com êxito um novo grupo de agendamento ao agendamento.|
|Grupo de agendamento editado|ScheduleGroupEdited|Um usuário edita com êxito um grupo de agendamento.|
|Grupo de agendamento excluído|ScheduleGroupDeleted|Um usuário exclui com êxito um grupo de agendamento do agendamento.|
|Agenda retirou|ScheduleWithdrawn|Um usuário retira com êxito uma agenda publicada.|
|Turno adicionado|ShiftAdded|Um usuário adiciona um turno com êxito.|
|Turno editado|ShiftEdited|Um usuário edita com êxito um turno.|
|Turno excluído|ShiftDeleted|Um usuário exclui com êxito um turno.|
|Folga adicionada|TimeOffAdded|Um usuário adiciona folga com êxito ao agendamento.|
|Folga editada|TimeOffEdited|Um usuário edita com êxito o tempo limite.|
|Folga excluída|TimeOffDeleted|Um usuário exclui com êxito o tempo limite.|
|Turno aberto adicionado|OpenShiftAdded|Um usuário adiciona com êxito um turno aberto a um grupo de agendamento.|
|Turno aberto editado|OpenShiftEdited|Um usuário edita com êxito um turno aberto em um grupo de agendamento.|
|Turno aberto excluído|OpenShiftDeleted|Um usuário exclui com êxito um turno aberto de um grupo de agendamento.|
|Agenda compartilhada|ScheduleShared|Um usuário compartilhou com êxito uma agenda de equipe para um intervalo de datas.|
|Relógio no uso do Relógio|ClockedIn|Um usuário relógios com êxito usando o relógio de hora.|
|Relógio de saída usando o relógio de hora|ClockedOut|Um usuário sai com êxito usando o relógio de hora.|
|Interrupção iniciada usando o relógio de hora|BreakStarted|Um usuário inicia com êxito uma interrupção durante uma sessão de relógio de hora ativa.|
|Interrupção encerrada usando o relógio de hora|BreakEnded|Um usuário encerra com êxito uma interrupção durante uma sessão de relógio de hora ativa.|
|Entrada de relógio de hora adicionada|TimeClockEntryAdded|Um usuário adiciona com êxito uma nova entrada manual de relógio de hora no Time Sheet.|
|Entrada de relógio de hora editada|TimeClockEntryEdited|Um usuário edita com êxito uma entrada de relógio de hora no Time Sheet.|
|Entrada de relógio de hora excluída|TimeClockEntryDeleted|Um usuário exclui com êxito uma entrada de relógio de hora no Time Sheet.|
|Solicitação de turno adicionada|RequestAdded|Um usuário adicionou uma solicitação de turno.|
|Resposta à solicitação de deslocamento|RequestRespondedTo|Um usuário respondeu a uma solicitação de turno.|
|Solicitação de turno cancelada|RequestCancelled|Um usuário cancelou uma solicitação de turno.|
|Configuração de agenda alterada|ScheduleSettingChanged|Um usuário altera uma configuração nas configurações de Turnos.|
|Integração de força de trabalho adicionada|WorkforceIntegrationAdded|O aplicativo Shifts é integrado a um sistema de terceiros.|
|Mensagem de deslocamento aceita|OffShiftDialogAccepted|Um usuário reconhece a mensagem de folga para acessar o Teams após o horário de turno.|

## <a name="office-365-management-activity-api"></a>API Office 365 de Atividade de Gerenciamento do Office 365

Você pode usar a API Office 365 de Atividade de Gerenciamento para recuperar informações sobre eventos do Teams. Para saber mais sobre o esquema da API da Atividade de Gerenciamento para o Teams, consulte [o esquema do Teams](/office/office-365-management-api/office-365-management-activity-api-schema#microsoft-teams-schema).

## <a name="attribution-in-teams-audit-logs"></a>Atribuição nos logs de auditoria do Teams

As alterações de associação ao Teams (como usuários adicionados ou excluídos) feitas por meio do Azure Active Directory (Azure AD), do portal de administração do Microsoft 365 ou do Grupos do Microsoft 365 API do Graph aparecerão nas mensagens de auditoria do Teams e no canal Geral com uma atribuição a um proprietário existente da equipe, e não ao iniciador real da ação. Nesses cenários, consulte Azure AD logs de auditoria do [Grupo do Microsoft 365](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) para ver as informações relevantes.

## <a name="use-defender-for-cloud-apps-to-set-activity-policies"></a>Usar o Defender para Aplicativos de Nuvem para definir políticas de atividade

Usando [Microsoft Defender para Aplicativos de Nuvem](/cloud-app-security/what-is-cloud-app-security) integração, você pode definir políticas de [](/cloud-app-security/user-activity-policies) atividade para impor uma ampla variedade de processos automatizados usando as APIs do provedor de aplicativos. Essas políticas permitem monitorar atividades específicas realizadas por vários usuários ou seguir taxas inesperadamente altas de um determinado tipo de atividade.

Depois de definir uma política de detecção de atividade, ela começa a gerar alertas. Os alertas só são gerados em atividades que ocorrem depois que você cria a política. Aqui estão alguns cenários de exemplo de como você pode usar políticas de atividade no Defender para Aplicativos de Nuvem para monitorar as atividades do Teams.

### <a name="external-user-scenario"></a>Cenário de usuário externo

Um cenário no qual talvez você queira ficar atento, de uma perspectiva de negócios, é a adição de usuários externos ao seu ambiente do Teams. Se os usuários externos estão habilitados, monitorar sua presença é uma boa ideia.  Você pode usar o [Defender para Aplicativos de Nuvem](/cloud-app-security/what-is-cloud-app-security) para identificar possíveis ameaças.

:::image type="content" alt-text="Política para monitorar a adição de usuários externos." source="media/TeamsExternalUserAddPolicy.png" lightbox="media/TeamsExternalUserAddPolicy.png":::

A captura de tela dessa política para monitorar a adição de usuários externos permite nomear a política, definir a severidade de acordo com suas necessidades de negócios, defini-la como (nesse caso) uma única atividade e, em seguida, estabelecer os parâmetros que monitorarão especificamente apenas a adição de usuários não internos e limitar essa atividade ao Teams.

Os resultados dessa política podem ser exibidos no log de atividades:

:::image type="content" alt-text="Eventos disparados pela política de usuários externos." source="media/TeamsExternalUserList.png" lightbox="media/TeamsExternalUserList.png":::

Aqui, você pode examinar as correspondentes à política que definiu e fazer os ajustes conforme necessário ou exportar os resultados a serem usado em outro lugar.

### <a name="mass-delete-scenario"></a>Cenário de exclusão em massa

Conforme mencionado anteriormente, você pode monitorar cenários de exclusão. É possível criar uma política que monitora a exclusão em massa de sites do Teams. Neste exemplo, uma política baseada em alerta é configurada para detectar a exclusão em massa de equipes em um período de 30 minutos.

:::image type="content" alt-text="Política mostrando a configuração de uma política para detecção de exclusão em massa da equipe." source="media/TeamsMassDeletePolicy.png" lightbox="media/TeamsMassDeletePolicy.png":::

Como mostra a captura de tela, você pode definir muitos parâmetros diferentes para essa política para monitorar exclusões do Teams, incluindo severidade, ação única ou repetida e parâmetros que limitam isso ao Teams e à exclusão do site. Isso pode ser feito independentemente de um modelo ou você pode ter um modelo criado para basear essa política, dependendo de suas necessidades organizacionais.

Depois de estabelecer uma política que funcione para sua empresa, você pode examinar os resultados no log de atividades à medida que os eventos são disparados:

:::image type="content" alt-text="Captura de tela de eventos disparados por exclusões em massa." source="media/TeamsMassDeleteList.png" lightbox="media/TeamsMassDeleteList.png":::

Você pode filtrar até a política definida para ver os resultados dessa política. Se os resultados que você está obtendo no log de atividades não forem satisfatórios (talvez você esteja vendo muitos resultados ou nada), isso poderá ajudá-lo a ajustar a consulta para torná-la mais relevante para o que você precisa fazer.

### <a name="alert-and-governance-scenario"></a>Cenário de alerta e governança

Você pode definir alertas e enviar emails para administradores e outros usuários quando uma política de atividade é disparada. Você pode definir ações de governança automatizadas, como suspender um usuário ou fazer com que um usuário entre novamente de maneira automatizada. Este exemplo mostra como uma conta de usuário pode ser suspensa quando uma política de atividade é disparada e determina que um usuário excluiu duas ou mais equipes em 30 minutos.

![Captura de tela de alertas e ações de governança para uma política de atividade.](media/audit-log-governance.png)

## <a name="use-defender-for-cloud-apps-to-set-anomaly-detection-policies"></a>Usar o Defender para Aplicativos de Nuvem para definir políticas de detecção de anomalias

[](/cloud-app-security/anomaly-detection-policy) As políticas de detecção de anomalias no Defender para Aplicativos de Nuvem fornecem UEBA (análise comportamental de entidade e usuário) e ML (machine learning) integradas para que você possa executar imediatamente a detecção avançada de ameaças em seu ambiente de nuvem. Como elas são habilitadas automaticamente, as novas políticas de detecção de anomalias fornecem resultados imediatos fornecendo detecções imediatas, direcionando várias anomalias comportamentais em seus usuários e computadores e dispositivos conectados à sua rede. Além disso, as novas políticas expõem mais dados do mecanismo de detecção do Defender para Aplicativos de Nuvem, para ajudá-lo a acelerar o processo de investigação e a conter ameaças contínuas.

Estamos trabalhando para integrar eventos do Teams às políticas de detecção de anomalias. Por enquanto, você pode configurar políticas de detecção de anomalias para outros produtos do Office e executar itens de ação em usuários que correspondem a essas políticas.

## <a name="related-topics"></a>Tópicos relacionados

- [Pesquise o log de auditoria no portal de conformidade do Microsoft Purview](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)
