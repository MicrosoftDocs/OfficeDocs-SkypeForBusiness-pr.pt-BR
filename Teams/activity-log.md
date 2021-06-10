---
title: Exibir suas atribuições de política no log de atividades no Microsoft Teams de administração
author: cichur
ms.author: v-cichur
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Saiba como exibir suas atividades de atribuição de política no log de atividades no centro Microsoft Teams administrador.
localization_priority: Normal
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a8d1d49d187808b768b4a92c64c4e667ca0ea8f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821311"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a><span data-ttu-id="9f208-103">Exibir suas atribuições de política no log de atividades</span><span class="sxs-lookup"><span data-stu-id="9f208-103">View your policy assignments in the Activity log</span></span>

<span data-ttu-id="9f208-104">Quando você atribui políticas aos usuários no centro de administração Microsoft Teams, você pode exibir o status dessas atribuições de política no log de atividades.</span><span class="sxs-lookup"><span data-stu-id="9f208-104">When you assign policies to users in the Microsoft Teams admin center, you can view the status of those policy assignments in the Activity log.</span></span> <span data-ttu-id="9f208-105">O log de atividades mostra atribuições de política para lotes de mais de 20 usuários por meio do Microsoft Teams de administração dos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="9f208-105">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="9f208-106">Lembre-se de que o log de atividades não mostra atribuições de pacote de política, atribuições de política para lotes de menos de 20 usuários por meio do centro de administração do Microsoft Teams ou atribuições de política por meio do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9f208-106">Keep in mind that the Activity log doesn't show policy package assignments, policy assignments to batches of less than 20 users through the Microsoft Teams admin center, or policy assignments through PowerShell.</span></span>

![Captura de tela da página de log atividade](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a><span data-ttu-id="9f208-108">Exibir suas atividades de atribuição de política no log de atividades</span><span class="sxs-lookup"><span data-stu-id="9f208-108">View your policy assignment activities in the Activity log</span></span>

<span data-ttu-id="9f208-109">Para exibir suas atribuições de política no log de atividades:</span><span class="sxs-lookup"><span data-stu-id="9f208-109">To view your policy assignments in the Activity log:</span></span>

1. <span data-ttu-id="9f208-110">Na navegação à esquerda do centro de administração Microsoft Teams, vá para **Painel** e, em Seguida, em **Log** de **Atividades,** selecione Exibir detalhes .</span><span class="sxs-lookup"><span data-stu-id="9f208-110">In the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity Log**, select **View details**.</span></span>
2. <span data-ttu-id="9f208-111">Você pode exibir todas as atribuições de política ou filtrar a lista por status para mostrar apenas as atribuições não iniciadas **,** em andamento **ou** **concluídas.**</span><span class="sxs-lookup"><span data-stu-id="9f208-111">You can view all policy assignments or filter the list by status to show only assignments that are **Not started**, **In progress**, or **Completed**.</span></span> <span data-ttu-id="9f208-112">Você verá as seguintes informações sobre cada atribuição:</span><span class="sxs-lookup"><span data-stu-id="9f208-112">You'll see the following information about each assignment:</span></span>
    - <span data-ttu-id="9f208-113">**Nome**: o nome da atribuição de política.</span><span class="sxs-lookup"><span data-stu-id="9f208-113">**Name**: The name of the policy assignment.</span></span> <span data-ttu-id="9f208-114">Clique no link para exibir mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="9f208-114">Click the link to view more details.</span></span> <span data-ttu-id="9f208-115">Isso inclui o número de usuários aos que a política foi atribuída e o número de atribuições concluídas, em andamento e não iniciadas.</span><span class="sxs-lookup"><span data-stu-id="9f208-115">This includes the number of users the policy was assigned to and the number of assignments completed, in progress, and not started.</span></span> <span data-ttu-id="9f208-116">Você também verá a lista de usuários no lote e o status e o resultado para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="9f208-116">You'll also see the list of users in the batch, and the status and result for each user.</span></span> <span data-ttu-id="9f208-117">Veja um exemplo:</span><span class="sxs-lookup"><span data-stu-id="9f208-117">Here's an example:</span></span>

        ![Captura de tela do](media/activity-log-policy-assignment-detail.png)

    - <span data-ttu-id="9f208-119">**Enviado**: Data e hora em que a atribuição de política foi enviada.</span><span class="sxs-lookup"><span data-stu-id="9f208-119">**Submitted**: Date and time the policy assignment was submitted.</span></span>
    - <span data-ttu-id="9f208-120">**Tempo de conclusão**: Data e hora em que a atribuição de política foi concluída.</span><span class="sxs-lookup"><span data-stu-id="9f208-120">**Completion time**: Date and time the policy assignment was completed.</span></span>
    - <span data-ttu-id="9f208-121">**Impacto em**: Número de usuários no lote.</span><span class="sxs-lookup"><span data-stu-id="9f208-121">**Impact on**: Number of users in the batch.</span></span>
    - <span data-ttu-id="9f208-122">**Status geral**: Status da atribuição de política.</span><span class="sxs-lookup"><span data-stu-id="9f208-122">**Overall status**: Status of the policy assignment.</span></span>

> [!NOTE]
> <span data-ttu-id="9f208-123">Você também pode acessar o log atividade na **página Usuários.**</span><span class="sxs-lookup"><span data-stu-id="9f208-123">You can also get to the Activity log from the **Users** page.</span></span> <span data-ttu-id="9f208-124">Depois de clicar **em Aplicar** para enviar uma atribuição de política em massa, você verá um banner na parte superior da página.</span><span class="sxs-lookup"><span data-stu-id="9f208-124">After you click **Apply** to submit a bulk policy assignment, you'll see a banner at the top of the page.</span></span> <span data-ttu-id="9f208-125">Clique no link **Log de** atividades no banner.</span><span class="sxs-lookup"><span data-stu-id="9f208-125">Click the **Activity log** link in the banner.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9f208-126">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9f208-126">Related topics</span></span>

- [<span data-ttu-id="9f208-127">Atribuir políticas aos usuários</span><span class="sxs-lookup"><span data-stu-id="9f208-127">Assign policies to users</span></span>](assign-policies.md)
