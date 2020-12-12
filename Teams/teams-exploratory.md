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
ms.openlocfilehash: df06c03ab37a98c5ea4404d8dbd12703b07ad3ee
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611805"
---
# <a name="manage-the-microsoft-teams-exploratory-license"></a><span data-ttu-id="f6979-103">Gerenciar a licença do Microsoft Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="f6979-103">Manage the Microsoft Teams Exploratory license</span></span>

<span data-ttu-id="f6979-104">A experiência do Microsoft Teams Exploratory permite que os usuários em sua organização que têm o Azure Active Directory (Azure AD) e não estão licenciados para o Teams iniciem uma experiência exploratória do Teams.</span><span class="sxs-lookup"><span data-stu-id="f6979-104">The Microsoft Teams Exploratory experience lets users in your organization who have Azure Active Directory (Azure AD) and aren't licensed for Teams initiate an exploratory experience of Teams.</span></span> <span data-ttu-id="f6979-105">Os administradores podem ativar ou desativar esse recurso para os usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="f6979-105">Admins can switch this feature on or off for users in their organization.</span></span> <span data-ttu-id="f6979-106">O [Microsoft Commercial Cloud Trial](iw-trial-teams.md) anterior agora foi substituído pela experiência do Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="f6979-106">The earlier [Microsoft Commercial Cloud Trial](iw-trial-teams.md) is now replaced by The Teams Exploratory experience.</span></span>

## <a name="whats-in-the-teams-exploratory-experience"></a><span data-ttu-id="f6979-107">O que há na experiência do Teams Exploratory?</span><span class="sxs-lookup"><span data-stu-id="f6979-107">What's in the Teams Exploratory experience</span></span>

<span data-ttu-id="f6979-108">Os planos de serviço que um administrador exibirá como parte da experiência de exploratório da equipe são:</span><span class="sxs-lookup"><span data-stu-id="f6979-108">The service plans that an admin will see as part of the Teams Exploratory experience are:</span></span>

- <span data-ttu-id="f6979-109">Exchange Online (Plano 1)</span><span class="sxs-lookup"><span data-stu-id="f6979-109">Exchange Online (Plan 1)</span></span>
- <span data-ttu-id="f6979-110">Flow para o Microsoft 365 ou para o Office 365</span><span class="sxs-lookup"><span data-stu-id="f6979-110">Flow for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="f6979-111">Insight por MyAnalytics</span><span class="sxs-lookup"><span data-stu-id="f6979-111">Insights by MyAnalytics</span></span>
- <span data-ttu-id="f6979-112">Microsoft Forms (Plano E1)</span><span class="sxs-lookup"><span data-stu-id="f6979-112">Microsoft Forms (Plan E1)</span></span>
- <span data-ttu-id="f6979-113">Microsoft Planner</span><span class="sxs-lookup"><span data-stu-id="f6979-113">Microsoft Planner</span></span>
- <span data-ttu-id="f6979-114">Pesquisa da Microsoft</span><span class="sxs-lookup"><span data-stu-id="f6979-114">Microsoft Search</span></span>
- <span data-ttu-id="f6979-115">Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="f6979-115">Microsoft StaffHub</span></span>
- <span data-ttu-id="f6979-116">Microsoft Stream para Microsoft 365 e Office 365 E1 SKUs<sup>1</1></span><span class="sxs-lookup"><span data-stu-id="f6979-116">Microsoft Stream for Microsoft 365 and Office 365 E1 SKUs <sup>1</1></span></span>
- <span data-ttu-id="f6979-117">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f6979-117">Microsoft Teams</span></span>
- <span data-ttu-id="f6979-118">Gerenciamento de Dispositivo Móvel para o Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="f6979-118">Mobile Device Management for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="f6979-119">Aplicativos do Office Mobile para Office 365</span><span class="sxs-lookup"><span data-stu-id="f6979-119">Office Mobile Apps for Office 365</span></span>
- <span data-ttu-id="f6979-120">Office Online</span><span class="sxs-lookup"><span data-stu-id="f6979-120">Office Online</span></span>
- <span data-ttu-id="f6979-121">PowerApps para o Microsoft 365 ou para o Office 365</span><span class="sxs-lookup"><span data-stu-id="f6979-121">PowerApps for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="f6979-122">SharePoint Online (Plano 1)</span><span class="sxs-lookup"><span data-stu-id="f6979-122">SharePoint Online (Plan 1)</span></span>
- <span data-ttu-id="f6979-123">Sway</span><span class="sxs-lookup"><span data-stu-id="f6979-123">Sway</span></span>
- <span data-ttu-id="f6979-124">To-Do (Plano 1)</span><span class="sxs-lookup"><span data-stu-id="f6979-124">To-Do (Plan 1)</span></span>
- <span data-ttu-id="f6979-125">Quadro de Comunicações (Plano 1)</span><span class="sxs-lookup"><span data-stu-id="f6979-125">Whiteboard (Plan 1)</span></span>
- <span data-ttu-id="f6979-126">Yammer Enterprise</span><span class="sxs-lookup"><span data-stu-id="f6979-126">Yammer Enterprise</span></span>

  <span data-ttu-id="f6979-127"><sup>1</sup> A mudança do Microsoft Stream para o [OneDrive for Business e o Microsoft Office SharePoint Online para gravações de reunião](tmr-meeting-recording-change.md) será uma abordagem em fases.</span><span class="sxs-lookup"><span data-stu-id="f6979-127"><sup>1</sup> The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach.</span></span> <span data-ttu-id="f6979-128">No lançamento, você poderá optar por essa experiência.</span><span class="sxs-lookup"><span data-stu-id="f6979-128">At launch, you'll be able to opt in to this experience.</span></span> <span data-ttu-id="f6979-129">Em novembro, você terá que cancelar se quiser continuar usando o Stream.</span><span class="sxs-lookup"><span data-stu-id="f6979-129">In November, you'll have to opt out if you want to continue using Stream.</span></span> <span data-ttu-id="f6979-130">Em algum momento no início de 2021, exigiremos que todos os clientes usem o OneDrive for Business e o Microsoft Office SharePoint Online para novas gravações de reuniões.</span><span class="sxs-lookup"><span data-stu-id="f6979-130">Sometime in early 2021, we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

## <a name="whos-eligible"></a><span data-ttu-id="f6979-131">Quem é elegível</span><span class="sxs-lookup"><span data-stu-id="f6979-131">Who's eligible</span></span>

<span data-ttu-id="f6979-132">Os usuários atendem aos critérios para uma experiência Exploratória de Teams se:</span><span class="sxs-lookup"><span data-stu-id="f6979-132">Users fit the criteria for a Teams Exploratory experience if they:</span></span>

- <span data-ttu-id="f6979-133">Tem um endereço de email de domínio gerenciado do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f6979-133">Have a managed Azure AD domain email address.</span></span>
- <span data-ttu-id="f6979-134">Pertence a um locatário com uma assinatura paga.</span><span class="sxs-lookup"><span data-stu-id="f6979-134">Belong to a tenant with a paid subscription.</span></span>

<span data-ttu-id="f6979-135">Habilite os usuários para se inscreverem em aplicativos e versões de avaliação (no centro de administração do Office 365).</span><span class="sxs-lookup"><span data-stu-id="f6979-135">Users must be enabled to sign up for apps and trials (in the Microsoft 365 admin center).</span></span> <span data-ttu-id="f6979-136">Para obter mais informações, confira [Gerenciar a experiência do Teams Exploratory](#manage-the-teams-exploratory-experience), mais adiante neste artigo.</span><span class="sxs-lookup"><span data-stu-id="f6979-136">For more information, see [Manage the Teams Exploratory experience](#manage-the-teams-exploratory-experience), later in this article.</span></span>

## <a name="who-isnt-eligible"></a><span data-ttu-id="f6979-137">Quem não está qualificado</span><span class="sxs-lookup"><span data-stu-id="f6979-137">Who isn't eligible</span></span>

<span data-ttu-id="f6979-138">Os usuários não se enquadram nos critérios se:</span><span class="sxs-lookup"><span data-stu-id="f6979-138">Users don't fit the criteria if they:</span></span>

- <span data-ttu-id="f6979-139">Atualmente ou anteriormente o Teams era disponibilizado com uma licença paga, não paga ou licença de avaliação </span><span class="sxs-lookup"><span data-stu-id="f6979-139">Currently or previously had Teams from a paid, unpaid, or trial license</span></span>
- <span data-ttu-id="f6979-140">Estão em um locatário que usou/recebeu pelo menos uma oferta especial de COVID.</span><span class="sxs-lookup"><span data-stu-id="f6979-140">Are in a tenant that used/received at least one special COVID offer.</span></span>

<span data-ttu-id="f6979-141">Sua organização não está qualificada para esta oferta se você for um Cliente Parceiro de Agregação ou se for um cliente do GCC, GCC High, DoD ou EDU.</span><span class="sxs-lookup"><span data-stu-id="f6979-141">Your organization isn't eligible for this offer if you're a Syndication Partner Customer or a GCC, GCC High, DoD, or EDU customer.</span></span>

## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a><span data-ttu-id="f6979-142">Como os usuários se inscrevem na experiência do Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="f6979-142">How users sign up for the Teams Exploratory experience</span></span>

<span data-ttu-id="f6979-143">Os usuários qualificados podem se inscrever para a Experiência do Teams Exploratory entrando no Teams a partir da área de trabalho ou da web ([teams.microsoft.com](https://teams.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="f6979-143">Eligible users can sign up for the Teams Exploratory experience by signing in to Teams from the desktop or web ([teams.microsoft.com](https://teams.microsoft.com)).</span></span> <span data-ttu-id="f6979-144">No momento, a ativação do Exploratory por meio do dispositivo móvel não é compatível.</span><span class="sxs-lookup"><span data-stu-id="f6979-144">At this time, enabling Exploratory through mobile is not supported.</span></span> <span data-ttu-id="f6979-145">Ao se inscreverem, essa licença será atribuída automaticamente a eles e o administrador do locatário receberá uma notificação por email na primeira vez que alguém em sua organização iniciar a experiência do Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="f6979-145">When they sign up, they'll be assigned this license automatically and the tenant admin will receive an email notification the first time someone in your org starts the Teams Exploratory experience.</span></span>

## <a name="manage-the-teams-exploratory-experience"></a><span data-ttu-id="f6979-146">Gerenciar a experiência do Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="f6979-146">Manage the Teams Exploratory experience</span></span>

<span data-ttu-id="f6979-147">A experiência Exploratória do Teams deve ser iniciada por usuários finais individuais e você não pode iniciar esta oferta em nome de funcionários usuários finais.</span><span class="sxs-lookup"><span data-stu-id="f6979-147">The Teams Exploratory experience is meant to be initiated by individual end users, and you can't initiate this offer on behalf of end-user employees.</span></span>

<span data-ttu-id="f6979-148">A experiência Exploratória do Teams vem com uma licença do Exchange Online, mas não será atribuída ao usuário até que o administrador a atribua.</span><span class="sxs-lookup"><span data-stu-id="f6979-148">The Teams Exploratory experience comes with an Exchange Online license, but it won't be assigned to the user until the admin assigns it.</span></span> <span data-ttu-id="f6979-149">Se o usuário ainda não tiver uma licença do Exchange e o administrador ainda não tiver atribuído a licença do Exchange Online, o usuário não poderá agendar reuniões no Teams e pode estar perdendo outras funcionalidades do Teams.</span><span class="sxs-lookup"><span data-stu-id="f6979-149">If the user doesn't have an Exchange license already, and the admin has yet to assign the Exchange Online license, the user won't be able to schedule meetings in Teams and might be missing other Teams functionality.</span></span>

<span data-ttu-id="f6979-150">Os administradores podem desabilitar a capacidade para que os usuários finais executem a experiência do Teams Exploratory em sua organização, usando a opção **Aplicativos e serviços de avaliação**.</span><span class="sxs-lookup"><span data-stu-id="f6979-150">Admins can disable the ability for end users to run the Teams Exploratory experience within their organization by using the **Trial apps and services** switch.</span></span>

### <a name="prevent-users-from-installing-trial-apps-and-services"></a><span data-ttu-id="f6979-151">Impedir que os usuários instalem serviços e aplicativos de avaliação</span><span class="sxs-lookup"><span data-stu-id="f6979-151">Prevent users from installing trial apps and services</span></span>

<span data-ttu-id="f6979-152">Você pode desativar a capacidade de um usuário de instalar aplicativos e serviços de avaliação, o que impediria o usuário de executar a experiência Exploratória do Teams.</span><span class="sxs-lookup"><span data-stu-id="f6979-152">You can turn off a user's ability to install trial apps and services, which would prevent the user from running the Teams Exploratory experience.</span></span>

1. <span data-ttu-id="f6979-153">Do Centro de administração do Microsoft 365, vá até **Configurações** > **Configurações da Organização**, selecione **Serviços** e, em seguida, selecione **Aplicativos e serviços de propriedade do usuário**.</span><span class="sxs-lookup"><span data-stu-id="f6979-153">From the Microsoft 365 admin center, go to **Settings** > **Org settings**, select **Services**, and then select **User owned apps and services**.</span></span>

    ![a página de Serviços no centro de administração](media/iw-trial-services.png)

2. <span data-ttu-id="f6979-155">Desmarque a caixa de seleção **Permitir que os usuários instalem aplicativos e serviços de avaliação**.</span><span class="sxs-lookup"><span data-stu-id="f6979-155">Clear the check mark from **Let users install trial apps and services**.</span></span>

    ![a página de aplicativos e serviços de propriedade do Usuário no centro de administração](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > <span data-ttu-id="f6979-157">Se a sua organização não estiver qualificada para a experiência do Teams Exploratory, você não verá a opção **Permitir que os usuários instalem aplicativos e serviços de avaliação**.</span><span class="sxs-lookup"><span data-stu-id="f6979-157">If your organization is ineligible for the Teams Exploratory experience, you won't see the **Let users install trial apps and services** option.</span></span>

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a><span data-ttu-id="f6979-158">Gerenciar a disponibilidade de um usuário com uma licença que inclua o Teams</span><span class="sxs-lookup"><span data-stu-id="f6979-158">Manage availability for a user with a license that includes Teams</span></span>

<span data-ttu-id="f6979-159">Um usuário que recebe uma licença que inclui o Teams não está qualificado para a experiência do Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="f6979-159">A user who is assigned a license that includes Teams isn't eligible for the Teams Exploratory experience.</span></span> <span data-ttu-id="f6979-160">Quando o plano de serviço do Teams está ativado, o usuário pode entrar e usar o Teams.</span><span class="sxs-lookup"><span data-stu-id="f6979-160">When the Teams service plan is turned on, the user can sign in and use Teams.</span></span> <span data-ttu-id="f6979-161">Se o plano do serviço estiver desabilitado, o usuário não poderá entrar e a experiência do Teams Exploratory não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="f6979-161">If the service plan is disabled, the user can't sign in and the Teams Exploratory experience isn't available.</span></span> <span data-ttu-id="f6979-162">Você deve ter privilégios de administrador.</span><span class="sxs-lookup"><span data-stu-id="f6979-162">You must have admin privileges.</span></span>

<span data-ttu-id="f6979-163">Para desativar o acesso ao Teams:</span><span class="sxs-lookup"><span data-stu-id="f6979-163">To turn off access to Teams:</span></span>

1. <span data-ttu-id="f6979-164">No Centro de administração do Microsoft 365, selecione **Usuários** > **Usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="f6979-164">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="f6979-165">Marque a caixa ao lado do nome do usuário.</span><span class="sxs-lookup"><span data-stu-id="f6979-165">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="f6979-166">Na linha **Licenças de produto**, escolha **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f6979-166">In the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="f6979-167">No painel **​​Licenças do produto**, alterne a chave para **Desligado**.</span><span class="sxs-lookup"><span data-stu-id="f6979-167">In the **Product licenses** pane, switch the toggle to **Off**.</span></span>

    ![a página de licenças do Produto no centro de administração.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a><span data-ttu-id="f6979-169">Gerenciar a disponibilidade do Teams para os usuários que já estão usando a experiência do Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="f6979-169">Manage Teams availability for users who are already using the Teams Exploratory experience</span></span>

<span data-ttu-id="f6979-170">Se um usuário estiver executando a experiência do Teams Exploratory, você poderá desativá-la removendo a licença ou o plano de serviço.</span><span class="sxs-lookup"><span data-stu-id="f6979-170">If a user is running the Teams Exploratory experience, you can turn it off by removing the license or service plan.</span></span> <span data-ttu-id="f6979-171">Você deve ter privilégios de administrador.</span><span class="sxs-lookup"><span data-stu-id="f6979-171">You must have admin privileges.</span></span>

<span data-ttu-id="f6979-172">Para desativar a licença de experiência do Teams Exploratory:</span><span class="sxs-lookup"><span data-stu-id="f6979-172">To turn off the Teams Exploratory experience license:</span></span>

1. <span data-ttu-id="f6979-173">No Centro de administração do Microsoft 365, selecione **Usuários** > **Usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="f6979-173">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="f6979-174">Marque a caixa ao lado do nome do usuário.</span><span class="sxs-lookup"><span data-stu-id="f6979-174">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="f6979-175">Na linha **Licenças de produto**, escolha **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f6979-175">In the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="f6979-176">No painel **Licenças de produto**, alterne a opção desta licença exploratória para **Desativar**.</span><span class="sxs-lookup"><span data-stu-id="f6979-176">In the **Product licenses** pane, switch the toggle for this exploratory license to **Off**.</span></span>

    >[!Note]
    ><span data-ttu-id="f6979-177">A opção de alternância do Teams Exploratory será exibida após o primeiro usuário da organização iniciar a experiência do Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="f6979-177">The Teams Exploratory toggle switch will appear after the first user in the organization launches the Teams Exploratory experience.</span></span>

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a><span data-ttu-id="f6979-178">Gerenciar o Teams para usuários que possuem a licença do Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="f6979-178">Manage Teams for users who have the Teams Exploratory license</span></span>

<span data-ttu-id="f6979-179">Você pode gerenciar usuários que possuem a licença do Teams Exploratory, assim como gerencia usuários que possuem uma licença paga regular.</span><span class="sxs-lookup"><span data-stu-id="f6979-179">You can manage users who have the Teams Exploratory license just like you manage users who have a regular paid license.</span></span> <span data-ttu-id="f6979-180">Para mais informações, confira [Gerenciar as configurações do Teams da sua organização](enable-features-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="f6979-180">For more information, see [Manage Teams settings for your organization](enable-features-office-365.md).</span></span>

### <a name="upgrade-users-from-the-teams-exploratory-license"></a><span data-ttu-id="f6979-181">Atualizar os usuários da licença do Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="f6979-181">Upgrade users from the Teams Exploratory license</span></span>

<span data-ttu-id="f6979-182">Para atualizar os usuários da licença do Teams Exploratory (você deve ter privilégios de administrador), execute as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="f6979-182">To upgrade users from the Teams Exploratory license (you must have admin privileges), do the following tasks:</span></span>

1. <span data-ttu-id="f6979-183">Compre uma assinatura que inclua o Teams.</span><span class="sxs-lookup"><span data-stu-id="f6979-183">Purchase a subscription that includes Teams.</span></span>

2. <span data-ttu-id="f6979-184">Remova a assinatura do Teams Exploratory do usuário.</span><span class="sxs-lookup"><span data-stu-id="f6979-184">Remove the Teams Exploratory subscription from the user.</span></span>

3. <span data-ttu-id="f6979-185">Atribua as licenças adquiridas recentemente.</span><span class="sxs-lookup"><span data-stu-id="f6979-185">Assign the newly purchased license.</span></span>

<span data-ttu-id="f6979-186">Para saber mais, confira [Descrição do serviço do Microsoft Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span><span class="sxs-lookup"><span data-stu-id="f6979-186">For more information, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

> [!NOTE]
> <span data-ttu-id="f6979-187">Se a licença Exploratória do Teams terminar e um usuário não fizer upgrade imediatamente para uma assinatura que inclua o Teams, ele terá 30 dias de período de carência e mais 30 dias após os quais os dados serão excluídos.</span><span class="sxs-lookup"><span data-stu-id="f6979-187">If the Teams Exploratory license ends and a user isn't immediately upgraded to a subscription that includes Teams, they have 30 days of grace period and then another 30 days after which time the data is going to be deleted.</span></span> <span data-ttu-id="f6979-188">O usuário ainda existe no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f6979-188">The user still exists in Azure Active Directory.</span></span> <span data-ttu-id="f6979-189">Assim que uma nova licença for atribuída ao usuário para habilitar a funcionalidade do Teams novamente, todo o conteúdo ainda existirá se o usuário for adicionado dentro do período de tempo de tolerância.</span><span class="sxs-lookup"><span data-stu-id="f6979-189">Once a new license is assigned to the user to enable Teams functionality again, all content will still exist if the user is added within the grace period time frame.</span></span>

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a><span data-ttu-id="f6979-190">O que acontece com as licenças do Microsoft Teams Commercial Cloud Trial</span><span class="sxs-lookup"><span data-stu-id="f6979-190">What happens to legacy Microsoft Teams Commercial Cloud Trial licenses</span></span>

<span data-ttu-id="f6979-191">A partir de fevereiro de 2020, os usuários qualificados podem começar a usar a experiência mais recente do Microsoft Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="f6979-191">As of February 2020, eligible users can begin using the latest Microsoft Teams Exploratory experience.</span></span> <span data-ttu-id="f6979-192">Todas as licenças do Teams Commercial Cloud Trial legado serão convertidas automaticamente para a nova oferta antes que o teste expire.</span><span class="sxs-lookup"><span data-stu-id="f6979-192">All legacy Teams Commercial Cloud Trial licenses will be automatically converted to the new offer before their trial expires.</span></span>

<span data-ttu-id="f6979-193">Quando os usuários se conectam no Teams Commercial Cloud Trial expirado pela primeira vez, atribuímos automaticamente uma licença de experiência do Teams Exploratory a esses usuários.</span><span class="sxs-lookup"><span data-stu-id="f6979-193">When users sign in to their expired Teams Commercial Cloud Trial for the first time, we automatically assign a Teams Exploratory experience license to those users.</span></span> <span data-ttu-id="f6979-194">Os usuários não serão convertidos antes de entrar.</span><span class="sxs-lookup"><span data-stu-id="f6979-194">Users aren't converted until they sign in.</span></span>

### <a name="remove-a-teams-exploratory-license"></a><span data-ttu-id="f6979-195">Remover uma licença do Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="f6979-195">Remove a Teams Exploratory license</span></span>

- <span data-ttu-id="f6979-196">Se você deseja remover essa licença por meio do PowerShell, confira: [Remover licenças de contas de usuário com o Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="f6979-196">If you would like to remove this license by using PowerShell, see: [Remove licenses from user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span></span>

- <span data-ttu-id="f6979-197">Se você quiser remover essa licença por meio do portal de administração do, confira: [Excluir um usuário da sua organização](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)</span><span class="sxs-lookup"><span data-stu-id="f6979-197">If you would like to remove this license through the admin portal, see: [Delete a user from your organization](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)</span></span>

## <a name="what-is-the-data-retention-policy"></a><span data-ttu-id="f6979-198">Qual é a política de retenção de dados</span><span class="sxs-lookup"><span data-stu-id="f6979-198">What is the data retention policy</span></span>

<span data-ttu-id="f6979-199">Confira as [Informações de assinatura do Microsoft 365](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="f6979-199">See [Microsoft 365 subscription information](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).</span></span>

## <a name="how-long-does-the-teams-exploratory-experience-last"></a><span data-ttu-id="f6979-200">Quanto tempo dura a experiência do Teams Exploratory?</span><span class="sxs-lookup"><span data-stu-id="f6979-200">How long does the Teams Exploratory experience last</span></span>

<span data-ttu-id="f6979-201">A experiência Microsoft Teams Exploratory está disponível sem custo adicional por 12 meses (a partir da inscrição inicial do usuário) mais um período de cortesia adicional de 30 dias.</span><span class="sxs-lookup"><span data-stu-id="f6979-201">The Microsoft Teams Exploratory experience is available at no additional cost for 12 months (from initial user sign-up) plus an additional 30 day grace period.</span></span> <span data-ttu-id="f6979-202">Nesse momento, os usuários finais em uma licença do Microsoft Exploratory precisarão passar para uma licença paga que inclua o Teams.</span><span class="sxs-lookup"><span data-stu-id="f6979-202">At that time, end users on a Microsoft Exploratory experience license will need to move to a paid license that includes Teams.</span></span> <span data-ttu-id="f6979-203">A mesma data de término será aplicada a todos os usuários no mesmo locatário, com o prazo de 12 meses iniciado na data de inscrição do primeiro usuário.</span><span class="sxs-lookup"><span data-stu-id="f6979-203">The same end date will apply to all users on the same tenant, with the 12-month term starting on the first user’s sign-up date.</span></span>

### <a name="what-happens-if-an-end-user-initiates-the-microsoft-teams-exploratory-experience-just-before-the-anniversary-or-renewal-date"></a><span data-ttu-id="f6979-204">O que acontece se um usuário final iniciar a experiência Microsoft Teams Exploratory pouco antes do aniversário ou data de renovação</span><span class="sxs-lookup"><span data-stu-id="f6979-204">What happens if an end user initiates the Microsoft Teams Exploratory experience just before the anniversary or renewal date</span></span>

<span data-ttu-id="f6979-205">Licenças de experiência do Microsoft Teams Exploratory iniciadas dentro de 90 dias de seu **aniversário de contrato** ou **renovação** não serão necessárias para mudar para uma licença paga até o aniversário subsequente ou ciclo de renovação.</span><span class="sxs-lookup"><span data-stu-id="f6979-205">Microsoft Teams Exploratory experience licenses initiated within 90 days of your **agreement anniversary** or **renewal** won't be required to move to a paid license until the subsequent anniversary or renewal cycle.</span></span>

### <a name="what-if-my-agreement-doesnt-have-an-anniversary-or-yearly-renewal-date-for-example-month-to-month-agreements"></a><span data-ttu-id="f6979-206">E se meu contrato não tiver um aniversário ou data de renovação anual (por exemplo, contratos mensais)</span><span class="sxs-lookup"><span data-stu-id="f6979-206">What if my agreement doesn’t have an anniversary or yearly renewal date (for example, month-to-month agreements)</span></span>

<span data-ttu-id="f6979-207">Para contratos sem uma data de aniversário ou de renovação anual, o ano subsequente após o primeiro usuário final ativar as licenças de experiências do Microsoft Teams Exploratory será considerado como a data de aniversário ou de renovação.</span><span class="sxs-lookup"><span data-stu-id="f6979-207">For agreements without an anniversary or yearly renewal date, the subsequent year after the first end user activates the Microsoft Teams Exploratory experience licenses will be treated as the anniversary or renewal date.</span></span> <span data-ttu-id="f6979-208">Os usuários da licença do Microsoft Teams Exploratory devem ser convertidos em uma licença paga até essa data a cada ano, de acordo com as políticas descritas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="f6979-208">Users on the Microsoft Teams Exploratory license must be converted to a paid license by that date each year, according to the policies outlined in this article.</span></span>

<span data-ttu-id="f6979-209">Por exemplo, se o primeiro usuário final ativar o Microsoft Teams Exploratory em 19 de junho de 2020, ele e todos os outros usuários qualificados no locatário do cliente devem ser convertidos para uma licença paga com o Teams até 19 de junho de 2021.</span><span class="sxs-lookup"><span data-stu-id="f6979-209">For example, if the first end user activates Microsoft Teams Exploratory on June 19, 2020, then they and all other eligible users in the customer tenant must convert to a paid license with Teams by June 19, 2021.</span></span>

> [!Note]
> <span data-ttu-id="f6979-210">Os clientes serão desabilitados e impedidos de iniciar uma nova licença de avaliação do Exploratory por 3 meses após a expiração de sua licença de avaliação do Exploratory anterior.</span><span class="sxs-lookup"><span data-stu-id="f6979-210">Customers will be disabled and blocked from starting a new Exploratory trial licenses for 3 months past the expiration of their previous Exploratory trial license.</span></span>
