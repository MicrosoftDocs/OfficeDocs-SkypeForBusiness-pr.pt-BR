---
title: 'Editar configurações em massa dos usuários do Microsoft Teams '
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.date: 04/19/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Saiba como gerenciar as configurações de usuário do Microsoft Teams em massa no centro de administração do Microsoft Teams.
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.bulkoperations.edit
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c1dfba0bdaec642b0ea078d7f10ba022c8514da
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32245050"
---
# <a name="edit-microsoft-teams-user-settings-in-bulk"></a><span data-ttu-id="fd641-103">Editar as configurações de usuário do Microsoft Teams em massa</span><span class="sxs-lookup"><span data-stu-id="fd641-103">Edit Microsoft Teams user settings in bulk</span></span>

<span data-ttu-id="fd641-104">Como administrador, você gerencia as configurações de usuário do teams no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fd641-104">As an admin, you manage Teams user settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="fd641-105">Na página **usuários** , você pode exibir informações como a conta e os detalhes de licenciamento e editar a política e outras configurações.</span><span class="sxs-lookup"><span data-stu-id="fd641-105">On the **Users** page, you can view information such as account and licensing details and edit policy and other settings.</span></span> <span data-ttu-id="fd641-106">Você pode editar as configurações de usuários individualmente ou para vários usuários ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="fd641-106">You can edit settings for users individually or for multiple users at the same time.</span></span>

## <a name="edit-user-settings-in-bulk"></a><span data-ttu-id="fd641-107">Editar configurações de usuário em massa</span><span class="sxs-lookup"><span data-stu-id="fd641-107">Edit user settings in bulk</span></span>

<span data-ttu-id="fd641-108">Use o centro de administração do Microsoft Teams para editar as configurações de vários usuários de uma vez.</span><span class="sxs-lookup"><span data-stu-id="fd641-108">Use the Microsoft Teams admin center to edit settings for multiple users at a time.</span></span> <span data-ttu-id="fd641-109">Recomendamos a edição de configurações para 20 usuários de cada vez.</span><span class="sxs-lookup"><span data-stu-id="fd641-109">We recommend editing settings for 20 users at a time.</span></span> <span data-ttu-id="fd641-110">Para editar as configurações de um grande número de usuários, use o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd641-110">To edit settings for a large number of users, use PowerShell.</span></span> <span data-ttu-id="fd641-111">Para obter mais informações, consulte [visão geral do teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fd641-111">For more information, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

1. <span data-ttu-id="fd641-112">Na navegação à esquerda do centro de administração do Microsoft Teams, selecione **usuários**.</span><span class="sxs-lookup"><span data-stu-id="fd641-112">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="fd641-113">Procure os usuários que você deseja editar ou filtrar o modo de exibição para mostrar os usuários que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="fd641-113">Search for the users you want to edit or filter the view to show the users you want to edit.</span></span>
3. <span data-ttu-id="fd641-114">Na coluna **&#x2713;** (marca de seleção), selecione usuários seguindo um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="fd641-114">In the **&#x2713;** (check mark) column, select users by doing one of the following:</span></span>
    - <span data-ttu-id="fd641-115">Selecione um usuário de cada vez.</span><span class="sxs-lookup"><span data-stu-id="fd641-115">Select users one at a time.</span></span> <span data-ttu-id="fd641-116">Um **&#x2713;** é exibido ao lado de cada usuário que você selecionar.</span><span class="sxs-lookup"><span data-stu-id="fd641-116">A **&#x2713;** is displayed next to each user you select.</span></span> <span data-ttu-id="fd641-117">Se você selecionar mais de 20 usuários, não será possível bloquea-los, mas lembre-se de que quanto mais usuários você selecionar, a operação levará mais tempo para ser concluída.</span><span class="sxs-lookup"><span data-stu-id="fd641-117">If you select more than 20 users, you won't be blocked but keep in mind that the more users you select, the operation will take longer to complete.</span></span>

        ![Captura de tela da página usuários mostrando seleção do usuário](media/bulk-edit-user-settings-select-users.png)

    - <span data-ttu-id="fd641-119">Clique na &#x2713; (marca de seleção) na parte superior da tabela para selecionar todos os usuários (até um máximo de 20 usuários) e, em seguida, na caixa de diálogo **limite de seleção** , clique em **continuar selecionar tudo** para concluir a seleção.</span><span class="sxs-lookup"><span data-stu-id="fd641-119">Click the &#x2713; (check mark) at the top of the table to select all users (up to a maximum of 20 users), and then in the **Selection limit** dialog box, click **Continue select all** to complete the selection.</span></span>

        <span data-ttu-id="fd641-120">![Captura de tela da página usuários, mostrando o limite de seleção](media/bulk-edit-user-settings-select-all-limit.png)</span><span class="sxs-lookup"><span data-stu-id="fd641-120">![Screen shot of the Users page, showing the selection limit](media/bulk-edit-user-settings-select-all-limit.png)</span></span> <br> <span data-ttu-id="fd641-121">Um **&#x2713;** é exibido ao lado dos usuários selecionados.</span><span class="sxs-lookup"><span data-stu-id="fd641-121">A **&#x2713;** is displayed next to the selected users.</span></span>

        ![Captura de tela da página usuários, mostrando 20 usuários selecionados](media/bulk-edit-user-settings-select-all.png)
4. <span data-ttu-id="fd641-123">Clique em **Editar configurações**, faça as alterações desejadas e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="fd641-123">Click **Edit settings**, make the changes that you want, and then click **Save**.</span></span>

    ![Captura de tela do painel Editar configurações](media/bulk-edit-user-settings-edit-settings.png)
