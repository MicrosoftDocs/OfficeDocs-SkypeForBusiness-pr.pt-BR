---
title: Guia de Início Rápido - Como configurar Planos de Chamadas no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille, crowe
search.appverid: MET150
description: Guia de Início Rápido para configurar Planos de Chamadas no Microsoft Teams.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- Teams_ITAdmin_Training
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fd1e9484b522a657a92916815c1ae8940dcc2117
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33898519"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="9cb62-103">Guia de Início Rápido: como configurar Planos de Chamadas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9cb62-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="9cb62-104">Este guia o ajudará a estabelecer um grupo de usuários para que eles possam explorar os Planos de Chamadas no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9cb62-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="9cb62-105">Leia o anúncio feito em 12 de dezembro de 2017, dos Planos de Chamadas no Microsoft Teams: [A comunicação inteligente avança com as chamadas do Microsoft Teams](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="9cb62-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="9cb62-106">Recomendamos que, em paralelo com este guia de início rápido, você leia [O sistema telefônico com planos de chamada](calling-plan-landing-page.md) e [FastTrack](https://aka.ms/cloudvoice) planejar e a unidade uma distribuição bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="9cb62-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="9cb62-107">Com a inclusão dos Planos de Chamadas, um recurso do Office 365 acionado pelo Skype for Business, agora você pode usar o Microsoft Teams para fazer e receber chamadas de telefones fixos e celulares pela PSTN (Rede Telefônica Pública Comutada).</span><span class="sxs-lookup"><span data-stu-id="9cb62-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Fazendo chamadas no Microsoft Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="9cb62-109">Pré-requisitos para habilitar a guia **Chamadas** no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9cb62-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="9cb62-110">Para habilitar a guia **chamadas** em equipes os usuários precisam ter o 1:1 chamando ativados nas equipes e usando um cliente de equipes que ofereça suporte a chamada de equipes de 1:1.</span><span class="sxs-lookup"><span data-stu-id="9cb62-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="9cb62-111">Para saber como gerenciar 1:1 chamando em equipes, leia [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="9cb62-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="9cb62-112">Para saber quais clientes suportam a chamada, leia [limites e as especificações para equipes da Microsoft](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span><span class="sxs-lookup"><span data-stu-id="9cb62-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="9cb62-113">Atualmente, caixa postal não estarão disponível na guia chamadas, a menos que o usuário está habilitado para chamadas PSTN.</span><span class="sxs-lookup"><span data-stu-id="9cb62-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="9cb62-114">Pré-requisitos para habilitar o **Teclado de discagem** em equipes</span><span class="sxs-lookup"><span data-stu-id="9cb62-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="9cb62-115">Para habilitar a guia **Teclado de discagem** em equipes e permitir que os usuários façam e recebam chamadas PSTN, você precisará provisionar usuários para o sistema telefônico e planos de chamada.</span><span class="sxs-lookup"><span data-stu-id="9cb62-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="9cb62-116">Para saber como configurar planos de chamada, leia [Configurar planos de chamada](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="9cb62-116">To learn how to set up Calling Plans, read [Set up Calling Plans](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span></span>

> [!NOTE]
> <span data-ttu-id="9cb62-117">Você também pode usar o roteamento direto para permitir que os usuários façam e recebam chamadas PSTN.</span><span class="sxs-lookup"><span data-stu-id="9cb62-117">You can also use Direct Routing to allow your users to make and receive PSTN calls.</span></span> <span data-ttu-id="9cb62-118">Para saber como configurar o roteamento direto, leia a [Configurar o roteamento direto](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span><span class="sxs-lookup"><span data-stu-id="9cb62-118">To learn how to set up Direct Routing, read [Configure Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="9cb62-119">Usando TeamsUpgradePolicy para controlar onde chamadas land</span><span class="sxs-lookup"><span data-stu-id="9cb62-119">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="9cb62-120">Para controlar se as chamadas de entrada (e bate-papos) land em equipes ou Skype para os negócios, os administradores usam TeamsUpgradePolicy, usando o [Centro de administração de equipes da Microsoft](https://aka.ms/teamsadmincenter) ou usando uma sessão remota do Windows PowerShell com o [Skype para negócios](https://docs.microsoft.com/powershell/module/skype) cmdlets.</span><span class="sxs-lookup"><span data-stu-id="9cb62-120">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](https://docs.microsoft.com/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="9cb62-121">A configuração padrão do TeamsUpgradePolicy é o modo de ilhas, que foi projetado para garantir que os fluxos de trabalho não são interrompidos durante uma implantação de equipes de negócios existentes.</span><span class="sxs-lookup"><span data-stu-id="9cb62-121">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="9cb62-122">Por padrão, a VoIP, PSTN e chamadas federadas para seus usuários continuarão a ser roteadas para Skype para negócios até que você atualiza a política para permitir que as chamadas de entrada para equipes.</span><span class="sxs-lookup"><span data-stu-id="9cb62-122">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="9cb62-123">Quando os destinatários estão no modo de ilhas:</span><span class="sxs-lookup"><span data-stu-id="9cb62-123">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="9cb62-124">Entrada VOIP chama esse Skype originado na for Business sempre land no Skype do destinatário para o cliente de negócios.</span><span class="sxs-lookup"><span data-stu-id="9cb62-124">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="9cb62-125">Entrada VOIP chama originados no land equipes em equipes, *se o remetente e o receptor estiverem no mesmo inquilino*.</span><span class="sxs-lookup"><span data-stu-id="9cb62-125">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="9cb62-126">Entrada federados VOIP (independentemente de qual cliente originado) e chamadas PSTN sempre land no Skype do destinatário para o cliente de negócios.</span><span class="sxs-lookup"><span data-stu-id="9cb62-126">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="9cb62-127">Para garantir a entrada VOIP e PSTN sempre chama land no cliente de equipes de um usuário, atualize o modo de coexistência do usuário para ser TeamsOnly (o que significa que atribuí-las a instância de "UpgradeToTeams" do TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="9cb62-127">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="9cb62-128">Para obter mais informações sobre os modos de coexistência e TeamsUpgradePolicy, consulte [migração e orientações de interoperabilidade para organizações que usam equipes em conjunto com o Skype para negócios](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span><span class="sxs-lookup"><span data-stu-id="9cb62-128">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="9cb62-129">**NOTAS**</span><span class="sxs-lookup"><span data-stu-id="9cb62-129">**NOTES**</span></span>
 - <span data-ttu-id="9cb62-130">Skype para telefones IP Business receberá chamadas, mesmo se o usuário está no modo de TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="9cb62-130">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="9cb62-131">Usuários que tenham sido configurados com o sistema telefônico e planos de chamar licenças para uso com o Skype para Business Online (por exemplo, eles tiverem sido atribuídos um valor de OnlineVoiceRoutingPolicy), terá a guia chamadas habilitada em equipes e pode fazer chamadas de PSTN de saída de Equipes sem precisar realizar qualquer ação administrativa de administradores.</span><span class="sxs-lookup"><span data-stu-id="9cb62-131">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="9cb62-132">Como configurar usuários para todos os VOIP e PSTN de entrada de receber chamadas em equipes</span><span class="sxs-lookup"><span data-stu-id="9cb62-132">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="9cb62-133">Para garantir que os usuários recebem todas as chamadas recebidas de VOIP e PSTN em equipes, definir o modo de coexistência do usuário para TeamsOnly no Centro de administração do Microsoft Teams, ou usar Skype para a sessão do Windows PowerShell remoto de negócios para atualizar TeamsUpgradePolicy da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="9cb62-133">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

    Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com


## <a name="see-also"></a><span data-ttu-id="9cb62-134">Confira também</span><span class="sxs-lookup"><span data-stu-id="9cb62-134">See also</span></span>
[<span data-ttu-id="9cb62-135">Configurar Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="9cb62-135">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="9cb62-136">Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="9cb62-136">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="9cb62-137">Sistema telefônico com a chamada de planos</span><span class="sxs-lookup"><span data-stu-id="9cb62-137">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="9cb62-138">Skype para referência de cmdlet do PowerShell de negócios</span><span class="sxs-lookup"><span data-stu-id="9cb62-138">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

