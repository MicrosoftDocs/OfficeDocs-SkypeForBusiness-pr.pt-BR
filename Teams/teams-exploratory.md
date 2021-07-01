---
title: Gerenciar a experiência do Microsoft Teams Exploratory
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: Admin
ms.reviewer: baluc
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: Usuários do Microsoft 365 ou do Office 365 que não possuem licenças para o Microsoft Teams podem começar com uma licença do Teams Exploratory.
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8803219c93a66d7094ce6ca1aa635f1fbff8580e
ms.sourcegitcommit: b39bd1de0219a9e3a3b0c97fc485c9578ddb643c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2021
ms.locfileid: "53230548"
---
# <a name="manage-the-microsoft-teams-exploratory-license"></a><span data-ttu-id="c50a4-103">Gerenciar a licença do Microsoft Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="c50a4-103">Manage the Microsoft Teams Exploratory license</span></span>

<span data-ttu-id="c50a4-p101">A experiência do Microsoft Teams Exploratory permite que os usuários em sua organização que têm o Azure Active Directory (Azure AD) e não estão licenciados para o Teams iniciem uma experiência exploratória do Teams. Os administradores podem ativar ou desativar esse recurso para usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="c50a4-p101">The Microsoft Teams Exploratory experience lets users in your organization who have Azure Active Directory (Azure AD) and aren't licensed for Teams initiate an exploratory experience of Teams. Admins can switch this feature on or off for users in their organization.</span></span>

## <a name="whats-in-the-teams-exploratory-experience"></a><span data-ttu-id="c50a4-106">O que há na experiência do Teams Exploratory?</span><span class="sxs-lookup"><span data-stu-id="c50a4-106">What's in the Teams Exploratory experience</span></span>

<span data-ttu-id="c50a4-107">Os planos de serviço que um administrador exibirá como parte da experiência de exploratório da equipe são:</span><span class="sxs-lookup"><span data-stu-id="c50a4-107">The service plans that an admin will see as part of the Teams Exploratory experience are:</span></span>

- <span data-ttu-id="c50a4-108">Exchange Online (Plano 1)</span><span class="sxs-lookup"><span data-stu-id="c50a4-108">Exchange Online (Plan 1)</span></span>
- <span data-ttu-id="c50a4-109">Flow para o Microsoft 365 ou para o Office 365</span><span class="sxs-lookup"><span data-stu-id="c50a4-109">Flow for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="c50a4-110">Insight por MyAnalytics</span><span class="sxs-lookup"><span data-stu-id="c50a4-110">Insights by MyAnalytics</span></span>
- <span data-ttu-id="c50a4-111">Microsoft Forms (Plano E1)</span><span class="sxs-lookup"><span data-stu-id="c50a4-111">Microsoft Forms (Plan E1)</span></span>
- <span data-ttu-id="c50a4-112">Microsoft Planner</span><span class="sxs-lookup"><span data-stu-id="c50a4-112">Microsoft Planner</span></span>
- <span data-ttu-id="c50a4-113">Pesquisa da Microsoft</span><span class="sxs-lookup"><span data-stu-id="c50a4-113">Microsoft Search</span></span>
- <span data-ttu-id="c50a4-114">Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="c50a4-114">Microsoft StaffHub</span></span>
- <span data-ttu-id="c50a4-115">Microsoft Stream para Microsoft 365 e Office 365 E1 SKUs<sup>1</1></span><span class="sxs-lookup"><span data-stu-id="c50a4-115">Microsoft Stream for Microsoft 365 and Office 365 E1 SKUs <sup>1</1></span></span>
- <span data-ttu-id="c50a4-116">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c50a4-116">Microsoft Teams</span></span>
- <span data-ttu-id="c50a4-117">Gerenciamento de Dispositivo Móvel para o Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="c50a4-117">Mobile Device Management for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="c50a4-118">Aplicativos do Office Mobile para Office 365</span><span class="sxs-lookup"><span data-stu-id="c50a4-118">Office Mobile Apps for Office 365</span></span>
- <span data-ttu-id="c50a4-119">Office Online</span><span class="sxs-lookup"><span data-stu-id="c50a4-119">Office Online</span></span>
- <span data-ttu-id="c50a4-120">PowerApps para o Microsoft 365 ou para o Office 365</span><span class="sxs-lookup"><span data-stu-id="c50a4-120">PowerApps for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="c50a4-121">SharePoint Online (Plano 1)</span><span class="sxs-lookup"><span data-stu-id="c50a4-121">SharePoint Online (Plan 1)</span></span>
- <span data-ttu-id="c50a4-122">Sway</span><span class="sxs-lookup"><span data-stu-id="c50a4-122">Sway</span></span>
- <span data-ttu-id="c50a4-123">To-Do (Plano 1)</span><span class="sxs-lookup"><span data-stu-id="c50a4-123">To-Do (Plan 1)</span></span>
- <span data-ttu-id="c50a4-124">Quadro de Comunicações (Plano 1)</span><span class="sxs-lookup"><span data-stu-id="c50a4-124">Whiteboard (Plan 1)</span></span>
- <span data-ttu-id="c50a4-125">Yammer Enterprise</span><span class="sxs-lookup"><span data-stu-id="c50a4-125">Yammer Enterprise</span></span>

  <span data-ttu-id="c50a4-126"><sup>1</sup> A mudança do Microsoft Stream para o [OneDrive for Business e o Microsoft Office SharePoint Online para gravações de reunião](tmr-meeting-recording-change.md) será uma abordagem em fases.</span><span class="sxs-lookup"><span data-stu-id="c50a4-126"><sup>1</sup> The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach.</span></span> <span data-ttu-id="c50a4-127">No lançamento, você poderá optar por essa experiência.</span><span class="sxs-lookup"><span data-stu-id="c50a4-127">At launch, you'll be able to opt in to this experience.</span></span> <span data-ttu-id="c50a4-128">Em novembro, você terá que cancelar se quiser continuar usando o Stream.</span><span class="sxs-lookup"><span data-stu-id="c50a4-128">In November, you'll have to opt out if you want to continue using Stream.</span></span> <span data-ttu-id="c50a4-129">Em algum momento no início de 2021, exigiremos que todos os clientes usem o OneDrive for Business e o Microsoft Office SharePoint Online para novas gravações de reuniões.</span><span class="sxs-lookup"><span data-stu-id="c50a4-129">Sometime in early 2021, we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

## <a name="whos-eligible"></a><span data-ttu-id="c50a4-130">Quem é elegível</span><span class="sxs-lookup"><span data-stu-id="c50a4-130">Who's eligible</span></span>

<span data-ttu-id="c50a4-131">Os usuários atendem aos critérios para uma experiência Exploratória de Teams se:</span><span class="sxs-lookup"><span data-stu-id="c50a4-131">Users fit the criteria for a Teams Exploratory experience if they:</span></span>

- <span data-ttu-id="c50a4-132">Tem um endereço de email de domínio gerenciado do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c50a4-132">Have a managed Azure AD domain email address.</span></span>
- <span data-ttu-id="c50a4-133">Pertence a um locatário com uma assinatura paga.</span><span class="sxs-lookup"><span data-stu-id="c50a4-133">Belong to a tenant with a paid subscription.</span></span>
- <span data-ttu-id="c50a4-134">Não tenha uma licença do Teams ativa.</span><span class="sxs-lookup"><span data-stu-id="c50a4-134">Do not have an active Teams license.</span></span>
- <span data-ttu-id="c50a4-135">Não estão em um locatário onde uma política de atribuição de licença foi criada.</span><span class="sxs-lookup"><span data-stu-id="c50a4-135">Are not in a tenant where a license assignment policy was created.</span></span>

<span data-ttu-id="c50a4-136">Habilite os usuários para se inscreverem em aplicativos e versões de avaliação (no centro de administração do Office 365).</span><span class="sxs-lookup"><span data-stu-id="c50a4-136">Users must be enabled to sign up for apps and trials (in the Microsoft 365 admin center).</span></span> <span data-ttu-id="c50a4-137">Para obter mais informações, confira [Gerenciar a experiência do Teams Exploratory](#manage-the-teams-exploratory-experience), mais adiante neste artigo.</span><span class="sxs-lookup"><span data-stu-id="c50a4-137">For more information, see [Manage the Teams Exploratory experience](#manage-the-teams-exploratory-experience), later in this article.</span></span>

## <a name="who-isnt-eligible"></a><span data-ttu-id="c50a4-138">Quem não está qualificado</span><span class="sxs-lookup"><span data-stu-id="c50a4-138">Who isn't eligible</span></span>

<span data-ttu-id="c50a4-139">Os usuários não se enquadram nos critérios se:</span><span class="sxs-lookup"><span data-stu-id="c50a4-139">Users don't fit the criteria if they:</span></span>

- <span data-ttu-id="c50a4-140">Atualmente ou anteriormente o Teams era disponibilizado com uma licença paga, não paga ou licença de avaliação </span><span class="sxs-lookup"><span data-stu-id="c50a4-140">Currently or previously had Teams from a paid, unpaid, or trial license</span></span>
- <span data-ttu-id="c50a4-141">Estão em um locatário que usou/recebeu pelo menos uma oferta especial de COVID.</span><span class="sxs-lookup"><span data-stu-id="c50a4-141">Are in a tenant that used/received at least one special COVID offer.</span></span>

<span data-ttu-id="c50a4-142">Sua organização não está qualificada para esta oferta se você for um Cliente Parceiro de Agregação ou se for um cliente do GCC, GCC High, DoD ou EDU.</span><span class="sxs-lookup"><span data-stu-id="c50a4-142">Your organization isn't eligible for this offer if you're a Syndication Partner Customer or a GCC, GCC High, DoD, or EDU customer.</span></span>

## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a><span data-ttu-id="c50a4-143">Como os usuários se inscrevem na experiência do Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="c50a4-143">How users sign up for the Teams Exploratory experience</span></span>

<span data-ttu-id="c50a4-144">Os usuários qualificados podem se inscrever para a Experiência do Teams Exploratory entrando no Teams a partir da área de trabalho ou da web ([teams.microsoft.com](https://teams.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="c50a4-144">Eligible users can sign up for the Teams Exploratory experience by signing in to Teams from the desktop or web ([teams.microsoft.com](https://teams.microsoft.com)).</span></span> <span data-ttu-id="c50a4-145">No momento, a ativação do Exploratory por meio do dispositivo móvel não é compatível.</span><span class="sxs-lookup"><span data-stu-id="c50a4-145">At this time, enabling Exploratory through mobile is not supported.</span></span> <span data-ttu-id="c50a4-146">Ao se inscreverem, essa licença será atribuída automaticamente a eles e o administrador do locatário receberá uma notificação por email na primeira vez que alguém em sua organização iniciar a experiência do Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="c50a4-146">When they sign up, they'll be assigned this license automatically and the tenant admin will receive an email notification the first time someone in your org starts the Teams Exploratory experience.</span></span>

## <a name="manage-the-teams-exploratory-experience"></a><span data-ttu-id="c50a4-147">Gerenciar a experiência do Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="c50a4-147">Manage the Teams Exploratory experience</span></span>

<span data-ttu-id="c50a4-148">A experiência Exploratória do Teams deve ser iniciada por usuários finais individuais e você não pode iniciar esta oferta em nome de funcionários usuários finais.</span><span class="sxs-lookup"><span data-stu-id="c50a4-148">The Teams Exploratory experience is meant to be initiated by individual end users, and you can't initiate this offer on behalf of end-user employees.</span></span>

<span data-ttu-id="c50a4-149">A experiência Exploratória do Teams vem com uma licença do Exchange Online, mas não será atribuída ao usuário até que o administrador a atribua.</span><span class="sxs-lookup"><span data-stu-id="c50a4-149">The Teams Exploratory experience comes with an Exchange Online license, but it won't be assigned to the user until the admin assigns it.</span></span> <span data-ttu-id="c50a4-150">Se o usuário ainda não tiver uma licença do Exchange e o administrador ainda não tiver atribuído a licença do Exchange Online, o usuário não poderá agendar reuniões no Teams e pode estar perdendo outras funcionalidades do Teams.</span><span class="sxs-lookup"><span data-stu-id="c50a4-150">If the user doesn't have an Exchange license already, and the admin has yet to assign the Exchange Online license, the user won't be able to schedule meetings in Teams and might be missing other Teams functionality.</span></span>

<span data-ttu-id="c50a4-151">Os administradores podem desabilitar a capacidade para que os usuários finais executem a experiência do Teams Exploratory em sua organização, usando a opção **Aplicativos e serviços de avaliação**.</span><span class="sxs-lookup"><span data-stu-id="c50a4-151">Admins can disable the ability for end users to run the Teams Exploratory experience within their organization by using the **Trial apps and services** switch.</span></span>

### <a name="prevent-users-from-installing-trial-apps-and-services"></a><span data-ttu-id="c50a4-152">Impedir que os usuários instalem serviços e aplicativos de avaliação</span><span class="sxs-lookup"><span data-stu-id="c50a4-152">Prevent users from installing trial apps and services</span></span>

<span data-ttu-id="c50a4-153">Você pode desativar a capacidade de um usuário de instalar aplicativos e serviços de avaliação, o que impediria o usuário de executar a experiência Exploratória do Teams.</span><span class="sxs-lookup"><span data-stu-id="c50a4-153">You can turn off a user's ability to install trial apps and services, which would prevent the user from running the Teams Exploratory experience.</span></span>

1. <span data-ttu-id="c50a4-154">Do Centro de administração do Microsoft 365, vá até **Configurações** > **Configurações da Organização**, selecione **Serviços** e, em seguida, selecione **Aplicativos e serviços de propriedade do usuário**.</span><span class="sxs-lookup"><span data-stu-id="c50a4-154">From the Microsoft 365 admin center, go to **Settings** > **Org settings**, select **Services**, and then select **User owned apps and services**.</span></span>

    ![a página de Serviços no centro de administração](media/iw-trial-services.png)

2. <span data-ttu-id="c50a4-156">Desmarque a caixa de seleção **Permitir que os usuários instalem aplicativos e serviços de avaliação**.</span><span class="sxs-lookup"><span data-stu-id="c50a4-156">Clear the check mark from **Let users install trial apps and services**.</span></span>

    ![a página de aplicativos e serviços de propriedade do Usuário no centro de administração](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > <span data-ttu-id="c50a4-158">Se a sua organização não estiver qualificada para a experiência do Teams Exploratory, você não verá a opção **Permitir que os usuários instalem aplicativos e serviços de avaliação**.</span><span class="sxs-lookup"><span data-stu-id="c50a4-158">If your organization is ineligible for the Teams Exploratory experience, you won't see the **Let users install trial apps and services** option.</span></span>

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a><span data-ttu-id="c50a4-159">Gerenciar a disponibilidade de um usuário com uma licença que inclua o Teams</span><span class="sxs-lookup"><span data-stu-id="c50a4-159">Manage availability for a user with a license that includes Teams</span></span>

<span data-ttu-id="c50a4-160">Um usuário que recebe uma licença que inclui o Teams não está qualificado para a experiência do Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="c50a4-160">A user who is assigned a license that includes Teams isn't eligible for the Teams Exploratory experience.</span></span> <span data-ttu-id="c50a4-161">Quando o plano de serviço do Teams está ativado, o usuário pode entrar e usar o Teams.</span><span class="sxs-lookup"><span data-stu-id="c50a4-161">When the Teams service plan is turned on, the user can sign in and use Teams.</span></span> <span data-ttu-id="c50a4-162">Se o plano do serviço estiver desabilitado, o usuário não poderá entrar e a experiência do Teams Exploratory não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="c50a4-162">If the service plan is disabled, the user can't sign in and the Teams Exploratory experience isn't available.</span></span> <span data-ttu-id="c50a4-163">Você deve ter privilégios de administrador.</span><span class="sxs-lookup"><span data-stu-id="c50a4-163">You must have admin privileges.</span></span>

<span data-ttu-id="c50a4-164">Para desativar o acesso ao Teams:</span><span class="sxs-lookup"><span data-stu-id="c50a4-164">To turn off access to Teams:</span></span>

1. <span data-ttu-id="c50a4-165">No Centro de administração do Microsoft 365, selecione **Usuários** > **Usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="c50a4-165">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="c50a4-166">Marque a caixa ao lado do nome do usuário.</span><span class="sxs-lookup"><span data-stu-id="c50a4-166">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="c50a4-167">Na linha **Licenças de produto**, escolha **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c50a4-167">In the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="c50a4-168">No painel **​​Licenças do produto**, alterne a chave para **Desligado**.</span><span class="sxs-lookup"><span data-stu-id="c50a4-168">In the **Product licenses** pane, switch the toggle to **Off**.</span></span>

    ![a página de licenças do Produto no centro de administração.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a><span data-ttu-id="c50a4-170">Gerenciar a disponibilidade do Teams para os usuários que já estão usando a experiência do Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="c50a4-170">Manage Teams availability for users who are already using the Teams Exploratory experience</span></span>

<span data-ttu-id="c50a4-p107">Se um usuário estiver executando a experiência do Teams Exploratory, você poderá desativá-la removendo a licença ou o plano de serviço. Você deve ter privilégios de administrador.</span><span class="sxs-lookup"><span data-stu-id="c50a4-p107">If a user is running the Teams Exploratory experience, you can turn it off by removing the license or service plan. You must have admin privileges.</span></span>

<span data-ttu-id="c50a4-173">Para desativar a licença de experiência do Teams Exploratory:</span><span class="sxs-lookup"><span data-stu-id="c50a4-173">To turn off the Teams Exploratory experience license:</span></span>

1. <span data-ttu-id="c50a4-174">No Centro de administração do Microsoft 365, selecione **Usuários** > **Usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="c50a4-174">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="c50a4-175">Marque a caixa ao lado do nome do usuário.</span><span class="sxs-lookup"><span data-stu-id="c50a4-175">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="c50a4-176">Na linha **Licenças de produto**, escolha **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c50a4-176">In the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="c50a4-177">No painel **Licenças de produto**, alterne a opção desta licença exploratória para **Desativar**.</span><span class="sxs-lookup"><span data-stu-id="c50a4-177">In the **Product licenses** pane, switch the toggle for this exploratory license to **Off**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c50a4-178">A opção de alternância do Teams Exploratory será exibida após o primeiro usuário da organização iniciar a experiência do Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="c50a4-178">The Teams Exploratory toggle switch will appear after the first user in the organization launches the Teams Exploratory experience.</span></span>

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a><span data-ttu-id="c50a4-179">Gerenciar o Teams para usuários que possuem a licença do Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="c50a4-179">Manage Teams for users who have the Teams Exploratory license</span></span>

<span data-ttu-id="c50a4-180">Você pode gerenciar usuários que possuem a licença do Teams Exploratory, assim como gerencia usuários que possuem uma licença paga regular.</span><span class="sxs-lookup"><span data-stu-id="c50a4-180">You can manage users who have the Teams Exploratory license just like you manage users who have a regular paid license.</span></span> <span data-ttu-id="c50a4-181">Para mais informações, confira [Gerenciar as configurações do Teams da sua organização](enable-features-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="c50a4-181">For more information, see [Manage Teams settings for your organization](enable-features-office-365.md).</span></span>

### <a name="upgrade-users-from-teams-exploratory"></a><span data-ttu-id="c50a4-182">Atualizar usuários do Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="c50a4-182">Upgrade users from Teams Exploratory</span></span>

<span data-ttu-id="c50a4-183">Você deve ter privilégios de administrador para atualizar usuários do Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="c50a4-183">You must have admin privileges to upgrade users from Teams Exploratory.</span></span> <span data-ttu-id="c50a4-184">Para obter mais informações, confira [Atualizar usuários da versão de avaliação do Teams Exploratory](upgrade-from-teams-exploratory.md).</span><span class="sxs-lookup"><span data-stu-id="c50a4-184">For more information see [Upgrade users from the Teams Exploratory trial](upgrade-from-teams-exploratory.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c50a4-185">Se a licença do Teams Exploratory terminar e um usuário não for atualizado imediatamente para uma assinatura que inclui o Teams, ele perderá o acesso ao Teams após um período de carência de 30 dias.</span><span class="sxs-lookup"><span data-stu-id="c50a4-185">If the Teams Exploratory license ends and a user isn't immediately upgraded to a subscription that includes Teams, they lose access to Teams after a 30-days grace period.</span></span> <span data-ttu-id="c50a4-186">Após mais 30 dias depois da carência, os dados serão excluídos.</span><span class="sxs-lookup"><span data-stu-id="c50a4-186">Another 30 days after which, the data is deleted.</span></span> <span data-ttu-id="c50a4-187">O usuário ainda existe no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c50a4-187">The user still exists in Azure Active Directory.</span></span> <span data-ttu-id="c50a4-188">Assim que uma nova licença for atribuída ao usuário para habilitar a funcionalidade do Teams novamente, todo o conteúdo ainda existirá se o usuário for adicionado dentro do período de tempo de tolerância.</span><span class="sxs-lookup"><span data-stu-id="c50a4-188">Once a new license is assigned to the user to enable Teams functionality again, all content will still exist if the user is added within the grace period time frame.</span></span>

### <a name="remove-a-teams-exploratory-license"></a><span data-ttu-id="c50a4-189">Remover uma licença do Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="c50a4-189">Remove a Teams Exploratory license</span></span>

- <span data-ttu-id="c50a4-190">Se você deseja remover essa licença por meio do PowerShell, confira: [Remover licenças de contas de usuário com o Office 365 PowerShell](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="c50a4-190">If you would like to remove this license by using PowerShell, see: [Remove licenses from user accounts with Office 365 PowerShell](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span></span>

- <span data-ttu-id="c50a4-191">Se você quiser remover essa licença por meio do portal de administração do, confira: [Excluir um usuário da sua organização](/microsoft-365/admin/add-users/delete-a-user)</span><span class="sxs-lookup"><span data-stu-id="c50a4-191">If you would like to remove this license through the admin portal, see: [Delete a user from your organization](/microsoft-365/admin/add-users/delete-a-user)</span></span>

## <a name="what-is-the-data-retention-policy"></a><span data-ttu-id="c50a4-192">Qual é a política de retenção de dados</span><span class="sxs-lookup"><span data-stu-id="c50a4-192">What is the data retention policy</span></span>

<span data-ttu-id="c50a4-193">Confira as [Informações de assinatura do Microsoft 365](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="c50a4-193">See [Microsoft 365 subscription information](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).</span></span>

## <a name="how-long-does-the-teams-exploratory-experience-last"></a><span data-ttu-id="c50a4-194">Quanto tempo dura a experiência do Teams Exploratory?</span><span class="sxs-lookup"><span data-stu-id="c50a4-194">How long does the Teams Exploratory experience last</span></span>

<span data-ttu-id="c50a4-195">No início de 2021, o Teams Exploratory está disponível como uma assinatura de 12 meses (a partir da inscrição inicial do usuário) para todos os novos clientes.</span><span class="sxs-lookup"><span data-stu-id="c50a4-195">As of early 2021, Teams Exploratory is available as a 12 month subscription (from initial user sign-up) for all new customers.</span></span> <span data-ttu-id="c50a4-196">A nova assinatura do Teams Exploratory inicia quando o primeiro usuário de uma organização se inscreve no Teams Exploratory e expira após 12 meses.</span><span class="sxs-lookup"><span data-stu-id="c50a4-196">The new Teams Exploratory subscription starts when the first user in an organization signs-up for Teams Exploratory and it will expire after 12 months.</span></span> <span data-ttu-id="c50a4-197">A data de expiração se aplicará a todos os usuários no mesmo locatário, pois o prazo de 12 meses começa na data de inscrição do primeiro usuário.</span><span class="sxs-lookup"><span data-stu-id="c50a4-197">The expiry date will apply to all users in the same tenant as the 12-month term begins on the first user's sign-up date.</span></span>

> [!NOTE]
> <span data-ttu-id="c50a4-198">A data de término da experiência é configurada no nível da organização, o que significa que se aplicará a todos os usuários da mesma organização.</span><span class="sxs-lookup"><span data-stu-id="c50a4-198">The end date for the experience is configured at an organization level, meaning it will apply to all users in the same organization.</span></span> <span data-ttu-id="c50a4-199">Por exemplo, o usuário 1 se inscreveu para a assinatura em 1º de janeiro de 2021.</span><span class="sxs-lookup"><span data-stu-id="c50a4-199">For example, User 1 signs up for the subscription on January 1, 2021.</span></span> <span data-ttu-id="c50a4-200">Isso inicia a data de término da assinatura em 31 de dezembro de 2021.</span><span class="sxs-lookup"><span data-stu-id="c50a4-200">This initiates a subscription end-date of December 31, 2021.</span></span> <span data-ttu-id="c50a4-201">Outro usuário, o Usuário 2, se inscreveu para a assinatura em 1º de outubro de 2021.</span><span class="sxs-lookup"><span data-stu-id="c50a4-201">Another user, User 2, signs up for the subscription on October 1, 2021.</span></span> <span data-ttu-id="c50a4-202">O usuário 2 pode usar o Teams Exploratory por dois meses, já que a data de término será 31 de dezembro de 2021 porque eles estão sob a mesma assinatura da organização do Usuário 1.</span><span class="sxs-lookup"><span data-stu-id="c50a4-202">User 2 can use Teams Exploratory for two months, as their end-date will be December 31, 2021 because they're under the same organization's subscription as User 1.</span></span>

### <a name="what-should-administrators-do-at-the-end-of-the-12-month-teams-exploratory-experience"></a><span data-ttu-id="c50a4-203">O que os administradores devem fazer ao final dos 12 meses do Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="c50a4-203">What should administrators do at the end of the 12 month Teams Exploratory experience</span></span>

<span data-ttu-id="c50a4-204">No final da assinatura de 12 meses, os administradores devem converter todos os usuários do Teams Exploratory para uma licença paga que inclui o Teams.</span><span class="sxs-lookup"><span data-stu-id="c50a4-204">At the end of the 12 month subscription, administrators should convert all Teams Exploratory users to a paid license that includes Teams.</span></span> <span data-ttu-id="c50a4-205">É vital garantir que isso seja concluído antes que a assinatura do Teams Exploratory expire para evitar qualquer interrupção na experiência do usuário.</span><span class="sxs-lookup"><span data-stu-id="c50a4-205">It is vital to ensure this is completed before the Teams Exploratory subscription expires to avoid any disruption to user's experience.</span></span>


> [!NOTE]
> <span data-ttu-id="c50a4-206">Os clientes serão desabilitados e impedidos de iniciar uma nova licença de avaliação do Exploratory por 3 meses após a expiração de sua licença de avaliação do Exploratory anterior.</span><span class="sxs-lookup"><span data-stu-id="c50a4-206">Customers will be disabled and blocked from starting a new Exploratory trial licenses for 3 months past the expiration of their previous Exploratory trial license.</span></span>

<span data-ttu-id="c50a4-207">Para obter mais informações, confira [Atualizar usuários do Teams Exploratory](#upgrade-users-from-teams-exploratory), acima nesse artigo.</span><span class="sxs-lookup"><span data-stu-id="c50a4-207">For more information, see [Upgrade users from Teams Exploratory](#upgrade-users-from-teams-exploratory), above in this article.</span></span>
