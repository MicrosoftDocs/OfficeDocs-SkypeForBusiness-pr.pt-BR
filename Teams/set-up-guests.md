---
title: Ativar ou desativar o acesso de convidados ao Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Saiba mais sobre como ativar ou desativar o recurso de acesso de convidado no Microsoft Teams como um administrador do Office 365.
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6674f755c4f6a36c3877680aa0c4c4de4f27c83c
ms.sourcegitcommit: 875c854547b5d3ad838ad10c1eada3f0cddc8e66
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656192"
---
<a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="0414d-103">Ativar ou desativar o acesso de convidados ao Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0414d-103">Turn on or turn off guest access to Microsoft Teams</span></span>
===================================================

<span data-ttu-id="0414d-104">Por padrão, o acesso de convidado está desativado.</span><span class="sxs-lookup"><span data-stu-id="0414d-104">By default, guest access is turned off.</span></span> <span data-ttu-id="0414d-105">Como o Microsoft 365 ou o administrador do Office 365, você deve ativar o acesso de convidado para Teams para que os proprietários do administrador ou da equipe possam adicionar convidados.</span><span class="sxs-lookup"><span data-stu-id="0414d-105">As the Microsoft 365 or Office 365 admin, you must turn on guest access for Teams before the admin or team owners can add guests.</span></span> <span data-ttu-id="0414d-106">Para ativar o acesso de convidado, use a [lista de verificação de acesso de convidado](guest-access-checklist.md).</span><span class="sxs-lookup"><span data-stu-id="0414d-106">To turn on guest access, use the [Guest access checklist](guest-access-checklist.md).</span></span> 

<span data-ttu-id="0414d-107">Depois de ativar o acesso de convidado, pode levar algumas horas para que as alterações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="0414d-107">After you turn on guest access, it may take a few hours for the changes to take effect.</span></span> <span data-ttu-id="0414d-108">Se um usuário vir a mensagem "entrar em contato com seu administrador" ao tentar adicionar um convidado à equipe, é provável que o acesso de convidado não tenha sido ativado ou que as configurações ainda não estejam efetivas.</span><span class="sxs-lookup"><span data-stu-id="0414d-108">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either guest access hasn't been turned on or the settings aren't effective yet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0414d-109">Ativar o acesso de convidado depende das configurações do Azure Active Directory, do Microsoft 365 ou do Office 365, do SharePoint Online e do teams.</span><span class="sxs-lookup"><span data-stu-id="0414d-109">Turning on guest access depends on settings in Azure Active Directory, Microsoft 365 or Office 365, SharePoint Online, and Teams.</span></span> <span data-ttu-id="0414d-110">Para obter mais informações, consulte [autorizar o acesso de convidado no Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="0414d-110">For more information, see [Authorize guest access in Teams](Teams-dependencies.md).</span></span>



## <a name="configure-guest-access-in-the-teams-admin-center"></a><span data-ttu-id="0414d-111">Configurar o acesso de convidado no centro de administração do teams</span><span class="sxs-lookup"><span data-stu-id="0414d-111">Configure guest access in the Teams admin center</span></span>

1. <span data-ttu-id="0414d-112">Entre no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0414d-112">Sign in to the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="0414d-113">Selecione **Configurações em toda a organização** > **Acesso de convidados**.</span><span class="sxs-lookup"><span data-stu-id="0414d-113">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="0414d-114">Defina **permitir acesso de convidado no Microsoft Teams** como **ativado**.</span><span class="sxs-lookup"><span data-stu-id="0414d-114">Set **Allow guest access in Microsoft Teams** to **On**.</span></span>

    ![<span data-ttu-id="0414d-115">Permita que a opção de acesso de convidados seja definida como Ativada</span><span class="sxs-lookup"><span data-stu-id="0414d-115">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4. <span data-ttu-id="0414d-116">Em **chamadas**, **reuniões**e **mensagens**, selecione **Ativar** ou **desativar** para cada recurso, dependendo do que você deseja permitir para usuários convidados.</span><span class="sxs-lookup"><span data-stu-id="0414d-116">Under **Calling**, **Meeting**, and **Messaging**, select **On** or **Off** for each capability, depending on what you want to allow for guest users.</span></span>

      - <span data-ttu-id="0414d-117">**Fazer chamadas privadas** – **Ativar** essa função para permitir que os usuários façam chamadas ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="0414d-117">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
      - <span data-ttu-id="0414d-118">**Permitir vídeo IP** - **Ativar** essa configuração para permitir que os convidados usem vídeos em suas chamadas e reuniões.</span><span class="sxs-lookup"><span data-stu-id="0414d-118">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
      - <span data-ttu-id="0414d-119">**Modo de compartilhamento de tela** – Essa configuração controla a disponibilidade do compartilhamento de tela para usuários convidados.</span><span class="sxs-lookup"><span data-stu-id="0414d-119">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
          - <span data-ttu-id="0414d-120">**Desativar** essa configuração para remover a capacidade de os convidados compartilharem suas telas no Teams.</span><span class="sxs-lookup"><span data-stu-id="0414d-120">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
          - <span data-ttu-id="0414d-121">Defina essa configuração como **Aplicativo único** para permitir o compartilhamento de aplicativos individuais.</span><span class="sxs-lookup"><span data-stu-id="0414d-121">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
          - <span data-ttu-id="0414d-122">Defina essa configuração como **Tela inteira** para permitir o compartilhamento completo da tela.</span><span class="sxs-lookup"><span data-stu-id="0414d-122">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
      - <span data-ttu-id="0414d-123">**Permitir Reunir Agora** - **Ativar** essa configuração para permitir que os convidados usem o recurso Reunir Agora no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0414d-123">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
      - <span data-ttu-id="0414d-124">**Editar mensagens enviadas** - **Ativar** essa configuração para permitir que os convidados editem as mensagens enviadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="0414d-124">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
      - <span data-ttu-id="0414d-125">**Os convidados podem excluir mensagens enviadas** - **Ativar** essa configuração para permitir que os convidados excluam mensagens enviadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="0414d-125">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
      - <span data-ttu-id="0414d-126">**Chat** - **Ativar** essa configuração para oferecer aos convidados a capacidade de usar o chat no Teams.</span><span class="sxs-lookup"><span data-stu-id="0414d-126">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
      - <span data-ttu-id="0414d-127">**Usar Giphys em conversas** - **Ativar** essa configuração para permitir que os convidados usem Giphys nas conversas.</span><span class="sxs-lookup"><span data-stu-id="0414d-127">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="0414d-128">O Giphy é um mecanismo de pesquisa e banco de dados online que permite aos usuários pesquisar e compartilhar arquivos GIF animados.</span><span class="sxs-lookup"><span data-stu-id="0414d-128">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="0414d-129">Cada Giphy recebe uma classificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="0414d-129">Each Giphy is assigned a content rating.</span></span>
      - <span data-ttu-id="0414d-130">**Classificação de conteúdo para Giphy** – Selecione uma classificação na lista suspensa:</span><span class="sxs-lookup"><span data-stu-id="0414d-130">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
          - <span data-ttu-id="0414d-131">**Permitir todo o conteúdo** - Os convidados poderão inserir todos os Giphys nos chats, independentemente da classificação do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="0414d-131">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
          - <span data-ttu-id="0414d-132">**Moderado** - Os convidados poderão inserir Giphys nos chats, mas o conteúdo adulto será moderadamente restringido.</span><span class="sxs-lookup"><span data-stu-id="0414d-132">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
          - <span data-ttu-id="0414d-133">**Estrito** - Os convidados poderão inserir Giphys nos chats, mas serão impedidos de inserir conteúdo adulto.</span><span class="sxs-lookup"><span data-stu-id="0414d-133">**Strict** – Guests will be able to insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
      - <span data-ttu-id="0414d-134">**Usar memes em conversas** - **Ativar** essa configuração para permitir que os convidados usem memes nas conversas.</span><span class="sxs-lookup"><span data-stu-id="0414d-134">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
      - <span data-ttu-id="0414d-135">**Usar Figurinhas em conversas** - **Ativar** essa configuração para permitir que os convidados usem figurinhas nas conversas.</span><span class="sxs-lookup"><span data-stu-id="0414d-135">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 

5. <span data-ttu-id="0414d-136">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0414d-136">Click **Save**.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="0414d-137">Use o PowerShell para ativar ou desativar o acesso de convidados</span><span class="sxs-lookup"><span data-stu-id="0414d-137">Use PowerShell to turn guest access on or off</span></span>

<span data-ttu-id="0414d-138">Leia [usar o PowerShell para ativar ou desativar o acesso de convidado](guest-access-PowerShell.md#use-powershell-to-turn-guest-access-on-or-off).</span><span class="sxs-lookup"><span data-stu-id="0414d-138">Read [Use PowerShell to turn guest access on or off](guest-access-PowerShell.md#use-powershell-to-turn-guest-access-on-or-off).</span></span>

## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="0414d-139">Acesso externo (federação) e o acesso de convidado</span><span class="sxs-lookup"><span data-stu-id="0414d-139">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
