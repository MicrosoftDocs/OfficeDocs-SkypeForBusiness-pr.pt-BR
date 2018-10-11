---
title: Habilitar ou desabilitar o acesso de convidados no Microsoft Teams
author: LaithAlShamri
ms.author: lolaj
manager: serdars
ms.date: 10/11/2018
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
ms.openlocfilehash: 3ab67b3fa9ad58c1aa3e8fdd254e3b3515743b4c
ms.sourcegitcommit: 9dd5d8fe6888f0c7d2df1e40fdd8b4c80512f8f9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/11/2018
ms.locfileid: "25498117"
---
<a name="turn-on-or-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="955ff-103">Habilitar ou desabilitar o acesso de convidados no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="955ff-103">Turn on or off guest access to Microsoft Teams</span></span>
======================================

<span data-ttu-id="955ff-104">Como administrador do Office 365, você precisa habilitar o recurso de convidados para que você ou os usuários da sua organização (especificamente os proprietários de equipe) possam adicionar convidados.</span><span class="sxs-lookup"><span data-stu-id="955ff-104">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span> 

<span data-ttu-id="955ff-105">As configurações do convidado são definidas no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="955ff-105">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="955ff-106">Leva entre 2 e 24 horas para que as alterações entrem em vigor na sua organização do Office 365.</span><span class="sxs-lookup"><span data-stu-id="955ff-106">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="955ff-107">Se um usuário vir a mensagem “Entre em contato com o seu administrador” ao tentar adicionar um convidado para a sua equipe, aparentemente o recurso de convidados não foi habilitado ou as configurações ainda não entraram em vigor.</span><span class="sxs-lookup"><span data-stu-id="955ff-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings haven’t become effective yet.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="955ff-108">Para habilitar a experiência completa do recurso de acesso de convidados, é importante compreender a dependência de autorização básica entre o Microsoft Teams, o Azure Active Directory e o Office 365.</span><span class="sxs-lookup"><span data-stu-id="955ff-108">To enable the full experience of the guest access feature, it's important to understand the core authorization dependency between Microsoft Teams, Azure Active Directory, and Office 365.</span></span> <span data-ttu-id="955ff-109">Para obter mais informações, consulte [Autorizar acesso de convidados no Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="955ff-109">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>

## <a name="configure-guest-access-in-the-teams--skype-for-business-admin-center"></a><span data-ttu-id="955ff-110">Configurar o acesso de convidado na equipes & Skype para o Centro de administração de negócios</span><span class="sxs-lookup"><span data-stu-id="955ff-110">Configure guest access in the Teams & Skype for Business admin center</span></span>

1.  <span data-ttu-id="955ff-111">Entrar no equipes & Skype para centro de administração de negócios.</span><span class="sxs-lookup"><span data-stu-id="955ff-111">Sign in to the Teams & Skype for Business admin center.</span></span>

2.  <span data-ttu-id="955ff-112">Selecione **configurações de toda a organização** > **acesso de convidado**.</span><span class="sxs-lookup"><span data-stu-id="955ff-112">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="955ff-113">Defina a opção de alternância de **Permitir o acesso de convidado em equipes da Microsoft** para **ativado**.</span><span class="sxs-lookup"><span data-stu-id="955ff-113">Set the **Allow guest access in Microsoft Teams** toggle switch to **On**.</span></span>

    ![<span data-ttu-id="955ff-114">Permitir a opção de acesso de convidado definida como em</span><span class="sxs-lookup"><span data-stu-id="955ff-114">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4.  <span data-ttu-id="955ff-115">Defina a alterna para **chamar**, **reuniões**e **mensagens** para **ou **desativado**,** dependendo do acesso que você deseja permitir.</span><span class="sxs-lookup"><span data-stu-id="955ff-115">Set the toggles for **Calling**, **Meeting**, and **Messaging** to **On** or **Off**, depending on the access you want to allow.</span></span>

5.  <span data-ttu-id="955ff-116">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="955ff-116">Click **Save**.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="955ff-117">Usar o PowerShell para ativar ou desativar o acesso de convidado</span><span class="sxs-lookup"><span data-stu-id="955ff-117">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="955ff-118">Baixe o Skype para o módulo de PowerShell Online de negócios dahttps://www.microsoft.com/en-us/download/details.aspx?id=39366</span><span class="sxs-lookup"><span data-stu-id="955ff-118">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/en-us/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="955ff-119">Conecte-se uma sessão do PowerShell para o Skype para ponto de extremidade Business Online.</span><span class="sxs-lookup"><span data-stu-id="955ff-119">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  <span data-ttu-id="955ff-120">Verificar sua configuração e se `AllowGuestUser` é `$False`, use o cmdlet [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) para defini-la como `$True`.</span><span class="sxs-lookup"><span data-stu-id="955ff-120">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

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
<span data-ttu-id="955ff-121">Agora você pode ter usuários convidados em equipes para sua organização.</span><span class="sxs-lookup"><span data-stu-id="955ff-121">You can now have guest users in Teams for your organization.</span></span>

## <a name="more-information"></a><span data-ttu-id="955ff-122">Mais informações</span><span class="sxs-lookup"><span data-stu-id="955ff-122">More information</span></span>

<span data-ttu-id="955ff-123">Assista o vídeo a seguir para obter mais detalhes sobre o acesso de convidado.</span><span class="sxs-lookup"><span data-stu-id="955ff-123">Watch the following video for more details about guest access.</span></span>

|  |  |
|---------|---------|
| <span data-ttu-id="955ff-124">Adição de convidados no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="955ff-124">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
