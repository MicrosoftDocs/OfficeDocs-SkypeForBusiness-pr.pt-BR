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
description: Aprenda a mover suas equipes da Microsoft StaffHub e agendar dados às mudanças na Teams da Microsoft.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8ca4249c88ce5793cd04eb2e2cc1ed3035915975
ms.sourcegitcommit: 790ca37e2b12e4c8adcc526b1695017161749f51
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/01/2019
ms.locfileid: "33526852"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="1388c-103">Mover suas equipes da Microsoft StaffHub para mudanças na Teams da Microsoft</span><span class="sxs-lookup"><span data-stu-id="1388c-103">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1388c-104">A partir de 1 de outubro de 2019, Microsoft StaffHub será desativada.</span><span class="sxs-lookup"><span data-stu-id="1388c-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="1388c-105">Estamos compilando recursos StaffHub em Teams da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1388c-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="1388c-106">Hoje, equipes inclui o aplicativo desloca para o gerenciamento de agenda e recursos adicionais serão distribuir ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="1388c-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="1388c-107">StaffHub irá parar de funcionar para todos os usuários em 1 de outubro de 2019.</span><span class="sxs-lookup"><span data-stu-id="1388c-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="1388c-108">Qualquer pessoa que tenta abrir StaffHub será mostrada uma mensagem direcionando-os para baixar as equipes.</span><span class="sxs-lookup"><span data-stu-id="1388c-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="1388c-109">Para saber mais, consulte [Microsoft StaffHub para ser retirado](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="1388c-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

> <span data-ttu-id="1388c-110">O recurso discutido neste artigo ainda não foi liberado.</span><span class="sxs-lookup"><span data-stu-id="1388c-110">The capability discussed in this article hasn't yet been released.</span></span> <span data-ttu-id="1388c-111">Ela será foi anunciada e estarão disponíveis em breve, em direção à parte central de maio de 2019.</span><span class="sxs-lookup"><span data-stu-id="1388c-111">It's been announced, and is coming soon, towards the middle of May 2019.</span></span> <span data-ttu-id="1388c-112">Se você for um administrador, você pode descobrir quando isso estarão disponível no Centro de mensagens (no [Centro de administração do Microsoft 365](https://portal.office.com/adminportal/home)).</span><span class="sxs-lookup"><span data-stu-id="1388c-112">If you're an admin, you can find out when this will be available in the Message Center (in the [Microsoft 365 admin center](https://portal.office.com/adminportal/home)).</span></span>

<span data-ttu-id="1388c-113">O aplicativo desloca em equipes fornece uma abordagem simples para gerenciar agendamentos e o fluxo constante de trocas de shift e cancelamentos que ocorrem em uma base diária.</span><span class="sxs-lookup"><span data-stu-id="1388c-113">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="1388c-114">Os membros da equipe podem acessar sua agenda e shift informações diretamente no aplicativo e nos seus dispositivos para definir suas preferências, gerenciar suas próprias agendas e tempo de solicitação.</span><span class="sxs-lookup"><span data-stu-id="1388c-114">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="1388c-115">Este artigo explora como mover as equipes de StaffHub da sua organização e agendar dados às mudanças na equipes.</span><span class="sxs-lookup"><span data-stu-id="1388c-115">This article walks you through how to move your organization’s StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="1388c-116">Se você estiver em uma pequena empresa com uma ou duas equipes de StaffHub ou uma empresa de grande porte com centenas de equipes StaffHub, aqui você encontrará as orientações de admin, que você precisa para ajudar a tornar sua transição para equipes bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="1388c-116">Whether you’re a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you’ll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="1388c-117">Você deve ser um administrador global para executar as etapas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="1388c-117">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="1388c-118">Se você ainda não tiver feito isso, dê uma olhada através de [aposentadoria StaffHub perguntas Frequentes](microsoft-staffhub-to-be-retired.md) para obter respostas às dúvidas que você pode ter.</span><span class="sxs-lookup"><span data-stu-id="1388c-118">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span> 

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="1388c-119">O que você precisa saber sobre a movimentação para equipes</span><span class="sxs-lookup"><span data-stu-id="1388c-119">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="1388c-120">Quando se mover para equipes</span><span class="sxs-lookup"><span data-stu-id="1388c-120">When to move to Teams</span></span>

<span data-ttu-id="1388c-121">A partir de 1 de outubro de 2019, StaffHub será desativada.</span><span class="sxs-lookup"><span data-stu-id="1388c-121">Effective October 1, 2019, StaffHub will be retired.</span></span> <span data-ttu-id="1388c-122">Recomendamos que você inicie com equipes hoje e começar a fazer a transição de equipes e os usuários de StaffHub da sua organização.</span><span class="sxs-lookup"><span data-stu-id="1388c-122">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="1388c-123">Com o gerenciamento de agenda sendo o recurso comumente usadas no StaffHub, é recomendável que você usa o aplicativo de mudanças em equipes avançando.</span><span class="sxs-lookup"><span data-stu-id="1388c-123">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="1388c-124">O que é movido para equipes</span><span class="sxs-lookup"><span data-stu-id="1388c-124">What is moved to Teams</span></span>

<span data-ttu-id="1388c-125">Detalhes do usuário, informações de agenda e bate-papo e o arquivo de dados são uma transição às equipes.</span><span class="sxs-lookup"><span data-stu-id="1388c-125">User details, schedule information, and chat and file data are transitioned to Teams.</span></span> <span data-ttu-id="1388c-126">Isso inclui a associação da equipe, agendamentos de equipe e bate-papos e arquivos dos últimos 90 dias.</span><span class="sxs-lookup"><span data-stu-id="1388c-126">This includes team membership, team schedules, and chats and files from the last 90 days.</span></span>

<span data-ttu-id="1388c-127">Cada equipe StaffHub necessita de um grupo de 365 correspondente do Office.</span><span class="sxs-lookup"><span data-stu-id="1388c-127">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="1388c-128">Se uma equipe StaffHub não tiver um grupo do Office 365 associado a ela, um é criado automaticamente para você ofereça suporte a transição.</span><span class="sxs-lookup"><span data-stu-id="1388c-128">If a StaffHub team doesn't have an Office 365 Group associated with it, one is automatically created for you to support the transition.</span></span> <span data-ttu-id="1388c-129">A diferença na equipe e nomeação de grupo entre equipes e StaffHub, você poderá ver um nome diferente de equipe em equipes.</span><span class="sxs-lookup"><span data-stu-id="1388c-129">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span>

<span data-ttu-id="1388c-130">Como fazer a transição de equipes de StaffHub às equipes, os usuários não terá mais acesso a suas próprias agendas em StaffHub e são redirecionados para mudanças na equipes.</span><span class="sxs-lookup"><span data-stu-id="1388c-130">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="1388c-131">Recomendamos que você se comunica essa alteração em toda a organização para minimizar a interrupção e incentivar os usuários a adotar e explore equipes.</span><span class="sxs-lookup"><span data-stu-id="1388c-131">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span>

## <a name="prepare"></a><span data-ttu-id="1388c-132">Preparar</span><span class="sxs-lookup"><span data-stu-id="1388c-132">Prepare</span></span>

<span data-ttu-id="1388c-133">Aqui está como se preparar para a mudança para equipes.</span><span class="sxs-lookup"><span data-stu-id="1388c-133">Here's how to prepare for the move to Teams.</span></span>

### <a name="assign-teams-licenses"></a><span data-ttu-id="1388c-134">Atribuir licenças do Teams</span><span class="sxs-lookup"><span data-stu-id="1388c-134">Assign Teams licenses</span></span>

<span data-ttu-id="1388c-135">Cada usuário deve ter uma licença do Microsoft 365 ou do Office 365 ativa de [um plano de elegível](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) e deve ter uma licença de equipes.</span><span class="sxs-lookup"><span data-stu-id="1388c-135">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan ](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="1388c-136">Atribuir uma licença de equipes a usuários lhes acesso às equipes.</span><span class="sxs-lookup"><span data-stu-id="1388c-136">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="1388c-137">Você gerenciar licenças de equipes no Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1388c-137">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="1388c-138">Para saber mais, consulte [Manage user access às equipes](../../user-access.md).</span><span class="sxs-lookup"><span data-stu-id="1388c-138">To learn more, see [Manage user access to Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1388c-139">Se sua organização usa Skype para negócios e você não estiver pronto para migrar todos os seus usuários para equipes, você poderá habilitar equipes para seus funcionários de Firstline que poderá executar equipes junto com Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="1388c-139">If your organization uses Skype for Business and you’re not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="1388c-140">Neste modo de coexistência, chamado *Ilhas*, cada aplicativo cliente opera como uma solução separada.</span><span class="sxs-lookup"><span data-stu-id="1388c-140">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="1388c-141">Para saber mais, consulte [entender equipes e Skype para interoperabilidade e coexistência de negócios](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="1388c-141">To learn more, see [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a><span data-ttu-id="1388c-142">Provisionar contas para usuários StaffHub que não têm uma identidade no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1388c-142">Provision accounts for StaffHub users who don't have an identity in Azure AD</span></span>

<span data-ttu-id="1388c-143">Cada gerente e um membro da equipe precisam ter uma identidade no Windows Azure Active Directory (AD Azure).</span><span class="sxs-lookup"><span data-stu-id="1388c-143">Each manager and team member must have an identity in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="1388c-144">Se um usuário já não tenha uma identidade no Azure AD, provisione uma conta para eles.</span><span class="sxs-lookup"><span data-stu-id="1388c-144">If a user doesn't already have an identity in Azure AD, provision an account for them.</span></span> <span data-ttu-id="1388c-145">Veja como.</span><span class="sxs-lookup"><span data-stu-id="1388c-145">Here's how.</span></span>

- <span data-ttu-id="1388c-146">Os gerentes e os proprietários de equipe StaffHub podem converter uma conta fictícia ou inativa e vinculá-lo a uma conta provisionada no StaffHub, alterando o endereço de email do usuário para um UPN válido, na página de configurações da equipe do StaffHub.</span><span class="sxs-lookup"><span data-stu-id="1388c-146">StaffHub team owners and managers can convert a dummy or inactive account and link it to a provisioned account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="1388c-147">Administradores podem executar o [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) e cmdlets de [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) para remover uma conta não provisionado de uma equipe de StaffHub e adicione a conta de volta usando o UPN.</span><span class="sxs-lookup"><span data-stu-id="1388c-147">Admins can run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) and [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) cmdlets to remove a non-provisioned account from a StaffHub team and add the account back by using the UPN.</span></span>

### <a name="install-the-staffhub-powershell-module"></a><span data-ttu-id="1388c-148">Instalar o módulo PowerShell do StaffHub</span><span class="sxs-lookup"><span data-stu-id="1388c-148">Install the StaffHub PowerShell module</span></span>

<span data-ttu-id="1388c-149">Se você ainda não estiver, [Instale o módulo de StaffHub PowerShell](install-the-staffhub-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="1388c-149">If you haven't already, [install the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span>

<span data-ttu-id="1388c-150">Quando você move uma equipe StaffHub, a solicitação de movimentação verifica os pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="1388c-150">When you move a StaffHub team, the move request checks for prerequisites.</span></span> <span data-ttu-id="1388c-151">Eis motivos por que uma solicitação de movimentação pode falhar:</span><span class="sxs-lookup"><span data-stu-id="1388c-151">Here's reasons why a move request may fail:</span></span>

- <span data-ttu-id="1388c-152">O usuário conectado não é um administrador global</span><span class="sxs-lookup"><span data-stu-id="1388c-152">The signed-in user is not a global admin</span></span>
- <span data-ttu-id="1388c-153">As equipes está desabilitada para todos os usuários no locatário</span><span class="sxs-lookup"><span data-stu-id="1388c-153">Teams is disabled for all users in the tenant</span></span>
- <span data-ttu-id="1388c-154">Criação de grupos do Office 365 está desabilitada no locatário</span><span class="sxs-lookup"><span data-stu-id="1388c-154">Office 365 Groups creation is disabled in the tenant</span></span>
- <span data-ttu-id="1388c-155">O teamId StaffHub não é válida ou não possui membros</span><span class="sxs-lookup"><span data-stu-id="1388c-155">The StaffHub teamId is not valid or has no members</span></span>
- <span data-ttu-id="1388c-156">A equipe de StaffHub inclui membros que não estão vinculados a uma conta do Windows Azure AD</span><span class="sxs-lookup"><span data-stu-id="1388c-156">The StaffHub team includes members that aren't linked to an Azure AD account</span></span>  

## <a name="run-a-pilot"></a><span data-ttu-id="1388c-157">Executar um piloto</span><span class="sxs-lookup"><span data-stu-id="1388c-157">Run a pilot</span></span>

<span data-ttu-id="1388c-158">Recomendamos que você inicie movendo dois ou três equipes de StaffHub para um grupo seleto de usuários iniciais.</span><span class="sxs-lookup"><span data-stu-id="1388c-158">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="1388c-159">Executar um piloto ajuda refinar seu plano de transição e certifique-se de que você está pronto para mover as equipes de StaffHub todos da sua organização para equipes.</span><span class="sxs-lookup"><span data-stu-id="1388c-159">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="1388c-160">Ele também identifica campeões que podem ajudar incentivar a adoção em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="1388c-160">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="1388c-161">Se você tem uma pequena empresa que não precisa de uma abordagem em fases, as etapas desta seção podem ser tudo o que você precisa para fazer a opção de StaffHub com equipes.</span><span class="sxs-lookup"><span data-stu-id="1388c-161">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="1388c-162">Identificar as equipes piloto</span><span class="sxs-lookup"><span data-stu-id="1388c-162">Identify pilot teams</span></span>

<span data-ttu-id="1388c-163">Chegar aos identificar dois ou três equipes piloto.</span><span class="sxs-lookup"><span data-stu-id="1388c-163">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="1388c-164">Todos os membros da equipe devem confirmar usando desloca nas equipes para gerenciar suas próprias agendas e se comunicar e colaborar entre si.</span><span class="sxs-lookup"><span data-stu-id="1388c-164">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="1388c-165">Identificar os campeões de equipe</span><span class="sxs-lookup"><span data-stu-id="1388c-165">Identify team champions</span></span>

<span data-ttu-id="1388c-166">Identificar campeões entre equipes piloto e inscrevê-los para ajudar a Pregue desloca.</span><span class="sxs-lookup"><span data-stu-id="1388c-166">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="1388c-167">Campeões de equipe são entusiasmados pela sobre o que isso acontece, compartilhamento de seus próprios lições para oferecer suporte e orientações para membros da equipe.</span><span class="sxs-lookup"><span data-stu-id="1388c-167">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="1388c-168">Campeões da equipe podem ser proprietários de equipe ou gerentes.</span><span class="sxs-lookup"><span data-stu-id="1388c-168">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="1388c-169">Verifique se campeões equipe membros da equipe são configurada pela dedicar tempo todos para [obter os clientes de equipes](../../get-clients.md), entrar com equipes e check-out de suas próprias agendas em desloca e iniciar o bate-papo uns com os outros.</span><span class="sxs-lookup"><span data-stu-id="1388c-169">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="1388c-170">Usuários que já estão familiarizados com StaffHub estará em funcionamento rapidamente no desloca.</span><span class="sxs-lookup"><span data-stu-id="1388c-170">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="1388c-171">Você também pode apontá-los para [Ajudar a desloca](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) para obter ajuda adicional.</span><span class="sxs-lookup"><span data-stu-id="1388c-171">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team-coming-soon"></a><span data-ttu-id="1388c-172">Mover uma equipe de StaffHub (em breve)</span><span class="sxs-lookup"><span data-stu-id="1388c-172">Move a StaffHub team (coming soon)</span></span>

<span data-ttu-id="1388c-173">Use estas etapas para mover uma equipe de StaffHub por vez.</span><span class="sxs-lookup"><span data-stu-id="1388c-173">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="1388c-174">Recomendamos essa abordagem para suas equipes piloto.</span><span class="sxs-lookup"><span data-stu-id="1388c-174">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="1388c-175">Posteriormente, quando estiver pronto para migrar as equipes de StaffHub todos da sua organização, consulte [mover suas equipes StaffHub](#move-your-staffhub-teams-coming-soon) para obter etapas sobre como mover várias equipes de cada vez.</span><span class="sxs-lookup"><span data-stu-id="1388c-175">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams-coming-soon) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="1388c-176">Execute o seguinte procedimento para mover uma equipe de StaffHub.</span><span class="sxs-lookup"><span data-stu-id="1388c-176">Run the following to move a StaffHub team.</span></span>

```
Move-StaffHubTeam -TeamId <String>

Sample:

Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

<span data-ttu-id="1388c-177">Aqui está um exemplo da resposta obtido quando você envia uma solicitação para mover uma equipe StaffHub para equipes.</span><span class="sxs-lookup"><span data-stu-id="1388c-177">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

<span data-ttu-id="1388c-178">Para verificar o status de uma solicitação de movimentação, execute o seguinte.</span><span class="sxs-lookup"><span data-stu-id="1388c-178">To check the status of a move request, run the following.</span></span>

```
Get-TeamMigrationJobStatus <String>

Sample:
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"

```

<span data-ttu-id="1388c-179">Aqui está um exemplo da resposta obtido quando uma movimentação está em andamento.</span><span class="sxs-lookup"><span data-stu-id="1388c-179">Here's an example of the response you get when a move is in progress.</span></span>

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

## <a name="make-the-transition-from-staffhub-to-teams"></a><span data-ttu-id="1388c-180">Fazer a transição de StaffHub às equipes</span><span class="sxs-lookup"><span data-stu-id="1388c-180">Make the transition from StaffHub to Teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="1388c-181">Aumente a conscientização</span><span class="sxs-lookup"><span data-stu-id="1388c-181">Raise awareness</span></span>

<span data-ttu-id="1388c-182">Quando você está pronto para ir além suas equipes piloto e mover as equipes de StaffHub da sua organização para equipes, é importante se comunicar pela primeira vez a alteração em sua organização.</span><span class="sxs-lookup"><span data-stu-id="1388c-182">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="1388c-183">Difundir o word sobre mudanças e a transição para equipes atenção, estimular o interesse e direcionar a adoção.</span><span class="sxs-lookup"><span data-stu-id="1388c-183">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams-coming-soon"></a><span data-ttu-id="1388c-184">Mover suas equipes StaffHub (em breve)</span><span class="sxs-lookup"><span data-stu-id="1388c-184">Move your StaffHub teams (coming soon)</span></span>

<span data-ttu-id="1388c-185">Use estas etapas para mover StaffHub equipes em massa.</span><span class="sxs-lookup"><span data-stu-id="1388c-185">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="1388c-186">Você pode optar por mover as equipes de StaffHub todos da sua organização ou mover equipes de StaffHub específicas.</span><span class="sxs-lookup"><span data-stu-id="1388c-186">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="1388c-187">Se você deseja mover que staffhub às equipes um de cada vez, consulte [Mover uma equipe de StaffHub](#move-a-staffhub-team-coming-soon).</span><span class="sxs-lookup"><span data-stu-id="1388c-187">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team-coming-soon).</span></span>

#### <a name="move-all-staffhub-teams-coming-soon"></a><span data-ttu-id="1388c-188">Mover todas as equipes StaffHub (em breve)</span><span class="sxs-lookup"><span data-stu-id="1388c-188">Move all StaffHub teams (coming soon)</span></span>

<span data-ttu-id="1388c-189">Execute o seguinte procedimento para obter uma lista de todas as equipes de StaffHub em sua organização.</span><span class="sxs-lookup"><span data-stu-id="1388c-189">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="1388c-190">Em seguida, execute o seguinte procedimento para mover todas as equipes.</span><span class="sxs-lookup"><span data-stu-id="1388c-190">Then, run the following to move all teams.</span></span>

```
$StaffHubTeams | foreach {Move-StaffHubTeam -TeamId {$_.Id}}
```

<span data-ttu-id="1388c-191">Aqui está um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="1388c-191">Here's an example of the response.</span></span>

<span data-ttu-id="1388c-192">Para qualquer equipe que já foi movido para equipes ou já existe no equipes, o jobId será "nulo" como um trabalho não precisa ser enviados para mover a equipe.</span><span class="sxs-lookup"><span data-stu-id="1388c-192">For any team that was already moved to Teams or already exists in Teams, the jobId will be "null" as a job doesn't need to be submitted to move that team.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams-coming-soon"></a><span data-ttu-id="1388c-193">Mover as equipes de StaffHub específicas (em breve)</span><span class="sxs-lookup"><span data-stu-id="1388c-193">Move specific StaffHub teams (coming soon)</span></span>

<span data-ttu-id="1388c-194">Execute o seguinte procedimento para obter uma lista de equipe todos StaffHub Ids em sua organização.</span><span class="sxs-lookup"><span data-stu-id="1388c-194">Run the following to get a list of all StaffHub team Ids in your organization.</span></span>

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="1388c-195">Nos resultados retornados pelo `Get-StaffHubteamsForTenant` cmdlet executou anteriormente, selecione as Ids de equipe que você deseja mover e, em seguida, adicioná-los para um arquivo de valores separados por vírgula (CSV).</span><span class="sxs-lookup"><span data-stu-id="1388c-195">In the results returned by the `Get-StaffHubteamsForTenant` cmdlet you ran earlier, select the Team Ids you want to move, and then add them to a comma-separated values (CSV) file.</span></span>

<span data-ttu-id="1388c-196">Aqui está um exemplo de como o arquivo CSV deve ser formatado.</span><span class="sxs-lookup"><span data-stu-id="1388c-196">Here's an example of how the CSV file should be formatted.</span></span>

|<span data-ttu-id="1388c-197">ID</span><span class="sxs-lookup"><span data-stu-id="1388c-197">Id</span></span>  |
|---------|
|<span data-ttu-id="1388c-198">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="1388c-198">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="1388c-199">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="1388c-199">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="1388c-200">TEAM_b42d0fa2 - 0fc 9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="1388c-200">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="1388c-201">TEAM_b42d0fa2 - 0fc 9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="1388c-201">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="1388c-202">Após criar o arquivo CSV, execute o seguinte procedimento para mover as equipes que você especificou no arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="1388c-202">After you create the CSV file, run the following to move the teams you specified in the CSV file.</span></span>

```
Import-Csv .\teams.txt | foreach {Move-StaffHubTeam -TeamdId {$_.Id}}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams-coming-soon"></a><span data-ttu-id="1388c-203">Confirme que as equipes StaffHub tem transferido para equipes (em breve)</span><span class="sxs-lookup"><span data-stu-id="1388c-203">Confirm that your StaffHub teams have moved to Teams (coming soon)</span></span>

<span data-ttu-id="1388c-204">Execute o seguinte procedimento para obter uma lista de todas as equipes em desloca em sua organização.</span><span class="sxs-lookup"><span data-stu-id="1388c-204">Run the following to get a list of all teams in Shifts in your organization.</span></span> 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

## <a name="monitor-teams-usage"></a><span data-ttu-id="1388c-205">Monitorar o uso de equipes</span><span class="sxs-lookup"><span data-stu-id="1388c-205">Monitor Teams usage</span></span>

<span data-ttu-id="1388c-206">Relatórios de uso podem ajudá-lo a entender os padrões de uso melhor e a fornecer ideias sobre onde priorizar os esforços de treinamento e comunicação em sua organização.</span><span class="sxs-lookup"><span data-stu-id="1388c-206">Usage reports can help you better understand usage patterns and give you insights on where to prioritize training and communication efforts across your organization.</span></span> <span data-ttu-id="1388c-207">Como desloca é um aplicativo em equipes, você pode visualizar o uso por meio de relatórios de equipes.</span><span class="sxs-lookup"><span data-stu-id="1388c-207">Because Shifts is an app in Teams, you can view usage through Teams reports.</span></span> <span data-ttu-id="1388c-208">Para obter mais informações, consulte [equipes relatórios no Centro de administração do Microsoft equipes](../../teams-analytics-and-reports/teams-reporting-reference.md) e [relatórios de atividade de equipes no Centro de administração do Microsoft 365](../../teams-activity-reports.md).</span><span class="sxs-lookup"><span data-stu-id="1388c-208">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="1388c-209">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="1388c-209">Related topics</span></span>
- [<span data-ttu-id="1388c-210">O Microsoft StaffHub será desativado</span><span class="sxs-lookup"><span data-stu-id="1388c-210">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="1388c-211">Gerencie o aplicativo Turnos para sua organização no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1388c-211">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="1388c-212">Referência StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="1388c-212">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
