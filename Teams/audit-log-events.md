---
title: Pesquisar o log de auditoria de eventos no Microsoft Teams
author: markjjo
ms.author: markjjo
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
description: Saiba como recuperar dados do Microsoft Teams do log de auditoria no centro de conformidade do Microsoft 365.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 41fe449a80a9243a9385b6153a8ff18b15332e53
ms.sourcegitcommit: c1aaf1f81c07c0956095b5bd4cb241b1de67b189
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2020
ms.locfileid: "46897701"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a>Pesquisar o log de auditoria de eventos no Microsoft Teams

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

O log de auditoria pode ajudá-lo a investigar atividades específicas em todos os serviços do Microsoft 365. Para o Microsoft Teams, aqui estão algumas das atividades auditadas:

- Criação de equipes
- Exclusão de equipes
- Canal adicionado
- Configuração alterada

Para obter uma lista completa das atividades do teams que são auditadas, consulte atividades e turnos do [Teams](#teams-activities) [nas atividades do Teams (na visualização)](#shifts-in-teams-activities).

> [!NOTE]
> Os eventos de auditoria de canais privados também são registrados como são para equipes e canais padrão.

## <a name="turn-on-auditing-in-teams"></a>Ativar a auditoria no Microsoft Teams

Antes de poder ver os dados de auditoria, você deve primeiro ativar a auditoria no centro de [conformidade do & de segurança](https://protection.office.com). Para obter ajuda com a ativação de auditoria, leia [Ativar ou desativar a pesquisa ativar log de auditoria](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).

> [!IMPORTANT]
> Os dados de auditoria só estão disponíveis no momento em que você ativou a auditoria.

## <a name="retrieve-teams-data-from-the-audit-log"></a>Recuperar dados do Microsoft Teams a partir do log de auditoria

1. Para recuperar logs de auditoria, vá até o [Centro de Conformidade e Segurança](https://go.microsoft.com/fwlink/?linkid=855775). Em **Pesquisar**, selecione **pesquisa de log de auditoria**.
2. Use a **Pesquisa** para filtrar pelas atividades, datas e usuários que você deseja auditar.
3. Exporte os resultados para o Excel para analisá-los melhor.

> [!IMPORTANT]
> Os dados de auditoria só ficam visíveis no log de auditoria se a auditoria estiver ativada.

O período de tempo que um registro de auditoria é mantido e pesquisável no log de auditoria depende da sua assinatura do Microsoft 365 ou do Office 365 e, especificamente, do tipo de licença atribuído aos usuários. Para saber mais, consulte a [Descrição do serviço do centro de conformidade do & Security](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).

## <a name="tips-for-searching-the-audit-log"></a>Dicas para pesquisar o log de auditoria

Aqui estão dicas para pesquisar atividades do teams no log de auditoria.

![Captura de tela da página de pesquisa do log de auditoria](media/audit-log-search-page.png)

- Você pode selecionar atividades específicas a serem pesquisadas clicando no nome da atividade. Ou você pode pesquisar por todas as atividades em um grupo (como **atividades de arquivos e pastas**) clicando no nome do grupo. Se uma atividade estiver selecionada, você poderá clicar nela para cancelar a seleção. Você também pode usar a caixa de pesquisa para exibir as atividades que contêm a palavra-chave que você digita.<br>
    ![Captura de tela da pesquisa de log de auditoria](media/audit-log-search.png)

- Para exibir eventos para atividades executadas usando cmdlets, selecione **Mostrar resultados de todas as atividades** na lista **atividades** . Se você souber o nome da operação para essas atividades, procure todas as atividades e, em seguida, filtre os resultados digitando o nome da operação na caixa na coluna **atividade** . Para saber mais, veja [a etapa 3: filtrar os resultados da pesquisa](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance?view=o365-worldwide#step-3-filter-the-search-results).

- Para limpar os critérios de pesquisa atuais, clique em **limpar**. O intervalo de datas retorna para o padrão dos últimos sete dias. Você também pode clicar em **limpar tudo para mostrar os resultados de todas as atividades** para cancelar todas as atividades selecionadas.

- Se forem encontrados resultados do 5.000, provavelmente você pode pressupor que há mais de 5.000 eventos que atingiram os critérios de pesquisa. Você pode refinar os critérios de pesquisa e executar a pesquisa novamente para retornar menos resultados, ou pode exportar todos os resultados da pesquisa selecionando **Exportar resultados**  >  **baixar todos os resultados**.

Confira [este vídeo](https://www.youtube.com/embed/UBxaRySAxyE) para usar a pesquisa de log de áudio. Participe do Ansuman Acharya, um gerente de programa do Teams, enquanto demonstra como fazer uma pesquisa de log de auditoria para Teams.

## <a name="use-cloud-app-security-to-set-activity-policies"></a>Usar o Cloud app Security para definir políticas de atividade

Usando a integração do [Microsoft Cloud app Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) , você pode definir [políticas de atividades](https://docs.microsoft.com/cloud-app-security/user-activity-policies) para impor uma ampla gama de processos automatizados usando APIs do provedor de aplicativo. Essas políticas permitem monitorar atividades específicas transferidas por vários usuários ou seguir taxas inesperadamente altas de um certo tipo de atividade.

Depois de definir uma política de detecção de atividades, ela começará a gerar alertas. Os alertas são gerados apenas em atividades que ocorrem após a criação da política. Veja alguns exemplos de cenários sobre como você pode usar políticas de atividade no Cloud app Security para monitorar as atividades do teams.

### <a name="external-user-scenario"></a>Cenário de usuário externo

Um cenário do qual você pode querer ficar atento, do ponto de vista dos negócios, é a adição de usuários externos ao seu ambiente de equipe. Se usuários externos estiverem habilitados, o monitoramento da presença será uma boa ideia.  Você pode usar o [Cloud app Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) para identificar possíveis ameaças.

![Captura de tela de uma lista de eventos disparados por exclusões em massa](media/TeamsExternalUserAddPolicy.png)

A captura de tela desta política para monitorar a adição de usuários externos permite que você nomeie a política, defina a gravidade de acordo com suas necessidades comerciais, defina-a como (nesse caso) uma única atividade e, em seguida, estabeleça os parâmetros que monitorarão especificamente apenas a adição de usuários não internos e limitarão essa atividade às equipes.

Os resultados desta política podem ser visualizados no log de atividades:

![Captura de tela de uma lista de eventos disparados por exclusões em massa](media/TeamsExternalUserList.png)

Aqui você pode revisar as correspondências da política que definiu e fazer os ajustes necessários ou exportar os resultados para usar em outro lugar.

### <a name="mass-delete-scenario"></a>Cenário de exclusão em massa

Conforme mencionado anteriormente, você pode monitorar cenários de exclusão. É possível criar uma política que monitoria a exclusão em massa de sites de equipe. Neste exemplo, uma política baseada em alertas é configurada para detectar a exclusão em massa de equipes em um intervalo de 30 minutos.

![Captura de tela da página Criar política mostrando a configuração de uma política para a detecção de exclusão da equipe em massa](media/TeamsMassDeletePolicy.png)

Conforme mostrado na captura de tela, você pode definir vários parâmetros diferentes para essa política para monitorar as exclusões do Teams, incluindo gravidade, ação única ou repetida e parâmetros que limitam isso a equipes e exclusão de sites. Isso pode ser feito independentemente de um modelo, ou você pode ter um modelo criado para basear essa política, dependendo das suas necessidades organizacionais.

Depois de estabelecer uma política que funcione para a sua empresa, você pode revisar os resultados no log de atividades à medida que os eventos são disparados:

![Captura de tela de uma lista de eventos disparados por exclusões em massa](media/TeamsMassDeleteList.png)

Você pode filtrar para baixo até a política definida para ver os resultados dessa política. Se os resultados que você está recebendo no registro de atividades não forem satisfatórios (talvez você esteja vendo muitos resultados ou nada), isso pode ajudá-lo a ajustar a consulta para torná-la mais relevante para o que você precisa.

### <a name="alert-and-governance-scenario"></a>Cenário de alerta e de governança

Você pode definir alertas e enviar emails para administradores e outros usuários quando uma política de atividade é disparada. Você pode definir ações de governança automatizadas, como suspender um usuário ou fazer com que um usuário entre novamente de uma maneira automatizada. Este exemplo mostra como uma conta de usuário pode ser suspensa quando uma política de atividade é disparada e determina que um usuário excluiu duas ou mais equipes em 30 minutos.

![Captura de tela de alertas e ações de governança para uma política de atividade](media/audit-log-governance.png)

## <a name="use-cloud-app-security-to-set-anomaly-detection-policies"></a>Usar o Cloud app Security para definir políticas de detecção de anomalias

[Políticas de detecção de anomalias](https://docs.microsoft.com/cloud-app-security/anomaly-detection-policy) na Cloud app Security fornecem o usuário e a análise de comportamento de entidade (Ueba) e o Machine Learning (ml) prontos para você poder executar imediatamente a detecção avançada de ameaças em seu ambiente de nuvem. Como elas são habilitadas automaticamente, as novas políticas de detecção de anomalias fornecem resultados imediatos fornecendo detecções imediatas, direcionando várias anomalias comportamentais em todos os seus usuários e máquinas e dispositivos conectados à sua rede. Além disso, as novas políticas expõem mais dados do mecanismo de detecção do Cloud app Security, para ajudar você a acelerar o processo de investigação e conter ameaças contínuas.

Estamos trabalhando para integrar os eventos do teams a políticas de detecção de anomalias. Por enquanto, você pode configurar políticas de detecção de anomalias para outros produtos do Office e executar itens de ação em usuários que correspondam a essas políticas.

## <a name="teams-activities"></a>Atividades do teams

Aqui está uma lista de todos os eventos registrados para atividades de usuário e administrador no Microsoft Teams no log de auditoria do Microsoft 365. A tabela inclui o nome amigável que é exibido na coluna **atividades** e o nome da operação correspondente que aparece nas informações detalhadas de um registro de auditoria e no arquivo CSV quando você exporta os resultados da pesquisa.

|Nome amigável  |Operação|Descrição |
|---------|---------|---------|
|Foi adicionado um bot à equipe   |BotAddedToTeam        |Um usuário adiciona um bot a uma equipe.        |
|Canal adicionado   |ChannelAdded         |Um usuário adiciona um canal a uma equipe.         |
|Conector adicionado  |ConnectorAdded          |Um usuário adiciona um conector a um canal.        |
|Membros adicionados    |MemberAdded         |Um proprietário de equipe adiciona membros a uma equipe, canal ou chat em grupo.         |
|Guia adicionar    |TabAdded         |Um usuário adiciona uma guia a um canal.        |
|Configuração de canal alterada    |ChannelSettingChanged         |A operação ChannelSettingChanged é registrada quando as seguintes atividades são executadas por um membro da equipe. Para cada uma dessas atividades, uma descrição da configuração que foi alterada (mostrada entre parênteses é exibida na coluna **Item** nos resultados da pesquisa do log de auditoria. <ul><li>Altera o nome de um canal de equipe (**nome do canal**)</li><li>Altera a descrição de um canal de equipe (**Descrição do canal**)</li> </ul>      |
|Configuração de organização alterada   |TeamsTenantSettingChanged         |A operação TeamsTenantSettingChanged é registrada quando as seguintes atividades são realizadas por um administrador global no centro de administração do Microsoft 365. Essas atividades afetam as configurações de equipes de toda a organização. Para saber mais, consulte [gerenciar as configurações do Microsoft Teams para sua organização](enable-features-office-365.md). <br>Para cada uma dessas atividades, uma descrição da configuração que foi alterada (mostrada entre parênteses) é exibida na coluna **Item** nos resultados da pesquisa do log de auditoria.<ul><li>Habilita ou desabilita o Microsoft Teams para a organização (**Microsoft Teams**).</li><li>Habilita ou desabilita a interoperabilidade entre o Microsoft Teams e o Skype for Business para a organização (**interoperabilidade do Skype for Business**).</li><li>Habilita ou desabilita o modo de exibição de organograma em clientes do Microsoft Teams (**modo de exibição de organograma**).</li><li>Habilita ou desabilita a capacidade dos membros da equipe de agendar reuniões particulares (**agendamento de reunião particular**).</li><li>Habilita ou desabilita a capacidade dos membros da equipe de agendar reuniões de canal (**agendamento de reunião de canal**).</li><li>Habilita ou desabilita a chamada com vídeo em reuniões de equipes (**vídeo para reuniões do Skype**).</li><li>Habilita ou desabilita o compartilhamento de tela no Microsoft Teams reuniões microsoftteams para a organização (**compartilhamento de tela para reuniões do Skype**).</li><li>Habilita ou desabilita a capacidade de adicionar imagens animadas (chamadas Giphys) a conversas do Teams (**imagens animadas**).</li><li>Altera a configuração de classificação de conteúdo da organização (**classificação de conteúdo**). A classificação de conteúdo restringe o tipo de imagem animada que pode ser exibido nas conversas.</li><li>Habilita ou desabilita a capacidade dos membros da equipe de adicionar imagens personalizáveis (chamadas de memes personalizadas) da Internet a conversas da equipe (**imagens personalizáveis da Internet**).</li><li>Habilita ou desabilita a capacidade dos membros da equipe de adicionar imagens editáveis (chamadas adesivos) a conversas da equipe (**imagens editáveis**).</li><li>Habilita ou desabilita a capacidade dos membros da equipe de usar bots em chats e canais do Microsoft Teams (**bots de toda a organização)**.</li><li>Habilita bots específicos para o Microsoft Teams. Isso não inclui o T-bot, que é o bot de ajuda do teams que está disponível quando os bots estão habilitados para a organização (**bots individuais**).</li><li>Habilita ou desabilita a capacidade dos membros da equipe de adicionar extensões ou guias (**extensões ou guias**).</li><li>Habilita ou desabilita o carregamento no lado dos bots proprietários do Microsoft Teams (**carregando lado dos bots**).</li><li>Habilita ou desabilita a capacidade dos usuários de enviar mensagens de email para um canal do Microsoft Teams (**email de canal**).</li></ul>|
|Função de membros alterada no Team    |MemberRoleChanged         |Um proprietário de equipe altera a função dos membros de uma equipe. Os valores a seguir indicam o tipo de função atribuído ao usuário. <br><br>**1** -indica a função de proprietário.<br>**2** -indica a função do membro.<br>**3** -indica a função de convidado.<br><br>A propriedade Members também inclui o nome da sua organização e o endereço de email do membro.        |
|Configuração da equipe alterada    |TeamSettingChanged        |A operação TeamSettingChanged é registrada quando as seguintes atividades são executadas por um proprietário de equipe. Para cada uma dessas atividades, uma descrição da configuração que foi alterada (mostrada entre parênteses) é exibida na coluna **Item** nos resultados da pesquisa do log de auditoria.<ul><li>Altera o tipo de acesso de uma equipe. As equipes podem ser definidas como privadas ou públicas (**tipo de acesso à equipe**). Quando uma equipe é particular (a configuração padrão), os usuários podem acessar a equipe somente por convite. Quando uma equipe é pública, ela é detectável por qualquer pessoa.</li><li>Altera a classificação das informações de uma equipe (**classificação da equipe**). Por exemplo, os dados da equipe podem ser classificados como alto impacto empresarial, impacto na média empresa ou baixo impacto nos negócios.</li><li>Altera o nome de uma equipe (**nome da equipe**).</li><li>Altera a descrição da equipe (**Descrição da equipe**).</li><li>Alterações feitas nas configurações da equipe. Para acessar essas configurações, um proprietário de equipe pode clicar com o botão direito do mouse em uma equipe, selecionar **Gerenciar equipe**e, em seguida, clicar na guia **configurações** . Para essas atividades, o nome da configuração que foi alterada é exibido na coluna **Item** nos resultados da pesquisa do log de auditoria.</li></ul>         |
|Equipe criada    |TeamCreated         |Um usuário cria uma equipe.         |
|Todos os aplicativos da organização excluídos|DeletedAllOrganizationApps           |Excluiu todos os aplicativos da organização do catálogo.     |
|Aplicativo excluído |AppDeletedFromCatalog           |Um aplicativo foi excluído do catálogo.     |
|Canal excluído     |ChannelDeleted         |Um usuário exclui um canal de uma equipe.         |
|Equipe excluída  |TeamDeleted            |Um proprietário da equipe exclui uma equipe.      |
|Aplicativo instalado |AppInstalled         |Um aplicativo foi instalado.   |
|Ação realizada no cartão|PerformedCardAction|Um usuário executou uma ação em um cartão adaptável em um chat. Os cartões adaptáveis são geralmente usados por bots para permitir a exibição rica de informações e interação em chats. <br/><br/>**Observação:** Somente as ações de entrada embutidas em um cartão adaptável dentro de um chat estarão disponíveis no log de auditoria. Por exemplo, quando um usuário envia uma resposta de votação em uma conversa de canal em um cartão adaptável gerado por um bot de votação. Ações do usuário, como "Exibir resultado", que abrirão uma caixa de diálogo, ou as ações do usuário dentro dos diálogos não estarão disponíveis no log de auditoria.|
|Aplicativo publicado |AppPublishedToCatalog           |Um aplicativo foi adicionado ao catálogo.     |
|Bot removido da equipe   |BotRemovedFromTeam         |Um usuário remove um bot de uma equipe.       |
|Conector removido     |ConnectorRemoved         |Um usuário remove um conector de um canal.         |
|Membros removidos    |MemberRemoved        |Um proprietário da equipe remove membros de uma equipe, canal ou chat em grupo.         |
|Guia removida    |TabRemoved         |Um usuário remove uma guia de um canal.         |
|Aplicativo não instalado |AppUninstalled           |Um aplicativo foi desinstalado.     |
|Aplicativo atualizado |AppUpdatedInCatalog           |Um aplicativo foi atualizado no catálogo.     |
|Conector atualizado    |ConnectorUpdated         |Um usuário modificou um conector em um canal.         |
|Guia atualizado   |TabUpdated         |Um usuário modificou uma guia em um canal.         |
|Aplicativo atualizado |AppUpgraded           |Um aplicativo foi atualizado para a versão mais recente no catálogo.     |
|Usuário conectado ao Microsoft Teams     |TeamsSessionStarted         |Um usuário entra em um cliente do Microsoft Teams. Esse evento não captura atividades de atualização de tokens.         |

## <a name="shifts-in-teams-activities"></a>Turnos nas atividades do teams

**(em visualização)**

Se a sua organização estiver usando o aplicativo turnos no Microsoft Teams, você poderá pesquisar as atividades relacionadas ao aplicativo turnos no log de auditoria. Aqui está uma lista de todos os eventos que são registrados para atividades de turnos no Microsoft Teams no log de auditoria do Microsoft 365.

|Nome amigável  |Operação  |Descrição  |
|---------|---------|---------|
|Grupo de agendamento adicionado |ScheduleGroupAdded          |Um usuário adiciona com êxito um novo grupo de agendamento ao cronograma.|
|Grupo de agendamento editado     |ScheduleGroupEdited         |Um usuário edita com êxito um grupo de agendamento.          |
|Grupo de agendamento excluído         |ScheduleGroupDeleted              |Um usuário excluiu com êxito um grupo de agendamento do cronograma.|
|Mudança adicionada      |ShiftAdded          |Um usuário adiciona um turno com sucesso.           |
|Turno editado       |ShiftEdited       |Um usuário edita com êxito um turno.        |
|Turno excluído          |ShiftDeleted          | Um usuário excluiu com êxito um turno.               |
|Adição de folga      |TimeOffAdded          |Um usuário adiciona com êxito o tempo limite no cronograma.          |
|Folga editada         |TimeOffEdited           |Um usuário edita com êxito o tempo limite.          |
|Folga excluído     |TimeOffDeleted              |Um usuário exclui com êxito o tempo de desativação.           |
|Adicionado turno aberto     |OpenShiftAdded          |Um usuário adiciona com êxito um turno aberto a um grupo de agendamento.          |
|Turno aberto editado    |OpenShiftEdited          |Um usuário edita com êxito um turno aberto em um grupo de agendamento.          |
|Turno aberto excluído      |OpenShiftDeleted          |Um usuário exclui com êxito um turno aberto de um grupo de agendamento.         |
|Agenda compartilhada     |ScheduleShared                  |Um usuário compartilhou com êxito um cronograma de equipe para um intervalo de datas.          |
|Com temporização no relógio de tempo         |ClockedIn          |Um usuário relógio com êxito ao usar o relógio de tempo.          |
|Registrando-se usando o relógio de hora      |ClockedOut          |Um usuário relógios com êxito usando o relógio de hora.          |
|Foi iniciada a interrupção usando o relógio de hora      |BreakStarted          |Um usuário inicia uma pausa com êxito durante uma sessão de relógio do tempo ativo.          |
|Quebra interrompida usando o relógio de hora    |BreakEnded          |Um usuário Finaliza uma pausa com êxito durante uma sessão de relógio do tempo ativo.          |
|Entrada de relógio do tempo adicionada     |TimeClockEntryAdded          |Um usuário adiciona com êxito uma nova entrada de relógio de tempo manual à folha de tempo.          |
|Entrada do relógio do tempo editado     | TimeClockEntryEdited             |Um usuário edita com êxito uma entrada de relógio de hora na planilha de tempo.          |
|Entrada de relógio do tempo excluído    |TimeClockEntryDeleted              |Um usuário exclui com êxito uma entrada de relógio de hora na planilha de tempo.          |
|Solicitação Shift adicionada         |RequestAdded              |Um usuário adicionou uma solicitação de mudança.          |
|Respondeu a solicitação de turno     |RequestRespondedTo                  |Um usuário respondeu a uma solicitação de mudança.          |
|Solicitação de turno cancelada         |RequestCancelled               |Um usuário cancelou uma solicitação de mudança.          |
|Configuração de cronograma alterada      |ScheduleSettingChanged          |Um usuário altera uma configuração nas configurações de turnos.         |
|Integração da força de força adicionada      |WorkforceIntegrationAdded                  | O aplicativo turnos está integrado a um sistema de terceiros.         |
|Mensagem de desativação de turno aceita         |OffShiftDialogAccepted          |Um usuário reconhece a mensagem de desativação para acessar o Microsoft Teams depois de turnos de horas.           |

## <a name="office-365-management-activity-api"></a>API de atividade de gerenciamento do Office 365

Você pode usar a API de atividade de gerenciamento do Office 365 para recuperar informações sobre os eventos do teams. Para saber mais sobre o esquema de API de atividade de gerenciamento do Teams, consulte [esquema do teams](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#microsoft-teams-schema).

## <a name="attribution-in-teams-audit-logs"></a>Atribuição nos logs de auditoria do teams

As alterações de associação ao Teams (como usuários adicionados ou excluídos) feitas por meio do Azure Active Directory (Azure AD), do portal de administração do Microsoft 365 ou da API do Microsoft 365 groups Graph serão exibidas nas mensagens de auditoria do Teams e no canal geral com uma atribuição para um proprietário existente da equipe e não para o iniciador real da ação. Nesses cenários, consulte logs do Azure AD ou do [Microsoft 365 Group Audit](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) para ver as informações relevantes.

## <a name="related-topics"></a>Tópicos relacionados

- [Pesquisar o log de auditoria no centro de conformidade do Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)
