---
title: Colocar um usuário ou uma equipe do Microsoft Teams em retenção legal
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: Saiba como colocar um usuário ou uma equipe do Microsoft Teams em retenção legal usando o Centro de Segurança e Conformidade, e saiba o que necessita de uma retenção legal com base nas exigências de dados.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 25bd8e235be79ed805a854cbda2b4947f1c1269b
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2019
ms.locfileid: "37968032"
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a><span data-ttu-id="e3825-103">Colocar um usuário ou uma equipe do Microsoft Teams em retenção legal</span><span class="sxs-lookup"><span data-stu-id="e3825-103">Place a Microsoft Teams user or team on legal hold</span></span>
==================================================

<span data-ttu-id="e3825-104">Para colocar um usuário ou uma equipe em retenção legal, navegue até o [Centro de Segurança e Conformidade](https://go.microsoft.com/fwlink/?linkid=854628).</span><span class="sxs-lookup"><span data-stu-id="e3825-104">To put a user or a team on Legal Hold, navigate to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=854628).</span></span> <span data-ttu-id="e3825-105">Quando você cria um caso novo, você se depara com a opção de colocar caixas de correio ou sites em retenção.</span><span class="sxs-lookup"><span data-stu-id="e3825-105">When you create a new case, you are presented with the option to place mailboxes or sites on hold.</span></span>

> [!NOTE]
> <span data-ttu-id="e3825-106">A colocação de um usuário em retenção não coloca automaticamente um grupo em retenção ou vice-versa.</span><span class="sxs-lookup"><span data-stu-id="e3825-106">Placing a user on hold does not automatically place a group on hold or vice-versa.</span></span>

> [!NOTE]
> <span data-ttu-id="e3825-107">Ainda não damos suporte à configuração de controle legal de mensagens de canal privado.</span><span class="sxs-lookup"><span data-stu-id="e3825-107">We don’t yet support configuration for legal hold of private channel messages.</span></span> <span data-ttu-id="e3825-108">Há suporte para o controle legal de arquivos compartilhados em canais privados.</span><span class="sxs-lookup"><span data-stu-id="e3825-108">Legal hold of files shared in private channels is supported.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3825-109">Quando um usuário ou grupo é colocado em espera, todas as cópias da mensagem serão mantidas.</span><span class="sxs-lookup"><span data-stu-id="e3825-109">When a user or group is placed on hold, all message copies will be retained.</span></span> <span data-ttu-id="e3825-110">Exemplo: Clay publicou uma mensagem em um canal e depois modificou a mensagem.</span><span class="sxs-lookup"><span data-stu-id="e3825-110">Example: Clay posted a message in a channel and then modified the message.</span></span> <span data-ttu-id="e3825-111">Em um cenário de retenção, ambas as cópias da mensagem são mantidas.</span><span class="sxs-lookup"><span data-stu-id="e3825-111">In a hold scenario, both copies of the message are retained.</span></span> <span data-ttu-id="e3825-112">Sem a retenção legal, apenas a última mensagem seria mantida.</span><span class="sxs-lookup"><span data-stu-id="e3825-112">Without Legal Hold, only the latest message is retained.</span></span>

<span data-ttu-id="e3825-113">Na imagem abaixo, há uma investigação que envolve Clay.</span><span class="sxs-lookup"><span data-stu-id="e3825-113">In the figure below, there is an investigation involving Clay.</span></span> <span data-ttu-id="e3825-114">Clay é membro da equipe de Corretores-Revendedores.</span><span class="sxs-lookup"><span data-stu-id="e3825-114">Clay is a member of the Brokers-Dealers team.</span></span>

<span data-ttu-id="e3825-115">Se precisássemos de retenção legal em todos os lugares que Clay possa ter discutido os planos de corretagem, certifique-se de que o site do SharePoint da equipe seja adicionado à lista do site de retenção legal, bem como ao site OneDrive for Business de Clay.</span><span class="sxs-lookup"><span data-stu-id="e3825-115">If we needed to Legal Hold all the places Clay could have discussed Brokering plans, ensure that the team’s SharePoint site is added to the Legal Hold site list, as well as Clay’s OneDrive for Business site.</span></span>

![Captura de tela da caixa de diálogo Criar uma nova retenção.](media/Place_a_Microsoft_Teams_user_or_team_on_legal_hold_image3.png)

<span data-ttu-id="e3825-117">Para recapitular, use a tabela abaixo para entender o que precisa ser colocado no retenção legal com base nas exigências de dados:</span><span class="sxs-lookup"><span data-stu-id="e3825-117">To recap, use the table below to understand what needs to be placed on Legal Hold based on data requirements:</span></span>

|<span data-ttu-id="e3825-118">Cenário</span><span class="sxs-lookup"><span data-stu-id="e3825-118">Scenario</span></span>  |<span data-ttu-id="e3825-119">O que colocar em retenção</span><span class="sxs-lookup"><span data-stu-id="e3825-119">What to place on hold</span></span>  |
|---------|---------|
|<span data-ttu-id="e3825-120">**Bate-papos privados do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="e3825-120">**Microsoft Teams Private Chats**</span></span>     |<span data-ttu-id="e3825-121">Caixa de correio do usuário</span><span class="sxs-lookup"><span data-stu-id="e3825-121">User mailbox</span></span>         |
|<span data-ttu-id="e3825-122">**Bate-papos nos canais do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="e3825-122">**Microsoft Teams Channel Chats**</span></span>    |<span data-ttu-id="e3825-123">Caixa de correio do grupo usada para a equipe</span><span class="sxs-lookup"><span data-stu-id="e3825-123">Group mailbox used for the team</span></span>         |
|<span data-ttu-id="e3825-124">**Conteúdo do Microsoft Teams (ex.: wiki, arquivos)**</span><span class="sxs-lookup"><span data-stu-id="e3825-124">**Microsoft Teams Content (e.g. Wiki, Files)**</span></span>     |<span data-ttu-id="e3825-125">Site SharePoint usado pela equipe</span><span class="sxs-lookup"><span data-stu-id="e3825-125">SharePoint site used by the team</span></span>         |
|<span data-ttu-id="e3825-126">**Conteúdo privado**</span><span class="sxs-lookup"><span data-stu-id="e3825-126">**Private Content**</span></span>     |<span data-ttu-id="e3825-127">Site OneDrive for Business do usuário</span><span class="sxs-lookup"><span data-stu-id="e3825-127">OneDrive for Business site of the user</span></span>         |
