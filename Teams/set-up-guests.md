---
title: Ativar ou desativar o acesso de convidado ao Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/06/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Habilitar ou desabilitar o recurso de acesso de convidados no Microsoft Teams
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
appliesto:
- Microsoft Teams
ms.openlocfilehash: 240e93d5f6329090940e6bf49cb2d6a4ee46ce2f
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221447"
---
<a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="beba2-103">Ativar ou desativar o acesso de convidado ao Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="beba2-103">Turn on or turn off guest access to Microsoft Teams</span></span>
===================================================

<span data-ttu-id="beba2-104">Como administrador do Office 365, você precisa habilitar o recurso de convidados para que você ou os usuários da sua organização (especificamente os proprietários de equipe) possam adicionar convidados.</span><span class="sxs-lookup"><span data-stu-id="beba2-104">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span>

<span data-ttu-id="beba2-105">As configurações do convidado são definidas no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="beba2-105">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="beba2-106">Leva entre 2 e 24 horas para que as alterações entrem em vigor na sua organização do Office 365.</span><span class="sxs-lookup"><span data-stu-id="beba2-106">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="beba2-107">Se um usuário vir a mensagem "entrar em contato com seu administrador" ao tentar adicionar um convidado à equipe, é provável que o recurso convidado ainda não tenha sido habilitado ou que as configurações ainda não sejam efetivadas.</span><span class="sxs-lookup"><span data-stu-id="beba2-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings aren't effective yet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="beba2-108">Para habilitar a experiência completa do recurso de acesso de convidados, é importante compreender a dependência de autorização básica entre o Microsoft Teams, o Azure Active Directory e o Office 365.</span><span class="sxs-lookup"><span data-stu-id="beba2-108">To enable the full experience of the guest access feature, it's important to understand the core authorization dependency between Microsoft Teams, Azure Active Directory, and Office 365.</span></span> <span data-ttu-id="beba2-109">Para obter mais informações, consulte [Autorizar acesso de convidados no Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="beba2-109">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>

## <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="beba2-110">Acesso de convidado vs. acesso externo (federação)</span><span class="sxs-lookup"><span data-stu-id="beba2-110">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="configure-guest-access-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="beba2-111">Configurar o acesso de convidado no centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="beba2-111">Configure guest access in the Microsoft Teams admin center</span></span>

1.  <span data-ttu-id="beba2-112">Entre no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="beba2-112">Sign in to the Microsoft Teams admin center.</span></span>

2.  <span data-ttu-id="beba2-113"> > Selecione **configurações de toda a organizaçã\o\*\*\**acesso de convidado**.</span><span class="sxs-lookup"><span data-stu-id="beba2-113">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="beba2-114">Defina o botão de alternância **permitir acesso de convidado no Microsoft Teams** como **ativado**.</span><span class="sxs-lookup"><span data-stu-id="beba2-114">Set the **Allow guest access in Microsoft Teams** toggle switch to **On**.</span></span>

    ![<span data-ttu-id="beba2-115">Opção permitir acesso de convidado definido como ativado</span><span class="sxs-lookup"><span data-stu-id="beba2-115">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4.  <span data-ttu-id="beba2-116">Defina as alternâncias em **chamada**, **reunião**e **mensagens** para **ativado** ou **desativado**, dependendo das funcionalidades que você deseja permitir para os usuários convidados.</span><span class="sxs-lookup"><span data-stu-id="beba2-116">Set the toggles under **Calling**, **Meeting**, and **Messaging** to **On** or **Off**, depending on the capabilities you want to allow for guest users.</span></span>

    - <span data-ttu-id="beba2-117">**Faça chamadas privadas** -Ative essa configuração \*\*\*\* para permitir que os convidados façam chamadas ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="beba2-117">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
    - <span data-ttu-id="beba2-118">**Permitir vídeo por IP** -Ative esta \*\*\*\* configuração para permitir que os convidados usem vídeo em suas chamadas e reuniões.</span><span class="sxs-lookup"><span data-stu-id="beba2-118">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
    - <span data-ttu-id="beba2-119">**Modo de compartilhamento de tela** – essa configuração controla a disponibilidade de compartilhamento de tela para usuários convidados.</span><span class="sxs-lookup"><span data-stu-id="beba2-119">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
       - <span data-ttu-id="beba2-120">Transforme essa configuração \*\*\*\* como desabilitada para remover a capacidade dos convidados de compartilhar suas telas no Teams.</span><span class="sxs-lookup"><span data-stu-id="beba2-120">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
       - <span data-ttu-id="beba2-121">Ative essa configuração para **um único aplicativo** para permitir o compartilhamento de aplicativos individuais.</span><span class="sxs-lookup"><span data-stu-id="beba2-121">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
       - <span data-ttu-id="beba2-122">Transforme essa configuração em **tela inteira** para permitir o compartilhamento de tela completo.</span><span class="sxs-lookup"><span data-stu-id="beba2-122">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
    - <span data-ttu-id="beba2-123">**Permitir reunião agora** – Ative essa configuração \*\*\*\* para permitir que os convidados usem o recurso reunir agora no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="beba2-123">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
    - <span data-ttu-id="beba2-124">**Editar mensagens enviadas** -Ative essa configuração \*\*\*\* para permitir que os convidados editem as mensagens que enviaram anteriormente.</span><span class="sxs-lookup"><span data-stu-id="beba2-124">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
    - <span data-ttu-id="beba2-125">**Convidados podem excluir mensagens enviadas** – Ative essa configuração \*\*\*\* para permitir que os convidados excluam mensagens que enviaram anteriormente.</span><span class="sxs-lookup"><span data-stu-id="beba2-125">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
    - <span data-ttu-id="beba2-126">**Chat** – Ative essa configuração \*\*\*\* para dar aos convidados a capacidade de usar o chat no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="beba2-126">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
    - <span data-ttu-id="beba2-127">**Use o Giphys em conversas** – Ative essa \*\*\*\* configuração para permitir que os convidados usem o Giphys nas conversas.</span><span class="sxs-lookup"><span data-stu-id="beba2-127">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="beba2-128">O Giphy é um banco de dados online e um mecanismo de pesquisa que permite aos usuários procurar e compartilhar arquivos GIF animados.</span><span class="sxs-lookup"><span data-stu-id="beba2-128">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="beba2-129">Cada Giphy é atribuído a uma classificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="beba2-129">Each Giphy is assigned a content rating.</span></span>
    - <span data-ttu-id="beba2-130">**Classificação de conteúdo do Giphy** – selecione uma classificação na lista suspensa:</span><span class="sxs-lookup"><span data-stu-id="beba2-130">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
       - <span data-ttu-id="beba2-131">**Permitir todo o conteúdo** -convidados poderão inserir todos os Giphys em chats, independentemente da classificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="beba2-131">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
       - <span data-ttu-id="beba2-132">**Moderado** -convidados poderão inserir Giphys em chats, mas serão moderadamente restritos ao conteúdo somente para adultos.</span><span class="sxs-lookup"><span data-stu-id="beba2-132">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
       - <span data-ttu-id="beba2-133">**Estrito** – os convidados poderão inserir Giphys em chats, mas não poderão inserir conteúdo somente para adultos.</span><span class="sxs-lookup"><span data-stu-id="beba2-133">**Strict** – Guests will be able to insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
    - <span data-ttu-id="beba2-134">**Usar o memes em conversas** -Ative essa \*\*\*\* configuração para permitir que os convidados usem o memes nas conversas.</span><span class="sxs-lookup"><span data-stu-id="beba2-134">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
    - <span data-ttu-id="beba2-135">**Use adesivos em conversas** – Ative essa \*\*\*\* configuração para permitir que os convidados usem adesivos nas conversas.</span><span class="sxs-lookup"><span data-stu-id="beba2-135">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 


5.  <span data-ttu-id="beba2-136">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="beba2-136">Click **Save**.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="beba2-137">Usar o PowerShell para ativar ou desativar o acesso ao convidado</span><span class="sxs-lookup"><span data-stu-id="beba2-137">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="beba2-138">Baixe o módulo PowerShell do Skype for Business online emhttps://www.microsoft.com/en-us/download/details.aspx?id=39366</span><span class="sxs-lookup"><span data-stu-id="beba2-138">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/en-us/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="beba2-139">Conecte uma sessão do PowerShell ao ponto de extremidade do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="beba2-139">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  <span data-ttu-id="beba2-140">Verifique a configuração e, `AllowGuestUser` se `$False`estiver, use o cmdlet [set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) para defini- `$True`la.</span><span class="sxs-lookup"><span data-stu-id="beba2-140">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

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
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
<span data-ttu-id="beba2-141">Agora você pode ter usuários convidados no Teams para sua organização.</span><span class="sxs-lookup"><span data-stu-id="beba2-141">You can now have guest users in Teams for your organization.</span></span>

## <a name="more-information"></a><span data-ttu-id="beba2-142">Mais informações</span><span class="sxs-lookup"><span data-stu-id="beba2-142">More information</span></span>

<span data-ttu-id="beba2-143">Assista ao vídeo a seguir para obter mais detalhes sobre o acesso de convidados.</span><span class="sxs-lookup"><span data-stu-id="beba2-143">Watch the following video for more details about guest access.</span></span>

|  |  |
|---------|---------|
| <span data-ttu-id="beba2-144">Adição de convidados no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="beba2-144">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
