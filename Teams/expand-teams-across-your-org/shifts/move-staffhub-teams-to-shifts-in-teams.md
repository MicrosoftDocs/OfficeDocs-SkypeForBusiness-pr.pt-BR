---
title: Mover suas equipes StaffHub para mudanças na Teams da Microsoft
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
ms.openlocfilehash: 2eb6e6616d1164dad462e349a80e7ac36cc5ce1e
ms.sourcegitcommit: 70d3a3b162fdbca1cf2c2713d6bce54c3cbad3bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2019
ms.locfileid: "31026209"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="05b57-103">Mover suas equipes da Microsoft StaffHub para mudanças na Teams da Microsoft</span><span class="sxs-lookup"><span data-stu-id="05b57-103">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="05b57-104">A partir de 1 de outubro de 2019, Microsoft StaffHub será desativada.</span><span class="sxs-lookup"><span data-stu-id="05b57-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="05b57-105">Estamos compilando recursos StaffHub em Teams da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="05b57-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="05b57-106">Hoje, equipes inclui o aplicativo desloca para o gerenciamento de agenda e recursos adicionais serão distribuir ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="05b57-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="05b57-107">StaffHub irá parar de funcionar para todos os usuários em 1 de outubro de 2019.</span><span class="sxs-lookup"><span data-stu-id="05b57-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="05b57-108">Qualquer pessoa que tenta abrir StaffHub será mostrada uma mensagem direcionando-os para baixar as equipes.</span><span class="sxs-lookup"><span data-stu-id="05b57-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="05b57-109">Para saber mais, consulte [Microsoft StaffHub para ser retirado](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="05b57-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span> 

<span data-ttu-id="05b57-110">O aplicativo desloca em equipes fornece uma abordagem simples para gerenciar agendamentos e o fluxo constante de trocas de shift e cancelamentos que ocorrem em uma base diária.</span><span class="sxs-lookup"><span data-stu-id="05b57-110">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="05b57-111">Os membros da equipe podem acessar sua agenda e shift informações diretamente no aplicativo e nos seus dispositivos para definir suas preferências, gerenciar suas próprias agendas e tempo de solicitação.</span><span class="sxs-lookup"><span data-stu-id="05b57-111">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="05b57-112">Este artigo explora como mover as equipes de StaffHub da sua organização e agendar dados às mudanças na equipes.</span><span class="sxs-lookup"><span data-stu-id="05b57-112">This article walks you through how to move your organization’s StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="05b57-113">Se você estiver em uma pequena empresa com uma ou duas equipes de StaffHub ou uma empresa de grande porte com centenas de equipes StaffHub, aqui você encontrará as orientações de admin, que você precisa para ajudar a tornar sua transição para equipes bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="05b57-113">Whether you’re a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you’ll find the admin guidance you need to help make your transition to Teams successful.</span></span> 

<span data-ttu-id="05b57-114">Você deve ser um administrador global para executar as etapas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="05b57-114">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="05b57-115">Se você ainda não tiver feito isso, dê uma olhada através de [aposentadoria StaffHub perguntas Frequentes](microsoft-staffhub-to-be-retired.md) para obter respostas às dúvidas que você pode ter.</span><span class="sxs-lookup"><span data-stu-id="05b57-115">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span> 

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="05b57-116">O que você precisa saber sobre a movimentação para equipes</span><span class="sxs-lookup"><span data-stu-id="05b57-116">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="05b57-117">Quando se mover para equipes</span><span class="sxs-lookup"><span data-stu-id="05b57-117">When to move to Teams</span></span>

<span data-ttu-id="05b57-118">A partir de 1 de outubro de 2019, StaffHub será desativada.</span><span class="sxs-lookup"><span data-stu-id="05b57-118">Effective October 1, 2019, StaffHub will be retired.</span></span> <span data-ttu-id="05b57-119">Recomendamos que você inicie com equipes hoje e começar a fazer a transição de equipes e os usuários de StaffHub da sua organização.</span><span class="sxs-lookup"><span data-stu-id="05b57-119">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="05b57-120">Com o gerenciamento de agenda sendo o recurso comumente usadas no StaffHub, é recomendável que você usa o aplicativo de mudanças em equipes avançando.</span><span class="sxs-lookup"><span data-stu-id="05b57-120">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="05b57-121">O que é movido para equipes</span><span class="sxs-lookup"><span data-stu-id="05b57-121">What is moved to Teams</span></span>

<span data-ttu-id="05b57-122">Detalhes do usuário, informações de agenda e bate-papo e o arquivo de dados são uma transição às equipes.</span><span class="sxs-lookup"><span data-stu-id="05b57-122">User details, schedule information, and chat and file data are transitioned to Teams.</span></span> <span data-ttu-id="05b57-123">Isso inclui a associação da equipe, agendamentos de equipe e bate-papos e arquivos dos últimos 90 dias.</span><span class="sxs-lookup"><span data-stu-id="05b57-123">This includes team membership, team schedules, and chats and files from the last 90 days.</span></span>

<span data-ttu-id="05b57-124">Cada equipe StaffHub necessita de um grupo de 365 correspondente do Office.</span><span class="sxs-lookup"><span data-stu-id="05b57-124">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="05b57-125">Se uma equipe StaffHub não tiver um grupo do Office 365 associado a ela, um é criado automaticamente para você ofereça suporte a transição.</span><span class="sxs-lookup"><span data-stu-id="05b57-125">If a StaffHub team doesn't have an Office 365 Group associated with it, one is automatically created for you to support the transition.</span></span> <span data-ttu-id="05b57-126">A diferença na equipe e nomeação de grupo entre equipes e StaffHub, você poderá ver um nome diferente de equipe em equipes.</span><span class="sxs-lookup"><span data-stu-id="05b57-126">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span>

<span data-ttu-id="05b57-127">Como fazer a transição de equipes de StaffHub às equipes, os usuários não terá mais acesso a suas próprias agendas em StaffHub e são redirecionados para mudanças na equipes.</span><span class="sxs-lookup"><span data-stu-id="05b57-127">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="05b57-128">Recomendamos que você se comunica essa alteração em toda a organização para minimizar a interrupção e incentivar os usuários a adotar e explore equipes.</span><span class="sxs-lookup"><span data-stu-id="05b57-128">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span>

## <a name="prepare"></a><span data-ttu-id="05b57-129">Preparar</span><span class="sxs-lookup"><span data-stu-id="05b57-129">Prepare</span></span>

<span data-ttu-id="05b57-130">Aqui está como se preparar para a mudança para equipes.</span><span class="sxs-lookup"><span data-stu-id="05b57-130">Here's how to prepare for the move to Teams.</span></span>

### <a name="assign-teams-licenses"></a><span data-ttu-id="05b57-131">Atribuir licenças do Teams</span><span class="sxs-lookup"><span data-stu-id="05b57-131">Assign Teams licenses</span></span>

<span data-ttu-id="05b57-132">Cada usuário deve ter uma licença do Microsoft 365 ou do Office 365 ativa de [um plano de elegível](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) e deve ter uma licença de equipes.</span><span class="sxs-lookup"><span data-stu-id="05b57-132">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan ](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="05b57-133">Atribuir uma licença de equipes a usuários lhes acesso às equipes.</span><span class="sxs-lookup"><span data-stu-id="05b57-133">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="05b57-134">Você gerenciar licenças de equipes no Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="05b57-134">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="05b57-135">Para saber mais, consulte [Manage user access às equipes](../../user-access.md).</span><span class="sxs-lookup"><span data-stu-id="05b57-135">To learn more, see [Manage user access to Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="05b57-136">Se sua organização usa Skype para negócios e você não estiver pronto para migrar todos os seus usuários para equipes, você poderá habilitar equipes para seus funcionários de Firstline que poderá executar equipes junto com Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="05b57-136">If your organization uses Skype for Business and you’re not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="05b57-137">Neste modo de coexistência, chamado *Ilhas*, cada aplicativo cliente opera como uma solução separada.</span><span class="sxs-lookup"><span data-stu-id="05b57-137">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="05b57-138">Para saber mais, consulte [entender equipes e Skype para interoperabilidade e coexistência de negócios](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="05b57-138">To learn more, see [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a><span data-ttu-id="05b57-139">Provisionar contas para usuários StaffHub que não têm uma identidade no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="05b57-139">Provision accounts for StaffHub users who don't have an identity in Azure AD</span></span>

<span data-ttu-id="05b57-140">Cada gerente e um membro da equipe precisam ter uma identidade no Windows Azure Active Directory (AD Azure).</span><span class="sxs-lookup"><span data-stu-id="05b57-140">Each manager and team member must have an identity in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="05b57-141">Se um usuário já não tenha uma identidade no Azure AD, provisione uma conta para eles.</span><span class="sxs-lookup"><span data-stu-id="05b57-141">If a user doesn't already have an identity in Azure AD, provision an account for them.</span></span> <span data-ttu-id="05b57-142">Veja como.</span><span class="sxs-lookup"><span data-stu-id="05b57-142">Here's how.</span></span>

- <span data-ttu-id="05b57-143">Os gerentes e os proprietários de equipe StaffHub podem converter uma conta fictícia ou inativa e vinculá-lo a uma conta provisionada no StaffHub, alterando o endereço de email do usuário para um UPN válido, na página de configurações da equipe do StaffHub.</span><span class="sxs-lookup"><span data-stu-id="05b57-143">StaffHub team owners and managers can convert a dummy or inactive account and link it to a provisioned account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="05b57-144">Administradores podem executar o [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) e cmdlets de [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) para remover uma conta não provisionado de uma equipe de StaffHub e adicione a conta de volta usando o UPN.</span><span class="sxs-lookup"><span data-stu-id="05b57-144">Admins can run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) and [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) cmdlets to remove a non-provisioned account from a StaffHub team and add the account back by using the UPN.</span></span>

### <a name="install-the-staffhub-powershell-module"></a><span data-ttu-id="05b57-145">Instale o módulo StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="05b57-145">Install the StaffHub PowerShell module</span></span>

<span data-ttu-id="05b57-146">Se você ainda não estiver, instale o [módulo de StaffHub PowerShell](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha).</span><span class="sxs-lookup"><span data-stu-id="05b57-146">If you haven't already, install the [StaffHub PowerShell module](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha).</span></span>

<span data-ttu-id="05b57-147">Quando você move uma equipe StaffHub, a solicitação de movimentação verifica os pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="05b57-147">When you move a StaffHub team, the move request checks for prerequisites.</span></span> <span data-ttu-id="05b57-148">Eis motivos por que uma solicitação de movimentação pode falhar:</span><span class="sxs-lookup"><span data-stu-id="05b57-148">Here's reasons why a move request may fail:</span></span>

- <span data-ttu-id="05b57-149">O usuário conectado não é um administrador global</span><span class="sxs-lookup"><span data-stu-id="05b57-149">The signed-in user is not a global admin</span></span>
- <span data-ttu-id="05b57-150">As equipes está desabilitada para todos os usuários no locatário</span><span class="sxs-lookup"><span data-stu-id="05b57-150">Teams is disabled for all users in the tenant</span></span>
- <span data-ttu-id="05b57-151">Criação de grupos do Office 365 está desabilitada no locatário</span><span class="sxs-lookup"><span data-stu-id="05b57-151">Office 365 Groups creation is disabled in the tenant</span></span>
- <span data-ttu-id="05b57-152">O teamId StaffHub não é válida ou não possui membros</span><span class="sxs-lookup"><span data-stu-id="05b57-152">The StaffHub teamId is not valid or has no members</span></span>
- <span data-ttu-id="05b57-153">A equipe de StaffHub inclui membros que não estão vinculados a uma conta do Windows Azure AD</span><span class="sxs-lookup"><span data-stu-id="05b57-153">The StaffHub team includes members that aren't linked to an Azure AD account</span></span>  

## <a name="run-a-pilot"></a><span data-ttu-id="05b57-154">Executar um piloto</span><span class="sxs-lookup"><span data-stu-id="05b57-154">Run a pilot</span></span>

<span data-ttu-id="05b57-155">Recomendamos que você inicie movendo dois ou três equipes de StaffHub para um grupo seleto de usuários iniciais.</span><span class="sxs-lookup"><span data-stu-id="05b57-155">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="05b57-156">Executar um piloto ajuda refinar seu plano de transição e certifique-se de que você está pronto para mover as equipes de StaffHub todos da sua organização para equipes.</span><span class="sxs-lookup"><span data-stu-id="05b57-156">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="05b57-157">Ele também identifica campeões que podem ajudar incentivar a adoção em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="05b57-157">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="05b57-158">Se você tem uma pequena empresa que não precisa de uma abordagem em fases, as etapas desta seção podem ser tudo o que você precisa para fazer a opção de StaffHub com equipes.</span><span class="sxs-lookup"><span data-stu-id="05b57-158">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="05b57-159">Identificar as equipes piloto</span><span class="sxs-lookup"><span data-stu-id="05b57-159">Identify pilot teams</span></span>

<span data-ttu-id="05b57-160">Chegar aos identificar dois ou três equipes piloto.</span><span class="sxs-lookup"><span data-stu-id="05b57-160">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="05b57-161">Todos os membros da equipe devem confirmar usando desloca nas equipes para gerenciar suas próprias agendas e se comunicar e colaborar entre si.</span><span class="sxs-lookup"><span data-stu-id="05b57-161">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="05b57-162">Identificar os campeões de equipe</span><span class="sxs-lookup"><span data-stu-id="05b57-162">Identify team champions</span></span>

<span data-ttu-id="05b57-163">Identificar campeões entre equipes piloto e inscrevê-los para ajudar a Pregue desloca.</span><span class="sxs-lookup"><span data-stu-id="05b57-163">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="05b57-164">Campeões de equipe são entusiasmados pela sobre o que isso acontece, compartilhamento de seus próprios lições para oferecer suporte e orientações para membros da equipe.</span><span class="sxs-lookup"><span data-stu-id="05b57-164">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="05b57-165">Campeões da equipe podem ser proprietários de equipe ou gerentes.</span><span class="sxs-lookup"><span data-stu-id="05b57-165">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="05b57-166">Verifique se campeões equipe membros da equipe são configurada pela dedicar tempo todos para [obter os clientes de equipes](../../get-clients.md), entrar com equipes e check-out de suas próprias agendas em desloca e iniciar o bate-papo uns com os outros.</span><span class="sxs-lookup"><span data-stu-id="05b57-166">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="05b57-167">Usuários que já estão familiarizados com StaffHub estará em funcionamento rapidamente no desloca.</span><span class="sxs-lookup"><span data-stu-id="05b57-167">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="05b57-168">Você também pode apontá-los para [Ajudar a desloca](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) para obter ajuda adicional.</span><span class="sxs-lookup"><span data-stu-id="05b57-168">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team"></a><span data-ttu-id="05b57-169">Mover uma equipe StaffHub</span><span class="sxs-lookup"><span data-stu-id="05b57-169">Move a StaffHub team</span></span>

<span data-ttu-id="05b57-170">Use estas etapas para mover uma equipe de StaffHub por vez.</span><span class="sxs-lookup"><span data-stu-id="05b57-170">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="05b57-171">Recomendamos essa abordagem para suas equipes piloto.</span><span class="sxs-lookup"><span data-stu-id="05b57-171">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="05b57-172">Posteriormente, quando estiver pronto para migrar as equipes de StaffHub todos da sua organização, consulte [mover suas equipes StaffHub](#move-your-staffhub-teams) para obter etapas sobre como mover várias equipes de cada vez.</span><span class="sxs-lookup"><span data-stu-id="05b57-172">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="05b57-173">Execute o seguinte procedimento para mover uma equipe de StaffHub.</span><span class="sxs-lookup"><span data-stu-id="05b57-173">Run the following to move a StaffHub team.</span></span>

```
Move-StaffHubTeam -Identity <String>
```

<span data-ttu-id="05b57-174">Aqui está um exemplo da resposta obtido quando você envia uma solicitação para mover uma equipe StaffHub para equipes.</span><span class="sxs-lookup"><span data-stu-id="05b57-174">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```
    jobId   teamId                                      teamAlreadyInMicrosofteams  
    -----   ------                                      ------------          
        1   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   True
```

<span data-ttu-id="05b57-175">Para verificar o status de uma solicitação de movimentação, execute o seguinte.</span><span class="sxs-lookup"><span data-stu-id="05b57-175">To check the status of a move request, run the following.</span></span>

```
Get-TeamMigrationJobStatus <Int32>
```

<span data-ttu-id="05b57-176">Aqui está um exemplo da resposta obtido quando uma movimentação está em andamento.</span><span class="sxs-lookup"><span data-stu-id="05b57-176">Here's an example of the response you get when a move is in progress.</span></span>

```
    jobId   status       teamId                                     isO365GroupCreated  Error
    -----   ------       ------                                     ------------------  -----    
        1   InProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  True                None
```

## <a name="make-the-transition-from-staffhub-to-teams"></a><span data-ttu-id="05b57-177">Fazer a transição de StaffHub às equipes</span><span class="sxs-lookup"><span data-stu-id="05b57-177">Make the transition from StaffHub to Teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="05b57-178">Aumente a conscientização</span><span class="sxs-lookup"><span data-stu-id="05b57-178">Raise awareness</span></span>

<span data-ttu-id="05b57-179">Quando você está pronto para ir além suas equipes piloto e mover as equipes de StaffHub da sua organização para equipes, é importante se comunicar pela primeira vez a alteração em sua organização.</span><span class="sxs-lookup"><span data-stu-id="05b57-179">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="05b57-180">Difundir o word sobre mudanças e a transição para equipes atenção, estimular o interesse e direcionar a adoção.</span><span class="sxs-lookup"><span data-stu-id="05b57-180">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams"></a><span data-ttu-id="05b57-181">Mover suas equipes StaffHub</span><span class="sxs-lookup"><span data-stu-id="05b57-181">Move your StaffHub teams</span></span>

<span data-ttu-id="05b57-182">Use estas etapas para mover StaffHub equipes em massa.</span><span class="sxs-lookup"><span data-stu-id="05b57-182">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="05b57-183">Você pode optar por mover as equipes de StaffHub todos da sua organização ou mover equipes de StaffHub específicas.</span><span class="sxs-lookup"><span data-stu-id="05b57-183">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="05b57-184">Se você deseja mover que staffhub às equipes um de cada vez, consulte [Mover uma equipe de StaffHub](#move-a-staffhub-team).</span><span class="sxs-lookup"><span data-stu-id="05b57-184">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team).</span></span>

#### <a name="move-all-staffhub-teams"></a><span data-ttu-id="05b57-185">Mover todas as equipes de StaffHub</span><span class="sxs-lookup"><span data-stu-id="05b57-185">Move all StaffHub teams</span></span>

<span data-ttu-id="05b57-186">Execute o seguinte procedimento para obter uma lista de todas as equipes de StaffHub em sua organização.</span><span class="sxs-lookup"><span data-stu-id="05b57-186">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```
$StaffHubTeams = Get-StaffHubTeamsForTenant
```

<span data-ttu-id="05b57-187">Em seguida, execute o seguinte procedimento para mover todas as equipes.</span><span class="sxs-lookup"><span data-stu-id="05b57-187">Then, run the following to move all teams.</span></span>

```
$StaffHubTeams | foreach {Move-StaffHubTeam -Identity {$_.Id}}
```

<span data-ttu-id="05b57-188">Aqui está um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="05b57-188">Here's an example of the response.</span></span>

```
    jobId   teamId                                      teamAlreadyInMicrosofteams  
    -----   ------                                      ------------          
        1   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   True
        2   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   False
```

#### <a name="move-specific-staffhub-teams"></a><span data-ttu-id="05b57-189">Mover as equipes de StaffHub específicas</span><span class="sxs-lookup"><span data-stu-id="05b57-189">Move specific StaffHub teams</span></span>

<span data-ttu-id="05b57-190">Execute o seguinte procedimento para obter uma lista de todas as equipes de StaffHub em sua organização.</span><span class="sxs-lookup"><span data-stu-id="05b57-190">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```
$StaffHubTeams = Get-StaffHubTeamsForTenant
```

<span data-ttu-id="05b57-191">Crie um arquivo de valores separados por vírgula (CSV) e adicione as identificações das equipes que deseja mover.</span><span class="sxs-lookup"><span data-stu-id="05b57-191">Create a comma-separated values (CSV) file and add the IDs of the teams you want to move.</span></span>
<span data-ttu-id="05b57-192">Aqui está um exemplo.</span><span class="sxs-lookup"><span data-stu-id="05b57-192">Here's an example.</span></span>

|<span data-ttu-id="05b57-193">ID</span><span class="sxs-lookup"><span data-stu-id="05b57-193">Id</span></span>  |
|---------|
|<span data-ttu-id="05b57-194">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="05b57-194">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="05b57-195">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="05b57-195">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="05b57-196">TEAM_b42d0fa2 - 0fc 9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="05b57-196">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="05b57-197">TEAM_b42d0fa2 - 0fc 9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="05b57-197">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="05b57-198">Em seguida, execute o seguinte procedimento para mover as equipes que você especificou no arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="05b57-198">Then, run the following to move the teams you specified in the CSV file.</span></span>

```
Import-Csv .\teams.txt | foreach {Move-StaffHubTeam -Identity {$_.Id}}
```

## <a name="monitor-teams-usage"></a><span data-ttu-id="05b57-199">Monitorar o uso de equipes</span><span class="sxs-lookup"><span data-stu-id="05b57-199">Monitor Teams usage</span></span>

<span data-ttu-id="05b57-200">Relatórios de uso podem ajudá-lo a entender os padrões de uso melhor e a fornecer ideias sobre onde priorizar os esforços de treinamento e comunicação em sua organização.</span><span class="sxs-lookup"><span data-stu-id="05b57-200">Usage reports can help you better understand usage patterns and give you insights on where to prioritize training and communication efforts across your organization.</span></span> <span data-ttu-id="05b57-201">Como desloca é um aplicativo em equipes, você pode visualizar o uso por meio de relatórios de equipes.</span><span class="sxs-lookup"><span data-stu-id="05b57-201">Because Shifts is an app in Teams, you can view usage through Teams reports.</span></span> <span data-ttu-id="05b57-202">Para obter mais informações, consulte [equipes relatórios no Centro de administração do Microsoft equipes](../../teams-analytics-and-reports/teams-reporting-reference.md) e [relatórios de atividade de equipes no Centro de administração do Microsoft 365](../../teams-activity-reports.md).</span><span class="sxs-lookup"><span data-stu-id="05b57-202">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="05b57-203">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="05b57-203">Related topics</span></span>
- [<span data-ttu-id="05b57-204">O Microsoft StaffHub será desativado</span><span class="sxs-lookup"><span data-stu-id="05b57-204">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="05b57-205">Gerenciar o aplicativo Turnos para sua organização no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="05b57-205">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="05b57-206">Referência StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="05b57-206">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
