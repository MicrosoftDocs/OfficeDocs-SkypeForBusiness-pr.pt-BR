---
title: Migrar do Slack para o Microsoft Teams
author: lolajacobsen
ms.author: lolaj
ms.reviewer: brandber
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1.keywords:
- NOCSH
description: Orientação completa para migrar do Slack para o Microsoft Teams.
ms.openlocfilehash: 15ef6203fa2cf27d081865e3966198f033b1bd80
ms.sourcegitcommit: 8e2fa7b744d0a174b699ae7298d4688b971eeff3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/07/2020
ms.locfileid: "41845203"
---
# <a name="migrate-from-slack-to-microsoft-teams"></a><span data-ttu-id="b7998-103">Migrar do Slack para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b7998-103">Migrate from Slack to Microsoft Teams</span></span>

<span data-ttu-id="b7998-104">Este artigo guiará na jornada de migração para o Microsoft Teams a partir do Slack.</span><span class="sxs-lookup"><span data-stu-id="b7998-104">This article walks you through the journey of moving to Microsoft Teams from Slack.</span></span>

<span data-ttu-id="b7998-105">Ao planejar a mudança da sua organização para o Teams a partir do Slack, é importante decidir o que é necessário manter (caso haja algo).</span><span class="sxs-lookup"><span data-stu-id="b7998-105">When planning your organization’s move to Teams from Slack, it's important to decide what you need to keep (if anything).</span></span> <span data-ttu-id="b7998-106">Para começar, descreveremos quais tipos de dados podem ser migrados, em seguida, orientaremos na avaliação das suas necessidades, no planejamento da mudança e como fazê-la.</span><span class="sxs-lookup"><span data-stu-id="b7998-106">We'll start off by describing what types of data can be migrated and then walk you through how to assess your needs, plan your move, and then make the move.</span></span>

<span data-ttu-id="b7998-107">O diagrama a seguir mostra a arquitetura do Slack em alto nível.</span><span class="sxs-lookup"><span data-stu-id="b7998-107">The diagram below shows the Slack architecture at a high level.</span></span>

![Imagem que reduz a arquitetura do Slack em alto nível.](media/migrate-slack-to-teams-image1.png)

## <a name="plan-your-migration-from-slack"></a><span data-ttu-id="b7998-109">Planeje sua migração do Slack</span><span class="sxs-lookup"><span data-stu-id="b7998-109">Plan your migration from Slack</span></span>
### <a name="what-you-can-and-cant-migrate"></a><span data-ttu-id="b7998-110">O que pode e não pode migrar</span><span class="sxs-lookup"><span data-stu-id="b7998-110">What you can and can’t migrate</span></span>
<span data-ttu-id="b7998-111">O seu plano de serviço do Slack determinará o que pode e não pode migrar.</span><span class="sxs-lookup"><span data-stu-id="b7998-111">Your Slack service plan will determine what you can and can’t migrate.</span></span> <span data-ttu-id="b7998-112">Por exemplo, alguns planos de serviço do Slack permitem exportar apenas arquivos e histórico de canais públicos, outros exigem uma solicitação do DocuSign para incluir Canais Privados e Mensagens Diretas.</span><span class="sxs-lookup"><span data-stu-id="b7998-112">For example, some Slack service plans only let you export public channels history and files, other require a DocuSign request to include Private Channels and Direct Messages.</span></span> 

<span data-ttu-id="b7998-113">Para determinar o nível de serviço do seu Slack Workspace, faça logon no Slack e observe o tipo de plano na página **Sobre este Workspace**.</span><span class="sxs-lookup"><span data-stu-id="b7998-113">To determine your Slack Workspace service level, log into Slack and note your plan type on the **About this Workspace** page.</span></span>

<span data-ttu-id="b7998-114">Para saber mais sobre as opções de exportação do Slack, vá para o site do Slack: https://get.slack.help/hc/articles/204897248-Guide-to-Slack-import-and-export-tools</span><span class="sxs-lookup"><span data-stu-id="b7998-114">To learn more about Slack export options, go to the Slack website: https://get.slack.help/hc/articles/204897248-Guide-to-Slack-import-and-export-tools</span></span> 

<span data-ttu-id="b7998-115">O diagrama a seguir fornece uma visão de alto nível do panorama de migração do Slack que abordaremos neste artigo.</span><span class="sxs-lookup"><span data-stu-id="b7998-115">The diagram below gives you a high-level look at the Slack migration landscape that we’ll cover in this article.</span></span> 

![Diagrama que mostra o panorama de exportação do Slack.](media/migrate-slack-to-teams-image2.png)

<span data-ttu-id="b7998-117">Ao terminar esta seção, você será capaz de entender:</span><span class="sxs-lookup"><span data-stu-id="b7998-117">When you're done with this section, you should understand:</span></span>
- <span data-ttu-id="b7998-118">O nível de serviço dos seus Slack Workspaces</span><span class="sxs-lookup"><span data-stu-id="b7998-118">The service level of your Slack Workspaces</span></span>
- <span data-ttu-id="b7998-119">O que pode e não pode ser exportado</span><span class="sxs-lookup"><span data-stu-id="b7998-119">What can and can't be exported</span></span>
- <span data-ttu-id="b7998-120">Abordagens comuns à exportação</span><span class="sxs-lookup"><span data-stu-id="b7998-120">Common approaches to exporting</span></span>

### <a name="assess-your-slack-workspaces"></a><span data-ttu-id="b7998-121">Avaliar seus Slack workspaces</span><span class="sxs-lookup"><span data-stu-id="b7998-121">Assess your Slack workspaces</span></span>
<span data-ttu-id="b7998-122">Antes de fazer o plano de migração da sua organização, você precisa reunir algumas informações sobre os seus Slack workspaces.</span><span class="sxs-lookup"><span data-stu-id="b7998-122">Before you can plan your organization’s migration plan, you need to pull together some information about your Slack workspaces.</span></span> <span data-ttu-id="b7998-123">Entender como os Slack workspaces estão sendo usados ajuda a determinar o escopo da migração.</span><span class="sxs-lookup"><span data-stu-id="b7998-123">Understanding how your Slack workspaces are being used helps you determine the scope of your migration.</span></span> <span data-ttu-id="b7998-124">Por exemplo, quantos workspaces estão sendo movidos?</span><span class="sxs-lookup"><span data-stu-id="b7998-124">For example, how many workspaces are being moved?</span></span> <span data-ttu-id="b7998-125">Eles são usados por um departamento específico, por vários, ou por toda organização?</span><span class="sxs-lookup"><span data-stu-id="b7998-125">Are they used by a specific department, many, or in use by an entire organization?</span></span>

<span data-ttu-id="b7998-126">Se você é membro dos Slack Workspaces que deseja migrar, poderá analisar o uso por conta própria, indo para *<your Slack workspace>.slack.com/stats*. Examine as guias Canais e Membros para procurar por padrões de uso.</span><span class="sxs-lookup"><span data-stu-id="b7998-126">If you’re a member of the Slack Workspaces you want to migrate, you can analyze the usage yourself by going to *<your Slack workspace>.slack.com/stats*. Review the Channels and Members tabs to look for usage patterns.</span></span> <span data-ttu-id="b7998-127">Decida quais workspaces você deseja migrar (e quais deseja deixar para trás).</span><span class="sxs-lookup"><span data-stu-id="b7998-127">Decide which workspaces you want to migrate (and which ones you want to leave behind).</span></span> 

> [!NOTE]
> <span data-ttu-id="b7998-128">Se não tiver acesso à página de estatísticas, então você não é um administrador ou proprietário.</span><span class="sxs-lookup"><span data-stu-id="b7998-128">If you don’t have access to the stats page, you’re not an admin or owner.</span></span> 

### <a name="export-channels"></a><span data-ttu-id="b7998-129">Exportar Canais</span><span class="sxs-lookup"><span data-stu-id="b7998-129">Export Channels</span></span>

<span data-ttu-id="b7998-130">No Slack, os usuários ingressam em um canal que faz parte de um Slack Workspace, enquanto que no Teams, os usuários ingressam em uma equipe que é uma coleção de canais.</span><span class="sxs-lookup"><span data-stu-id="b7998-130">In Slack, users join a channel which is part of a Slack Workspace, whereas in Teams users join a team which is a collection of channels.</span></span> <span data-ttu-id="b7998-131">Recomendamos que você use a análise do Slack para ver quanta atividade acontece em cada canal para ajudá-lo a decidir quais canais mover.</span><span class="sxs-lookup"><span data-stu-id="b7998-131">We recommend that you use Slack analytics to see how much activity happens in each channel to help you decide which channels to move.</span></span> <span data-ttu-id="b7998-132">Você usará a lista resultante para descobrir como agrupar seus canais do Slack em equipes no Teams, bem como quem deverá ser os membros de cada equipe.</span><span class="sxs-lookup"><span data-stu-id="b7998-132">You’ll use the resulting list to figure out how to group your Slack channels into teams in Teams as well as who should be members of each team.</span></span>

<span data-ttu-id="b7998-133">Se você possui um plano de serviço pago do Slack (qualquer outro que não seja gratuito), poderá usar as análises do Slack (<your Slack workspace>.slack.com/admin/stats#channels) para ver a quantidade de atividades de um canal, quando foi usado pela última vez e quantas pessoas são membros.</span><span class="sxs-lookup"><span data-stu-id="b7998-133">If you have a paid Slack service plan (anything other than Free), you can use Slack’s analytics (<your Slack workspace>.slack.com/admin/stats#channels) to see how active a channel is, when it was last used, and how many people are members.</span></span> <span data-ttu-id="b7998-134">Isso poderá ajudá-lo a decidir se migrará o canal.</span><span class="sxs-lookup"><span data-stu-id="b7998-134">This can help you decide whether to migrate the channel.</span></span> <span data-ttu-id="b7998-135">Por padrão, o conteúdo de canais públicos (mensagens e arquivos) pode ser exportado.</span><span class="sxs-lookup"><span data-stu-id="b7998-135">By default, public channels content (messages and files) can be exported.</span></span> <span data-ttu-id="b7998-136">Dependendo do seu plano de serviço do Slack e caso tenha solicitado Canais Privados e Mensagens Diretas do Slack, eles poderão ser exportados.</span><span class="sxs-lookup"><span data-stu-id="b7998-136">Depending on your Slack service plan and whether you’ve requested Private Channels and Direct Messages from Slack, those can be exported.</span></span>

<span data-ttu-id="b7998-137">Para saber mais sobre as opções de exportação do Slack, vá para o site do Slack: https://get.slack.help/hc/articles/204897248-Guide-to-Slack-import-and-export-tools</span><span class="sxs-lookup"><span data-stu-id="b7998-137">To learn more about Slack export options, go to the Slack website: https://get.slack.help/hc/articles/204897248-Guide-to-Slack-import-and-export-tools</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="b7998-138">Verifique os requisitos de privacidade e conformidade da sua organização em relação aos dados do canal.</span><span class="sxs-lookup"><span data-stu-id="b7998-138">Check your organization’s privacy and compliance requirements around channel data.</span></span> <span data-ttu-id="b7998-139">Sua organização pode ter requisitos de conformidade em relação ao manuseio, armazenamento e processamento desses dados, além de cumprir o ciclo de vida do conteúdo identificável do usuário final (EUII).</span><span class="sxs-lookup"><span data-stu-id="b7998-139">Your organization may have compliance requirements around the handling, storage, and processing of this data, in addition to complying with the lifecycle of end-user identifiable content (EUII).</span></span>

### <a name="export-direct-messages"></a><span data-ttu-id="b7998-140">Exportar Mensagens Diretas</span><span class="sxs-lookup"><span data-stu-id="b7998-140">Export Direct Messages</span></span>
<span data-ttu-id="b7998-141">As Mensagens Diretas são iguais aos chats no Teams, que são de 1:1 ou 1 para várias conversas que não são de canal.</span><span class="sxs-lookup"><span data-stu-id="b7998-141">Direct Messages are the same as chats in Teams, which are 1:1 or 1-to-many non-channel conversations.</span></span> <span data-ttu-id="b7998-142">A capacidade de exportação depende do plano de serviço do Slack e se você tiver solicitado a inclusão de Mensagens Diretas no seu Slack Export.</span><span class="sxs-lookup"><span data-stu-id="b7998-142">Export-ability depends on your Slack service plan and if you’ve requested Direct Messages to be included in your Slack Export.</span></span> <span data-ttu-id="b7998-143">O Teams não dá suporte a importação de Mensagens Diretas no momento.</span><span class="sxs-lookup"><span data-stu-id="b7998-143">Teams doesn’t support importing Direct messages currently.</span></span> <span data-ttu-id="b7998-144">Consulte um parceiro da Microsoft para saber mais sobre as soluções de terceiros que você pode explorar e que trazem o conteúdo de Mensagens Diretas para o Teams.</span><span class="sxs-lookup"><span data-stu-id="b7998-144">Consult a Microsoft partner to learn about third-party solutions you can explore that bring Direct Messages content into Teams.</span></span>

<span data-ttu-id="b7998-145">Para exportar Mensagens Diretas, confira as ferramentas, como o Export, na Loja de Aplicativos do Slack.</span><span class="sxs-lookup"><span data-stu-id="b7998-145">For exporting Direct Messages, check out tools, such as Export, in the Slack App Store.</span></span>

### <a name="apps-and-custom-integrations"></a><span data-ttu-id="b7998-146">Aplicativos e integrações personalizadas</span><span class="sxs-lookup"><span data-stu-id="b7998-146">Apps and custom integrations</span></span>

<span data-ttu-id="b7998-147">Os aplicativos no Slack são como os aplicativos no Teams.</span><span class="sxs-lookup"><span data-stu-id="b7998-147">Apps in Slack are like apps in Teams.</span></span> <span data-ttu-id="b7998-148">Depois de ter uma lista de aplicativos e suas configurações no Workspace, você poderá pesquisar na Loja de Aplicativos do Teams para ver se eles estão disponíveis para o Teams\*.</span><span class="sxs-lookup"><span data-stu-id="b7998-148">Once you have a list of apps and their configurations in the Workspace, you can search in the Teams App store to see if they’re available for Teams\*.</span></span> 

<span data-ttu-id="b7998-149">Vá para <your Slack workspace>.slack.com/apps/manage para obter uma lista de Aplicativos e Integrações Personalizadas.</span><span class="sxs-lookup"><span data-stu-id="b7998-149">Go to <your Slack workspace>.slack.com/apps/manage to get a list of Apps and Custom Integrations.</span></span> <span data-ttu-id="b7998-150">Essa página também mostra o número de configurações em que cada aplicativo está em uso.</span><span class="sxs-lookup"><span data-stu-id="b7998-150">This page also shows you the number of configurations where each app is in use.</span></span> <span data-ttu-id="b7998-151">As Integrações Personalizadas variam em sua "capacidade de migração".</span><span class="sxs-lookup"><span data-stu-id="b7998-151">Custom Integrations vary in their “migrate-ability.”</span></span> <span data-ttu-id="b7998-152">Se for um Web Hook, você poderá enviá-lo a um Conector do Office 365 para mudar o fluxo de trabalho no Teams.</span><span class="sxs-lookup"><span data-stu-id="b7998-152">If it’s a Web Hook, you can usually send it to an Office 365 Connector to shift the workflow into Teams.</span></span> <span data-ttu-id="b7998-153">Avalie bots e outros aplicativos caso a caso ao planejar movê-los para o Teams.</span><span class="sxs-lookup"><span data-stu-id="b7998-153">Assess bots and other apps on a case-by-case basis to plan for moving them to Teams.</span></span>

<span data-ttu-id="b7998-154">\*Se o seu administrador restringiu o uso de aplicativos, talvez você não tenha acesso a lista completa de aplicativos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="b7998-154">\* If your administrator has restricted apps usage, you may not be looking at the full list of available apps.</span></span>

### <a name="users"></a><span data-ttu-id="b7998-155">Usuários</span><span class="sxs-lookup"><span data-stu-id="b7998-155">Users</span></span>
<span data-ttu-id="b7998-156">Os esquemas de identidade usados no Slack podem não ser mapeados diretamente para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="b7998-156">The identity schemes you used in Slack might not map directly to Office 365.</span></span> <span data-ttu-id="b7998-157">Por exemplo, os endereços de email dos usuários do Slack podem não ser mapeados para as contas corporativas ou de estudante do Office 365.</span><span class="sxs-lookup"><span data-stu-id="b7998-157">For example, the email addresses of your Slack users may not map to Office 365 work or school accounts.</span></span> <span data-ttu-id="b7998-158">Você deverá criar um mapa de ID do usuário antes de começar a planejar a distribuição do Teams.</span><span class="sxs-lookup"><span data-stu-id="b7998-158">You should create a user-ID map before you start planning your Teams rollout.</span></span>

<span data-ttu-id="b7998-159">Se você tiver um plano de serviço pago do Slack, vá para *<your Slack workspace>.slack.com/admin/stats#members* para obter detalhes dos membros, como endereço de email e tipo de conta para cada usuário (por exemplo, convidado único versus multicanal).</span><span class="sxs-lookup"><span data-stu-id="b7998-159">If you’re on a paid Slack service plan, you can go to *<your Slack workspace>.slack.com/admin/stats#members* to get member details such as email address and account type for each user (for example, single vs. multi-channel guest).</span></span>

<span data-ttu-id="b7998-160">Este é um script que pode ser usado para comparar endereços de email de uma exportação do Slack com o Azure AD para ajudar a resolver ambiguidade de nome.</span><span class="sxs-lookup"><span data-stu-id="b7998-160">Here’s a script you can use to compare email addresses from a Slack export against Azure AD to help solve for name ambiguity.</span></span> <span data-ttu-id="b7998-161">Ele também reportará se o usuário está habilitado ao Teams.</span><span class="sxs-lookup"><span data-stu-id="b7998-161">It’ll also report if the user is enabled for Teams.</span></span> <span data-ttu-id="b7998-162">Se precisar de ajuda com o PowerShell, leia [Introdução ao Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span><span class="sxs-lookup"><span data-stu-id="b7998-162">If you need help with PowerShell, read [Get started with Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span></span>

```azurepowershell
Connect-AzureAD
Function Get-TimeStamp {
    return "[{0:MM/dd/yy} {0:HH:mm:ss}]" -f (Get-Date)
}

class User {
    [ValidateNotNullOrEmpty()] $ID
    [ValidateNotNullOrEmpty()] $FullName
    [string] $Email
    [string] $UPN
    [ValidateNotNullOrEmpty()][bool] $ExistsAzureAD
    [ValidateNotNullOrEmpty()][bool] $TeamsEnabled
}

$output = New-Object -type System.Collections.ObjectModel.Collection["User"]

$users = Get-Content -Raw -Path .\slackHistory\users.json | ConvertFrom-Json

Write-Host -ForegroundColor Green "$(Get-Timestamp) User Count: " $users.Count

$i=1
Write-Host "$(Get-Timestamp) Attempting direct email match.. `n"
foreach ($slackUser in $users) {
    $user = New-Object User
    $user.id = $slackUser.id
    $user.FullName = $slackUser.name
    try {
        if ($null -ne $slackUser.profile.email) {
            $user.email = $slackUser.profile.email
            $emailSplit = $slackUser.profile.email.Split('@')
            $mailNickName = $emailSplit[0]
            $result = Get-AzureADUser -Filter "MailNickName eq '$($mailNickName)' or UserPrincipalName eq '$($slackUser.profile.email)' or proxyAddresses/any(c:c eq 'smtp:$($slackUser.profile.email)')"
            if ($null -ne $result) {
                $user.ExistsAzureAD = $true
                $user.UPN = $result.UserPrincipalName
                $assignedPlans = $result.assignedPlans
                foreach ($plan in $assignedPlans) {
                    if ($plan.ServicePlanId -eq "57ff2da0-773e-42df-b2af-ffb7a2317929") {
                        if ($plan.CapabilityStatus -eq "Enabled") {
                            $user.TeamsEnabled = $true
                        }
                        else {
                            $user.TeamsEnabled = $false
                        }
                    }
                }
                Write-Host -ForegroundColor Green "$(Get-Timestamp) Current User $($i) - AzureAD object found:" $result.MailNickName
                Write-Host -ForegroundColor Green "$(Get-Timestamp) Current User $($i) - Teams Enabled:" $user.TeamsEnabled
            }
            else {
                $user.ExistsAzureAD = $false
                Write-Host -ForegroundColor Yellow "$(Get-Timestamp) Current User $($i) - AzureAD object not found: " $slackUser.profile.email
            }
        }
        $i++
    }   
    catch
    {
        $user.ExistsAzureAD = $false
        Write-Host -ForegroundColor Yellow "$(Get-Timestamp) Current User $($i) - AzureAD object not found: $($i)" $user.profile.email
        $i++
    }
    $output.Add($user)
}

$output | Export-Csv -Path .\SlackToAzureADIdentityMapping.csv -NoTypeInformation
Write-Host "`n $(Get-Timestamp) Generated SlackToAzureADIdentityMapping.csv. Exiting..."
$output | Export-Csv -Path .\SlackToAzureADIdentityMapping.csv -NoTypeInformation
Write-Host "`n $(Get-Timestamp) Generated SlackToAzureADIdentityMapping.csv. Exiting..."
```

<span data-ttu-id="b7998-163">Ao terminar esta seção, você deverá ter:</span><span class="sxs-lookup"><span data-stu-id="b7998-163">When you’re done with this section, you should have:</span></span>
- <span data-ttu-id="b7998-164">Uma lista de Canais por Workspace com estatísticas de uso.</span><span class="sxs-lookup"><span data-stu-id="b7998-164">A list of Channels per Workspace with usage statistics.</span></span>
- <span data-ttu-id="b7998-165">Uma lista de Aplicativos do Slack com configurações por canal.</span><span class="sxs-lookup"><span data-stu-id="b7998-165">A list of Slack Apps with configurations per channel.</span></span>
- <span data-ttu-id="b7998-166">Determinado o tipo de histórico de mensagens do Slack você deseja exportar (se houver).</span><span class="sxs-lookup"><span data-stu-id="b7998-166">Determined what type of Slack message history you want to export (if any).</span></span>
- <span data-ttu-id="b7998-167">Uma lista de usuários cujas contas do Slack são mapeadas para contas corporativas ou de estudante da Microsoft e quais licenças do Teams eles têm.</span><span class="sxs-lookup"><span data-stu-id="b7998-167">A list of users whose Slack accounts map to Microsoft work or school accounts and which Teams license they have.</span></span>

## <a name="plan-your-teams-deployment"></a><span data-ttu-id="b7998-168">Planejar sua implantação do Teams</span><span class="sxs-lookup"><span data-stu-id="b7998-168">Plan your Teams deployment</span></span>
<span data-ttu-id="b7998-169">Você exportou o que precisa do Slack (e deixou para trás tudo o que não precisa).</span><span class="sxs-lookup"><span data-stu-id="b7998-169">You’ve exported what you need from Slack (and left behind anything you don’t need).</span></span> <span data-ttu-id="b7998-170">Agora é hora de planejar como será feito a distribuição do Teams e de importar seus dados do Slack.</span><span class="sxs-lookup"><span data-stu-id="b7998-170">Now it’s time to plan how you’ll roll out Teams and import your Slack data.</span></span> <span data-ttu-id="b7998-171">Esta é uma ótima oportunidade para avaliar o que funcionou bem para a equipe com base no uso e incluir esses elementos no plano de implantação do Teams.</span><span class="sxs-lookup"><span data-stu-id="b7998-171">This is a great opportunity to assess what's worked well for the team based on usage and include those elements in your Teams deployment plan.</span></span> <span data-ttu-id="b7998-172">No final desta seção, você terá um plano gráfico para usuários, canais e aplicativos do Teams.</span><span class="sxs-lookup"><span data-stu-id="b7998-172">At the end of this section, you’ll have a blueprint for your Teams users, channels, and apps.</span></span> 

<span data-ttu-id="b7998-173">O diagrama a seguir fornece uma estrutura de tópicos de alto nível dos itens que você abordará na implantação do Teams.</span><span class="sxs-lookup"><span data-stu-id="b7998-173">The diagram below gives you a high-level outline of the things you’ll address in your Teams deployment.</span></span>

:::image type="content" source="media/migrate-slack-to-teams-image3.png" alt-text="Estrutura de tópicos de alto nível sobre como planejar uma implantação do Teams a partir do Slack.":::

### <a name="team-and-channel-structure"></a><span data-ttu-id="b7998-175">Estrutura de equipe e canal</span><span class="sxs-lookup"><span data-stu-id="b7998-175">Team and channel structure</span></span>

<span data-ttu-id="b7998-176">Um Slack Workspace pode representar uma única equipe, várias equipes ou uma organização inteira.</span><span class="sxs-lookup"><span data-stu-id="b7998-176">A Slack Workspace may represent a single team, multiple teams or an entire organization.</span></span> <span data-ttu-id="b7998-177">É importante entender o escopo dos Workspaces ao determinar a estrutura.</span><span class="sxs-lookup"><span data-stu-id="b7998-177">It’s important to understand the scope of the Workspaces as you determine the structure.</span></span> <span data-ttu-id="b7998-178">A relação mais próxima a uma equipe do Teams no Slack é o Workspace, que contém uma coleção de canais.</span><span class="sxs-lookup"><span data-stu-id="b7998-178">The closest relationship to a Teams team in Slack is the Workspace, which contains a collection of channels.</span></span> <span data-ttu-id="b7998-179">O diagrama a seguir demonstra três mapeamentos diferentes do Slack ao Teams, e orientações para escolher o caminho certo para cada Workspace.</span><span class="sxs-lookup"><span data-stu-id="b7998-179">The diagram below demonstrates 3 different Slack-to-Teams mappings, and guidance for picking the right one for each Workspace.</span></span>


|<span data-ttu-id="b7998-180">Mapeamento do Slack ao Teams</span><span class="sxs-lookup"><span data-stu-id="b7998-180">Slack-to-Teams mapping</span></span> |  |
|---------|---------|
|<span data-ttu-id="b7998-181">1 Slack Workspace: seta_para_direita: 1 equipe</span><span class="sxs-lookup"><span data-stu-id="b7998-181">1 Slack Workspace :arrow_right: 1 team</span></span>   | <span data-ttu-id="b7998-182">Para Slack workspaces menores que precisam menos do que 200 canais</span><span class="sxs-lookup"><span data-stu-id="b7998-182">For smaller Slack workspaces that need fewer than 200 channels</span></span><br><span data-ttu-id="b7998-183">Incluir um buffer para o crescimento e planejamento do canal privado</span><span class="sxs-lookup"><span data-stu-id="b7998-183">Include a buffer for growth and private channel planning</span></span>  |
|<span data-ttu-id="b7998-184">1 Slack Workspace: seta_para_direita: várias equipes</span><span class="sxs-lookup"><span data-stu-id="b7998-184">1 Slack Workspace :arrow_right: multiple teams</span></span>     | <span data-ttu-id="b7998-185">Use os dados de análise do Slack Workspace para criar agrupamentos lógicos de canais, que se tornam a base das equipes</span><span class="sxs-lookup"><span data-stu-id="b7998-185">Use your Slack Workspace analytics data to create logical channel groupings, which become the basis of your teams</span></span>        |
|<span data-ttu-id="b7998-186">2+ Slack Workspaces: seta_para_direita: várias equipes</span><span class="sxs-lookup"><span data-stu-id="b7998-186">2+ Slack Workspaces :arrow_right: multiple teams</span></span>     | <span data-ttu-id="b7998-187">Use os dados de análise do Slack Workspace para criar agrupamentos lógicos de equipes e de canais, que se tornam a base das equipes</span><span class="sxs-lookup"><span data-stu-id="b7998-187">Use your Slack Workspace analytics data to create logical team and channel groupings, which become the basis of your teams</span></span>        |

<span data-ttu-id="b7998-188">As soluções de terceiros têm estatísticas de uso para ajudá-lo a avaliar o quanto o canal está ativo e quantas postagens existem.</span><span class="sxs-lookup"><span data-stu-id="b7998-188">Third-party solutions have usage statistics to help you assess how active the channel is and how many posts there are.</span></span> <span data-ttu-id="b7998-189">Normalmente, os canais usados com frequência seriam incluídos no planejamento da equipe.</span><span class="sxs-lookup"><span data-stu-id="b7998-189">Typically, channels that are frequently used would be candidates to include in your team planning.</span></span>

> [!TIP]
> <span data-ttu-id="b7998-190">Guarde apenas o que é necessário para determinar quais canais devem ser recriados no Teams.</span><span class="sxs-lookup"><span data-stu-id="b7998-190">Retain only what is required in your approach to determine which channels to recreate in Teams.</span></span> <span data-ttu-id="b7998-191">Para saber mais, leia [Visão geral de equipes e canais](teams-channels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b7998-191">To learn more, read [Overview of teams and channels](teams-channels-overview.md).</span></span> 

#### <a name="team-planning"></a><span data-ttu-id="b7998-192">Planejamento de Equipe</span><span class="sxs-lookup"><span data-stu-id="b7998-192">Team Planning</span></span>
<span data-ttu-id="b7998-193">Ao usar o inventário de Canais compilados na seção de Planejamento acima, trabalhe com os proprietários e administradores do Slack para descobrir quais canais devem se tornar equipes e quais devem se tornar canais em uma equipe.</span><span class="sxs-lookup"><span data-stu-id="b7998-193">Using the Channel inventory you compiled in the Planning section above, work with your Slack owners and admins to figure out which channels should become teams and which ones should become channels in a team.</span></span> <span data-ttu-id="b7998-194">Use o Excel ou o PowerBI para ajudar nessa análise. Ambos podem fornecer informações adicionais que ajudam a orientar essas discussões sobre quais canais manter.</span><span class="sxs-lookup"><span data-stu-id="b7998-194">Use either Excel or PowerBI to help with this analysis - both can provide additional insights to help drive these discussions on which channels to retain.</span></span>

> [!TIP]
> <span data-ttu-id="b7998-195">Atualmente, o Teams têm um limite de 200 canais por equipe.</span><span class="sxs-lookup"><span data-stu-id="b7998-195">Teams currently has a 200-channel limit per team.</span></span> <span data-ttu-id="b7998-196">Se a sua lista de canais estiver chegando perto desse limite, descubra uma maneira de dividi-los em duas equipes diferentes.</span><span class="sxs-lookup"><span data-stu-id="b7998-196">If your list of channels is getting close to that limit, you should figure out a way to split them into two separate teams.</span></span>

### <a name="channel-history"></a><span data-ttu-id="b7998-197">Histórico de Canal</span><span class="sxs-lookup"><span data-stu-id="b7998-197">Channel History</span></span>

<span data-ttu-id="b7998-198">Existem soluções gratuitas no GitHub e soluções pagas que você pode usar, dependendo dos requisitos da sua organização para manter o Histórico de Canal de canais Públicos e Privados.</span><span class="sxs-lookup"><span data-stu-id="b7998-198">There are both free solutions on GitHub and paid solutions you can use, depending on your organization’s requirements to retain Channel History of Public and Private channels.</span></span> <span data-ttu-id="b7998-199">Além disso, isso poderia ser controlado por script no Teams.</span><span class="sxs-lookup"><span data-stu-id="b7998-199">Additionally, this could be scripted into Teams.</span></span>

<span data-ttu-id="b7998-200">Depois de configurar a sua nova estrutura de equipe e de canal no Teams, você poderá copiar os arquivos exportados para as bibliotecas de documentos apropriadas nos canais do Teams.</span><span class="sxs-lookup"><span data-stu-id="b7998-200">Once you’ve set up your new team and channel structure in Teams, you can copy the exported files into the appropriate document libraries in your Teams channels.</span></span>

<span data-ttu-id="b7998-201">Para automatizar a importação de seu conteúdo, há várias abordagens que você pode considerar.</span><span class="sxs-lookup"><span data-stu-id="b7998-201">To automate the importing of your content, there are several approaches you can consider.</span></span> <span data-ttu-id="b7998-202">Há soluções gratuitas no GitHub ([ChannelSurf](https://github.com/tamhinsf/ChannelSurf) ou [Slack Export Viewer](https://github.com/hfaran/slack-export-viewer)) e soluções de parceiros.</span><span class="sxs-lookup"><span data-stu-id="b7998-202">There are  free solutions on GitHub ([ChannelSurf](https://github.com/tamhinsf/ChannelSurf) or [Slack Export Viewer](https://github.com/hfaran/slack-export-viewer)) and partner solutions.</span></span> <span data-ttu-id="b7998-203">Escolha uma solução baseada nas necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="b7998-203">Choose a solution based on your organization’s needs.</span></span> 

### <a name="channel-files"></a><span data-ttu-id="b7998-204">Arquivos de Canal</span><span class="sxs-lookup"><span data-stu-id="b7998-204">Channel Files</span></span>

<span data-ttu-id="b7998-205">A maioria das soluções exportará arquivos.</span><span class="sxs-lookup"><span data-stu-id="b7998-205">Most solutions will export files.</span></span> <span data-ttu-id="b7998-206">No entanto, eles geralmente são fornecidos como links no Histórico de Canal que exigem uma chave de API para ser recuperada de forma programática.</span><span class="sxs-lookup"><span data-stu-id="b7998-206">However, they’re typically provided as links in the Channel History that require an API key to programmatically retrieve.</span></span>

<span data-ttu-id="b7998-207">Para arquivos armazenados no Slack, uma vez configurado suas equipes e canais em Teams, será possível copiá-los de forma programática do Slack para o canal de destino do Teams.</span><span class="sxs-lookup"><span data-stu-id="b7998-207">For files stored in Slack, once you’ve set up your teams and channels in Teams, you can programmatically copy them from Slack into the target Teams channel.</span></span>

<span data-ttu-id="b7998-208">O script a seguir recupera arquivos do Slack.</span><span class="sxs-lookup"><span data-stu-id="b7998-208">The following script retrieves files from Slack.</span></span> <span data-ttu-id="b7998-209">Ele pesquisa a especificada exportação do Slack no seu computador, cria uma pasta em cada canal de destino e baixa todos os arquivos para esse local.</span><span class="sxs-lookup"><span data-stu-id="b7998-209">It searches the specified Slack export on your computer, creates a folder in each target channel, and downloads all of the files to that location.</span></span> <span data-ttu-id="b7998-210">Existem soluções de terceiros que podem extrair dados.</span><span class="sxs-lookup"><span data-stu-id="b7998-210">Third-party solutions exist that can extract data.</span></span> <span data-ttu-id="b7998-211">Se precisar de ajuda com o PowerShell, leia [Introdução ao Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span><span class="sxs-lookup"><span data-stu-id="b7998-211">If you need help with PowerShell, read [Get started with Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span></span>



```azurepowershell
$ExportPath = ".\slackHistory"
$ExportContents = Get-ChildItem -path $ExportPath -Recurse
Function Get-TimeStamp {
    return "[{0:MM/dd/yy} {0:HH:mm:ss}]" -f (Get-Date)
}

class File {
    [string] $Name
    [string] $Title
    [string] $Channel
    [string] $DownloadURL
    [string] $MimeType
    [double] $Size
    [string] $ParentPath
    [string] $Time
}

$channelList = Get-Content -Raw -Path .\slackHistory\channels.json | ConvertFrom-Json
$Files = New-Object -TypeName System.Collections.ObjectModel.Collection["File"]

Write-Host -ForegroundColor Green "$(Get-TimeStamp) Starting Step 1 (processing channel export for files) of 2. Total Channel Count: $($channelList.Count)"
#Iterate through each Channel listed in the Archive
foreach ($channel in $channelList) {
    #Iterate through Channel folders from the Export
    foreach ($folder in $ExportContents)
    {
        #If Channel Name matches..
        if ($channel.name -eq $folder){
            $channelJsons = Get-ChildItem -Path $folder.FullName -File
            Write-Host -ForegroundColor White "$(Get-TimeStamp) Info: Starting to process $($channelJsons.Count) days of content for #$($channel.name)."
            #Start processing the daily JSON for files
            foreach ($json in $channelJsons){
                $currentJson = Get-Content -Raw -Path $json.FullName | ConvertFrom-Json
                #Write-Host -ForegroundColor Yellow "$(Get-TimeStamp) Info: Processing $($json.Name) in #$($channel.name).."
                #Iterate through every action
                foreach ($entry in $currentJson){
                    #If the action contained file(s)..
                    if($null -ne $entry.files){
                        #Iterate through each file and add it to the List of Files to download
                        foreach ($item in $entry.Files) {
                        $file = New-Object -TypeName File
                            if ($null -ne $item.url_private_download){
                                $file.Name = $item.name
                                $file.Title = $item.Title
                                $file.Channel = $channel.name
                                $file.DownloadURL = $item.url_private_download
                                $file.MimeType = $item.mimetype
                                $file.Size = $item.size
                                $file.ParentPath = $folder.FullName
                                $file.Time = $item.created
                                $files.Add($file)
                            }
                        }
                    }
                }
            }
        }
    }
}
Write-Host -ForegroundColor Green "$(Get-TimeStamp) Step 1 of 2 complete. `n"

Write-Host -ForegroundColor Green "$(Get-TimeStamp) Starting step 2 (creating folders and downloading files) of 2."
#Determine which Files folders need to be created
$FoldersToMake = New-Object System.Collections.ObjectModel.Collection["string"]
foreach ($file in $files){
    if ($FoldersToMake -notcontains $file.Channel){
        $FoldersToMake.Add($file.Channel)
    }
}

#Create Folders
foreach ($folder in $FoldersToMake){
    #$fullFolderPath = $file.ParentPath + "\Files"
    $fullFolderPath = $ExportPath +"\$($folder)"
    $fullFilesPath = $ExportPath +"\$($folder)\Files"
    if (-not (Test-Path $fullFilesPath)){
        New-Item -Path $fullFolderPath  -Name "Files" -ItemType "directory"
    }
}

#Downloading Files
foreach ($file in $files)
{
    Write-Host -ForegroundColor Yellow "$(Get-TimeStamp) Downloading $($file.Name)."
    $fullFilePath = $file.ParentPath + "\Files\" + $file.Name
        if (-not (Test-Path $fullFilePath)){
            try{
                $request = (New-Object System.Net.WebClient).DownloadFile($file.DownloadURL, $fullFilePath)
            }
            catch [System.Net.WebException]{
                Write-Host -ForegroundColor Red "$(Get-TimeStamp) Error: Unable to download $($file.Name) to $($fullFilePath)"
            }   
        }
        else {
            try{
                $extensionPosition = $file.name.LastIndexOf('.')
                $splitFileName = $file.name.Substring(0,$extensionPosition)
                $splitFileExtention = $file.name.Substring($extensionPosition)
                $newFileName = $splitFileName + $file.Time + $splitFileExtention
                $fullFilePath = $file.ParentPath + "\Files\" + $newFileName
                $request = (New-Object System.Net.WebClient).DownloadFile($file.DownloadURL, $fullFilePath)
            }
            catch [System.Net.WebException]{
                Write-Host -ForegroundColor Red "$(Get-TimeStamp) Error: Unable to download $($file.Name) to $($fullFilePath)"
            }   
        }
}
Write-Host -ForegroundColor Green "$(Get-TimeStamp) Step 2 of 2 complete. `n"
Write-Host -ForegroundColor Green "$(Get-TimeStamp) Exiting.."
```


### <a name="apps-and-custom-integrations"></a><span data-ttu-id="b7998-212">Aplicativos e Integrações Personalizadas</span><span class="sxs-lookup"><span data-stu-id="b7998-212">Apps and Custom Integrations</span></span>
<span data-ttu-id="b7998-213">Examine sua lista de aplicativos do Slack e integrações personalizadas (com configurações) e decida quais você deseja mover para o Teams.</span><span class="sxs-lookup"><span data-stu-id="b7998-213">Review your list of Slack apps and custom integrations (with configurations) and decide which ones you want to move to Teams.</span></span> <span data-ttu-id="b7998-214">Confira o Teams Marketplace para ver se um aplicativo está disponível.</span><span class="sxs-lookup"><span data-stu-id="b7998-214">Check the Teams Marketplace to see if an app is available.</span></span> <span data-ttu-id="b7998-215">Caso contrário, existem alternativas possíveis.</span><span class="sxs-lookup"><span data-stu-id="b7998-215">If not, there are likely alternatives.</span></span> 

<span data-ttu-id="b7998-216">Para descobrir quais aplicativos adicionar ao Teams, é importante entender como o aplicativo está sendo usado.</span><span class="sxs-lookup"><span data-stu-id="b7998-216">To figure out which apps to add to Teams, it’s important to understand how the app is being used.</span></span> <span data-ttu-id="b7998-217">Ao fazer a pergunta "que funcionalidade o aplicativo fornece para este canal?", você aprenderá sobre o resultado que o aplicativo está fornecendo.</span><span class="sxs-lookup"><span data-stu-id="b7998-217">By asking the question "what functionality is the app providing to this channel?", you'll learn about the outcome the app is delivering.</span></span> 

<span data-ttu-id="b7998-218">Em muitos casos, os aplicativos recebem basicamente dados direcionados a eventos de um serviço externo (por exemplo, sistema de monitoramento) e enviam uma mensagem para o Slack.</span><span class="sxs-lookup"><span data-stu-id="b7998-218">In many cases, apps primarily receive event-driven data from an external service (for example, monitoring system) and push a message into Slack.</span></span> <span data-ttu-id="b7998-219">Você pode obter o mesmo resultado usando um Conector do Microsoft 365, que pode enviar mensagens no Teams com base em eventos.</span><span class="sxs-lookup"><span data-stu-id="b7998-219">You can achieve the same outcome by using a Microsoft 365 Connector that can push messages into Teams based on events.</span></span>

<span data-ttu-id="b7998-220">A seguir estão exemplos de soluções do Slack em que um Conector do Office 365 foi usado no Teams para integração.</span><span class="sxs-lookup"><span data-stu-id="b7998-220">Below are examples of Slack solutions where an Office 365 Connector was used in Teams for integration.</span></span>
- <span data-ttu-id="b7998-221">Ansível</span><span class="sxs-lookup"><span data-stu-id="b7998-221">Ansible</span></span>
  - <span data-ttu-id="b7998-222">Os alertas podem ser enviados ao Teams por meio de [Webhook ansível](https://docs.ansible.com/ansible-tower/latest/html/userguide/notifications.html#webhook)</span><span class="sxs-lookup"><span data-stu-id="b7998-222">Alerts can be sent to Teams via [Ansible webhook](https://docs.ansible.com/ansible-tower/latest/html/userguide/notifications.html#webhook)</span></span>
- <span data-ttu-id="b7998-223">New Relic</span><span class="sxs-lookup"><span data-stu-id="b7998-223">New Relic</span></span>
  - <span data-ttu-id="b7998-224">Confira a solução de usuário para [Enviar alertas New Relic ao Teams](https://discuss.newrelic.com/t/new-relic-alerts-not-working-with-microsoft-teams/48609/3)</span><span class="sxs-lookup"><span data-stu-id="b7998-224">Check out this user solution for [sending New Relic alerts to Teams](https://discuss.newrelic.com/t/new-relic-alerts-not-working-with-microsoft-teams/48609/3)</span></span>
- <span data-ttu-id="b7998-225">Nagios </span><span class="sxs-lookup"><span data-stu-id="b7998-225">Nagios</span></span>
  - <span data-ttu-id="b7998-226">Hoje, os alertas podem ser integrados via conectores.</span><span class="sxs-lookup"><span data-stu-id="b7998-226">Alerts can be integrated today via Connectors.</span></span> <span data-ttu-id="b7998-227">https://github.com/isaac-galvan/nagios-teams-notify</span><span class="sxs-lookup"><span data-stu-id="b7998-227">https://github.com/isaac-galvan/nagios-teams-notify</span></span>
- <span data-ttu-id="b7998-228">ZenDesk</span><span class="sxs-lookup"><span data-stu-id="b7998-228">ZenDesk</span></span>
  - <span data-ttu-id="b7998-229">O aplicativo existe no Teams Store</span><span class="sxs-lookup"><span data-stu-id="b7998-229">App exists in Teams Store</span></span>
- <span data-ttu-id="b7998-230">Jenkins</span><span class="sxs-lookup"><span data-stu-id="b7998-230">Jenkins</span></span>
  - <span data-ttu-id="b7998-231">Os alertas podem ser enviados ao Teams usando o [Conector do Office 365 do Jenkins](https://plugins.jenkins.io/Office-365-Connector)</span><span class="sxs-lookup"><span data-stu-id="b7998-231">Alerts can be sent to Teams using [Jenkins’s Office 365 Connector](https://plugins.jenkins.io/Office-365-Connector)</span></span>


### <a name="user-readiness-and-adoption-plan"></a><span data-ttu-id="b7998-232">Plano de adoção e preparação do usuário </span><span class="sxs-lookup"><span data-stu-id="b7998-232">User readiness and adoption plan</span></span>
<span data-ttu-id="b7998-233">A base de qualquer implantação bem-sucedida de software depende de como os usuários estão preparados para a mudança.</span><span class="sxs-lookup"><span data-stu-id="b7998-233">The cornerstone of any successful software deployment hinges on how prepared users are for the change.</span></span> <span data-ttu-id="b7998-234">Os usuários da organização que usam o Slack entenderão facilmente os conceitos do Teams, mas ainda assim, será necessário um treinamento para ajudá-los a fazer uma transição tranquila.</span><span class="sxs-lookup"><span data-stu-id="b7998-234">Users in your organization using Slack will easily understand Teams concepts, but training is still needed to help them make a smooth transition.</span></span> <span data-ttu-id="b7998-235">Para obter um conjunto abrangente de recursos de adoção de equipes, vá para [Hub de adoção do Teams](adopt-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="b7998-235">For a comprehensive set of Teams adoption resources, go to the [Teams adoption hub](adopt-microsoft-teams-landing-page.md).</span></span>

<span data-ttu-id="b7998-236">Por exemplo, os dois produtos apresentam canais, mas são usados de forma diferente em cada produto.</span><span class="sxs-lookup"><span data-stu-id="b7998-236">For example, both products feature channels, but they’re used differently in each product.</span></span> <span data-ttu-id="b7998-237">Por exemplo, geralmente um Canal no Slack é usado como um chat no Teams para conversas transacionais de curto prazo.</span><span class="sxs-lookup"><span data-stu-id="b7998-237">For example, often a Channel in Slack is used like a chat in Teams for short-term, transactional conversations.</span></span> <span data-ttu-id="b7998-238">Outras diferenças notáveis são as conversas encadeadas/não encadeadas e as configurações de notificação de ajuste.</span><span class="sxs-lookup"><span data-stu-id="b7998-238">Other notable differences are around threaded/non-threaded conversations and tuning notification settings.</span></span>

<span data-ttu-id="b7998-239">Confira nossa rica biblioteca de [Treinamento para usuários finais do Teams](enduser-training.md).</span><span class="sxs-lookup"><span data-stu-id="b7998-239">Check out our rich library of [End-user Teams training](enduser-training.md).</span></span> 

## <a name="move-to-teams"></a><span data-ttu-id="b7998-240">Mover para o Teams</span><span class="sxs-lookup"><span data-stu-id="b7998-240">Move to Teams</span></span> 
<span data-ttu-id="b7998-241">Agora que o seu plano de transição está definido, comece a criar suas equipes e canais no Teams.</span><span class="sxs-lookup"><span data-stu-id="b7998-241">Now that your transition plan is defined, you can begin creating your teams and channels in Teams.</span></span> 

<span data-ttu-id="b7998-242">Depois de criar as equipes e canais, comece a copiar arquivos dos canais do Slack para o Teams e a configurar seus aplicativos.</span><span class="sxs-lookup"><span data-stu-id="b7998-242">Once you’ve created your teams & channels, begin copying files from Slack channels into Teams and configuring your apps.</span></span> <span data-ttu-id="b7998-243">Se você estiver usando uma solução para manter o histórico, ele ainda pode ser configurado também.</span><span class="sxs-lookup"><span data-stu-id="b7998-243">If you’re using a solution to retain history, that can be configured now as well.</span></span> <span data-ttu-id="b7998-244">Em seguida, você estará pronto para começar a licenciar usuários (caso eles ainda não estejam licenciados) e adicioná-los às equipes apropriadas.</span><span class="sxs-lookup"><span data-stu-id="b7998-244">Then you’re ready to start licensing users (if they aren’t licensed already) and adding them to the appropriate teams.</span></span> <span data-ttu-id="b7998-245">Para reduzir a necessidade de exportações adicionais e cópias de arquivos, considere remover o acesso ao Slack em uma data acordada que coincida com a adição de cada usuário à equipe.</span><span class="sxs-lookup"><span data-stu-id="b7998-245">To reduce the need for additional exports and file copies, consider removing Slack access at an agreed-upon date that coincides with each user’s addition to the team.</span></span> <span data-ttu-id="b7998-246">Isso evita que você precise novamente exportar e importar alterações delta de arquivos e histórico.</span><span class="sxs-lookup"><span data-stu-id="b7998-246">This avoids needing to re-export and import delta changes on files and history.</span></span>

<span data-ttu-id="b7998-247">Siga as etapas no diagrama a seguir para distribuir o Teams em sua organização.</span><span class="sxs-lookup"><span data-stu-id="b7998-247">Follow the steps in the diagram below to roll out Teams in your organization.</span></span> <span data-ttu-id="b7998-248">Para saber mais, confira [Como distribuir o Teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="b7998-248">For more information, check out [How to roll out Teams](How-to-roll-out-teams.md).</span></span>


:::image type="content" source="media/migrate-slack-to-teams-image4.png" alt-text="Diagrama que lista as etapas de mudança para o Teams a partir do Slack.":::
