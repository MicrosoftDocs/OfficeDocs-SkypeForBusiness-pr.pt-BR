---
title: Ativar ou desativar o acesso de convidados ao Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/06/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
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
ms.openlocfilehash: f00b585b1473a366769650c2a59f6dee2a9d3bea
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36242616"
---
<a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="49357-103">Ativar ou desativar o acesso de convidados ao Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="49357-103">Turn on or off guest access to Microsoft Teams</span></span>
===================================================

<span data-ttu-id="49357-104">Como administrador do Office 365, você precisa habilitar o recurso de convidados para que você ou os usuários da sua organização (especificamente os proprietários de equipe) possam adicionar convidados.</span><span class="sxs-lookup"><span data-stu-id="49357-104">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span>

<span data-ttu-id="49357-105">As configurações do convidado são definidas no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="49357-105">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="49357-106">Leva entre 2 e 24 horas para que as alterações entrem em vigor na sua organização do Office 365.</span><span class="sxs-lookup"><span data-stu-id="49357-106">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="49357-107">Se um usuário vir a mensagem “Entre em contato com o seu administrador” ao tentar adicionar um convidado para a sua equipe, é provável que o recurso de convidado não tenha sido ativado ou as configurações ainda não entraram em vigor.</span><span class="sxs-lookup"><span data-stu-id="49357-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings haven’t become effective yet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="49357-108">Para habilitar a experiência completa do recurso de acesso de convidados, é importante compreender a dependência de autorização básica entre o Microsoft Teams, o Azure Active Directory e o Office 365.</span><span class="sxs-lookup"><span data-stu-id="49357-108">To enable the full experience of the guest access feature, it's important to understand the core authorization dependency between Microsoft Teams, Azure Active Directory, and Office 365.</span></span> <span data-ttu-id="49357-109">Para obter mais informações, consulte [Autorizar acesso de convidados no Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="49357-109">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>

## <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="49357-110">Acesso de convidado vs. acesso externo (federação)</span><span class="sxs-lookup"><span data-stu-id="49357-110">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="configure-guest-access-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="49357-111">Configure o acesso de convidados no centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="49357-111">Configure guest access in the Microsoft Teams admin center</span></span>

1.  <span data-ttu-id="49357-112">Entre no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="49357-112">Manage teams in the Microsoft Teams admin center</span></span>

2.  <span data-ttu-id="49357-113">Selecione **Configurações em toda a organização** > **Acesso de convidados**.</span><span class="sxs-lookup"><span data-stu-id="49357-113">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="49357-114">Defina o botão de alternância **Permitir acesso de convidados no Microsoft Teams** para **Ativado**.</span><span class="sxs-lookup"><span data-stu-id="49357-114">Set the **Allow guest access in Microsoft Teams** toggle switch to **On**.</span></span>

    ![<span data-ttu-id="49357-115">Permita que a opção de acesso de convidados seja definida como Ativada</span><span class="sxs-lookup"><span data-stu-id="49357-115">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4.  <span data-ttu-id="49357-116">Defina as alternâncias em **Chamada**, **Reunião** e **Mensagens** como **Ativada** ou **Desativada**, dependendo dos recursos que você deseja permitir aos usuários convidados.</span><span class="sxs-lookup"><span data-stu-id="49357-116">Set the toggles under **Calling**, **Meeting**, and **Messaging** to **On** or **Off**, depending on the capabilities you want to allow for guest users.</span></span>

    - <span data-ttu-id="49357-117">**Fazer chamadas privadas** – **Ativar** essa função para permitir que os usuários façam chamadas ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="49357-117">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
    - <span data-ttu-id="49357-118">**Permitir vídeo IP** - **Ativar** essa configuração para permitir que os convidados usem vídeos em suas chamadas e reuniões.</span><span class="sxs-lookup"><span data-stu-id="49357-118">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
    - <span data-ttu-id="49357-119">**Modo de compartilhamento de tela** – Essa configuração controla a disponibilidade do compartilhamento de tela para usuários convidados.</span><span class="sxs-lookup"><span data-stu-id="49357-119">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
       - <span data-ttu-id="49357-120">**Desativar** essa configuração para remover a capacidade de os convidados compartilharem suas telas no Teams.</span><span class="sxs-lookup"><span data-stu-id="49357-120">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
       - <span data-ttu-id="49357-121">Defina essa configuração como **Aplicativo único** para permitir o compartilhamento de aplicativos individuais.</span><span class="sxs-lookup"><span data-stu-id="49357-121">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
       - <span data-ttu-id="49357-122">Defina essa configuração como **Tela inteira** para permitir o compartilhamento completo da tela.</span><span class="sxs-lookup"><span data-stu-id="49357-122">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
    - <span data-ttu-id="49357-123">**Permitir Reunir Agora** - **Ativar** essa configuração para permitir que os convidados usem o recurso Reunir Agora no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="49357-123">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
    - <span data-ttu-id="49357-124">**Editar mensagens enviadas** - **Ativar** essa configuração para permitir que os convidados editem as mensagens enviadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="49357-124">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
    - <span data-ttu-id="49357-125">**Os convidados podem excluir mensagens enviadas** - **Ativar** essa configuração para permitir que os convidados excluam mensagens enviadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="49357-125">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
    - <span data-ttu-id="49357-126">**Chat** - **Ativar** essa configuração para oferecer aos convidados a capacidade de usar o chat no Teams.</span><span class="sxs-lookup"><span data-stu-id="49357-126">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
    - <span data-ttu-id="49357-127">**Usar Giphys em conversas** - **Ativar** essa configuração para permitir que os convidados usem Giphys nas conversas.</span><span class="sxs-lookup"><span data-stu-id="49357-127">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="49357-128">O Giphy é um mecanismo de pesquisa e banco de dados online que permite aos usuários pesquisar e compartilhar arquivos GIF animados.</span><span class="sxs-lookup"><span data-stu-id="49357-128">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="49357-129">Cada Giphy recebe uma classificação de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="49357-129">Each Giphy is assigned a content rating.</span></span>
    - <span data-ttu-id="49357-130">**Classificação de conteúdo para Giphy** – Selecione uma classificação na lista suspensa:</span><span class="sxs-lookup"><span data-stu-id="49357-130">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
       - <span data-ttu-id="49357-131">**Permitir todo o conteúdo** - Os convidados poderão inserir todos os Giphys nos chats, independentemente da classificação do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="49357-131">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
       - <span data-ttu-id="49357-132">**Moderado** - Os convidados poderão inserir Giphys nos chats, mas o conteúdo adulto será moderadamente restringido.</span><span class="sxs-lookup"><span data-stu-id="49357-132">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
       - <span data-ttu-id="49357-133">**Estrito** - Os convidados poderão inserir Giphys nos chats, mas serão impedidos de inserir conteúdo adulto.</span><span class="sxs-lookup"><span data-stu-id="49357-133">**Strict** – Guests will be able to insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
    - <span data-ttu-id="49357-134">**Usar memes em conversas** - **Ativar** essa configuração para permitir que os convidados usem memes nas conversas.</span><span class="sxs-lookup"><span data-stu-id="49357-134">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
    - <span data-ttu-id="49357-135">**Usar Figurinhas em conversas** - **Ativar** essa configuração para permitir que os convidados usem figurinhas nas conversas.</span><span class="sxs-lookup"><span data-stu-id="49357-135">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 


5.  <span data-ttu-id="49357-136">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="49357-136">Click **Save**.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="49357-137">Use o PowerShell para ativar ou desativar o acesso de convidados</span><span class="sxs-lookup"><span data-stu-id="49357-137">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="49357-138">Baixe o módulo PowerShell do Skype for Business Online em https://www.microsoft.com/en-us/download/details.aspx?id=39366</span><span class="sxs-lookup"><span data-stu-id="49357-138">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/en-us/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="49357-139">Conecte uma sessão do PowerShell ao ponto de extremidade do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="49357-139">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  <span data-ttu-id="49357-140">Verifique sua configuração e se `AllowGuestUser` for `$False`, use o cmdlet [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) para defini-lo como `$True`.</span><span class="sxs-lookup"><span data-stu-id="49357-140">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

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
<span data-ttu-id="49357-141">Agora você pode ter usuários convidados no Teams da sua organização.</span><span class="sxs-lookup"><span data-stu-id="49357-141">You can now have guest users in Teams for your organization.</span></span>

## <a name="more-information"></a><span data-ttu-id="49357-142">Mais informações</span><span class="sxs-lookup"><span data-stu-id="49357-142">More information</span></span>

<span data-ttu-id="49357-143">Assista ao vídeo a seguir para obter mais detalhes sobre o acesso de convidados.</span><span class="sxs-lookup"><span data-stu-id="49357-143">Watch the following videos for more details about guest access:</span></span>

|  |  |
|---------|---------|
| <span data-ttu-id="49357-144">Adição de convidados no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="49357-144">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
