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
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- Teams_ITAdmin_Training
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e1d2fd7a9b999d98109e732b3bdbbba16f26e3bf
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30460568"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="90454-103">Guia de Início Rápido: como configurar Planos de Chamadas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="90454-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="90454-104">Este guia o ajudará a estabelecer um grupo de usuários para que eles possam explorar os Planos de Chamadas no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="90454-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="90454-105">Leia o anúncio feito em 12 de dezembro de 2017, dos Planos de Chamadas no Microsoft Teams: [A comunicação inteligente avança com as chamadas do Microsoft Teams](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="90454-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="90454-106">Recomendamos que, em paralelo com este guia de início rápido, você leia [O sistema telefônico com planos de chamada](calling-plan-landing-page.md) e [FastTrack](https://aka.ms/cloudvoice) planejar e a unidade uma distribuição bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="90454-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="90454-107">Com a inclusão dos Planos de Chamadas, um recurso do Office 365 acionado pelo Skype for Business, agora você pode usar o Microsoft Teams para fazer e receber chamadas de telefones fixos e celulares pela PSTN (Rede Telefônica Pública Comutada).</span><span class="sxs-lookup"><span data-stu-id="90454-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Fazendo chamadas no Microsoft Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="90454-109">Pré-requisitos para habilitar a guia **Chamadas** no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="90454-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="90454-110">Para habilitar a guia **chamadas** em equipes os usuários precisam ter o 1:1 chamando ativados nas equipes e usando um cliente de equipes que ofereça suporte a chamada de equipes de 1:1.</span><span class="sxs-lookup"><span data-stu-id="90454-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="90454-111">Para saber como gerenciar 1:1 chamando em equipes, leia [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="90454-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="90454-112">Para saber quais clientes suportam a chamada, leia [limites e as especificações para equipes da Microsoft](https://docs.microsoft.com/en-us/microsoftteams/limits-specifications-teams).</span><span class="sxs-lookup"><span data-stu-id="90454-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](https://docs.microsoft.com/en-us/microsoftteams/limits-specifications-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="90454-113">Atualmente, caixa postal não estarão disponível na guia chamadas, a menos que o usuário está habilitado para chamadas PSTN.</span><span class="sxs-lookup"><span data-stu-id="90454-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="90454-114">Pré-requisitos para habilitar o **Teclado de discagem** em equipes</span><span class="sxs-lookup"><span data-stu-id="90454-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="90454-115">Para habilitar a guia **Teclado de discagem** em equipes e permitir que os usuários façam e recebam chamadas PSTN, você precisará provisionar usuários para o sistema telefônico e planos de chamada.</span><span class="sxs-lookup"><span data-stu-id="90454-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="90454-116">Para saber como configurar planos de chamada, leia [Configurar planos de chamada](https://docs.microsoft.com/en-us/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="90454-116">To learn how to set up Calling Plans, read [Set up Calling Plans](https://docs.microsoft.com/en-us/microsoftteams/set-up-calling-plans).</span></span>

> [!NOTE]
> <span data-ttu-id="90454-117">Você também pode usar o roteamento direto para permitir que os usuários Obrigat e receber chamadas PSTN.</span><span class="sxs-lookup"><span data-stu-id="90454-117">You can also use Direct Routing to allow your users to mand and receive PSTN calls.</span></span> <span data-ttu-id="90454-118">Para saber como configurar o roteamento direto, leia a [Configurar o roteamento direto](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure).</span><span class="sxs-lookup"><span data-stu-id="90454-118">To learn how to set up Direct Routing, read [Configure Direct Routing](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure).</span></span>

## <a name="teams-interop-policy-configuration"></a><span data-ttu-id="90454-119">Configuração da política de interoperabilidade do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="90454-119">Teams interop policy configuration</span></span>
<span data-ttu-id="90454-120">Para permitir que equipes começar a receber chamadas, você precisará atualizar a política de atualização de equipes e política de interoperabilidade de equipes, usando o [Centro de administração de equipes da Microsoft](https://aka.ms/teamsadmincenter) ou usando uma sessão remota do Windows PowerShell com o Skype para negócios [ `*-CsTeamsUpgradePolicy` e `*-CsTeamsInteropPolicy` ](https://docs.microsoft.com/powershell/module/skype) cmdlets para redirecionar chamadas às equipes.</span><span class="sxs-lookup"><span data-stu-id="90454-120">To enable Teams to begin receiving calls, you'll need to update Teams upgrade policy and Teams interop policy, using [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the Skype for Business [`*-CsTeamsUpgradePolicy` and `*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) cmdlets, to redirect calls to Teams.</span></span>

<span data-ttu-id="90454-121">Para obter mais informações sobre a política de atualização de equipes e política de interoperabilidade de equipes, consulte [migração e orientações de interoperabilidade para organizações que usam equipes em conjunto com o Skype para negócios](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="90454-121">For more information about Teams upgrade policy and Teams interop policy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).</span></span>

> [!TIP]
> <span data-ttu-id="90454-122">Para localizar os cmdlets do PowerShell que você precisa, digite "CsTeamsUpgradePolicy" ou "CsTeamsInteropPolicy" na caixa **filtro** no [Skype para documentação de cmdlet do PowerShell de negócios](https://docs.microsoft.com/powershell/module/skype).</span><span class="sxs-lookup"><span data-stu-id="90454-122">To find the PowerShell cmdlets you need, type "CsTeamsUpgradePolicy" or "CsTeamsInteropPolicy" in the **Filter** box in the [Skype for Business PowerShell cmdlet documentation](https://docs.microsoft.com/powershell/module/skype).</span></span>

### <a name="default-teams-upgrade-and-interop-policies"></a><span data-ttu-id="90454-123">Padrão às equipes políticas de atualização e interoperabilidade</span><span class="sxs-lookup"><span data-stu-id="90454-123">Default Teams upgrade and interop policies</span></span>
<span data-ttu-id="90454-124">O Microsoft Teams tem uma configuração de política padrão criada para garantir que os fluxos de trabalho de negócios existentes não sejam interrompidos durante a implantação do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="90454-124">Teams has a default policy configuration designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="90454-125">Por padrão, as chamadas VoIP, PSTN e federadas para seus usuários continuarão sendo encaminhadas para o Skype for Business até que você atualize a política para habilitar as chamadas de entrada para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="90454-125">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span> <span data-ttu-id="90454-126">Isso garante que não haja interrupções involuntárias nos serviços de voz quando você começa a testar e implantar o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="90454-126">This ensures that there are no unintended interruptions in voice services as you start to pilot and deploy Teams.</span></span>

<span data-ttu-id="90454-127">As equipes de política de atualização por padrão é mantida em modo herdado que aceita a diretiva de interoperabilidade de equipes para determinar onde bate-papos e chamadas devem ser roteadas – equipes ou Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="90454-127">Teams upgrade policy by default is kept at legacy mode that will honor Teams interop policy to determine where chats and calls are to be routed--Teams or Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="90454-128">Os comportamentos de equipes atualizar a política e política de interoperabilidade de equipes em breve será alterada conforme descrito na [migração e orientações de interoperabilidade para organizações que usam equipes em conjunto com o Skype para negócios](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span><span class="sxs-lookup"><span data-stu-id="90454-128">The behaviors of Teams upgrade policy and Teams interop policy will soon change as described in [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="90454-129">A política de interoperabilidade do Microsoft Teams tem a seguinte configuração padrão:</span><span class="sxs-lookup"><span data-stu-id="90454-129">Teams interop policy has the following default configuration:</span></span>

    Identity                   : Global
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

<span data-ttu-id="90454-130">Por padrão, o comportamento da configuração padrão inclui:</span><span class="sxs-lookup"><span data-stu-id="90454-130">The behaviors of the default configuration are the following:</span></span>
* <span data-ttu-id="90454-131">**Para os clientes existentes do Skype for Business**, esta política tem como objetivo garantir que as chamadas do Skype for Business sejam direcionadas para o Skype for Business, e as chamadas do Microsoft Teams sejam direcionadas para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="90454-131">**For existing Skype for Business customers**, this policy is designed to ensure that Skype for Business calls are directed to Skype for Business, and Teams calls are directed to Teams.</span></span> <span data-ttu-id="90454-132">As chamadas PSTN e federadas serão direcionadas para o Skype for Business quando essa política estiver em vigor.</span><span class="sxs-lookup"><span data-stu-id="90454-132">PSTN and federated calls will be directed to Skype for Business when this policy is in effect.</span></span>
* <span data-ttu-id="90454-133">**Para os clientes que não têm o Skype for Business**, quando em vigor, além das chamadas entre usuários do Microsoft Teams, somente as chamadas PSTN de saída estarão disponíveis no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="90454-133">**For customers without Skype for Business**, when in effect, in addition to calls among Teams users, only outbound PSTN calling will be available in Teams.</span></span> <span data-ttu-id="90454-134">Para receber chamadas PSTN no Microsoft Teams, será necessário alterar a política de interoperabilidade do Microsoft Teams atribuída a seus usuários.</span><span class="sxs-lookup"><span data-stu-id="90454-134">You will need to alter the Teams interop policy assigned to your users to receive PSTN calls in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="90454-135">A guia Chamadas estará habilitada no Microsoft Teams para os usuários que foram provisionados com licenças do Sistema de Telefonia e de Planos de Chamadas para uso com o Skype for Business Online e que têm configurada a política de interoperabilidade global padrão do Microsoft Teams, e eles poderão fazer chamadas PSTN de saída no Microsoft Teams sem a necessidade de qualquer ação por parte dos administradores.</span><span class="sxs-lookup"><span data-stu-id="90454-135">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online, and configured with the default global Teams interop policy, will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a><span data-ttu-id="90454-136">Configuração do Microsoft Teams para receber chamadas PSTN de entrada</span><span class="sxs-lookup"><span data-stu-id="90454-136">Configuring Teams to receive inbound PSTN calls</span></span>
<span data-ttu-id="90454-137">Para receber chamadas de PSTN de entrada em equipes, você precisará configurar equipes como o aplicativo de chamada pela aplicação da diretiva de atualização de equipes com a política de interoperabilidade de equipes correspondente que define o padrão `CallingDefaultClient` parâmetro às equipes.</span><span class="sxs-lookup"><span data-stu-id="90454-137">To receive inbound PSTN calls in Teams, you will need to configure Teams as the default calling application by applying Teams upgrade policy with the corresponding Teams interop policy that sets `CallingDefaultClient` parameter to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="90454-138">Recomendamos aplicar essa configuração a um conjunto inicial de usuários para explorar as incríveis novas funcionalidades de chamadas do Microsoft Teams antes de fazer alterações mais abrangentes ou em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="90454-138">We recommend that you apply this configuration to an initial set of users to explore these exciting new calling capabilities in Teams prior to making wider or organization-level changes.</span></span>

<span data-ttu-id="90454-139">Se você escolher continuar a usar a política de atualização de equipes herdada, use a diretiva de interoperabilidade de equipes pré-configurado seguinte para rotear chamadas de entrada PSTN às equipes:</span><span class="sxs-lookup"><span data-stu-id="90454-139">If you choose to continue to use the legacy Teams upgrade policy, use the following preconfigured Teams interop policy to route inbound PSTN calling to Teams:</span></span>

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

<span data-ttu-id="90454-140">Se você optar por usar a diretiva de atualização de equipes atualizada, você precisará atribuir o modo de equipes apenas para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="90454-140">If you choose to use the updated Teams upgrade policy, you need to assign Teams Only mode to your users.</span></span>

<span data-ttu-id="90454-141">O comportamento da política acima inclui:</span><span class="sxs-lookup"><span data-stu-id="90454-141">The behaviors of the policy above are the following:</span></span>
* <span data-ttu-id="90454-142">**Para os clientes existentes do Skype for Business**, esta política tem como objetivo redirecionar as chamadas de entrada para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="90454-142">**For existing Skype for Business customers**, this policy is designed to redirect incoming calls to Teams.</span></span> <span data-ttu-id="90454-143">Isso inclui chamadas VoIP (do Microsoft Teams e do Skype for Business) e PSTN.</span><span class="sxs-lookup"><span data-stu-id="90454-143">This includes both VoIP (from Teams and Skype for Business) and PSTN calls.</span></span> 
* <span data-ttu-id="90454-144">**Para os clientes que não têm o Skype for Business**, quando em vigor, as chamadas PSTN serão recebidas no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="90454-144">**For customers without Skype for Business**, when in effect, PSTN calls will be received in Teams.</span></span>

> [!WARNING]
> <span data-ttu-id="90454-145">No momento, a alteração de `CallingDefaultClient` para o Microsoft Teams também afeta as chamadas para telefones IP do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="90454-145">Currently, changing `CallingDefaultClient` to Teams will also affect calls to Skype for Business IP phones.</span></span> <span data-ttu-id="90454-146">As chamadas de entrada não serão recebidas em telefones e vão tocar somente nos clientes do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="90454-146">Incoming calls will not be received on the phones and will only ring Teams clients.</span></span> <span data-ttu-id="90454-147">Consulte o [Mapa de 365 da Microsoft](https://aka.ms/O365Roadmap) para obter informações sobre o suporte para os telefones SIP certificados existentes.</span><span class="sxs-lookup"><span data-stu-id="90454-147">Please consult the [Microsoft 365 Roadmap](https://aka.ms/O365Roadmap) for information about support for existing certified SIP phones.</span></span>

### <a name="how-to-configure-users-to-receive-pstn-calls-in-teams"></a><span data-ttu-id="90454-148">Como configurar usuários para PSTN de receber chamadas em equipes</span><span class="sxs-lookup"><span data-stu-id="90454-148">How to configure users to receive PSTN calls in Teams</span></span>
<span data-ttu-id="90454-149">Ao usar a política de atualização de equipes herdada, aplica a política de interoperabilidade de equipes, conforme descrito acima via Skype para a sessão do Windows PowerShell remoto de negócios para redirecionar chamadas às equipes:</span><span class="sxs-lookup"><span data-stu-id="90454-149">When using the legacy Teams upgrade policy, apply the Teams interop policy as described above via Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

<span data-ttu-id="90454-150">Se você optar por usar o modo somente equipes, você poderá alterar modo de coexistência do usuário para equipes somente via o Centro de acmin Teams da Microsoft ou através de um Skype para a sessão do Windows PowerShell remoto de negócios para redirecionar chamadas às equipes:</span><span class="sxs-lookup"><span data-stu-id="90454-150">If you choose to use Teams Only mode, you can change the user's coexistence mode to Teams Only via the Microsoft Teams acmin center or via a Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsUpgradePolicy -PolicyName tag:UpgradeToTeams -Identity user@contoso.com
    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="see-also"></a><span data-ttu-id="90454-151">Consulte também</span><span class="sxs-lookup"><span data-stu-id="90454-151">See also</span></span>
[<span data-ttu-id="90454-152">Configurar Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="90454-152">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="90454-153">Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="90454-153">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="90454-154">Sistema de Telefonia com Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="90454-154">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="90454-155">Referência de cmdlets do PowerShell para o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="90454-155">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

[<span data-ttu-id="90454-156">Referência de cmdlets do PowerShell para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="90454-156">Teams PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/teams)
