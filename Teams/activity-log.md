---
title: Exibir suas atribuições de política no log de atividades no centro de administração do Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Saiba como exibir suas atividades de atribuição de política no log de atividades no centro de administração do Microsoft Teams.
localization_priority: Normal
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f85899869a8578df59516d0e0d702f8e36bd951
ms.sourcegitcommit: 47637ed816b471fe689e7bdac27b73e6efced60c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44374289"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a><span data-ttu-id="a83cc-103">Exibir suas atribuições de política no registro de atividades</span><span class="sxs-lookup"><span data-stu-id="a83cc-103">View your policy assignments in the Activity log</span></span>

<span data-ttu-id="a83cc-104">Ao atribuir políticas a usuários no centro de administração do Microsoft Teams, você pode exibir o status dessas atribuições de política no log de atividades.</span><span class="sxs-lookup"><span data-stu-id="a83cc-104">When you assign policies to users in the Microsoft Teams admin center, you can view the status of those policy assignments in the Activity log.</span></span> <span data-ttu-id="a83cc-105">O registro de atividades mostra as atribuições de política para lotes de mais de 20 usuários por meio do centro de administração do Microsoft Teams dos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="a83cc-105">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="a83cc-106">Lembre-se de que o registro de atividades não mostra as atribuições de pacotes de política, atribuições de política a lotes de menos de 20 usuários por meio do centro de administração do Microsoft Teams, ou atribuições de política por meio do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a83cc-106">Keep in mind that the Activity log doesn't show policy package assignments, policy assignments to batches of less than 20 users through the Microsoft Teams admin center, or policy assignments through PowerShell.</span></span>

![Captura de tela da página log de atividades](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a><span data-ttu-id="a83cc-108">Exibir suas atividades de atribuição de política no registro de atividades</span><span class="sxs-lookup"><span data-stu-id="a83cc-108">View your policy assignment activities in the Activity log</span></span>

<span data-ttu-id="a83cc-109">Para exibir suas atribuições de política no log de atividades:</span><span class="sxs-lookup"><span data-stu-id="a83cc-109">To view your policy assignments in the Activity log:</span></span>

1. <span data-ttu-id="a83cc-110">Na navegação à esquerda do centro de administração do Microsoft Teams, vá até **painel**e, em **log de atividades**, selecione **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="a83cc-110">In the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity Log**, select **View details**.</span></span>
2. <span data-ttu-id="a83cc-111">Você pode exibir todas as atribuições de política ou filtrar a lista por status para mostrar apenas as atribuições que **não foram iniciadas**, **em andamento**ou **concluídas**.</span><span class="sxs-lookup"><span data-stu-id="a83cc-111">You can view all policy assignments or filter the list by status to show only assignments that are **Not started**, **In progress**, or **Completed**.</span></span> <span data-ttu-id="a83cc-112">Você verá as seguintes informações sobre cada tarefa:</span><span class="sxs-lookup"><span data-stu-id="a83cc-112">You'll see the following information about each assignment:</span></span>
    - <span data-ttu-id="a83cc-113">**Nome**: o nome da atribuição de política.</span><span class="sxs-lookup"><span data-stu-id="a83cc-113">**Name**: The name of the policy assignment.</span></span> <span data-ttu-id="a83cc-114">Clique no link para ver mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="a83cc-114">Click the link to view more details.</span></span> <span data-ttu-id="a83cc-115">Isso inclui o número de usuários aos quais a política foi atribuída e o número de atribuições concluídas, em andamento e não iniciada.</span><span class="sxs-lookup"><span data-stu-id="a83cc-115">This includes the number of users the policy was assigned to and the number of assignments completed, in progress, and not started.</span></span> <span data-ttu-id="a83cc-116">Você também verá a lista de usuários no lote e o status e o resultado de cada usuário.</span><span class="sxs-lookup"><span data-stu-id="a83cc-116">You'll also see the list of users in the batch, and the status and result for each user.</span></span> <span data-ttu-id="a83cc-117">Veja um exemplo:</span><span class="sxs-lookup"><span data-stu-id="a83cc-117">Here's an example:</span></span>

        ![Captura de tela do](media/activity-log-policy-assignment-detail.png)

    - <span data-ttu-id="a83cc-119">**Enviado**: data e hora em que a atribuição da política foi enviada.</span><span class="sxs-lookup"><span data-stu-id="a83cc-119">**Submitted**: Date and time the policy assignment was submitted.</span></span>
    - <span data-ttu-id="a83cc-120">**Hora da conclusão**: data e hora em que a atribuição da política foi concluída.</span><span class="sxs-lookup"><span data-stu-id="a83cc-120">**Completion time**: Date and time the policy assignment was completed.</span></span>
    - <span data-ttu-id="a83cc-121">**Impacto em**: número de usuários no lote.</span><span class="sxs-lookup"><span data-stu-id="a83cc-121">**Impact on**: Number of users in the batch.</span></span>
    - <span data-ttu-id="a83cc-122">**Status geral**: status da atribuição de política.</span><span class="sxs-lookup"><span data-stu-id="a83cc-122">**Overall status**: Status of the policy assignment.</span></span>

> [!NOTE]
> <span data-ttu-id="a83cc-123">Você também pode acessar o log de atividades na página **usuários** .</span><span class="sxs-lookup"><span data-stu-id="a83cc-123">You can also get to the Activity log from the **Users** page.</span></span> <span data-ttu-id="a83cc-124">Depois de clicar em **aplicar** para enviar uma atribuição de política em massa, você verá uma faixa na parte superior da página.</span><span class="sxs-lookup"><span data-stu-id="a83cc-124">After you click **Apply** to submit a bulk policy assignment, you'll see a banner at the top of the page.</span></span> <span data-ttu-id="a83cc-125">Clique no link do **log de atividades** na faixa.</span><span class="sxs-lookup"><span data-stu-id="a83cc-125">Click the **Activity log** link in the banner.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a83cc-126">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="a83cc-126">Related topics</span></span>

- [<span data-ttu-id="a83cc-127">Atribuir políticas a usuários</span><span class="sxs-lookup"><span data-stu-id="a83cc-127">Assign policies to users</span></span>](assign-policies.md)
