---
title: Visão geral da associação dinâmica de equipes
author: jambirk
ms.author: jambirk
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Saiba mais sobre a associação de equipe dinâmica com base em AAD.
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7a96205f1971207f81d6191ef46e1be25e063f4c
ms.sourcegitcommit: 160ced7013c1c46595c4362c2f32c5769b082294
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/27/2018
ms.locfileid: "26699768"
---
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="6419c-103">Visão geral da associação dinâmica de equipes</span><span class="sxs-lookup"><span data-stu-id="6419c-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="6419c-104">Microsoft Teams suporta as equipes associadas a grupos de Office 365 usando a participação dinâmica.</span><span class="sxs-lookup"><span data-stu-id="6419c-104">Microsoft Teams supports teams associated with Office 365 groups using dynamic membership.</span></span> <span data-ttu-id="6419c-105">Participação dinâmica permite a associação de uma equipe sejam definidos por uma ou mais regras que verificam para alguns atributos de usuário no Windows Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="6419c-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (AAD).</span></span> <span data-ttu-id="6419c-106">Automaticamente, a usuários forem adicionados ou removidos para as equipes corretas como alterar os atributos de usuário ou usuários entram e saem de locatário.</span><span class="sxs-lookup"><span data-stu-id="6419c-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="6419c-107">Com associação dinâmica, que você pode a instalação para determinadas equipes colaboradores de usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="6419c-107">With dynamic membership you can setup teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="6419c-108">Os possíveis cenários incluem:</span><span class="sxs-lookup"><span data-stu-id="6419c-108">Possible scenarios include:</span></span>
- <span data-ttu-id="6419c-109">Um hospital pode criar equipes distintas para enfermeiros, os médicos e cirurgiões difusão de comunicações.</span><span class="sxs-lookup"><span data-stu-id="6419c-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="6419c-110">Isso é especialmente importante se hospital depende de funcionários temporários.</span><span class="sxs-lookup"><span data-stu-id="6419c-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="6419c-111">Uma universidade pode criar uma equipe para todo o Corpo Docente dentro de uma faculdade específico, incluindo um corpo docente prestado que muda com frequência.</span><span class="sxs-lookup"><span data-stu-id="6419c-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="6419c-112">Uma companhias quer criar uma equipe para cada aéreas (como uma terça-feira tarde contínuas de Chicago para Atlanta) e ter um crew aéreas muda com frequência automaticamente atribuídos ou removidos conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="6419c-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="6419c-113">Usar esse recurso, a atualização de membros da equipe de um determinado automaticamente com base em um conjunto específico de critérios, em vez de gerenciar manualmente a associação.</span><span class="sxs-lookup"><span data-stu-id="6419c-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="6419c-114">Esse procedimento exige o Windows Azure AD Premium P1 licenças e participação na equipe pode ser [atribuído por um administrador proprietário](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) para as propriedades do usuário, qualquer AAD fornecido a que você tem uma conta de administrador e de um inquilino.</span><span class="sxs-lookup"><span data-stu-id="6419c-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's AAD properties provided you have a tenant and an admin account.</span></span> 

<span data-ttu-id="6419c-115">Microsoft Teams pode levar alguns minutos até 2 horas para refletir as alterações de associação dinâmica depois que eles entrem em vigor no grupo Office 365 para uma equipe.</span><span class="sxs-lookup"><span data-stu-id="6419c-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Office 365 group for a team.</span></span> 

> [!NOTE]
> - <span data-ttu-id="6419c-116">Regras podem definir os membros da equipe, mas não os proprietários de equipe.</span><span class="sxs-lookup"><span data-stu-id="6419c-116">Rules can define team members, but not team Owners.</span></span>
> - <span data-ttu-id="6419c-117">Consulte [limites e as especificações para equipes da Microsoft](limits-specifications-teams.md) para atuais limites de tamanhos de equipe e de canal.</span><span class="sxs-lookup"><span data-stu-id="6419c-117">See [Limits and specifications for Microsoft Teams](limits-specifications-teams.md) for current limits on Team and channel sizes.</span></span>

## <a name="creating-and-managing-an-office-365-group-with-dynamic-membership"></a><span data-ttu-id="6419c-118">Criando e gerenciando um grupo do Office 365 com participação dinâmica</span><span class="sxs-lookup"><span data-stu-id="6419c-118">Creating and managing an Office 365 group with dynamic membership</span></span>
<span data-ttu-id="6419c-119">Enquanto logado como o administrador de locatário, siga as instruções em [um grupo dinâmico de criar e verificar o status](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span><span class="sxs-lookup"><span data-stu-id="6419c-119">While logged in as the tenant Admin, follow the instructions in [Create a dynamic group and check status](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span></span> <span data-ttu-id="6419c-120">Conforme necessário, consulte [regras de participação dinâmicas para grupos do Active Directory do Windows Azure](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span><span class="sxs-lookup"><span data-stu-id="6419c-120">As needed, refer to [Dynamic membership rules for groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span></span>

## <a name="create-a-new-team-with-your-o365-group"></a><span data-ttu-id="6419c-121">Criar uma nova equipe com seu grupo de O365</span><span class="sxs-lookup"><span data-stu-id="6419c-121">Create a new team with your O365 group</span></span>

<span data-ttu-id="6419c-122">Agora, reserve um tempo para as alterações de associação entre em vigor e crie uma nova equipe, conforme descrito em [grupos de aprimorar existente Office 365 com as equipes da Microsoft](enhance-office-365-groups.md).</span><span class="sxs-lookup"><span data-stu-id="6419c-122">Now allow time for the membership changes to take effect, and create a new team  as described in [Enhance Existing Office 365 groups with Microsoft Teams](enhance-office-365-groups.md).</span></span>

## <a name="apply-dynamic-membership-to-an-existing-team"></a><span data-ttu-id="6419c-123">Aplicar a participação dinâmica para uma equipe existente</span><span class="sxs-lookup"><span data-stu-id="6419c-123">Apply dynamic membership to an existing team</span></span>

<span data-ttu-id="6419c-124">Você também pode levar uma equipe existente e alterá-lo para ter uma associação dinâmica, conforme descrito em [alterar a associação de grupo estático para dinâmico no Windows Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).</span><span class="sxs-lookup"><span data-stu-id="6419c-124">You can also take an existing team and change it to have a dynamic membership, as described in [Change static group membership to dynamic in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).</span></span>

## <a name="changes-in-client-behavior"></a><span data-ttu-id="6419c-125">Alterações no comportamento dos clientes</span><span class="sxs-lookup"><span data-stu-id="6419c-125">Changes in client behavior</span></span>

<span data-ttu-id="6419c-126">Depois que a associação dinâmica estiver habilitada para uma equipe, os clientes de equipes não são mais permitirá que o gerenciamento de membros da equipe.</span><span class="sxs-lookup"><span data-stu-id="6419c-126">Once dynamic membership is enabled for a team, Teams clients will no longer allow member management for the team.</span></span> <span data-ttu-id="6419c-127">Opções para adicionar membros, edite as funções de membro, enviar e aprovar solicitações de ingresso e deixar a equipe todos estão ocultas.</span><span class="sxs-lookup"><span data-stu-id="6419c-127">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>
