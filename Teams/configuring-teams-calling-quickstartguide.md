---
title: Guia de Início Rápido - Como configurar Planos de Chamadas no Microsoft Teams
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor, lolaj
search.appverid: MET150
description: Guia de Início Rápido para configurar Planos de Chamadas no Microsoft Teams.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 86a4862a547df6f50d0831616a42824d9f8c3287
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882094"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="14bd3-103">Guia de Início Rápido: como configurar Planos de Chamadas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="14bd3-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="14bd3-104">Este guia o ajudará a estabelecer um grupo de usuários para que eles possam explorar os Planos de Chamadas no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="14bd3-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="14bd3-105">Leia o anúncio feito em 12 de dezembro de 2017, dos Planos de Chamadas no Microsoft Teams: [A comunicação inteligente avança com as chamadas do Microsoft Teams](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="14bd3-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="14bd3-106">Recomendamos que, em paralelo com este Guia de Início Rápido, você use as [orientações prática](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) e o [FastTrack](https://aka.ms/cloudvoice) para planejar e realizar uma distribuição bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="14bd3-106">We recommend that, in parallel with this quick-start guide, you use our [practical guidance](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="14bd3-107">Com a inclusão dos Planos de Chamadas, um recurso do Office 365 acionado pelo Skype for Business, agora você pode usar o Microsoft Teams para fazer e receber chamadas de telefones fixos e celulares pela PSTN (Rede Telefônica Pública Comutada).</span><span class="sxs-lookup"><span data-stu-id="14bd3-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Fazendo chamadas no Microsoft Teams](media/Calling_in_Teams.png)

## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="14bd3-109">Pré-requisitos para habilitar a guia **Chamadas** no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="14bd3-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="14bd3-110">Para habilitar a guia **Chamadas** no Microsoft Teams e permitir que os usuários façam e recebam chamadas PSTN, será necessário provisionar os usuários para o Sistema de Telefonia e os Planos de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="14bd3-110">To enable the **Calls** tab in Teams and allow your users to make and receive PSTN calls, you will need provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="14bd3-111">Para saber como configurar, leia [Configurar Planos de Chamadas](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="14bd3-111">To learn how to set this up, read [Set up Calling Plans](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans).</span></span>

## <a name="teams-interop-policy-configuration"></a><span data-ttu-id="14bd3-112">Configuração da política de interoperabilidade do Teams</span><span class="sxs-lookup"><span data-stu-id="14bd3-112">Teams interop policy configuration</span></span>
<span data-ttu-id="14bd3-113">Para permitir que o Teams comece a receber chamadas, você precisa atualizar a política de atualização do Teams e a política de interoperabilidade do Teams usando o [Centro de Administração do Microsoft Teams e do Skype for Business](https://aka.ms/teamsadmincenter) ou uma sessão remota do Windows PowerShell com os cmdlets do Skype for Business [`*-CsTeamsUpgradePolicy` e do `*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) para redirecionar chamadas ao Teams.</span><span class="sxs-lookup"><span data-stu-id="14bd3-113">To enable Teams to begin receiving calls, you'll need to update Teams upgrade policy and Teams interop policy, using [Microsoft Teams & Skype for Business Admin Center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the Skype for Business [`*-CsTeamsUpgradePolicy` and `*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) cmdlets, to redirect calls to Teams.</span></span>

<span data-ttu-id="14bd3-114">Para obter mais informações sobre a política de atualização do Teams e a política de interoperabilidade do Teams, consulte [Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="14bd3-114">For more information about Teams upgrade policy and Teams interop policy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).</span></span>

> [!TIP]
> <span data-ttu-id="14bd3-115">Para encontrar os cmdlets do PowerShell necessários, digite “CsTeamsUpgradePolicy” ou “CsTeamsInteropPolicy” na caixa **Filtrar** na [documentação de cmdlets do PowerShell para o Skype for Business](https://docs.microsoft.com/powershell/module/skype).</span><span class="sxs-lookup"><span data-stu-id="14bd3-115">To find the PowerShell cmdlets you need, type "CsTeamsInteropPolicy" in the **Filter** box in the [Skype for Business PowerShell cmdlet documentation](https://docs.microsoft.com/powershell/module/skype).</span></span>

### <a name="default-teams-upgrade-and-interop-policies"></a><span data-ttu-id="14bd3-116">Políticas de interoperabilidade e atualização padrão do Teams</span><span class="sxs-lookup"><span data-stu-id="14bd3-116">Default Teams upgrade and interop policies</span></span>
<span data-ttu-id="14bd3-117">O Teams tem uma configuração de política padrão criada para garantir que os fluxos de trabalho de negócios existentes não sejam interrompidos durante a implantação do Teams.</span><span class="sxs-lookup"><span data-stu-id="14bd3-117">Teams has a default policy configuration designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="14bd3-118">Por padrão, as chamadas VoIP, PSTN e federadas para seus usuários continuarão sendo encaminhadas para o Skype for Business até que você atualize a política para habilitar as chamadas de entrada para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="14bd3-118">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span> <span data-ttu-id="14bd3-119">Isso garante que não haja interrupções involuntárias nos serviços de voz quando você começa a testar e implantar o Teams.</span><span class="sxs-lookup"><span data-stu-id="14bd3-119">This ensures that there are no unintended interruptions in voice services as you start to pilot and deploy Teams.</span></span>

<span data-ttu-id="14bd3-120">Por padrão, a política de atualização do Teams é mantida no modo herdado que honrará a política de interoperabilidade do Teams para determinar onde os bate-papos e as chamadas devem ser encaminhados: Teams ou Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="14bd3-120">Teams upgrade policy by default is kept at legacy mode that will honor Teams interop policy to determine where chats and calls are to be routed--Teams or Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="14bd3-121">Os comportamentos da política de atualização do Teams e da política de interoperabilidade do Teams serão alterados em breve, conforme descrito em [Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span><span class="sxs-lookup"><span data-stu-id="14bd3-121">The behaviors of Teams upgrade policy and Teams interop policy will soon change as described in [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="14bd3-122">A política de interoperabilidade do Teams tem a seguinte configuração padrão:</span><span class="sxs-lookup"><span data-stu-id="14bd3-122">Teams interop policy has the following default configuration:</span></span>

    Identity                   : Global
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

<span data-ttu-id="14bd3-123">Por padrão, o comportamento da configuração padrão inclui:</span><span class="sxs-lookup"><span data-stu-id="14bd3-123">The behaviors of the default configuration are the following:</span></span>
* <span data-ttu-id="14bd3-124">**Para os clientes existentes do Skype for Business**, esta política tem como objetivo garantir que as chamadas do Skype for Business sejam direcionadas para o Skype for Business, e as chamadas do Microsoft Teams sejam direcionadas para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="14bd3-124">**For existing Skype for Business customers**, this policy is designed to ensure that Skype for Business calls are directed to Skype for Business, and Teams calls are directed to Teams.</span></span> <span data-ttu-id="14bd3-125">As chamadas PSTN e federadas serão direcionadas para o Skype for Business quando essa política estiver em vigor.</span><span class="sxs-lookup"><span data-stu-id="14bd3-125">PSTN and federated calls will be directed to Skype for Business when this policy is in effect.</span></span>
* <span data-ttu-id="14bd3-126">**Para os clientes que não têm o Skype for Business**, quando em vigor, além das chamadas entre usuários do Microsoft Teams, somente as chamadas PSTN de saída estarão disponíveis no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="14bd3-126">**For customers without Skype for Business**, when in effect, in addition to calls among Teams users, only outbound PSTN calling will be available in Teams.</span></span> <span data-ttu-id="14bd3-127">Para receber chamadas PSTN no Microsoft Teams, será necessário alterar a política de interoperabilidade do Microsoft Teams atribuída a seus usuários.</span><span class="sxs-lookup"><span data-stu-id="14bd3-127">You will need to alter the Teams interop policy assigned to your users to receive PSTN calls in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="14bd3-128">A guia Chamadas estará habilitada no Microsoft Teams para os usuários que foram provisionados com licenças do Sistema de Telefonia e de Planos de Chamadas para uso com o Skype for Business Online e que têm configurada a política de interoperabilidade global padrão do Microsoft Teams, e eles poderão fazer chamadas PSTN de saída no Microsoft Teams sem a necessidade de qualquer ação por parte dos administradores.</span><span class="sxs-lookup"><span data-stu-id="14bd3-128">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online, and configured with the default global Teams interop policy, will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a><span data-ttu-id="14bd3-129">Configuração do Teams para receber chamadas PSTN de entrada</span><span class="sxs-lookup"><span data-stu-id="14bd3-129">Configuring Teams to receive inbound PSTN calls</span></span>
<span data-ttu-id="14bd3-130">Para receber chamadas PSTN de entrada no Teams, é necessário configurar o Teams como aplicativo de chamadas padrão, aplicando a política de atualização do Teams com a política de interoperabilidade do Teams correspondente que define o parâmetro `CallingDefaultClient` para o Teams.</span><span class="sxs-lookup"><span data-stu-id="14bd3-130">To receive inbound PSTN calls in Teams, you will need to configure Teams as the default calling application by applying Teams interop policy with `CallingDefaultClient` parameter set to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="14bd3-131">Recomendamos aplicar essa configuração a um conjunto inicial de usuários para explorar as incríveis novas funcionalidades de chamadas do Microsoft Teams antes de fazer alterações mais abrangentes ou em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="14bd3-131">We recommend that you apply this configuration to an initial set of users to explore these exciting new calling capabilities in Teams prior to making wider or organization-level changes.</span></span>

<span data-ttu-id="14bd3-132">Se você optar por continuar a usar a política de atualização herdada do Teams, use a seguinte política de interoperabilidade do Teams pré-configurada para rotear chamadas PSTN de entrada para o Teams:</span><span class="sxs-lookup"><span data-stu-id="14bd3-132">If you choose to continue to use the legacy Teams upgrade policy, use the following preconfigured Teams interop policy to route inbound PSTN calling to Teams:</span></span>

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

<span data-ttu-id="14bd3-133">Se você optar por usar a política de atualização do Teams atualizada, será necessário atribuir o modo TeamsOnly aos usuários.</span><span class="sxs-lookup"><span data-stu-id="14bd3-133">If you choose to use the updated Teams upgrade policy, you need to assign TeamsOnly mode to your users.</span></span>

<span data-ttu-id="14bd3-134">Os comportamentos da política acima são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="14bd3-134">The behaviors of the policy above are the following:</span></span>
* <span data-ttu-id="14bd3-135">**Para os clientes existentes do Skype for Business**, esta política tem como objetivo redirecionar as chamadas de entrada para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="14bd3-135">**For existing Skype for Business customers**, this policy is designed to redirect incoming calls to Teams.</span></span> <span data-ttu-id="14bd3-136">Isso inclui chamadas VoIP (do Teams e do Skype for Business) e chamadas PSTN.</span><span class="sxs-lookup"><span data-stu-id="14bd3-136">This includes both VoIP (from Teams and Skype for Business) and PSTN calls.</span></span> 
* <span data-ttu-id="14bd3-137">**Para os clientes que não têm o Skype for Business**, quando em vigor, as chamadas PSTN serão recebidas no Teams.</span><span class="sxs-lookup"><span data-stu-id="14bd3-137">**For customers without Skype for Business**, when in effect, PSTN calls will be received in Teams.</span></span>

> [!WARNING]
> <span data-ttu-id="14bd3-138">No momento, a alteração de `CallingDefaultClient` para o Teams também afeta as chamadas para telefones IP do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="14bd3-138">Currently, changing `CallingDefaultClient` to Teams will also affect calls to Skype for Business IP phones.</span></span> <span data-ttu-id="14bd3-139">As chamadas de entrada não serão recebidas em telefones e vão tocar somente nos clientes do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="14bd3-139">Incoming calls will not be received on the phones and will only ring Teams clients.</span></span> <span data-ttu-id="14bd3-140">Consulte o [Roteiro de recursos do Skype for Business para o Microsoft Teams](https://aka.ms/skype2teamsroadmap) para obter informações sobre o suporte para telefones SIP certificados existentes.</span><span class="sxs-lookup"><span data-stu-id="14bd3-140">Please consult the [Skype for Business to Microsoft Teams Capabilities Roadmap](https://aka.ms/skype2teamsroadmap) for information about support for existing certified SIP phones.</span></span>

### <a name="how-to-configure-users-to-receive-pstn-calls-in-teams"></a><span data-ttu-id="14bd3-141">Como configurar os usuários para receber chamadas PSTN no Teams</span><span class="sxs-lookup"><span data-stu-id="14bd3-141">How to configure users to receive PSTN calls in Teams</span></span>
<span data-ttu-id="14bd3-142">Ao usar a política de atualização do Teams herdada, aplique a política de interoperabilidade do Teams, conforme descrito acima, via sessão do Windows PowerShell remoto do Skype for Business para redirecionar as chamadas para o Teams:</span><span class="sxs-lookup"><span data-stu-id="14bd3-142">Apply the Teams interop policy as described above via Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

<span data-ttu-id="14bd3-143">Se você optar por usar o modo TeamsOnly, será possível alterar o modo de coexistência do usuário para TeamsOnly por meio do Centro de Administração do Microsoft Teams e do Skype for Business ou sessão do Windows PowerShell remoto do Skype for Business para redirecionar chamadas para o Teams:</span><span class="sxs-lookup"><span data-stu-id="14bd3-143">If you choose to use TeamsOnly mode, you can change the user's coexistence mode to TeamsOnly via Microsoft Teams & Skype for Business Admin Center, or via Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsUpgradePolicy -PolicyName tag:UpgradeToTeams -Identity user@contoso.com
    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="see-also"></a><span data-ttu-id="14bd3-144">Consulte também</span><span class="sxs-lookup"><span data-stu-id="14bd3-144">See also</span></span>
[<span data-ttu-id="14bd3-145">Configurar Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="14bd3-145">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="14bd3-146">Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="14bd3-146">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="14bd3-147">Orientações práticas para Sistema de Telefonia com Planos de Chamadas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="14bd3-147">Practical Guidance for Phone System with Calling Plans in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[<span data-ttu-id="14bd3-148">Referência de cmdlets do PowerShell para o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="14bd3-148">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

[<span data-ttu-id="14bd3-149">Referência de cmdlets do PowerShell para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="14bd3-149">Teams PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/teams)
