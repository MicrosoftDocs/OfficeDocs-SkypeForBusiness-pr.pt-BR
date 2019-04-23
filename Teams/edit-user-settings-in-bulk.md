---
title: Editar configurações de usuários do Microsoft Teams em massa
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.date: 04/19/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Saiba como gerenciar as configurações de usuário do Microsoft Teams em massa no Centro de administração do Microsoft Teams.
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.bulkoperations.edit
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c1dfba0bdaec642b0ea078d7f10ba022c8514da
ms.sourcegitcommit: 3000a661ac420eecd825a8285bdac7b744bd25da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "31988969"
---
# <a name="edit-microsoft-teams-user-settings-in-bulk"></a><span data-ttu-id="5383c-103">Editar configurações de usuário do Microsoft Teams em massa</span><span class="sxs-lookup"><span data-stu-id="5383c-103">Edit Microsoft Teams user settings in bulk</span></span>

<span data-ttu-id="5383c-104">Como um administrador, você gerenciar configurações de usuário de equipes no Centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5383c-104">As an admin, you manage Teams user settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="5383c-105">Na página **usuários** , você pode exibir informações como a conta e detalhes de licenciamento e editar a política e outras configurações.</span><span class="sxs-lookup"><span data-stu-id="5383c-105">On the **Users** page, you can view information such as account and licensing details and edit policy and other settings.</span></span> <span data-ttu-id="5383c-106">Você pode editar as configurações para usuários individualmente ou para vários usuários ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="5383c-106">You can edit settings for users individually or for multiple users at the same time.</span></span>

## <a name="edit-user-settings-in-bulk"></a><span data-ttu-id="5383c-107">Editar configurações de usuário em massa</span><span class="sxs-lookup"><span data-stu-id="5383c-107">Edit user settings in bulk</span></span>

<span data-ttu-id="5383c-108">Use o Centro de administração do Microsoft Teams para editar as configurações para vários usuários ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="5383c-108">Use the Microsoft Teams admin center to edit settings for multiple users at a time.</span></span> <span data-ttu-id="5383c-109">É recomendável editando configurações para 20 usuários ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="5383c-109">We recommend editing settings for 20 users at a time.</span></span> <span data-ttu-id="5383c-110">Para editar configurações de um grande número de usuários, use o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5383c-110">To edit settings for a large number of users, use PowerShell.</span></span> <span data-ttu-id="5383c-111">Para obter mais informações, consulte [Visão geral do PowerShell equipes](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5383c-111">For more information, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

1. <span data-ttu-id="5383c-112">No painel de navegação à esquerda do Centro de administração do Microsoft Teams, selecione **os usuários**.</span><span class="sxs-lookup"><span data-stu-id="5383c-112">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="5383c-113">Pesquise os usuários que você deseja editar ou filtrar a exibição para mostrar os usuários que deseja editar.</span><span class="sxs-lookup"><span data-stu-id="5383c-113">Search for the users you want to edit or filter the view to show the users you want to edit.</span></span>
3. <span data-ttu-id="5383c-114">No **& #x 2713;** coluna (marca de seleção), selecione os usuários, seguindo um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="5383c-114">In the **&#x2713;** (check mark) column, select users by doing one of the following:</span></span>
    - <span data-ttu-id="5383c-115">Selecione usuários um por vez.</span><span class="sxs-lookup"><span data-stu-id="5383c-115">Select users one at a time.</span></span> <span data-ttu-id="5383c-116">Um **& #x 2713;** será exibido ao lado de cada usuário que você selecionar.</span><span class="sxs-lookup"><span data-stu-id="5383c-116">A **&#x2713;** is displayed next to each user you select.</span></span> <span data-ttu-id="5383c-117">Se você selecionar mais de 20 usuários, você não serão bloqueados, mas tenha em mente que mais usuários que você selecionar, a operação levará mais para ser concluída.</span><span class="sxs-lookup"><span data-stu-id="5383c-117">If you select more than 20 users, you won't be blocked but keep in mind that the more users you select, the operation will take longer to complete.</span></span>

        ![Captura de tela da página usuários mostrando a seleção do usuário](media/bulk-edit-user-settings-select-users.png)

    - <span data-ttu-id="5383c-119">Clique no & #x 2713; (marca de seleção) na parte superior da tabela para selecionar todos os usuários (até um máximo de 20 usuários) e clique em **continuar Selecionar tudo** para concluir a seleção na caixa de diálogo **seleção limitar** .</span><span class="sxs-lookup"><span data-stu-id="5383c-119">Click the &#x2713; (check mark) at the top of the table to select all users (up to a maximum of 20 users), and then in the **Selection limit** dialog box, click **Continue select all** to complete the selection.</span></span>

        <span data-ttu-id="5383c-120">![Captura de tela da página usuários, mostrando o limite de seleção](media/bulk-edit-user-settings-select-all-limit.png)</span><span class="sxs-lookup"><span data-stu-id="5383c-120">![Screen shot of the Users page, showing the selection limit](media/bulk-edit-user-settings-select-all-limit.png)</span></span> <br> <span data-ttu-id="5383c-121">Um **& #x 2713;** será exibido ao lado dos usuários selecionados.</span><span class="sxs-lookup"><span data-stu-id="5383c-121">A **&#x2713;** is displayed next to the selected users.</span></span>

        ![Captura de tela da página usuários, mostrando 20 usuários selecionados](media/bulk-edit-user-settings-select-all.png)
4. <span data-ttu-id="5383c-123">Clique em **Editar configurações**, faça as alterações desejadas e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5383c-123">Click **Edit settings**, make the changes that you want, and then click **Save**.</span></span>

    ![Captura de tela do painel Editar configurações](media/bulk-edit-user-settings-edit-settings.png)
