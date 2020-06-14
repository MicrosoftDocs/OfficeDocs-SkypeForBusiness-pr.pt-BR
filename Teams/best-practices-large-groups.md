---
title: Gerenciar grandes equipes no Microsoft Teams-práticas recomendadas
ms.reviewer: abgupta
author: lolaj
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Saiba mais sobre as práticas recomendadas para o gerenciamento de grandes equipes do Microsoft Teams para atender às necessidades da sua organização.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d939b4be4fcd5f3a1045f2f9adde750197b92f29
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638901"
---
<a name="manage-large-teams-in-microsoft-teams---best-practices"></a><span data-ttu-id="fbcb7-103">Gerenciar grandes equipes no Microsoft Teams-práticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="fbcb7-103">Manage large teams in Microsoft Teams - Best practices</span></span>
======================================================

<span data-ttu-id="fbcb7-104">O Microsoft Teams é igualmente eficaz para facilitar a comunicação entre pequenos grupos com dezenas de membros e grupos grandes com milhares de membros.</span><span class="sxs-lookup"><span data-stu-id="fbcb7-104">Microsoft Teams is equally effective at facilitating communications between small groups with dozens of members and large groups with thousands of members.</span></span> <span data-ttu-id="fbcb7-105">Revisar [limites e especificações para equipes](limits-specifications-teams.md) de atualizações em tamanhos de equipe.</span><span class="sxs-lookup"><span data-stu-id="fbcb7-105">Review [Limits and specifications for Teams](limits-specifications-teams.md) for updates on team sizes.</span></span> <span data-ttu-id="fbcb7-106">O aumento no tamanho da equipe leva a desafios operacionais e de gerenciamento exclusivos.</span><span class="sxs-lookup"><span data-stu-id="fbcb7-106">Increase in team size leads to unique management and operational challenges.</span></span> <span data-ttu-id="fbcb7-107">Este artigo descreve as práticas recomendadas para a criação e o gerenciamento de grandes equipes compostas de milhares de membros.</span><span class="sxs-lookup"><span data-stu-id="fbcb7-107">This article describes best practices for creating and managing large teams comprised of thousands of members.</span></span>

## <a name="value-of-large-teams"></a><span data-ttu-id="fbcb7-108">Valor de equipes grandes</span><span class="sxs-lookup"><span data-stu-id="fbcb7-108">Value of large teams</span></span>

<span data-ttu-id="fbcb7-109">As grandes equipes são muito úteis para habilitar os seguintes cenários de colaboração:</span><span class="sxs-lookup"><span data-stu-id="fbcb7-109">Large teams are very useful in enabling the following collaboration scenarios:</span></span>

- <span data-ttu-id="fbcb7-110">**Colaboração em todo o departamento**: se sua organização tiver vários departamentos, como finanças, operações, R&D etc., você poderá criar uma única equipe que inclua todos os membros de um departamento específico.</span><span class="sxs-lookup"><span data-stu-id="fbcb7-110">**Department-wide collaboration**: If your organization has multiple departments such as Finance, Operations, R&D etc., then you can create a single team that includes all members in a specific department.</span></span> <span data-ttu-id="fbcb7-111">Agora todas as comunicações relevantes para um departamento podem ser compartilhadas nesta equipe, o que facilita o acesso instantâneo e o envolvimento dos membros.</span><span class="sxs-lookup"><span data-stu-id="fbcb7-111">Now all communications relevant to a department can be shared in this team, which facilitates instant reach and engagement from members.</span></span>

- <span data-ttu-id="fbcb7-112">**Colaboração em grupos de recursos de funcionários**: as organizações geralmente têm grandes grupos de pessoas com interesses mútuos que pertencem a um departamento ou grupo de trabalho diferente.</span><span class="sxs-lookup"><span data-stu-id="fbcb7-112">**Collaboration in employee resource groups**: Organizations often have large groups of people with mutual interests who belong to a different department or work group.</span></span> <span data-ttu-id="fbcb7-113">Como exemplo, pode haver um grupo de pessoas que compartilham uma paixão por finanças pessoais e investimentos.</span><span class="sxs-lookup"><span data-stu-id="fbcb7-113">As an example, there can be a group of people who share a passion for personal finance and investing.</span></span> <span data-ttu-id="fbcb7-114">Muitas vezes, é difícil conectar-se em uma grande organização.</span><span class="sxs-lookup"><span data-stu-id="fbcb7-114">It's often hard to connect in a large organization.</span></span> <span data-ttu-id="fbcb7-115">Para desenvolver comunidades para tais grupos, os administradores de locatários podem criar uma equipe grande que sirva como um grupo de recursos de toda a empresa pública que qualquer pessoa pode participar e aproveitar.</span><span class="sxs-lookup"><span data-stu-id="fbcb7-115">To develop communities for such groups, tenant admins can create a large team that serves as a public company-wide resource group that anyone can join and take advantage of.</span></span> <span data-ttu-id="fbcb7-116">Por fim, essas comunidades coletam informações que podem ser aproveitadas por membros novos e existentes.</span><span class="sxs-lookup"><span data-stu-id="fbcb7-116">Eventually, these communities collect information that both new and existing members can enjoy.</span></span>

- <span data-ttu-id="fbcb7-117">**Colaboração entre membros internos e externos**: produtos populares muitas vezes desenvolvem uma comunidade de pioneiros que estão ansiosos para experimentar novas versões de produtos e enviar comentários.</span><span class="sxs-lookup"><span data-stu-id="fbcb7-117">**Collaboration between internal and external members**: Popular products often develop a community of early adopters who are eager to try new product releases and provide feedback.</span></span> <span data-ttu-id="fbcb7-118">Pioneiros desenvolve uma relação com grupos de produtos para ajudar a moldar o produto.</span><span class="sxs-lookup"><span data-stu-id="fbcb7-118">Early adopters develop a relationship with product groups to help shape the product.</span></span> <span data-ttu-id="fbcb7-119">Nesses cenários, os administradores de locatários podem configurar uma equipe grande que inclui grupos de produtos internos e avaliadores de produtos externos para facilitar um processo avançado de desenvolvimento de produtos.</span><span class="sxs-lookup"><span data-stu-id="fbcb7-119">In such scenarios, tenant admins can set up a large team which includes both internal product groups and external product evaluators to facilitate a rich product development process.</span></span> <span data-ttu-id="fbcb7-120">Essas equipes também podem fornecer suporte ao cliente para um conjunto de clientes selecionado.</span><span class="sxs-lookup"><span data-stu-id="fbcb7-120">These teams can also provide customer support to a select set of customers.</span></span>

## <a name="create-teams-from-existing-groups"></a><span data-ttu-id="fbcb7-121">Criar equipes a partir de grupos existentes</span><span class="sxs-lookup"><span data-stu-id="fbcb7-121">Create teams from existing groups</span></span>

<span data-ttu-id="fbcb7-122">Use grupos de contatos, grupos de segurança ou grupos do Office para começar a equipe.</span><span class="sxs-lookup"><span data-stu-id="fbcb7-122">Use contact groups, security groups, or Office groups to jump start your team.</span></span> <span data-ttu-id="fbcb7-123">Você pode importar um grupo para criar uma equipe ou criar uma equipe a partir de um grupo do Office.</span><span class="sxs-lookup"><span data-stu-id="fbcb7-123">You can import a group to make a team or create a team from an Office group.</span></span>

<span data-ttu-id="fbcb7-124">**Importar um grupo para criar uma equipe**: quando você importa um grupo com até 3.500 membros para o Teams, o Microsoft Teams calcula automaticamente o número total de membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="fbcb7-124">**Import a group to make a team**: When you import a group with up to 3,500 members into Teams, Teams automatically calculates the total number of members in the group.</span></span> <span data-ttu-id="fbcb7-125">Esta é uma importação única e alterações futuras no grupo não serão atualizadas automaticamente no Teams.</span><span class="sxs-lookup"><span data-stu-id="fbcb7-125">This is a one-time import only and future changes in the group will not automatically be updated in Teams.</span></span>

<span data-ttu-id="fbcb7-126">**Criar uma equipe a partir de um grande grupo do microsoft 365**: quando você cria uma equipe a partir de um grande grupo do Microsoft 365, os membros fazem parte automaticamente do grupo Microsoft 365 **e** da equipe.</span><span class="sxs-lookup"><span data-stu-id="fbcb7-126">**Create a team from a large Microsoft 365 group**: When you create a team from a large Microsoft 365 group, members are automatically part of the Microsoft 365 group **and** the team.</span></span> <span data-ttu-id="fbcb7-127">No futuro, como os membros da equipe se unem ou deixam o grupo do Microsoft 365, eles são automaticamente adicionados ou removidos da equipe.</span><span class="sxs-lookup"><span data-stu-id="fbcb7-127">In the future, as team members join or leave the Microsoft 365 group, they're automatically added or removed from the team.</span></span>

## <a name="create-channels-to-focus-discussions"></a><span data-ttu-id="fbcb7-128">Crie canais para concentrar discussões</span><span class="sxs-lookup"><span data-stu-id="fbcb7-128">Create channels to focus discussions</span></span>

<span data-ttu-id="fbcb7-129">Você pode restringir as discussões em grupo criando canais enfocados.</span><span class="sxs-lookup"><span data-stu-id="fbcb7-129">You can narrow the group discussions by creating focused channels.</span></span> <span data-ttu-id="fbcb7-130">Confira [práticas recomendadas para organizar equipes](best-practices-organizing.md).</span><span class="sxs-lookup"><span data-stu-id="fbcb7-130">See [Best practices for organizing teams](best-practices-organizing.md).</span></span>

## <a name="restrict-channel-creation"></a><span data-ttu-id="fbcb7-131">Restringir a criação de canais</span><span class="sxs-lookup"><span data-stu-id="fbcb7-131">Restrict channel creation</span></span>

<span data-ttu-id="fbcb7-132">Se algum membro da equipe tiver permissão para criar canais, essa equipe poderá ter acúmulo de canais.</span><span class="sxs-lookup"><span data-stu-id="fbcb7-132">If any team member is allowed to create channels, that team can have channel sprawl.</span></span> <span data-ttu-id="fbcb7-133">Os proprietários de equipe devem desativar a criação, a atualização, a exclusão e a restauração dos membros em **configurações > permissões de membros**.</span><span class="sxs-lookup"><span data-stu-id="fbcb7-133">Team owners should turn off channel create, update, delete, and restore for members in **Settings > Member permissions**.</span></span> <span data-ttu-id="fbcb7-134">Consulte [visão geral de equipes e canais](teams-channels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fbcb7-134">See [Overview of teams and channels](teams-channels-overview.md).</span></span>

<span data-ttu-id="fbcb7-135">![Imagem da tela que mostra a seção permissões de membro da guia Configurações do console de administração.](media/no-channel-creation.png "Imagem da tela que é a seção permissões de membro da guia Configurações do console de administração. A opção permitir que membros criem ou excluir canais está desmarcada.")</span><span class="sxs-lookup"><span data-stu-id="fbcb7-135">![Screen image that shows the member permissions section of the admin console Settings tab.](media/no-channel-creation.png "Screen image that member permissions section of the admin console Settings tab. The allow members to create or delete channels options are unchecked.")</span></span>

## <a name="add-favorite-channels"></a><span data-ttu-id="fbcb7-136">Adicionar canais favoritos</span><span class="sxs-lookup"><span data-stu-id="fbcb7-136">Add favorite channels</span></span>

<span data-ttu-id="fbcb7-137">Para acelerar o novo envolvimento do usuário e a descoberta de conteúdo, você pode selecionar os canais favoritos que estão disponíveis para o usuário por padrão.</span><span class="sxs-lookup"><span data-stu-id="fbcb7-137">In order to speed up new user engagement and content discovery, you can select favorite channels that are available to the user by default.</span></span> <span data-ttu-id="fbcb7-138">No painel **canais** do centro de administração, marque os canais na coluna **mostrar para membros** .</span><span class="sxs-lookup"><span data-stu-id="fbcb7-138">In the **Channels** pane of the admin center, check the channels under the **Show for members** column.</span></span>

<span data-ttu-id="fbcb7-139">![Imagem da tela que mostra o painel canais do console de administração.](media/favorite-channels.png "Imagem da tela que mostra o painel canais do console de administração. Alguns canais são verificados para exibição para membros.")</span><span class="sxs-lookup"><span data-stu-id="fbcb7-139">![Screen image that shows the channels pane of the admin console.](media/favorite-channels.png "Screen image that shows channels pane of the admin console. Some channels are checked for Show for members.")</span></span>

 <span data-ttu-id="fbcb7-140">Consulte [criar suas primeiras equipes e canais](get-started-with-teams-create-your-first-teams-and-channels.md) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="fbcb7-140">See [Create your first teams and channels](get-started-with-teams-create-your-first-teams-and-channels.md) for details.</span></span>

## <a name="regulate-applications-and-bots-in-large-teams"></a><span data-ttu-id="fbcb7-141">Regulari aplicativos e bots em equipes grandes</span><span class="sxs-lookup"><span data-stu-id="fbcb7-141">Regulate applications and bots in large teams</span></span>

<span data-ttu-id="fbcb7-142">Para impedir a inclusão de aplicativos ou bots indesejados, os proprietários da equipe podem desabilitar, adicionar, remover e carregar aplicativos e conectores para os membros da equipe.</span><span class="sxs-lookup"><span data-stu-id="fbcb7-142">To prevent addition of distracting applications or bots, team owners can disable, add, remove, and upload apps and connectors for team members.</span></span> <span data-ttu-id="fbcb7-143">No centro de administração, em **configurações > permissões de membro**, desmarque as três opções que permitem aos membros adicionar aplicativos ou conectores.</span><span class="sxs-lookup"><span data-stu-id="fbcb7-143">In the admin center under **Settings > Member permissions**, uncheck the three options that allow members to add apps or connectors.</span></span>

<span data-ttu-id="fbcb7-144">![Imagem da tela que mostra a seção permissões de membro do painel configurações.](media/disable-bots-connectors.png "Imagem da tela que mostra a seção permissão de membro do painel configurações. As opções para permitir que os membros adicionem aplicativos ou conectores estão desmarcadas.")</span><span class="sxs-lookup"><span data-stu-id="fbcb7-144">![Screen image that shows the Member permissions section of the Settings pane.](media/disable-bots-connectors.png "Screen image that shows the Member permission section of the Settings pane. The options for allow members to add apps or connectors are unchecked.")</span></span>

<span data-ttu-id="fbcb7-145">Consulte [aplicativos, bots & conectores](deploy-apps-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="fbcb7-145">See [Apps, bots, & connectors](deploy-apps-microsoft-teams-landing-page.md).</span></span>

## <a name="regulate-team-and-channel-mentions"></a><span data-ttu-id="fbcb7-146">Regular menção de equipe e de canal</span><span class="sxs-lookup"><span data-stu-id="fbcb7-146">Regulate team and channel mentions</span></span>

<span data-ttu-id="fbcb7-147">As menção de equipe e de canal podem ser usadas para chamar a atenção de toda a equipe para determinadas Postagens de canal.</span><span class="sxs-lookup"><span data-stu-id="fbcb7-147">Team and channel mentions can be used to draw the attention of the whole team to certain channel posts.</span></span> <span data-ttu-id="fbcb7-148">Quando uma menção é usada em uma postagem, uma notificação é enviada para milhares de membros da equipe.</span><span class="sxs-lookup"><span data-stu-id="fbcb7-148">Once a mention is used in a post, a notification is sent to thousands of team members.</span></span> <span data-ttu-id="fbcb7-149">Se as notificações forem muito frequentes, os membros da equipe poderão ficar sobrecarregados e poderão reclamar com os proprietários da equipe.</span><span class="sxs-lookup"><span data-stu-id="fbcb7-149">If the notifications are too frequent, then team members can become overloaded and might complain to team owners.</span></span> <span data-ttu-id="fbcb7-150">Para impedir que a equipe ou o canal mencionem, desative as caixas no painel configurações do Teams e de canal para os membros desmarcando as caixas no painel configurações do teams **> @mentions** .</span><span class="sxs-lookup"><span data-stu-id="fbcb7-150">To prevent team or channel mentions, turn off team and channel mentions for members by unchecking the boxes in the teams **Settings > @mentions** pane.</span></span>

<span data-ttu-id="fbcb7-151">![Imagem da tela que mostra a seção em menção do painel configurações.](media/no-at-mentions.png "Imagem da tela que mostra a seção em menção do painel configurações. As opções para mostrar e conceder acesso a membros em menção são desmarcadas.")</span><span class="sxs-lookup"><span data-stu-id="fbcb7-151">![Screen image that shows the at Mentions section of the Settings pane.](media/no-at-mentions.png "Screen image that shows the at Mentions section of the Settings pane. The options for show and give members access to at mentions are unchecked.")</span></span>

## <a name="consider-setting-up-moderation-in-your-channels"></a><span data-ttu-id="fbcb7-152">Considerar a configuração da moderação em seus canais</span><span class="sxs-lookup"><span data-stu-id="fbcb7-152">Consider setting up moderation in your channels</span></span>

<span data-ttu-id="fbcb7-153">Os proprietários da equipe podem ativar a moderação de um canal para controlar quem pode iniciar novas postagens e responder a postagens no canal.</span><span class="sxs-lookup"><span data-stu-id="fbcb7-153">Team owners can turn on moderation for a channel to control who can start new posts and reply to posts in that channel.</span></span> <span data-ttu-id="fbcb7-154">Ao configurar a moderação, você pode escolher um ou mais membros da equipe para serem moderadores.</span><span class="sxs-lookup"><span data-stu-id="fbcb7-154">When you set up moderation, you can choose one or more team members to be moderators.</span></span> <span data-ttu-id="fbcb7-155">Os proprietários da equipe são Moderadores por padrão.</span><span class="sxs-lookup"><span data-stu-id="fbcb7-155">Team owners are moderators by default.</span></span> <span data-ttu-id="fbcb7-156">Para obter mais informações, consulte [configurar e gerenciar a moderação do canal](manage-channel-moderation-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="fbcb7-156">For more information, see [Set up and manage channel moderation](manage-channel-moderation-in-teams.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="fbcb7-157">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="fbcb7-157">Related topics</span></span>

- [<span data-ttu-id="fbcb7-158">Práticas recomendadas para organizar equipes</span><span class="sxs-lookup"><span data-stu-id="fbcb7-158">Best practices for organizing Teams</span></span>](best-practices-organizing.md)
- [<span data-ttu-id="fbcb7-159">Criar uma equipe de toda a organização</span><span class="sxs-lookup"><span data-stu-id="fbcb7-159">Create an org-wide team</span></span>](create-an-org-wide-team.md)