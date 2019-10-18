---
title: Mova as suas equipes do StaffHub para Turnos do Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como mover suas equipes do Microsoft StaffHub e agendar dados para turnos no Microsoft Teams.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 03131bd9a89ae5f54fc8318b004385de3e32e26e
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569677"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="de484-103">Mover suas equipes do Microsoft StaffHub para turnos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="de484-103">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="de484-104">A partir de 31 de dezembro de 2019, o Microsoft StaffHub será desativado.</span><span class="sxs-lookup"><span data-stu-id="de484-104">Effective December 31, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="de484-105">Estamos criando recursos de StaffHub no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="de484-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="de484-106">Hoje, o Teams inclui o aplicativo turnos para gerenciamento de agendamento e recursos adicionais se acumularão ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="de484-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="de484-107">O StaffHub deixará de funcionar para todos os usuários em 31 de dezembro de 2019.</span><span class="sxs-lookup"><span data-stu-id="de484-107">StaffHub will stop working for all users on December 31, 2019.</span></span> <span data-ttu-id="de484-108">Qualquer pessoa que tentar abrir o StaffHub será exibida uma mensagem direcionando-o para o download do teams.</span><span class="sxs-lookup"><span data-stu-id="de484-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="de484-109">Para saber mais, confira [Microsoft StaffHub para ser desativado](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="de484-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

<span data-ttu-id="de484-110">O aplicativo turnos no Microsoft Teams oferece uma abordagem simples para o gerenciamento de cronogramas e o fluxo constante de trocas de turnos e cancelamentos que ocorrem diariamente.</span><span class="sxs-lookup"><span data-stu-id="de484-110">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="de484-111">Os membros da equipe podem acessar o cronograma e deslocar as informações diretamente no aplicativo e em seus dispositivos para definir suas preferências, gerenciar seus cronogramas e solicitar folga.</span><span class="sxs-lookup"><span data-stu-id="de484-111">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="de484-112">Este artigo apresenta uma orientação sobre como mover as equipes do StaffHub da sua organização e agendar dados para turnos no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="de484-112">This article walks you through how to move your organization’s StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="de484-113">Ele aborda:</span><span class="sxs-lookup"><span data-stu-id="de484-113">It covers:</span></span>

- [<span data-ttu-id="de484-114">O que você precisa saber sobre a mudança para o Teams</span><span class="sxs-lookup"><span data-stu-id="de484-114">What you need to know about the move to Teams</span></span>](#what-you-need-to-know-about-the-move-to-teams)
- [<span data-ttu-id="de484-115">Pare</span><span class="sxs-lookup"><span data-stu-id="de484-115">Prepare</span></span>](#prepare)
- [<span data-ttu-id="de484-116">Conduzir um piloto</span><span class="sxs-lookup"><span data-stu-id="de484-116">Conduct a pilot</span></span>](#conduct-a-pilot) 
- [<span data-ttu-id="de484-117">Vá além do seu piloto e mova todas as equipes do StaffHub</span><span class="sxs-lookup"><span data-stu-id="de484-117">Go beyond your pilot and move all StaffHub teams</span></span>](#go-beyond-your-pilot-and-move-all-staffhub-teams)
- [<span data-ttu-id="de484-118">Monitorar o uso do teams</span><span class="sxs-lookup"><span data-stu-id="de484-118">Monitor Teams usage</span></span>](#monitor-teams-usage)
- [<span data-ttu-id="de484-119">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="de484-119">Troubleshooting</span></span>](#troubleshooting)

<span data-ttu-id="de484-120">Seja você uma pequena empresa com uma ou duas equipes do StaffHub ou uma grande empresa com centenas de equipes do StaffHub, você encontrará as diretrizes de administração necessárias para ajudar a fazer sua transição para o Microsoft Teams com êxito.</span><span class="sxs-lookup"><span data-stu-id="de484-120">Whether you’re a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you’ll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="de484-121">Você deve ser um administrador global para executar as etapas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="de484-121">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="de484-122">Se ainda não tiver feito isso, examine as [perguntas frequentes sobre a descontinuação do StaffHub](microsoft-staffhub-to-be-retired.md) para obter respostas para qualquer pergunta que você tenha.</span><span class="sxs-lookup"><span data-stu-id="de484-122">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span>

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="de484-123">O que você precisa saber sobre a mudança para o Teams</span><span class="sxs-lookup"><span data-stu-id="de484-123">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="de484-124">Quando mover para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="de484-124">When to move to Teams</span></span>

<span data-ttu-id="de484-125">A partir de 31 de dezembro de 2019 de StaffHub será desativada.</span><span class="sxs-lookup"><span data-stu-id="de484-125">Effective December 31, 2019, StaffHub will be retired.</span></span> <span data-ttu-id="de484-126">Recomendamos que você comece a usar o Microsoft Teams hoje e comece a fazer a transição das equipes e dos usuários da sua organização do StaffHub.</span><span class="sxs-lookup"><span data-stu-id="de484-126">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="de484-127">Com o gerenciamento de agendamento sendo o recurso mais comumente usado no StaffHub, recomendamos que você use o aplicativo turnos no Microsoft Teams, avançando.</span><span class="sxs-lookup"><span data-stu-id="de484-127">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="de484-128">O que é movido para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="de484-128">What is moved to Teams</span></span>

<span data-ttu-id="de484-129">Quando você move uma equipe do StaffHub, associação da equipe, detalhes do usuário, cronogramas da equipe e dados de chat são movidos para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="de484-129">When you move a StaffHub team, team membership, user details, team schedules, and chat data are moved to Teams.</span></span> <span data-ttu-id="de484-130">Os arquivos não são movidos quando você move uma equipe do StaffHub.</span><span class="sxs-lookup"><span data-stu-id="de484-130">Files aren't moved when you move a StaffHub team.</span></span> <span data-ttu-id="de484-131">Se uma equipe do StaffHub contém arquivos que você também deseja mover para o Microsoft Teams, mova os arquivos em uma etapa separada.</span><span class="sxs-lookup"><span data-stu-id="de484-131">If a StaffHub team contains files that you also want to move to teams, you move the files in a separate step.</span></span>

<span data-ttu-id="de484-132">Cada equipe do StaffHub precisa de um grupo do Office 365 correspondente.</span><span class="sxs-lookup"><span data-stu-id="de484-132">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="de484-133">Se uma equipe do StaffHub estiver associada a um grupo do Office 365, a configuração de privacidade do grupo será mantida quando você mover a equipe.</span><span class="sxs-lookup"><span data-stu-id="de484-133">If a StaffHub team is associated with an Office 365 Group, the privacy setting of the group is retained when you move the team.</span></span> <span data-ttu-id="de484-134">Se uma equipe do StaffHub não tiver um grupo do Office 365 associado a ela, um grupo com uma configuração de privacidade de particular será criado automaticamente para você dar suporte à transição.</span><span class="sxs-lookup"><span data-stu-id="de484-134">If a StaffHub team doesn't have an Office 365 Group associated with it, a group with a privacy setting of Private is automatically created for you to support the transition.</span></span>  <span data-ttu-id="de484-135">Devido à diferença na nomenclatura de equipes e grupos entre o Teams e o StaffHub, você pode ver um nome de equipe diferente no Teams.</span><span class="sxs-lookup"><span data-stu-id="de484-135">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span> 

<span data-ttu-id="de484-136">À medida que você muda de equipe do StaffHub para o Teams, os usuários não têm mais acesso às suas agendas no StaffHub e são redirecionados para turnos no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="de484-136">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="de484-137">Recomendamos que você comunique essa alteração a toda a sua organização para minimizar as interrupções e incentivar os usuários a adotar e explorar o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="de484-137">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span> <span data-ttu-id="de484-138">Se você tiver o Azure AD Premium, poderá [executar um relatório](run-report-to-show-staffhub-usage.md) para obter uma lista de usuários do StaffHub em sua organização que precisam saber mais sobre essa alteração.</span><span class="sxs-lookup"><span data-stu-id="de484-138">If you have Azure AD Premium, you can [run a report](run-report-to-show-staffhub-usage.md) to get a list of StaffHub users in your organization who need to know about this change.</span></span>  

<span data-ttu-id="de484-139">Não há opção de reversão após mover uma equipe do StaffHub para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="de484-139">There's no rollback option after you move a StaffHub team to Teams.</span></span>

### <a name="user-experience-when-you-move-a-team"></a><span data-ttu-id="de484-140">Experiência do usuário ao mover uma equipe</span><span class="sxs-lookup"><span data-stu-id="de484-140">User experience when you move a team</span></span>

<span data-ttu-id="de484-141">Há um tempo de inatividade mínimo (menos de um segundo) para os usuários quando sua equipe é comutada de StaffHub para turnos no Teams.</span><span class="sxs-lookup"><span data-stu-id="de484-141">There's minimal downtime (less than a second, if any at all) for users when their team is switched from StaffHub to Shifts in Teams.</span></span> <span data-ttu-id="de484-142">Os usuários podem continuar a usar o StaffHub até que a mudança para o Microsoft Teams seja concluída.</span><span class="sxs-lookup"><span data-stu-id="de484-142">Users can continue using StaffHub until the move to Teams is completed.</span></span> <span data-ttu-id="de484-143">Quando a mudança for concluída, os membros da equipe verão uma mensagem para informar que precisam começar a usar os turnos no Teams para acessar o cronograma da equipe.</span><span class="sxs-lookup"><span data-stu-id="de484-143">When the move is completed, team members will see a message to let them know that they need to start using Shifts in Teams to access their team schedule.</span></span> <span data-ttu-id="de484-144">Veja um exemplo da mensagem que os usuários verão no StaffHub depois que a equipe do StaffHub for movida para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="de484-144">Here's an example of the message that users see in StaffHub after the StaffHub team is moved to Teams.</span></span>

<span data-ttu-id="de484-145">![Exemplo da mensagem exibida pelos usuários.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Exemplo da mensagem que os usuários veem no StaffHub após a equipe do StaffHub ser movida para o Microsoft Teams")</span><span class="sxs-lookup"><span data-stu-id="de484-145">![Example of the message that users see.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Example of the message that users see in StaffHub after the StaffHub team is moved to Teams")</span></span>

## <a name="prepare"></a><span data-ttu-id="de484-146">Pare</span><span class="sxs-lookup"><span data-stu-id="de484-146">Prepare</span></span>

<span data-ttu-id="de484-147">Veja como se preparar para a mudança para o Teams.</span><span class="sxs-lookup"><span data-stu-id="de484-147">Here's how to prepare for the move to Teams.</span></span>

### <a name="check-that-prerequisites-are-met"></a><span data-ttu-id="de484-148">Verificar se os pré-requisitos foram atendidos</span><span class="sxs-lookup"><span data-stu-id="de484-148">Check that prerequisites are met</span></span>

<span data-ttu-id="de484-149">Antes de mover uma equipe do StaffHub para o Microsoft Teams, certifique-se de que:</span><span class="sxs-lookup"><span data-stu-id="de484-149">Before you move a StaffHub team to Teams, make sure that:</span></span>

- <span data-ttu-id="de484-150">O usuário conectado é um administrador global.</span><span class="sxs-lookup"><span data-stu-id="de484-150">The signed-in user is a global admin.</span></span>
- <span data-ttu-id="de484-151">O Teams está habilitado para todos os usuários no locatário.</span><span class="sxs-lookup"><span data-stu-id="de484-151">Teams is enabled for all users in the tenant.</span></span>
- <span data-ttu-id="de484-152">A criação de grupos do Office 365 está habilitada no locatário.</span><span class="sxs-lookup"><span data-stu-id="de484-152">Office 365 Groups creation is enabled in the tenant.</span></span>
- <span data-ttu-id="de484-153">O StaffHub TeamID é válido.</span><span class="sxs-lookup"><span data-stu-id="de484-153">The StaffHub teamId is valid.</span></span>
- <span data-ttu-id="de484-154">A equipe do StaffHub tem pelo menos um proprietário de equipe.</span><span class="sxs-lookup"><span data-stu-id="de484-154">The StaffHub team has at least one team owner.</span></span>
- <span data-ttu-id="de484-155">A equipe do StaffHub contém membros.</span><span class="sxs-lookup"><span data-stu-id="de484-155">The StaffHub team contains members.</span></span>
- <span data-ttu-id="de484-156">Todos os membros da equipe do StaffHub são vinculados a uma conta do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="de484-156">All StaffHub team members are linked to an Azure AD account.</span></span>
- <span data-ttu-id="de484-157">Todos os membros da equipe do StaffHub recebem uma licença do teams.</span><span class="sxs-lookup"><span data-stu-id="de484-157">All StaffHub team members are assigned a Teams license.</span></span>  

<span data-ttu-id="de484-158">Se esses pré-requisitos não forem atendidos, a solicitação de mudança falhará.</span><span class="sxs-lookup"><span data-stu-id="de484-158">If these prerequisites aren't met, the move request will fail.</span></span>

### <a name="assign-teams-licenses"></a><span data-ttu-id="de484-159">Atribuir licenças do Teams</span><span class="sxs-lookup"><span data-stu-id="de484-159">Assign Teams licenses</span></span>

<span data-ttu-id="de484-160">Cada usuário deve ter uma licença ativa do Microsoft 365 ou do Office 365 de [um plano elegível](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) e deve receber uma licença do teams.</span><span class="sxs-lookup"><span data-stu-id="de484-160">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="de484-161">Atribuir uma licença do teams aos usuários permite que eles acessem o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="de484-161">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="de484-162">Você gerencia as licenças do teams no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="de484-162">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="de484-163">Para saber mais, consulte [gerenciar o acesso do usuário ao Teams](../../user-access.md).</span><span class="sxs-lookup"><span data-stu-id="de484-163">To learn more, see [Manage user access to Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="de484-164">Se a sua organização usa o Skype for Business e você não está pronto para mover todos os usuários para o Microsoft Teams, você pode habilitar o Microsoft Teams para os seus primeiros trabalhadores que podem executar o Microsoft Teams junto ao Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="de484-164">If your organization uses Skype for Business and you’re not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="de484-165">Nesse modo de coexistência, chamado de *ilhas*, cada aplicativo cliente Opera como uma solução separada.</span><span class="sxs-lookup"><span data-stu-id="de484-165">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="de484-166">Para saber mais, consulte [entender o Microsoft Teams e a coexistência e interoperabilidade do Skype for Business](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="de484-166">To learn more, see [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="install-the-prerelease-version-of-the-staffhub-powershell-module"></a><span data-ttu-id="de484-167">Instalar a versão de pré-lançamento do módulo StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="de484-167">Install the prerelease version of the StaffHub PowerShell module</span></span>

<span data-ttu-id="de484-168">Se você ainda não fez isso, [Instale a versão de pré-lançamento do módulo StaffHub PowerShell](install-the-staffhub-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="de484-168">If you haven't already, [install the prerelease version of the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span>

<span data-ttu-id="de484-169">Você deve ter a versão de pré-lançamento do módulo instalada para mover suas equipes do StaffHub para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="de484-169">You must have the prerelease version of the module installed to move your StaffHub teams to Teams.</span></span>

### <a name="link-an-azure-ad-account-for-staffhub-team-members-who-dont-have-one"></a><span data-ttu-id="de484-170">Vincular uma conta do Azure AD para os membros da equipe do StaffHub que não têm uma</span><span class="sxs-lookup"><span data-stu-id="de484-170">Link an Azure AD account for StaffHub team members who don't have one</span></span>

<span data-ttu-id="de484-171">Cada membro da equipe do StaffHub deve estar vinculado a uma conta do Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="de484-171">Each StaffHub team member must be linked to an Azure Active Directory (Azure AD) account.</span></span> <span data-ttu-id="de484-172">Os usuários em sua organização não serão vinculados a uma conta do Azure AD se qualquer um dos seguintes cenários se aplicarem:</span><span class="sxs-lookup"><span data-stu-id="de484-172">Users in your organization won't be linked to an Azure AD account if any of the following scenarios apply:</span></span>

- <span data-ttu-id="de484-173">Um proprietário da equipe adicionou um usuário que não tem uma conta do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="de484-173">A team owner added a user who doesn't have an Azure AD account.</span></span>
- <span data-ttu-id="de484-174">Um proprietário da equipe convidou um usuário para uma equipe do StaffHub e esse usuário não aceitou o convite.</span><span class="sxs-lookup"><span data-stu-id="de484-174">A team owner invited a user to a StaffHub team and that user didn't accept the invitation.</span></span>

<span data-ttu-id="de484-175">Esses usuários têm contas inativas e mostram o estado do usuário de desconhecido, convidado ou InviteRejected.</span><span class="sxs-lookup"><span data-stu-id="de484-175">These users have inactive accounts and show a user state of Unknown, Invited, or InviteRejected.</span></span> <span data-ttu-id="de484-176">Você pode vincular uma conta do Azure AD para esses usuários.</span><span class="sxs-lookup"><span data-stu-id="de484-176">You can link an Azure AD account for these users.</span></span>  <span data-ttu-id="de484-177">Veja como.</span><span class="sxs-lookup"><span data-stu-id="de484-177">Here's how.</span></span>

#### <a name="get-a-list-of-all-inactive-accounts-on-staffhub-teams"></a><span data-ttu-id="de484-178">Obter uma lista de todas as contas inativas no StaffHub Teams</span><span class="sxs-lookup"><span data-stu-id="de484-178">Get a list of all inactive accounts on StaffHub teams</span></span>

<span data-ttu-id="de484-179">Execute o seguinte para obter uma lista de todas as contas inativas no StaffHub Teams e exportar a lista para um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="de484-179">Run the following to get a list of all inactive accounts on StaffHub teams and export the list to a CSV file.</span></span>

```
$InvitedUsersObject = @()
$StaffHubTeams = Get-StaffHubTeamsForTenant $StaffHubTeams[0] = $StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq 'StaffHub' }
foreach($team in $StaffHubTeams[0]) { write-host $team.name $StaffHubUsers = Get-StaffHubMember -TeamId $team.Id | where {$_.State -eq "Invited"}
foreach($StaffHubUser in $StaffHubUsers) {
        $InvitedUsersObject  += New-Object PsObject -Property @{         "TeamID"="$($team.Id)"         "TeamName"="$($team.name)"         "MemberID"="$($StaffHubUser.Id)" }
}
}
$InvitedUsersObject | SELECT * $InvitedUsersObject | SELECT * | export-csv InvitedUsers.csv -NoTypeInformation  
```

#### <a name="link-the-account"></a><span data-ttu-id="de484-180">Vincular a conta</span><span class="sxs-lookup"><span data-stu-id="de484-180">Link the account</span></span>

<span data-ttu-id="de484-181">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="de484-181">Do one of the following:</span></span>

- <span data-ttu-id="de484-182">Converter e vincular a conta.</span><span class="sxs-lookup"><span data-stu-id="de484-182">Convert and link the account.</span></span>

  <span data-ttu-id="de484-183">Os gerentes e proprietários de equipe do StaffHub podem converter uma conta inativa e vinculá-la a uma conta do Azure AD no StaffHub alterando o endereço de email do usuário para um UPN válido na página de configurações da equipe do StaffHub.</span><span class="sxs-lookup"><span data-stu-id="de484-183">StaffHub team owners and managers can convert an inactive account and link it to an Azure AD account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="de484-184">Remova a conta não vinculada e, em seguida, adicione novamente a conta usando o UPN.</span><span class="sxs-lookup"><span data-stu-id="de484-184">Remove the unlinked account and then re-add the account by using the UPN.</span></span>
    1. <span data-ttu-id="de484-185">Execute o cmdlet [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubMember?view=staffhub-ps) para remover a conta não provisionada da equipe do StaffHub.</span><span class="sxs-lookup"><span data-stu-id="de484-185">Run the [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubMember?view=staffhub-ps) cmdlet to remove the non-provisioned account from the StaffHub team.</span></span>
    2. <span data-ttu-id="de484-186">Execute o cmdlet [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) para adicionar a conta de volta à equipe do StaffHub usando o UPN.</span><span class="sxs-lookup"><span data-stu-id="de484-186">Run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) cmdlet to add the account back to the StaffHub team by using the UPN.</span></span>

- <span data-ttu-id="de484-187">Remover a conta inativa.</span><span class="sxs-lookup"><span data-stu-id="de484-187">Remove the inactive account.</span></span> <span data-ttu-id="de484-188">Use esta opção se a conta do usuário não for mais necessária.</span><span class="sxs-lookup"><span data-stu-id="de484-188">Use this option if the user account is no longer needed.</span></span>

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a><span data-ttu-id="de484-189">Atribuir a política de configuração do aplicativo FirstlineWorker aos usuários</span><span class="sxs-lookup"><span data-stu-id="de484-189">Assign the FirstlineWorker app setup policy to users</span></span>

<span data-ttu-id="de484-190">O Teams inclui uma política interna de configuração de aplicativos do FirstlineWorker que você pode usar para personalizar o Microsoft Teams para destacar os aplicativos que são mais importantes para os primeiros funcionários da sua organização.</span><span class="sxs-lookup"><span data-stu-id="de484-190">Teams includes a built-in FirstlineWorker app setup policy that you can use to customize Teams to highlight the apps that are most important for the Firstline Workers in your organization.</span></span> <span data-ttu-id="de484-191">Quando você atribui essa política aos usuários, os aplicativos da política são fixados na barra de aplicativos no Microsoft Teams para acesso rápido e fácil.</span><span class="sxs-lookup"><span data-stu-id="de484-191">When you assign this policy to users, the apps in the policy are pinned to the app bar in Teams for quick and easy access.</span></span> <span data-ttu-id="de484-192">Outros aplicativos adicionados às equipes podem ser encontrados na barra de aplicativos clicando em **... Mais aplicativos** na área de trabalho da equipe e nos clientes Web e passando o dedo para cima no cliente do teams Mobile.</span><span class="sxs-lookup"><span data-stu-id="de484-192">Other apps added to Teams can be found in the app bar by clicking **... More apps** in the Teams desktop and web clients and by swiping up in the Teams mobile client.</span></span> <span data-ttu-id="de484-193">Por padrão, a política de configuração do aplicativo FirstlineWorker inclui a atividade, turnos, chat e aplicativos de chamada.</span><span class="sxs-lookup"><span data-stu-id="de484-193">By default, the FirstlineWorker app setup policy includes the Activity, Shifts, Chat, and Calling apps.</span></span>

<span data-ttu-id="de484-194">Para ver as etapas sobre como atribuir a política de configuração do aplicativo FirstlineWorker aos usuários, consulte [usar a política de configuração do aplicativo FirstlineWorker para fixar turnos em Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams).</span><span class="sxs-lookup"><span data-stu-id="de484-194">For steps on how to assign the FirstlineWorker app setup policy to users, see [Use the FirstlineWorker app setup policy to pin Shifts to Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams).</span></span> <span data-ttu-id="de484-195">Depois de atribuir uma política, pode levar até 24 horas para entrar em vigor.</span><span class="sxs-lookup"><span data-stu-id="de484-195">After you assign a policy, it can take up to 24 hours to take effect.</span></span>

<span data-ttu-id="de484-196">Recomendamos que você conclua esta etapa pelo menos uma semana antes de mover suas equipes e usuários do StaffHub para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="de484-196">We recommend you complete this step at least a week before you move your StaffHub teams and users to Teams.</span></span> <span data-ttu-id="de484-197">Quando os usuários estão em equipes, confirme se eles podem ver e acessar o aplicativo turnos.</span><span class="sxs-lookup"><span data-stu-id="de484-197">When users are on Teams, confirm that they can see and access the Shifts app.</span></span>

<span data-ttu-id="de484-198">Você também pode criar políticas de configuração de aplicativo personalizadas e editar as configurações na política de configuração de aplicativo global.</span><span class="sxs-lookup"><span data-stu-id="de484-198">You can also create custom app setup policies and edit the settings in the global app setup policy.</span></span> <span data-ttu-id="de484-199">Para saber mais, confira [gerenciar políticas de configuração de aplicativos no Microsoft Teams](../../teams-app-setup-policies.md).</span><span class="sxs-lookup"><span data-stu-id="de484-199">To learn more, check out [Manage app setup policies in Teams](../../teams-app-setup-policies.md).</span></span>

### <a name="onboard-users-to-teams"></a><span data-ttu-id="de484-200">Usuários integrados ao Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="de484-200">Onboard users to Teams</span></span>

<span data-ttu-id="de484-201">Como parte da sua estratégia de integração, forneça treinamento e orientação para que os usuários ajudem a se familiarizar com o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="de484-201">As part of your onboarding strategy, provide training and guidance for users to help them get familiar with Teams.</span></span> <span data-ttu-id="de484-202">Compartilhe os recursos a seguir com os usuários para que eles saibam onde obter clientes, treinamento e suporte do teams:</span><span class="sxs-lookup"><span data-stu-id="de484-202">Share the following resources with users so they know where to get Teams clients, training, and support:</span></span>

- [<span data-ttu-id="de484-203">Cliente Web do Teams</span><span class="sxs-lookup"><span data-stu-id="de484-203">Teams web client</span></span>](https://teams.microsoft.com)
- [<span data-ttu-id="de484-204">Links para download de clientes para área de trabalho e dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="de484-204">Desktop and mobile client download links</span></span>](https://teams.microsoft.com/downloads)
- [<span data-ttu-id="de484-205">Vídeos de treinamento do Teams</span><span class="sxs-lookup"><span data-stu-id="de484-205">Teams training videos</span></span>](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [<span data-ttu-id="de484-206">Documentação da Ajuda do Teams</span><span class="sxs-lookup"><span data-stu-id="de484-206">Teams Help documentation</span></span>](https://support.office.com/teams)

<span data-ttu-id="de484-207">Para obter orientação sobre como implantar equipes e conduzir a adoção do Teams, consulte [como implantar equipes](../../How-to-roll-out-teams.md) e [adotar equipes](../../adopt-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="de484-207">For guidance on deploying Teams and driving Teams adoption, see [How to roll out Teams](../../How-to-roll-out-teams.md) and [Adopt Teams](../../adopt-microsoft-teams-landing-page.md).</span></span>

## <a name="conduct-a-pilot"></a><span data-ttu-id="de484-208">Conduzir um piloto</span><span class="sxs-lookup"><span data-stu-id="de484-208">Conduct a pilot</span></span>

<span data-ttu-id="de484-209">Recomendamos que você comece movendo duas ou três equipes StaffHub para um grupo seleto de pioneiros.</span><span class="sxs-lookup"><span data-stu-id="de484-209">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="de484-210">A execução de um piloto ajuda você a refinar seu plano de transição e garantir que você esteja pronto para mover todas as equipes do StaffHub da sua organização para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="de484-210">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="de484-211">Ele também identifica campeões que podem ajudar a impulsionar a adoção em toda a sua organização.</span><span class="sxs-lookup"><span data-stu-id="de484-211">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="de484-212">Se você for uma pequena empresa que não precisa de uma abordagem em fases, as etapas nesta seção podem ser tudo o que você precisa fazer para fazer a mudança do StaffHub para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="de484-212">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="de484-213">Identificar equipes piloto</span><span class="sxs-lookup"><span data-stu-id="de484-213">Identify pilot teams</span></span>

<span data-ttu-id="de484-214">Tenha acesso à identificação de duas ou três equipes piloto.</span><span class="sxs-lookup"><span data-stu-id="de484-214">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="de484-215">Todos os membros da equipe devem confirmar o uso de turnos no Teams para gerenciar seus cronogramas e se comunicar e colaborar uns com os outros.</span><span class="sxs-lookup"><span data-stu-id="de484-215">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="de484-216">Identificar especialistas da equipe</span><span class="sxs-lookup"><span data-stu-id="de484-216">Identify team champions</span></span>

<span data-ttu-id="de484-217">Identifique especialistas em nossas equipes piloto e as solicite para ajudar a evangelizar turnos.</span><span class="sxs-lookup"><span data-stu-id="de484-217">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="de484-218">Os representantes da equipe são apaixonados pelo que fazem, compartilhando suas próprias informações para oferecer suporte e orientação aos membros da equipe.</span><span class="sxs-lookup"><span data-stu-id="de484-218">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="de484-219">Os campeões da equipe podem ser proprietários ou gerentes da equipe.</span><span class="sxs-lookup"><span data-stu-id="de484-219">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="de484-220">Os campeões de equipe devem garantir que os membros da equipe sejam configurados dedicando-se tempo para que todos [obtenham clientes](../../get-clients.md)do Teams, entrem no Teams e confiram suas agendas em turnos e comecem a conversar uns com os outros.</span><span class="sxs-lookup"><span data-stu-id="de484-220">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="de484-221">Os usuários que já estão familiarizados com o StaffHub estarão em funcionamento rapidamente em turnos.</span><span class="sxs-lookup"><span data-stu-id="de484-221">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="de484-222">Você também pode apontá-los para a [ajuda de turnos](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) para obter ajuda adicional.</span><span class="sxs-lookup"><span data-stu-id="de484-222">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team"></a><span data-ttu-id="de484-223">Mover uma equipe do StaffHub</span><span class="sxs-lookup"><span data-stu-id="de484-223">Move a StaffHub team</span></span>

<span data-ttu-id="de484-224">Use estas etapas para mover uma equipe do StaffHub de cada vez.</span><span class="sxs-lookup"><span data-stu-id="de484-224">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="de484-225">Recomendamos essa abordagem para suas equipes piloto.</span><span class="sxs-lookup"><span data-stu-id="de484-225">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="de484-226">Mais tarde, quando você estiver pronto para mover todas as equipes do StaffHub da sua organização, consulte [mover suas equipes do StaffHub](#move-your-staffhub-teams) para ver as etapas sobre como mover várias equipes de cada vez.</span><span class="sxs-lookup"><span data-stu-id="de484-226">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="de484-227">Execute o seguinte para mover uma equipe do StaffHub.</span><span class="sxs-lookup"><span data-stu-id="de484-227">Run the following to move a StaffHub team.</span></span>

```
Move-StaffHubTeam -TeamId <String>
```
<span data-ttu-id="de484-228">Exemplo</span><span class="sxs-lookup"><span data-stu-id="de484-228">Example:</span></span>

```
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

<span data-ttu-id="de484-229">Veja um exemplo da resposta que você obtém quando envia uma solicitação para mover uma equipe do StaffHub para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="de484-229">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```
 jobId                                      teamId                                      teamAlreadyInMicrosofteams  
---------------------------------------    ----------------------------------------    ---------------------------          
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

<span data-ttu-id="de484-230">Para verificar o status de uma solicitação de movimentação, execute o seguinte.</span><span class="sxs-lookup"><span data-stu-id="de484-230">To check the status of a move request, run the following.</span></span>

```
Get-TeamMigrationJobStatus <String>
```
<span data-ttu-id="de484-231">Exemplo</span><span class="sxs-lookup"><span data-stu-id="de484-231">Example:</span></span>

```
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

<span data-ttu-id="de484-232">Veja um exemplo da resposta que você obtém quando uma mudança está em andamento.</span><span class="sxs-lookup"><span data-stu-id="de484-232">Here's an example of the response you get when a move is in progress.</span></span>

```
jobId                                     status       teamId                                     isO365GroupCreated  Error
----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a><span data-ttu-id="de484-233">Mover arquivos de uma equipe do StaffHub para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="de484-233">Move files from a StaffHub team to Teams</span></span>

<span data-ttu-id="de484-234">Esta etapa aplica-se apenas se a equipe do StaffHub que você moveu para o Microsoft Teams tiver arquivos que você deseja que também se movam para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="de484-234">This step only applies if the StaffHub team that you moved to Teams has files that you want to also move to Teams.</span></span> <span data-ttu-id="de484-235">Você pode mover arquivos diretamente no SharePoint Online ou usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="de484-235">You can move files directly in SharePoint Online or by using PowerShell.</span></span>

#### <a name="in-sharepoint-online"></a><span data-ttu-id="de484-236">No SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="de484-236">In SharePoint Online</span></span>

<span data-ttu-id="de484-237">Veja [como mover arquivos no SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).</span><span class="sxs-lookup"><span data-stu-id="de484-237">See [How to move files in SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="de484-238">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="de484-238">Using PowerShell</span></span>

<span data-ttu-id="de484-239">Baixe e instale o [Shell de gerenciamento do SharePoint Online](https://www.microsoft.com/download/details.aspx?id=35588), caso ainda não tenha feito isso.</span><span class="sxs-lookup"><span data-stu-id="de484-239">Download and install the [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588), if you haven't already.</span></span> <span data-ttu-id="de484-240">Ele contém os cmdlets necessários para mover arquivos.</span><span class="sxs-lookup"><span data-stu-id="de484-240">It contains the cmdlets you need to move files.</span></span>  

<span data-ttu-id="de484-241">Use o cmdlet [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) para se conectar ao site de equipe do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="de484-241">Use the [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) cmdlet to connect to the SharePoint Online team site.</span></span>

```
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

<span data-ttu-id="de484-242">Para cada arquivo que você deseja mover do StaffHub para o Microsoft Teams, use o cmdlet [move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) para mover o arquivo.</span><span class="sxs-lookup"><span data-stu-id="de484-242">For each file that you want to move from StaffHub to Teams, use the [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) cmdlet to move the file.</span></span>

```
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

<span data-ttu-id="de484-243">Para mover vários arquivos, execute um loop sobre os arquivos e execute o segundo comando no loop.</span><span class="sxs-lookup"><span data-stu-id="de484-243">To move multiple files, loop over the files and run the second command on the loop.</span></span> <span data-ttu-id="de484-244">Você não precisa repetir o primeiro comando se a sessão permanecer ativa.</span><span class="sxs-lookup"><span data-stu-id="de484-244">You don't need to repeat the first command if the session remains active.</span></span>

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a><span data-ttu-id="de484-245">Vá além do seu piloto e mova todas as equipes do StaffHub</span><span class="sxs-lookup"><span data-stu-id="de484-245">Go beyond your pilot and move all StaffHub teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="de484-246">Aumentar a conscientização</span><span class="sxs-lookup"><span data-stu-id="de484-246">Raise awareness</span></span>

<span data-ttu-id="de484-247">Quando você estiver pronto para ir além de suas equipes piloto e mover as equipes do StaffHub da sua organização para o Microsoft Teams, é importante primeiro comunicar a alteração em toda a sua organização.</span><span class="sxs-lookup"><span data-stu-id="de484-247">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="de484-248">Espalhe a palavra sobre turnos e a transição para o Microsoft Teams para aumentar a conscientização, gerar entusiasmo e impulsionar a adoção.</span><span class="sxs-lookup"><span data-stu-id="de484-248">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams"></a><span data-ttu-id="de484-249">Mover suas equipes do StaffHub</span><span class="sxs-lookup"><span data-stu-id="de484-249">Move your StaffHub teams</span></span>

<span data-ttu-id="de484-250">Use estas etapas para mover as equipes do StaffHub em massa.</span><span class="sxs-lookup"><span data-stu-id="de484-250">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="de484-251">Você pode optar por mover todas as equipes do StaffHub da sua organização ou mover equipes específicas do StaffHub.</span><span class="sxs-lookup"><span data-stu-id="de484-251">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="de484-252">Se você quiser mover um StaffHub Teams, um por vez, consulte [mover uma equipe do StaffHub](#move-a-staffhub-team).</span><span class="sxs-lookup"><span data-stu-id="de484-252">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team).</span></span>

#### <a name="move-all-staffhub-teams"></a><span data-ttu-id="de484-253">Mover todas as equipes do StaffHub</span><span class="sxs-lookup"><span data-stu-id="de484-253">Move all StaffHub teams</span></span>

<span data-ttu-id="de484-254">Execute o seguinte para obter uma lista de todas as equipes do StaffHub em sua organização.</span><span class="sxs-lookup"><span data-stu-id="de484-254">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```
$StaffHubTeams = Get-StaffHubTeamsForTenant
$StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq ‘StaffHub’ }
```

<span data-ttu-id="de484-255">Em seguida, execute o seguinte para mover todas as equipes.</span><span class="sxs-lookup"><span data-stu-id="de484-255">Then, run the following to move all teams.</span></span>

```
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

<span data-ttu-id="de484-256">Veja um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="de484-256">Here's an example of the response.</span></span>

<span data-ttu-id="de484-257">Para todas as equipes que já foram movidas para o Microsoft Teams ou já existirem no Teams, o jobId será "nulo" porque um trabalho não precisará ser enviado para mover a equipe.</span><span class="sxs-lookup"><span data-stu-id="de484-257">For any team that was already moved to Teams or already exists in Teams, the jobId will be "null" as a job doesn't need to be submitted to move that team.</span></span>

```
jobId                                      teamId                                      teamAlreadyInMicrosofteams  
----------------------------------------   -----------------------------------------   --------------------------         
null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a><span data-ttu-id="de484-258">Mover equipes específicas do StaffHub</span><span class="sxs-lookup"><span data-stu-id="de484-258">Move specific StaffHub teams</span></span>

<span data-ttu-id="de484-259">Execute o seguinte para obter uma lista de todas as IDs de equipe do StaffHub em sua organização.</span><span class="sxs-lookup"><span data-stu-id="de484-259">Run the following to get a list of all StaffHub team Ids in your organization.</span></span>

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="de484-260">Nos resultados retornados pelo `Get-StaffHubteamsForTenant` cmdlet executado anteriormente, selecione as IDs de equipe que você deseja mover e, em seguida, adicione-as a um arquivo CSV (valores separados por vírgula).</span><span class="sxs-lookup"><span data-stu-id="de484-260">In the results returned by the `Get-StaffHubteamsForTenant` cmdlet you ran earlier, select the Team Ids you want to move, and then add them to a comma-separated values (CSV) file.</span></span>

<span data-ttu-id="de484-261">Aqui está um exemplo de como o arquivo CSV deve ser formatado.</span><span class="sxs-lookup"><span data-stu-id="de484-261">Here's an example of how the CSV file should be formatted.</span></span>

|<span data-ttu-id="de484-262">%</span><span class="sxs-lookup"><span data-stu-id="de484-262">Id</span></span>  |
|---------|
|<span data-ttu-id="de484-263">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="de484-263">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="de484-264">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="de484-264">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="de484-265">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="de484-265">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="de484-266">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="de484-266">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="de484-267">Depois de criar o arquivo CSV, execute o seguinte para mover as equipes que você especificou no arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="de484-267">After you create the CSV file, run the following to move the teams you specified in the CSV file.</span></span>

```
$StaffHubTeams = Import-Csv .\teams.csv
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a><span data-ttu-id="de484-268">Confirme se suas equipes do StaffHub foram movidas para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="de484-268">Confirm that your StaffHub teams have moved to Teams</span></span>

<span data-ttu-id="de484-269">Execute o seguinte para obter uma lista de todas as equipes em turnos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="de484-269">Run the following to get a list of all teams in Shifts in your organization.</span></span> 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a><span data-ttu-id="de484-270">Mover arquivos de suas equipes do StaffHub para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="de484-270">Move files from your StaffHub teams to Teams</span></span>

<span data-ttu-id="de484-271">Se as equipes do StaffHub que você moveu contiverem arquivos que você também deseja mover para o Microsoft Teams, consulte [mover arquivos de uma equipe do StaffHub para o Microsoft Teams](#move-files-from-a-staffhub-team-to-teams).</span><span class="sxs-lookup"><span data-stu-id="de484-271">If the StaffHub teams that you moved contain files that you also want to move to Teams, see [Move files from a StaffHub team to Teams](#move-files-from-a-staffhub-team-to-teams).</span></span>

## <a name="monitor-teams-usage"></a><span data-ttu-id="de484-272">Monitorar o uso do teams</span><span class="sxs-lookup"><span data-stu-id="de484-272">Monitor Teams usage</span></span>

<span data-ttu-id="de484-273">Os relatórios de uso podem ajudá-lo a entender melhor os padrões de uso e oferecer ideias sobre onde priorizar os esforços de treinamento e comunicação em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="de484-273">Usage reports can help you better understand usage patterns and give you insights on where to prioritize training and communication efforts across your organization.</span></span> <span data-ttu-id="de484-274">Você pode executar relatórios que mostram o uso geral das equipes, os tipos de atividades realizadas pelos usuários no Teams, como os usuários se conectam ao Teams e muito mais.</span><span class="sxs-lookup"><span data-stu-id="de484-274">You can run reports that show you overall Teams usage, the types of activities that users perform in Teams, how users connect to Teams, and more.</span></span> <span data-ttu-id="de484-275">Para obter mais informações, consulte relatórios [do Microsoft Teams no centro de administração do Microsoft Teams](../../teams-analytics-and-reports/teams-reporting-reference.md) e [relatórios de atividade do Microsoft Teams no centro de administração do Microsoft 365](../../teams-activity-reports.md).</span><span class="sxs-lookup"><span data-stu-id="de484-275">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="de484-276">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="de484-276">Troubleshooting</span></span>

<span data-ttu-id="de484-277">**Como obter mais informações sobre erros de falha**</span><span class="sxs-lookup"><span data-stu-id="de484-277">**How to get more information about failure errors**</span></span>

<span data-ttu-id="de484-278">Execute o seguinte para obter mais informações sobre erros de "falha" que ocorrem quando você tenta mover uma equipe:</span><span class="sxs-lookup"><span data-stu-id="de484-278">Run the following to get more information about "Failure" errors that occur when you try to move a team:</span></span>

```
Move-StaffHubTeam -TeamId <TeamId>
$res = Get-TeamMigrationJobStatus -JobId <JobId>
$res.Status
```

<span data-ttu-id="de484-279">Você verá um dos seguintes status: êxito, falha, InProgress, enfileirado.</span><span class="sxs-lookup"><span data-stu-id="de484-279">You'll see one of the following statuses returned: Success, Failure, InProgress, Queued.</span></span>

<span data-ttu-id="de484-280">Se "falha" for retornado, execute o seguinte procedimento para obter mais informações sobre o erro:</span><span class="sxs-lookup"><span data-stu-id="de484-280">If "Failure" is returned, run the following to get more information about the error:</span></span>

```
$res.Result.Error.Innererror
```

<span data-ttu-id="de484-281">**Quando você tenta mover uma equipe do StaffHub, o status é mostrado como "falha" e você recebe uma mensagem de erro "falha ao recuperar categorias de SKU aplicáveis para o usuário"**</span><span class="sxs-lookup"><span data-stu-id="de484-281">**When you try to move a StaffHub team, the status shows as "Failure" and you receive a "Failed to retrieve applicable SKU categories for the user" error message**</span></span>

<span data-ttu-id="de484-282">Isso pode ocorrer se um ou mais membros da equipe não tiverem uma licença do teams.</span><span class="sxs-lookup"><span data-stu-id="de484-282">This can occur if one or more team members don't have a Teams license.</span></span> <span data-ttu-id="de484-283">Vá para portal.office.com, localize o grupo e, em seguida, confirme que os membros do grupo recebem uma licença do teams.</span><span class="sxs-lookup"><span data-stu-id="de484-283">Go to portal.office.com, find the group, and then confirm that group members are assigned a Teams license.</span></span>

<span data-ttu-id="de484-284">**Quando você tenta mover uma equipe do StaffHub, o status é mostrado como "falha" e você recebe uma mensagem de erro "proprietário da equipe não encontrado"**</span><span class="sxs-lookup"><span data-stu-id="de484-284">**When you try to move a StaffHub team, the status shows as "Failure" and you receive a "Team owner not found" error message**</span></span>

<span data-ttu-id="de484-285">Isso pode ocorrer se o grupo associado à equipe do StaffHub não tiver um proprietário da equipe.</span><span class="sxs-lookup"><span data-stu-id="de484-285">This can occur if the group that's associated with the StaffHub team doesn't have a team owner.</span></span> <span data-ttu-id="de484-286">Vá para portal.office.com, localize o grupo e adicione um ou mais proprietários ao grupo.</span><span class="sxs-lookup"><span data-stu-id="de484-286">Go to portal.office.com, find the group, and then add one or more owners to the group.</span></span>

<span data-ttu-id="de484-287">**Ao tentar mover arquivos do StaffHub para o Microsoft Teams, você recebe a mensagem de erro "permissão negada".**</span><span class="sxs-lookup"><span data-stu-id="de484-287">**When you try to move files from StaffHub to Teams, you get a "Permission denied" error message.**</span></span>

<span data-ttu-id="de484-288">Isso pode ocorrer se você estiver tentando mover arquivos em um grupo particular do Office 365 do qual você não é membro.</span><span class="sxs-lookup"><span data-stu-id="de484-288">This may occur if you're trying to move files in a private Office 365 group that you're not a member of.</span></span> <span data-ttu-id="de484-289">Se esse for o caso, use o cmdlet [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) para se adicionar à equipe do StaffHub e, em seguida, mova os arquivos.</span><span class="sxs-lookup"><span data-stu-id="de484-289">If this is the case, use the [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) cmdlet to add yourself to the StaffHub team, and then move the files.</span></span> <span data-ttu-id="de484-290">Depois de mover os arquivos, use o cmdlet [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) para remover-se da equipe.</span><span class="sxs-lookup"><span data-stu-id="de484-290">After you move the files, use the [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) cmdlet to remove yourself from the team.</span></span> 

<span data-ttu-id="de484-291">**Ao tentar mover arquivos do StaffHub para o Microsoft Teams, você recebe um erro que diz que a pasta geral não existe.**</span><span class="sxs-lookup"><span data-stu-id="de484-291">**When you try to move files from StaffHub to Teams, you get an error that says the General folder doesn't exist.**</span></span>

<span data-ttu-id="de484-292">Execute o seguinte comando para adicionar a pasta geral ao SharePoint e tente novamente:</span><span class="sxs-lookup"><span data-stu-id="de484-292">Run the following command to add the General folder to SharePoint, and then try again:</span></span>

  ```
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a><span data-ttu-id="de484-293">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="de484-293">Related topics</span></span>
- [<span data-ttu-id="de484-294">Como implementar o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="de484-294">How to roll out Microsoft Teams</span></span>](../../How-to-roll-out-teams.md)
- [<span data-ttu-id="de484-295">O Microsoft StaffHub será desativado</span><span class="sxs-lookup"><span data-stu-id="de484-295">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="de484-296">Gerencie o aplicativo Turnos para sua organização no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="de484-296">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="de484-297">Referência do PowerShell do StaffHub</span><span class="sxs-lookup"><span data-stu-id="de484-297">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
