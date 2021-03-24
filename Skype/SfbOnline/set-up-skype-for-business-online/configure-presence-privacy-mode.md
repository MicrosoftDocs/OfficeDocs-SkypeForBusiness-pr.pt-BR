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
ms.openlocfilehash: 0b708c86d2693228ad7a613755a181fff5b3743d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093465"
---
# <a name="configure-presence-privacy-mode"></a><span data-ttu-id="5be82-103">Configurar o modo de privacidade de presença</span><span class="sxs-lookup"><span data-stu-id="5be82-103">Configure presence privacy mode</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5be82-104">O centro de administração do Microsoft Teams substituiu o Centro de administração do Skype for Business (portal herdado).</span><span class="sxs-lookup"><span data-stu-id="5be82-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="5be82-105">Todas as configurações para gerenciar o Skype for Business agora estão no Centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="5be82-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="5be82-106">Você deve ter a função de administrador do [Azure AD](/azure/active-directory/roles/permissions-reference) de administrador global ou administrador do Skype for Business para gerenciar recursos do Skype for Business no centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="5be82-106">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="5be82-107">Para obter mais informações, confira [Gerenciar as configurações do Skype for Business do centro de Administração do Microsoft Teams](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span><span class="sxs-lookup"><span data-stu-id="5be82-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

<span data-ttu-id="5be82-108">A configuração de presença do Skype for Business Online oferece às pessoas mais controle sobre quem pode ver se elas estão disponíveis, em uma reunião ou fora do escritório.</span><span class="sxs-lookup"><span data-stu-id="5be82-108">The Skype for Business Online presence setting gives people more control over who can see whether they are available, in a meeting, or out of the office.</span></span> <span data-ttu-id="5be82-109">Para obter detalhes sobre as configurações de privacidade e presença do Skype for Business, consulte [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="5be82-109">For details about Skype for Business presence and privacy settings, see [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md).</span></span> 
  
## <a name="choose-the-default-online-presence-setting-for-everyone-in-your-organization"></a><span data-ttu-id="5be82-110">Escolha a configuração de presença online padrão para todos na sua organização</span><span class="sxs-lookup"><span data-stu-id="5be82-110">Choose the default online presence setting for everyone in your organization</span></span>
<span data-ttu-id="5be82-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="5be82-111"><a name="__top"> </a></span></span>

1. <span data-ttu-id="5be82-112">Vá para o Centro de administração do Skype for Business Online > **Organização > Geral.**</span><span class="sxs-lookup"><span data-stu-id="5be82-112">Go to the Skype for Business Online admin center > **Organization > General**.</span></span>
    
2. <span data-ttu-id="5be82-113">Em **Modo de privacidade de presença,** escolha a configuração e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5be82-113">Under **Presence privacy mode**, choose the setting, and then click **Save**.</span></span>
    
|<span data-ttu-id="5be82-114">**Configuração**</span><span class="sxs-lookup"><span data-stu-id="5be82-114">**Setting**</span></span>|<span data-ttu-id="5be82-115">**Quem pode exibir a presença de um usuário**</span><span class="sxs-lookup"><span data-stu-id="5be82-115">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5be82-116">**Exibir automaticamente as informações de presença**</span><span class="sxs-lookup"><span data-stu-id="5be82-116">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="5be82-117">Qualquer usuário do Skype for Business que não esteja no grupo de privacidade **Externo** ou **Bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="5be82-117">Any Skype for Business user who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> |
|<span data-ttu-id="5be82-118">**Exibir informações de presença somente para contatos de um usuário**</span><span class="sxs-lookup"><span data-stu-id="5be82-118">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="5be82-119">Qualquer pessoa na lista de contatos de um  usuário que não pertence ao **grupo de** privacidade Externo ou Bloqueado.</span><span class="sxs-lookup"><span data-stu-id="5be82-119">Anyone in a user's contact list who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> <span data-ttu-id="5be82-120">Usuários individuais podem alterar essa configuração na caixa de diálogo Opções do Skype for **Business.**</span><span class="sxs-lookup"><span data-stu-id="5be82-120">Individual users can change this setting in the Skype for Business **Options** dialog box.</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="5be82-121">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="5be82-121">Related topics</span></span>
[<span data-ttu-id="5be82-122">Instalar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="5be82-122">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="5be82-123">Permitir que os usuários do Skype for Business adicionem contatos do Skype</span><span class="sxs-lookup"><span data-stu-id="5be82-123">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
