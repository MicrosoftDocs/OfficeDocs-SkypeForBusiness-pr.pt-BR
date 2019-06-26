---
title: Visão geral da associação dinâmica de equipes
author: jambirk
ms.author: jambirk
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
description: Saiba mais sobre associações dinâmicas a equipes com base no AAD.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8f48309b5816c61668d240087c1f2815fc94ebe4
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221432"
---
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="f0b55-103">Visão geral da associação dinâmica de equipes</span><span class="sxs-lookup"><span data-stu-id="f0b55-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="f0b55-104">O Microsoft Teams dá suporte a equipes associadas a grupos do Office 365 usando *associação dinâmica*.</span><span class="sxs-lookup"><span data-stu-id="f0b55-104">Microsoft Teams supports teams associated with Office 365 groups by using *dynamic membership*.</span></span> <span data-ttu-id="f0b55-105">Associação dinâmica permite que a associação de uma equipe seja definida por uma ou mais regras que verificam certos atributos de usuário no Active Directory do Azure (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="f0b55-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="f0b55-106">Os usuários são automaticamente adicionados ou removidos às equipes corretas à medida que os atributos do usuário mudam ou fazem o usuário ingressar e deixar o locatário.</span><span class="sxs-lookup"><span data-stu-id="f0b55-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="f0b55-107">Com associação dinâmica, você pode configurar equipes para determinados cohorts de usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="f0b55-107">With dynamic membership you can set up teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="f0b55-108">Os cenários possíveis incluem:</span><span class="sxs-lookup"><span data-stu-id="f0b55-108">Possible scenarios include:</span></span>
- <span data-ttu-id="f0b55-109">Um hospital pode criar equipes distintas para surgeonss, médicos e para transmitir comunicações.</span><span class="sxs-lookup"><span data-stu-id="f0b55-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="f0b55-110">Isso é especialmente importante se o hospital depende de funcionários temporários.</span><span class="sxs-lookup"><span data-stu-id="f0b55-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="f0b55-111">Uma universidade pode criar uma equipe para todos os professores dentro de uma faculdade específica, incluindo um docente Adjunct que muda com frequência.</span><span class="sxs-lookup"><span data-stu-id="f0b55-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="f0b55-112">Uma companhia aérea quer criar uma equipe para cada voo (como uma tarde de terça-feira de terça-feira de Chicago para Atlanta) e ter uma equipe de voo que muda com frequência automaticamente atribuída ou removida conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="f0b55-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="f0b55-113">Usando esse recurso, uma determinada atualização dos membros da equipe com base em um conjunto específico de critérios, em vez de gerenciar manualmente a associação.</span><span class="sxs-lookup"><span data-stu-id="f0b55-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="f0b55-114">Isso exige que as licenças do Azure AD Premium e a associação da equipe possam ser [atribuídas por um administrador locatário](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) às propriedades do Azure AD de qualquer usuário, desde que você tenha um locatário e uma conta de administrador.</span><span class="sxs-lookup"><span data-stu-id="f0b55-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's Azure AD properties provided you have a tenant and an admin account.</span></span>

<span data-ttu-id="f0b55-115">O Microsoft Teams pode levar alguns minutos de até 2 horas para refletir as alterações de associação dinâmica quando entrarem em vigor no grupo do Office 365 para uma equipe.</span><span class="sxs-lookup"><span data-stu-id="f0b55-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Office 365 group for a team.</span></span>

> [!NOTE]
> - <span data-ttu-id="f0b55-116">As regras podem definir quem é um membro da equipe, mas não quem é o proprietário da equipe.</span><span class="sxs-lookup"><span data-stu-id="f0b55-116">Rules can define who is a team member, but not who is a team owner.</span></span>
> - <span data-ttu-id="f0b55-117">Consulte [limites e especificações do Microsoft Teams](limits-specifications-teams.md) para obter os limites atuais sobre tamanhos de canal e equipe.</span><span class="sxs-lookup"><span data-stu-id="f0b55-117">See [Limits and specifications for Microsoft Teams](limits-specifications-teams.md) for current limits on team and channel sizes.</span></span>
> - <span data-ttu-id="f0b55-118">Os proprietários não poderão adicionar ou remover usuários como membros da equipe, pois os membros são definidos por regras de grupo dinâmico.</span><span class="sxs-lookup"><span data-stu-id="f0b55-118">Owners will not be able to add or remove users as members of the team, since members are defined by dynamic group rules.</span></span>
> - <span data-ttu-id="f0b55-119">Os membros não poderão deixar a equipe apoiada por grupos dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="f0b55-119">Members will not be able to leave teams backed by dynamic groups.</span></span>


## <a name="creating-and-managing-an-office-365-group-with-dynamic-membership"></a><span data-ttu-id="f0b55-120">Criando e gerenciando um grupo do Office 365 com associação dinâmica</span><span class="sxs-lookup"><span data-stu-id="f0b55-120">Creating and managing an Office 365 group with dynamic membership</span></span>
<span data-ttu-id="f0b55-121">Enquanto estiver conectado como administrador de locatários, siga as instruções em [criar um grupo dinâmico e verificar o status](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span><span class="sxs-lookup"><span data-stu-id="f0b55-121">While logged in as the tenant admin, follow the instructions in [Create a dynamic group and check status](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span></span> <span data-ttu-id="f0b55-122">Conforme necessário, consulte [regras de associação dinâmica para grupos no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span><span class="sxs-lookup"><span data-stu-id="f0b55-122">As needed, refer to [Dynamic membership rules for groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span></span>

## <a name="create-a-new-team-with-your-o365-group"></a><span data-ttu-id="f0b55-123">Criar uma nova equipe com seu grupo do O365</span><span class="sxs-lookup"><span data-stu-id="f0b55-123">Create a new team with your O365 group</span></span>

<span data-ttu-id="f0b55-124">Agora, aguarde o tempo para as alterações de associação entrarem em vigor e crie uma nova equipe, conforme descrito em aprimorar os [grupos existentes do Office 365 com o Microsoft Teams](enhance-office-365-groups.md).</span><span class="sxs-lookup"><span data-stu-id="f0b55-124">Now allow time for the membership changes to take effect, and create a new team  as described in [Enhance Existing Office 365 groups with Microsoft Teams](enhance-office-365-groups.md).</span></span>

## <a name="apply-dynamic-membership-to-an-existing-team"></a><span data-ttu-id="f0b55-125">Aplicar associação dinâmica a uma equipe existente</span><span class="sxs-lookup"><span data-stu-id="f0b55-125">Apply dynamic membership to an existing team</span></span>

<span data-ttu-id="f0b55-126">Você também pode pegar uma equipe existente e alterá-la para ter uma associação dinâmica, conforme descrito em [Alterar Associação de grupo estático para dinâmico no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).</span><span class="sxs-lookup"><span data-stu-id="f0b55-126">You can also take an existing team and change it to have a dynamic membership, as described in [Change static group membership to dynamic in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).</span></span>

## <a name="changes-in-client-behavior"></a><span data-ttu-id="f0b55-127">Alterações no comportamento do cliente</span><span class="sxs-lookup"><span data-stu-id="f0b55-127">Changes in client behavior</span></span>

<span data-ttu-id="f0b55-128">Depois que a associação dinâmica estiver habilitada para uma equipe, os clientes do Teams não permitirão mais o gerenciamento de membros da equipe.</span><span class="sxs-lookup"><span data-stu-id="f0b55-128">Once dynamic membership is enabled for a team, Teams clients will no longer allow member management for the team.</span></span> <span data-ttu-id="f0b55-129">Opções para adicionar membros, editar funções de membro, enviar e aprovar solicitações de junção e deixar a equipe estar oculta.</span><span class="sxs-lookup"><span data-stu-id="f0b55-129">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>
