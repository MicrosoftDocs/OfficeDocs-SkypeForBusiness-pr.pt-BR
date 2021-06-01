---
title: Configuração de presença do Skype for Business Online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: ce59ac0b-8115-4c6b-8174-e3aef982d3cb
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
- O365P_OnlinePresenceDesc
description: 'Learn how to set up Skype for Business so you can see the availability of your co-workers. '
ms.openlocfilehash: 5eec57f295dbb45649fea6590147798881297a1b
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239961"
---
# <a name="configure-presence-in-skype-for-business-online"></a><span data-ttu-id="a849c-103">Configuração de presença do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a849c-103">Configure presence in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> <span data-ttu-id="a849c-104">O Microsoft Teams de administração substituiu o Skype for Business de administração (portal herdado).</span><span class="sxs-lookup"><span data-stu-id="a849c-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="a849c-105">Todas as configurações para o Skype for Business agora estão no centro Teams administrador.</span><span class="sxs-lookup"><span data-stu-id="a849c-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="a849c-106">Você deve ter a função de administrador do [Azure AD](/azure/active-directory/roles/permissions-reference) de administrador global ou Skype for Business para gerenciar Skype for Business recursos no centro de administração Teams do Azure.</span><span class="sxs-lookup"><span data-stu-id="a849c-106">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="a849c-107">Para obter mais informações, confira [Gerenciar as configurações do Skype for Business do centro de Administração do Microsoft Teams](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span><span class="sxs-lookup"><span data-stu-id="a849c-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

<span data-ttu-id="a849c-108">Por padrão, qualquer pessoa que possa se comunicar com uma das pessoas em sua organização usando Skype for Business também pode ver se essa pessoa está online.</span><span class="sxs-lookup"><span data-stu-id="a849c-108">By default, anyone who can communicate with one of the people in your organization using Skype for Business can also see whether that person is online.</span></span> <span data-ttu-id="a849c-109">Skype for Business mostra se uma pessoa está disponível online, em uma reunião, offline ou em outro indicador.</span><span class="sxs-lookup"><span data-stu-id="a849c-109">Skype for Business shows whether a person is available online, in a meeting, offline, or another indicator.</span></span>

![Um exemplo do status online de uma pessoa no Skype for Business.](../images/f0849132-1ddb-480f-bca6-cfe9eaa0486d.png)

<span data-ttu-id="a849c-111">Como administrador **[de](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** todos em sua empresa, você pode escolher quem vê sua presença online no Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="a849c-111">As the **[admin](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** for everyone in your business, you can choose who sees their online presence in Skype for Business.</span></span>

<span data-ttu-id="a849c-112">![Um ícone mostrando o logotipo do Skype for Business](../images/sfb-logo-30x30.png) **Usando o centro de administração do Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="a849c-112">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="a849c-113">Vá para o centro de administração > **centros de administração**  >  **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="a849c-113">Go to the admin center > **Admin centers** > **Skype for Business**.</span></span>

2. <span data-ttu-id="a849c-114">No centro **Skype for Business de administração,** escolha **organização**.</span><span class="sxs-lookup"><span data-stu-id="a849c-114">In the **Skype for Business admin center**, choose **organization**.</span></span>

3. <span data-ttu-id="a849c-115">Em **modo de privacidade de** presença, selecione uma das seguintes configurações e escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a849c-115">Under **presence privacy mode**, select one of the following settings, and then choose **Save**.</span></span>

|<span data-ttu-id="a849c-116">**Configuração**</span><span class="sxs-lookup"><span data-stu-id="a849c-116">**Setting**</span></span>|<span data-ttu-id="a849c-117">**Who pode exibir a presença de um usuário**</span><span class="sxs-lookup"><span data-stu-id="a849c-117">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a849c-118">**Exibir automaticamente as informações de presença**</span><span class="sxs-lookup"><span data-stu-id="a849c-118">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="a849c-119">Qualquer Skype for Business usuário em sua empresa que não tenha sido  adicionado  à lista Externa ou Bloqueada de uma pessoa poderá ver a presença online dessa pessoa.</span><span class="sxs-lookup"><span data-stu-id="a849c-119">Any Skype for Business user in your business who has not been added to a person's **External** or **Blocked** list will be able to see that person's online presence.</span></span> <br/> |
|<span data-ttu-id="a849c-120">**Exibir informações de presença somente para contatos de um usuário**</span><span class="sxs-lookup"><span data-stu-id="a849c-120">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="a849c-121">Qualquer pessoa na lista contatos de uma pessoa que não tenha adicionado à **lista Externa** ou **Bloqueada.**</span><span class="sxs-lookup"><span data-stu-id="a849c-121">Anyone in a person's Contacts list who they have not added to their **External** or **Blocked** list.</span></span> <br/> <span data-ttu-id="a849c-122">Os indivíduos podem substituir suas configurações padrão em seu aplicativo Skype for Business: **Configurações**  >  **Ferramentas.**  >  </span><span class="sxs-lookup"><span data-stu-id="a849c-122">Individuals can override your default settings in their Skype for Business app: **Settings** > **Tools** > **Options**.</span></span> <br/> |

<span data-ttu-id="a849c-123">Para obter informações sobre o que seus usuários podem alterar no Skype for Business, consulte estes artigos:</span><span class="sxs-lookup"><span data-stu-id="a849c-123">For information about what your users can change in Skype for Business, see these articles:</span></span>

- [<span data-ttu-id="a849c-124">Controlar o acesso às informações de presença no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="a849c-124">Control access to your presence information in Skype for Business</span></span>](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)

- [<span data-ttu-id="a849c-125">Definir opções de status em Skype for Business</span><span class="sxs-lookup"><span data-stu-id="a849c-125">Set Status options in Skype for Business</span></span>](https://support.office.com/article/efd25395-c8ef-4510-b9cb-6f70e2fff8a0)

## <a name="related-topics"></a><span data-ttu-id="a849c-126">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="a849c-126">Related topics</span></span>

[<span data-ttu-id="a849c-127">Instalar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a849c-127">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="a849c-128">Permitir que os usuários do Skype for Business adicionem contatos do Skype</span><span class="sxs-lookup"><span data-stu-id="a849c-128">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
