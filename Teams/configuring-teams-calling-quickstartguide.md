---
title: Guia de início rápido-Configurando planos de chamada
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: Guia de início rápido para configurar planos de chamada no Microsoft Teams para que você possa obter um conjunto de usuários em funcionamento.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 10d52aca36d92029f8ee832be84e6dc7d140f749
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43902876"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="b6b39-103">Guia de Início Rápido: como configurar Planos de Chamadas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b6b39-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="b6b39-104">Este guia o ajudará a estabelecer um grupo de usuários para que eles possam explorar os Planos de Chamadas no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b6b39-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="b6b39-105">Leia o anúncio feito em 12 de dezembro de 2017, dos Planos de Chamadas no Microsoft Teams: [A comunicação inteligente avança com as chamadas do Microsoft Teams](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="b6b39-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="b6b39-106">Recomendamos que, em paralelo com este guia de início rápido, você leia o [sistema telefônico com planos de chamadas](calling-plan-landing-page.md) e o [FastTrack](https://aka.ms/cloudvoice) para planejar e conduzir uma implementação bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="b6b39-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="b6b39-107">Com a inclusão dos Planos de Chamadas, um recurso do Office 365 acionado pelo Skype for Business, agora você pode usar o Microsoft Teams para fazer e receber chamadas de telefones fixos e celulares pela PSTN (Rede Telefônica Pública Comutada).</span><span class="sxs-lookup"><span data-stu-id="b6b39-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Captura de tela mostrando a página contatos no Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="b6b39-109">Pré-requisitos para habilitar a guia **Chamadas** no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b6b39-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="b6b39-110">Para habilitar a guia **chamadas** em Teams os usuários precisam ter chamadas do 1:1 habilitadas no Teams e usar um cliente do teams que suporte chamadas para o 1:1 Teams.</span><span class="sxs-lookup"><span data-stu-id="b6b39-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="b6b39-111">Para saber como gerenciar chamadas do 1:1 no Teams, leia [set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b6b39-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="b6b39-112">Para saber quais clientes dão suporte à chamada, leia [limites e especificações do Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span><span class="sxs-lookup"><span data-stu-id="b6b39-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="b6b39-113">No momento, o correio de voz não estará disponível na guia chamadas, a menos que o usuário esteja habilitado para chamadas PSTN.</span><span class="sxs-lookup"><span data-stu-id="b6b39-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="b6b39-114">Pré-requisitos para habilitar o **teclado de discagem** no Teams</span><span class="sxs-lookup"><span data-stu-id="b6b39-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="b6b39-115">Para habilitar a guia do **teclado de discagem** no Teams e permitir que os usuários façam e recebam chamadas PSTN, você precisará provisionar usuários para o sistema telefônico e planos de chamadas.</span><span class="sxs-lookup"><span data-stu-id="b6b39-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="b6b39-116">Para saber como configurar planos de chamadas, leia [configurar planos de chamadas](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="b6b39-116">To learn how to set up Calling Plans, read [Set up Calling Plans](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span></span>
<span data-ttu-id="b6b39-117">Além disso, somente para usuários do Teams, você deve garantir que "permitir chamadas privadas" esteja habilitado na política de chamada de equipes.</span><span class="sxs-lookup"><span data-stu-id="b6b39-117">Additionally, for Teams only users, you must ensure that "Allow private calling" is enabled in the Teams calling policy.</span></span> <span data-ttu-id="b6b39-118">Consulte [gerenciar equipes durante a transição para o novo centro de administração do Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b6b39-118">See [Manage Teams during the transition to the new Microsoft Teams admin center](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center) for more information.</span></span>
> [!NOTE]
> <span data-ttu-id="b6b39-119">Você também pode usar o roteamento direto para permitir que os usuários façam e recebam chamadas PSTN.</span><span class="sxs-lookup"><span data-stu-id="b6b39-119">You can also use Direct Routing to allow your users to make and receive PSTN calls.</span></span> <span data-ttu-id="b6b39-120">Para saber como configurar o roteamento direto, leia [Configurar roteamento direto](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span><span class="sxs-lookup"><span data-stu-id="b6b39-120">To learn how to set up Direct Routing, read [Configure Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="b6b39-121">Usar o TeamsUpgradePolicy para controlar onde as chamadas se esterram</span><span class="sxs-lookup"><span data-stu-id="b6b39-121">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="b6b39-122">Para controlar se as chamadas recebidas (e chats) chegam ao Teams ou ao Skype for Business, os administradores usam o TeamsUpgradePolicy usando o [centro de administração do Microsoft Teams](https://aka.ms/teamsadmincenter) ou usando uma sessão remota do Windows PowerShell com os cmdlets do [Skype for Business](https://docs.microsoft.com/powershell/module/skype) .</span><span class="sxs-lookup"><span data-stu-id="b6b39-122">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](https://docs.microsoft.com/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="b6b39-123">A configuração padrão de TeamsUpgradePolicy é o modo de ilhas, que é projetado para garantir que os fluxos de trabalho de negócios existentes não sejam interrompidos durante uma implantação do teams.</span><span class="sxs-lookup"><span data-stu-id="b6b39-123">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="b6b39-124">Por padrão, VoIP, PSTN e chamadas federadas para seus usuários continuarão a ser roteadas para o Skype for Business até você atualizar a política para habilitar as chamadas de entrada para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b6b39-124">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="b6b39-125">Quando os destinatários estão no modo de ilhas:</span><span class="sxs-lookup"><span data-stu-id="b6b39-125">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="b6b39-126">As chamadas de VOIP recebidas que originou no Skype for Business sempre chegam ao cliente Skype for Business do destinatário.</span><span class="sxs-lookup"><span data-stu-id="b6b39-126">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="b6b39-127">Chamadas de VOIP recebidas originadas no Teams Land no Teams, *se o remetente e o receptor estiverem no mesmo locatário*.</span><span class="sxs-lookup"><span data-stu-id="b6b39-127">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="b6b39-128">VOIP federado de entrada (independentemente de qual o cliente originou) e as chamadas PSTN sempre chegam ao cliente Skype for Business do destinatário.</span><span class="sxs-lookup"><span data-stu-id="b6b39-128">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="b6b39-129">Para garantir que as chamadas VOIP e PSTN de entrada sejam sempre chamadas para o cliente do teams de um usuário, atualize o modo de coexistência do usuário para ser TeamsOnly (ou seja, atribua a eles a instância "UpgradeToTeams" do TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="b6b39-129">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="b6b39-130">Para obter mais informações sobre modos de coexistência e TeamsUpgradePolicy, consulte [orientação de migração e interoperabilidade para organizações que usam o Skype for Business em equipe](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype) .</span><span class="sxs-lookup"><span data-stu-id="b6b39-130">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="b6b39-131">**INFORMA**</span><span class="sxs-lookup"><span data-stu-id="b6b39-131">**NOTES**</span></span>
 - <span data-ttu-id="b6b39-132">Os telefones IP do Skype for Business receberão chamadas, mesmo se o usuário estiver no modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="b6b39-132">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="b6b39-133">Os usuários que foram provisionados com licenças do sistema telefônico e planos de chamadas para uso com o Skype for Business online (por exemplo, um valor de OnlineVoiceRoutingPolicy) terão a guia chamadas habilitada no Teams e poderão fazer chamadas PSTN de saída do teams sem administradores com a necessidade de tomar qualquer ação administrativa.</span><span class="sxs-lookup"><span data-stu-id="b6b39-133">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="b6b39-134">Como configurar os usuários para receber todas as chamadas VOIP e PSTN de entrada no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b6b39-134">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="b6b39-135">Para garantir que os usuários recebam todas as chamadas VOIP e PSTN de entrada no Teams, defina o modo de coexistência do usuário como TeamsOnly no centro de administração do Microsoft Teams ou use a sessão remota do Windows PowerShell do Skype for Business para atualizar o TeamsUpgradePolicy da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="b6b39-135">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

    Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com


## <a name="see-also"></a><span data-ttu-id="b6b39-136">Confira também</span><span class="sxs-lookup"><span data-stu-id="b6b39-136">See also</span></span>
[<span data-ttu-id="b6b39-137">Configurar Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="b6b39-137">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="b6b39-138">Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b6b39-138">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="b6b39-139">Sistema de Telefonia com Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="b6b39-139">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="b6b39-140">Referência do cmdlet do PowerShell do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b6b39-140">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

