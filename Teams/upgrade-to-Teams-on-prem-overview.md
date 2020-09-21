---
title: Atualize para o Teams a partir de uma implantação local do Skype for Business-Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
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
ms.openlocfilehash: e146394b5f000ce984d7bfaff5e6674c2c091b98
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47955878"
---
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="e1f2d-103">Atualize o Skype for Business para o Teams &mdash; para administradores de ti</span><span class="sxs-lookup"><span data-stu-id="e1f2d-103">Upgrade from Skype for Business to Teams &mdash; for IT administrators</span></span>

## <a name="overview"></a><span data-ttu-id="e1f2d-104">Visão geral</span><span class="sxs-lookup"><span data-stu-id="e1f2d-104">Overview</span></span>

<span data-ttu-id="e1f2d-105">Ao fazer a atualização do Skype for Business para o Teams, algumas organizações exigem uma distribuição progressiva planejada e gerenciada pelos departamentos de ti.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-105">When upgrading from Skype for Business to Teams, some organizations require a progressive rollout that is planned and managed by their IT departments.</span></span> <span data-ttu-id="e1f2d-106">Os artigos nesta seção se aplicam principalmente aos administradores de ti em grandes organizações.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-106">The articles in this section apply primarily to IT administrators in large organizations.</span></span> <span data-ttu-id="e1f2d-107">Essas organizações são geralmente locais, mas também podem ser organizações do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-107">These organizations are typically on-premises, but they might also be large Skype for Business Online organizations.</span></span> <span data-ttu-id="e1f2d-108">Antes de ler estes artigos, lembre-se de ler introdução [à atualização do seu Teams](upgrade-start-here.md) e [sobre a estrutura de atualização](upgrade-framework.md).</span><span class="sxs-lookup"><span data-stu-id="e1f2d-108">Before reading these articles, be sure to read [Getting started with your Teams Upgrade](upgrade-start-here.md) and [About the Upgrade framework](upgrade-framework.md).</span></span>


<span data-ttu-id="e1f2d-109">Os artigos a seguir o orientarão durante o processo de atualização de sua organização:</span><span class="sxs-lookup"><span data-stu-id="e1f2d-109">The following articles will guide you through the upgrade process for your organization:</span></span> 

- [<span data-ttu-id="e1f2d-110">Métodos de atualização</span><span class="sxs-lookup"><span data-stu-id="e1f2d-110">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="e1f2d-111">Ferramentas para gerenciar a atualização</span><span class="sxs-lookup"><span data-stu-id="e1f2d-111">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- [<span data-ttu-id="e1f2d-112">Considerações adicionais sobre organizações com o Skype for Business no local</span><span class="sxs-lookup"><span data-stu-id="e1f2d-112">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- [<span data-ttu-id="e1f2d-113">Implementar sua atualização</span><span class="sxs-lookup"><span data-stu-id="e1f2d-113">Implement your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="e1f2d-114">Considerações sobre PSTN (rede telefônica pública comutada)</span><span class="sxs-lookup"><span data-stu-id="e1f2d-114">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="e1f2d-115">Além disso, os seguintes artigos descrevem conceitos importantes de atualização e comportamentos de coexistência:</span><span class="sxs-lookup"><span data-stu-id="e1f2d-115">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="e1f2d-116">Coexistência de Teams e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e1f2d-116">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="e1f2d-117">Modos de coexistência-referência</span><span class="sxs-lookup"><span data-stu-id="e1f2d-117">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="e1f2d-118">Experiência e conformidade do cliente do Teams a modos de coexistência</span><span class="sxs-lookup"><span data-stu-id="e1f2d-118">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

>[!NOTE]
><span data-ttu-id="e1f2d-119">Estes artigos usam os termos Skype for Business Online, Skype for Business Server local e Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-119">These articles use the terms Skype for Business Online, Skype for Business Server on-premises, and Skype for Business.</span></span> <span data-ttu-id="e1f2d-120">O último termo refere-se às versões online e local.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-120">The latter term refers to both online and on-premises versions.</span></span>

<span data-ttu-id="e1f2d-121">Antes de começar, lembre-se de que um usuário que foi migrado para o Microsoft Teams não usa mais um cliente Skype for Business, exceto para ingressar em uma reunião hospedada no Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-121">Before you get started, be aware that a user who has been migrated to Teams no longer uses a Skype for Business client except to join a meeting hosted in Skype for Business.</span></span>  <span data-ttu-id="e1f2d-122">Todos os chats e chamadas recebidos chegam ao cliente do Teams do usuário, independentemente do remetente usar o Teams ou o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-122">All incoming chats and calls land in the user’s Teams client, regardless of whether the sender uses Teams or Skype for Business.</span></span> <span data-ttu-id="e1f2d-123">Qualquer reunião nova organizada pelo usuário migrado será agendada como reuniões do teams.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-123">Any new meetings organized by the migrated user will be scheduled as Teams meetings.</span></span> <span data-ttu-id="e1f2d-124">Se o usuário tentar usar o cliente Skype for Business, a iniciação de chats e chamadas será bloqueada.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-124">If the user attempts to use the Skype for Business client, initiation of chats and calls is blocked.</span></span>  <span data-ttu-id="e1f2d-125">No entanto, o usuário pode (e deve) ainda usar o cliente Skype for Business para ingressar em reuniões do Skype for Business às quais eles são convidados.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-125">However, the user can (and must) still use the Skype for Business client to join Skype for Business meetings they are invited to.</span></span> <span data-ttu-id="e1f2d-126">(Os clientes Skype for Business mais antigos que foram enviados antes do 2017 não obedecem ao TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-126">(Older Skype for Business clients that shipped before 2017 do not honor TeamsUpgradePolicy.</span></span> <span data-ttu-id="e1f2d-127">Verifique se você está usando o mais recente cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-127">Make sure you are using the latest Skype for Business client.)</span></span>
 
<span data-ttu-id="e1f2d-128">Você gerencia a transição do seu usuário para o Microsoft Teams usando o conceito de [Mode](migration-interop-guidance-for-teams-with-skype.md), que é uma propriedade de [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="e1f2d-128">You manage your user's transition to Teams using the concept of [mode](migration-interop-guidance-for-teams-with-skype.md), which is a property of [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span></span> <span data-ttu-id="e1f2d-129">Um usuário que foi migrado para o Teams, conforme descrito acima, está no modo "TeamsOnly".</span><span class="sxs-lookup"><span data-stu-id="e1f2d-129">A user who has been migrated to Teams as described above is in “TeamsOnly” mode.</span></span>  <span data-ttu-id="e1f2d-130">Para uma organização que esteja migrando para o Teams, o objetivo final é mover todos os usuários para o modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-130">For an organization that is migrating to Teams, the ultimate goal is to move all users to TeamsOnly mode.</span></span>

<span data-ttu-id="e1f2d-131">Okey.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-131">OK.</span></span> <span data-ttu-id="e1f2d-132">Vamos começar.</span><span class="sxs-lookup"><span data-stu-id="e1f2d-132">Let's get started.</span></span>  <span data-ttu-id="e1f2d-133">A primeira etapa é entender os [métodos de atualização disponíveis para você](upgrade-to-teams-on-prem-upgrade-methods.md).</span><span class="sxs-lookup"><span data-stu-id="e1f2d-133">The first step is understanding the [upgrade methods available to you](upgrade-to-teams-on-prem-upgrade-methods.md).</span></span>







   

## <a name="related-links"></a><span data-ttu-id="e1f2d-134">Links relacionados</span><span class="sxs-lookup"><span data-stu-id="e1f2d-134">Related links</span></span>

[<span data-ttu-id="e1f2d-135">Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e1f2d-135">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="e1f2d-136">Configurar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365</span><span class="sxs-lookup"><span data-stu-id="e1f2d-136">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="e1f2d-137">Mover os usuários entre um ambiente local e a nuvem</span><span class="sxs-lookup"><span data-stu-id="e1f2d-137">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="e1f2d-138">Definir suas configurações de coexistência e atualização</span><span class="sxs-lookup"><span data-stu-id="e1f2d-138">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="e1f2d-139">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="e1f2d-139">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="e1f2d-140">Usando o Meeting Migration Service (MMS)</span><span class="sxs-lookup"><span data-stu-id="e1f2d-140">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

