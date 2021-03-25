---
title: Planejar o Grupos do Microsoft 365 quando criar equipes
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 08/29/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Saiba mais sobre como planejar grupos do Microsoft 365 no Teams, incluindo as diferenças entre grupos & conversas do Teams e como o Teams respeita a política de nomenis de grupos.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: 1acde038bc2df64d7cf35828bf0b08273bf1f095
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51108347"
---
<a name="plan-for-microsoft-365-groups-when-creating-teams-in-microsoft-teams"></a><span data-ttu-id="177f1-103">Planejar grupos do Microsoft 365 ao criar equipes no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="177f1-103">Plan for Microsoft 365 Groups when creating teams in Microsoft Teams</span></span>
==========================================================

<span data-ttu-id="177f1-104">Ao considerar o uso de Grupos do Microsoft 365 ou ao criar equipes, considere para o que a equipe será usada, para quem deve ter acesso e qual resultado a equipe espera alcançar.</span><span class="sxs-lookup"><span data-stu-id="177f1-104">When considering the use of Microsoft 365 Groups or when creating teams, consider what the team will be used for, who should have access, and what outcome the team will expect to achieve.</span></span> <span data-ttu-id="177f1-105">Preste especial atenção ao número de canais que você cria, pois as pessoas podem ficar rapidamente saturadas por conteúdo espalhado em demasia (em muitos canais).</span><span class="sxs-lookup"><span data-stu-id="177f1-105">Pay special attention to the number of channels you create as people can quickly become overrun by content spread too thin (across too many channels).</span></span>

<span data-ttu-id="177f1-106">Há dois cenários que garantem alguma discussão sobre o planejamento de Grupos do Microsoft 365 e seu impacto no (ou pelo) Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="177f1-106">There are two scenarios that warrant some discussion around planning of Microsoft 365 Groups and their impact on (or by) Microsoft Teams:</span></span>

-   <span data-ttu-id="177f1-107">Primeiro, como os clientes podem ter [investimentos existentes](./limits-specifications-teams.md)em Grupos, atualmente suportamos grupos públicos e privados, para o número de membros atualmente suportados, consulte Limites e especificações do Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="177f1-107">First, since customers could have existing investments in Groups, we currently support both Public and Private groups, for the number of members currently supported, please see [Limits and specifications for Microsoft Teams](./limits-specifications-teams.md).</span></span> <span data-ttu-id="177f1-108">Como mencionado anteriormente, você deseja gerenciar a associação de pessoas a uma equipe usando o cliente do Teams em vez do centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="177f1-108">As mentioned previously, you want to manage the membership of people to a team using the Teams client rather than the Microsoft 365 admin center.</span></span> <span data-ttu-id="177f1-109">Devido a esse cenário, se as pessoas são usadas para conversas encadeadas nos Grupos do Microsoft 365, vale a pena destacar que uma conversa de Grupos é essencialmente email e não o mesmo que uma mensagem de chat em um canal do Teams.</span><span class="sxs-lookup"><span data-stu-id="177f1-109">Given this scenario, if people are used to threaded conversations in Microsoft 365 Groups, it is worthwhile noting that a Groups conversation is essentially email and not the same as a chat message in a Teams channel.</span></span> <span data-ttu-id="177f1-110">Informe essa diferença ao seu pessoal ou sugira que adotem um formato de mensagens de bate-papo mais flexível no Teams, em vez de enviar e-mails aos grupos usando o Outlook ou o OWA.</span><span class="sxs-lookup"><span data-stu-id="177f1-110">Educate your people about this difference and suggest they adopt the more flexible chat message format in Teams versus emailing the Group using Outlook or OWA.</span></span>

-   <span data-ttu-id="177f1-111">Em segundo lugar, para clientes que não têm Grupos existentes definidos no Microsoft 365, você pode criar eles usando o centro de administração do Microsoft 365, a Web do Teams ou clientes de área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="177f1-111">Second, for customers who don't have existing Groups defined in Microsoft 365, you can either create them using the Microsoft 365 admin center, the Teams web, or desktop clients.</span></span> <span data-ttu-id="177f1-112">Conforme mencionado anteriormente, gerencie toda a associação futura ao grupo do Microsoft 365 usando o cliente do Teams.</span><span class="sxs-lookup"><span data-stu-id="177f1-112">As mentioned previously, manage all future membership to the Microsoft 365 group using the Teams client.</span></span> <span data-ttu-id="177f1-113">Como a associação a uma equipe também está definindo a associação aos Grupos do Microsoft 365, você deve preparar as pessoas para essa alteração.</span><span class="sxs-lookup"><span data-stu-id="177f1-113">Since membership to a team is also defining membership to Microsoft 365 Groups, you should prepare people for this change.</span></span>

## <a name="teams-respects-microsoft-365-groups-naming-policy-in-private-preview"></a><span data-ttu-id="177f1-114">O Teams respeita a política de nomenis dos Grupos do Microsoft 365 (em visualização privada)</span><span class="sxs-lookup"><span data-stu-id="177f1-114">Teams respects Microsoft 365 Groups naming policy (in private preview)</span></span>

<span data-ttu-id="177f1-115">Qualquer política de nomenis do Microsoft 365 Groups que tenha sido definida pelo administrador será aplicada no Teams quando os usuários criarem ou editarem nomes de equipe.</span><span class="sxs-lookup"><span data-stu-id="177f1-115">Any Microsoft 365 Groups naming policy that has been set by your admin will be applied in Teams when users create or edit team names.</span></span> <span data-ttu-id="177f1-116">Isso inclui itens como prefixos ou sufixos obrigatórios e a exclusão de palavras banidas.</span><span class="sxs-lookup"><span data-stu-id="177f1-116">This includes things like mandatory prefixes or suffixes and excluding banned words.</span></span>

> [!NOTE]
> <span data-ttu-id="177f1-117">Esse recurso está em visualização privada, o que significa que, se você não faz parte dessa visualização, o Teams ainda não adere a essa política de nomenis do Microsoft 365 Groups.</span><span class="sxs-lookup"><span data-stu-id="177f1-117">This feature is in private preview, which means that if you're not part of this preview, Teams doesn't yet adhere to this Microsoft 365 Groups naming policy.</span></span>

<span data-ttu-id="177f1-118">Para saber mais, leia a política de [nomenis dos Grupos do Microsoft 365 no Teams](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span><span class="sxs-lookup"><span data-stu-id="177f1-118">To learn more, read [Microsoft 365 Groups naming policy in Teams](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>

<span data-ttu-id="177f1-119">Os artigos a seguir são um bom local para encontrar conteúdo de preparação e adoção para seus Grupos do Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="177f1-119">The following articles are a good place to find readiness and adoption content for your Microsoft 365 Groups:</span></span>

-   [<span data-ttu-id="177f1-120">Obter mais com o grupos no Outlook</span><span class="sxs-lookup"><span data-stu-id="177f1-120">Get more with groups in Outlook</span></span>](https://support.office.com/article/Get-more-with-Office-365-Groups-in-Outlook-93132800-5b11-49de-8cc2-605b6075b2b9)

-   [<span data-ttu-id="177f1-121">Adicionar ou remover membros dos Grupos do Microsoft 365 usando o Centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="177f1-121">Add or remove members from Microsoft 365 Groups using the Microsoft 365 admin center</span></span>](https://support.office.com/article/Manage-Group-membership-in-the-Office-365-admin-center-e186d224-a324-4afa-8300-0e4fc0c3000a)

-   [<span data-ttu-id="177f1-122">Restaurar um grupo excluído</span><span class="sxs-lookup"><span data-stu-id="177f1-122">Restore a deleted group</span></span>](/microsoft-365/admin/create-groups/restore-deleted-group)