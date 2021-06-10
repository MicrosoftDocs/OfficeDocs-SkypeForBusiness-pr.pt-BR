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
ms.openlocfilehash: 34759e601f5c0cd232bcd6227ff5c7d1fef1d3fe
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107397"
---
# <a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="f8cd8-103">Ativar ou desativar o acesso de convidados ao Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f8cd8-103">Turn on or turn off guest access to Microsoft Teams</span></span>

> [!Note]

> <span data-ttu-id="f8cd8-104">Até **fevereiro de 2021**, o acesso de convidados é desligado por padrão.</span><span class="sxs-lookup"><span data-stu-id="f8cd8-104">Until **February 2021**, guest access is turned off by default.</span></span> <span data-ttu-id="f8cd8-105">Você deve ativar o acesso de convidado para o Teams antes que os administradores ou proprietários de equipe possam adicionar convidados.</span><span class="sxs-lookup"><span data-stu-id="f8cd8-105">You must turn on guest access for Teams before admins or team owners can add guests.</span></span> <span data-ttu-id="f8cd8-106">Depois de ativar o acesso de convidados, pode levar algumas horas para que as alterações tenham efeito.</span><span class="sxs-lookup"><span data-stu-id="f8cd8-106">After you turn on guest access, it might take a few hours for the changes to take effect.</span></span> <span data-ttu-id="f8cd8-107">Se os usuários  verem a mensagem Contate seu administrador quando tentarem adicionar um convidado à sua equipe, é provável que o acesso de convidados ainda não tenha sido ligado ou as configurações ainda não tenham sido efetivas.</span><span class="sxs-lookup"><span data-stu-id="f8cd8-107">If users see the message **Contact your administrator** when they try to add a guest to their team, it's likely that either guest access hasn't been turned on or the settings aren't effective yet.</span></span>

> <span data-ttu-id="f8cd8-108">Após **fevereiro de 2021,** o acesso de convidados no Microsoft Teams será ligado por padrão para novos clientes & clientes existentes que não tenham configurado essa configuração.</span><span class="sxs-lookup"><span data-stu-id="f8cd8-108">After **February 2021**, guest access in Microsoft Teams will be turned on by default for new customers & existing customers who haven't configured this setting.</span></span> <span data-ttu-id="f8cd8-109">Quando essa alteração for implementada, se você ainda não tiver configurado o recurso de acesso de convidado no Microsoft Teams, esse recurso será habilitado em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="f8cd8-109">When this change is implemented, if you've not already configured guest access capability in Microsoft Teams, that capability will be enabled in your tenant.</span></span> <span data-ttu-id="f8cd8-110">Se você quiser que o acesso de convidado permaneça desabilitado para sua organização, você precisará confirmar se a configuração de acesso de convidado está definida como **Desativado** em vez do **Padrão de Serviço**.</span><span class="sxs-lookup"><span data-stu-id="f8cd8-110">If you want guest access to remain disabled for your organization, you'll need to confirm that the guest access setting is set to **Off** instead of **Service default**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f8cd8-111">Ativar o acesso de convidado depende das configurações no Azure Active Directory, Microsoft 365, Microsoft Office SharePoint Online e Teams.</span><span class="sxs-lookup"><span data-stu-id="f8cd8-111">Turning on guest access depends on settings in Azure Active Directory, Microsoft 365, SharePoint, and Teams.</span></span> <span data-ttu-id="f8cd8-112">Para saber mais, confira [Colabore com os convidados em uma equipe](/microsoft-365/solutions/collaborate-as-team).</span><span class="sxs-lookup"><span data-stu-id="f8cd8-112">For more information, see [Collaborate with guests in a team](/microsoft-365/solutions/collaborate-as-team).</span></span>

## <a name="configure-guest-access-in-the-teams-admin-center"></a><span data-ttu-id="f8cd8-113">Configure o acesso de convidados no centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f8cd8-113">Configure guest access in the Teams admin center</span></span>

1. <span data-ttu-id="f8cd8-114">Entre no [Centro de administração do Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="f8cd8-114">Sign in to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

2. <span data-ttu-id="f8cd8-115">Selecione **Configurações em toda a organização** > **Acesso de convidados**.</span><span class="sxs-lookup"><span data-stu-id="f8cd8-115">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="f8cd8-116">Defina **Permitir acesso de convidado no Microsoft Teams** como **Ativado**.</span><span class="sxs-lookup"><span data-stu-id="f8cd8-116">Set **Allow guest access in Microsoft Teams** to **On**.</span></span>

    ![<span data-ttu-id="f8cd8-117">Permita que a opção de acesso de convidados seja definida como Ativada</span><span class="sxs-lookup"><span data-stu-id="f8cd8-117">Allow guest access switch set to On</span></span> ](media/guest-access-setting.png)

4. <span data-ttu-id="f8cd8-118">Em **Chamadas**, **Reunião** e **Mensagens**, selecione **Ativado** ou **Desativado** para cada recurso, dependendo do que você deseja permitir para usuários convidados.</span><span class="sxs-lookup"><span data-stu-id="f8cd8-118">Under **Calling**, **Meeting**, and **Messaging**, select **On** or **Off** for each capability, depending on what you want to allow for guest users.</span></span>

      - <span data-ttu-id="f8cd8-119">**Fazer chamadas privadas** – **Ativar** essa função para permitir que os usuários façam chamadas ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="f8cd8-119">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
      - <span data-ttu-id="f8cd8-120">**Permitir vídeo IP** - **Ativar** essa configuração para permitir que os convidados usem vídeos em suas chamadas e reuniões.</span><span class="sxs-lookup"><span data-stu-id="f8cd8-120">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
      - <span data-ttu-id="f8cd8-121">**Modo de compartilhamento de tela** – Essa configuração controla a disponibilidade do compartilhamento de tela para usuários convidados.</span><span class="sxs-lookup"><span data-stu-id="f8cd8-121">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span>
          - <span data-ttu-id="f8cd8-122">**Desativar** essa configuração para remover a capacidade de os convidados compartilharem suas telas no Teams.</span><span class="sxs-lookup"><span data-stu-id="f8cd8-122">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span>
          - <span data-ttu-id="f8cd8-123">Defina essa configuração como **Aplicativo único** para permitir o compartilhamento de aplicativos individuais.</span><span class="sxs-lookup"><span data-stu-id="f8cd8-123">Turn this setting to **Single application** to allow sharing of individual applications.</span></span>
          - <span data-ttu-id="f8cd8-124">Defina essa configuração como **Tela inteira** para permitir o compartilhamento completo da tela.</span><span class="sxs-lookup"><span data-stu-id="f8cd8-124">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
      - <span data-ttu-id="f8cd8-125">**Permitir Reunir Agora** - **Ativar** essa configuração para permitir que os convidados usem o recurso Reunir Agora no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f8cd8-125">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
      - <span data-ttu-id="f8cd8-126">**Editar mensagens enviadas** - **Ativar** essa configuração para permitir que os convidados editem as mensagens enviadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f8cd8-126">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
      - <span data-ttu-id="f8cd8-127">**Os convidados podem excluir mensagens enviadas** - **Ativar** essa configuração para permitir que os convidados excluam mensagens enviadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f8cd8-127">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
      - <span data-ttu-id="f8cd8-128">**Chat** - **Ativar** essa configuração para oferecer aos convidados a capacidade de usar o chat no Teams.</span><span class="sxs-lookup"><span data-stu-id="f8cd8-128">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
      - <span data-ttu-id="f8cd8-129">**Usar Giphys em conversas** - **Ativar** essa configuração para permitir que os convidados usem Giphys nas conversas.</span><span class="sxs-lookup"><span data-stu-id="f8cd8-129">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="f8cd8-130">O Giphy é um mecanismo de pesquisa e banco de dados online que permite aos usuários pesquisar e compartilhar arquivos GIF animados.</span><span class="sxs-lookup"><span data-stu-id="f8cd8-130">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="f8cd8-131">Cada Giphy recebe uma classificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="f8cd8-131">Each Giphy is assigned a content rating.</span></span>
      - <span data-ttu-id="f8cd8-132">**Classificação de conteúdo para Giphy** – Selecione uma classificação na lista suspensa:</span><span class="sxs-lookup"><span data-stu-id="f8cd8-132">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
          - <span data-ttu-id="f8cd8-133">**Permitir todo o conteúdo** - Os convidados poderão inserir todos os Giphys nos chats, independentemente da classificação do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="f8cd8-133">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
          - <span data-ttu-id="f8cd8-134">**Moderado** - Os convidados poderão inserir Giphys nos chats, mas o conteúdo adulto será moderadamente restringido.</span><span class="sxs-lookup"><span data-stu-id="f8cd8-134">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
          - <span data-ttu-id="f8cd8-135">**Estrito** – Os convidados podem inserir Giphys em chats, mas serão impedidos de inserir conteúdo adulto.</span><span class="sxs-lookup"><span data-stu-id="f8cd8-135">**Strict** – Guests can insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
      - <span data-ttu-id="f8cd8-136">**Usar memes em conversas** - **Ativar** essa configuração para permitir que os convidados usem memes nas conversas.</span><span class="sxs-lookup"><span data-stu-id="f8cd8-136">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
      - <span data-ttu-id="f8cd8-137">**Usar Figurinhas em conversas** - **Ativar** essa configuração para permitir que os convidados usem figurinhas nas conversas.</span><span class="sxs-lookup"><span data-stu-id="f8cd8-137">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span>

    ![Configurações de permissões de convidado no Teams](media/manage-guest-access-image1.png)

5. <span data-ttu-id="f8cd8-139">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f8cd8-139">Select **Save**.</span></span>

## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="f8cd8-140">Acesso externo (federação) e o acesso de convidado</span><span class="sxs-lookup"><span data-stu-id="f8cd8-140">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="see-also"></a><span data-ttu-id="f8cd8-141">Confira também</span><span class="sxs-lookup"><span data-stu-id="f8cd8-141">See also</span></span>

[<span data-ttu-id="f8cd8-142">Configurar a colaboração segura com o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f8cd8-142">Set up secure collaboration with Microsoft 365</span></span>](/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[<span data-ttu-id="f8cd8-143">Bloquear usuários convidados de um grupo específico</span><span class="sxs-lookup"><span data-stu-id="f8cd8-143">Block guest users from a specific team</span></span>](/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="f8cd8-144">Set-CsTeamsClientConfiguration</span><span class="sxs-lookup"><span data-stu-id="f8cd8-144">Set-CsTeamsClientConfiguration</span></span>](/powershell/module/skype/set-csteamsclientconfiguration)