---
title: Atualizar para o Teams a partir de uma implantação local do Skype for Business – Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Atualização do Skype for Business para o Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0fe5bb56979b9b4b430076602e76ece595b8661f
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578394"
---
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="02fa8-103">Atualizar do Skype for Business para o Teams &mdash; para administradores de IT</span><span class="sxs-lookup"><span data-stu-id="02fa8-103">Upgrade from Skype for Business to Teams &mdash; for IT administrators</span></span>

## <a name="overview"></a><span data-ttu-id="02fa8-104">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="02fa8-104">Overview</span></span>

<span data-ttu-id="02fa8-105">Ao atualizar do Skype for Business para o Teams, algumas organizações exigem uma adoção progressiva que seja planejada e gerenciada por seus departamentos de TE.</span><span class="sxs-lookup"><span data-stu-id="02fa8-105">When upgrading from Skype for Business to Teams, some organizations require a progressive rollout that is planned and managed by their IT departments.</span></span> <span data-ttu-id="02fa8-106">Os artigos desta seção se aplicam principalmente a administradores de IT em grandes organizações.</span><span class="sxs-lookup"><span data-stu-id="02fa8-106">The articles in this section apply primarily to IT administrators in large organizations.</span></span> <span data-ttu-id="02fa8-107">Essas organizações geralmente são locais, mas também podem ser grandes organizações do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="02fa8-107">These organizations are typically on-premises, but they might also be large Skype for Business Online organizations.</span></span> <span data-ttu-id="02fa8-108">Antes de ler estes artigos, não deixe de ler ["Começar](upgrade-start-here.md) a trabalhar com a atualização do [Teams" e "Sobre a estrutura de atualização".](upgrade-framework.md)</span><span class="sxs-lookup"><span data-stu-id="02fa8-108">Before reading these articles, be sure to read [Getting started with your Teams Upgrade](upgrade-start-here.md) and [About the Upgrade framework](upgrade-framework.md).</span></span>


<span data-ttu-id="02fa8-109">Os artigos a seguir orientarão você durante o processo de atualização para sua organização:</span><span class="sxs-lookup"><span data-stu-id="02fa8-109">The following articles will guide you through the upgrade process for your organization:</span></span> 

- [<span data-ttu-id="02fa8-110">Métodos de atualização</span><span class="sxs-lookup"><span data-stu-id="02fa8-110">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="02fa8-111">Ferramentas para gerenciar sua atualização</span><span class="sxs-lookup"><span data-stu-id="02fa8-111">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- [<span data-ttu-id="02fa8-112">Considerações adicionais para organizações com o Skype for Business local</span><span class="sxs-lookup"><span data-stu-id="02fa8-112">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- [<span data-ttu-id="02fa8-113">Implementar sua atualização</span><span class="sxs-lookup"><span data-stu-id="02fa8-113">Implement your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="02fa8-114">Considerações sobre A Rede Telefônica Pública Comutado (PSTN)</span><span class="sxs-lookup"><span data-stu-id="02fa8-114">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="02fa8-115">Além disso, os artigos a seguir descrevem conceitos de atualização importantes e comportamentos de coexistência:</span><span class="sxs-lookup"><span data-stu-id="02fa8-115">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="02fa8-116">Coexistência do Teams e do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="02fa8-116">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="02fa8-117">Modos de coexistência - Referência</span><span class="sxs-lookup"><span data-stu-id="02fa8-117">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="02fa8-118">Experiência e conformidade do cliente do Teams a modos de coexistência</span><span class="sxs-lookup"><span data-stu-id="02fa8-118">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

>[!NOTE]
><span data-ttu-id="02fa8-119">Estes artigos usam os termos Skype for Business Online, Skype for Business Server local e Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="02fa8-119">These articles use the terms Skype for Business Online, Skype for Business Server on-premises, and Skype for Business.</span></span> <span data-ttu-id="02fa8-120">O último termo refere-se às versões online e local.</span><span class="sxs-lookup"><span data-stu-id="02fa8-120">The latter term refers to both online and on-premises versions.</span></span>

<span data-ttu-id="02fa8-121">Antes de começar, esteja ciente de que um usuário que foi migrado para o Teams não usa mais um cliente Skype for Business, exceto para ingressar em uma reunião hospedada no Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="02fa8-121">Before you get started, be aware that a user who has been migrated to Teams no longer uses a Skype for Business client except to join a meeting hosted in Skype for Business.</span></span>  <span data-ttu-id="02fa8-122">Todos os chats e chamadas recebidos chegam ao cliente do Teams do usuário, independentemente do remetente usar o Teams ou o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="02fa8-122">All incoming chats and calls land in the user’s Teams client, regardless of whether the sender uses Teams or Skype for Business.</span></span> <span data-ttu-id="02fa8-123">Todas as novas reuniões organizadas pelo usuário migrado serão agendadas como reuniões do Teams.</span><span class="sxs-lookup"><span data-stu-id="02fa8-123">Any new meetings organized by the migrated user will be scheduled as Teams meetings.</span></span> <span data-ttu-id="02fa8-124">Se o usuário tentar usar o cliente Skype for Business, o início de chats e chamadas será bloqueado.</span><span class="sxs-lookup"><span data-stu-id="02fa8-124">If the user attempts to use the Skype for Business client, initiation of chats and calls is blocked.</span></span>  <span data-ttu-id="02fa8-125">No entanto, o usuário ainda pode (e deve) usar o cliente Skype for Business para ingressar em reuniões do Skype for Business para as que ele for convidado.</span><span class="sxs-lookup"><span data-stu-id="02fa8-125">However, the user can (and must) still use the Skype for Business client to join Skype for Business meetings they are invited to.</span></span> <span data-ttu-id="02fa8-126">(Clientes mais antigos do Skype for Business que foram enviados antes de 2017 não fazem respeito ao TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="02fa8-126">(Older Skype for Business clients that shipped before 2017 do not honor TeamsUpgradePolicy.</span></span> <span data-ttu-id="02fa8-127">Certifique-se de que você está usando o cliente Skype for Business mais recente.)</span><span class="sxs-lookup"><span data-stu-id="02fa8-127">Make sure you are using the latest Skype for Business client.)</span></span>
 
<span data-ttu-id="02fa8-128">Você gerencia a transição do usuário para o Teams usando o conceito de [modo,](migration-interop-guidance-for-teams-with-skype.md)que é uma propriedade do [TeamsUpgradePolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="02fa8-128">You manage your user's transition to Teams using the concept of [mode](migration-interop-guidance-for-teams-with-skype.md), which is a property of [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span></span> <span data-ttu-id="02fa8-129">Um usuário que tenha sido migrado para o Teams conforme descrito acima está no modo "TeamsOnly".</span><span class="sxs-lookup"><span data-stu-id="02fa8-129">A user who has been migrated to Teams as described above is in “TeamsOnly” mode.</span></span>  <span data-ttu-id="02fa8-130">Para uma organização que esteja migrando para o Teams, o objetivo final é mover todos os usuários para o modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="02fa8-130">For an organization that is migrating to Teams, the ultimate goal is to move all users to TeamsOnly mode.</span></span>

>[!NOTE]
><span data-ttu-id="02fa8-131">Os usuários que têm uma conta local do Skype for Business não podem ser o TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="02fa8-131">Users who have a Skype for Business on-premises account cannot be TeamsOnly.</span></span> <span data-ttu-id="02fa8-132">Embora esses usuários possam usar o [Teams](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)no modo Ilhas, isso não fornece o conjunto completo de funcionalidades do Teams disponíveis no modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="02fa8-132">Although these users can [use Teams in Islands mode](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype), this does not provide the full set of Teams functionality that is available in TeamsOnly mode.</span></span> <span data-ttu-id="02fa8-133">Para tornar esses usuários do TeamsOnly, eles devem ser movidos para a nuvem usando as ferramentas locais do `Move-CsUser` Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="02fa8-133">To make these users TeamsOnly, they must be moved to the cloud using `Move-CsUser` in the on-premises Skype for Business Server tools.</span></span>

<span data-ttu-id="02fa8-134">Okey.</span><span class="sxs-lookup"><span data-stu-id="02fa8-134">OK.</span></span> <span data-ttu-id="02fa8-135">Vamos começar.</span><span class="sxs-lookup"><span data-stu-id="02fa8-135">Let's get started.</span></span>  <span data-ttu-id="02fa8-136">A primeira etapa é entender os [métodos de atualização disponíveis para você.](upgrade-to-teams-on-prem-upgrade-methods.md)</span><span class="sxs-lookup"><span data-stu-id="02fa8-136">The first step is understanding the [upgrade methods available to you](upgrade-to-teams-on-prem-upgrade-methods.md).</span></span>







   

## <a name="related-links"></a><span data-ttu-id="02fa8-137">Links relacionados</span><span class="sxs-lookup"><span data-stu-id="02fa8-137">Related links</span></span>

[<span data-ttu-id="02fa8-138">Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="02fa8-138">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="02fa8-139">Configurar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365</span><span class="sxs-lookup"><span data-stu-id="02fa8-139">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="02fa8-140">Mover os usuários entre um ambiente local e a nuvem</span><span class="sxs-lookup"><span data-stu-id="02fa8-140">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="02fa8-141">Definir suas configurações de coexistência e atualização</span><span class="sxs-lookup"><span data-stu-id="02fa8-141">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="02fa8-142">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="02fa8-142">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="02fa8-143">Usando o Meeting Migration Service (MMS)</span><span class="sxs-lookup"><span data-stu-id="02fa8-143">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

