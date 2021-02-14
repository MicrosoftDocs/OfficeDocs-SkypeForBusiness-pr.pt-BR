---
title: Expiração e renovação da equipe no Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Saiba mais sobre a expiração e a renovação da equipe e como usar a política de expiração de grupo do Microsoft 365 para limpar automaticamente as equipes não usadas no Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: b111ddd6b874fef22a7d221f6eb932c4c14c7b70
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809401"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a><span data-ttu-id="b59b2-103">Expiração e renovação da equipe no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b59b2-103">Team expiration and renewal in Microsoft Teams</span></span>

<span data-ttu-id="b59b2-104">Organizações com um grande número de equipes geralmente têm equipes que nunca são realmente usadas.</span><span class="sxs-lookup"><span data-stu-id="b59b2-104">Organizations with a large number of teams often have teams that are never actually used.</span></span> <span data-ttu-id="b59b2-105">Isso pode acontecer por vários motivos, incluindo experimentos de produtos, colaboração em equipe a curto prazo ou proprietários de equipe saindo da organização.</span><span class="sxs-lookup"><span data-stu-id="b59b2-105">This can happen because of several reasons including product experimentation, short-term team collaboration, or team owners leaving the organization.</span></span> <span data-ttu-id="b59b2-106">Ao longo do tempo, essas equipes podem se acumular e criar uma sobrecarga nos recursos do locatário.</span><span class="sxs-lookup"><span data-stu-id="b59b2-106">Over time, such teams can accumulate and create a burden on tenant resources.</span></span>  

<span data-ttu-id="b59b2-107">Para conter o número de equipes não usadas, como administrador, você pode usar a política de expiração de grupo do [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) para limpar automaticamente as equipes não usadas.</span><span class="sxs-lookup"><span data-stu-id="b59b2-107">To curb the number of unused teams, as an admin, you can use [Microsoft 365 group expiration policy](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) to automatically clean up unused teams.</span></span> <span data-ttu-id="b59b2-108">Como as equipes são respaldadas por grupos, as políticas de expiração de grupo também se aplicam automaticamente às equipes.</span><span class="sxs-lookup"><span data-stu-id="b59b2-108">Because teams are backed by groups, group expiration policies automatically apply to teams as well.</span></span>

<span data-ttu-id="b59b2-109">Quando você aplica uma política de expiração a uma equipe, um proprietário da equipe recebe uma notificação de renovação da equipe 30 dias, 15 dias e 1 dia antes da data de vencimento da equipe.</span><span class="sxs-lookup"><span data-stu-id="b59b2-109">When you apply an expiration policy to a team, a team owner receives a notification for team renewal 30 days, 15 days and 1 day before the team's expiration date.</span></span> <span data-ttu-id="b59b2-110">Quando o proprietário da equipe receber a notificação, ele poderá clicar em Renovar **agora** nas configurações da equipe para renovar a equipe.</span><span class="sxs-lookup"><span data-stu-id="b59b2-110">When the team owner receives the notification, they can click **Renew now** in team settings to renew the team.</span></span>

<span data-ttu-id="b59b2-111">![Captura de tela do botão Renovar Agora para renovar uma equipe nas configurações da equipe](media/team-expiration.png "Captura de tela do botão Renovar Agora para renovar uma equipe nas configurações da equipe")</span><span class="sxs-lookup"><span data-stu-id="b59b2-111">![Screenshot of the Renew Now button to renew a team in team settings](media/team-expiration.png "Screenshot of the Renew Now button to renew a team in team settings")</span></span>

<span data-ttu-id="b59b2-112">Se o proprietário da equipe não renovar a equipe e não houver mais atividades na equipe até o final da política de expiração, a equipe será colocada em um estado "excluído suavemente", o que significa que pode ser restaurada dentro dos próximos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="b59b2-112">If the team owner doesn't renew the team and there is no further activity on the team until the end of the expiration policy, the team is put in a "soft-deleted" state, which means it can be restored within the next 30 days.</span></span>

## <a name="team-auto-renewal"></a><span data-ttu-id="b59b2-113">Renovação automática da equipe</span><span class="sxs-lookup"><span data-stu-id="b59b2-113">Team auto-renewal</span></span>

<span data-ttu-id="b59b2-114">Pode haver ocasiões em que o proprietário da equipe não consegue renovar a equipe, talvez porque ele se esqueceu de renovar ou estava fora quando a renovação estava prevista.</span><span class="sxs-lookup"><span data-stu-id="b59b2-114">There can be times when a team owner is unable to renew the team perhaps because they forgot to renew or were away when renewal was due.</span></span> <span data-ttu-id="b59b2-115">Nesses cenários, uma equipe em uso ativo pode ser excluída devido a políticas de expiração que se aplicam à equipe.</span><span class="sxs-lookup"><span data-stu-id="b59b2-115">In these scenarios, a team in active use can get deleted because of expiration policies that apply to the team.</span></span>  

<span data-ttu-id="b59b2-116">Para impedir a exclusão acidental, a renovação automática é habilitada automaticamente para uma equipe na política de expiração do grupo.</span><span class="sxs-lookup"><span data-stu-id="b59b2-116">To prevent accidental deletion, auto-renewal is automatically enabled for a team in the group expiration policy.</span></span> <span data-ttu-id="b59b2-117">Quando a política de expiração do grupo é configurada, qualquer equipe que tenha pelo menos uma visita de canal de qualquer membro da equipe antes de sua data de expiração é automaticamente renovada sem qualquer intervenção manual do proprietário da equipe.</span><span class="sxs-lookup"><span data-stu-id="b59b2-117">When the group expiration policy is set up, any team that has at least one channel visit from any team member before its expiration date is automatically renewed without any manual intervention from the team owner.</span></span>

## <a name="known-issues"></a><span data-ttu-id="b59b2-118">Problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="b59b2-118">Known issues</span></span>

<span data-ttu-id="b59b2-119">**A data de expiração da equipe e do grupo subjacente não corresponderão**</span><span class="sxs-lookup"><span data-stu-id="b59b2-119">**Expiration date of team and underlying group don't match**</span></span>

<span data-ttu-id="b59b2-120">Antes que uma equipe seja renovada, o grupo que faz o apoio da equipe será renovado primeiro.</span><span class="sxs-lookup"><span data-stu-id="b59b2-120">Before a team is renewed, the group that backs the team is renewed first.</span></span> <span data-ttu-id="b59b2-121">Como parte da renovação, uma nova data de vencimento é definida no grupo para uma data futura.</span><span class="sxs-lookup"><span data-stu-id="b59b2-121">As part of renewal, a new expiry date is set on the group for a future date.</span></span> <span data-ttu-id="b59b2-122">Essa nova data pode não estar imediatamente visível no Teams.</span><span class="sxs-lookup"><span data-stu-id="b59b2-122">This new date may not be immediately visible in Teams.</span></span> <span data-ttu-id="b59b2-123">A sincronização pode levar até 24 horas. Se você vir uma discrepância entre a data de vencimento de uma equipe e seu grupo subjacente, aguarde 24 horas antes de buscar mais suporte.</span><span class="sxs-lookup"><span data-stu-id="b59b2-123">It can take up to 24 hours to sync. If you see a discrepancy between the expiry date for a team and its underlying group, wait 24 hours before seeking further support.</span></span>
