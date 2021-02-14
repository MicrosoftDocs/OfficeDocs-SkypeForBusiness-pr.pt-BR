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
description: Guia de início rápido para configurar planos de chamada no Microsoft Teams para que você possa configurar e executar um conjunto de usuários.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c43decd3b3f7d5e23e0e7937a93b4663a80aa583
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799761"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="f44b9-103">Guia de Início Rápido: como configurar Planos de Chamadas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f44b9-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="f44b9-104">Este guia o ajudará a estabelecer um grupo de usuários para que eles possam explorar os Planos de Chamadas no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f44b9-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="f44b9-105">Leia o anúncio feito em 12 de dezembro de 2017, dos Planos de Chamadas no Microsoft Teams: [A comunicação inteligente avança com as chamadas do Microsoft Teams](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="f44b9-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="f44b9-106">Recomendamos que, em paralelo com este guia [](calling-plan-landing-page.md) de início rápido, você leia o Sistema de Telefonia com Planos de Chamada e o [FastTrack](https://aka.ms/cloudvoice) para planejar e impulsionar uma adoção bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="f44b9-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="f44b9-107">Ao adicionar Planos de Chamada , um recurso do Microsoft 365 e do Office 365 da plataforma Skype for Business, agora você pode usar o Teams para fazer e receber chamadas telefônicas para ou de telefones fixos e celulares por meio da PSTN (rede telefônica pública comutado).</span><span class="sxs-lookup"><span data-stu-id="f44b9-107">By adding Calling Plans - a Microsoft 365 and Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Captura de tela mostrando a página Contatos no Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="f44b9-109">Pré-requisitos para habilitar a guia **Chamadas** no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f44b9-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="f44b9-110">Para habilitar a guia Chamadas no Teams, os usuários precisam ter chamadas 1:1 habilitadas no Teams e usar um cliente do Teams compatível com chamadas do Teams 1:1. </span><span class="sxs-lookup"><span data-stu-id="f44b9-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="f44b9-111">Para saber como gerenciar chamadas 1:1 no Teams, leia [Set-CsTeamsCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="f44b9-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="f44b9-112">Para saber quais clientes são suportados por chamada, leia [Limites e especificações do Microsoft Teams.](https://docs.microsoft.com/microsoftteams/limits-specifications-teams)</span><span class="sxs-lookup"><span data-stu-id="f44b9-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="f44b9-113">Atualmente, a caixa postal não estará disponível na guia Chamadas, a menos que o usuário esteja habilitado para chamadas PSTN.</span><span class="sxs-lookup"><span data-stu-id="f44b9-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="f44b9-114">Pré-requisitos para habilite o Teclado **de Discagem** no Teams</span><span class="sxs-lookup"><span data-stu-id="f44b9-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="f44b9-115">Para habilitar a guia **Teclado** de Discagem no Teams e permitir que seus usuários façam e recebam chamadas PSTN, você precisará provisionar usuários para o Sistema de Telefonia e planos de chamada.</span><span class="sxs-lookup"><span data-stu-id="f44b9-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="f44b9-116">Para saber como configurar Planos de Chamada, leia [Configurar Planos de Chamada.](https://docs.microsoft.com/microsoftteams/set-up-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="f44b9-116">To learn how to set up Calling Plans, read [Set up Calling Plans](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span></span>
<span data-ttu-id="f44b9-117">Além disso, somente para usuários do Teams, você deve garantir que "Permitir chamada privada" está habilitado na política de chamada do Teams.</span><span class="sxs-lookup"><span data-stu-id="f44b9-117">Additionally, for Teams only users, you must ensure that "Allow private calling" is enabled in the Teams calling policy.</span></span> <span data-ttu-id="f44b9-118">Consulte [Gerenciar Equipes durante a transição para o novo centro de administração do Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="f44b9-118">See [Manage Teams during the transition to the new Microsoft Teams admin center](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center) for more information.</span></span>
> [!NOTE]
> <span data-ttu-id="f44b9-119">Você também pode usar o Roteamento Direto para permitir que seus usuários façam e recebam chamadas PSTN.</span><span class="sxs-lookup"><span data-stu-id="f44b9-119">You can also use Direct Routing to allow your users to make and receive PSTN calls.</span></span> <span data-ttu-id="f44b9-120">Para saber como configurar o Roteamento Direto, leia [Configurar Roteamento Direto.](https://docs.microsoft.com/microsoftteams/direct-routing-configure)</span><span class="sxs-lookup"><span data-stu-id="f44b9-120">To learn how to set up Direct Routing, read [Configure Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="f44b9-121">Usando o TeamsUpgradePolicy para controlar onde as chamadas chegarão</span><span class="sxs-lookup"><span data-stu-id="f44b9-121">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="f44b9-122">Para controlar se as chamadas de entrada (e chats) chegam no Teams ou no Skype for Business, os administradores usam o TeamsUpgradePolicy, usando o Centro de administração do [Microsoft Teams](https://aka.ms/teamsadmincenter) ou usando uma sessão remota do Windows PowerShell com os cmdlets do Skype [for Business.](https://docs.microsoft.com/powershell/module/skype)</span><span class="sxs-lookup"><span data-stu-id="f44b9-122">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](https://docs.microsoft.com/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="f44b9-123">A configuração padrão do TeamsUpgradePolicy é o modo Ilhas, que foi projetado para garantir que fluxos de trabalho comerciais existentes não sejam interrompidos durante uma implantação do Teams.</span><span class="sxs-lookup"><span data-stu-id="f44b9-123">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="f44b9-124">Por padrão, as chamadas VoIP, PSTN e federadas para seus usuários continuarão a ser roteadas para o Skype for Business até que você atualize a política para habilitar chamadas de entrada para o Teams.</span><span class="sxs-lookup"><span data-stu-id="f44b9-124">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="f44b9-125">Quando os destinatários estão no modo de ilhas:</span><span class="sxs-lookup"><span data-stu-id="f44b9-125">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="f44b9-126">Chamadas VOIP de entrada que se originam no Skype for Business sempre chegam ao cliente Skype for Business do destinatário.</span><span class="sxs-lookup"><span data-stu-id="f44b9-126">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="f44b9-127">Chamadas VOIP de entrada originadas no Teams chegam ao Teams, se o remetente e o *destinatário estão no mesmo locatário.*</span><span class="sxs-lookup"><span data-stu-id="f44b9-127">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="f44b9-128">VoIP federado de entrada (independentemente da origem do cliente) e chamadas PSTN sempre chegam no cliente Skype for Business do destinatário.</span><span class="sxs-lookup"><span data-stu-id="f44b9-128">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="f44b9-129">Para garantir que as chamadas VOIP e PSTN de entrada sempre sejam recebidas no cliente do Teams de um usuário, atualize o modo de coexistência do usuário para que ele seja o TeamsOnly (o que significa atribuir a instância "UpgradeToTeams" do TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="f44b9-129">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="f44b9-130">Para obter mais informações sobre modos de coexistência e TeamsUpgradePolicy, consulte as diretrizes de migração e [interoperabilidade](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype) para as organizações que usam o Teams em conjunto com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f44b9-130">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="f44b9-131">**Notas**</span><span class="sxs-lookup"><span data-stu-id="f44b9-131">**NOTES**</span></span>
 - <span data-ttu-id="f44b9-132">Os telefones IP do Skype for Business receberão chamadas, mesmo se o usuário estiver no modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="f44b9-132">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="f44b9-133">Os usuários que foram provisionados com licenças do Sistema de Telefonia e planos de chamada para uso com o Skype for Business Online (por exemplo, eles têm um valor de OnlineVoiceRoutingPolicy), terão a guia Chamadas habilitadas no Teams e poderão fazer chamadas PSTN de saída do Teams sem que os administradores tenham que tomar nenhuma medida administrativa.</span><span class="sxs-lookup"><span data-stu-id="f44b9-133">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="f44b9-134">Como configurar os usuários para receber todas as chamadas VOIP e PSTN de entrada no Teams</span><span class="sxs-lookup"><span data-stu-id="f44b9-134">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="f44b9-135">Para garantir que os usuários recebam todas as chamadas VOIP e PSTN de entrada no Teams, de definir o modo de coexistência do usuário para o TeamsOnly no Centro de administração do Microsoft Teams ou usar a sessão remota do Windows PowerShell do Skype for Business para atualizar o TeamsUpgradePolicy da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="f44b9-135">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a><span data-ttu-id="f44b9-136">Confira também</span><span class="sxs-lookup"><span data-stu-id="f44b9-136">See also</span></span>
[<span data-ttu-id="f44b9-137">Configurar Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="f44b9-137">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="f44b9-138">Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f44b9-138">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="f44b9-139">Sistema de Telefonia com Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="f44b9-139">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="f44b9-140">Referência de cmdlet do PowerShell do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f44b9-140">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

