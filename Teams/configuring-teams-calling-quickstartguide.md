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
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: eea3c6ed4084648877fd31b84bb9cdea26986565
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23856095"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="cd846-103">Guia de Início Rápido: como configurar Planos de Chamadas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cd846-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="cd846-104">Este guia o ajudará a estabelecer um grupo de usuários para que eles possam explorar os Planos de Chamadas no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cd846-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="cd846-105">Leia o anúncio feito em 12 de dezembro de 2017, dos Planos de Chamadas no Microsoft Teams: [A comunicação inteligente avança com as chamadas do Microsoft Teams](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="cd846-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="cd846-106">Recomendamos que, em paralelo com este Guia de Início Rápido, você use as [orientações prática](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) e o [FastTrack](https://aka.ms/cloudvoice) para planejar e realizar uma distribuição bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="cd846-106">We recommend that, in parallel with this quick-start guide, you use our [practical guidance](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="cd846-107">Com a inclusão dos Planos de Chamadas, um recurso do Office 365 acionado pelo Skype for Business, agora você pode usar o Microsoft Teams para fazer e receber chamadas de telefones fixos e celulares pela PSTN (Rede Telefônica Pública Comutada).</span><span class="sxs-lookup"><span data-stu-id="cd846-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Fazendo chamadas no Microsoft Teams](media/Calling_in_Teams.png)

## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="cd846-109">Pré-requisitos para habilitar a guia **Chamadas** no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cd846-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="cd846-110">Para habilitar a guia **Chamadas** no Microsoft Teams e permitir que os usuários façam e recebam chamadas PSTN, será necessário provisionar os usuários para o Sistema de Telefonia e os Planos de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="cd846-110">To enable the **Calls** tab in Teams and allow your users to make and receive PSTN calls, you will need provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="cd846-111">Para saber como configurar isso, leia [Configurar Planos de Chamadas](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="cd846-111">To learn how to set this up, read [Set up Calling Plans](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans).</span></span>

## <a name="teams-interop-policy-configuration"></a><span data-ttu-id="cd846-112">Configuração da política de interoperabilidade do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cd846-112">Teams interop policy configuration</span></span>
<span data-ttu-id="cd846-113">Para permitir que equipes começar a receber chamadas, você precisará atualizar a política de atualização de equipes e política de interoperabilidade de equipes, usando [as equipes da Microsoft & Skype para Business Admin Center](https://aka.ms/teamsadmincenter) ou usando uma sessão remota do Windows PowerShell com o Skype para negócios [ `*-CsTeamsUpgradePolicy`e `*-CsTeamsInteropPolicy` ](https://docs.microsoft.com/powershell/module/skype) cmdlets, para redirecionar chamadas para equipes.</span><span class="sxs-lookup"><span data-stu-id="cd846-113">To enable Teams to begin receiving calls, you'll need to update Teams upgrade policy and Teams interop policy, using [Microsoft Teams & Skype for Business Admin Center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the Skype for Business [`*-CsTeamsUpgradePolicy` and `*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) cmdlets, to redirect calls to Teams.</span></span>

<span data-ttu-id="cd846-114">Para obter mais informações sobre a política de atualização de equipes e política de interoperabilidade de equipes, consulte [migração e orientações de interoperabilidade para organizações que usam equipes em conjunto com o Skype para negócios](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="cd846-114">For more information about Teams upgrade policy and Teams interop policy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).</span></span>

> [!TIP]
> <span data-ttu-id="cd846-115">Para localizar os cmdlets do PowerShell que você precisa, digite "CsTeamsUpgradePolicy" ou "CsTeamsInteropPolicy" na caixa **filtro** no [Skype para documentação de cmdlet do PowerShell de negócios](https://docs.microsoft.com/powershell/module/skype).</span><span class="sxs-lookup"><span data-stu-id="cd846-115">To find the PowerShell cmdlets you need, type "CsTeamsUpgradePolicy" or "CsTeamsInteropPolicy" in the **Filter** box in the [Skype for Business PowerShell cmdlet documentation](https://docs.microsoft.com/powershell/module/skype).</span></span>

### <a name="default-teams-upgrade-and-interop-policies"></a><span data-ttu-id="cd846-116">Padrão às equipes políticas de atualização e interoperabilidade</span><span class="sxs-lookup"><span data-stu-id="cd846-116">Default Teams upgrade and interop policies</span></span>
<span data-ttu-id="cd846-117">O Microsoft Teams tem uma configuração de política padrão criada para garantir que os fluxos de trabalho de negócios existentes não sejam interrompidos durante a implantação do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cd846-117">Teams has a default policy configuration designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="cd846-118">Por padrão, as chamadas VoIP, PSTN e federadas para seus usuários continuarão sendo encaminhadas para o Skype for Business até que você atualize a política para habilitar as chamadas de entrada para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cd846-118">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span> <span data-ttu-id="cd846-119">Isso garante que não haja interrupções involuntárias nos serviços de voz quando você começa a testar e implantar o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cd846-119">This ensures that there are no unintended interruptions in voice services as you start to pilot and deploy Teams.</span></span>

<span data-ttu-id="cd846-120">As equipes de política de atualização por padrão é mantida em modo herdado que aceita a diretiva de interoperabilidade de equipes para determinar onde bate-papos e chamadas devem ser roteadas – equipes ou Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="cd846-120">Teams upgrade policy by default is kept at legacy mode that will honor Teams interop policy to determine where chats and calls are to be routed--Teams or Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="cd846-121">Os comportamentos de equipes atualizar a política e política de interoperabilidade de equipes em breve será alterada conforme descrito na [migração e orientações de interoperabilidade para organizações que usam equipes em conjunto com o Skype para negócios](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span><span class="sxs-lookup"><span data-stu-id="cd846-121">The behaviors of Teams upgrade policy and Teams interop policy will soon change as described in [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="cd846-122">A política de interoperabilidade do Microsoft Teams tem a seguinte configuração padrão:</span><span class="sxs-lookup"><span data-stu-id="cd846-122">Teams interop policy has the following default configuration:</span></span>

    Identity                   : Global
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

<span data-ttu-id="cd846-123">Por padrão, o comportamento da configuração padrão inclui:</span><span class="sxs-lookup"><span data-stu-id="cd846-123">The behaviors of the default configuration are the following:</span></span>
* <span data-ttu-id="cd846-124">**Para os clientes existentes do Skype for Business**, esta política tem como objetivo garantir que as chamadas do Skype for Business sejam direcionadas para o Skype for Business, e as chamadas do Microsoft Teams sejam direcionadas para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cd846-124">**For existing Skype for Business customers**, this policy is designed to ensure that Skype for Business calls are directed to Skype for Business, and Teams calls are directed to Teams.</span></span> <span data-ttu-id="cd846-125">As chamadas PSTN e federadas serão direcionadas para o Skype for Business quando essa política estiver em vigor.</span><span class="sxs-lookup"><span data-stu-id="cd846-125">PSTN and federated calls will be directed to Skype for Business when this policy is in effect.</span></span>
* <span data-ttu-id="cd846-126">**Para os clientes que não têm o Skype for Business**, quando em vigor, além das chamadas entre usuários do Microsoft Teams, somente as chamadas PSTN de saída estarão disponíveis no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cd846-126">**For customers without Skype for Business**, when in effect, in addition to calls among Teams users, only outbound PSTN calling will be available in Teams.</span></span> <span data-ttu-id="cd846-127">Para receber chamadas PSTN no Microsoft Teams, será necessário alterar a política de interoperabilidade do Microsoft Teams atribuída a seus usuários.</span><span class="sxs-lookup"><span data-stu-id="cd846-127">You will need to alter the Teams interop policy assigned to your users to receive PSTN calls in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="cd846-128">A guia Chamadas estará habilitada no Microsoft Teams para os usuários que foram provisionados com licenças do Sistema de Telefonia e de Planos de Chamadas para uso com o Skype for Business Online e que têm configurada a política de interoperabilidade global padrão do Microsoft Teams, e eles poderão fazer chamadas PSTN de saída no Microsoft Teams sem a necessidade de qualquer ação por parte dos administradores.</span><span class="sxs-lookup"><span data-stu-id="cd846-128">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online, and configured with the default global Teams interop policy, will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a><span data-ttu-id="cd846-129">Configuração do Microsoft Teams para receber chamadas PSTN de entrada</span><span class="sxs-lookup"><span data-stu-id="cd846-129">Configuring Teams to receive inbound PSTN calls</span></span>
<span data-ttu-id="cd846-130">Para receber chamadas de PSTN de entrada em equipes, você precisará configurar equipes como o aplicativo de chamada pela aplicação da diretiva de atualização de equipes com a política de interoperabilidade de equipes correspondente que define o padrão `CallingDefaultClient` parâmetro às equipes.</span><span class="sxs-lookup"><span data-stu-id="cd846-130">To receive inbound PSTN calls in Teams, you will need to configure Teams as the default calling application by applying Teams upgrade policy with the corresponding Teams interop policy that sets `CallingDefaultClient` parameter to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd846-131">Recomendamos aplicar essa configuração a um conjunto inicial de usuários para explorar as incríveis novas funcionalidades de chamadas do Microsoft Teams antes de fazer alterações mais abrangentes ou em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="cd846-131">We recommend that you apply this configuration to an initial set of users to explore these exciting new calling capabilities in Teams prior to making wider or organization-level changes.</span></span>

<span data-ttu-id="cd846-132">Se você escolher continuar a usar a política de atualização de equipes herdada, use a diretiva de interoperabilidade de equipes pré-configurado seguinte para rotear chamadas de entrada PSTN às equipes:</span><span class="sxs-lookup"><span data-stu-id="cd846-132">If you choose to continue to use the legacy Teams upgrade policy, use the following preconfigured Teams interop policy to route inbound PSTN calling to Teams:</span></span>

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

<span data-ttu-id="cd846-133">Se você optar por usar a diretiva de atualização de equipes atualizada, você precisará atribuir o modo de TeamsOnly para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="cd846-133">If you choose to use the updated Teams upgrade policy, you need to assign TeamsOnly mode to your users.</span></span>

<span data-ttu-id="cd846-134">O comportamento da política acima inclui:</span><span class="sxs-lookup"><span data-stu-id="cd846-134">The behaviors of the policy above are the following:</span></span>
* <span data-ttu-id="cd846-135">**Para os clientes existentes do Skype for Business**, esta política tem como objetivo redirecionar as chamadas de entrada para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cd846-135">**For existing Skype for Business customers**, this policy is designed to redirect incoming calls to Teams.</span></span> <span data-ttu-id="cd846-136">Isso inclui chamadas VoIP (do Microsoft Teams e do Skype for Business) e PSTN.</span><span class="sxs-lookup"><span data-stu-id="cd846-136">This includes both VoIP (from Teams and Skype for Business) and PSTN calls.</span></span> 
* <span data-ttu-id="cd846-137">**Para os clientes que não têm o Skype for Business**, quando em vigor, as chamadas PSTN serão recebidas no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cd846-137">**For customers without Skype for Business**, when in effect, PSTN calls will be received in Teams.</span></span>

> [!WARNING]
> <span data-ttu-id="cd846-138">No momento, a alteração de `CallingDefaultClient` para o Microsoft Teams também afeta as chamadas para telefones IP do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="cd846-138">Currently, changing `CallingDefaultClient` to Teams will also affect calls to Skype for Business IP phones.</span></span> <span data-ttu-id="cd846-139">As chamadas de entrada não serão recebidas em telefones e vão tocar somente nos clientes do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cd846-139">Incoming calls will not be received on the phones and will only ring Teams clients.</span></span> <span data-ttu-id="cd846-140">Consulte o [Skype for Business to Microsoft Teams Capabilities Roadmap](https://aka.ms/skype2teamsroadmap) para obter informações sobre o suporte para telefones SIP certificados existentes.</span><span class="sxs-lookup"><span data-stu-id="cd846-140">Please consult the [Skype for Business to Microsoft Teams Capabilities Roadmap](https://aka.ms/skype2teamsroadmap) for information about support for existing certified SIP phones.</span></span>

### <a name="how-to-configure-users-to-receive-pstn-calls-in-teams"></a><span data-ttu-id="cd846-141">Como configurar usuários para PSTN de receber chamadas em equipes</span><span class="sxs-lookup"><span data-stu-id="cd846-141">How to configure users to receive PSTN calls in Teams</span></span>
<span data-ttu-id="cd846-142">Ao usar a política de atualização de equipes herdada, aplica a política de interoperabilidade de equipes, conforme descrito acima via Skype para a sessão do Windows PowerShell remoto de negócios para redirecionar chamadas às equipes:</span><span class="sxs-lookup"><span data-stu-id="cd846-142">When using the legacy Teams upgrade policy, apply the Teams interop policy as described above via Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

<span data-ttu-id="cd846-143">Se você optar por usar o modo de TeamsOnly, você pode alterar o modo de coexistência do usuário para TeamsOnly via Teams Microsoft & Skype para Business Admin Center, ou via Skype para a sessão do Windows PowerShell remoto de negócios para redirecionar chamadas às equipes:</span><span class="sxs-lookup"><span data-stu-id="cd846-143">If you choose to use TeamsOnly mode, you can change the user's coexistence mode to TeamsOnly via Microsoft Teams & Skype for Business Admin Center, or via Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsUpgradePolicy -PolicyName tag:UpgradeToTeams -Identity user@contoso.com
    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="see-also"></a><span data-ttu-id="cd846-144">Consulte também</span><span class="sxs-lookup"><span data-stu-id="cd846-144">See also</span></span>
[<span data-ttu-id="cd846-145">Configurar Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="cd846-145">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="cd846-146">Diretrizes de migração e interoperabilidade para organizações que usam equipes em conjunto com o Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="cd846-146">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="cd846-147">Orientações práticas para Sistema de Telefonia com Planos de Chamadas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cd846-147">Practical Guidance for Phone System with Calling Plans in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[<span data-ttu-id="cd846-148">Referência de cmdlets do PowerShell para o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="cd846-148">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

[<span data-ttu-id="cd846-149">Referência de cmdlets do PowerShell para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cd846-149">Teams PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/teams)
