---
title: "Guia de Início Rápido - Como configurar Planos de Chamadas no Microsoft Teams"
author: arachmanGitHub
ms.author: MyAdvisor
manager: lolaj
ms.date: 12/12/2017
ms.topic: article
ms.service: msteams
description: "Guia de Início Rápido para configurar Planos de Chamadas no Microsoft Teams."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: bf2aa9b698516882ed5e48b4d9b7b639b74af40e
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2017
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="66412-103">Guia de Início Rápido: como configurar Planos de Chamadas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="66412-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="66412-104">Este guia o ajudará a estabelecer um grupo de usuários para que eles possam explorar os Planos de Chamadas no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="66412-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="66412-105">Leia o anúncio feito em 12 de dezembro de 2017, dos Planos de Chamadas no Microsoft Teams: [A comunicação inteligente avança com as chamadas do Microsoft Teams](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="66412-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="66412-106">Recomendamos que, em paralelo com este Guia de Início Rápido, você use as [orientações prática](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) e o [FastTrack](https://aka.ms/cloudvoice) para planejar e realizar uma distribuição bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="66412-106">We recommend that, in parallel with this quick-start guide, you use our [practical guidance](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="66412-107">Com a inclusão dos Planos de Chamadas, um recurso do Office 365 acionado pelo Skype for Business, agora você pode usar o Microsoft Teams para fazer e receber chamadas de telefones fixos e celulares pela PSTN (Rede Telefônica Pública Comutada).</span><span class="sxs-lookup"><span data-stu-id="66412-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Fazendo chamadas no Microsoft Teams](media/Calling_in_Teams.png)

## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="66412-109">Pré-requisitos para habilitar a guia **Chamadas** no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="66412-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="66412-110">Para habilitar a guia **Chamadas** no Microsoft Teams e permitir que os usuários façam e recebam chamadas PSTN, será necessário provisionar os usuários para o Sistema de Telefonia e os Planos de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="66412-110">To enable the **Calls** tab in Teams and allow your users to make and receive PSTN calls, you will need provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="66412-111">Para saber como configurar isso, leia [Configurar Planos de Chamadas](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0).</span><span class="sxs-lookup"><span data-stu-id="66412-111">To learn how to set this up, read [Set up Calling Plans](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66412-112">Antes de configurar os Planos de Chamadas no Microsoft Teams, esteja ciente das seguintes limitações:</span><span class="sxs-lookup"><span data-stu-id="66412-112">Before configuring Calling Plans in Teams, please be aware of the following limitations:</span></span>
> * <span data-ttu-id="66412-113">**O Microsoft Teams não dá suporte ao Hybrid Voice** - o Hybrid Voice ainda não é compatível com o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="66412-113">**Hybrid Voice is not supported in Teams** - Hybrid Voice is currently not supported in Teams.</span></span> <span data-ttu-id="66412-114">Recomendamos que os clientes do Hybrid Voice não alterem nenhuma das políticas para receber chamadas no Microsoft Teams, pois isso causaria interrupções do serviço.</span><span class="sxs-lookup"><span data-stu-id="66412-114">Hybrid Voice customers are not advised to change any of the policies to receive calls in Teams, as this will cause service interruptions.</span></span>
> * <span data-ttu-id="66412-115">**O Microsoft Teams não dá suporte a chamadas federadas** - as chamadas federadas (chamadas entre locatários/empresas) ainda não são compatíveis com o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="66412-115">**Federated calling is not supported in Teams** - Federated calling (calling between tenants/companies) is currently not supported in Teams.</span></span> <span data-ttu-id="66412-116">As chamadas federadas serão encaminhadas para o Skype for Business, independentemente da configuração das chamadas, até que o Microsoft Teams ofereça suporte a elas.</span><span class="sxs-lookup"><span data-stu-id="66412-116">Federated calls will always be routed to Skype for Business regardless of how you configure calling, until it's supported in Teams.</span></span>

## <a name="teams-interop-policy-configuration"></a><span data-ttu-id="66412-117">Configuração da política de interoperabilidade do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="66412-117">Teams interop policy configuration</span></span>
<span data-ttu-id="66412-118">Para habilitar o Microsoft Teams para receber chamadas, é necessário atualizar a política de interoperabilidade do Microsoft Teams usando uma sessão do Windows PowerShell remoto com os cmdlets [`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) do Skype for Business para redirecionar as chamadas para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="66412-118">To enable Teams to begin receiving calls, you'll need to update Teams interop policy, using a remote Windows PowerShell session with the Skype for Business [`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) cmdlets, to redirect calls to Teams.</span></span> <span data-ttu-id="66412-119">Para obter mais informações sobre a política de interoperabilidade do Microsoft Teams, veja [Interoperabilidade entre o Microsoft Teams e o Skype for Business](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability).</span><span class="sxs-lookup"><span data-stu-id="66412-119">For more information about Teams interop policy, see [Microsoft Teams and Skype for Business Interoperability](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability).</span></span>

> [!TIP]
> <span data-ttu-id="66412-120">Para encontrar os cmdlets do PowerShell necessários, digite "CsTeamsInteropPolicy" na caixa **Filtrar** na [documentação de cmdlets do PowerShell para o Skype for Business](https://docs.microsoft.com/powershell/module/skype).</span><span class="sxs-lookup"><span data-stu-id="66412-120">To find the PowerShell cmdlets you need, type "CsTeamsInteropPolicy" in the **Filter** box in the [Skype for Business PowerShell cmdlet documentation](https://docs.microsoft.com/powershell/module/skype).</span></span>

### <a name="default-teams-interop-policy"></a><span data-ttu-id="66412-121">Política de interoperabilidade padrão do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="66412-121">Default Teams interop policy</span></span>
<span data-ttu-id="66412-122">O Microsoft Teams tem uma configuração de política padrão criada para garantir que os fluxos de trabalho de negócios existentes não sejam interrompidos durante a implantação do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="66412-122">Teams has a default policy configuration designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="66412-123">Por padrão, as chamadas VoIP, PSTN e federadas para seus usuários continuarão sendo encaminhadas para o Skype for Business até que você atualize a política para habilitar as chamadas de entrada para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="66412-123">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span> <span data-ttu-id="66412-124">Isso garante que não haja interrupções involuntárias nos serviços de voz quando você começa a testar e implantar o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="66412-124">This ensures that there are no unintended interruptions in voice services as you start to pilot and deploy Teams.</span></span>

<span data-ttu-id="66412-125">A política de interoperabilidade do Microsoft Teams tem a seguinte configuração padrão:</span><span class="sxs-lookup"><span data-stu-id="66412-125">Teams interop policy has the following default configuration:</span></span>

    Identity                   : Global
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

<span data-ttu-id="66412-126">Por padrão, o comportamento da configuração padrão inclui:</span><span class="sxs-lookup"><span data-stu-id="66412-126">The behaviors of the default configuration are the following:</span></span>
* <span data-ttu-id="66412-127">**Para os clientes existentes do Skype for Business**, esta política tem como objetivo garantir que as chamadas do Skype for Business sejam direcionadas para o Skype for Business, e as chamadas do Microsoft Teams sejam direcionadas para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="66412-127">**For existing Skype for Business customers**, this policy is designed to ensure that Skype for Business calls are directed to Skype for Business, and Teams calls are directed to Teams.</span></span> <span data-ttu-id="66412-128">As chamadas PSTN e federadas serão direcionadas para o Skype for Business quando essa política estiver em vigor.</span><span class="sxs-lookup"><span data-stu-id="66412-128">PSTN and federated calls will be directed to Skype for Business when this policy is in effect.</span></span>
* <span data-ttu-id="66412-129">**Para os clientes que não têm o Skype for Business**, quando em vigor, além das chamadas entre usuários do Microsoft Teams, somente as chamadas PSTN de saída estarão disponíveis no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="66412-129">**For customers without Skype for Business**, when in effect, in addition to calls among Teams users, only outbound PSTN calling will be available in Teams.</span></span> <span data-ttu-id="66412-130">Para receber chamadas PSTN no Microsoft Teams, será necessário alterar a política de interoperabilidade do Microsoft Teams atribuída a seus usuários.</span><span class="sxs-lookup"><span data-stu-id="66412-130">You will need to alter the Teams interop policy assigned to your users to receive PSTN calls in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="66412-131">A guia Chamadas estará habilitada no Microsoft Teams para os usuários que foram provisionados com licenças do Sistema de Telefonia e de Planos de Chamadas para uso com o Skype for Business Online e que têm configurada a política de interoperabilidade global padrão do Microsoft Teams, e eles poderão fazer chamadas PSTN de saída no Microsoft Teams sem a necessidade de qualquer ação por parte dos administradores.</span><span class="sxs-lookup"><span data-stu-id="66412-131">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online, and configured with the default global Teams interop policy, will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>

#### <a name="how-to-configure-teams-to-use-the-default-policy"></a><span data-ttu-id="66412-132">Como configurar o Microsoft Teams para usar a política padrão</span><span class="sxs-lookup"><span data-stu-id="66412-132">How to configure Teams to use the default policy</span></span>
<span data-ttu-id="66412-133">Por padrão, a política de interoperabilidade global do Microsoft Teams é aplicada a todos os usuários em seu locatário, sendo definida com as configurações padrão, conforme descrito acima.</span><span class="sxs-lookup"><span data-stu-id="66412-133">By default, global Teams interop policy is applied to all users in your tenant, and it is configured with the default settings as described above.</span></span> <span data-ttu-id="66412-134">Se, por algum motivo, você atribuiu políticas diferentes a seus usuários e deseja reverter para a configuração padrão, deve aplicar a política de interoperabilidade global do Microsoft Teams via sessão do Windows PowerShell remoto do Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="66412-134">If for some reason you have granted different policies to your users and would like to revert to the default setting, you will need to apply the global Teams interop policy via Skype for Business remote Windows PowerShell session:</span></span>

    Grant-CsTeamsInteropPolicy -PolicyName Global -Identity user@contoso.com

> [!WARNING]
> <span data-ttu-id="66412-135">Embora seja possível modificar a política de interoperabilidade global do Microsoft Teams a partir dos valores padrão, não é recomendável fazer isso.</span><span class="sxs-lookup"><span data-stu-id="66412-135">While it is possible to modify the global Teams interop policy from the default values, we strongly advise against it.</span></span> 

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a><span data-ttu-id="66412-136">Configuração do Microsoft Teams para receber chamadas PSTN de entrada</span><span class="sxs-lookup"><span data-stu-id="66412-136">Configuring Teams to receive inbound PSTN calls</span></span>
<span data-ttu-id="66412-137">Para receber chamadas PSTN de entrada no Microsoft Teams, é necessário configurar o Microsoft Teams como aplicativo de chamadas padrão, aplicando a política de interoperabilidade do Microsoft Teams com o parâmetro `CallingDefaultClient` definido para o Teams.</span><span class="sxs-lookup"><span data-stu-id="66412-137">To receive inbound PSTN calls in Teams, you will need to configure Teams as the default calling application by applying Teams interop policy with `CallingDefaultClient` parameter set to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66412-138">Recomendamos aplicar essa configuração a um conjunto inicial de usuários para explorar as incríveis novas funcionalidades de chamadas do Microsoft Teams antes de fazer alterações mais abrangentes ou em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="66412-138">We recommend that you apply this configuration to an initial set of users to explore these exciting new calling capabilities in Teams prior to making wider or organization-level changes.</span></span>

<span data-ttu-id="66412-139">Pense na possibilidade de usar a seguinte política de interoperabilidade do Microsoft Teams pré-configurada para encaminhar as chamadas PSTN de entrada para o Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="66412-139">Consider using the following preconfigured Teams interop policy to route inbound PSTN calling to Teams:</span></span>

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

<span data-ttu-id="66412-140">O comportamento da política acima inclui:</span><span class="sxs-lookup"><span data-stu-id="66412-140">The behaviors of the policy above are the following:</span></span>
* <span data-ttu-id="66412-141">**Para os clientes existentes do Skype for Business**, esta política tem como objetivo redirecionar as chamadas de entrada para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="66412-141">**For existing Skype for Business customers**, this policy is designed to redirect incoming calls to Teams.</span></span> <span data-ttu-id="66412-142">Isso inclui chamadas VoIP (do Microsoft Teams e do Skype for Business) e PSTN.</span><span class="sxs-lookup"><span data-stu-id="66412-142">This includes both VoIP (from Teams and Skype for Business) and PSTN calls.</span></span> <span data-ttu-id="66412-143">As chamadas federadas continuarão sendo recebidas no Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="66412-143">Federated calls will continue to be received in Skype for Business.</span></span> 
* <span data-ttu-id="66412-144">**Para os clientes que não têm o Skype for Business**, quando em vigor, as chamadas PSTN serão recebidas no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="66412-144">**For customers without Skype for Business**, when in effect, PSTN calls will be received in Teams.</span></span> <span data-ttu-id="66412-145">Por enquanto, as chamadas federadas **não têm suporte** no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="66412-145">Federated calling is currently **not supported** in Teams.</span></span>

> [!WARNING]
> <span data-ttu-id="66412-146">No momento, a alteração de `CallingDefaultClient` para o Microsoft Teams também afeta as chamadas para telefones IP do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="66412-146">Currently, changing `CallingDefaultClient` to Teams will also affect calls to Skype for Business IP phones.</span></span> <span data-ttu-id="66412-147">As chamadas de entrada não serão recebidas em telefones e vão tocar somente nos clientes do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="66412-147">Incoming calls will not be received on the phones and will only ring Teams clients.</span></span> <span data-ttu-id="66412-148">Consulte o [Skype for Business to Microsoft Teams Capabilities Roadmap](https://aka.ms/skype2teamsroadmap) para obter informações sobre o suporte para telefones SIP certificados existentes.</span><span class="sxs-lookup"><span data-stu-id="66412-148">Please consult the [Skype for Business to Microsoft Teams Capabilities Roadmap](https://aka.ms/skype2teamsroadmap) for information about support for existing certified SIP phones.</span></span>

### <a name="how-to-configure-teams-to-receive-pstn-calls"></a><span data-ttu-id="66412-149">Como configurar o Microsoft Teams para receber chamadas PSTN</span><span class="sxs-lookup"><span data-stu-id="66412-149">How to configure Teams to receive PSTN calls</span></span>
<span data-ttu-id="66412-150">Aplique a política de interoperabilidade do Microsoft Teams, conforme descrito acima, via sessão do Windows PowerShell remoto do Skype for Business para redirecionar as chamadas para o Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="66412-150">Apply the Teams interop policy as described above via Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="configuring-teams-to-allow-users-to-change-their-preferred-calling-experience"></a><span data-ttu-id="66412-151">Configuração do Microsoft Teams para permitir que os usuários alterem sua experiência de chamadas preferencial</span><span class="sxs-lookup"><span data-stu-id="66412-151">Configuring Teams to allow users to change their preferred calling experience</span></span>
<span data-ttu-id="66412-152">Para que os usuários possam decidir sobre sua experiência de chamadas preferencial, seja para receber chamadas no Microsoft Teams ou no Skype for Business, você precisa criar uma política de interoperabilidade personalizada do Microsoft Teams que habilite o parâmetro `AllowEndUserClientOverride`.</span><span class="sxs-lookup"><span data-stu-id="66412-152">To let users to make their own decision over the preferred calling experience, whether to receive calls in Teams or Skype for Business, you need to create a custom Teams interop policy that enables `AllowEndUserClientOverride` parameter.</span></span>

<span data-ttu-id="66412-153">Veja a seguir um exemplo da política de interoperabilidade do Microsoft Teams para habilitar a opção do usuário de experiência de chamadas preferencial:</span><span class="sxs-lookup"><span data-stu-id="66412-153">The following is the example of Teams interop policy to enable user choice of the preferred calling experience:</span></span>

    Identity                   : Tag:CustomPolicy
    AllowEndUserClientOverride : True
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

<span data-ttu-id="66412-154">Quando essa política personalizada for aplicada para os usuários, a opção de alterar o aplicativo de chamadas preferencial estará disponível no cliente do Microsoft Teams para que os próprios usuários façam suas alterações.</span><span class="sxs-lookup"><span data-stu-id="66412-154">Once this custom policy is applied to the users, the option to change the preferred calling application will be available in Teams client for users to make the changes themselves.</span></span>

![Opção preferencial de aplicativo de chamadas](media/Preferred_calling_application_option.png)

> [!IMPORTANT]
> <span data-ttu-id="66412-156">Recomendamos aplicar essa configuração a um conjunto inicial de usuários antes de fazer alterações mais abrangentes ou em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="66412-156">It is recommended that you apply this configuration to an initial set of users prior to making wider or organization level changes.</span></span>

### <a name="how-to-create-and-apply-the-custom-teams-interop-policy"></a><span data-ttu-id="66412-157">Como criar e aplicar a política de interoperabilidade personalizada do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="66412-157">How to create and apply the custom Teams interop policy</span></span>
<span data-ttu-id="66412-158">Para criar a política de interoperabilidade personalizada do Microsoft Teams, conforme descrito acima, via sessão do Windows PowerShell remoto do Skype for Business, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="66412-158">To create the custom Teams interop policy as described above via Skype for Business remote Windows PowerShell session, perform the following:</span></span>

    New-CsTeamsInteropPolicy -Identity tag:CustomPolicy -AllowEndUserClientOverride:$True -CallingDefaultClient:Default -ChatDefaultClient:Default

    Grant-CsTeamsInteropPolicy -PolicyName tag:CustomPolicy -Identity user@contoso.com



## <a name="see-also"></a><span data-ttu-id="66412-159">Consulte também</span><span class="sxs-lookup"><span data-stu-id="66412-159">See also</span></span>
[<span data-ttu-id="66412-160">Configurar Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="66412-160">Set up Calling Plans</span></span>](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0)

[<span data-ttu-id="66412-161">Interoperabilidade entre o Microsoft Teams e o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="66412-161">Microsoft Teams and Skype for Business Interoperability</span></span>](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability)

[<span data-ttu-id="66412-162">Orientações práticas para Sistema de Telefonia com Planos de Chamadas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="66412-162">Practical Guidance for Phone System with Calling Plans in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[<span data-ttu-id="66412-163">Referência de cmdlets do PowerShell para o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="66412-163">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

[<span data-ttu-id="66412-164">Referência de cmdlets do PowerShell para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="66412-164">PowerShell cmdlet reference for Teams</span></span>](https://docs.microsoft.com/powershell/module/teams)
