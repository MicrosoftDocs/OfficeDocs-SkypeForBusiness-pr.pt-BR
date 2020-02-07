---
title: Chat, equipes, canais e aplicativos no Microsoft Teams
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Orientações passo a passo para implementar chat, equipes, canais e aplicativos no Microsoft Teams
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.quickstartteamsadmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 51fd22257635502e92b89482f320b6bd68987cfe
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826699"
---
# <a name="chat-teams-channels--apps-in-microsoft-teams"></a>Chat, equipes, canais e aplicativos no Microsoft Teams

O Teams oferece uma excelente experiência de colaboração pronta para uso para sua organização e a maioria das organizações acha que as configurações padrão atendem suas necessidades. Este artigo ajuda você a decidir se deseja alterar as configurações padrão, com base no perfil da organização e requisitos de negócios e, em seguida, orienta você em cada alteração. Dividimos as configurações em dois grupos, começando com o conjunto principal de [alterações que você provavelmente realizará](#core-deployment-decisions). O segundo grupo inclui [configurações adicionais](#additional-deployment-decisions) que poderão ser configuradas com base nas necessidades de sua organização. 

Para começar, assista ao nosso breve vídeo sobre chat, equipes e canais do Teams (4:30 minutos): 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE476Yj]

*Novidades de novembro de 2019*
 - Agora é possível [Usar o Assistente do Teams (visualização) para ajudá-lo na implantação do Microsoft Teams](use-advisor-teams-roll-out.md). O Assistente do Teams (visualização) o orienta na implemetação do Microsoft Teams. Ele avalia o ambiente do Office 365 e identifica as configurações mais comuns que talvez seja necessário atualizar ou modificar antes de poder implantar o Teams com êxito.
 - [Canal do YouTube sobre Noções Básicas do Microsoft Teams para TI](https://aka.ms/MicrosoftTeamsforIT), incluindo vídeos curtos (8 a 10 minutos) que mostram como implantar, configurar e gerenciar o Teams.

> [!TIP]
> É recomendável incluir os aplicativos em destaque, como o Planner, na implementação inicial do Teams. Adicionar outros [aplicativos, bots e conectores](deploy-apps-microsoft-teams-landing-page.md) ao executar a adoção do Teams.

## <a name="chat-deployment-prerequisites"></a>Pré-requisitos de implantação do chat

Antes de implementar o Teams em sua organização, reserve algum tempo para confirmar se seu ambiente está preparado para receber o Teams. Examine as informações a seguir e faça as alterações necessárias em seu ambiente.

- Para ter acesso à experiência completa do Teams, sua organização deverá ter implantado o [Exchange Online e o SharePoint Online](#exchange-and-sharepoint-interoperability) e você deverá ter um domínio verificado para o Office 365 (por exemplo, contoso.com).

- Para dimensionar o chat, equipes e canais em toda a organização, verifique se todos os locais têm acesso à Internet para que eles possam se conectar ao Office 365. Verifique ao menos se as seguintes portas comuns estão abertas à Internet em todos os locais:

    - Portas **TCP** 80 e 443 abertas de tráfego de saída dos clientes que usarão o Teams.
    - Portas **UDP** 3478 até 3481 abertas de tráfego de saída dos clientes que usarão o Teams

|Pergunte-se|Ação |
|------------|-------|
|Minha organização está pronta para implementar o Teams?|Para responder a essa pergunta, confira: <ul><li> [Verificar a preparação de seu ambiente para o Teams](environment-readiness.md)</li><li>[Preparo da rede da sua organização para o Teams](prepare-network.md)</li><li>[URLs e intervalos de endereços IP do Office 365](office-365-urls-ip-address-ranges.md)</li><li>[Planejar os Grupos do Office 365 ao criar equipes](plan-office-365-groups.md)</li></ul>|
|||

## <a name="core-deployment-decisions"></a>Decisões principais de implantação

Estas são as configurações de chat, equipes e canais que a maioria das organizações deseja alterar (se as configurações padrão não atenderem suas necessidades).

### <a name="teams-administrators"></a>Administradores do Teams

O Teams fornece um conjunto personalizado de funções de administrador que pode ser usado para gerenciar o programa na organização. As funções fornecem vários recursos para administradores.

| Pergunte a si mesmo | Ação |
|--------------|--------|
|A quem será atribuída a função de Administrador de Comunicações de Equipes?|Para saber mais sobre as funções de administrador do Teams, confira [Usar funções de administrador para gerenciar o Microsoft Teams](using-admin-roles.md).|
|A quem será atribuída função de Engenheiro de Suporte de Comunicações de Equipes?|Para atribuir funções de administrador, confira [Atribuir funções de administrador e não administrador aos usuários com o Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).|
|A quem será atribuída a função de Especialista de Suporte de Comunicações do Teams?||
|||

### <a name="teams-owners-and-members"></a>Proprietários e membros do Teams

Além das funções de administrador, o Teams permite que você atribua funções de usuário ao membro e ao proprietário e forneça seletivamente recursos de moderador (se a moderação tiver sido configurada) para controlar quem pode realizar determinadas ações dentro de um canal. A moderação permite controlar quem pode iniciar novas postagens em um canal, adicionar e remover membros da equipe como moderadores e controlar se os membros da equipe podem responder a mensagens existentes do canal.

|Pergunte-se|Ação |
|------------|-------|
|Quem deve ser atribuído a cada função? | Para comparar os recursos de cada função, confira [Atribuir proprietários, moderadores e membros de equipe no Microsoft Teams.](assign-roles-permissions.md)
|Como posso atribuir uma função de usuário? | Para atribuir ou alterar uma função, confira [Atribuir uma função de usuário](assign-roles-permissions.md#assign-a-user-role).
|Preciso controlar quem pode postar e responder em um canal? | Para configurar a moderação, confira [Configurar e gerenciar a moderação de canal no Microsoft Teams](manage-channel-moderation-in-teams.md).

### <a name="messaging-policies"></a>Políticas de mensagens

As políticas de mensagens controlam quais recursos de mensagens de chat e canal estão disponíveis para usuários no Teams. Por exemplo, quem pode editar e excluir mensagens, quem pode usar o chat, quem pode usar memes em conversas e muito mais. Por padrão, os usuários recebem a atribuição da política global de mensagens e todos os recursos estão **Habilitados**. Você pode usar a política global padrão ou criar uma ou mais políticas de mensagens personalizadas para pessoas em sua organização. 

|Pergunte-se|Ação |
|------------|-------|
|Vou personalizar a política global de mensagens?|Para obter informações sobre como usar o Centro de administração do Microsoft Teams para alterar a política global de mensagens ou adicionar uma nova política, confira [Gerenciar políticas de mensagens no Teams](messaging-policies-in-teams.md).|
|Exijo várias políticas de mensagens?|Para criar e atribuir uma política de mensagens no PowerShell, confira [Exemplo de script do PowerShell - Criar e atribuir uma política de mensagens](scripts/powershell-script-teams-messaging-policy-edu.md).|
|Como determinarei quais grupos de usuários receberão qual política de mensagens?|Para saber mais sobre os cmdlets CsTeamsMessagingPolicy, confira [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps).|
||| 

### <a name="external-access"></a>Acesso externo

O acesso externo (anteriormente conhecido como federação) permite que os usuários do Teams e do Skype for Business se comuniquem com usuários que estão fora da organização. Ao habilitar essa opção e adicionar domínios à lista de permissões, os usuários podem se comunicar com usuários em outros domínios e organizações.O acesso externo é diferente do acesso de convidado já que um domínio inteiro recebe permissão de acesso e não apenas um indivíduo. O acesso externo está desativado por padrão.

|Pergunte-se|Ação |
|------------|-------|
|<ul><li>Vou ativar o acesso externo para minha organização?</li><li>Se habilitado, vou limitar os domínios com os quais minha organização poderá se comunicar?</li></ul> |<br>Para ativar o acesso externo, confira [Plano para acesso externo](manage-external-access.md#plan-for-external-access).|
|||

### <a name="guest-access"></a>Acesso de convidados

No Teams, o acesso de convidado permite que pessoas que não pertencem à organização acessem canais e equipes. Você pode usar as configurações de acesso de convidado para controlar quais recursos os usuários convidados podem ou não usar. O acesso de convidado está desativado por padrão. Para saber mais, confira [Acesso de convidado do Teams](https://docs.microsoft.com/microsoftteams/guest-access).

|Pergunte-se|Ação |
|------------|-------|
|Vou ativar o acesso de convidado para minha organização?|Para habilitar o acesso de convidado, confira [Ativar ou desativar o acesso de convidado no Teams](set-up-guests.md).|
|Se o acesso for habilitado, devo personalizar os recursos disponíveis para pessoas em minha organização?|Para personalizar a disponibilidade dos recursos do acesso de convidado, confira [Autorizar o acesso de convidado no Teams](teams-dependencies.md).|
|||

### <a name="teams-settings"></a>Configurações de equipes

As configurações do Teams permitem que você configure suas equipes para usar recursos, como a integração de email, opções de armazenamento em nuvem, guia da organização, configuração de dispositivos de salas de reunião e escopo de pesquisa. Ao realizar alterações nessas configurações, elas serão aplicadas a todas as equipes da organização. Para saber mais, confira [Configurações do Teams](enable-features-office-365.md#teams-settings).

|Pergunte-se|Ação |
|------------|-------|
|Vou personalizar as configurações do Teams para minha organização? | Para saber sobre as configurações do Teams e personalizá-las, confira [Configurações do Teams](enable-features-office-365.md#teams-settings).|
|||

### <a name="teams-clients"></a>Clientes do Teams

O Teams é compatível com vários clientes, como clientes de área de trabalho, móveis e clientes Web, e a configuração padrão permite que os usuários escolham os clientes desejados.Para saber mais, confira [Obter clientes para o Teams](get-clients.md).

|Pergunte-se|Ação |
|------------|-------|
|Vou personalizar a disponibilidade do cliente do Teams para minha organização?|Confira os [Requisitos de hardware para o aplicativo Teams](hardware-requirements-for-the-teams-app.md). |
|Vou personalizar as configurações de cliente do Teams para minha organização?|Saiba como [Instalar o Teams usando o MSI](msi-deployment.md).|
|||


### <a name="teams-usage-reporting"></a>Relatórios de uso do Teams

As funções de Administrador global no Office 365, Administrador de serviços do Teams e Leitores de Relatórios podem exibir relatórios de uso do Teams. Para saber mais, confira os [artigos de análise de uso do Microsoft 365](https://docs.microsoft.com/office365/admin/usage-analytics/usage-analytics?redirectSourcePath=%252farticle%252fMicrosoft-365-usage-analytics-77ff780d-ab19-4553-adea-09cb65ad0f1f&view=o365-worldwide).

|Pergunte-se|Ação |
|------------|-------|
|<br> Quem precisa ver os relatórios de uso do Teams e eles têm a função correta para visualizá-los? |<ul><li>Se o usuário não for um administrador, [atribua a função de leitor de relatórios](teams-activity-reports.md#reports-reader-role).</li><li>Confira [Funções e permissões](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) e [Exibir e atribuir funções](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal) para saber como atribuir funções de administrador no Azure Active Directory. |
|||

### <a name="teams-default-apps"></a>Aplicativos padrão do Teams 

O Teams oferece vários aplicativos próprios (fornecidos pela Microsoft) e de terceiros para envolver usuários, dar suporte à produtividade e integrar serviços comerciais comumente usados no Teams. Obtenha aplicativos na Teams Store. Os aplicativos estão ativados por padrão no Teams. 

Para saber mais sobre a implantação e gerenciamento de aplicativos no Teams, confira nossa orientação detalhada sobre [Aplicativos, bots e conectores](deploy-apps-microsoft-teams-landing-page.md).


## <a name="additional-deployment-decisions"></a>Decisões adicionais de implantação

Convém alterar essas configurações, com base nas necessidades da organização e da configuração.

### <a name="teams-licensing"></a>Licenciamento do Teams

O Teams é oferecido como parte de muitas licenças do Office 365. Para saber mais sobre o licenciamento do Teams, confira [Licenciamento do Office 365 para o Teams](office-365-licensing.md).

|Pergunte-se|Ação |
|------------|-------|
|Meus usuários têm licenças necessárias para usar todos os recursos do Teams que desejo implementar? | Para saber mais sobre os requisitos de licenciamento, confira [Licenciamento do Office 365 para o Teams](office-365-licensing.md).|
|||

### <a name="exchange-and-sharepoint-interoperability"></a>Interoperabilidade entre o Exchange e o SharePoint 

Para a experiência completa com o Teams, todos os usuários devem estar habilitados para o Exchange Online, para o SharePoint Online e para a criação de grupos no Office 365. Os artigos a seguir descrevem informações relacionadas às caixas de correio do Exchange hospedadas em vários ambientes, como o Exchange e o Teams interagem e considerações semelhantes para o SharePoint e o OneDrive for Business. 

|Pergunte-se|Ação |
|------------|-------|
| Será possível implantar os recursos necessários do Teams com as implantações atuais do Exchange e do SharePoint? |Para obter mais informações sobre o Exchange e o SharePoint no Teams, confira:<ul><li> [Como o Exchange e o Teams interagem](exchange-teams-interact.md)</li><li>[Como o SharePoint Online e o OneDrive for Business interagem com o Teams](sharepoint-onedrive-interact.md)|
|||

### <a name="teams-limits-and-specifications"></a>Especificações e limites do Teams 

Ao planejar uma implantação corporativa do Teams, você deve levar em consideração todas as limitações e especificações relevantes, como o número máximo de membros em uma equipe, o número máximo de equipes que um usuário pode criar e assim por diante.

|Pergunte-se|Ação |
|------------|-------|
| Quais limites provavelmente atingirei com a implementação do Teams? | Para saber mais, confira [Limites e especificações para o Teams](limits-specifications-teams.md). |
|||

### <a name="office-365-urls-and-ports"></a>URLs e portas do Office 365

As organizações que mantêm um controle refinado de seu tráfego da Internet devem ler [URLs do Office 365 e intervalos de endereços IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) para obter uma lista atualizada de URLs, endereços IP, portas e protocolos que devem ser configurados corretamente para o Teams. A Microsoft está aprimorando continuamente o serviço do Office 365 e acrescentando novas funcionalidades; assim, as portas, as URLs e os endereços IP necessários podem mudar com o passar do tempo. Recomendamos que você se inscreva via RSS para receber notificações quando essas informações forem atualizadas ou alteradas. Pelo menos, verifique se abriu as portas listadas acima em [Pré-requisitos da implantação do chat](#chat-deployment-prerequisites).

|Pergunte-se|Ação |
|------------|-------|
| Preciso de regras de acesso à Internet para permitir que os usuários usem o Teams ou é suficiente abrir as portas mínimas necessárias? | Para saber mais, confira [URLs e intervalos de endereços IP do Office 365](office-365-urls-ip-address-ranges.md).|
|||


### <a name="governance-naming-conventions-who-can-create-teams"></a>Governança (convenções de nomenclatura, quem pode criar equipes)

Sua organização pode exigir que você implemente controles sobre como as equipes são nomeadas e classificadas, quem pode criar equipes e a expiração, retenção e arquivamento da equipe. Isso é chamado de governança. Você pode usar o Azure Active Directory (Azure AD) para configurar cada uma dessas áreas.


| Pergunte-se | Ação |
|--------------|--------|
|Será necessário implementar controles sobre quem tem autorização para criar equipes?| Leia [Plano de governança no Teams](plan-teams-governance.md).|
|Precisarei implementar controles sobre como as equipes são nomeadas?|Leia [Aplicar uma política de nomenclatura para grupos do Office 365 no Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy).|
|||

### <a name="teams-application-policy-side-rail-control"></a>Política de aplicativo do Teams (controle lateral)

Um aplicativo fixado é exibido na lateral do Teams. Ao criar políticas de aplicativo do Teams, você pode predefinir conjuntos de aplicativos fixados do Teams para personalizá-lo para grupos selecionados de usuários. Por padrão, a configuração **Permitir aplicativos externos no Microsoft Teams** está habilitada.

| Pergunte-se | Ação |
|--------------|--------|
|Devo criar conjuntos predefinidos de aplicativos Teams fixados? | Leia [Configurações de administração para aplicativos no Teams](admin-settings.md).|
|Como decidir quais grupos receberão esses agrupamentos de aplicativos?|Leia [Permissões e considerações dos aplicativos Teams](app-permissions.md).|
|||

### <a name="archiving-and-compliance"></a>Arquivamento e conformidade 

Sua organização pode exigir que você implemente controles sobre como as equipes são arquivadas e os tipos de dados que são retidos em certos tipos de equipes. Para saber quais configurações são ativadas por padrão, leia [Visão geral de segurança e conformidade no Teams](security-compliance-overview.md).

| Pergunte-se | Ação |
|--------------|--------|
|Será necessário configurar a retenção das equipes?|Para configurar políticas de retenção, confira [Configurar políticas de retenção do Teams](retention-policies.md).|
|Será necessário configurar o arquivamento das equipes?|Para arquivar ou restaurar uma equipe, confira [Arquivar ou restaurar uma equipe](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).|
|Será necessário definir mais configurações de conformidade?|Para obter informações sobre segurança e conformidade, confira [Visão geral de segurança e conformidade no Teams](security-compliance-overview.md).|
|||

### <a name="conditional-access"></a>Acesso condicional 

O Teams depende muito do Exchange Online, do SharePoint Online e do Skype for Business Online para cenários principais de produtividade, como reuniões, calendários, chats de interoperabilidade e compartilhamento de arquivos. As políticas de acesso condicional definidas para esses aplicativos em nuvem se aplicam ao Teams quando um usuário entra diretamente no Teams, em qualquer cliente. Políticas de acesso condicional que são definidas para os aspectos de controle de aplicativos de nuvem do Teams, por exemplo, se os usuários podem acessar serviços do Teams de determinadas redes.

| Pergunte-se | Ação |
|--------------|--------|
|<br>Será necessário configurar acesso condicional para o Teams?|<ul><li>Para entender como as políticas de acesso funcionam, confira [Como funcionam as políticas de acesso condicional no Teams?](security-compliance-overview.md#how-do-conditional-access-policies-work-for-teams)</li><li>Para configurar a MFA (Autenticação Multifator) para o Teams, confira:<ul><li>[Início rápido: exige o MFA para aplicativos específicos com acesso condicional do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-mfa)</li><li>[Referência de configurações de acesso condicional do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference)</li></ul></ul>|
|||


### <a name="education-edu"></a>Educação (EDU) 

Os profissionais de TI que trabalham com educação podem aproveitar o Teams para Educação, que conta com vários recursos adaptados para atender a cenários específicos de educação para alunos, professores e empresas em geral.

| Pergunte-se | Ação |
|--------------|--------|
|Vou usar modelos do Teams específico de EDU? |Para saber mais sobre o Teams para Educação, confira [Perguntas frequentes de governança do Microsoft Education para administradores](plan-teams-governance-edu.md).|
|Vou implantar a pesquisa com escopo?|Para configurar o Teams para EDU, confira [Início rápido: administradores do Teams para Educação](teams-quick-start-edu.yml).|
|Vou integrar o Teams ao serviço do School Data Sync para provisionar contas de usuários?|[Recursos do Teams para administradores de Educação](resources-teams-edu.md)|
|||

### <a name="government---gcc-considerations"></a>Governo - Considerações de GCC

O uso do Microsoft 365 for Government - GCC (certificado de competência governamental) é apropriado para atender aos requisitos dos profissionais de TI que conduzem implantações do Office 365 em entidades governamentais federais, estaduais, locais, tribais ou territoriais dos EUA ou outras entidades que tratam de dados sujeitos a regulamentações e requisitos governamentais.

| Pergunte-se | Ação |
|--------------|--------|
| Será necessário implantar o Teams em um Microsoft 365 Government - ambiente GCC? | Para ver considerações de implantação, confira [Plano para o Microsoft 365 Government - implantações de GCC](plan-for-government-gcc.md).|
|||

## <a name="next-steps"></a>Próximas etapas
- [Direcionar a adoção](adopt-microsoft-teams-landing-page.md) do chat, equipes, canais e aplicativos.
- Incluir os aplicativos em destaque, como o Planner, na implementação inicial do Teams. Adicionar outros [aplicativos, bots e conectores](deploy-apps-microsoft-teams-landing-page.md) ao direcionar a adoção do Teams.
- [Implementar reuniões e conferências](deploy-meetings-microsoft-teams-landing-page.md)
- [Implementar o Cloud Voice](cloud-voice-landing-page.md)

