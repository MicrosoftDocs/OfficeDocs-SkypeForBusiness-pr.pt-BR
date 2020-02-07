---
title: Planejar-se para Grupos do Office 365 ao criar equipes no Microsoft Teams
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/29/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Conheça as decisões que você deve fazer ao planejar os grupos do Office 365, como escolher grupos públicos e privados, usar o cliente do teams ou o console da Web do Office 365 Administration e como ensinar suas equipes sobre como usar conversas.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 092a30be3fb8cffce8abfc9b885e3de3caa8bed4
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41833831"
---
<a name="plan-for-office-365-groups-when-creating-teams-in-microsoft-teams"></a><span data-ttu-id="f98e1-103">Planejar-se para Grupos do Office 365 ao criar equipes no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f98e1-103">Plan for Office 365 Groups when creating teams in Microsoft Teams</span></span>
==========================================================

<span data-ttu-id="f98e1-104">Ao considerar o uso dos Grupos do Office 365 ou ao criar equipes, considere para que a equipe será usada, quem deverá ter acesso e os resultados que a equipe espera alcançar.</span><span class="sxs-lookup"><span data-stu-id="f98e1-104">When considering the use of Office 365 Groups or when creating teams, consider what the team will be used for, who should have access, and what outcome the team will expect to achieve.</span></span> <span data-ttu-id="f98e1-105">Preste especial atenção ao número de canais que você cria, pois as pessoas podem ficar rapidamente saturadas por conteúdo espalhado em demasia (em muitos canais).</span><span class="sxs-lookup"><span data-stu-id="f98e1-105">Pay special attention to the number of channels you create as people can quickly become overrun by content spread too thin (across too many channels).</span></span>

<span data-ttu-id="f98e1-106">Existem dois cenários que justificam uma discussão em torno do planejamento dos Grupos do Office 365 e seu impacto em (ou pelo) Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="f98e1-106">There are two scenarios that warrant some discussion around planning of Office 365 Groups and their impact on (or by) Microsoft Teams:</span></span>

-   <span data-ttu-id="f98e1-107">Primeiro, como os clientes podem ter investimentos existentes em grupos, atualmente damos suporte a grupos públicos e privados de menos de 5000 membros.</span><span class="sxs-lookup"><span data-stu-id="f98e1-107">First, since customers could have existing investments in Groups, we currently support both Public and Private groups of less than 5000 members.</span></span> <span data-ttu-id="f98e1-108">Conforme mencionado anteriormente, você deseja gerenciar a associação de pessoas a uma equipe usando o cliente do Teams, em vez do console da Web de administração do Office 365.</span><span class="sxs-lookup"><span data-stu-id="f98e1-108">As mentioned previously, you want to manage the membership of people to a team using the Teams client rather than the Office 365 admin web console.</span></span> <span data-ttu-id="f98e1-109">Considerando esse cenário, se as pessoas forem usadas para conversas encadeadas nos grupos do Office 365, vale a pena observar que uma conversa de grupos é essencialmente email e não é a mesma que uma mensagem de chat em um canal do teams.</span><span class="sxs-lookup"><span data-stu-id="f98e1-109">Given this scenario, if people are used to threaded conversations in Office 365 Groups, it is worthwhile noting that a Groups conversation is essentially email and not the same as a chat message in a Teams channel.</span></span> <span data-ttu-id="f98e1-110">Informe essa diferença ao seu pessoal ou sugira que adotem um formato de mensagens de bate-papo mais flexível no Teams, em vez de enviar e-mails aos grupos usando o Outlook ou o OWA.</span><span class="sxs-lookup"><span data-stu-id="f98e1-110">Educate your people about this difference and suggest they adopt the more flexible chat message format in Teams versus emailing the Group using Outlook or OWA.</span></span>

-   <span data-ttu-id="f98e1-111">Em segundo lugar, para os clientes que não possuem Grupos definidos no Office 365, você pode criá-los usando o portal de administração do Office 365, o Teams web ou os clientes desktop.</span><span class="sxs-lookup"><span data-stu-id="f98e1-111">Second, for customers who don’t have existing Groups defined in Office 365, you can either create them using the Office 365 admin portal, the Teams web, or desktop clients.</span></span> <span data-ttu-id="f98e1-112">Conforme mencionado anteriormente, gerencie todas as futuras assinaturas do Grupo do Office 365 usando o cliente Teams.</span><span class="sxs-lookup"><span data-stu-id="f98e1-112">As mentioned previously, manage all future membership to the Office 365 Group using the Teams client.</span></span> <span data-ttu-id="f98e1-113">Como a associação a uma equipe também está definindo associação a grupos do Office 365, você deve preparar as pessoas para essa alteração.</span><span class="sxs-lookup"><span data-stu-id="f98e1-113">Since membership to a team is also defining membership to Office 365 Groups, you should prepare people for this change.</span></span>
 


## <a name="teams-respects-office-365-groups-naming-policy-in-private-preview"></a><span data-ttu-id="f98e1-114">O Microsoft Teams respeita a política de nomenclatura de Grupos do Office 365 (no modo preview privado)</span><span class="sxs-lookup"><span data-stu-id="f98e1-114">Teams respects Office 365 Groups naming policy (in private preview)</span></span>

<span data-ttu-id="f98e1-115">Todas as políticas de nomenclatura de Grupos do Office 365 que tenham sido definidas pelo seu administrador serão aplicadas no Teams quando os usuários criarem ou editarem o nome de uma equipe.</span><span class="sxs-lookup"><span data-stu-id="f98e1-115">Any Office 365 Groups naming policy that has been set by your admin will be applied in Teams when users create or edit team names.</span></span> <span data-ttu-id="f98e1-116">Isso inclui itens como prefixos ou sufixos obrigatórios e a exclusão de palavras banidas.</span><span class="sxs-lookup"><span data-stu-id="f98e1-116">This includes things like mandatory prefixes or suffixes and excluding banned words.</span></span>

> [!NOTE]
> <span data-ttu-id="f98e1-117">Esse recurso está no modo preview privado; isso quer dizer que, se você não participa dessa preview, o Microsoft Teams ainda não aderiu a essa política de nomenclatura de Grupos do Office 365.</span><span class="sxs-lookup"><span data-stu-id="f98e1-117">This feature is in private preview, which means that if you're not part of this preview, Teams doesn't yet adhere to this Office 365 Groups naming policy.</span></span>

<span data-ttu-id="f98e1-118">Para saber mais, leia [Política de nomenclatura de Grupos do Office 365 no Teams](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span><span class="sxs-lookup"><span data-stu-id="f98e1-118">To learn more, read [Office 365 Groups naming policy in Teams](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>

<span data-ttu-id="f98e1-119">Os artigos a seguir são um bom lugar para encontrar conteúdo de preparação e adoção para seus grupos do Office 365:</span><span class="sxs-lookup"><span data-stu-id="f98e1-119">The following articles are a good place to find readiness and adoption content for your Office 365 Groups:</span></span>

-   [<span data-ttu-id="f98e1-120">Obter mais com o grupos no Outlook</span><span class="sxs-lookup"><span data-stu-id="f98e1-120">Get more with groups in Outlook</span></span>](https://support.office.com/article/Get-more-with-Office-365-Groups-in-Outlook-93132800-5b11-49de-8cc2-605b6075b2b9)

-   [<span data-ttu-id="f98e1-121">Adicionar ou remover membros de grupos do Office 365 usando o centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f98e1-121">Add or remove members from Office 365 Groups using the Microsoft 365 admin center</span></span>](https://support.office.com/article/Manage-Group-membership-in-the-Office-365-admin-center-e186d224-a324-4afa-8300-0e4fc0c3000a)

-   [<span data-ttu-id="f98e1-122">Restaurar um grupo do Office 365 excluído</span><span class="sxs-lookup"><span data-stu-id="f98e1-122">Restore a deleted Office 365 Group</span></span>](https://support.office.com/article/Restore-a-deleted-Office-365-Group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54)
