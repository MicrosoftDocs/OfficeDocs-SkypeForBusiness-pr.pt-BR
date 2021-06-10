---
title: Microsoft Teams Relatório de usuários bloqueados PSTN
author: cichur
ms.author: v-cichur
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
description: Use o relatório de usuários bloqueados PSTN no centro de administração Microsoft Teams para obter uma visão geral dos usuários Teams da sua organização que estão bloqueados para fazer chamadas PSTN.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ed775c3796e40a775b3be2b78f22e162a047bf78
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809331"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a><span data-ttu-id="b1a9d-103">Microsoft Teams Relatório de usuários bloqueados PSTN</span><span class="sxs-lookup"><span data-stu-id="b1a9d-103">Microsoft Teams PSTN blocked users report</span></span>

<span data-ttu-id="b1a9d-104">O relatório de usuários bloqueados PSTN no centro de administração Microsoft Teams mostra os usuários em sua organização que estão impedidos de fazer chamadas PSTN em Teams.</span><span class="sxs-lookup"><span data-stu-id="b1a9d-104">The PSTN blocked users report in the Microsoft Teams admin center shows you the users in your organization who are blocked from making PSTN calls in Teams.</span></span> <span data-ttu-id="b1a9d-105">Você pode exibir mais informações sobre cada usuário bloqueado, incluindo o número de telefone atribuído e o motivo pelo qual eles foram impedidos de fazer chamadas.</span><span class="sxs-lookup"><span data-stu-id="b1a9d-105">You can view more information about each blocked user, including their assigned phone number and the reason they were blocked from making calls.</span></span>

## <a name="view-the-pstn-blocked-users-report"></a><span data-ttu-id="b1a9d-106">Exibir o relatório de usuários bloqueados PSTN</span><span class="sxs-lookup"><span data-stu-id="b1a9d-106">View the PSTN blocked users report</span></span>

<span data-ttu-id="b1a9d-107">Na navegação à esquerda do centro de administração Microsoft Teams, clique **em Análise & relatórios** de  >  **uso.**</span><span class="sxs-lookup"><span data-stu-id="b1a9d-107">In the left navigation of the Microsoft Teams admin center, click **Analytics & reports** > **Usage reports**.</span></span> <span data-ttu-id="b1a9d-108">Na guia **Exibir relatórios,** em **Relatório,** selecione **Usuários bloqueados PSTN** e clique em **Executar relatório**.</span><span class="sxs-lookup"><span data-stu-id="b1a9d-108">On the **View reports** tab, under **Report**, select **PSTN blocked users**, and then click **Run report**.</span></span>

<span data-ttu-id="b1a9d-109">![Captura de tela do relatório de relatório de usuários bloqueados PSTN no centro de administração](../media/teams-reports-pstn-blocked-users-with-callouts.png "Captura de tela do relatório de usuários bloqueados do PSTN no centro de administração Microsoft Teams com callouts numerados")</span><span class="sxs-lookup"><span data-stu-id="b1a9d-109">![Screenshot of the PSTN blocked users report report in the admin center](../media/teams-reports-pstn-blocked-users-with-callouts.png "Screenshot of the PSTN blocked users report in the Microsoft Teams admin center with numbered callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="b1a9d-110">Interpretar relatório</span><span class="sxs-lookup"><span data-stu-id="b1a9d-110">Interpret the report</span></span>

|<span data-ttu-id="b1a9d-111">Texto Explicativo</span><span class="sxs-lookup"><span data-stu-id="b1a9d-111">Callout</span></span> |<span data-ttu-id="b1a9d-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="b1a9d-112">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="b1a9d-113">**1**</span><span class="sxs-lookup"><span data-stu-id="b1a9d-113">**1**</span></span>   |<span data-ttu-id="b1a9d-114">Cada relatório tem uma data para quando ele foi gerado.</span><span class="sxs-lookup"><span data-stu-id="b1a9d-114">Each report has a date for when it was generated.</span></span> <span data-ttu-id="b1a9d-115">O relatório geralmente reflete um período de latência de atividade de 24 a 48 horas.</span><span class="sxs-lookup"><span data-stu-id="b1a9d-115">The reports usually reflect a 24 to 48 hour latency from time of activity.</span></span> |
|<span data-ttu-id="b1a9d-116">**2**</span><span class="sxs-lookup"><span data-stu-id="b1a9d-116">**2**</span></span>   |<span data-ttu-id="b1a9d-117">O eixo X é a data.</span><span class="sxs-lookup"><span data-stu-id="b1a9d-117">The X axis is the date.</span></span> <span data-ttu-id="b1a9d-118">O eixo Y é o número de usuários.</span><span class="sxs-lookup"><span data-stu-id="b1a9d-118">The Y axis is the number of users.</span></span> <br><span data-ttu-id="b1a9d-119">Passe o mouse sobre o ponto em uma determinada data para ver o número de usuários bloqueados nessa data.</span><span class="sxs-lookup"><span data-stu-id="b1a9d-119">Hover over the dot on a given date to see the number of users blocked on that date.</span></span> |
|<span data-ttu-id="b1a9d-120">**3**</span><span class="sxs-lookup"><span data-stu-id="b1a9d-120">**3**</span></span>   |<span data-ttu-id="b1a9d-121">A tabela fornece uma divisão de todos os usuários que estão impedidos de fazer chamadas PSTN.</span><span class="sxs-lookup"><span data-stu-id="b1a9d-121">The table gives a breakdown of all users who are blocked from making PSTN calls.</span></span>  <span data-ttu-id="b1a9d-122">Ele mostra todos os usuários que Sistema de Telefonia ou Audioconferência atribuídas e fornece mais informações sobre cada usuário.</span><span class="sxs-lookup"><span data-stu-id="b1a9d-122">It shows all users who have Phone System or Audio Conferencing assigned and gives you more information about each user.</span></span> <ul><li><span data-ttu-id="b1a9d-123">**Nome para** exibição é o nome de exibição do usuário.</span><span class="sxs-lookup"><span data-stu-id="b1a9d-123">**Display name** is the display name of the user.</span></span> <span data-ttu-id="b1a9d-124">Você pode clicar no nome de exibição para ir para a página de configuração do usuário no Microsoft Teams de administração.</span><span class="sxs-lookup"><span data-stu-id="b1a9d-124">You can click the display name to go to the user's setting page in the Microsoft Teams admin center.</span></span> </li> <li><span data-ttu-id="b1a9d-125">**Telefone** é o número atribuído ao usuário.</span><span class="sxs-lookup"><span data-stu-id="b1a9d-125">**Phone** is the number that's assigned to the user.</span></span></li> <li><span data-ttu-id="b1a9d-126">**O motivo bloqueado** é o motivo pelo qual o usuário é impedido de fazer chamadas.</span><span class="sxs-lookup"><span data-stu-id="b1a9d-126">**Blocked reason** is the reason the user is blocked from making calls.</span></span></li><li><span data-ttu-id="b1a9d-127">**A ação bloqueada** informa se o usuário está bloqueado ou não bloqueado para fazer chamadas PSTN em Teams.</span><span class="sxs-lookup"><span data-stu-id="b1a9d-127">**Blocked action**  tells you whether the user is blocked or unblocked from making PSTN calls in Teams.</span></span></li> <li><span data-ttu-id="b1a9d-128">**A hora bloqueada** é a data e a hora (UTC) que o usuário foi impedido de fazer chamadas.</span><span class="sxs-lookup"><span data-stu-id="b1a9d-128">**Blocked time** is the date and time (UTC) that the user was blocked from making calls.</span></span></li></li> </ul><span data-ttu-id="b1a9d-129">Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela.</span><span class="sxs-lookup"><span data-stu-id="b1a9d-129">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="b1a9d-130">**4**</span><span class="sxs-lookup"><span data-stu-id="b1a9d-130">**4**</span></span>   |<span data-ttu-id="b1a9d-131">Selecione **Editar colunas** para adicionar ou remover colunas na tabela.</span><span class="sxs-lookup"><span data-stu-id="b1a9d-131">Select **Edit columns** to add or remove columns in the table.</span></span>|
|<span data-ttu-id="b1a9d-132">**5**</span><span class="sxs-lookup"><span data-stu-id="b1a9d-132">**5**</span></span>   |<span data-ttu-id="b1a9d-133">Selecione **Tela inteira** para exibir o relatório no modo de tela inteira.</span><span class="sxs-lookup"><span data-stu-id="b1a9d-133">Select **Full screen** to view the report in full screen mode.</span></span>|

## <a name="related-topics"></a><span data-ttu-id="b1a9d-134">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b1a9d-134">Related topics</span></span>

- [<span data-ttu-id="b1a9d-135">Análises e relatórios do Teams</span><span class="sxs-lookup"><span data-stu-id="b1a9d-135">Teams analytics and reporting</span></span>](teams-reporting-reference.md)