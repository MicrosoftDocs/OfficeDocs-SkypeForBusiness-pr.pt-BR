---
title: "Movendo o provedor de audioconferência de um usuário para Microsoft"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 3a518241-1ecc-406a-93a1-d2653eecc0f5
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.PSTNConferencingEnableUsers
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Change your Skype for Business users from third-party audio conferencing providers (ACP) to a Microsoft dial-in conferencing provider. '
ms.openlocfilehash: 8df53a27f3dc0934411284c373206fc4b6dcf41a
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2018
---
# <a name="moving-a-users-audio-conferencing-provider-to-microsoft"></a><span data-ttu-id="b8f97-103">Movendo o provedor de audioconferência de um usuário para Microsoft</span><span class="sxs-lookup"><span data-stu-id="b8f97-103">Moving a user's audio conferencing provider to Microsoft</span></span>

<span data-ttu-id="b8f97-104">Para usar conferência de áudio no Office 365 com Skype para negócios e Teams da Microsoft, os usuários em sua organização precisam ter uma licença de **Serviços de audioconferência** atribuída a eles e seu provedor de serviços de audioconferência devem ser definidos para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b8f97-104">To use Audio Conferencing in Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an **Audio Conferencing** license assigned to them and their audio conferencing provider must be set to Microsoft.</span></span> <span data-ttu-id="b8f97-105">Para obter mais informações sobre licenciamento e quanto custa, consulte [tente ou adquirir audioconferência no Office 365](try-or-purchase-audio-conferencing-in-office-365.md) .</span><span class="sxs-lookup"><span data-stu-id="b8f97-105">See [Try or purchase Audio Conferencing in Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span></span>
  
## <a name="to-move-a-users-audio-conferencing-provider-to-microsoft"></a><span data-ttu-id="b8f97-106">Para mover o provedor de serviços de audioconferência do usuário à Microsoft</span><span class="sxs-lookup"><span data-stu-id="b8f97-106">To move a user's audio conferencing provider to Microsoft</span></span>

<span data-ttu-id="b8f97-107">Se uma licença de **Serviços de audioconferência** for atribuída a um usuário que não tem um provedor de serviços de audioconferência, o provedor do usuário será automaticamente definido como o Microsoft e você não precisa fazer qualquer outra coisa.</span><span class="sxs-lookup"><span data-stu-id="b8f97-107">If an **Audio Conferencing** license is assigned to a user who doesn't have an audio conferencing provider, the user's provider will be automatically set to Microsoft and you don't have to do anything else.</span></span> <span data-ttu-id="b8f97-108">Se o usuário já tiver um provedor de serviços de audioconferência, você deverá alterar o provedor do usuário à Microsoft após atribuindo a elas uma licença de **Serviços de audioconferência** .</span><span class="sxs-lookup"><span data-stu-id="b8f97-108">If the user already had an audio conferencing provider, you must change the user's provider to Microsoft after assigning them an **Audio Conferencing** license.</span></span>
  
<span data-ttu-id="b8f97-109">Para definir a Microsoft como o provedor de serviços de audioconferência para um usuário que tenha uma licença de **Serviços de audioconferência** atribuída, mas está usando outro provedor de serviços de audioconferência, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b8f97-109">To set Microsoft as the audio conferencing provider for a user that has an **Audio Conferencing** license assigned but is using another audio conferencing provider, do this:</span></span>
  
1. <span data-ttu-id="b8f97-110">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="b8f97-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="b8f97-111">Vá para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="b8f97-111">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="b8f97-112">No **Skype para centro de administração de negócios**, vá para a **conferência de áudio**.</span><span class="sxs-lookup"><span data-stu-id="b8f97-112">In the **Skype for Business admin center**, go to **Audio conferencing**.</span></span>
    
4. <span data-ttu-id="b8f97-113">Se você vir um banner informando que não existem usuários que têm uma **Conferência de áudio** licença atribuída, mas não tenho o Microsoft definido como seu provedor de serviços de audioconferência ainda, clique em **clique aqui para movê-los**.</span><span class="sxs-lookup"><span data-stu-id="b8f97-113">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**.</span></span> <span data-ttu-id="b8f97-114">Se você não vir o banner, no **Skype para centro de administração de negócios** clique em **usuários**e, em seguida, selecione o filtro de **usuários prontos para ser movida para conferência de áudio** .</span><span class="sxs-lookup"><span data-stu-id="b8f97-114">If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span></span>
    
5. <span data-ttu-id="b8f97-115">Selecione os usuários que você deseja mover e, em seguida, no painel de ações, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b8f97-115">Select the users you want to move, and then in the Action pane, click **Edit**.</span></span>
    
6. <span data-ttu-id="b8f97-116">Selecione **Microsoft** na lista **nome do provedor** .</span><span class="sxs-lookup"><span data-stu-id="b8f97-116">Select **Microsoft** in the **Provider name** list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b8f97-117">Quando o provedor de serviços de audioconferência de um usuário é alterado para a Microsoft, as informações de conferência de áudio do usuário serão alterado.</span><span class="sxs-lookup"><span data-stu-id="b8f97-117">When the audio conferencing provider of a user is changed to Microsoft, the audio conferencing information of the user will change.</span></span> <span data-ttu-id="b8f97-118">Se você precisa manter essas informações, por favor, registre-a em algum lugar antes de alterar o provedor de qualquer um dos usuários.</span><span class="sxs-lookup"><span data-stu-id="b8f97-118">If you need to keep this information, please record it somewhere before changing the provider of any of the users.</span></span> 
  
7. <span data-ttu-id="b8f97-119">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b8f97-119">Click **Save**.</span></span>
    
## <a name="what-else-should-i-know"></a><span data-ttu-id="b8f97-120">O que mais devo saber?</span><span class="sxs-lookup"><span data-stu-id="b8f97-120">What else should I know?</span></span>

- <span data-ttu-id="b8f97-121">Se você selecionar o usuário na lista, você pode exibir as informações de conferência de áudio padrão do usuário, mas não será possível ver o PIN de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="b8f97-121">If you select the user in the list, you can view the default audio conferencing information of the user but you won't be able to see the audio conferencing PIN.</span></span> <span data-ttu-id="b8f97-122">Você pode redefinir o PIN de um usuário de serviços de audioconferência clicando em **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="b8f97-122">You can reset the audio conferencing PIN of a user by clicking **Reset**.</span></span>
    
- <span data-ttu-id="b8f97-123">Se você deseja alterar as configurações de serviços de audioconferência para um usuário, você pode selecione o usuário na lista e, em seguida, clique em **Editar** e faça suas alterações na página **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="b8f97-123">If you want to change audio conferencing settings for a user, you can select the user from the list and then click **Edit** and make your changes on the **Properties** page.</span></span> 
    
## <a name="related-topics"></a><span data-ttu-id="b8f97-124">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b8f97-124">Related topics</span></span>

[<span data-ttu-id="b8f97-125">Configurar conferência de áudio para o Skype for Business e Teams da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b8f97-125">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
  

