---
title: Mova as suas equipes do StaffHub para o Shifts no Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Aprenda a mover suas equipes e os dados agendados do Microsoft StaffHub para o Shifts no Microsoft Teams.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e2e8b0ac4f1c4eb0cce2cae97481fc428f588ec5
ms.sourcegitcommit: 8f9bf1acdcdc2104fa8c343c030d64838e2c31eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/07/2019
ms.locfileid: "34780805"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="82509-103">Mova as suas equipes do Microsoft StaffHub para o Shifts no Teams</span><span class="sxs-lookup"><span data-stu-id="82509-103">Move your StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="82509-104">A partir 1 de outubro de 2019, o Microsoft StaffHub será desativado.</span><span class="sxs-lookup"><span data-stu-id="82509-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="82509-105">Estamos criando recursos StaffHub no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="82509-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="82509-106">Hoje, o Teams inclui o aplicativo Shifts para o gerenciamento de cronogramas e os recursos adicionais serão implantados com o tempo.</span><span class="sxs-lookup"><span data-stu-id="82509-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="82509-107">O StaffHub deixará de funcionar para todos os usuários em 1 de outubro de 2019.</span><span class="sxs-lookup"><span data-stu-id="82509-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="82509-108">Todas as pessoas que tentarem abrir o StaffHub receberão uma mensagem direcionando-as para o download do Teams.</span><span class="sxs-lookup"><span data-stu-id="82509-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="82509-109">Para saber mais, confira [O Microsoft StaffHub será desativado](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="82509-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

<span data-ttu-id="82509-110">O aplicativo Shifts no Teams oferece uma abordagem simples para o gerenciamento de cronogramas e o fluxo constante de trocas de turnos e cancelamentos que ocorrem diariamente.</span><span class="sxs-lookup"><span data-stu-id="82509-110">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="82509-111">Os membros da equipe podem acessar o cronograma e as informações de turno diretamente no aplicativo e em seus dispositivos para definir suas preferências, gerenciar seus cronogramas e solicitar folgas.</span><span class="sxs-lookup"><span data-stu-id="82509-111">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="82509-112">Este artigo descreve como mover as equipes StaffHub da sua organização e os dados agendados para o Shifts no Teams.</span><span class="sxs-lookup"><span data-stu-id="82509-112">This article walks you through how to move your organization’s StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="82509-113">Ele abrange:</span><span class="sxs-lookup"><span data-stu-id="82509-113">It covers:</span></span>

- [<span data-ttu-id="82509-114">O que você precisa saber sobre a mudança para o Teams</span><span class="sxs-lookup"><span data-stu-id="82509-114">What you need to know about the move to Teams</span></span>](#what-you-need-to-know-about-the-move-to-teams)
- [<span data-ttu-id="82509-115">Preparar</span><span class="sxs-lookup"><span data-stu-id="82509-115">Prepare Schema</span></span>](#prepare)
- [<span data-ttu-id="82509-116">Conduzir um piloto</span><span class="sxs-lookup"><span data-stu-id="82509-116">Conduct a user pilot</span></span>](#conduct-a-pilot) 
- [<span data-ttu-id="82509-117">Ir além do seu piloto e mover todas as equipes do StaffHub</span><span class="sxs-lookup"><span data-stu-id="82509-117">Go beyond your pilot and move all StaffHub teams</span></span>](#go-beyond-your-pilot-and-move-all-staffhub-teams)
- [<span data-ttu-id="82509-118">Monitorar o uso do Teams</span><span class="sxs-lookup"><span data-stu-id="82509-118">Monitor Teams usage</span></span>](#monitor-teams-usage)
- [<span data-ttu-id="82509-119">Solução de Problemas</span><span class="sxs-lookup"><span data-stu-id="82509-119">Troubleshooting</span></span>](#troubleshooting)

<span data-ttu-id="82509-120">Seja você uma pequena empresa com uma ou duas equipes do StaffHub ou uma grande empresa com centenas de equipes do StaffHub, aqui você encontrará as diretrizes de administração necessárias que ajudarão a tornar sua transição para o Teams bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="82509-120">Whether you’re a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you’ll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="82509-121">Você deve ser um administrador global para realizar as etapas deste artigo.</span><span class="sxs-lookup"><span data-stu-id="82509-121">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="82509-122">Se você ainda não fez isso, dê uma olhada nas [Perguntas frequentes sobre a desativação do StaffHub](microsoft-staffhub-to-be-retired.md) para obter respostas para quaisquer dúvidas que possa ter.</span><span class="sxs-lookup"><span data-stu-id="82509-122">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span>

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="82509-123">O que você precisa saber sobre a mudança para o Teams</span><span class="sxs-lookup"><span data-stu-id="82509-123">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="82509-124">Quando ir para o Teams</span><span class="sxs-lookup"><span data-stu-id="82509-124">When to move to Teams</span></span>

<span data-ttu-id="82509-125">A partir 1 de outubro de 2019, o StaffHub será desativado.</span><span class="sxs-lookup"><span data-stu-id="82509-125">Effective October 1, 2019, StaffHub will be retired.</span></span> <span data-ttu-id="82509-126">Incentivamos você a começar a usar o Teams hoje e a começar a fazer a transição das equipes e dos usuários da sua organização do StaffHub.</span><span class="sxs-lookup"><span data-stu-id="82509-126">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="82509-127">Com o gerenciamento de agendamento sendo o recurso mais usado no StaffHub, recomendamos que você use o aplicativo Shifts no Teams em andamento.</span><span class="sxs-lookup"><span data-stu-id="82509-127">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="82509-128">O que é movido para o Teams</span><span class="sxs-lookup"><span data-stu-id="82509-128">What is moved to Teams</span></span>

<span data-ttu-id="82509-129">Os detalhes do usuário, as informações do cronograma e os dados de chat e arquivos são transicionados para ao Teams.</span><span class="sxs-lookup"><span data-stu-id="82509-129">User details, schedule information, and chat and file data are transitioned to Teams.</span></span> <span data-ttu-id="82509-130">Isso inclui membros da equipe, cronograma da equipe, bate-papos e arquivos dos últimos 90 dias.</span><span class="sxs-lookup"><span data-stu-id="82509-130">This includes team membership, team schedules, and chats and files from the last 90 days.</span></span>

<span data-ttu-id="82509-131">Cada equipe do StaffHub precisa de um Grupo do Office 365 correspondente.</span><span class="sxs-lookup"><span data-stu-id="82509-131">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="82509-132">Se uma equipe do StaffHub não tiver um Grupo do Office 365 associado a ele, um será criado automaticamente para você para dar suporte à transição.</span><span class="sxs-lookup"><span data-stu-id="82509-132">If a StaffHub team doesn't have an Office 365 Group associated with it, one is automatically created for you to support the transition.</span></span> <span data-ttu-id="82509-133">Devido à diferença na nomeação da equipe e do grupo entre o Teams e o StaffHub, você poderá ver um nome de equipe diferente no Teams.</span><span class="sxs-lookup"><span data-stu-id="82509-133">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span>

<span data-ttu-id="82509-134">À medida que você faz a transição das equipes do StaffHub para o Teams, os usuários não terão mais acesso a seus cronogramas no StaffHub e serão redirecionados para o Shifts no Teams.</span><span class="sxs-lookup"><span data-stu-id="82509-134">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="82509-135">É recomendável comunicar essa alteração a toda a sua organização para minimizar as interrupções e incentivar os usuários a adotar e explorar o Teams.</span><span class="sxs-lookup"><span data-stu-id="82509-135">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span> <span data-ttu-id="82509-136">Caso tenha o Azure AD Premium, você pode [executar um relatório](run-report-to-show-staffhub-usage.md) para obter uma lista de usuários do StaffHub em sua organização que precisam saber mais sobre essa alteração.</span><span class="sxs-lookup"><span data-stu-id="82509-136">If you have Azure AD Premium, you can [run a report](run-report-to-show-staffhub-usage.md) to get a list of StaffHub users in your organization who need to know about this change.</span></span>  

<span data-ttu-id="82509-137">Não há uma opção de reversão após mover uma equipe do StaffHub para o Teams.</span><span class="sxs-lookup"><span data-stu-id="82509-137">There's no rollback option after you move a StaffHub team to Teams.</span></span>

### <a name="user-experience-when-you-move-a-team"></a><span data-ttu-id="82509-138">Experiência do usuário ao mover uma equipe</span><span class="sxs-lookup"><span data-stu-id="82509-138">User experience when you move a team</span></span>

<span data-ttu-id="82509-139">O tempo de inatividade é mínimo (menos de um segundo, se houver) para os usuários quando sua equipe for migrada do StaffHub para o Shifts no Teams.</span><span class="sxs-lookup"><span data-stu-id="82509-139">There's minimal downtime (less than a second, if any at all) for users when their team is switched from StaffHub to Shifts in Teams.</span></span> <span data-ttu-id="82509-140">Os usuários podem continuar usando o StaffHub até que a mudança para o Teams seja concluída.</span><span class="sxs-lookup"><span data-stu-id="82509-140">Users can continue using StaffHub until the move to Teams is completed.</span></span> <span data-ttu-id="82509-141">Quando a mudança estiver concluída, os membros da equipe verão uma mensagem informando que eles precisam começar a usar o Shifts no Teams para acessar o cronograma da equipe.</span><span class="sxs-lookup"><span data-stu-id="82509-141">When the move is completed, team members will see a message to let them know that they need to start using Shifts in Teams to access their team schedule.</span></span> <span data-ttu-id="82509-142">Veja um exemplo da mensagem que os usuários veem no StaffHub após a equipe do StaffHub ser movida para o Teams.</span><span class="sxs-lookup"><span data-stu-id="82509-142">Here's an example of the message that users see in StaffHub after the StaffHub team is moved to Teams.</span></span>

<span data-ttu-id="82509-143">![Exemplo da mensagem que os usuários visualizam. ](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Exemplo da mensagem que os usuários veem no StaffHub depois que a equipe do StaffHub é movida para o Teams")</span><span class="sxs-lookup"><span data-stu-id="82509-143">![Example of the message that users see.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Example of the message that users see in StaffHub after the StaffHub team is moved to Teams")</span></span>

## <a name="prepare"></a><span data-ttu-id="82509-144">Preparação</span><span class="sxs-lookup"><span data-stu-id="82509-144">Prepare Schema</span></span>

<span data-ttu-id="82509-145">Veja como se preparar para a mudança para o Teams.</span><span class="sxs-lookup"><span data-stu-id="82509-145">Here's how to prepare for the move to Teams.</span></span>

### <a name="check-that-prerequisites-are-met"></a><span data-ttu-id="82509-146">Verifique se os pré-requisitos foram atendidos</span><span class="sxs-lookup"><span data-stu-id="82509-146">Ensure that deployment prerequisites are met</span></span>

<span data-ttu-id="82509-147">Antes de mudar uma equipe do StaffHub para o Teams, certifique-se de que:</span><span class="sxs-lookup"><span data-stu-id="82509-147">Before you move a StaffHub team to Teams, make sure that:</span></span>

- <span data-ttu-id="82509-148">O usuário conectado é um administrador global.</span><span class="sxs-lookup"><span data-stu-id="82509-148">The signed-in user is a global admin.</span></span>
- <span data-ttu-id="82509-149">O Teams está habilitado para todos os usuários no locatário.</span><span class="sxs-lookup"><span data-stu-id="82509-149">Teams is enabled for all users in the tenant.</span></span>
- <span data-ttu-id="82509-150">A criação de grupos do Office 365 está habilitada no locatário.</span><span class="sxs-lookup"><span data-stu-id="82509-150">Office 365 Groups creation is enabled in the tenant.</span></span>
- <span data-ttu-id="82509-151">O teamId do StaffHub é válido.</span><span class="sxs-lookup"><span data-stu-id="82509-151">The StaffHub teamId is valid.</span></span>
- <span data-ttu-id="82509-152">A equipe do StaffHub contém membros.</span><span class="sxs-lookup"><span data-stu-id="82509-152">The StaffHub team contains members.</span></span> 
- <span data-ttu-id="82509-153">Todos os membros da equipe do StaffHub estão vinculados a uma conta do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="82509-153">All StaffHub team members are linked to an Azure AD account.</span></span> 

<span data-ttu-id="82509-154">Se esses pré-requisitos não forem atendidos, a solicitação de movimentação falhará.</span><span class="sxs-lookup"><span data-stu-id="82509-154">If these prerequisites aren't met, the move request will fail.</span></span> 

### <a name="assign-teams-licenses"></a><span data-ttu-id="82509-155">Atribuir licenças ao Teams</span><span class="sxs-lookup"><span data-stu-id="82509-155">Assign Teams licenses</span></span>

<span data-ttu-id="82509-156">Cada usuário deve ter uma licença ativa do Microsoft 365 ou do Office 365 de um [plano elegível](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) e deve ter uma licença do Teams.</span><span class="sxs-lookup"><span data-stu-id="82509-156">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="82509-157">Atribuir uma licença do Teams aos usuários lhes concede acesso ao Teams.</span><span class="sxs-lookup"><span data-stu-id="82509-157">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="82509-158">Gerencie as licenças do Teams no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="82509-158">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="82509-159">Para saber mais, confira [Gerenciar o acesso dos usuários ao Teams](../../user-access.md).</span><span class="sxs-lookup"><span data-stu-id="82509-159">To learn more, see [Manage user access to Microsoft Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="82509-160">Se a sua organização usa o Skype for Business e você não está pronto para mover todos os usuários para o Temas, é possível habilitar o Teams para os seus Firstline Workers que possam executar o Teams junto com o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="82509-160">If your organization uses Skype for Business and you’re not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="82509-161">Neste modo de coexistência, chamado *Ilhas*, cada aplicativo cliente funciona como uma solução separada.</span><span class="sxs-lookup"><span data-stu-id="82509-161">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="82509-162">Para saber mais, confira [Entender a coexistência e a interoperabilidade do Microsoft Teams e do Skype for Business](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="82509-162">To learn more, see [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="install-the-staffhub-powershell-module"></a><span data-ttu-id="82509-163">Instalar o módulo PowerShell do StaffHub</span><span class="sxs-lookup"><span data-stu-id="82509-163">Install the StaffHub PowerShell module</span></span>

<span data-ttu-id="82509-164">Se você ainda não [instalou o módulo PowerShell do StaffHub](install-the-staffhub-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="82509-164">If you haven't already, [install the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span> 

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a><span data-ttu-id="82509-165">Provisionar contas para usuários do StaffHub que não têm uma identidade no Azure AD</span><span class="sxs-lookup"><span data-stu-id="82509-165">Provision accounts for StaffHub users who don't have an identity in Azure AD</span></span>

<span data-ttu-id="82509-166">Cada gerente e membro da equipe devem ter uma identidade no Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="82509-166">Each manager and team member must have an identity in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="82509-167">Se um usuário ainda não tiver uma identidade no Azure AD, provisione uma conta para ele.</span><span class="sxs-lookup"><span data-stu-id="82509-167">If a user doesn't already have an identity in Azure AD, provision an account for them.</span></span> <span data-ttu-id="82509-168">Veja como.</span><span class="sxs-lookup"><span data-stu-id="82509-168">Here's how.</span></span> 

#### <a name="get-a-list-of-all-users-on-staffhub-teams-that-have-team-members-that-arent-provisioned-with-an-azure-ad-account"></a><span data-ttu-id="82509-169">Obtenha uma lista de todos os usuários na equipe do StaffHub que têm membros da equipe que não estão provisionados com uma conta do Azure AD</span><span class="sxs-lookup"><span data-stu-id="82509-169">Get a list of all users on StaffHub teams that have team members that aren't provisioned with an Azure AD account</span></span>

<span data-ttu-id="82509-170">Execute:</span><span class="sxs-lookup"><span data-stu-id="82509-170">Run the following:</span></span>
```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
foreach($team in $StaffHubTeams[0]) {Get-StaffHubMember -TeamId $team.Id | where {$_.Email -eq $null -or $_.State -eq "Invited"}}
```

#### <a name="provision-the-account"></a><span data-ttu-id="82509-171">Provisionar a conta</span><span class="sxs-lookup"><span data-stu-id="82509-171">Provision the account</span></span>

<span data-ttu-id="82509-172">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="82509-172">Do one of the following:</span></span>

- <span data-ttu-id="82509-173">Converta e vincule a conta a uma conta provisionada.</span><span class="sxs-lookup"><span data-stu-id="82509-173">Convert and link the account to a provisioned account.</span></span>

  <span data-ttu-id="82509-174">Os gerentes e proprietários da equipe do StaffHub podem converter uma conta fictícia ou inativa e vinculá-la a uma conta provisionada no StaffHub alterando o endereço de email do usuário para um UPN válido na página de configurações da equipe do StaffHub.</span><span class="sxs-lookup"><span data-stu-id="82509-174">StaffHub team owners and managers can convert a dummy or inactive account and link it to a provisioned account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="82509-175">Remova a conta não provisionada e, em seguida, adicione a conta novamente usando o UPN.</span><span class="sxs-lookup"><span data-stu-id="82509-175">Remove the non-provisioned account and then re-add the account by using the UPN.</span></span>
    1. <span data-ttu-id="82509-176">Execute o cmdlet [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) para remover a conta não provisionada da equipe do StaffHub.</span><span class="sxs-lookup"><span data-stu-id="82509-176">Run the [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) cmdlet to remove the non-provisioned account from the StaffHub team.</span></span>
    2. <span data-ttu-id="82509-177">Execute o cmdlet [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) para adicionar a conta novamente à equipe do StaffHub usando o UPN.</span><span class="sxs-lookup"><span data-stu-id="82509-177">Run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) cmdlet to add the account back to the StaffHub team by using the UPN.</span></span> 

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a><span data-ttu-id="82509-178">Atribua a política de configuração do aplicativo FirstlineWorker aos usuários</span><span class="sxs-lookup"><span data-stu-id="82509-178">Assign the FirstlineWorker app setup policy to users</span></span>

<span data-ttu-id="82509-179">O Teams possui uma política interna de configuração de aplicativos FirstlineWorker que você pode usar para personalizar o Teams para destacar os aplicativos mais importantes para os Firstline Workers da sua organização.</span><span class="sxs-lookup"><span data-stu-id="82509-179">Teams includes a built-in FirstlineWorker app setup policy that you can use to customize Teams to highlight the apps that are most important for the Firstline Workers in your organization.</span></span> <span data-ttu-id="82509-180">Quando você atribui essa política aos usuários, os aplicativos da política são fixados na barra de aplicativos do Teams para um acesso rápido e fácil.</span><span class="sxs-lookup"><span data-stu-id="82509-180">When you assign this policy to users, the apps in the policy are pinned to the app bar in Teams for quick and easy access.</span></span> <span data-ttu-id="82509-181">Outros aplicativos adicionados ao Teams podem ser encontrados na barra do aplicativo clicando em **... Mais aplicativos** na área de trabalho do Teams e nos clientes Web e ao passar o dedo para cima no cliente para dispositivo móvel do Teams.</span><span class="sxs-lookup"><span data-stu-id="82509-181">Other apps added to Teams can be found in the app bar by clicking **... More apps** in the Teams desktop and web clients and by swiping up in the Teams mobile client.</span></span> <span data-ttu-id="82509-182">Por padrão, a política de configuração do aplicativo FirstlineWorker inclui a atividade, turnos, chat e aplicativos de chamada.</span><span class="sxs-lookup"><span data-stu-id="82509-182">By default, the FirstlineWorker app setup policy includes the Activity, Shifts, Chat, and Calling apps.</span></span>

<span data-ttu-id="82509-183">Para obter as etapas sobre como atribuir a política de configuração do aplicativo FirstlineWorker aos [usuários, confira ](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams) usar a política de configuração do aplicativo FirstlineWorker para fixar turnos em equipes.</span><span class="sxs-lookup"><span data-stu-id="82509-183">For steps on how to assign the FirstlineWorker app setup policy to users, see [Use the FirstlineWorker app setup policy to pin Shifts to Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams).</span></span> <span data-ttu-id="82509-184">Depois de atribuir uma política, pode levar até 24 horas para entrar em vigor.</span><span class="sxs-lookup"><span data-stu-id="82509-184">After you assign a policy, it can take up to 24 hours to take effect.</span></span>

<span data-ttu-id="82509-185">É recomendável concluir esta etapa pelo menos uma semana antes de mover as equipes e usuários do StaffHub para o Teams.</span><span class="sxs-lookup"><span data-stu-id="82509-185">We recommend you complete this step at least a week before you move your StaffHub teams and users to Teams.</span></span> <span data-ttu-id="82509-186">Quando os usuários estão no Teams, confirme se eles podem ver e acessar o aplicativo turnos.</span><span class="sxs-lookup"><span data-stu-id="82509-186">When users are on Teams, confirm that they can see and access the Shifts app.</span></span>

<span data-ttu-id="82509-187">Você também pode criar políticas personalizadas de configuração de aplicativos e editar as configurações na política de configuração do aplicativo global.</span><span class="sxs-lookup"><span data-stu-id="82509-187">You can also create custom app setup policies and edit the settings in the global app setup policy.</span></span> <span data-ttu-id="82509-188">Para saber mais, confira [o gerenciamento de políticas de configuração de aplicativos no Teams](../../teams-app-setup-policies.md).</span><span class="sxs-lookup"><span data-stu-id="82509-188">To learn more, check out [Manage app setup policies in Teams](../../teams-app-setup-policies.md).</span></span>

### <a name="onboard-users-to-teams"></a><span data-ttu-id="82509-189">Integrar usuários ao Teams</span><span class="sxs-lookup"><span data-stu-id="82509-189">Onboard users to Teams</span></span>

<span data-ttu-id="82509-190">Como parte da sua estratégia de integração, forneça treinamento e orientações para os usuários que os ajudem a se familiarizar com o Teams.</span><span class="sxs-lookup"><span data-stu-id="82509-190">As part of your onboarding strategy, provide training and guidance for users to help them get familiar with Teams.</span></span> <span data-ttu-id="82509-191">Compartilhe os seguintes recursos com usuários, para que eles saibam onde obter os clientes, os treinamentos e o suporte do Teams:</span><span class="sxs-lookup"><span data-stu-id="82509-191">Share the following resources with users so they know where to get Teams clients, training, and support:</span></span>

- [<span data-ttu-id="82509-192">Cliente Web do Teams</span><span class="sxs-lookup"><span data-stu-id="82509-192">Teams web client</span></span>](https://teams.microsoft.com)
- [<span data-ttu-id="82509-193">Links para download de clientes para área de trabalho e dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="82509-193">Desktop and mobile client download links</span></span>](https://teams.microsoft.com/downloads)
- [<span data-ttu-id="82509-194">Vídeos de treinamento do Teams</span><span class="sxs-lookup"><span data-stu-id="82509-194">Teams training videos</span></span>](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [<span data-ttu-id="82509-195">Documentação da Ajuda do Teams</span><span class="sxs-lookup"><span data-stu-id="82509-195">Teams Help documentation</span></span>](https://support.office.com/teams)

<span data-ttu-id="82509-196">Para obter instruções sobre como implantar o Teams e conduzir a adoção do Teams, confira [como implantar o Teams](../../How-to-roll-out-teams.md)e [adotar o Teams](../../adopt-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="82509-196">For guidance on deploying Teams and driving Teams adoption, see [How to roll out Teams](../../How-to-roll-out-teams.md) and [Adopt Teams](../../adopt-microsoft-teams-landing-page.md).</span></span>

## <a name="conduct-a-pilot"></a><span data-ttu-id="82509-197">Conduzir um piloto</span><span class="sxs-lookup"><span data-stu-id="82509-197">Conduct a user pilot</span></span>

<span data-ttu-id="82509-198">Recomendamos que você comece movendo duas ou três equipes de StaffHub para um grupo seleto de pioneiros.</span><span class="sxs-lookup"><span data-stu-id="82509-198">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="82509-199">Executar um piloto ajuda você a refinar seu plano de transição e garantir que você esteja pronto para migrar todas as equipes de StaffHub da sua organização do Teams.</span><span class="sxs-lookup"><span data-stu-id="82509-199">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="82509-200">Também identifica os especialistas que podem ajudar a impulsionar a adoção em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="82509-200">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="82509-201">Se você for um pequeno negócio que não precisa de uma abordagem em fases, as etapas nesta seção talvez sejam tudo o que você precisa fazer no StaffHub para o Teams.</span><span class="sxs-lookup"><span data-stu-id="82509-201">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="82509-202">Identificar equipes piloto</span><span class="sxs-lookup"><span data-stu-id="82509-202">Identify pilot teams</span></span>

<span data-ttu-id="82509-203">Aproxime para identificar duas ou três equipes piloto.</span><span class="sxs-lookup"><span data-stu-id="82509-203">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="82509-204">Todos os membros da equipe devem se comprometer com o uso de turnos no Teams para gerenciar suas agendas e se comunicar e colaborar entre si.</span><span class="sxs-lookup"><span data-stu-id="82509-204">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="82509-205">Identificar os campeões da equipe</span><span class="sxs-lookup"><span data-stu-id="82509-205">Identify team champions</span></span>

<span data-ttu-id="82509-206">Identifique campeões nas equipes piloto e os convoque para ajudar a começar difundir turnos.</span><span class="sxs-lookup"><span data-stu-id="82509-206">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="82509-207">Os campeões da equipe são apaixonados pelo que fazem, compartilhando suas próprias novidades para oferecer suporte e orientações aos membros da equipe.</span><span class="sxs-lookup"><span data-stu-id="82509-207">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="82509-208">Os campeões da equipe podem ser proprietários ou gerentes da equipe.</span><span class="sxs-lookup"><span data-stu-id="82509-208">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="82509-209">Os campeões da equipe devem garantir que os membros da equipe sejam configurados por um tempo dedicado para que todos possam [ obter clientes do Teams](../../get-clients.md), entre no Teams e verifique suas agendas em turnos e comece a conversar com os outros.</span><span class="sxs-lookup"><span data-stu-id="82509-209">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="82509-210">Os usuários que já conhecem o StaffHub estarão funcionando rapidamente em turnos.</span><span class="sxs-lookup"><span data-stu-id="82509-210">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="82509-211">Você também pode apontá-los para a [Ajuda de turnos](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) para obter ajuda adicional.</span><span class="sxs-lookup"><span data-stu-id="82509-211">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team"></a><span data-ttu-id="82509-212">Mover uma equipe do StaffHub</span><span class="sxs-lookup"><span data-stu-id="82509-212">Move a StaffHub team</span></span>

<span data-ttu-id="82509-213">Use estas etapas para mover uma equipe do StaffHub por vez.</span><span class="sxs-lookup"><span data-stu-id="82509-213">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="82509-214">Recomendamos essa abordagem para suas equipes piloto.</span><span class="sxs-lookup"><span data-stu-id="82509-214">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="82509-215">Mais tarde, quando você estiver pronto para migrar todas as equipes do StaffHub da sua organização, confira[ o artigo migrar suas equipes do StaffHub](#move-your-staffhub-teams) para obter as etapas sobre como mover várias equipes de cada vez.</span><span class="sxs-lookup"><span data-stu-id="82509-215">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="82509-216">Execute o seguinte para mover uma equipe do StaffHub.</span><span class="sxs-lookup"><span data-stu-id="82509-216">Run the following to move a StaffHub team.</span></span>

```
Move-StaffHubTeam -TeamId <String>
```
<span data-ttu-id="82509-217">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="82509-217">Example</span></span>

```
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

<span data-ttu-id="82509-218">Veja um exemplo da resposta que você obtém ao enviar uma solicitação para mover uma equipe do StaffHub para o Teams.</span><span class="sxs-lookup"><span data-stu-id="82509-218">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

<span data-ttu-id="82509-219">Faça o seguinte para verificar o status das suas solicitações de movimentação.</span><span class="sxs-lookup"><span data-stu-id="82509-219">To check the status of a move request, run the following.</span></span>

```
Get-TeamMigrationJobStatus <String>
```
<span data-ttu-id="82509-220">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="82509-220">Example</span></span>

```
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

<span data-ttu-id="82509-221">Veja um exemplo da resposta que você obtém quando uma mudança está em andamento.</span><span class="sxs-lookup"><span data-stu-id="82509-221">Here's an example of the response you get when a move is in progress.</span></span>

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a><span data-ttu-id="82509-222">Mova os arquivos de uma equipe do StaffHub para o Teams</span><span class="sxs-lookup"><span data-stu-id="82509-222">Move files from a StaffHub team to Teams</span></span>

<span data-ttu-id="82509-223">Essa etapa só será aplicada se a equipe do StaffHub que você moveu para o Teams tiver arquivos que você deseja migrar para o Teams.</span><span class="sxs-lookup"><span data-stu-id="82509-223">This step only applies if the StaffHub team that you moved to Teams has files that you want to also move to Teams.</span></span> <span data-ttu-id="82509-224">Você pode mover os arquivos diretamente no SharePoint Online ou usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82509-224">You can move files directly in SharePoint Online or by using PowerShell.</span></span> 

#### <a name="in-sharepoint-online"></a><span data-ttu-id="82509-225">No SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="82509-225">In SharePoint Online</span></span>

<span data-ttu-id="82509-226">Veja [como mover arquivos no SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).</span><span class="sxs-lookup"><span data-stu-id="82509-226">See [How to move files in SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="82509-227">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="82509-227">Using Windows PowerShell</span></span>

<span data-ttu-id="82509-228">Baixe e instale o [Shell de Gerenciamento do SharePoint Online](https://www.microsoft.com/download/details.aspx?id=35588), caso ainda não tenha feito.</span><span class="sxs-lookup"><span data-stu-id="82509-228">Download and install the [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588), if you haven't already.</span></span> <span data-ttu-id="82509-229">Ela contém os cmdlets de que você precisa para mover arquivos.</span><span class="sxs-lookup"><span data-stu-id="82509-229">It contains the cmdlets you need to move files.</span></span>  

<span data-ttu-id="82509-230">Use o [cmdlet Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) para conectar-se ao site de equipe do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="82509-230">Use the [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) cmdlet to connect to the SharePoint Online team site.</span></span>

```
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

<span data-ttu-id="82509-231">Para cada arquivo que você deseja mover de StaffHub para o Teams, use o [cmdlet Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) para mover o arquivo.</span><span class="sxs-lookup"><span data-stu-id="82509-231">For each file that you want to move from StaffHub to Teams, use the [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) cmdlet to move the file.</span></span>

```
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

<span data-ttu-id="82509-232">Para mover vários arquivos, execute o loop sobre os arquivos e execute o segundo comando no loop.</span><span class="sxs-lookup"><span data-stu-id="82509-232">To move multiple files, loop over the files and run the second command on the loop.</span></span> <span data-ttu-id="82509-233">Não é necessário repetir o primeiro comando se a sessão permanecer ativa.</span><span class="sxs-lookup"><span data-stu-id="82509-233">You don't need to repeat the first command if the session remains active.</span></span>

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a><span data-ttu-id="82509-234">Ir além do seu piloto e mover todas as equipes do StaffHub</span><span class="sxs-lookup"><span data-stu-id="82509-234">Go beyond your pilot and move all StaffHub teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="82509-235">Aumentar a conscientização</span><span class="sxs-lookup"><span data-stu-id="82509-235">Raise awareness</span></span>

<span data-ttu-id="82509-236">Quando estiver pronto para ir além das suas equipes piloto e mover as equipes de StaffHub da sua organização para o Teams, é importante primeiro comunicar a alteração em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="82509-236">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="82509-237">Divulgue a palavra sobre turnos e a transição para as equipes aumentar a conscientização, gerar entusiasmo e impulsionar a adoção.</span><span class="sxs-lookup"><span data-stu-id="82509-237">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams"></a><span data-ttu-id="82509-238">Migrar suas equipes do StaffHub</span><span class="sxs-lookup"><span data-stu-id="82509-238">Move your StaffHub teams to Shifts in Microsoft Teams</span></span>

<span data-ttu-id="82509-239">Use estas etapas para mover equipes do StaffHub em massa.</span><span class="sxs-lookup"><span data-stu-id="82509-239">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="82509-240">Você pode optar por mover todas as equipes de StaffHub da sua organização ou mover equipes específicas do StaffHub.</span><span class="sxs-lookup"><span data-stu-id="82509-240">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="82509-241">Se você quiser mover uma equipe do StaffHub por vez, confira [migrar para uma equipe do StaffHub](#move-a-staffhub-team).</span><span class="sxs-lookup"><span data-stu-id="82509-241">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team).</span></span>

#### <a name="move-all-staffhub-teams"></a><span data-ttu-id="82509-242">Migrar todas as equipes do StaffHub</span><span class="sxs-lookup"><span data-stu-id="82509-242">Move all StaffHub teams</span></span>

<span data-ttu-id="82509-243">Execute o seguinte procedimento para obter uma lista de todas as equipes de StaffHub na sua organização.</span><span class="sxs-lookup"><span data-stu-id="82509-243">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="82509-244">Então, execute o seguinte para mover todas as equipes.</span><span class="sxs-lookup"><span data-stu-id="82509-244">Then, run the following to move all teams.</span></span>

```
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

<span data-ttu-id="82509-245">Veja um exemplo de resposta.</span><span class="sxs-lookup"><span data-stu-id="82509-245">Here's an example of the response.</span></span>

<span data-ttu-id="82509-246">Para todas as equipes que já foram movidas para o Teams ou já existem no Teams, a jobId será "nula", uma vez que não será necessário enviar um trabalho para migrar essa equipe.</span><span class="sxs-lookup"><span data-stu-id="82509-246">For any team that was already moved to Teams or already exists in Teams, the jobId will be "null" as a job doesn't need to be submitted to move that team.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a><span data-ttu-id="82509-247">Mover equipes StaffHub específicas</span><span class="sxs-lookup"><span data-stu-id="82509-247">Move specific StaffHub teams</span></span>

<span data-ttu-id="82509-248">Execute o seguinte procedimento para obter uma lista de todas as equipes lds de StaffHub na sua organização.</span><span class="sxs-lookup"><span data-stu-id="82509-248">Run the following to get a list of all StaffHub team Ids in your organization.</span></span>

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="82509-249">Nos resultados retornados pelo `Get-StaffHubteamsForTenant` cmdlet executado anteriormente, selecione as IDs da equipe que você deseja mover e, em seguida, adicione-as a um arquivo CSV (valores separados por vírgula).</span><span class="sxs-lookup"><span data-stu-id="82509-249">In the results returned by the `Get-StaffHubteamsForTenant` cmdlet you ran earlier, select the Team Ids you want to move, and then add them to a comma-separated values (CSV) file.</span></span>

<span data-ttu-id="82509-250">Veja um exemplo de como o arquivo CSV deve ser formatado.</span><span class="sxs-lookup"><span data-stu-id="82509-250">Here's an example of how the CSV file should be formatted.</span></span>

|<span data-ttu-id="82509-251">Id</span><span class="sxs-lookup"><span data-stu-id="82509-251">ID</span></span>  |
|---------|
|<span data-ttu-id="82509-252">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="82509-252">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="82509-253">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="82509-253">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="82509-254">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="82509-254">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="82509-255">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="82509-255">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="82509-256">Depois de criar o arquivo CSV, execute o seguinte procedimento para mover as equipes especificadas no arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="82509-256">After you create the CSV file, run the following to move the teams you specified in the CSV file.</span></span>

```
$StaffHubTeams = Import-Csv .\teams.csv
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a><span data-ttu-id="82509-257">Confirme se suas equipes do StaffHub migraram para o Teams</span><span class="sxs-lookup"><span data-stu-id="82509-257">Confirm that your StaffHub teams have moved to Teams</span></span>

<span data-ttu-id="82509-258">Execute o seguinte procedimento para obter uma lista de todas as equipes em turnos na sua organização.</span><span class="sxs-lookup"><span data-stu-id="82509-258">Run the following to get a list of all teams in Shifts in your organization.</span></span> 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a><span data-ttu-id="82509-259">Mova os arquivos de suas equipes do StaffHub para o Teams</span><span class="sxs-lookup"><span data-stu-id="82509-259">Move files from your StaffHub teams to Teams</span></span>

<span data-ttu-id="82509-260">Se as equipes do StaffHub que você moveu contiverem arquivos que você também deseja migrar para o Teams, confira [migrar arquivos de uma equipe do StaffHub para o Teams](#move-files-from-a-staffhub-team-to-teams).</span><span class="sxs-lookup"><span data-stu-id="82509-260">If the StaffHub teams that you moved contain files that you also want to move to Teams, see [Move files from a StaffHub team to Teams](#move-files-from-a-staffhub-team-to-teams).</span></span>

## <a name="monitor-teams-usage"></a><span data-ttu-id="82509-261">Monitorar o uso do Teams</span><span class="sxs-lookup"><span data-stu-id="82509-261">Monitor Teams usage</span></span>

<span data-ttu-id="82509-262">Os relatórios de uso podem ajudar você a entender melhor os padrões de uso e, com os comentários dos usuários, fornecer informações para orientar a implantação geral e indicar onde priorizar os esforços de treinamento e comunicação.</span><span class="sxs-lookup"><span data-stu-id="82509-262">Usage reports can help you better understand usage patterns, and along with user feedback, give you insights to inform your wider rollout and where to prioritize training and communication efforts.</span></span> <span data-ttu-id="82509-263">Como turnos é um aplicativo do Teams, você pode exibir o uso por meio de relatórios da equipe.</span><span class="sxs-lookup"><span data-stu-id="82509-263">Because Shifts is an app in Teams, you can view usage through Teams reports.</span></span> <span data-ttu-id="82509-264">Para obter mais informações, confira [relatórios do Teams no centro de Administração do Microsoft Teams](../../teams-analytics-and-reports/teams-reporting-reference.md) e[do relatórios de atividades do Teams o centro de administração do Microsoft 365.](../../teams-activity-reports.md)</span><span class="sxs-lookup"><span data-stu-id="82509-264">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="82509-265">Solução de Problemas</span><span class="sxs-lookup"><span data-stu-id="82509-265">Troubleshooting</span></span> 

<span data-ttu-id="82509-266">**Quando você tenta migrar arquivos do StaffHub para o Teams, você recebe a mensagem de erro "permissão negada".**</span><span class="sxs-lookup"><span data-stu-id="82509-266">**When you try to move files from StaffHub to Teams, you get a "Permission denied" error message.**</span></span>

<span data-ttu-id="82509-267">Isso pode ocorrer se você estiver tentando migrar arquivos em um grupo privado do Office 365 para o qual você não é membro.</span><span class="sxs-lookup"><span data-stu-id="82509-267">This may occur if you're trying to move files in a private Office 365 group that you're not a member of.</span></span> <span data-ttu-id="82509-268">Se esse for o caso, use o [cmdlet AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) para adicionar-se à equipe do StaffHub e, em seguida, mova os arquivos.</span><span class="sxs-lookup"><span data-stu-id="82509-268">If this is the case, use the [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) cmdlet to add yourself to the StaffHub team, and then move the files.</span></span> <span data-ttu-id="82509-269">Depois de mover os arquivos, use o [cmdlet Remove-](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) StaffHubMember para remover-se da equipe.</span><span class="sxs-lookup"><span data-stu-id="82509-269">After you move the files, use the [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) cmdlet to remove yourself from the team.</span></span> 

<span data-ttu-id="82509-270">**Quando tenta migrar arquivos do StaffHub para o Teams, você recebe uma mensagem de erro informando que a pasta geral não existe.**</span><span class="sxs-lookup"><span data-stu-id="82509-270">**When you try to move files from StaffHub to Teams, you get an error that says the General folder doesn't exist.**</span></span>

<span data-ttu-id="82509-271">Execute o seguinte comando para adicionar a pasta Geral ao SharePoint e, em seguida, tente novamente:</span><span class="sxs-lookup"><span data-stu-id="82509-271">Run the following command to add the General folder to SharePoint, and then try again:</span></span>

  ```
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a><span data-ttu-id="82509-272">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="82509-272">Related topics</span></span>
- [<span data-ttu-id="82509-273">Como implementar o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="82509-273">How to roll out Microsoft Teams</span></span>](../../How-to-roll-out-teams.md)
- [<span data-ttu-id="82509-274">O Microsoft StaffHub será desativado</span><span class="sxs-lookup"><span data-stu-id="82509-274">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="82509-275">Gerencie o aplicativo Turnos para sua organização no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="82509-275">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="82509-276">Referência do PowerShell do StaffHub</span><span class="sxs-lookup"><span data-stu-id="82509-276">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
