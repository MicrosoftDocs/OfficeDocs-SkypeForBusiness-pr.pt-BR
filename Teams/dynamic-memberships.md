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
description: Saiba como Microsoft Teams dá suporte a equipes associadas Microsoft 365 grupos usando associação dinâmica.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 74974f7b94a5d1bcadb340e132dae9e3b39a7704
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856320"
---
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="13fce-103">Visão geral da associação dinâmica de equipes</span><span class="sxs-lookup"><span data-stu-id="13fce-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="13fce-104">Microsoft Teams dá suporte a equipes associadas Microsoft 365 grupos usando *a associação dinâmica*.</span><span class="sxs-lookup"><span data-stu-id="13fce-104">Microsoft Teams supports teams associated with Microsoft 365 groups by using *dynamic membership*.</span></span> <span data-ttu-id="13fce-105">A associação dinâmica permite que a associação de uma equipe seja definida por uma ou mais regras que verificam determinados atributos de usuário no Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="13fce-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="13fce-106">Os usuários são adicionados ou removidos automaticamente às equipes corretas à medida que os atributos do usuário mudam ou os usuários ingressam e saem do locatário.</span><span class="sxs-lookup"><span data-stu-id="13fce-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="13fce-107">Com a associação dinâmica, você pode configurar equipes para determinados grupos de usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="13fce-107">With dynamic membership you can set up teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="13fce-108">Cenários possíveis incluem:</span><span class="sxs-lookup"><span data-stu-id="13fce-108">Possible scenarios include:</span></span>
- <span data-ttu-id="13fce-109">Um hospital pode criar equipes distintas para profissionais de saúde, médicos e médicos transmitirem comunicações.</span><span class="sxs-lookup"><span data-stu-id="13fce-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="13fce-110">Isso é especialmente importante se o hospital depende de funcionários temporários.</span><span class="sxs-lookup"><span data-stu-id="13fce-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="13fce-111">Uma universidade pode criar uma equipe para todos os professores em uma determinada universidade, incluindo um corpo docente adjunta que muda com frequência.</span><span class="sxs-lookup"><span data-stu-id="13fce-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="13fce-112">Uma companhia aérea deseja criar uma equipe para cada voo (como uma tarde de terça-feira sem parar de Chicago para Atlanta) e ter uma equipe de voo com frequência mudando automaticamente atribuída ou removida conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="13fce-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="13fce-113">Usando esse recurso, os membros de uma determinada equipe são atualizados automaticamente com base em um conjunto específico de critérios, em vez de gerenciar manualmente a associação.</span><span class="sxs-lookup"><span data-stu-id="13fce-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="13fce-114">Isso exige que as licenças do Azure AD Premium [](/azure/active-directory/users-groups-roles/groups-dynamic-membership) P1 e a associação à equipe possam ser atribuídas por um administrador de locatários às propriedades do Azure AD de qualquer usuário, desde que você tenha um locatário e uma conta de administrador.</span><span class="sxs-lookup"><span data-stu-id="13fce-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's Azure AD properties provided you have a tenant and an admin account.</span></span>

<span data-ttu-id="13fce-115">Microsoft Teams pode levar de alguns minutos a até duas horas para refletir as alterações dinâmicas de associação depois que elas entrarem em vigor no grupo Microsoft 365 para uma equipe.</span><span class="sxs-lookup"><span data-stu-id="13fce-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Microsoft 365 group for a team.</span></span>

<span data-ttu-id="13fce-116">Ao usar equipes com grupos dinâmicos:</span><span class="sxs-lookup"><span data-stu-id="13fce-116">When using teams with dynamic groups:</span></span>

- <span data-ttu-id="13fce-117">As regras podem definir quem é membro da equipe, mas não quem é o proprietário da equipe.</span><span class="sxs-lookup"><span data-stu-id="13fce-117">Rules can define who is a team member, but not who is a team owner.</span></span>
- <span data-ttu-id="13fce-118">Os proprietários não poderão adicionar ou remover usuários como membros da equipe, já que os membros são definidos por regras dinâmicas de grupo.</span><span class="sxs-lookup"><span data-stu-id="13fce-118">Owners will not be able to add or remove users as members of the team, since members are defined by dynamic group rules.</span></span>
- <span data-ttu-id="13fce-119">Teams clientes não permitem o gerenciamento de membros para a equipe.</span><span class="sxs-lookup"><span data-stu-id="13fce-119">Teams clients don't allow member management for the team.</span></span> <span data-ttu-id="13fce-120">Opções para adicionar membros, editar funções de membro, enviar e aprovar solicitações de junção e deixar a equipe estão ocultas.</span><span class="sxs-lookup"><span data-stu-id="13fce-120">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>

<span data-ttu-id="13fce-121">Para criar uma equipe que use [](/azure/active-directory/users-groups-roles/groups-create-rule) associação dinâmica, comece criando um grupo Microsoft 365 dinâmico e crie uma [equipe desse grupo.](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)</span><span class="sxs-lookup"><span data-stu-id="13fce-121">To create a team that uses dynamic membership, start by [creating a dynamic Microsoft 365 group](/azure/active-directory/users-groups-roles/groups-create-rule) and then [create a team from that group](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865).</span></span>

<span data-ttu-id="13fce-122">Você pode alterar uma equipe existente para ter uma associação dinâmica.</span><span class="sxs-lookup"><span data-stu-id="13fce-122">You can change an existing team to have a dynamic membership.</span></span> <span data-ttu-id="13fce-123">Consulte [Alterar a associação do grupo estático para dinâmica Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type) informações.</span><span class="sxs-lookup"><span data-stu-id="13fce-123">See [Change static group membership to dynamic in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type) for information.</span></span>

## <a name="related-topics"></a><span data-ttu-id="13fce-124">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="13fce-124">Related topics</span></span>

[<span data-ttu-id="13fce-125">Limites e especificações do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="13fce-125">Limits and specifications for Microsoft Teams</span></span>](limits-specifications-teams.md)

[<span data-ttu-id="13fce-126">Regras de associação dinâmicas para grupos Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="13fce-126">Dynamic membership rules for groups in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/groups-dynamic-membership)
