---
title: Considerações sobre o modo Teams Only (Apenas Teams)
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: O administrador pode aprender sobre como se preparar para uma atualização para Microsoft Teams modo Somente no Microsoft Teams de administração.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b2232d4774a31f3b081b2410371a5903debe9123
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239008"
---
# <a name="teams-only-mode-considerations"></a><span data-ttu-id="afd86-103">Considerações sobre o modo Teams Only (Apenas Teams)</span><span class="sxs-lookup"><span data-stu-id="afd86-103">Teams Only mode considerations</span></span>

<span data-ttu-id="afd86-104">Os administradores de Microsoft 365 ou Office 365 podem atualizar usuários individuais ou o locatário inteiro para Teams modo Somente.</span><span class="sxs-lookup"><span data-stu-id="afd86-104">Administrators of Microsoft 365 or Office 365 organizations can upgrade either individual users or the entire tenant to Teams Only mode.</span></span>  

[!INCLUDE [sfbo-retirement-skype](../Skype/Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="afd86-105">A atualização para o modo Somente Teams oferece aos usuários os benefícios completos do Microsoft Teams, o hub para trabalho em equipe no Microsoft 365 ou Office 365, por meio de uma única experiência do cliente.</span><span class="sxs-lookup"><span data-stu-id="afd86-105">Upgrading to Teams Only mode offers users the full benefits of Microsoft Teams, the hub for teamwork in Microsoft 365 or Office 365, via a single client experience.</span></span> <span data-ttu-id="afd86-106">Os usuários no modo somente Teams receberão todas as chamadas e chats no Teams, independentemente de o remetente usar Skype for Business ou Teams e se beneficiarão do suporte de interop e federação.</span><span class="sxs-lookup"><span data-stu-id="afd86-106">Users in Teams Only mode will receive all calls and chats in Teams, regardless of whether the sender is using Skype for Business or Teams, and benefit from interop and federation support.</span></span>

<span data-ttu-id="afd86-107">Embora milhares de clientes tenham sido atualizados com êxito para Microsoft Teams, há considerações que podem influenciar a linha do tempo de atualização da sua organização e a experiência do usuário ao longo do caminho.</span><span class="sxs-lookup"><span data-stu-id="afd86-107">Although thousands of customers have successfully upgraded to Microsoft Teams, there are considerations that may influence your organization's upgrade timeline and user experience along the way.</span></span> <span data-ttu-id="afd86-108">Para obter a melhor experiência do usuário, confirme se o Microsoft Teams atende a seus requisitos de colaboração e comunicação, verifique se a rede está pronta para dar suporte ao Microsoft Teams e implemente seu plano de preparação do usuário antes de atualizar os usuários para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="afd86-108">For the best user experience, confirm that Teams meets your collaboration and communication requirements, make sure that your network is ready to support Teams, and implement your user readiness plan before upgrading users to Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="afd86-109">Se você está apenas iniciando seu planejamento de atualização, não deixe de revisar nosso guia De início [Microsoft Teams atualização.](upgrade-start-here.md)</span><span class="sxs-lookup"><span data-stu-id="afd86-109">If you are just starting your upgrade planning, be sure to review our [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md) guide.</span></span> 

<span data-ttu-id="afd86-110">**Considerações de coexistência:** as organizações que já usam o Skype for Business Online e/ou Skype for Business Server podem introduzir Teams em seu ambiente em um ritmo que atenda às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="afd86-110">**Coexistence considerations**: Organizations already using Skype for Business Online and/or Skype for Business Server can introduce Teams into their environment at a pace that meets their needs.</span></span> <span data-ttu-id="afd86-111">As organizações podem Teams um conjunto desejado de usuários, conforme necessário, e os usuários que usam o Teams podem se comunicar com usuários que usam Skype for Business e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="afd86-111">Organizations can incrementally roll out Teams to a desired set of users as needed, and users who use Teams can communicate with users who use Skype for Business and vice versa.</span></span> <span data-ttu-id="afd86-112">Para gerenciar essa experiência, os administradores usam modos de coexistência, que definem a experiência do cliente do usuário final, o comportamento de roteamento de chats e chamadas de entrada e se novas reuniões são agendadas em Teams ou Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="afd86-112">To manage this experience, administrators use coexistence modes, which define the end-user client experience, the routing behavior of incoming chats and calls, and whether new meetings are scheduled in Teams or Skype for Business.</span></span> <span data-ttu-id="afd86-113">Os usuários podem federar com usuários em outras organizações se o usuário for atualizado para Teams **Somente**; no entanto, a melhor experiência é fornecida quando ambos os usuários usam Teams.</span><span class="sxs-lookup"><span data-stu-id="afd86-113">Users can federate with users in other organizations if the user is upgraded to **Teams Only**; however, the best experience is provided when both users use Teams.</span></span> <span data-ttu-id="afd86-114">Os usuários que são atualizados para o Teams Somente ainda podem ingressar Skype for Business reuniões.</span><span class="sxs-lookup"><span data-stu-id="afd86-114">Users who are upgraded to Teams Only can still join Skype for Business meetings.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="afd86-115">Para obter informações mais detalhadas sobre coexistência, consulte [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="afd86-115">For more detailed information about coexistence, please refer to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span> <span data-ttu-id="afd86-116">Para obter mais informações sobre Teams e Skype (Consumidor), consulte [Teams e Skype interoperabilidade](teams-skype-interop.md).</span><span class="sxs-lookup"><span data-stu-id="afd86-116">For more information about Teams and Skype (Consumer), see [Teams and Skype interoperability](teams-skype-interop.md).</span></span>


<span data-ttu-id="afd86-117">**Considerações específicas** do usuário : alguns cenários do usuário ainda estão evoluindo, e os administradores podem optar por adiar temporariamente a atualização de determinados usuários enquanto atualiza outros usuários na organização.</span><span class="sxs-lookup"><span data-stu-id="afd86-117">**User-specific considerations**: Some user scenarios are still evolving, and administrators may decide to temporarily postpone the upgrade of certain users while upgrading other users in the organization.</span></span> <span data-ttu-id="afd86-118">Em particular, ainda estamos trabalhando em cenários de endereçamento para usuários cujo dispositivo principal é baseado em VDI.</span><span class="sxs-lookup"><span data-stu-id="afd86-118">In particular, we are still working on addressing scenarios for users whose primary device is VDI-based.</span></span> <span data-ttu-id="afd86-119">Para anúncios de site, monitore [o Microsoft 365 mapa](https://www.microsoft.com/microsoft-365/roadmap).</span><span class="sxs-lookup"><span data-stu-id="afd86-119">For site announcements, monitor the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

> [!NOTE]
> <span data-ttu-id="afd86-120">Antes de mover para Teams modo Somente, você precisa substituir ou atualizar dispositivos que não suportam Teams.</span><span class="sxs-lookup"><span data-stu-id="afd86-120">Before you move to Teams Only mode you need to replace or update devices that don't support Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="afd86-121">**Lembre-se**: a mudança para Teams é mais do que uma migração técnica.</span><span class="sxs-lookup"><span data-stu-id="afd86-121">**Remember**: The move to Teams is more than a technical migration.</span></span> <span data-ttu-id="afd86-122">Uma atualização bem-sucedida avalia a preparação técnica e a preparação do usuário final.</span><span class="sxs-lookup"><span data-stu-id="afd86-122">A successful upgrade assesses both technical readiness and end-user readiness.</span></span> <span data-ttu-id="afd86-123">Revise nossa Skype for Business para Teams [de](upgrade-framework.md) atualização para obter mais informações sobre como planejar uma implementação da atualização para Teams.</span><span class="sxs-lookup"><span data-stu-id="afd86-123">Review our Skype for Business to Teams [upgrade guidance](upgrade-framework.md) for more information on planning an implementing your upgrade to Teams.</span></span>  
