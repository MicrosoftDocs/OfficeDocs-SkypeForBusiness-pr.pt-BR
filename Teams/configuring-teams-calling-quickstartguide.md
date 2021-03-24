---
title: Guia de início rápido - Configurando planos de chamada
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: Guia de início rápido para configurar planos de chamada no Microsoft Teams para que você possa obter um conjunto de usuários em execução.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6420fdff102533c44bdd3ccb2ab503a646c354b8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101177"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="55fef-103">Guia de Início Rápido: Como configurar Planos de Chamadas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="55fef-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="55fef-104">Este guia ajudará você a obter um conjunto de usuários em execução para que eles possam explorar Planos de Chamada no Teams.</span><span class="sxs-lookup"><span data-stu-id="55fef-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="55fef-105">Leia o comunicado de 12 de dezembro de 2017 sobre Planos de Chamada no Teams: [Comunicações](https://aka.ms/ipyqus) Inteligentes dá a próxima etapa com a chamada no Teams</span><span class="sxs-lookup"><span data-stu-id="55fef-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="55fef-106">Recomendamos que, em paralelo com este guia [](calling-plan-landing-page.md) de início rápido, você leia Sistema de Telefonia com Planos de Chamadas e [FastTrack](https://aka.ms/cloudvoice) para planejar e conduzir uma rolagem bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="55fef-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="55fef-107">Adicionando Planos de Chamadas - um recurso do Microsoft 365 e do Office 365 com o Skype for Business - agora você pode usar o Teams para fazer e receber chamadas telefônicas para ou de linhas de telefone fixo e celulares por meio da PSTN (rede telefônica pública comutado).</span><span class="sxs-lookup"><span data-stu-id="55fef-107">By adding Calling Plans - a Microsoft 365 and Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Captura de tela mostrando a página Contatos no Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="55fef-109">Pré-requisitos para habilite a guia **Chamadas** no Teams</span><span class="sxs-lookup"><span data-stu-id="55fef-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="55fef-110">Para **habilitar** a guia Chamadas no Teams, os usuários precisam ter a chamada 1:1 habilitada no Teams e usar um cliente do Teams que oferece suporte a chamadas do Teams 1:1.</span><span class="sxs-lookup"><span data-stu-id="55fef-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="55fef-111">Para saber como gerenciar chamadas 1:1 no Teams, leia [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="55fef-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="55fef-112">Para saber quais clientes suportam a chamada, leia [Limites e especificações do Microsoft Teams.](./limits-specifications-teams.md)</span><span class="sxs-lookup"><span data-stu-id="55fef-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](./limits-specifications-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="55fef-113">Atualmente, a Caixa Postal não estará disponível na guia Chamadas, a menos que o usuário esteja habilitado para chamadas PSTN.</span><span class="sxs-lookup"><span data-stu-id="55fef-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="55fef-114">Pré-requisitos para habilite o **Dial Pad** no Teams</span><span class="sxs-lookup"><span data-stu-id="55fef-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="55fef-115">Para habilitar a guia **Dial Pad** no Teams e permitir que seus usuários façam e recebam chamadas PSTN, você precisará provisionar usuários para o Sistema de Telefonia e Planos de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="55fef-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="55fef-116">Para saber como configurar Planos de Chamada, leia [Configurar Planos de Chamada.](./set-up-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="55fef-116">To learn how to set up Calling Plans, read [Set up Calling Plans](./set-up-calling-plans.md).</span></span>
<span data-ttu-id="55fef-117">Além disso, somente para usuários do Teams, você deve garantir que "Permitir chamada privada" está habilitado na política de chamada do Teams.</span><span class="sxs-lookup"><span data-stu-id="55fef-117">Additionally, for Teams only users, you must ensure that "Allow private calling" is enabled in the Teams calling policy.</span></span> <span data-ttu-id="55fef-118">Consulte [Gerenciar o Teams durante a transição para o novo centro](./manage-teams-skypeforbusiness-admin-center.md) de administração do Microsoft Teams para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="55fef-118">See [Manage Teams during the transition to the new Microsoft Teams admin center](./manage-teams-skypeforbusiness-admin-center.md) for more information.</span></span>
> [!NOTE]
> <span data-ttu-id="55fef-119">Você também pode usar o Roteamento Direto para permitir que seus usuários façam e recebam chamadas PSTN.</span><span class="sxs-lookup"><span data-stu-id="55fef-119">You can also use Direct Routing to allow your users to make and receive PSTN calls.</span></span> <span data-ttu-id="55fef-120">Para saber como configurar o Roteamento Direto, leia [Configure Direct Routing](./direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="55fef-120">To learn how to set up Direct Routing, read [Configure Direct Routing](./direct-routing-configure.md).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="55fef-121">Usando o TeamsUpgradePolicy para controlar onde as chamadas estão em terra</span><span class="sxs-lookup"><span data-stu-id="55fef-121">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="55fef-122">Para controlar se as chamadas de entrada (e os chats) chegam no Teams ou no Skype for Business, os administradores usam o TeamsUpgradePolicy, usando o Centro de administração do [Microsoft Teams](https://aka.ms/teamsadmincenter) ou usando uma sessão de Windows PowerShell remota com os cmdlets do Skype [for Business.](/powershell/module/skype)</span><span class="sxs-lookup"><span data-stu-id="55fef-122">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="55fef-123">A configuração padrão do TeamsUpgradePolicy é o modo Ilhas, que foi projetado para garantir que fluxos de trabalho comerciais existentes não sejam interrompidos durante uma implantação do Teams.</span><span class="sxs-lookup"><span data-stu-id="55fef-123">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="55fef-124">Por padrão, as chamadas VoIP, PSTN e federadas para seus usuários continuarão sendo roteadas para o Skype for Business até que você atualize a política para habilitar chamadas de entrada para o Teams.</span><span class="sxs-lookup"><span data-stu-id="55fef-124">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="55fef-125">Quando os destinatários estão no modo de ilhas:</span><span class="sxs-lookup"><span data-stu-id="55fef-125">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="55fef-126">Chamadas VOIP de entrada originadas no Skype for Business sempre chegam no cliente Skype for Business do destinatário.</span><span class="sxs-lookup"><span data-stu-id="55fef-126">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="55fef-127">Chamadas VOIP de entrada originadas no Teams chegam ao Teams, se o remetente e o *receptor estão no mesmo locatário*.</span><span class="sxs-lookup"><span data-stu-id="55fef-127">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="55fef-128">VoIP federado de entrada (independentemente de qual cliente se origina) e as chamadas PSTN sempre chegam no cliente skype for Business do destinatário.</span><span class="sxs-lookup"><span data-stu-id="55fef-128">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="55fef-129">Para garantir que as chamadas VOIP e PSTN de entrada sempre chegam no cliente do Teams de um usuário, atualize o modo de coexistência do usuário para ser TeamsOnly (o que significa, atribua a eles a instância "UpgradeToTeams" do TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="55fef-129">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="55fef-130">Para obter mais informações sobre modos de coexistência e TeamsUpgradePolicy, consulte [Migration and interoperability guidance for](./migration-interop-guidance-for-teams-with-skype.md) organizations using Teams together with Skype for Business</span><span class="sxs-lookup"><span data-stu-id="55fef-130">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](./migration-interop-guidance-for-teams-with-skype.md)</span></span>

<span data-ttu-id="55fef-131">**NOTES**</span><span class="sxs-lookup"><span data-stu-id="55fef-131">**NOTES**</span></span>
 - <span data-ttu-id="55fef-132">Os telefones IP do Skype for Business receberão chamadas, mesmo se o usuário estiver no modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="55fef-132">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="55fef-133">Os usuários que foram provisionados com licenças do Sistema de Telefonia e planos de chamadas para uso com o Skype for Business Online (por exemplo, eles foram atribuídos a um valor de OnlineVoiceRoutingPolicy) , terão a guia Chamadas habilitadas no Teams e poderão fazer chamadas PSTN de saída do Teams sem que os administradores tenham que tomar qualquer ação administrativa.</span><span class="sxs-lookup"><span data-stu-id="55fef-133">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="55fef-134">Como configurar os usuários para receber todas as chamadas VOIP e PSTN de entrada no Teams</span><span class="sxs-lookup"><span data-stu-id="55fef-134">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="55fef-135">Para garantir que os usuários recebam todas as chamadas VOIP e PSTN de entrada no Teams, de definir o modo de coexistência do usuário como TeamsOnly no centro de administração do Microsoft Teams ou use a sessão de Windows PowerShell remota do Skype for Business para atualizar o TeamsUpgradePolicy da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="55fef-135">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a><span data-ttu-id="55fef-136">Confira também</span><span class="sxs-lookup"><span data-stu-id="55fef-136">See also</span></span>
[<span data-ttu-id="55fef-137">Configurar Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="55fef-137">Set up Calling Plans</span></span>](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="55fef-138">Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="55fef-138">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](./migration-interop-guidance-for-teams-with-skype.md)

[<span data-ttu-id="55fef-139">Sistema de Telefonia com Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="55fef-139">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="55fef-140">Referência de cmdlet do Skype for Business PowerShell</span><span class="sxs-lookup"><span data-stu-id="55fef-140">Skype for Business PowerShell cmdlet reference</span></span>](/powershell/module/skype)