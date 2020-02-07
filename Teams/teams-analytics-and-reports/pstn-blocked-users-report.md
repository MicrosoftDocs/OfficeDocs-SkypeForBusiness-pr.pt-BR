---
title: Relatório de usuários bloqueados PSTN do Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-voice
description: Saiba como usar o relatório de usuários bloqueados PSTN no centro de administração do Microsoft Teams para obter uma visão geral dos usuários do teams em sua organização que estão bloqueados para fazer chamadas PSTN.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1ef4dfbab2b32b088c8e2f8b38b55c15a66eb32
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827339"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a><span data-ttu-id="60452-103">Relatório de usuários bloqueados PSTN do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="60452-103">Microsoft Teams PSTN blocked users report</span></span>

<span data-ttu-id="60452-104">O relatório de usuários bloqueados PSTN no centro de administração do Microsoft Teams mostra os usuários em sua organização que estão bloqueados da realização de chamadas PSTN no Teams.</span><span class="sxs-lookup"><span data-stu-id="60452-104">The PSTN blocked users report in the Microsoft Teams admin center shows you the users in your organization who are blocked from making PSTN calls in Teams.</span></span> <span data-ttu-id="60452-105">Você pode ver mais informações sobre cada usuário bloqueado, incluindo o número de telefone atribuído a ele e o motivo pelo qual eles foram bloqueados para fazerem chamadas.</span><span class="sxs-lookup"><span data-stu-id="60452-105">You can view more information about each blocked user, including their assigned phone number and the reason they were blocked from making calls.</span></span>

## <a name="view-the-report"></a><span data-ttu-id="60452-106">Exibir o relatório</span><span class="sxs-lookup"><span data-stu-id="60452-106">View the report</span></span>

<span data-ttu-id="60452-107">Na navegação à esquerda do centro de administração do Microsoft Teams, clique em **análises &** > relatórios de**uso**dos relatórios.</span><span class="sxs-lookup"><span data-stu-id="60452-107">In the left navigation of the Microsoft Teams admin center, click **Analytics & reports** > **Usage reports**.</span></span> <span data-ttu-id="60452-108">Na guia **exibir relatórios** , em **relatório**, selecione **usuários bloqueados PSTN**e clique em **executar relatório**.</span><span class="sxs-lookup"><span data-stu-id="60452-108">On the **View reports** tab, under **Report**, select **PSTN blocked users**, and then click **Run report**.</span></span>

<span data-ttu-id="60452-109">![Captura de tela do relatório de relatório de usuários bloqueados PSTN no centro de administração](../media/teams-reports-pstn-blocked-users-with-callouts.png "Captura de tela do relatório de usuários bloqueados PSTN no centro de administração do Microsoft Teams com textos explicativos numerados")</span><span class="sxs-lookup"><span data-stu-id="60452-109">![Screenshot of the PSTN blocked users report report in the admin center](../media/teams-reports-pstn-blocked-users-with-callouts.png "Screenshot of the PSTN blocked users report in the Microsoft Teams admin center with numbered callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="60452-110">Interpretar relatório</span><span class="sxs-lookup"><span data-stu-id="60452-110">Interpret the report</span></span>

|<span data-ttu-id="60452-111">Texto Explicativo</span><span class="sxs-lookup"><span data-stu-id="60452-111">Callout</span></span> |<span data-ttu-id="60452-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="60452-112">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="60452-113">**1**</span><span class="sxs-lookup"><span data-stu-id="60452-113">**1**</span></span>   |<span data-ttu-id="60452-114">Cada relatório tem uma data para o momento em que foi gerado.</span><span class="sxs-lookup"><span data-stu-id="60452-114">Each report has a date for when it was generated.</span></span> <span data-ttu-id="60452-115">O relatório geralmente reflete um período de latência de atividade de 24 a 48 horas.</span><span class="sxs-lookup"><span data-stu-id="60452-115">The reports usually reflect a 24 to 48 hour latency from time of activity.</span></span> |
|<span data-ttu-id="60452-116">**2**</span><span class="sxs-lookup"><span data-stu-id="60452-116">**2**</span></span>   |<span data-ttu-id="60452-117">O eixo X é a data.</span><span class="sxs-lookup"><span data-stu-id="60452-117">The X axis is the date.</span></span> <span data-ttu-id="60452-118">O eixo Y é o número de usuários.</span><span class="sxs-lookup"><span data-stu-id="60452-118">The Y axis is the number of users.</span></span> <br><span data-ttu-id="60452-119">Passe o mouse sobre o ponto em uma determinada data para ver o número de usuários bloqueados nessa data.</span><span class="sxs-lookup"><span data-stu-id="60452-119">Hover over the dot on a given date to see the number of users blocked on that date.</span></span> |
|<span data-ttu-id="60452-120">**3**</span><span class="sxs-lookup"><span data-stu-id="60452-120">**3**</span></span>   |<span data-ttu-id="60452-121">A tabela fornece uma divisão de todos os usuários que estão bloqueados para fazerem chamadas PSTN.</span><span class="sxs-lookup"><span data-stu-id="60452-121">The table gives a breakdown of all users who are blocked from making PSTN calls.</span></span>  <span data-ttu-id="60452-122">Ele mostra todos os usuários que têm o sistema de telefonia ou a conferência de áudio atribuída e fornece mais informações sobre cada usuário.</span><span class="sxs-lookup"><span data-stu-id="60452-122">It shows all users who have Phone System or Audio Conferencing assigned and gives you more information about each user.</span></span> <ul><li><span data-ttu-id="60452-123">**Nome para exibição** é o nome de exibição do usuário.</span><span class="sxs-lookup"><span data-stu-id="60452-123">**Display name** is the display name of the user.</span></span> <span data-ttu-id="60452-124">Você pode clicar no nome para exibição para acessar a página de configuração do usuário no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="60452-124">You can click the display name to go to the user's setting page in the Microsoft Teams admin center.</span></span> </li> <li><span data-ttu-id="60452-125">**Telefone** é o número atribuído ao usuário.</span><span class="sxs-lookup"><span data-stu-id="60452-125">**Phone** is the number that's assigned to the user.</span></span></li> <li><span data-ttu-id="60452-126">**Motivo bloqueado** é o motivo pelo qual o usuário está bloqueado para fazerem chamadas.</span><span class="sxs-lookup"><span data-stu-id="60452-126">**Blocked reason** is the reason the user is blocked from making calls.</span></span></li><li><span data-ttu-id="60452-127">**Ação bloqueada** informa se o usuário está bloqueado ou desbloqueado da realização de chamadas PSTN no Teams.</span><span class="sxs-lookup"><span data-stu-id="60452-127">**Blocked action**  tells you whether the user is blocked or unblocked from making PSTN calls in Teams.</span></span></li> <li><span data-ttu-id="60452-128">**Tempo bloqueado** é a data e a hora (UTC) em que o usuário foi bloqueado para fazerem chamadas.</span><span class="sxs-lookup"><span data-stu-id="60452-128">**Blocked time** is the date and time (UTC) that the user was blocked from making calls.</span></span></li></li> </ul><span data-ttu-id="60452-129">Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela.</span><span class="sxs-lookup"><span data-stu-id="60452-129">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="60452-130">**4**</span><span class="sxs-lookup"><span data-stu-id="60452-130">**4**</span></span>   |<span data-ttu-id="60452-131">Selecione **Editar colunas** para adicionar ou remover colunas na tabela.</span><span class="sxs-lookup"><span data-stu-id="60452-131">Select **Edit columns** to add or remove columns in the table.</span></span>|
|<span data-ttu-id="60452-132">**5**</span><span class="sxs-lookup"><span data-stu-id="60452-132">**5**</span></span>   |<span data-ttu-id="60452-133">Selecione **tela inteira** para exibir o relatório em modo de tela inteira.</span><span class="sxs-lookup"><span data-stu-id="60452-133">Select **Full screen** to view the report in full screen mode.</span></span>|

## <a name="related-topics"></a><span data-ttu-id="60452-134">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="60452-134">Related topics</span></span>

- [<span data-ttu-id="60452-135">Análises e relatórios do Teams</span><span class="sxs-lookup"><span data-stu-id="60452-135">Teams analytics and reporting</span></span>](teams-reporting-reference.md)