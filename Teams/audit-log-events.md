---
title: Pesquisar o log de auditoria de eventos no Microsoft Teams
description: Saiba como recuperar dados do Microsoft Teams do log de auditoria no portal de conformidade do Microsoft Purview.
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- tier1
- purview-compliance
- M365-collaboration
- audit
f1.keywords:
- NOCSH
ms.reviewer: anwara
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: f7219ee11f6818890b8be34f42f76dfa26ef0d12
ms.sourcegitcommit: 5e0900ed7a21ed4e854cc00dbfb4ae4ff2372262
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2023
ms.locfileid: "69950438"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a>Pesquisar o log de auditoria de eventos no Microsoft Teams

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

O log de auditoria pode ajudá-lo a investigar atividades específicas em serviços do Microsoft 365. Para o Microsoft Teams, aqui estão algumas das atividades auditadas:

- Criação de equipes
- Exclusão de equipes
- Canal adicionado
- Canal excluído
- Configuração de canal alterada

Para obter uma lista completa das atividades do Teams auditadas, consulte [atividades do Teams](#teams-activities) e [Turnos nas atividades do Teams](#shifts-in-teams-activities).

> [!NOTE]
> Eventos de auditoria de canais privados também são registrados como são para equipes e canais padrão.

## <a name="turn-on-auditing-in-teams"></a>Ativar a auditoria no Microsoft Teams

Antes de examinar os dados de auditoria, você precisa primeiro ativar a auditoria no portal de conformidade do Microsoft Purview. Para obter mais informações, consulte [Ativar ou desativar a auditoria](/microsoft-365/compliance/turn-audit-log-search-on-or-off).

> [!IMPORTANT]
> Os dados de auditoria só estão disponíveis no ponto em que você ligou a auditoria.

## <a name="retrieve-teams-data-from-the-audit-log"></a>Recuperar dados do Microsoft Teams a partir do log de auditoria

1. Para recuperar logs de auditoria para atividades do Teams, acesse <https://compliance.microsoft.com> e selecione **Auditoria**.

2. Na página **Pesquisa** , filtre as atividades, as datas e os usuários que você deseja auditar.

3. Exporte os resultados para o Excel para analisá-los melhor.

Para obter instruções passo a passo, consulte [Pesquisar o log de auditoria no centro de conformidade](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#search-the-audit-log).

> [!IMPORTANT]
> Os dados de auditoria só ficarão visíveis no log de auditoria se a auditoria estiver ativada.

O tempo que um registro de auditoria é mantido e pesquisável no log de auditoria depende da assinatura do Microsoft 365 ou Office 365 e especificamente do tipo de licença atribuída aos usuários. Para saber mais, confira a [descrição do serviço da Central de Conformidade de Segurança &](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).

## <a name="tips-for-searching-the-audit-log"></a>Dicas para pesquisar o log de auditoria

Aqui estão dicas para pesquisar atividades do Teams no log de auditoria.

:::image type="content" alt-text="Captura de tela da página de pesquisa de log de auditoria no centro de conformidade" source="media/audit-log-search-page.png" lightbox="media/audit-log-search-page.png":::

- Você pode selecionar atividades específicas para pesquisar clicando na caixa de seleção ao lado de uma ou mais atividades. Se uma atividade for selecionada, você poderá clicar nela para cancelar a seleção. Você também pode usar a caixa de pesquisa para exibir as atividades que contêm a palavra-chave que você digita.

  ![Captura de tela da lista suspensa de atividades na página de pesquisa de log de auditoria](media/audit-log-search.png)

- Para exibir eventos para atividades executadas usando cmdlets, selecione **Mostrar resultados para todas as atividades** na lista **Atividades** . Se você souber o nome da operação para essas atividades, digite-a na caixa de pesquisa para exibir a atividade e selecione-a.

- Para limpar os critérios de pesquisa atuais, clique em **Limpar tudo**. O intervalo de datas retorna ao padrão dos últimos sete dias.

- Se 5.000 resultados forem encontrados, você provavelmente poderá assumir que há mais de 5.000 eventos que atenderam aos critérios de pesquisa. Você pode refinar os critérios de pesquisa e executar novamente a pesquisa para retornar menos resultados ou exportar todos os resultados da pesquisa selecionando **Exportar** > **Baixar todos os resultados**. Para obter instruções passo a passo para exportar logs de auditoria, consulte [Exportar os resultados da pesquisa para um arquivo](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#step-3-export-the-search-results-to-a-file).

Confira [este vídeo](https://www.youtube.com/embed/UBxaRySAxyE) para usar a pesquisa de log de áudio. Junte-se a Ansuman Acharya, gerente de programas do Teams, pois ele demonstra como fazer uma pesquisa de log de auditoria para o Teams.

## <a name="teams-activities"></a>Atividades do Teams

Aqui está uma lista de todos os eventos registrados para atividades de usuário e administrador no Teams no log de auditoria do Microsoft 365. A tabela inclui o nome amigável exibido na coluna **Atividades** e o nome da operação correspondente que aparece nas informações detalhadas de um registro de auditoria e no arquivo CSV ao exportar os resultados da pesquisa.

|**Nome amigável**|**Operação**|**Descrição**|
|:----------------|:------------|:--------------|
|Adicionado bot à equipe|BotAddedToTeam|Um usuário adiciona um bot a uma equipe.|
|Canal adicionado|Canal Adicionado|Um usuário adiciona um canal a uma equipe.|
|Conector adicionado|Conector Adicionado|Um usuário adiciona um conector a um canal.|
|Detalhes adicionados sobre a reunião <sup>do Teams 2</sup>|MeetingDetail|O Teams adicionou informações sobre uma reunião, incluindo a hora de início, a hora de término e a URL para ingressar na reunião.|
|Informações adicionadas sobre os participantes <sup>da reunião 2</sup>|MeetingParticipantDetail|O Teams adicionou informações sobre os participantes de uma reunião, incluindo a ID do usuário de cada participante, a hora em que um participante ingressou na reunião e a hora em que um participante saiu da reunião.|
|Membros adicionados|Membro Adicionado|Um proprietário da equipe adiciona membros a uma equipe, canal ou chat em grupo.|
|Guia adicionada|TabAdded|Um usuário adiciona uma guia a um canal.|
| Rótulo de confidencialidade aplicado | SensitivityLabelApplied | Um usuário ou organizador de reunião aplicou um rótulo de confidencialidade a uma reunião do Teams. |
|Configuração de canal alterada|ChannelSettingChanged|A operação ChannelSettingChanged é registrada quando as atividades a seguir são executadas por um membro da equipe. Para cada uma dessas atividades, uma descrição da configuração que foi alterada (mostrada em parênteses é exibida na coluna **Item** nos resultados da pesquisa de log de auditoria. <ul><li>Altera o nome de um canal de equipe (**nome do canal**)</li><li>Altera a descrição de um canal de equipe (**descrição do canal**)</li> </ul>|
|Configuração de organização alterada|TeamsTenantSettingChanged|A operação TeamsTenantSettingChanged é registrada quando as atividades a seguir são executadas por um administrador global no Centro de administração do Microsoft 365. Essas atividades afetam as configurações do Teams em toda a organização. Para saber mais, confira [Gerenciar configurações do Teams para sua organização](enable-features-office-365.md). <br>Para cada uma dessas atividades, uma descrição da configuração que foi alterada (mostrada em parênteses) é exibida na coluna **Item** nos resultados da pesquisa de log de auditoria.<ul><li>Habilita ou desabilita o Teams para a organização (**Microsoft Teams**).</li><li>Habilita ou desabilita a interoperabilidade entre o Microsoft Teams e Skype for Business para a organização (**Skype for Business interoperabilidade**).</li><li>Habilita ou desabilita a exibição do gráfico organizacional em clientes do Microsoft Teams (**exibição do gráfico da organização**).</li><li>Habilita ou desabilita a capacidade dos membros da equipe de agendar reuniões privadas (**agendamento de reuniões privadas**).</li><li>Habilita ou desabilita a capacidade dos membros da equipe de agendar reuniões de canal (**Agendamento de reunião do canal**).</li><li>Habilita ou desabilita a chamada de vídeo em reuniões do Teams (**Vídeo para reuniões do Skype**).</li><li>Habilita ou desabilita o compartilhamento de tela nos meetups do Microsoft Teams para a organização (**compartilhamento de tela para reuniões do Skype**).</li><li>Habilita ou desabilita essa capacidade de adicionar imagens animadas (chamadas Giphys) a conversas do Teams (**imagens animadas**).</li><li>Altera a configuração de classificação de conteúdo para a organização (**Classificação de conteúdo**). A classificação de conteúdo restringe o tipo de imagem animada que pode ser exibida em conversas.</li><li>Permite ou desabilita a capacidade dos membros da equipe de adicionar imagens personalizáveis (chamadas de memes personalizados) da Internet a conversas em equipe (**imagens personalizáveis da Internet**).</li><li>Habilita ou desabilita a capacidade dos membros da equipe de adicionar imagens editáveis (chamadas de adesivos) a conversas em equipe (**imagens editáveis**).</li><li>Habilita ou desabilita essa capacidade de os membros da equipe usarem bots em chats e canais do Microsoft Teams (**bots em toda a organização)**.</li><li>Habilita bots específicos para o Microsoft Teams. Isso não inclui o T-Bot, que é o bot de ajuda do Teams que está disponível quando os bots estão habilitados para a organização (**bots individuais**).</li><li>Habilita ou desabilita a capacidade dos membros da equipe de adicionar extensões ou guias (**Extensões ou guias**).</li><li>Habilita ou desabilita o carregamento lateral de bots proprietários para o Microsoft Teams (**carregamento lateral de bots**).</li><li>Habilita ou desabilita a capacidade dos usuários de enviar mensagens de email para um canal do Microsoft Teams (**email do Canal**).</li></ul>|
|Função alterada de membros na equipe|MemberRoleChanged|Um proprietário da equipe altera a função de membros em uma equipe. Os valores a seguir indicam o tipo de função atribuído ao usuário. <br><br>**1** – Indica a função Membro.<br>**2** – Indica a função Proprietário.<br>**3** – Indica a função convidado.<br><br>A propriedade Members também inclui o nome da sua organização e o endereço de email do membro.|
|Configuração de equipe alterada|TeamSettingChanged|A operação TeamSettingChanged é registrada quando as atividades a seguir são executadas por um proprietário da equipe. Para cada uma dessas atividades, uma descrição da configuração que foi alterada (mostrada em parênteses) é exibida na coluna **Item** nos resultados da pesquisa de log de auditoria.<ul><li>Altera o tipo de acesso de uma equipe. As equipes podem ser definidas como privadas ou públicas (**tipo de acesso da equipe**). Quando uma equipe é privada (a configuração padrão), os usuários podem acessar a equipe somente por convite. Quando uma equipe é pública, é detectável por qualquer um.</li><li>Altera a classificação de informações de uma equipe (**classificação de equipe**). Por exemplo, os dados da equipe podem ser classificados como alto impacto nos negócios, impacto médio nos negócios ou baixo impacto nos negócios.</li><li>Altera o nome de uma equipe (**nome da equipe**).</li><li>Altera a descrição da equipe (**descrição da equipe**).</li><li>Alterações feitas nas configurações da equipe. Para acessar essas configurações, o proprietário da equipe pode clicar com o botão direito do mouse em uma equipe, selecionar **Gerenciar equipe** e, em seguida, clicar na guia **Configurações** . Para essas atividades, o nome da configuração que foi alterada é exibido na coluna **Item** nos resultados da pesquisa de log de auditoria.</li></ul>|
| Rótulo de confidencialidade alterado | SensitivityLabelChanged | Um usuário alterou um rótulo de confidencialidade em uma reunião do Teams. |
|Criou um chat <sup>1, </sup> <sup>2</sup>|ChatCreated|Um chat do Teams foi criado.|
|Equipe criada|TeamCreated|Um usuário cria uma equipe.|
|Excluiu uma mensagem|MessageDeleted|Uma mensagem em um chat ou canal foi excluída.|
|Todos os aplicativos da organização excluídos|DeletedAllOrganizationApps|Todos os aplicativos da organização foram excluídos do catálogo.|
|Aplicativo excluído|AppDeletedFromCatalog|Um aplicativo foi excluído do catálogo.|
|Canal excluído|ChannelDeleted|Um usuário exclui um canal de uma equipe.|
|Equipe excluída|TeamDeleted|Um proprietário da equipe exclui uma equipe.|
|Editou uma mensagem com um link de URL no Teams|MessageEditedHasLink|Um usuário edita uma mensagem e adiciona um link de URL a ela no Teams.|
|Mensagens exportadas <sup>1, </sup> <sup>2</sup>|MessagesExported|Mensagens de chat ou canal foram exportadas.|
|Falha ao validar o convite para o canal compartilhado<sup>3</sup>|FailedValidation|Um usuário responde a um convite para um canal compartilhado, mas o convite falhou na validação.|
|Chat buscado <sup>1, </sup> <sup>2</sup>|ChatRetrieved|Um chat do Microsoft Teams foi recuperado.|
|Buscar todo o conteúdo hospedado de uma mensagem<sup>1, </sup> <sup>2</sup>|MessageHostedContentsListed|Todo o conteúdo hospedado em uma mensagem, como imagens ou snippets de código, foi recuperado.|
|Aplicativo instalado|AppInstalled|Um aplicativo foi instalado.|
|Ação executada no cartão|PerformedCardAction|Um usuário tomou medidas em um cartão adaptável dentro de um chat. Cartões adaptáveis normalmente são usados por bots para permitir a exibição avançada de informações e interação em chats. <br/><br/>**Nota:** Somente ações de entrada embutidas em um cartão adaptável dentro de um chat estarão disponíveis no log de auditoria. Por exemplo, quando um usuário envia uma resposta de pesquisa em uma conversa de canal em um cartão adaptável gerado por um bot poll. Ações do usuário, como "Exibir resultado", que abrirá uma caixa de diálogo ou ações do usuário dentro de caixas de diálogo não estarão disponíveis no log de auditoria.|
|Postado uma nova mensagem <sup>1, </sup> <sup>2</sup>|MessageSent|Uma nova mensagem foi postada em um chat ou canal.|
|Aplicativo publicado|AppPublishedToCatalog|Um aplicativo foi adicionado ao catálogo.|
|Ler uma mensagem <sup>1, </sup> <sup>2</sup>|MessageRead|Uma mensagem de um chat ou canal foi recuperada.|
|Ler o conteúdo hospedado de uma mensagem <sup>1, </sup> <sup>2</sup>|MessageHostedContentRead|O conteúdo hospedado em uma mensagem, como uma imagem ou um snippet de código, foi recuperado.|
|Bot removido da equipe|BotRemovedFromTeam|Um usuário remove um bot de uma equipe.|
|Conector removido|ConnectorRemoved|Um usuário remove um conector de um canal.|
|Membros removidos|MemberRemoved|Um proprietário da equipe remove membros de uma equipe, canal ou chat em grupo.|
| Rótulo de confidencialidade removido | SensitivityLabelRemoved | Um usuário removeu um rótulo de confidencialidade de uma reunião do Teams. |
|Compartilhamento removido do canal de equipe<sup>3</sup>|Compartilhamento encerrado|Uma equipe ou proprietário do canal desabilitou o compartilhamento para um canal compartilhado.|
|Compartilhamento restaurado do canal<sup>de equipe 3</sup>|SharingRestored|Um compartilhamento reabilitado do proprietário de uma equipe ou do canal para um canal compartilhado.|
|Guia removida|TabRemoved|Um usuário remove uma guia de um canal.|
|Respondeu ao convite para o canal compartilhado<sup>3</sup>|InviteeResponded|Um usuário respondeu a um convite de canal compartilhado.|
|Respondeu à resposta de convite ao canal compartilhado<sup>3</sup>|ChannelOwnerResponded|Um proprietário do canal respondeu a uma resposta de um usuário que respondeu a um convite de canal compartilhado.|
|Mensagens recuperadas <sup>1, </sup> <sup>2</sup>|MessagesListed|Mensagens de um chat ou canal foram recuperadas.|
|Enviou uma mensagem com um link de URL no Teams|MessageCreatedHasLink|Um usuário envia uma mensagem contendo um link de URL no Teams.|
|Notificação de alteração enviada para criação <sup>de mensagem 1, </sup> <sup>2</sup>|MessageCreatedNotification|Uma notificação de alteração foi enviada para notificar um aplicativo ouvinte inscrito de uma nova mensagem.|
|Notificação de alteração enviada para exclusão <sup>de mensagem 1, </sup> <sup>2</sup>|MessageDeletedNotification|Uma notificação de alteração foi enviada para notificar um aplicativo ouvinte inscrito de uma mensagem excluída.|
|Notificação de alteração enviada para a atualização <sup>da mensagem 1, </sup> <sup>2</sup>|MessageUpdatedNotification|Uma notificação de alteração foi enviada para notificar um aplicativo ouvinte inscrito de uma mensagem atualizada.|
|Convite enviado para o canal compartilhado<sup>3</sup>|InviteSent|Um proprietário ou membro do canal envia um convite para um canal compartilhado. Convites para canais compartilhados podem ser enviados para pessoas fora da sua organização se a política de canal estiver configurada para compartilhar o canal com usuários externos.|
|Inscrito nas notificações de alteração de mensagem <sup>1, </sup> <sup>2</sup>|SubscribedToMessages|Uma assinatura foi criada por um aplicativo ouvinte para receber notificações de alteração para mensagens.|
|Aplicativo desinstalado|AppUninstalled|Um aplicativo foi desinstalado.|
|Aplicativo atualizado|AppUpdatedInCatalog|Um aplicativo foi atualizado no catálogo.|
|Atualizado um chat <sup>1, </sup> <sup>2</sup>|ChatUpdated|Um chat do Teams foi atualizado.|
|Atualizado uma mensagem <sup>1, </sup> <sup>2</sup>|MessageUpdated|Uma mensagem de um chat ou canal foi atualizada.|
|Conector atualizado|ConnectorUpdated|Um usuário modificou um conector em um canal.|
|Guia atualizada|TabUpdated|Um usuário modificou uma guia em um canal.|
|Aplicativo atualizado|AppUpgraded|Um aplicativo foi atualizado para sua versão mais recente no catálogo.|
|Usuário conectado ao Teams|TeamsSessionStarted|Um usuário entra em um cliente do Microsoft Teams. Este evento não captura atividades de atualização de token.|

> [!NOTE]
> <sup>1</sup> Um registro de auditoria para esse evento só é registrado quando a operação é executada chamando um microsoft API do Graph. Se a operação for executada no cliente do Teams, um registro de auditoria não será registrado<br/><sup>2</sup> Este evento só está disponível em Auditoria (Premium). Isso significa que os usuários devem receber a licença apropriada antes que esses eventos sejam registrados no log de auditoria. Para obter mais informações sobre as atividades disponíveis apenas em Auditoria (Premium), consulte [Auditoria (Premium) no Microsoft Purview](/microsoft-365/compliance/advanced-audit#advanced-audit-events). Para requisitos de licenciamento de Auditoria (Premium), consulte [Soluções de auditoria no Microsoft 365](/microsoft-365/compliance/auditing-solutions-overview#licensing-requirements). <br/> <sup>3</sup> Este evento está em versão prévia pública.

## <a name="shifts-in-teams-activities"></a>Turnos nas atividades do Teams

**(em visualização)**

Se sua organização estiver usando o aplicativo Shifts no Teams, você poderá pesquisar no log de auditoria atividades relacionadas ao aplicativo Shifts. Aqui está uma lista de todos os eventos registrados para atividades do Shifts no Teams no log de auditoria do Microsoft 365.

|Nome amigável|Operação|Descrição|
|---|---|---|
|Grupo de agendamento adicionado|ScheduleGroupAdded|Um usuário adiciona com êxito um novo grupo de agendamento à agenda.|
|Grupo de agendamento editado|ScheduleGroupEdited|Um usuário edita com êxito um grupo de agendamento.|
|Grupo de agendamento excluído|ScheduleGroupDeleted|Um usuário exclui com êxito um grupo de agendamento da agenda.|
|Agendamento retirado|AgendaMentoComdrawn|Um usuário retira com êxito uma agenda publicada.|
|Turno adicionado|ShiftAdded|Um usuário adiciona com êxito uma mudança.|
|Turno editado|ShiftEdited|Um usuário edita com êxito uma mudança.|
|Turno excluído|ShiftDeleted|Um usuário exclui com êxito uma mudança.|
|Tempo limite adicionado|TimeOffAdded|Um usuário adiciona uma folga com êxito na agenda.|
|Folga editada|TimeOffEdited|Um usuário edita com êxito a folga.|
|Tempo limite excluído|TimeOffDeleted|Um usuário exclui com êxito a folga.|
|Adicionado turno aberto|OpenShift Adicionado|Um usuário adiciona com êxito um turno aberto a um grupo de agendamento.|
|Turno aberto editado|OpenShiftEdited|Um usuário edita com êxito um turno aberto em um grupo de agendamento.|
|Turno aberto excluído|OpenShiftDeleted|Um usuário exclui com êxito um turno aberto de um grupo de agendamento.|
|Agenda compartilhada|ScheduleShared|Um usuário compartilhou com êxito uma agenda de equipe para um intervalo de datas.|
|Clocked in using Time clock|ClockedIn|Um usuário marca com êxito o uso do relógio De tempo.|
|Tempo limite usando o relógio de tempo|ClockedOut|Um usuário marca com êxito o relógio de tempo.|
|Iniciou o intervalo usando o relógio de tempo|BreakStarted|Um usuário inicia com êxito uma interrupção durante uma sessão de relógio de tempo ativo.|
|Interrupção final usando o relógio de tempo|BreakEnded|Um usuário encerra com êxito uma interrupção durante uma sessão do relógio temporizado ativo.|
|Entrada de relógio de tempo adicionado|TimeClockEntry Adicionado|Um usuário adiciona com êxito uma nova entrada de relógio de tempo manual na Folha de Tempo.|
|Entrada de relógio de hora editada|TimeClockEntryEdited|Um usuário edita com êxito uma entrada de relógio de hora na Folha de Tempo.|
|Entrada de relógio de hora excluída|TimeClockEntryDeleted|Um usuário exclui com êxito uma entrada de relógio de hora na Folha de Tempo.|
|Solicitação de turno adicionada|Solicitação Adicionada|Um usuário adicionou uma solicitação de turno.|
|Respondeu à solicitação de turno|RequestRespondedTo|Um usuário respondeu a uma solicitação de turno.|
|Solicitação de turno cancelada|RequestCancelled|Um usuário cancelou uma solicitação de turno.|
|Configuração de agendamento alterada|ScheduleSettingChanged|Um usuário altera uma configuração nas configurações shifts.|
|Integração da força de trabalho adicionada|WorkforceIntegration Adicionado|O aplicativo Shifts é integrado a um sistema de terceiros.|
|Mensagem de desativação aceita|OffShiftDialogAccepted|Um usuário reconhece a mensagem off-shift para acessar o Teams após o horário de turno.|

## <a name="office-365-management-activity-api"></a>API de Atividade de Gerenciamento de Office 365

Você pode usar a API de Atividade de Gerenciamento Office 365 para recuperar informações sobre eventos do Teams. Para saber mais sobre o esquema de API de Atividade de Gerenciamento do Teams, consulte [Esquema do Teams](/office/office-365-management-api/office-365-management-activity-api-schema#microsoft-teams-schema).

## <a name="attribution-in-teams-audit-logs"></a>Atribuição em logs de auditoria do Teams

Alterações de associação ao Teams (como usuários adicionados ou excluídos) feitas por meio do Azure Active Directory (Azure AD), portal de administração do Microsoft 365 ou Grupos do Microsoft 365 API do Graph serão exibidas em mensagens de auditoria do Teams e no canal Geral com uma atribuição a um proprietário existente da equipe, e não ao iniciador real da ação. Nesses cenários, consulte Azure AD ou [logs de auditoria do Grupo do Microsoft 365](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) para ver as informações relevantes.

## <a name="use-defender-for-cloud-apps-to-set-activity-policies"></a>Usar o Defender para Aplicativos na Nuvem para definir políticas de atividade

Usando [Microsoft Defender para Aplicativos de Nuvem](/cloud-app-security/what-is-cloud-app-security) integração, você pode definir [políticas de atividade](/cloud-app-security/user-activity-policies) para impor uma ampla gama de processos automatizados usando as APIs do provedor de aplicativos. Essas políticas permitem monitorar atividades específicas realizadas por vários usuários ou seguir taxas inesperadamente altas de um determinado tipo de atividade.

Depois de definir uma política de detecção de atividades, ela começa a gerar alertas. Os alertas só são gerados em atividades que ocorrem depois que você cria a política. Veja alguns cenários de exemplo de como você pode usar políticas de atividade no Defender para Aplicativos de Nuvem para monitorar as atividades do Teams.

### <a name="external-user-scenario"></a>Cenário de usuário externo

Um cenário em que você pode querer ficar de olho, de uma perspectiva de negócios, é a adição de usuários externos ao seu ambiente do Teams. Se os usuários externos estiverem habilitados, monitorar sua presença será uma boa ideia.  Você pode usar o [Defender para Aplicativos de Nuvem](/cloud-app-security/what-is-cloud-app-security) para identificar possíveis ameaças.

:::image type="content" alt-text="Política para monitorar a adição de usuários externos." source="media/TeamsExternalUserAddPolicy.png" lightbox="media/TeamsExternalUserAddPolicy.png":::

A captura de tela dessa política para monitorar a adição de usuários externos permite que você nomeie a política, defina a gravidade de acordo com suas necessidades empresariais, defina-a como (nesse caso) uma única atividade e, em seguida, estabeleça os parâmetros que monitorarão especificamente apenas a adição de usuários não internos e limitem essa atividade ao Teams.

Os resultados dessa política podem ser exibidos no log de atividades:

:::image type="content" alt-text="Eventos disparados pela política de usuários externos." source="media/TeamsExternalUserList.png" lightbox="media/TeamsExternalUserList.png":::

Aqui, você pode examinar as correspondências com a política definida e fazer os ajustes conforme necessário ou exportar os resultados a serem usados em outro lugar.

### <a name="mass-delete-scenario"></a>Cenário de exclusão em massa

Conforme mencionado anteriormente, você pode monitorar cenários de exclusão. É possível criar uma política que monitore a exclusão em massa de sites do Teams. Neste exemplo, uma política baseada em alerta é configurada para detectar a exclusão em massa de equipes em um período de 30 minutos.

:::image type="content" alt-text="Política mostrando a configuração de uma política para detecção de exclusão de equipe em massa." source="media/TeamsMassDeletePolicy.png" lightbox="media/TeamsMassDeletePolicy.png":::

Como a captura de tela mostra, você pode definir muitos parâmetros diferentes para essa política para monitorar exclusões do Teams, incluindo gravidade, ação única ou repetida e parâmetros que limitam isso ao Teams e à exclusão do site. Isso pode ser feito independentemente de um modelo ou você pode ter um modelo criado para basear essa política, dependendo de suas necessidades organizacionais.

Depois de estabelecer uma política que funcione para sua empresa, você poderá examinar os resultados no log de atividades à medida que os eventos são disparados:

:::image type="content" alt-text="Captura de tela de eventos disparados por exclusões em massa." source="media/TeamsMassDeleteList.png" lightbox="media/TeamsMassDeleteList.png":::

Você pode filtrar para baixo para a política que você definiu para ver os resultados dessa política. Se os resultados que você está obtendo no log de atividades não forem satisfatórios (talvez você esteja vendo muitos resultados ou nada), isso pode ajudá-lo a ajustar a consulta para torná-la mais relevante para o que você precisa que ela faça.

### <a name="alert-and-governance-scenario"></a>Cenário de alerta e governança

Você pode definir alertas e enviar emails para administradores e outros usuários quando uma política de atividade é disparada. Você pode definir ações de governança automatizadas, como suspender um usuário ou fazer com que um usuário entre novamente de forma automatizada. Este exemplo mostra como uma conta de usuário pode ser suspensa quando uma política de atividade é disparada e determina que um usuário excluiu duas ou mais equipes em 30 minutos.

![Captura de tela de alertas e ações de governança para uma política de atividade.](media/audit-log-governance.png)

## <a name="use-defender-for-cloud-apps-to-set-anomaly-detection-policies"></a>Usar o Defender para Aplicativos de Nuvem para definir políticas de detecção de anomalias

[As políticas de detecção de anomalias](/cloud-app-security/anomaly-detection-policy) no Defender para Aplicativos de Nuvem fornecem UEBA (análise comportamental de usuário e entidade) e ML (machine learning) para que você possa executar imediatamente a detecção avançada de ameaças em seu ambiente de nuvem. Como elas estão habilitadas automaticamente, as novas políticas de detecção de anomalias fornecem resultados imediatos fornecendo detecções imediatas, visando inúmeras anomalias comportamentais entre seus usuários e os computadores e dispositivos conectados à sua rede. Além disso, as novas políticas expõem mais dados do mecanismo de detecção do Defender para Aplicativos de Nuvem, para ajudá-lo a acelerar o processo de investigação e conter ameaças contínuas.

Estamos trabalhando para integrar eventos do Teams em políticas de detecção de anomalias. Por enquanto, você pode configurar políticas de detecção de anomalias para outros produtos do Office e executar itens de ação em usuários que correspondem a essas políticas.

## <a name="related-topics"></a>Tópicos relacionados

- [Pesquise o log de auditoria no portal de conformidade do Microsoft Purview](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)
