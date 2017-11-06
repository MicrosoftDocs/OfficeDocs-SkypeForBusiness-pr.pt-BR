---
title: Configurar o acesso de convidados no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: Habilite o recurso do acesso de convidados no Microsoft Teams.
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 7b571d166ed1fdc078ecdb2ecc0f9bfc2ab5cdb3
ms.sourcegitcommit: f6c2673a2ccd951770296972234938e627bd49ad
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2017
---
<a name="set-up-guest-access-to-microsoft-teams"></a><span data-ttu-id="f910d-103">Configurar o acesso de convidados no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f910d-103">Set up guest access to Microsoft Teams</span></span>
======================================

<span data-ttu-id="f910d-104">O Microsoft Teams é construído em cima dos grupos do Office 365 e também depende do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f910d-104">Microsoft Teams is built upon Office 365 Groups, and it also relies on SharePoint Online.</span></span> <span data-ttu-id="f910d-105">É por isso que as configurações específicas devem ser habilitadas nos Grupos do Office 365 e no SharePoint Online, além de ativar o recurso de acesso de convidado no Teams.</span><span class="sxs-lookup"><span data-stu-id="f910d-105">That’s why specific settings must be enabled in Office 365 Groups and SharePoint Online in addition to turning on the guest access feature in Teams.</span></span>


## <a name="allow-the-addition-of-guests-in-office-365-groups"></a><span data-ttu-id="f910d-106">Permitir a adição de convidados nos grupos do Office 365</span><span class="sxs-lookup"><span data-stu-id="f910d-106">Allow the addition of guests in Office 365 Groups</span></span>
<span data-ttu-id="f910d-107"><a name="bkmk_ControlAddingGuestUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="f910d-107"></span></span>


1. <span data-ttu-id="f910d-108">Inicie sessão na sua conta de administrador global do Office 365 em [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="f910d-108">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="f910d-109">No menu de navegação, escolha **Configurações** e, em seguida, selecione **Serviços &amp; complementos**.</span><span class="sxs-lookup"><span data-stu-id="f910d-109">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
  
3. <span data-ttu-id="f910d-110">Selecione **Grupos do Office 365**.</span><span class="sxs-lookup"><span data-stu-id="f910d-110">Select **Office 365 Groups**.</span></span>
    
     ![Grupos do Office 365](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  

  

  
4. <span data-ttu-id="f910d-112">Na página de grupos do Office 365, selecione o botão de alternância para **Habilitar** ou **Desabilitar**, dependendo se desejar permitir que os proprietários de equipes e de grupos de fora de sua organização acessem os grupos do Office 365.</span><span class="sxs-lookup"><span data-stu-id="f910d-112">On the Office 365 Groups page, set the toggle to **On** or **Off**, depending if you want to let team and group owners outside your organization access Office 365 groups.</span></span> <span data-ttu-id="f910d-113">Clique ou toque no botão de alternância para **Habilitar** ao lado de **Permitir que proprietários de grupos adicionem aos grupos pessoas externas à organização**.</span><span class="sxs-lookup"><span data-stu-id="f910d-113">Click or tap the toggle to **On** next to **Let group owners add people outside the organization to groups**.</span></span>


![A captura de tela mostra o painel de Grupos do Office 365 com as opções habilitadas para permitir que membros de grupo de fora da organização acessem o conteúdo do grupo e para permitir que proprietários de grupos adicionem aos grupos pessoas externas à organização.](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)
    

## <a name="enable-sharing-in-sharepoint-online"></a><span data-ttu-id="f910d-115">Habilitar o compartilhamento no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f910d-115">Enable sharing in SharePoint Online</span></span>

<span data-ttu-id="f910d-116">A opção de compartilhamento no SharePoint Online permite que convidados sejam adicionados à sua organização.</span><span class="sxs-lookup"><span data-stu-id="f910d-116">The Sharing option allows guests to be added to your organization.</span></span> <span data-ttu-id="f910d-117">Por padrão, a opção de compartilhamento está habilitada.</span><span class="sxs-lookup"><span data-stu-id="f910d-117">By default, the Sharing option is enabled.</span></span> <span data-ttu-id="f910d-118">Para obter informações sobre como desabilitar a opção de compartilhamento, consulte [Desabilitar a opção de compartilhamento](https://support.office.com/en-us/article/Turn-on-or-off-the-Sharing-option-7c713d74-a144-4eab-92e7-d50df526ff96#bkmk_beforeyoubegin).</span><span class="sxs-lookup"><span data-stu-id="f910d-118">For information about how to turn off the Sharing option, see [Turn on or off the Sharing option](https://support.office.com/en-us/article/Turn-on-or-off-the-Sharing-option-7c713d74-a144-4eab-92e7-d50df526ff96#bkmk_beforeyoubegin).</span></span>
  
   <span data-ttu-id="f910d-119">Os administradores podem criar contas de convidados no Azure Active Directory, independentemente das configurações de compartilhamento externo.</span><span class="sxs-lookup"><span data-stu-id="f910d-119">Admins can create guest accounts in Azure Active Directory, independent from external sharing settings.</span></span> <span data-ttu-id="f910d-120">Se o compartilhamento externo estiver desativado, somente um administrador pode criar contas de convidados.</span><span class="sxs-lookup"><span data-stu-id="f910d-120">If external sharing is off, only an admin can create guest accounts.</span></span> 
    

> [!IMPORTANT]
> <span data-ttu-id="f910d-121">Se você desabilitar a opção de compartilhamento, o acesso de convidados ficará indisponível.</span><span class="sxs-lookup"><span data-stu-id="f910d-121">If you turn off the Sharing option, guest access isn't available.</span></span> 
  

## <a name="turn-on-or-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="f910d-122">Habilitar ou desabilitar o acesso de convidados no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f910d-122">Turn on or off guest access for Microsoft Teams</span></span>
<span data-ttu-id="f910d-123"><a name="bkmk_TurnonOrTurnOff"> </a></span><span class="sxs-lookup"><span data-stu-id="f910d-123"></span></span>

<span data-ttu-id="f910d-124">Como administrador do Office 365, você precisa habilitar o recurso de convidados para que você ou os usuários da sua organização (especificamente os proprietários de equipe) possam adicionar convidados.</span><span class="sxs-lookup"><span data-stu-id="f910d-124">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span> 

<span data-ttu-id="f910d-125">As configurações do convidado são definidas no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f910d-125">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="f910d-126">Leva entre 2 e 24 horas para que as alterações entrem em vigor na sua organização do Office 365.</span><span class="sxs-lookup"><span data-stu-id="f910d-126">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="f910d-127">Se um usuário vir a mensagem “Entre em contato com o seu administrador” ao tentar adicionar um convidado para a sua equipe, aparentemente o recurso de convidados não foi habilitado ou as configurações ainda não entraram em vigor.</span><span class="sxs-lookup"><span data-stu-id="f910d-127">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings haven’t become effective yet.</span></span>



1. <span data-ttu-id="f910d-128">Inicie sessão na sua conta de administrador global do Office 365 em [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="f910d-128">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="f910d-129">No menu de navegação, escolha **Configurações** e, em seguida, selecione **Serviços &amp; complementos**.</span><span class="sxs-lookup"><span data-stu-id="f910d-129">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
     ![Inicie sessão no Office 365, vá para o centro de administração, vá até Configurações, e então escolha Serviços &amp; complementos.](media/99e676d4-5b48-4525-9556-547031fa37d9.png)
  
 

  
3. <span data-ttu-id="f910d-131">Selecione **Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="f910d-131">Select **Microsoft Teams**.</span></span>
    
     ![A captura de tela mostra a opção para o complemento do Microsoft Teams, conforme selecionado do centro de administração do Office 365.](media/17ac5608-d212-4fa8-ae3a-e78c62003968.png)
  
  
4. <span data-ttu-id="f910d-133">Em **Selecionar o tipo de licença/usuário que deseja configurar**, selecione **Convidado**.</span><span class="sxs-lookup"><span data-stu-id="f910d-133">In **Select the user/license type you want to configure**, select **Guest**.</span></span>
   
    ![A captura de tela do complemento do Microsoft Teams mostra a licença de Convidado selecionada e a opção do Microsoft Teams definida para Habilitado.](media/92aabda5-431c-4fdd-803e-5ab49290f4f7.png)
      

  
  
5. <span data-ttu-id="f910d-135">Clique ou toque no botão de alternância ao lado de **Tornar o Microsoft Teams habilitado ou desabilitado para todos os usuários desse tipo** para **Habilitar** para ativar o acesso de convidados no Teams para a sua organização e, em seguida, escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f910d-135">Click or tap the toggle next to **Turn Microsoft Teams on or off for all users of this type** to **On** to turn on Teams and guest access for your organization, and then choose **Save**.</span></span> 
    
  

