---
title: Chat, equipes, canais e aplicativos no Microsoft Teams
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
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
appliesto:
- Microsoft Teams
- seo-marvel-apr2020
- seo-marvel-may2020
ms.openlocfilehash: 19296d5def314bdd54af25c27401a9bbd0972cf2
ms.sourcegitcommit: 69a5d4994ef75b9c16efa99554fb7f2ee1ccf52a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2021
ms.locfileid: "58973009"
---
# <a name="chat-teams-channels--apps-in-microsoft-teams"></a>Chat, equipes, canais e aplicativos no Microsoft Teams

O Teams fornece uma grande experiência de colaboração imediata para sua organização, e a maioria das organizações descobrem que as configurações padrão funcionam para eles. Este artigo o ajuda a decidir se quer alterar alguma das configurações padrão com base no perfil da sua organização e nos requisitos comerciais, e depois o acompanha em cada alteração. Dividimos as configurações em dois grupos, começando com o conjunto central de [alterações que você está mais propenso a fazer](#core-deployment-decisions). O segundo grupo inclui as [configurações adicionais](#additional-deployment-decisions) que você pode querer configura com base nas necessidades da sua organização.

Para começar, assista ao nosso breve vídeo sobre chat, equipes e canais do Teams (4:30 minutos):

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE476Yj]

*Novidades de novembro de 2019*
 - Você já pode [usar o Advisor for Teams (pré-visualização) para ajudá-lo a implantar o Microsoft Teams](use-advisor-teams-roll-out.md). O Advisor for Teams (pré-visualização) o acompanha durante a implementação do seu Teams. Ele avalia seu ambiente do Microsoft 365 ou do Office 365 e identifica as configurações mais comuns que talvez você precise atualizar ou modificar antes de poder implantar o Teams com sucesso.
 - [Canal do YouTube sobre Noções Básicas do Microsoft Teams para TI](https://aka.ms/MicrosoftTeamsforIT), incluindo vídeos curtos (8 a 10 minutos) que mostram como implantar, configurar e gerenciar o Teams.

> [!TIP]
> Recomendamos que você inclua nossos aplicativos que estão em destaque -- como o Planner -- no seu lançamento inicial do Teams. Adicione outros [aplicativos, bots e conectores](deploy-apps-microsoft-teams-landing-page.md) à medida que você impulsiona a adoção do Teams.

 > [!Note]
 > Para saber mais sobre os recursos do Teams em diferentes plataformas, confira [recursos do Teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="chat-deployment-prerequisites"></a>Pré-requisitos de implantação do chat

Antes de implementar o Teams na sua organização, reserve um tempo para confirmar que seu ambiente está pronto para o Teams. Reveja [Prepare a rede da sua organização para o Teams](prepare-network.md) e faça as alterações necessárias no seu ambiente.

|Pergunte a si mesmo|Ação |
|------------|-------|
|Minha organização está pronta para implementar o Teams?|Para responder a essa pergunta, confira: <ul><li>[Preparo da rede da sua organização para o Teams](prepare-network.md)</li><li>[URLs e intervalos de endereços IP](office-365-urls-ip-address-ranges.md)</li><li>[Planejar o Grupos do Microsoft 365 quando criar equipes](plan-office-365-groups.md)</li></ul>|
|||

## <a name="core-deployment-decisions"></a>Decisões importantes sobre implantação

Estas são as configurações de chat, equipes e canais que a maioria das organizações deseja alterar (se as configurações padrão não atenderem suas necessidades).

### <a name="teams-administrators"></a>Administradores do Teams

O Teams fornece um conjunto de funções de administrador personalizado que pode ser usado para administrar o Teams para sua organização. As funções fornecem vários recursos aos administradores.

| Pergunte a si mesmo | Ação |
|--------------|--------|
|A quem será atribuída a função de Administrador de Comunicações de Equipes?|Para saber mais sobre as funções de administrador do Teams, confira [Usar funções de administrador para gerenciar o Microsoft Teams](using-admin-roles.md).|
|A quem será atribuída função de Engenheiro de Suporte de Comunicações de Equipes?|Para atribuir funções de administrador, confira [Atribuir funções de administrador e não administrador aos usuários com o Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).|
|A quem será atribuída a função de Especialista de Suporte de Comunicações do Teams?||
|||

### <a name="teams-owners-and-members"></a>Proprietários e membros do Teams

Além das funções de administrador, o Teams permite que você atribua funções de proprietário e de usuário membro, e seletivamente lhes dá recursos de moderador (se a moderação tiver sido configurada) para controlar quem pode realizar certas ações dentro de um canal. A moderação permite que você controle quem pode iniciar novos postos em um canal, adicionar e remover membros da equipe como moderadores e controlar se os membros da equipe podem responder às mensagens existentes no canal.

|Pergunte a si mesmo|Ação |
|------------|-------|
|Quem deve ser atribuído a cada função? | Para comparar os recursos de cada função, confira [Atribuir proprietários, moderadores e membros de equipe no Microsoft Teams.](assign-roles-permissions.md)
|Como posso atribuir uma função de usuário? | Para atribuir ou alterar uma função, confira [Atribuir uma função de usuário](assign-roles-permissions.md#assign-a-user-role).
|Preciso controlar quem pode postar e responder em um canal? | Para configurar a moderação, confira [Configurar e gerenciar a moderação de canal no Microsoft Teams](manage-channel-moderation-in-teams.md).

### <a name="messaging-policies"></a>Políticas de mensagens

A Política de mensagens controla quais recursos de chat e de mensagens de canal estão disponíveis aos usuários no Teams. Por exemplo, quem pode editar e excluir mensagens enviadas, quem pode usar o chat, quem pode usar memes nas conversas e muito mais. Por padrão, a política global de mensagens é atribuída aos usuários e todos os recursos estão **Ativados**. Você pode usar a política global padrão ou criar uma ou mais políticas de mensagens personalizadas para as pessoas da sua organização. 

|Pergunte a si mesmo|Ação |
|------------|-------|
|Vou personalizar a política global de mensagens?|Para obter informações sobre como usar o Centro de administração do Microsoft Teams para alterar a política global de mensagens ou adicionar uma nova política, confira [Gerenciar políticas de mensagens no Teams](messaging-policies-in-teams.md).|
|Exijo várias políticas de mensagens?|Para criar e atribuir uma política de mensagens no PowerShell, confira [Exemplo de script do PowerShell - Criar e atribuir uma política de mensagens](scripts/powershell-script-teams-messaging-policy-edu.md).|
|Como determinarei quais grupos de usuários receberão qual política de mensagens?|Para saber mais sobre os cmdlets CsTeamsMessagingPolicy, confira [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps).|
||| 

### <a name="external-access"></a>Acesso externo

O acesso externo (anteriormente conhecido como federação) permite que seus usuários Teams e Skype for Business se comuniquem com usuários que estão fora de sua organização. Ao habilitar isso e adicionar domínios à lista permitida, seus usuários podem se comunicar com usuários em outros domínios e organizações. O acesso externo difere do acesso de convidado porque um domínio inteiro recebe permissão de acesso, não um indivíduo. O acesso externo está habilitado por padrão.

|Pergunte a si mesmo|Ação |
|------------|-------|
|<ul><li>Vou ativar o acesso externo para minha organização?</li><li>Se habilitado, vou limitar os domínios com os quais minha organização poderá se comunicar?</li></ul> |<br>Para ativar o acesso externo, confira [Plano para acesso externo](manage-external-access.md#plan-for-external-access).|
|||

### <a name="guest-access"></a>Acesso de convidados

No Teams, o acesso de convidado permite que pessoas que não pertencem à organização acessem canais e equipes. Você pode usar as configurações de acesso de convidado para controlar quais recursos os convidados podem ou não usar. O acesso de convidado está habilitado por padrão. Para saber mais, confira [Acesso de convidado do Teams](./guest-access.md).

> [!NOTE]
> Para obter mais informações sobre acesso externo e acesso de convidado, confira aqui: [Comunicar-se com usuários de outras organizações no Microsoft Teams](communicate-with-users-from-other-organizations.md)


|Pergunte a si mesmo|Ação |
|------------|-------|
|Vou ativar o acesso de convidado para minha organização?|Para habilitar o acesso de convidado, confira [Ativar ou desativar o acesso de convidado no Teams](set-up-guests.md).|
|Se o acesso for habilitado, devo personalizar os recursos disponíveis para pessoas em minha organização?|Para personalizar a disponibilidade dos recursos do acesso de convidado, confira [Autorizar o acesso de convidado no Teams](teams-dependencies.md).|
|||

### <a name="teams-settings"></a>Configurações de equipes

As configurações do Teams permitem que você configure suas equipes para recursos como integração de e-mail, opções de armazenamento em nuvem, guia de organização, configuração do dispositivo da sala de reuniões e escopo de pesquisa. Quando você faz alterações nestas configurações, elas se aplicam a todas as equipes na sua organização. Para obter mais informações, consulte [Configurações do Teams](enable-features-office-365.md#teams-settings).

|Pergunte a si mesmo|Ação |
|------------|-------|
|Vou personalizar as configurações do Teams para minha organização? | Para saber sobre as configurações do Teams e personalizá-las, confira [Configurações do Teams](enable-features-office-365.md#teams-settings).|
|||

### <a name="teams-clients"></a>Clientes do Teams

O Teams suporta uma série de clientes da Web à área de trabalho e ao dispositivo móvel, e a configuração padrão permite que os usuários escolham os clientes que quiserem. Para obter mais informações, consulte [Obter clientes do Teams](get-clients.md).

|Pergunte a si mesmo|Ação |
|------------|-------|
|Vou personalizar a disponibilidade do cliente do Teams para minha organização?|Confira os [Requisitos de hardware para o aplicativo Teams](hardware-requirements-for-the-teams-app.md). |
|Vou personalizar as configurações de cliente do Teams para minha organização?|Saiba como [Instalar o Teams usando o MSI](msi-deployment.md).|
|||

### <a name="teams-usage-reporting"></a>Relatórios de uso do Teams

As funções de Administração Global, Administração de Serviços do Teams e Leitores de Relatórios podem visualizar relatórios de uso do Teams. Para obter mais informações, consulte a [Análise de uso do Microsoft 365](/microsoft-365/admin/usage-analytics/usage-analytics).

|Pergunte a si mesmo|Ação |
|------------|-------|
|<br> Quem precisa ver os relatórios de uso do Teams e eles têm a função correta para visualizá-los? |<ul><li>Se o usuário não for um administrador, [atribua a função de leitor de relatórios](teams-activity-reports.md#reports-reader-role).</li><li>Confira [Funções e permissões](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) e [Exibir e atribuir funções](/azure/active-directory/users-groups-roles/directory-manage-roles-portal) para saber como atribuir funções de administrador no Azure Active Directory. |
|||

### <a name="teams-default-apps"></a>Aplicativos padrão do Teams 

O Teams fornece uma série de aplicativos exclusivos (fornecidos pela Microsoft) e de terceiros para envolver os usuários, apoiar a produtividade e integrar serviços comerciais geralmente usados no Teams. Obtenha aplicativos na Loja do Teams. Os aplicativos são ativados por padrão no Teams. 

Para saber mais sobre a implantação e gerenciamento de aplicativos no Teams, confira nossa orientação detalhada sobre [Aplicativos, bots e conectores](deploy-apps-microsoft-teams-landing-page.md).

## <a name="additional-deployment-decisions"></a>Decisões adicionais de implantação

Convém alterar essas configurações, com base nas necessidades da organização e da configuração.

### <a name="teams-licensing"></a>Licenciamento do Teams

O Teams é fornecido como parte de muitas licenças do Microsoft 365 ou do Office 365. Para obter mais informações sobre o licenciamento do Teams, consulte [Descrição do serviço do Teams da Microsoft](/office365/servicedescriptions/teams-service-description).

|Pergunte a si mesmo|Ação |
|------------|-------|
|Meus usuários têm licenças necessárias para usar todos os recursos do Teams que desejo implementar? | Para aprender sobre os requisitos de licenciamento, leia a [descrição do serviço do Microsoft Teams](/office365/servicedescriptions/teams-service-description).|
|||

### <a name="exchange-and-sharepoint-interoperability"></a>Interoperabilidade entre o Exchange e o SharePoint

Para a experiência integral do Teams, cada usuário deve estar habilitado para o Exchange Online, o SharePoint Online e a criação de grupo do Microsoft 365. Os artigos a seguir descrevem informações relacionadas às caixas de correio do Exchange hospedadas em vários ambientes, como o Exchange e o Teams interagem, assim como considerações similares do SharePoint e do OneDrive for Business.

|Pergunte a si mesmo|Ação |
|------------|-------|
| Será possível implantar os recursos necessários do Teams com as implantações atuais do Exchange e do SharePoint? |Para obter mais informações sobre o Exchange e o SharePoint no Teams, confira:<ul><li> [Como o Exchange e o Teams interagem](exchange-teams-interact.md)</li><li>[Como o SharePoint Online e o OneDrive for Business interagem com o Teams](sharepoint-onedrive-interact.md)|
|||

### <a name="teams-limits-and-specifications"></a>Especificações e limites do Teams 

Ao planejar uma implantação corporativa do Teams, você deve levar em consideração todas as limitações e especificações relevantes, como o número máximo de membros em uma equipe, o número máximo de equipes que um usuário pode criar e assim por diante.

|Pergunte-se|Ação |
|------------|-------|
| Quais limites provavelmente atingirei com a implementação do Teams? | Para saber mais, confira [Limites e especificações para o Teams](limits-specifications-teams.md). |
|||

### <a name="urls-and-ports"></a>URLs e portas

As organizações que mantêm um controle preciso do seu tráfego na Internet devem ler [URLs e intervalos de endereços de IP](/office365/enterprise/urls-and-ip-address-ranges) de uma lista atualizada de URLs, endereços IP, portas e protocolos que devem ser configurados corretamente no Teams. A Microsoft está continuamente melhorando os serviços do Microsoft 365 e do Office 365, além de adicionar novas funções, o que significa que as portas, URLs e endereços de IP necessários podem mudar com o tempo. Recomendamos que você se inscreva por RSS para receber notificações quando estas informações forem atualizadas ou alteradas. No mínimo, certifique-se de ter aberto as portas listadas acima nos [Pré-requisitos de implementação do Chat](#chat-deployment-prerequisites).

|Pergunte a si mesmo|Ação |
|------------|-------|
| Preciso de regras de acesso à Internet para permitir que os usuários usem o Teams ou é suficiente abrir as portas mínimas necessárias? | Para saber mais, confira [URLs e intervalos de endereços IP](office-365-urls-ip-address-ranges.md).|
|||

### <a name="governance-naming-conventions-who-can-create-teams"></a>Governança (convenções de nomenclatura, quem pode criar equipes)

Sua organização pode exigir que você implemente controles sobre como as equipes são nomeadas e classificadas, quem pode criar equipes e duração, retenção e arquivamento das equipes. Isso é chamado de governança. Você pode usar o Azure Active Directory (Azure AD) para configurar cada uma dessas áreas.


| Pergunte a si mesmo | Ação |
|--------------|--------|
|Será necessário implementar controles sobre quem tem autorização para criar equipes?| Leia [Plano de governança no Teams](plan-teams-governance.md).|
|Precisarei implementar controles sobre como as equipes são nomeadas?|Leia [Aplicar uma política de nomenclatura para grupos do Microsoft 365 no Azure AD](/azure/active-directory/users-groups-roles/groups-naming-policy).|
|||

### <a name="teams-application-policy-side-rail-control"></a>Política de aplicativo do Teams (controle lateral)

Um aplicativo afixado é exibido no trilho lateral no Teams. Ao criar políticas de aplicativo do Teams, você pode pré-configurar conjuntos de aplicativos do Teams afixados para personalizar o Teams para grupos selecionados de usuários. Por padrão, a opção **Permitir aplicativos externos na configuração do Teams da Microsoft** é ativada.

| Pergunte a si mesmo | Ação |
|--------------|--------|
|Devo criar conjuntos predefinidos de aplicativos Teams fixados? | Leia [Configurações de administração para aplicativos no Teams](admin-settings.md).|
|Como decidir quais grupos receberão esses agrupamentos de aplicativos?|Leia [Permissões e considerações dos aplicativos Teams](app-permissions.md).|
|||

### <a name="archiving-and-compliance"></a>Arquivamento e conformidade 

Sua organização pode exigir que você implemente controles sobre como as equipes são arquivadas e os tipos de dados que são mantidos em certos tipos de equipes. Leia [Visão geral da segurança e conformidade no Teams](security-compliance-overview.md) para saber quais configurações do Teams são ativadas por padrão.

| Pergunte a si mesmo | Ação |
|--------------|--------|
|Será necessário configurar a retenção das equipes?|Para configurar políticas de retenção, confira [Configurar políticas de retenção do Teams](retention-policies.md).|
|Será necessário configurar o arquivamento das equipes?|Para arquivar ou restaurar uma equipe, confira [Arquivar ou restaurar uma equipe](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).|
|Será necessário definir mais configurações de conformidade?|Para obter informações sobre segurança e conformidade, confira [Visão geral de segurança e conformidade no Teams](security-compliance-overview.md).|
|||

### <a name="conditional-access"></a>Acesso condicional 

O Teams confia muito no Exchange Online, SharePoint Online e Skype for Business Online para cenários centrais de produtividade, incluindo reuniões, calendários, chats de interoperabilidade e compartilhamento de arquivos. As políticas de acesso condicional que são definidas para esses aplicativos em nuvem se aplicam ao Teams quando um usuário entra diretamente no Teams, em qualquer cliente. As políticas de acesso condicional que são configuradas para os aplicativos em nuvem do Teams controlam aspectos como a possibilidade de os usuários acessarem os serviços do Teams de determinadas redes.

| Pergunte a si mesmo | Ação |
|--------------|--------|
|<br>Será necessário configurar acesso condicional para o Teams?|<ul><li>Para entender como as políticas de acesso funcionam, confira [Como funcionam as políticas de acesso condicional no Teams?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)</li><li>Para configurar a autenticação multifator (MFA) para o Teams, consultar:<ul><li>[Início rápido: exige o MFA para aplicativos específicos com acesso condicional do Azure Active Directory](/azure/active-directory/conditional-access/app-based-mfa)</li><li>[Referência de configurações de acesso condicional do Azure Active Directory](/azure/active-directory/conditional-access/technical-reference)</li></ul></ul>|
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

O uso do Microsoft 365 for Government - GCC (Nuvem da Comunidade Governamental) é apropriado para atender aos requisitos de profissionais de TI que estejam conduzindo implantações do Office 365 em entidades governamentais federais, estaduais, locais, tribais ou territoriais dos Estados Unidos, ou outras entidades que manipulem dados sujeitos a regulamentos e exigências governamentais.

| Pergunte a si mesmo | Action |
|--------------|--------|
| Será necessário implantar o Teams em um Office 365 for Government - ambiente GCC? | Para ver considerações de implantação, confira [Plano para o Office 365 Government - implantações de GCC](plan-for-government-gcc.md).|
|||

## <a name="next-steps"></a>Próximas etapas
- [Direcionar a adoção](adopt-microsoft-teams-landing-page.md) do chat, equipes, canais e aplicativos.
- Inclua os aplicativos que estão em destaque — como o Planner — no seu lançamento inicial do Teams. Adicione outros [aplicativos, bots e conectores](deploy-apps-microsoft-teams-landing-page.md) à medida que você impulsiona a adoção do Teams.
- [Implementar reuniões e conferências](deploy-meetings-microsoft-teams-landing-page.md)
- [Implementar o Cloud Voice](cloud-voice-landing-page.md)
