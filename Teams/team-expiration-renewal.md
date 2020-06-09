---
title: Expiração e renovação da equipe no Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Saiba mais sobre expiração e renovação da equipe e como usar a política de expiração do grupo Microsoft 365 ou Microsoft 365 para limpar automaticamente as equipes não usadas no Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 34984c545e3e6593c9d5168a81d3465ce391dab2
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638550"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a><span data-ttu-id="48443-103">Expiração e renovação da equipe no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="48443-103">Team expiration and renewal in Microsoft Teams</span></span>

<span data-ttu-id="48443-104">Organizações com um grande número de equipes muitas vezes têm equipes que nunca são usadas de fato.</span><span class="sxs-lookup"><span data-stu-id="48443-104">Organizations with a large number of teams often have teams that are never actually used.</span></span> <span data-ttu-id="48443-105">Isso pode acontecer devido a vários motivos, incluindo a experimentação do produto, a colaboração da equipe de curto prazo ou os proprietários da equipe que deixam a organização.</span><span class="sxs-lookup"><span data-stu-id="48443-105">This can happen because of several reasons including product experimentation, short-term team collaboration, or team owners leaving the organization.</span></span> <span data-ttu-id="48443-106">Ao longo do tempo, tais equipes podem acumular e criar uma sobrecarga nos recursos do locatário.</span><span class="sxs-lookup"><span data-stu-id="48443-106">Over time, such teams can accumulate and create a burden on tenant resources.</span></span>  

<span data-ttu-id="48443-107">Para restringir o número de equipes não usadas, como administrador, você pode usar a [política de expiração do grupo microsoft 365 ou microsoft 365](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups-expiration-policy) para limpar automaticamente as equipes não usadas.</span><span class="sxs-lookup"><span data-stu-id="48443-107">To curb the number of unused teams, as an admin, you can use [Microsoft 365 or Microsoft 365 group expiration policy](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups-expiration-policy) to automatically clean up unused teams.</span></span> <span data-ttu-id="48443-108">Como as equipes são apoiadas por grupos, as políticas de expiração de grupo também se aplicam automaticamente às equipes.</span><span class="sxs-lookup"><span data-stu-id="48443-108">Because teams are backed by groups, group expiration policies automatically apply to teams as well.</span></span>

<span data-ttu-id="48443-109">Quando você aplica uma política de expiração a uma equipe, um proprietário da equipe recebe uma notificação para a renovação da equipe 30 dias, 15 dias e 1 dia antes da data de expiração da equipe.</span><span class="sxs-lookup"><span data-stu-id="48443-109">When you apply an expiration policy to a team, a team owner receives a notification for team renewal 30 days, 15 days and 1 day before the team's expiration date.</span></span> <span data-ttu-id="48443-110">Quando o proprietário da equipe receber a notificação, poderá clicar em **renovar agora** em configurações da equipe para renovar a equipe.</span><span class="sxs-lookup"><span data-stu-id="48443-110">When the team owner receives the notification, they can click **Renew now** in team settings to renew the team.</span></span>

<span data-ttu-id="48443-111">![Captura de tela do botão Renovar agora para renovar uma equipe nas configurações da equipe](media/team-expiration.png "Captura de tela do botão Renovar agora para renovar uma equipe nas configurações da equipe")</span><span class="sxs-lookup"><span data-stu-id="48443-111">![Screenshot of the Renew Now button to renew a team in team settings](media/team-expiration.png "Screenshot of the Renew Now button to renew a team in team settings")</span></span>

<span data-ttu-id="48443-112">Se o proprietário da equipe não renovar a equipe, a equipe será colocada em um estado "excluído sem disco", o que significa que ela pode ser restaurada dentro dos próximos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="48443-112">If the team owner doesn't renew the team, the team is put in a "soft-deleted" state, which means it can be restored within the next 30 days.</span></span>

## <a name="team-auto-renewal"></a><span data-ttu-id="48443-113">Renovação automática da equipe</span><span class="sxs-lookup"><span data-stu-id="48443-113">Team auto-renewal</span></span>

<span data-ttu-id="48443-114">Pode haver ocasiões em que um proprietário de equipe não consiga renovar a equipe, talvez porque ela se esqueceu de ser renovada ou ficou ausente quando a renovação foi concluída.</span><span class="sxs-lookup"><span data-stu-id="48443-114">There can be times when a team owner is unable to renew the team perhaps because they forgot to renew or were away when renewal was due.</span></span> <span data-ttu-id="48443-115">Nesses cenários, uma equipe em uso ativo pode ser excluída devido às políticas de expiração que se aplicam à equipe.</span><span class="sxs-lookup"><span data-stu-id="48443-115">In these scenarios, a team in active use can get deleted because of expiration policies that apply to the team.</span></span>  

<span data-ttu-id="48443-116">Para evitar exclusão acidental, a renovação automática é habilitada automaticamente para uma equipe na política de expiração do grupo.</span><span class="sxs-lookup"><span data-stu-id="48443-116">To prevent accidental deletion, auto-renewal is automatically enabled for a team in the group expiration policy.</span></span> <span data-ttu-id="48443-117">Quando a política de expiração de grupo é configurada, qualquer equipe que tenha pelo menos um canal acessado de qualquer membro da equipe antes da data de expiração seja automaticamente renovada sem nenhuma intervenção manual do proprietário da equipe.</span><span class="sxs-lookup"><span data-stu-id="48443-117">When the group expiration policy is set up, any team that has at least one channel visit from any team member before its expiration date is automatically renewed without any manual intervention from the team owner.</span></span>

## <a name="known-issues"></a><span data-ttu-id="48443-118">Problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="48443-118">Known issues</span></span>

<span data-ttu-id="48443-119">**A data de expiração da equipe e do grupo subjacente não correspondem**</span><span class="sxs-lookup"><span data-stu-id="48443-119">**Expiration date of team and underlying group don't match**</span></span>

<span data-ttu-id="48443-120">Antes que uma equipe seja renovada, o grupo que faz o backup da equipe é renovado primeiro.</span><span class="sxs-lookup"><span data-stu-id="48443-120">Before a team is renewed, the group that backs the team is renewed first.</span></span> <span data-ttu-id="48443-121">Como parte da renovação, uma nova data de vencimento é definida no grupo para uma data futura.</span><span class="sxs-lookup"><span data-stu-id="48443-121">As part of renewal, a new expiry date is set on the group for a future date.</span></span> <span data-ttu-id="48443-122">Esta nova data pode não ser imediatamente visível no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="48443-122">This new date may not be immediately visible in Teams.</span></span> <span data-ttu-id="48443-123">Pode levar até 24 horas para sincronizar. Se você vir uma discrepância entre a data de vencimento de uma equipe e seu grupo subjacente, Aguarde 24 horas antes de buscar mais suporte.</span><span class="sxs-lookup"><span data-stu-id="48443-123">It can take up to 24 hours to sync. If you see a discrepancy between the expiry date for a team and its underlying group, wait 24 hours before seeking further support.</span></span>
