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
- m365initiative-externalcollab
ms.reviewer: rafarhi
search.appverid: MET150
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
localization_priority: Normal
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
description: Saiba mais sobre como ativar ou desativar o recurso de acesso de convidado no Microsoft Teams como um administrador do Office 365.
ms.openlocfilehash: 0920e9d8b8184f7f7ca83a71f0bd97d3a4d78470
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031187"
---
# <a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="72cea-103">Ativar ou desativar o acesso de convidados ao Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="72cea-103">Turn on or turn off guest access to Microsoft Teams</span></span>

<span data-ttu-id="72cea-104">Por padrão, o acesso de convidado está desativado.</span><span class="sxs-lookup"><span data-stu-id="72cea-104">By default, guest access is turned off.</span></span> <span data-ttu-id="72cea-105">Você deve habilitar o acesso de convidado para equipes para que administradores ou proprietários de equipe possam adicionar convidados.</span><span class="sxs-lookup"><span data-stu-id="72cea-105">You must turn on guest access for Teams before admins or team owners can add guests.</span></span>

<span data-ttu-id="72cea-106">Depois de ativar o acesso de convidado, pode levar algumas horas para que as alterações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="72cea-106">After you turn on guest access, it may take a few hours for the changes to take effect.</span></span> <span data-ttu-id="72cea-107">Se um usuário vir a mensagem "entrar em contato com seu administrador" ao tentar adicionar um convidado à equipe, é provável que o acesso de convidado não tenha sido ativado ou que as configurações ainda não estejam efetivas.</span><span class="sxs-lookup"><span data-stu-id="72cea-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either guest access hasn't been turned on or the settings aren't effective yet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="72cea-108">Ativar o acesso de convidado depende das configurações no Azure Active Directory, Microsoft 365, SharePoint e Teams.</span><span class="sxs-lookup"><span data-stu-id="72cea-108">Turning on guest access depends on settings in Azure Active Directory, Microsoft 365, SharePoint, and Teams.</span></span> <span data-ttu-id="72cea-109">Para obter mais informações, consulte [colaborar com convidados em uma equipe](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span><span class="sxs-lookup"><span data-stu-id="72cea-109">For more information, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>

## <a name="configure-guest-access-in-the-teams-admin-center"></a><span data-ttu-id="72cea-110">Configurar o acesso de convidado no centro de administração do teams</span><span class="sxs-lookup"><span data-stu-id="72cea-110">Configure guest access in the Teams admin center</span></span>

1. <span data-ttu-id="72cea-111">Entre no centro de [Administração do Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="72cea-111">Sign in to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

2. <span data-ttu-id="72cea-112">Selecione **Configurações em toda a organização** > **Acesso de convidados**.</span><span class="sxs-lookup"><span data-stu-id="72cea-112">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="72cea-113">Defina **permitir acesso de convidado no Microsoft Teams** como **ativado**.</span><span class="sxs-lookup"><span data-stu-id="72cea-113">Set **Allow guest access in Microsoft Teams** to **On**.</span></span>

    ![<span data-ttu-id="72cea-114">Permita que a opção de acesso de convidados seja definida como Ativada</span><span class="sxs-lookup"><span data-stu-id="72cea-114">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4. <span data-ttu-id="72cea-115">Em **chamadas** , **reuniões** e **mensagens** , selecione **Ativar** ou **desativar** para cada recurso, dependendo do que você deseja permitir para usuários convidados.</span><span class="sxs-lookup"><span data-stu-id="72cea-115">Under **Calling** , **Meeting** , and **Messaging** , select **On** or **Off** for each capability, depending on what you want to allow for guest users.</span></span>

      - <span data-ttu-id="72cea-116">**Fazer chamadas privadas** – **Ativar** essa função para permitir que os usuários façam chamadas ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="72cea-116">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
      - <span data-ttu-id="72cea-117">**Permitir vídeo IP** - **Ativar** essa configuração para permitir que os convidados usem vídeos em suas chamadas e reuniões.</span><span class="sxs-lookup"><span data-stu-id="72cea-117">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
      - <span data-ttu-id="72cea-118">**Modo de compartilhamento de tela** – Essa configuração controla a disponibilidade do compartilhamento de tela para usuários convidados.</span><span class="sxs-lookup"><span data-stu-id="72cea-118">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
          - <span data-ttu-id="72cea-119">**Desativar** essa configuração para remover a capacidade de os convidados compartilharem suas telas no Teams.</span><span class="sxs-lookup"><span data-stu-id="72cea-119">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
          - <span data-ttu-id="72cea-120">Defina essa configuração como **Aplicativo único** para permitir o compartilhamento de aplicativos individuais.</span><span class="sxs-lookup"><span data-stu-id="72cea-120">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
          - <span data-ttu-id="72cea-121">Defina essa configuração como **Tela inteira** para permitir o compartilhamento completo da tela.</span><span class="sxs-lookup"><span data-stu-id="72cea-121">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
      - <span data-ttu-id="72cea-122">**Permitir Reunir Agora** - **Ativar** essa configuração para permitir que os convidados usem o recurso Reunir Agora no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="72cea-122">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
      - <span data-ttu-id="72cea-123">**Editar mensagens enviadas** - **Ativar** essa configuração para permitir que os convidados editem as mensagens enviadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="72cea-123">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
      - <span data-ttu-id="72cea-124">**Os convidados podem excluir mensagens enviadas** - **Ativar** essa configuração para permitir que os convidados excluam mensagens enviadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="72cea-124">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
      - <span data-ttu-id="72cea-125">**Chat** - **Ativar** essa configuração para oferecer aos convidados a capacidade de usar o chat no Teams.</span><span class="sxs-lookup"><span data-stu-id="72cea-125">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
      - <span data-ttu-id="72cea-126">**Usar Giphys em conversas** - **Ativar** essa configuração para permitir que os convidados usem Giphys nas conversas.</span><span class="sxs-lookup"><span data-stu-id="72cea-126">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="72cea-127">O Giphy é um mecanismo de pesquisa e banco de dados online que permite aos usuários pesquisar e compartilhar arquivos GIF animados.</span><span class="sxs-lookup"><span data-stu-id="72cea-127">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="72cea-128">Cada Giphy recebe uma classificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="72cea-128">Each Giphy is assigned a content rating.</span></span>
      - <span data-ttu-id="72cea-129">**Classificação de conteúdo para Giphy** – Selecione uma classificação na lista suspensa:</span><span class="sxs-lookup"><span data-stu-id="72cea-129">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
          - <span data-ttu-id="72cea-130">**Permitir todo o conteúdo** - Os convidados poderão inserir todos os Giphys nos chats, independentemente da classificação do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="72cea-130">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
          - <span data-ttu-id="72cea-131">**Moderado** - Os convidados poderão inserir Giphys nos chats, mas o conteúdo adulto será moderadamente restringido.</span><span class="sxs-lookup"><span data-stu-id="72cea-131">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
          - <span data-ttu-id="72cea-132">**Estrito** - Os convidados poderão inserir Giphys nos chats, mas serão impedidos de inserir conteúdo adulto.</span><span class="sxs-lookup"><span data-stu-id="72cea-132">**Strict** – Guests will be able to insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
      - <span data-ttu-id="72cea-133">**Usar memes em conversas** - **Ativar** essa configuração para permitir que os convidados usem memes nas conversas.</span><span class="sxs-lookup"><span data-stu-id="72cea-133">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
      - <span data-ttu-id="72cea-134">**Usar Figurinhas em conversas** - **Ativar** essa configuração para permitir que os convidados usem figurinhas nas conversas.</span><span class="sxs-lookup"><span data-stu-id="72cea-134">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 

    ![Configurações de permissões de convidado no Teams](media/manage-guest-access-image1.png)

5. <span data-ttu-id="72cea-136">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="72cea-136">Click **Save**.</span></span>

## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="72cea-137">Acesso externo (federação) e o acesso de convidado</span><span class="sxs-lookup"><span data-stu-id="72cea-137">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="see-also"></a><span data-ttu-id="72cea-138">Confira também</span><span class="sxs-lookup"><span data-stu-id="72cea-138">See also</span></span>

[<span data-ttu-id="72cea-139">Configurar a colaboração segura com o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="72cea-139">Set up secure collaboration with Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[<span data-ttu-id="72cea-140">Bloquear usuários convidados de uma equipe específica</span><span class="sxs-lookup"><span data-stu-id="72cea-140">Block guest users from a specific team</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="72cea-141">Set-CsTeamsClientConfiguration</span><span class="sxs-lookup"><span data-stu-id="72cea-141">Set-CsTeamsClientConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration)
