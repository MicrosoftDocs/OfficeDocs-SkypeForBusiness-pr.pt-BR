---
title: Configurar o modo de privacidade de presença
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b33d57fe-b9cf-43c1-961a-edf28db738e8
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- ms.lync.lac.OrgPresencePrivacy
description: 'Saiba como configurar o modo de privacidade para seus usuários para que eles possam controlar melhor como as pessoas veem sua disponibilidade. '
ms.openlocfilehash: a2b4ed11f1d56927a4bc7eed6ce36b5b04411509
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753436"
---
# <a name="configure-presence-privacy-mode"></a><span data-ttu-id="b0f9d-103">Configurar o modo de privacidade de presença</span><span class="sxs-lookup"><span data-stu-id="b0f9d-103">Configure presence privacy mode</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b0f9d-104">O centro de administração do Microsoft Teams substituiu o centro de administração do Skype for Business (Portal herdado).</span><span class="sxs-lookup"><span data-stu-id="b0f9d-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="b0f9d-105">Todas as configurações para gerenciar o Skype for Business agora estão no centro de administração do teams.</span><span class="sxs-lookup"><span data-stu-id="b0f9d-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="b0f9d-106">Você deve receber a função de administrador global do [Azure ad](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) ou administrador do Skype for Business para gerenciar os recursos do Skype for Business no centro de administração do teams.</span><span class="sxs-lookup"><span data-stu-id="b0f9d-106">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="b0f9d-107">Para obter mais informações, confira [Gerenciar as configurações do Skype for Business do centro de Administração do Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="b0f9d-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="b0f9d-108">A configuração de presença do Skype for Business Online permite que as pessoas tenham mais controle sobre quem pode ver se estão disponíveis, em uma reunião ou fora do escritório.</span><span class="sxs-lookup"><span data-stu-id="b0f9d-108">The Skype for Business Online presence setting gives people more control over who can see whether they are available, in a meeting, or out of the office.</span></span> <span data-ttu-id="b0f9d-109">Para obter detalhes sobre as configurações de presença e privacidade do Skype for Business, consulte [Configurar presença no Skype for Business online](configure-presence-in-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="b0f9d-109">For details about Skype for Business presence and privacy settings, see [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md).</span></span> 
  
## <a name="choose-the-default-online-presence-setting-for-everyone-in-your-organization"></a><span data-ttu-id="b0f9d-110">Escolher a configuração de presença online padrão para todas as pessoas em sua organização</span><span class="sxs-lookup"><span data-stu-id="b0f9d-110">Choose the default online presence setting for everyone in your organization</span></span>
<span data-ttu-id="b0f9d-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="b0f9d-111"><a name="__top"> </a></span></span>

1. <span data-ttu-id="b0f9d-112">Vá para o centro de administração do Skype for Business online > **organização > geral**.</span><span class="sxs-lookup"><span data-stu-id="b0f9d-112">Go to the Skype for Business Online admin center > **Organization > General**.</span></span>
    
2. <span data-ttu-id="b0f9d-113">Em **modo de privacidade de presença**, escolha a configuração e, em seguida, clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="b0f9d-113">Under **Presence privacy mode**, choose the setting, and then click **Save**.</span></span>
    
|<span data-ttu-id="b0f9d-114">**Configuração**</span><span class="sxs-lookup"><span data-stu-id="b0f9d-114">**Setting**</span></span>|<span data-ttu-id="b0f9d-115">**Quem pode ver a presença de um usuário**</span><span class="sxs-lookup"><span data-stu-id="b0f9d-115">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0f9d-116">**Exibir automaticamente as informações de presença**</span><span class="sxs-lookup"><span data-stu-id="b0f9d-116">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="b0f9d-117">Qualquer usuário do Skype for Business que não esteja no grupo de privacidade **Externo** ou **Bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="b0f9d-117">Any Skype for Business user who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> |
|<span data-ttu-id="b0f9d-118">**Exibir informações de presença somente para os contatos de um usuário**</span><span class="sxs-lookup"><span data-stu-id="b0f9d-118">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="b0f9d-119">Qualquer pessoa na lista de contatos de um usuário que não pertence ao grupo de privacidade **externo** ou **bloqueado** .</span><span class="sxs-lookup"><span data-stu-id="b0f9d-119">Anyone in a user's contact list who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> <span data-ttu-id="b0f9d-120">Usuários individuais podem alterar essa configuração na caixa de diálogo **Opções** do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="b0f9d-120">Individual users can change this setting in the Skype for Business **Options** dialog box.</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="b0f9d-121">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b0f9d-121">Related topics</span></span>
[<span data-ttu-id="b0f9d-122">Instalar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b0f9d-122">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="b0f9d-123">Permitir que os usuários do Skype for Business adicionem contatos do Skype</span><span class="sxs-lookup"><span data-stu-id="b0f9d-123">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
