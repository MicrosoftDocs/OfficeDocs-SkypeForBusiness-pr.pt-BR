---
title: Mova as suas equipes do StaffHub para Turnos do Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 3/29/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Saiba como mover suas equipes do Microsoft StaffHub e agendar dados para turnos no Microsoft Teams.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: b6354c2edd4d8504aeb2c84715b982f6bf793d33
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548290"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="2ad41-103">Mover suas equipes do Microsoft StaffHub para turnos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2ad41-103">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2ad41-104">A partir de 1 ° de outubro de 2019, o Microsoft StaffHub será desativado.</span><span class="sxs-lookup"><span data-stu-id="2ad41-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="2ad41-105">Estamos criando recursos de StaffHub no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2ad41-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="2ad41-106">Hoje, o Teams inclui o aplicativo turnos para gerenciamento de agendamento e recursos adicionais se acumularão ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="2ad41-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="2ad41-107">O StaffHub deixará de funcionar para todos os usuários em 1 ° de outubro de 2019.</span><span class="sxs-lookup"><span data-stu-id="2ad41-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="2ad41-108">Qualquer pessoa que tentar abrir o StaffHub será exibida uma mensagem direcionando-o para o download do teams.</span><span class="sxs-lookup"><span data-stu-id="2ad41-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="2ad41-109">Para saber mais, confira [Microsoft StaffHub para ser desativado](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="2ad41-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

> <span data-ttu-id="2ad41-110">O recurso discutido neste artigo ainda não foi lançado.</span><span class="sxs-lookup"><span data-stu-id="2ad41-110">The capability discussed in this article hasn't yet been released.</span></span> <span data-ttu-id="2ad41-111">Ele foi anunciado e estará disponível em breve, no início de junho de 2019.</span><span class="sxs-lookup"><span data-stu-id="2ad41-111">It's been announced, and is coming soon, in early June 2019.</span></span> <span data-ttu-id="2ad41-112">Se você for um administrador, poderá descobrir quando isso estará disponível no centro de mensagens (no centro de administração do [Microsoft 365](https://portal.office.com/adminportal/home)).</span><span class="sxs-lookup"><span data-stu-id="2ad41-112">If you're an admin, you can find out when this will be available in the Message Center (in the [Microsoft 365 admin center](https://portal.office.com/adminportal/home)).</span></span>

<span data-ttu-id="2ad41-113">O aplicativo turnos no Microsoft Teams oferece uma abordagem simples para o gerenciamento de cronogramas e o fluxo constante de trocas de turnos e cancelamentos que ocorrem diariamente.</span><span class="sxs-lookup"><span data-stu-id="2ad41-113">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="2ad41-114">Os membros da equipe podem acessar o cronograma e deslocar as informações diretamente no aplicativo e em seus dispositivos para definir suas preferências, gerenciar seus cronogramas e solicitar folga.</span><span class="sxs-lookup"><span data-stu-id="2ad41-114">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="2ad41-115">Este artigo apresenta uma orientação sobre como mover as equipes do StaffHub da sua organização e agendar dados para turnos no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2ad41-115">This article walks you through how to move your organization’s StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="2ad41-116">Seja você uma pequena empresa com uma ou duas equipes do StaffHub ou uma grande empresa com centenas de equipes do StaffHub, você encontrará as diretrizes de administração necessárias para ajudar a fazer sua transição para o Microsoft Teams com êxito.</span><span class="sxs-lookup"><span data-stu-id="2ad41-116">Whether you’re a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you’ll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="2ad41-117">Você deve ser um administrador global para executar as etapas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="2ad41-117">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="2ad41-118">Se ainda não tiver feito isso, examine as [perguntas frequentes sobre](microsoft-staffhub-to-be-retired.md) a descontinuação do StaffHub para obter respostas para qualquer pergunta que você tenha.</span><span class="sxs-lookup"><span data-stu-id="2ad41-118">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span> 

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="2ad41-119">O que você precisa saber sobre a mudança para o Teams</span><span class="sxs-lookup"><span data-stu-id="2ad41-119">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="2ad41-120">Quando mover para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2ad41-120">When to move to Teams</span></span>

<span data-ttu-id="2ad41-121">A partir de 1 ° de outubro de 2019, a StaffHub será desativada.</span><span class="sxs-lookup"><span data-stu-id="2ad41-121">Effective October 1, 2019, StaffHub will be retired.</span></span> <span data-ttu-id="2ad41-122">Recomendamos que você comece a usar o Microsoft Teams hoje e comece a fazer a transição das equipes e dos usuários da sua organização do StaffHub.</span><span class="sxs-lookup"><span data-stu-id="2ad41-122">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="2ad41-123">Com o gerenciamento de agendamento sendo o recurso mais comumente usado no StaffHub, recomendamos que você use o aplicativo turnos no Microsoft Teams, avançando.</span><span class="sxs-lookup"><span data-stu-id="2ad41-123">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="2ad41-124">O que é movido para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2ad41-124">What is moved to Teams</span></span>

<span data-ttu-id="2ad41-125">Detalhes do usuário, informações do cronograma e dados de chat e arquivos são migrados para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2ad41-125">User details, schedule information, and chat and file data are transitioned to Teams.</span></span> <span data-ttu-id="2ad41-126">Isso inclui associação da equipe, cronogramas da equipe e chats e arquivos dos últimos 90 dias.</span><span class="sxs-lookup"><span data-stu-id="2ad41-126">This includes team membership, team schedules, and chats and files from the last 90 days.</span></span>

<span data-ttu-id="2ad41-127">Cada equipe do StaffHub precisa de um grupo do Office 365 correspondente.</span><span class="sxs-lookup"><span data-stu-id="2ad41-127">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="2ad41-128">Se uma equipe do StaffHub não tiver um grupo do Office 365 associado a ela, uma será criada automaticamente para você dar suporte à transição.</span><span class="sxs-lookup"><span data-stu-id="2ad41-128">If a StaffHub team doesn't have an Office 365 Group associated with it, one is automatically created for you to support the transition.</span></span> <span data-ttu-id="2ad41-129">Devido à diferença na nomenclatura de equipes e grupos entre o Teams e o StaffHub, você pode ver um nome de equipe diferente no Teams.</span><span class="sxs-lookup"><span data-stu-id="2ad41-129">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span>

<span data-ttu-id="2ad41-130">À medida que você muda de equipe do StaffHub para o Teams, os usuários não têm mais acesso às suas agendas no StaffHub e são redirecionados para turnos no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2ad41-130">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="2ad41-131">Recomendamos que você comunique essa alteração a toda a sua organização para minimizar as interrupções e incentivar os usuários a adotar e explorar o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2ad41-131">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span> <span data-ttu-id="2ad41-132">Se você tiver o Azure AD Premium, poderá [executar um relatório](run-report-to-show-staffhub-usage.md) para obter uma lista de usuários do StaffHub em sua organização que precisam saber mais sobre essa alteração.</span><span class="sxs-lookup"><span data-stu-id="2ad41-132">If you have Azure AD Premium, you can [run a report](run-report-to-show-staffhub-usage.md) to get a list of StaffHub users in your organization who need to know about this change.</span></span>  

<span data-ttu-id="2ad41-133">Não há opção de reversão após mover uma equipe do StaffHub para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2ad41-133">There's no rollback option after you move a StaffHub team to Teams.</span></span>

### <a name="user-experience-when-you-move-a-team"></a><span data-ttu-id="2ad41-134">Experiência do usuário ao mover uma equipe</span><span class="sxs-lookup"><span data-stu-id="2ad41-134">User experience when you move a team</span></span>

<span data-ttu-id="2ad41-135">Há um tempo de inatividade mínimo (menos de um segundo) para os usuários quando sua equipe é comutada de StaffHub para turnos no Teams.</span><span class="sxs-lookup"><span data-stu-id="2ad41-135">There's minimal downtime (less than a second, if any at all) for users when their team is switched from StaffHub to Shifts in Teams.</span></span> <span data-ttu-id="2ad41-136">Os usuários podem continuar a usar o StaffHub até que a mudança para o Microsoft Teams seja concluída.</span><span class="sxs-lookup"><span data-stu-id="2ad41-136">Users can continue using StaffHub until the move to Teams is completed.</span></span> <span data-ttu-id="2ad41-137">Quando a mudança for concluída, os membros da equipe verão uma mensagem para informar que precisam começar a usar os turnos no Teams para acessar o cronograma da equipe.</span><span class="sxs-lookup"><span data-stu-id="2ad41-137">When the move is completed, team members will see a message to let them know that they need to start using Shifts in Teams to access their team schedule.</span></span> <span data-ttu-id="2ad41-138">Veja um exemplo da mensagem que os usuários verão no StaffHub depois que a equipe do StaffHub for movida para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2ad41-138">Here's an example of the message that users see in StaffHub after the StaffHub team is moved to Teams.</span></span>

<span data-ttu-id="2ad41-139">![Exemplo da mensagem exibida pelos usuários.] (../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Exemplo da mensagem que os usuários veem no StaffHub após a equipe do StaffHub ser movida para") o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2ad41-139">![Example of the message that users see.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Example of the message that users see in StaffHub after the StaffHub team is moved to Teams")</span></span>

## <a name="prepare"></a><span data-ttu-id="2ad41-140">Pare</span><span class="sxs-lookup"><span data-stu-id="2ad41-140">Prepare</span></span>

<span data-ttu-id="2ad41-141">Veja como se preparar para a mudança para o Teams.</span><span class="sxs-lookup"><span data-stu-id="2ad41-141">Here's how to prepare for the move to Teams.</span></span>

### <a name="assign-teams-licenses"></a><span data-ttu-id="2ad41-142">Atribuir licenças do Teams</span><span class="sxs-lookup"><span data-stu-id="2ad41-142">Assign Teams licenses</span></span>

<span data-ttu-id="2ad41-143">Cada usuário deve ter uma licença ativa do Microsoft 365 ou do Office 365 de [um plano elegível](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) e deve receber uma licença do teams.</span><span class="sxs-lookup"><span data-stu-id="2ad41-143">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan ](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="2ad41-144">Atribuir uma licença do teams aos usuários permite que eles acessem o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2ad41-144">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="2ad41-145">Você gerencia as licenças do teams no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2ad41-145">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="2ad41-146">Para saber mais, consulte [gerenciar o acesso do usuário ao Teams](../../user-access.md).</span><span class="sxs-lookup"><span data-stu-id="2ad41-146">To learn more, see [Manage user access to Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2ad41-147">Se a sua organização usa o Skype for Business e você não está pronto para mover todos os usuários para o Microsoft Teams, você pode habilitar o Microsoft Teams para os seus primeiros trabalhadores que podem executar o Microsoft Teams junto ao Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="2ad41-147">If your organization uses Skype for Business and you’re not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="2ad41-148">Nesse modo de coexistência, chamado de *ilhas*, cada aplicativo cliente Opera como uma solução separada.</span><span class="sxs-lookup"><span data-stu-id="2ad41-148">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="2ad41-149">Para saber mais, consulte [entender o Microsoft Teams e a coexistência e interoperabilidade do Skype for Business](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="2ad41-149">To learn more, see [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a><span data-ttu-id="2ad41-150">Provisionar contas para usuários do StaffHub que não têm uma identidade no Azure AD</span><span class="sxs-lookup"><span data-stu-id="2ad41-150">Provision accounts for StaffHub users who don't have an identity in Azure AD</span></span>

<span data-ttu-id="2ad41-151">Cada gerente e membro da equipe devem ter uma identidade no Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="2ad41-151">Each manager and team member must have an identity in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="2ad41-152">Se um usuário ainda não tiver uma identidade no Azure AD, Provisione uma conta para elas.</span><span class="sxs-lookup"><span data-stu-id="2ad41-152">If a user doesn't already have an identity in Azure AD, provision an account for them.</span></span> <span data-ttu-id="2ad41-153">Veja como.</span><span class="sxs-lookup"><span data-stu-id="2ad41-153">Here's how.</span></span>

- <span data-ttu-id="2ad41-154">StaffHub os proprietários e gerentes de equipe podem converter uma conta fictícia ou inativa e vinculá-la a uma conta provisionada no StaffHub alterando o endereço de email do usuário para um UPN válido na página de configurações da equipe do StaffHub.</span><span class="sxs-lookup"><span data-stu-id="2ad41-154">StaffHub team owners and managers can convert a dummy or inactive account and link it to a provisioned account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="2ad41-155">Os administradores podem executar os cmdlets [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) e [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) para remover uma conta não provisionada de uma equipe do StaffHub e adicionar a conta novamente usando o UPN.</span><span class="sxs-lookup"><span data-stu-id="2ad41-155">Admins can run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) and [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) cmdlets to remove a non-provisioned account from a StaffHub team and add the account back by using the UPN.</span></span>

### <a name="install-the-staffhub-powershell-module"></a><span data-ttu-id="2ad41-156">Instalar o módulo PowerShell do StaffHub</span><span class="sxs-lookup"><span data-stu-id="2ad41-156">Install the StaffHub PowerShell module</span></span>

<span data-ttu-id="2ad41-157">Se ainda não fez isso, [Instale o módulo StaffHub PowerShell](install-the-staffhub-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="2ad41-157">If you haven't already, [install the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span>

<span data-ttu-id="2ad41-158">Quando você move uma equipe do StaffHub, a solicitação move verifica se há pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="2ad41-158">When you move a StaffHub team, the move request checks for prerequisites.</span></span> <span data-ttu-id="2ad41-159">Veja os motivos pelos quais uma solicitação de mudança pode falhar:</span><span class="sxs-lookup"><span data-stu-id="2ad41-159">Here's reasons why a move request may fail:</span></span>

- <span data-ttu-id="2ad41-160">O usuário conectado não é um administrador global</span><span class="sxs-lookup"><span data-stu-id="2ad41-160">The signed-in user is not a global admin</span></span>
- <span data-ttu-id="2ad41-161">O Microsoft Teams está desabilitado para todos os usuários no locatário</span><span class="sxs-lookup"><span data-stu-id="2ad41-161">Teams is disabled for all users in the tenant</span></span>
- <span data-ttu-id="2ad41-162">A criação de grupos do Office 365 está desabilitada no locatário</span><span class="sxs-lookup"><span data-stu-id="2ad41-162">Office 365 Groups creation is disabled in the tenant</span></span>
- <span data-ttu-id="2ad41-163">O StaffHub TeamID não é válido ou não tem membros</span><span class="sxs-lookup"><span data-stu-id="2ad41-163">The StaffHub teamId is not valid or has no members</span></span>
- <span data-ttu-id="2ad41-164">A equipe do StaffHub inclui membros que não estão vinculados a uma conta do Azure AD</span><span class="sxs-lookup"><span data-stu-id="2ad41-164">The StaffHub team includes members that aren't linked to an Azure AD account</span></span>  

## <a name="run-a-pilot"></a><span data-ttu-id="2ad41-165">Executar um piloto</span><span class="sxs-lookup"><span data-stu-id="2ad41-165">Run a pilot</span></span>

<span data-ttu-id="2ad41-166">Recomendamos que você comece movendo duas ou três equipes StaffHub para um grupo seleto de pioneiros.</span><span class="sxs-lookup"><span data-stu-id="2ad41-166">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="2ad41-167">A execução de um piloto ajuda você a refinar seu plano de transição e garantir que você esteja pronto para mover todas as equipes do StaffHub da sua organização para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2ad41-167">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="2ad41-168">Ele também identifica campeões que podem ajudar a impulsionar a adoção em toda a sua organização.</span><span class="sxs-lookup"><span data-stu-id="2ad41-168">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="2ad41-169">Se você for uma pequena empresa que não precisa de uma abordagem em fases, as etapas nesta seção podem ser tudo o que você precisa fazer para fazer a mudança do StaffHub para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2ad41-169">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="2ad41-170">Identificar equipes piloto</span><span class="sxs-lookup"><span data-stu-id="2ad41-170">Identify pilot teams</span></span>

<span data-ttu-id="2ad41-171">Tenha acesso à identificação de duas ou três equipes piloto.</span><span class="sxs-lookup"><span data-stu-id="2ad41-171">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="2ad41-172">Todos os membros da equipe devem confirmar o uso de turnos no Teams para gerenciar seus cronogramas e se comunicar e colaborar uns com os outros.</span><span class="sxs-lookup"><span data-stu-id="2ad41-172">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="2ad41-173">Identificar especialistas da equipe</span><span class="sxs-lookup"><span data-stu-id="2ad41-173">Identify team champions</span></span>

<span data-ttu-id="2ad41-174">Identifique especialistas em nossas equipes piloto e as solicite para ajudar a evangelizar turnos.</span><span class="sxs-lookup"><span data-stu-id="2ad41-174">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="2ad41-175">Os representantes da equipe são apaixonados pelo que fazem, compartilhando suas próprias informações para oferecer suporte e orientação aos membros da equipe.</span><span class="sxs-lookup"><span data-stu-id="2ad41-175">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="2ad41-176">Os campeões da equipe podem ser proprietários ou gerentes da equipe.</span><span class="sxs-lookup"><span data-stu-id="2ad41-176">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="2ad41-177">Os campeões de equipe devem garantir que os membros da equipe sejam configurados dedicando-se tempo para que todos [obtenham clientes](../../get-clients.md)do Teams, entrem no Teams e confiram suas agendas em turnos e comecem a conversar uns com os outros.</span><span class="sxs-lookup"><span data-stu-id="2ad41-177">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="2ad41-178">Os usuários que já estão familiarizados com o StaffHub estarão em funcionamento rapidamente em turnos.</span><span class="sxs-lookup"><span data-stu-id="2ad41-178">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="2ad41-179">Você também pode apontá-los para a [ajuda](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) de turnos para obter ajuda adicional.</span><span class="sxs-lookup"><span data-stu-id="2ad41-179">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team-coming-soon"></a><span data-ttu-id="2ad41-180">Mover uma equipe do StaffHub (disponível em breve)</span><span class="sxs-lookup"><span data-stu-id="2ad41-180">Move a StaffHub team (coming soon)</span></span>

<span data-ttu-id="2ad41-181">Use estas etapas para mover uma equipe do StaffHub de cada vez.</span><span class="sxs-lookup"><span data-stu-id="2ad41-181">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="2ad41-182">Recomendamos essa abordagem para suas equipes piloto.</span><span class="sxs-lookup"><span data-stu-id="2ad41-182">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="2ad41-183">Mais tarde, quando você estiver pronto para mover todas as equipes do StaffHub da sua organização, consulte [mover suas equipes do StaffHub](#move-your-staffhub-teams-coming-soon) para ver as etapas sobre como mover várias equipes de cada vez.</span><span class="sxs-lookup"><span data-stu-id="2ad41-183">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams-coming-soon) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="2ad41-184">Execute o seguinte para mover uma equipe do StaffHub.</span><span class="sxs-lookup"><span data-stu-id="2ad41-184">Run the following to move a StaffHub team.</span></span>

```
Move-StaffHubTeam -TeamId <String>

Sample:

Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

<span data-ttu-id="2ad41-185">Veja um exemplo da resposta que você obtém quando envia uma solicitação para mover uma equipe do StaffHub para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2ad41-185">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

<span data-ttu-id="2ad41-186">Para verificar o status de uma solicitação de movimentação, execute o seguinte.</span><span class="sxs-lookup"><span data-stu-id="2ad41-186">To check the status of a move request, run the following.</span></span>

```
Get-TeamMigrationJobStatus <String>

Sample:
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"

```

<span data-ttu-id="2ad41-187">Veja um exemplo da resposta que você obtém quando uma mudança está em andamento.</span><span class="sxs-lookup"><span data-stu-id="2ad41-187">Here's an example of the response you get when a move is in progress.</span></span>

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

## <a name="make-the-transition-from-staffhub-to-teams"></a><span data-ttu-id="2ad41-188">Fazer a transição do StaffHub para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2ad41-188">Make the transition from StaffHub to Teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="2ad41-189">Aumentar a conscientização</span><span class="sxs-lookup"><span data-stu-id="2ad41-189">Raise awareness</span></span>

<span data-ttu-id="2ad41-190">Quando você estiver pronto para ir além de suas equipes piloto e mover as equipes do StaffHub da sua organização para o Microsoft Teams, é importante primeiro comunicar a alteração em toda a sua organização.</span><span class="sxs-lookup"><span data-stu-id="2ad41-190">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="2ad41-191">Espalhe a palavra sobre turnos e a transição para o Microsoft Teams para aumentar a conscientização, gerar entusiasmo e impulsionar a adoção.</span><span class="sxs-lookup"><span data-stu-id="2ad41-191">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams-coming-soon"></a><span data-ttu-id="2ad41-192">Mover suas equipes do StaffHub (em breve)</span><span class="sxs-lookup"><span data-stu-id="2ad41-192">Move your StaffHub teams (coming soon)</span></span>

<span data-ttu-id="2ad41-193">Use estas etapas para mover as equipes do StaffHub em massa.</span><span class="sxs-lookup"><span data-stu-id="2ad41-193">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="2ad41-194">Você pode optar por mover todas as equipes do StaffHub da sua organização ou mover equipes específicas do StaffHub.</span><span class="sxs-lookup"><span data-stu-id="2ad41-194">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="2ad41-195">Se você quiser mover um StaffHub Teams, um por vez, consulte [mover uma equipe do StaffHub](#move-a-staffhub-team-coming-soon).</span><span class="sxs-lookup"><span data-stu-id="2ad41-195">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team-coming-soon).</span></span>

#### <a name="move-all-staffhub-teams-coming-soon"></a><span data-ttu-id="2ad41-196">Mover todas as equipes do StaffHub (em breve)</span><span class="sxs-lookup"><span data-stu-id="2ad41-196">Move all StaffHub teams (coming soon)</span></span>

<span data-ttu-id="2ad41-197">Execute o seguinte para obter uma lista de todas as equipes do StaffHub em sua organização.</span><span class="sxs-lookup"><span data-stu-id="2ad41-197">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="2ad41-198">Em seguida, execute o seguinte para mover todas as equipes.</span><span class="sxs-lookup"><span data-stu-id="2ad41-198">Then, run the following to move all teams.</span></span>

```
$StaffHubTeams | foreach {Move-StaffHubTeam -TeamId {$_.Id}}
```

<span data-ttu-id="2ad41-199">Veja um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="2ad41-199">Here's an example of the response.</span></span>

<span data-ttu-id="2ad41-200">Para todas as equipes que já foram movidas para o Microsoft Teams ou já existirem no Teams, o jobId será "nulo" porque um trabalho não precisará ser enviado para mover a equipe.</span><span class="sxs-lookup"><span data-stu-id="2ad41-200">For any team that was already moved to Teams or already exists in Teams, the jobId will be "null" as a job doesn't need to be submitted to move that team.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams-coming-soon"></a><span data-ttu-id="2ad41-201">Mover equipes específicas do StaffHub (disponível em breve)</span><span class="sxs-lookup"><span data-stu-id="2ad41-201">Move specific StaffHub teams (coming soon)</span></span>

<span data-ttu-id="2ad41-202">Execute o seguinte para obter uma lista de todas as IDs de equipe do StaffHub em sua organização.</span><span class="sxs-lookup"><span data-stu-id="2ad41-202">Run the following to get a list of all StaffHub team Ids in your organization.</span></span>

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="2ad41-203">Nos resultados retornados pelo `Get-StaffHubteamsForTenant` cmdlet executado anteriormente, selecione as IDs de equipe que você deseja mover e, em seguida, adicione-as a um arquivo CSV (valores separados por vírgula).</span><span class="sxs-lookup"><span data-stu-id="2ad41-203">In the results returned by the `Get-StaffHubteamsForTenant` cmdlet you ran earlier, select the Team Ids you want to move, and then add them to a comma-separated values (CSV) file.</span></span>

<span data-ttu-id="2ad41-204">Aqui está um exemplo de como o arquivo CSV deve ser formatado.</span><span class="sxs-lookup"><span data-stu-id="2ad41-204">Here's an example of how the CSV file should be formatted.</span></span>

|<span data-ttu-id="2ad41-205">%</span><span class="sxs-lookup"><span data-stu-id="2ad41-205">Id</span></span>  |
|---------|
|<span data-ttu-id="2ad41-206">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="2ad41-206">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="2ad41-207">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="2ad41-207">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="2ad41-208">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="2ad41-208">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="2ad41-209">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="2ad41-209">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="2ad41-210">Depois de criar o arquivo CSV, execute o seguinte para mover as equipes que você especificou no arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="2ad41-210">After you create the CSV file, run the following to move the teams you specified in the CSV file.</span></span>

```
Import-Csv .\teams.txt | foreach {Move-StaffHubTeam -TeamdId {$_.Id}}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams-coming-soon"></a><span data-ttu-id="2ad41-211">Confirme se suas equipes do StaffHub mudaram para o Microsoft Teams (em breve)</span><span class="sxs-lookup"><span data-stu-id="2ad41-211">Confirm that your StaffHub teams have moved to Teams (coming soon)</span></span>

<span data-ttu-id="2ad41-212">Execute o seguinte para obter uma lista de todas as equipes em turnos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="2ad41-212">Run the following to get a list of all teams in Shifts in your organization.</span></span> 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

## <a name="monitor-teams-usage"></a><span data-ttu-id="2ad41-213">Monitorar o uso do teams</span><span class="sxs-lookup"><span data-stu-id="2ad41-213">Monitor Teams usage</span></span>

<span data-ttu-id="2ad41-214">Os relatórios de uso podem ajudá-lo a entender melhor os padrões de uso e oferecer ideias sobre onde priorizar os esforços de treinamento e comunicação em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="2ad41-214">Usage reports can help you better understand usage patterns and give you insights on where to prioritize training and communication efforts across your organization.</span></span> <span data-ttu-id="2ad41-215">Como turnos é um aplicativo no Teams, você pode exibir o uso por meio de relatórios do teams.</span><span class="sxs-lookup"><span data-stu-id="2ad41-215">Because Shifts is an app in Teams, you can view usage through Teams reports.</span></span> <span data-ttu-id="2ad41-216">Para obter mais informações, consulte relatórios [do Microsoft Teams no centro de administração do Microsoft Teams](../../teams-analytics-and-reports/teams-reporting-reference.md) e [relatórios de atividade do Microsoft Teams no centro de administração do Microsoft 365](../../teams-activity-reports.md).</span><span class="sxs-lookup"><span data-stu-id="2ad41-216">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2ad41-217">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="2ad41-217">Related topics</span></span>
- [<span data-ttu-id="2ad41-218">O Microsoft StaffHub será desativado</span><span class="sxs-lookup"><span data-stu-id="2ad41-218">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="2ad41-219">Gerencie o aplicativo Turnos para sua organização no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2ad41-219">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="2ad41-220">Referência do PowerShell do StaffHub</span><span class="sxs-lookup"><span data-stu-id="2ad41-220">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
