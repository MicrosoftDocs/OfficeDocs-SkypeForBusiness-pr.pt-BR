---
title: Habilitar ou desabilitar o acesso de convidados no Microsoft Teams
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 10/18/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: sbhatta
search.appverid: MET150
description: Habilitar ou desabilitar o recurso de acesso de convidados no Microsoft Teams
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2fc37cbf4774f4d8f097f27d50cc3f7c8e4bf5bf
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2019
ms.locfileid: "29753488"
---
<a name="turn-on-or-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="77443-103">Habilitar ou desabilitar o acesso de convidados no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="77443-103">Turn on or off guest access to Microsoft Teams</span></span>
======================================

<span data-ttu-id="77443-104">Como administrador do Office 365, você precisa habilitar o recurso de convidados para que você ou os usuários da sua organização (especificamente os proprietários de equipe) possam adicionar convidados.</span><span class="sxs-lookup"><span data-stu-id="77443-104">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span> 

<span data-ttu-id="77443-105">As configurações do convidado são definidas no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="77443-105">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="77443-106">Leva entre 2 e 24 horas para que as alterações entrem em vigor na sua organização do Office 365.</span><span class="sxs-lookup"><span data-stu-id="77443-106">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="77443-107">Se um usuário vê a mensagem "Contate o administrador" ao tentar adicionar um convidado para sua equipe, é provável que o recurso de convidado ainda não foi ativado ou as configurações ainda não estejam efetivas.</span><span class="sxs-lookup"><span data-stu-id="77443-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings aren't effective yet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="77443-108">Para habilitar a experiência completa do recurso de acesso de convidados, é importante compreender a dependência de autorização básica entre o Microsoft Teams, o Azure Active Directory e o Office 365.</span><span class="sxs-lookup"><span data-stu-id="77443-108">To enable the full experience of the guest access feature, it's important to understand the core authorization dependency between Microsoft Teams, Azure Active Directory, and Office 365.</span></span> <span data-ttu-id="77443-109">Para obter mais informações, consulte [Autorizar acesso de convidados no Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="77443-109">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>

## <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="77443-110">Acesso de convidado versus acesso externo (federação)</span><span class="sxs-lookup"><span data-stu-id="77443-110">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="configure-guest-access-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="77443-111">Configurar o acesso de convidado no Centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="77443-111">Configure guest access in the Microsoft Teams admin center</span></span>

1.  <span data-ttu-id="77443-112">Entrar no Centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="77443-112">Sign in to the Microsoft Teams admin center.</span></span>

2.  <span data-ttu-id="77443-113">Selecione **configurações de toda a organização** > **acesso de convidado**.</span><span class="sxs-lookup"><span data-stu-id="77443-113">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="77443-114">Defina a opção de alternância de **Permitir o acesso de convidado em equipes da Microsoft** para **ativado**.</span><span class="sxs-lookup"><span data-stu-id="77443-114">Set the **Allow guest access in Microsoft Teams** toggle switch to **On**.</span></span>

    ![<span data-ttu-id="77443-115">Permitir a opção de acesso de convidado definida como em</span><span class="sxs-lookup"><span data-stu-id="77443-115">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4.  <span data-ttu-id="77443-116">Defina a comuta em **chamar**, **reuniões**e **mensagens** como **ou **desativado**,** dependendo dos recursos que você deseja permitir para usuários convidados.</span><span class="sxs-lookup"><span data-stu-id="77443-116">Set the toggles under **Calling**, **Meeting**, and **Messaging** to **On** or **Off**, depending on the capabilities you want to allow for guest users.</span></span>

    - <span data-ttu-id="77443-117">**Fazer chamadas privadas** – ativar esta configuração **em** permitir convidados fazer chamadas ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="77443-117">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
    - <span data-ttu-id="77443-118">**Permitir que o vídeo IP** - ativar esta configuração **em** permitir convidados usar o vídeo em suas chamadas e reuniões.</span><span class="sxs-lookup"><span data-stu-id="77443-118">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
    - <span data-ttu-id="77443-119">**Modo de compartilhamento de tela** – essa configuração controla a disponibilidade da tela de compartilhamento para usuários convidados.</span><span class="sxs-lookup"><span data-stu-id="77443-119">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
       - <span data-ttu-id="77443-120">Ative esta configuração como **desabilitada** para remover a capacidade de convidados compartilhar suas telas em equipes.</span><span class="sxs-lookup"><span data-stu-id="77443-120">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
       - <span data-ttu-id="77443-121">Ative essa configuração para um **único aplicativo** para permitir o compartilhamento de aplicativos individuais.</span><span class="sxs-lookup"><span data-stu-id="77443-121">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
       - <span data-ttu-id="77443-122">Ative essa configuração para **tela inteira** para permitir o compartilhamento de tela concluída.</span><span class="sxs-lookup"><span data-stu-id="77443-122">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
    - <span data-ttu-id="77443-123">**Permitir reunir agora** – ativar esta configuração **em** permitir convidados usar o recurso reunir agora no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="77443-123">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
    - <span data-ttu-id="77443-124">**Mensagens enviadas de editar** - ativar esta configuração **em** permitir convidados editar as mensagens que eles enviados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="77443-124">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
    - <span data-ttu-id="77443-125">**Convidados podem excluir as mensagens enviadas** – ativar esta configuração **em** permitir convidados excluir mensagens que eles enviados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="77443-125">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
    - <span data-ttu-id="77443-126">**Bate-papo** – ativar esta configuração **em** dar clientes pela capacidade de usar o bate-papo em equipes.</span><span class="sxs-lookup"><span data-stu-id="77443-126">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
    - <span data-ttu-id="77443-127">**Use Giphys em conversas** – ativar esta configuração **em** permitir convidados usar Giphys em conversas.</span><span class="sxs-lookup"><span data-stu-id="77443-127">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="77443-128">Giphy é um banco de dados online e o mecanismo de pesquisa que permite aos usuários pesquisar e compartilhar arquivos GIF animados.</span><span class="sxs-lookup"><span data-stu-id="77443-128">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="77443-129">Cada Giphy é atribuída uma classificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="77443-129">Each Giphy is assigned a content rating.</span></span>
    - <span data-ttu-id="77443-130">**Classificação de conteúdo Giphy** – selecione uma classificação na lista suspensa:</span><span class="sxs-lookup"><span data-stu-id="77443-130">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
       - <span data-ttu-id="77443-131">**Permitir todo o conteúdo** - convidados serão capazes de inserir Giphys todos no bate-papo, independentemente da classificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="77443-131">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
       - <span data-ttu-id="77443-132">**Moderado** - convidados serão capazes de inserir Giphys em bate-papos, mas serão restritos relativamente de conteúdo para adultos.</span><span class="sxs-lookup"><span data-stu-id="77443-132">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
       - <span data-ttu-id="77443-133">**Restrita** – convidados serão capazes de inserir Giphys em bate-papos, mas serão restritos estritamente de inserção de conteúdo para adultos.</span><span class="sxs-lookup"><span data-stu-id="77443-133">**Strict** – Guests will be able to insert Giphys in chats, but will be strictly restricted from inserting adult content.</span></span>
    - <span data-ttu-id="77443-134">**Use Memes em conversas** - ativar esta configuração **em** permitir convidados usar Memes em conversas.</span><span class="sxs-lookup"><span data-stu-id="77443-134">**Use Memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
    - <span data-ttu-id="77443-135">**Use adesivos em conversas** – ativar esta configuração **em** permitir convidados usar adesivos em conversas.</span><span class="sxs-lookup"><span data-stu-id="77443-135">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 


5.  <span data-ttu-id="77443-136">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="77443-136">Click **Save**.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="77443-137">Usar o PowerShell para ativar ou desativar o acesso de convidado</span><span class="sxs-lookup"><span data-stu-id="77443-137">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="77443-138">Baixe o Skype para o módulo de PowerShell Online de negócios dahttps://www.microsoft.com/en-us/download/details.aspx?id=39366</span><span class="sxs-lookup"><span data-stu-id="77443-138">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/en-us/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="77443-139">Conecte-se uma sessão do PowerShell para o Skype para ponto de extremidade Business Online.</span><span class="sxs-lookup"><span data-stu-id="77443-139">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  <span data-ttu-id="77443-140">Verificar sua configuração e se `AllowGuestUser` é `$False`, use o cmdlet [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) para defini-la como `$True`.</span><span class="sxs-lookup"><span data-stu-id="77443-140">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

    ```
    Get-CsTeamsClientConfiguration

    Identity                         : Global
    AllowEmailIntoChannel            : True
    RestrictedSenderList             :
    AllowDropBox                     : True
    AllowBox                         : True
    AllowGoogleDrive                 : True
    AllowShareFile                   : True
    AllowOrganizationTab             : True
    AllowSkypeBusinessInterop        : True
    AllowTBotProactiveMessaging      : False
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
<span data-ttu-id="77443-141">Agora você pode ter usuários convidados em equipes para sua organização.</span><span class="sxs-lookup"><span data-stu-id="77443-141">You can now have guest users in Teams for your organization.</span></span>

## <a name="more-information"></a><span data-ttu-id="77443-142">Mais informações</span><span class="sxs-lookup"><span data-stu-id="77443-142">More information</span></span>

<span data-ttu-id="77443-143">Assista o vídeo a seguir para obter mais detalhes sobre o acesso de convidado.</span><span class="sxs-lookup"><span data-stu-id="77443-143">Watch the following video for more details about guest access.</span></span>

|  |  |
|---------|---------|
| <span data-ttu-id="77443-144">Adição de convidados no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="77443-144">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
