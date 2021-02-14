---
title: Visão geral da associação dinâmica de equipes
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: Saiba como o Microsoft Teams dá suporte a equipes associadas a grupos do Microsoft 365 usando associação dinâmica.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 75bd058d79b1f54a40ad0e42207178c9c29d08cd
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583920"
---
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="b5e8f-103">Visão geral da associação dinâmica de equipes</span><span class="sxs-lookup"><span data-stu-id="b5e8f-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="b5e8f-104">O Microsoft Teams dá suporte a equipes associadas a grupos do Microsoft 365 usando *associação dinâmica.*</span><span class="sxs-lookup"><span data-stu-id="b5e8f-104">Microsoft Teams supports teams associated with Microsoft 365 groups by using *dynamic membership*.</span></span> <span data-ttu-id="b5e8f-105">A associação dinâmica permite que a associação de uma equipe seja definida por uma ou mais regras que verificam determinados atributos do usuário no Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="b5e8f-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="b5e8f-106">Os usuários são adicionados ou removidos automaticamente às equipes corretas à medida que os atributos do usuário mudam ou os usuários ingressam e saem do locatário.</span><span class="sxs-lookup"><span data-stu-id="b5e8f-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="b5e8f-107">Com a associação dinâmica, você pode configurar equipes para determinados tipos de usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="b5e8f-107">With dynamic membership you can set up teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="b5e8f-108">Os cenários possíveis incluem:</span><span class="sxs-lookup"><span data-stu-id="b5e8f-108">Possible scenarios include:</span></span>
- <span data-ttu-id="b5e8f-109">Um hospital pode criar equipes distintas para médicos, médicos e médicos para transmitir comunicações.</span><span class="sxs-lookup"><span data-stu-id="b5e8f-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="b5e8f-110">Isso é especialmente importante se o hospital depende de funcionários temporários.</span><span class="sxs-lookup"><span data-stu-id="b5e8f-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="b5e8f-111">Uma universidade pode criar uma equipe para todos os docentes em uma faculdade específica, incluindo um corpo docente adjunta que muda com frequência.</span><span class="sxs-lookup"><span data-stu-id="b5e8f-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="b5e8f-112">Uma companhia aérea quer criar uma equipe para cada voo (como uma terça-feira à tarde sem parar de Chicago para Atlanta) e ter uma equipe de voos de mudança frequente atribuída ou removida automaticamente, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="b5e8f-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="b5e8f-113">Usando esse recurso, os membros de uma determinada equipe são atualizados automaticamente com base em um conjunto específico de critérios, em vez de gerenciar manualmente a associação.</span><span class="sxs-lookup"><span data-stu-id="b5e8f-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="b5e8f-114">Isso requer licenças do Azure AD Premium [](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) P1 e a associação à equipe pode ser atribuída por um administrador de locatário às propriedades do Azure AD de qualquer usuário, desde que você tenha um locatário e uma conta de administrador.</span><span class="sxs-lookup"><span data-stu-id="b5e8f-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's Azure AD properties provided you have a tenant and an admin account.</span></span>

<span data-ttu-id="b5e8f-115">O Microsoft Teams pode levar de alguns minutos a até duas horas para refletir as alterações dinâmicas de associação depois que elas entrarem em vigor no grupo do Microsoft 365 para uma equipe.</span><span class="sxs-lookup"><span data-stu-id="b5e8f-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Microsoft 365 group for a team.</span></span>

> [!NOTE]
> - <span data-ttu-id="b5e8f-116">As regras podem definir quem é um membro da equipe, mas não quem é o proprietário da equipe.</span><span class="sxs-lookup"><span data-stu-id="b5e8f-116">Rules can define who is a team member, but not who is a team owner.</span></span>
> - <span data-ttu-id="b5e8f-117">Consulte [Limites e especificações do Microsoft Teams para](limits-specifications-teams.md) ver os limites atuais de tamanhos de equipe e canal.</span><span class="sxs-lookup"><span data-stu-id="b5e8f-117">See [Limits and specifications for Microsoft Teams](limits-specifications-teams.md) for current limits on team and channel sizes.</span></span>
> - <span data-ttu-id="b5e8f-118">Os proprietários não poderão adicionar ou remover usuários como membros da equipe, uma vez que os membros são definidos por regras dinâmicas de grupo.</span><span class="sxs-lookup"><span data-stu-id="b5e8f-118">Owners will not be able to add or remove users as members of the team, since members are defined by dynamic group rules.</span></span>
> -    <span data-ttu-id="b5e8f-119">Os membros não poderão sair das equipes com o apoio de grupos dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="b5e8f-119">Members will not be able to leave teams backed by dynamic groups.</span></span>

## <a name="creating-and-managing-a-microsoft-365-group-with-dynamic-membership"></a><span data-ttu-id="b5e8f-120">Criar e gerenciar um grupo do Microsoft 365 com associação dinâmica</span><span class="sxs-lookup"><span data-stu-id="b5e8f-120">Creating and managing a Microsoft 365 group with dynamic membership</span></span>

<span data-ttu-id="b5e8f-121">Enquanto estiver conectado como administrador do locatário, siga as instruções em Criar um [grupo dinâmico e verificar o status.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)</span><span class="sxs-lookup"><span data-stu-id="b5e8f-121">While logged in as the tenant admin, follow the instructions in [Create a dynamic group and check status](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span></span> <span data-ttu-id="b5e8f-122">Conforme necessário, consulte [as regras de associação dinâmicas para grupos no Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)</span><span class="sxs-lookup"><span data-stu-id="b5e8f-122">As needed, refer to [Dynamic membership rules for groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span></span>

## <a name="create-a-new-team-with-your-microsoft-365-group"></a><span data-ttu-id="b5e8f-123">Criar uma nova equipe com seu grupo do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b5e8f-123">Create a new team with your Microsoft 365 group</span></span>

<span data-ttu-id="b5e8f-124">Agora, permita que as alterações de associação entre em vigor e crie uma nova equipe conforme descrito em Criar uma equipe a partir de [um grupo existente.](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)</span><span class="sxs-lookup"><span data-stu-id="b5e8f-124">Now allow time for the membership changes to take effect, and create a new team  as described in [Create a team from an existing group](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865).</span></span>

## <a name="apply-dynamic-membership-to-an-existing-team"></a><span data-ttu-id="b5e8f-125">Aplicar associação dinâmica a uma equipe existente</span><span class="sxs-lookup"><span data-stu-id="b5e8f-125">Apply dynamic membership to an existing team</span></span>

<span data-ttu-id="b5e8f-126">Você também pode assumir uma equipe existente e alterá-la para ter uma associação dinâmica, conforme descrito em Alterar associação de grupo estático para dinâmica [no Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)</span><span class="sxs-lookup"><span data-stu-id="b5e8f-126">You can also take an existing team and change it to have a dynamic membership, as described in [Change static group membership to dynamic in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).</span></span>

## <a name="changes-in-client-behavior"></a><span data-ttu-id="b5e8f-127">Alterações no comportamento do cliente</span><span class="sxs-lookup"><span data-stu-id="b5e8f-127">Changes in client behavior</span></span>

<span data-ttu-id="b5e8f-128">Depois que a associação dinâmica for habilitada para uma equipe, os clientes do Teams não permitirão mais o gerenciamento de membros para a equipe.</span><span class="sxs-lookup"><span data-stu-id="b5e8f-128">Once dynamic membership is enabled for a team, Teams clients will no longer allow member management for the team.</span></span> <span data-ttu-id="b5e8f-129">As opções para adicionar membros, editar funções de membro, enviar e aprovar solicitações de junção e deixar a equipe estão ocultas.</span><span class="sxs-lookup"><span data-stu-id="b5e8f-129">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>
