---
title: Chat, equipes, canais e aplicativos no Microsoft Teams
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.subservice: teams-chat
audience: admin
search.appverid: MET150
description: Contém orientações passo a passo para definir as configurações do Teams para chat, equipes, aplicativos e canais no Microsoft Teams.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.quickstartteamsadmin
- intro-get-started
- seo-marvel-apr2020
- seo-marvel-may2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 10063b2b6c8c0f92de8d949578133b2577ff6d9f
ms.sourcegitcommit: ed7d3b12d4bfe48863de873360c2ae90bbb15530
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69194912"
---
# <a name="chat-teams-channels--apps-in-microsoft-teams"></a>Chat, equipes, canais e aplicativos no Microsoft Teams

Teams provides a great out-of-the-box collaboration experience for your organization, and most organizations find that the default settings work for them. This article helps you decide whether to change any of the default settings, based on your organization's profile and business requirements, then it walks you through each change. We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions). The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.

Para começar, assista ao nosso breve vídeo sobre chat, equipes e canais do Teams (4:30 minutos):

<br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE476Yj?autoplay=false]

You can use [Advisor for Teams](use-advisor-teams-roll-out.md) to help you roll out Microsoft Teams. Advisor for Teams walks you through your Teams rollout. It assesses your Microsoft 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.

> [!TIP]
> É recomendável incluir os aplicativos em destaque, como o Planner, na implementação inicial do Teams. Adicione outros [aplicativos do Teams](deploy-apps-microsoft-teams-landing-page.md) à medida que você impulsiona a adoção do Teams.

 > [!Note]
 > Para saber mais sobre os recursos do Teams em diferentes plataformas, confira [recursos do Teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="chat-deployment-prerequisites"></a>Pré-requisitos de implantação do chat

Before you roll out Teams across your organization, take time to confirm that your environment is ready for Teams. Review [Prepare your organization's network for Teams](prepare-network.md) and make any required changes to your environment.

|Pergunte-se|Ação |
|------------|-------|
|Minha organização está pronta para implementar o Teams?|Para responder a essa pergunta, confira: <ul><li>[Preparo da rede da sua organização para o Teams](prepare-network.md)</li><li>[URLs e intervalos de endereços IP](office-365-urls-ip-address-ranges.md)</li><li>[Planejar o Grupos do Microsoft 365 quando criar equipes](plan-office-365-groups.md)</li></ul>|

## <a name="core-deployment-decisions"></a>Decisões importantes sobre implantação

Estas são as configurações de chat, equipes e canais que a maioria das organizações deseja alterar (se as configurações padrão não atenderem suas necessidades).

### <a name="teams-administrators"></a>Administradores do Teams

Teams provides a set of custom administrator roles that can be used to manage Teams for your organization. The roles provide various capabilities to administrators.

| Pergunte-se | Ação |
|--------------|--------|
|A quem será atribuída a função de Administrador de Comunicações de Equipes?|Para saber mais sobre as funções de administrador do Teams, confira [Usar funções de administrador para gerenciar o Microsoft Teams](using-admin-roles.md).|
|A quem será atribuída função de Engenheiro de Suporte de Comunicações de Equipes?|Para atribuir funções de administrador, confira [Atribuir funções de administrador e não administrador aos usuários com o Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).|
|A quem será atribuída a função de Especialista de Suporte de Comunicações do Teams?||

### <a name="teams-owners-and-members"></a>Proprietários e membros do Teams

In addition to administrator roles, Teams lets you assign owner and member user roles, and selectively give them moderator capabilities (if moderation has been set up) to control who can perform certain actions within a channel. Moderation allows you to control who can start new posts in a channel, add and remove team members as moderators, and control whether team members can reply to existing channel messages.

|Pergunte-se|Ação |
|------------|-------|
|Quem deve ser atribuído a cada função? | Para comparar os recursos de cada função, confira [Atribuir proprietários, moderadores e membros de equipe no Microsoft Teams.](assign-roles-permissions.md)
|Como posso atribuir uma função de usuário? | Para atribuir ou alterar uma função, confira [Atribuir uma função de usuário](assign-roles-permissions.md).
|Preciso controlar quem pode postar e responder em um canal? | Para configurar a moderação, confira [Configurar e gerenciar a moderação de canal no Microsoft Teams](manage-channel-moderation-in-teams.md).

### <a name="messaging-policies"></a>Políticas de mensagens

Messaging policies control which chat and channel messaging features are available to users in Teams. For example, who can edit and delete sent messages, who can use chat, who can use memes in conversations, and more. By default, users are assigned the global messaging policy and all features are **On**. You can use the default global policy or create one or more custom messaging policies for people in your organization.

|Pergunte-se|Ação |
|------------|-------|
|Vou personalizar a política global de mensagens?|Para obter informações sobre como usar o Centro de administração do Microsoft Teams para alterar a política global de mensagens ou adicionar uma nova política, confira [Gerenciar políticas de mensagens no Teams](messaging-policies-in-teams.md).|
|Exijo várias políticas de mensagens?|Para criar e atribuir uma política de mensagens no PowerShell, confira [Exemplo de script do PowerShell - Criar e atribuir uma política de mensagens](scripts/powershell-script-teams-messaging-policy-edu.md).|
|Como determinarei quais grupos de usuários receberão qual política de mensagens?|Para saber mais sobre os cmdlets CsTeamsMessagingPolicy, confira [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy).|

### <a name="external-access"></a>Acesso externo

External access (federation) lets your users communicate with people outside of your organization via chat. By turning this on and adding domains to the allowed list, your users can communicate with users in other domains and organizations. External access is turned on by default.

|Pergunte-se|Ação |
|------------|-------|
|<ul><li>Desativarei reuniões externas e chats para minha organização?</li><li>Se habilitado, vou limitar os domínios com os quais minha organização poderá se comunicar?</li></ul> |<br>Para ativar ou desativar a reunião externa e o chat, consulte [Gerenciar reuniões externas e o chat](manage-external-access.md).|

### <a name="guest-access"></a>Acesso de convidados

Guest access in Teams lets individuals outside your organization access teams and channels. You can use the guest access settings to control which features guests can or can't use. Guest access is turned on by default. To learn more, see [Guest access in Teams](./guest-access.md).

> [!NOTE]
> Para obter mais informações sobre acesso externo e acesso de convidado, consulte aqui - [Comunicar-se com usuários de outras organizações no Microsoft Teams](communicate-with-users-from-other-organizations.md)

|Pergunte-se|Ação |
|------------|-------|
|Desativarei o acesso de convidado para minha organização?|Para ativar ou desativar o acesso de convidados, consulte [Ativar ou desativar o acesso de convidados no Teams](set-up-guests.md).|
|Se o acesso for habilitado, devo personalizar os recursos disponíveis para pessoas em minha organização?|Para personalizar a disponibilidade dos recursos do acesso de convidado, confira [Autorizar o acesso de convidado no Teams](teams-dependencies.md).|

### <a name="private-channels"></a>Canais privados

Os canais privados permitem que um subconjunto de membros da equipe colabore em um espaço privado que outros membros da equipe não podem ver ou acessar. É possível adicionar qualquer pessoa, inclusive convidados, como membro de um canal privado, desde que já sejam membros da equipe.

|Pergunte-se|Ação |
|------------|-------|
|Desejo permitir que os membros e proprietários da equipe criem canais privados?|Para definir a política de canais privados para sua organização, consulte [Gerenciar políticas de canal no Microsoft Teams](teams-policies.md)|

### <a name="shared-channels"></a>Canais compartilhados

Os canais compartilhados permitem adicionar pessoas que não são membros de uma equipe a um canal. Isso inclui pessoas que estão fora da sua organização. Os canais compartilhados oferecem vantagens sobre o acesso de convidados, pois para as pessoas de fora da sua organização não é exigido uma conta de convidado no seu diretório.

|Pergunte-se|Ação |
|------------|-------|
|Quando usar canais compartilhados em vez do acesso para convidado?|Consulte [Canais compartilhados no Microsoft Teams](shared-channels.md).|
|<ul><li>Permitirei que os proprietários de equipes criem canais compartilhados?</li><li>Permitirei que os proprietários de equipes compartilhem canais com pessoas de fora da organização?</li><li>Permitirei que os usuários participem de canais compartilhados que estejam fora da organização?</li></ul> |<br>Para definir a política de canais compartilhados para sua organização, consulte [Gerenciar políticas de canal no Microsoft Teams](teams-policies.md).|

### <a name="teams-settings"></a>Configurações de equipes

Teams settings let you set up your teams for features such as email integration, cloud storage options, organization tab, meeting room device setup, and search scope. When you make changes to these settings, they apply to all the teams in your organization. To learn more, see [Teams settings](enable-features-office-365.md#teams-settings).

|Pergunte-se|Ação |
|------------|-------|
|Vou personalizar as configurações do Teams para minha organização? | Para saber sobre as configurações do Teams e personalizá-las, confira [Configurações do Teams](enable-features-office-365.md#teams-settings).|

### <a name="teams-clients"></a>Clientes do Teams

Teams supports a number of clients from web to desktop to mobile, and the default configuration lets users choose whichever clients they want. To learn more, see [Get clients for Teams](get-clients.md).

|Pergunte-se|Ação |
|------------|-------|
|Vou personalizar a disponibilidade do cliente do Teams para minha organização?|Confira os [Requisitos de hardware para o aplicativo Teams](hardware-requirements-for-the-teams-app.md). |
|Vou personalizar as configurações de cliente do Teams para minha organização?|Saiba como [Instalar o Teams usando o MSI](msi-deployment.md).|

### <a name="teams-usage-reporting"></a>Relatórios de uso do Teams

The Global Admin, Teams Service Admin, and Reports Readers roles can view Teams usage reports. To learn more, see the [Microsoft 365 usage analytics](/microsoft-365/admin/usage-analytics/usage-analytics).

|Pergunte-se|Ação |
|------------|-------|
|<br> Quem precisa ver os relatórios de uso do Teams e eles têm a função correta para visualizá-los? |<ul><li>Se o usuário não for um administrador, [atribua a função de leitor de relatórios](teams-activity-reports.md#reports-reader-role).</li><li>Confira [Funções e permissões](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) e [Exibir e atribuir funções](/azure/active-directory/users-groups-roles/directory-manage-roles-portal) para saber como atribuir funções de administrador no Azure Active Directory.|

### <a name="teams-default-apps"></a>Aplicativos padrão do Teams

Teams provides a number of first-party (Microsoft provided) and third-party apps to engage users, support productivity, and integrate commonly used business services into Teams. Get apps from the Teams Store. Apps are turned on by default in Teams.

Para saber mais sobre como implantar e gerenciar aplicativos no Teams, confira nossas diretrizes detalhadas de [gerenciamento de aplicativos](deploy-apps-microsoft-teams-landing-page.md) .

## <a name="additional-deployment-decisions"></a>Decisões adicionais de implantação

Convém alterar essas configurações, com base nas necessidades da organização e da configuração.

### <a name="teams-licensing"></a>Licenciamento do Teams

O Teams é fornecido como parte das muitas licenças do Microsoft 365.

|Pergunte-se|Ação |
|------------|-------|
|Meus usuários têm licenças necessárias para usar todos os recursos do Teams que desejo implementar? | Para aprender sobre os requisitos de licenciamento, leia a [descrição do serviço do Microsoft Teams](/office365/servicedescriptions/teams-service-description).|

### <a name="exchange-and-sharepoint-interoperability"></a>Interoperabilidade entre o Exchange e o SharePoint

For the full Teams experience, every user should be enabled for Exchange, SharePoint, and Microsoft 365 group creation. The following articles outline information related to Exchange mailboxes hosted in various environments, how Exchange and Teams interact, and similar considerations for SharePoint and OneDrive.

|Pergunte-se|Ação |
|------------|-------|
| Será possível implantar os recursos necessários do Teams com as implantações atuais do Exchange e do SharePoint? |Para obter mais informações sobre o Exchange e o SharePoint no Teams, confira:<ul><li> [Como o Exchange e o Teams interagem](exchange-teams-interact.md)</li><li>[Como o SharePoint Online e o OneDrive interagem com o Teams](sharepoint-onedrive-interact.md)|

### <a name="teams-limits-and-specifications"></a>Especificações e limites do Teams

Ao planejar uma implantação corporativa do Teams, você deve levar em consideração todas as limitações e especificações relevantes, como o número máximo de membros em uma equipe, o número máximo de equipes que um usuário pode criar e assim por diante.

|Pergunte-se|Ação |
|------------|-------|
| Quais limites provavelmente atingirei com a implementação do Teams? | Para saber mais, confira [Limites e especificações para o Teams](limits-specifications-teams.md). |

### <a name="urls-and-ports"></a>URLs e portas

Organizations that maintain fine-grained control of their internet traffic should read [URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges) for an up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams. Microsoft is continuously improving the Microsoft 365 services and adding new functionality, which means the required ports, URLs, and IP addresses may change over time. We recommend that you subscribe via RSS to receive notifications when this information is updated or changed. At a minimum, make sure you've opened the ports listed above in [Chat deployment prerequisites](#chat-deployment-prerequisites).

|Pergunte-se|Ação |
|------------|-------|
| Preciso de regras de acesso à Internet para permitir que os usuários usem o Teams ou é suficiente abrir as portas mínimas necessárias? | Para saber mais, confira [URLs e intervalos de endereços IP](office-365-urls-ip-address-ranges.md).|

### <a name="governance-naming-conventions-who-can-create-teams"></a>Governança (convenções de nomenclatura, quem pode criar equipes)

Your organization might require that you implement controls on how teams are named and classified, who can create teams, and team expiration, retention, and archiving. This is called governance. You can use Azure Active Directory (Azure AD) to configure each of these areas.

| Pergunte-se | Ação |
|--------------|--------|
|Será necessário implementar controles sobre quem tem autorização para criar equipes?| Leia [Plano de governança no Teams](plan-teams-governance.md).|
|Precisarei implementar controles sobre como as equipes são nomeadas?|Leia [Aplicar uma política de nomenclatura para Grupos do Microsoft 365 no Azure AD](/azure/active-directory/users-groups-roles/groups-naming-policy).|

### <a name="teams-application-policy-side-rail-control"></a>Política de aplicativo do Teams (controle lateral)

A pinned app shows up in the side rail in Teams. By creating Teams application policies, you can preconfigure sets of pinned Teams apps to personalize Teams for select groups of users. By default, the **Allow external apps in Microsoft Teams** setting is turned on.

| Pergunte-se | Ação |
|--------------|--------|
|Devo criar conjuntos predefinidos de aplicativos Teams fixados? | Leia [Configurações de administração para aplicativos no Teams](admin-settings.md).|
|Como decidir quais grupos receberão esses agrupamentos de aplicativos?|Leia [Permissões e considerações dos aplicativos Teams](app-permissions.md).|

### <a name="archiving-and-compliance"></a>Arquivamento e conformidade

Your organization might require that you implement controls on how teams are archived and the types of data that are held in certain types of teams. Read [Overview of security and compliance in Teams](security-compliance-overview.md) to learn which Teams settings are turned on by default.

| Pergunte-se | Ação |
|--------------|--------|
|Será necessário configurar a retenção das equipes?|Para configurar políticas de retenção, confira [Configurar políticas de retenção do Teams](retention-policies.md).|
|Será necessário configurar o arquivamento das equipes?|Para arquivar ou restaurar uma equipe, confira [Arquivar ou restaurar uma equipe](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).|
|Será necessário definir mais configurações de conformidade?|Para obter informações sobre segurança e conformidade, confira [Visão geral de segurança e conformidade no Teams](security-compliance-overview.md).|

### <a name="conditional-access"></a>Acesso condicional

Teams relies heavily on Exchange and SharePoint for core productivity scenarios, including meetings, calendars, interop chats, and file sharing. Conditional access policies that are set for these cloud apps apply to Teams when a user signs in directly to Teams, on any client. Conditional access policies that are set for the Teams cloud app control aspects such as whether users can access Teams services from certain networks.

| Pergunte-se | Ação |
|--------------|--------|
|<br>Será necessário configurar acesso condicional para o Teams?|<ul><li>Para entender como as políticas de acesso funcionam, confira [Como funcionam as políticas de acesso condicional no Teams?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)</li><li>Para configurar a MFA (Autenticação Multifator) para o Teams, confira:<ul><li>[Início rápido: exige o MFA para aplicativos específicos com acesso condicional do Azure Active Directory](/azure/active-directory/conditional-access/app-based-mfa)</li><li>[Referência de configurações de acesso condicional do Azure Active Directory](/azure/active-directory/conditional-access/technical-reference)</li></ul></ul>|

### <a name="education-edu"></a>Educação (EDU)

Os profissionais de TI que trabalham com educação podem aproveitar o Teams para Educação, que conta com vários recursos adaptados para atender a cenários específicos de educação para alunos, professores e empresas em geral.

| Pergunte-se | Ação |
|--------------|--------|
|Vou usar modelos do Teams específico de EDU? |Para saber mais sobre o Teams para Educação, confira [Perguntas frequentes de governança do Microsoft Education para administradores](plan-teams-governance-edu.md).|
|Vou implantar a pesquisa com escopo?|Para configurar o Teams para EDU, confira [Início rápido: administradores do Teams para Educação](teams-quick-start-edu.yml).|
|Vou integrar o Teams ao serviço do School Data Sync para provisionar contas de usuários?|[Recursos do Teams para administradores de Educação](resources-teams-edu.md)|

### <a name="government---gcc-considerations"></a>Governo - Considerações de GCC

O uso do Microsoft 365 for Government - GCC (Nuvem da Comunidade Governamental) é apropriado para atender aos requisitos de profissionais de TI que estejam conduzindo implantações do Office 365 em entidades governamentais federais, estaduais, locais, tribais ou territoriais dos Estados Unidos, ou outras entidades que manipulem dados sujeitos a regulamentos e exigências governamentais.

| Pergunte a si mesmo | Ação |
|--------------|--------|
| Precisarei implantar o Teams em um ambiente Office 365 for Government – GCC? | Para ver considerações de implantação, confira [Plano para o Office 365 Government - implantações de GCC](plan-for-government-gcc.md).|

## <a name="next-steps"></a>Próximas etapas

- [Direcionar a adoção](adopt-microsoft-teams-landing-page.md) do chat, equipes, canais e aplicativos.
- Incluir os aplicativos em destaque, como o Planner, na implementação inicial do Teams. Adicione outro [aplicativo do Teams](deploy-apps-microsoft-teams-landing-page.md) à medida que você impulsiona a adoção do Teams.
- [Implementar reuniões e conferências](deploy-meetings-microsoft-teams-landing-page.md)
- [Implementar o Cloud Voice](cloud-voice-landing-page.md)
