---
title: Habilitar ou desabilitar o acesso de convidados no Microsoft Teams
author: LaithAlShamri
ms.author: lolaj
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
ms.openlocfilehash: 436dc26e9ef9b75849fb6aac0383ed40bc5e581b
ms.sourcegitcommit: 5d8b5dee1dea84494aea92bbce568dea10752af9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2018
ms.locfileid: "26510556"
---
<a name="turn-on-or-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="db77e-103">Habilitar ou desabilitar o acesso de convidados no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="db77e-103">Turn on or off guest access to Microsoft Teams</span></span>
======================================

<span data-ttu-id="db77e-104">Como administrador do Office 365, você precisa habilitar o recurso de convidados para que você ou os usuários da sua organização (especificamente os proprietários de equipe) possam adicionar convidados.</span><span class="sxs-lookup"><span data-stu-id="db77e-104">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span> 

<span data-ttu-id="db77e-105">As configurações do convidado são definidas no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="db77e-105">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="db77e-106">Leva entre 2 e 24 horas para que as alterações entrem em vigor na sua organização do Office 365.</span><span class="sxs-lookup"><span data-stu-id="db77e-106">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="db77e-107">Se um usuário vê a mensagem "Contate o administrador" ao tentar adicionar um convidado para sua equipe, é provável que o recurso de convidado ainda não foi ativado ou as configurações ainda não estejam efetivas.</span><span class="sxs-lookup"><span data-stu-id="db77e-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings aren't effective yet.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="db77e-108">Para habilitar a experiência completa do recurso de acesso de convidados, é importante compreender a dependência de autorização básica entre o Microsoft Teams, o Azure Active Directory e o Office 365.</span><span class="sxs-lookup"><span data-stu-id="db77e-108">To enable the full experience of the guest access feature, it's important to understand the core authorization dependency between Microsoft Teams, Azure Active Directory, and Office 365.</span></span> <span data-ttu-id="db77e-109">Para obter mais informações, consulte [Autorizar acesso de convidados no Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="db77e-109">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>

## <a name="configure-guest-access-in-the-teams--skype-for-business-admin-center"></a><span data-ttu-id="db77e-110">Configurar o acesso de convidado na equipes & Skype para o Centro de administração de negócios</span><span class="sxs-lookup"><span data-stu-id="db77e-110">Configure guest access in the Teams & Skype for Business admin center</span></span>

1.  <span data-ttu-id="db77e-111">Entrar no equipes & Skype para centro de administração de negócios.</span><span class="sxs-lookup"><span data-stu-id="db77e-111">Sign in to the Teams & Skype for Business admin center.</span></span>

2.  <span data-ttu-id="db77e-112">Selecione **configurações de toda a organização** > **acesso de convidado**.</span><span class="sxs-lookup"><span data-stu-id="db77e-112">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="db77e-113">Defina a opção de alternância de **Permitir o acesso de convidado em equipes da Microsoft** para **ativado**.</span><span class="sxs-lookup"><span data-stu-id="db77e-113">Set the **Allow guest access in Microsoft Teams** toggle switch to **On**.</span></span>

    ![<span data-ttu-id="db77e-114">Permitir a opção de acesso de convidado definida como em</span><span class="sxs-lookup"><span data-stu-id="db77e-114">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4.  <span data-ttu-id="db77e-115">Defina a comuta em **chamar**, **reuniões**e **mensagens** como **ou **desativado**,** dependendo dos recursos que você deseja permitir para usuários convidados.</span><span class="sxs-lookup"><span data-stu-id="db77e-115">Set the toggles under **Calling**, **Meeting**, and **Messaging** to **On** or **Off**, depending on the capabilities you want to allow for guest users.</span></span>

    - <span data-ttu-id="db77e-116">**Fazer chamadas privadas** – ativar esta configuração **em** permitir convidados fazer chamadas ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="db77e-116">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
    - <span data-ttu-id="db77e-117">**Permitir que o vídeo IP** - ativar esta configuração **em** permitir convidados usar o vídeo em suas chamadas e reuniões.</span><span class="sxs-lookup"><span data-stu-id="db77e-117">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
    - <span data-ttu-id="db77e-118">**Modo de compartilhamento de tela** – essa configuração controla a disponibilidade da tela de compartilhamento para usuários convidados.</span><span class="sxs-lookup"><span data-stu-id="db77e-118">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
       - <span data-ttu-id="db77e-119">Ative esta configuração como **desabilitada** para remover a capacidade de convidados compartilhar suas telas em equipes.</span><span class="sxs-lookup"><span data-stu-id="db77e-119">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
       - <span data-ttu-id="db77e-120">Ative essa configuração para um **único aplicativo** para permitir o compartilhamento de aplicativos individuais.</span><span class="sxs-lookup"><span data-stu-id="db77e-120">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
       - <span data-ttu-id="db77e-121">Ative essa configuração para **tela inteira** para permitir o compartilhamento de tela concluída.</span><span class="sxs-lookup"><span data-stu-id="db77e-121">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
    - <span data-ttu-id="db77e-122">**Permitir reunir agora** – ativar esta configuração **em** permitir convidados usar o recurso reunir agora no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="db77e-122">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
    - <span data-ttu-id="db77e-123">**Mensagens enviadas de editar** - ativar esta configuração **em** permitir convidados editar as mensagens que eles enviados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="db77e-123">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
    - <span data-ttu-id="db77e-124">**Convidados podem excluir as mensagens enviadas** – ativar esta configuração **em** permitir convidados excluir mensagens que eles enviados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="db77e-124">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
    - <span data-ttu-id="db77e-125">**Bate-papo** – ativar esta configuração **em** dar clientes pela capacidade de usar o bate-papo em equipes.</span><span class="sxs-lookup"><span data-stu-id="db77e-125">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
    - <span data-ttu-id="db77e-126">**Use Giphys em conversas** – ativar esta configuração **em** permitir convidados usar Giphys em conversas.</span><span class="sxs-lookup"><span data-stu-id="db77e-126">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="db77e-127">Giphy é um banco de dados online e o mecanismo de pesquisa que permite aos usuários pesquisar e compartilhar arquivos GIF animados.</span><span class="sxs-lookup"><span data-stu-id="db77e-127">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="db77e-128">Cada Giphy é atribuída uma classificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="db77e-128">Each Giphy is assigned a content rating.</span></span>
    - <span data-ttu-id="db77e-129">**Classificação de conteúdo Giphy** – selecione uma classificação na lista suspensa:</span><span class="sxs-lookup"><span data-stu-id="db77e-129">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
       - <span data-ttu-id="db77e-130">**Permitir todo o conteúdo** - convidados serão capazes de inserir Giphys todos no bate-papo, independentemente da classificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="db77e-130">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
       - <span data-ttu-id="db77e-131">**Moderado** - convidados serão capazes de inserir Giphys em bate-papos, mas serão restritos relativamente de conteúdo para adultos.</span><span class="sxs-lookup"><span data-stu-id="db77e-131">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
       - <span data-ttu-id="db77e-132">**Restrita** – convidados serão capazes de inserir Giphys em bate-papos, mas serão restritos estritamente de inserção de conteúdo para adultos.</span><span class="sxs-lookup"><span data-stu-id="db77e-132">**Strict** – Guests will be able to insert Giphys in chats, but will be strictly restricted from inserting adult content.</span></span>
    - <span data-ttu-id="db77e-133">**Use Memes em conversas** - ativar esta configuração **em** permitir convidados usar Memes em conversas.</span><span class="sxs-lookup"><span data-stu-id="db77e-133">**Use Memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
    - <span data-ttu-id="db77e-134">**Use adesivos em conversas** – ativar esta configuração **em** permitir convidados usar adesivos em conversas.</span><span class="sxs-lookup"><span data-stu-id="db77e-134">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 


5.  <span data-ttu-id="db77e-135">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="db77e-135">Click **Save**.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="db77e-136">Usar o PowerShell para ativar ou desativar o acesso de convidado</span><span class="sxs-lookup"><span data-stu-id="db77e-136">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="db77e-137">Baixe o Skype para o módulo de PowerShell Online de negócios dahttps://www.microsoft.com/en-us/download/details.aspx?id=39366</span><span class="sxs-lookup"><span data-stu-id="db77e-137">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/en-us/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="db77e-138">Conecte-se uma sessão do PowerShell para o Skype para ponto de extremidade Business Online.</span><span class="sxs-lookup"><span data-stu-id="db77e-138">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  <span data-ttu-id="db77e-139">Verificar sua configuração e se `AllowGuestUser` é `$False`, use o cmdlet [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) para defini-la como `$True`.</span><span class="sxs-lookup"><span data-stu-id="db77e-139">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

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
<span data-ttu-id="db77e-140">Agora você pode ter usuários convidados em equipes para sua organização.</span><span class="sxs-lookup"><span data-stu-id="db77e-140">You can now have guest users in Teams for your organization.</span></span>

## <a name="more-information"></a><span data-ttu-id="db77e-141">Mais informações</span><span class="sxs-lookup"><span data-stu-id="db77e-141">More information</span></span>

<span data-ttu-id="db77e-142">Assista o vídeo a seguir para obter mais detalhes sobre o acesso de convidado.</span><span class="sxs-lookup"><span data-stu-id="db77e-142">Watch the following video for more details about guest access.</span></span>

|  |  |
|---------|---------|
| <span data-ttu-id="db77e-143">Adição de convidados no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="db77e-143">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
