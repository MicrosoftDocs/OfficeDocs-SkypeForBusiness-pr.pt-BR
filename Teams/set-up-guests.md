---
title: Habilitar ou desabilitar o acesso de convidados no Microsoft Teams
author: LaithAlShamri
ms.author: laal
manager: lolaj
ms.date: 11/10/17
ms.topic: article
ms.service: msteams
description: Habilitar ou desabilitar o recurso de acesso de convidados no Microsoft Teams
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: a996f7cc9154d04870e4dea00da950d340de16e2
ms.sourcegitcommit: 4a396557d51c7fb246144cd682bcf5e6a2c823be
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2017
---
<a name="turn-on-or-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="0dcaf-103">Habilitar ou desabilitar o acesso de convidados no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0dcaf-103">Turn on or off guest access to Microsoft Teams</span></span>
======================================





  



<span data-ttu-id="0dcaf-104">Como administrador do Office 365, você precisa habilitar o recurso de convidados para que você ou os usuários da sua organização (especificamente os proprietários de equipe) possam adicionar convidados.</span><span class="sxs-lookup"><span data-stu-id="0dcaf-104">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span> 

<span data-ttu-id="0dcaf-105">As configurações do convidado são definidas no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0dcaf-105">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="0dcaf-106">Leva entre 2 e 24 horas para que as alterações entrem em vigor na sua organização do Office 365.</span><span class="sxs-lookup"><span data-stu-id="0dcaf-106">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="0dcaf-107">Se um usuário vir a mensagem “Entre em contato com o seu administrador” ao tentar adicionar um convidado para a sua equipe, aparentemente o recurso de convidados não foi habilitado ou as configurações ainda não entraram em vigor.</span><span class="sxs-lookup"><span data-stu-id="0dcaf-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings haven’t become effective yet.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="0dcaf-108">Para habilitar a experiência completa do recurso de acesso de convidados, é importante compreender a dependência de autorização básica entre o Microsoft Teams, o Azure Active Directory e o Office 365.</span><span class="sxs-lookup"><span data-stu-id="0dcaf-108">To enable the full experience of the guest access feature, it's important to understand the core authorization dependency between Microsoft Teams, Azure Active Directory, and Office 365.</span></span> <span data-ttu-id="0dcaf-109">Para obter mais informações, consulte [Autorizar acesso de convidados no Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="0dcaf-109">For more information, see [Control guest access to Microsoft Teams](Teams-dependencies.md).</span></span>

1. <span data-ttu-id="0dcaf-110">Inicie sessão na sua conta de administrador global do Office 365 em [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="0dcaf-110">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="0dcaf-111">No menu de navegação, escolha **Configurações** e, em seguida, selecione **Serviços &amp; complementos**.</span><span class="sxs-lookup"><span data-stu-id="0dcaf-111">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
     ![Inicie sessão no Office 365, vá para o centro de administração, vá até Configurações, e então escolha Serviços &amp; complementos.](media/99e676d4-5b48-4525-9556-547031fa37d9.png)
  
 

  
3. <span data-ttu-id="0dcaf-113">Selecione **Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="0dcaf-113">Select **Microsoft Teams**.</span></span>
    
     ![A captura de tela mostra a opção para o complemento do Microsoft Teams, conforme selecionado do centro de administração do Office 365.](media/17ac5608-d212-4fa8-ae3a-e78c62003968.png)
  
  
4. <span data-ttu-id="0dcaf-115">Em **Selecionar o tipo de licença/usuário que deseja configurar**, selecione **Convidado**.</span><span class="sxs-lookup"><span data-stu-id="0dcaf-115">In **Select the user/license type you want to configure**, select **Guest**.</span></span>
   
    ![A captura de tela do complemento do Microsoft Teams mostra a licença de Convidado selecionada e a opção do Microsoft Teams definida para Habilitado.](media/92aabda5-431c-4fdd-803e-5ab49290f4f7.png)
      

  
  
5. <span data-ttu-id="0dcaf-117">Clique ou toque no botão de alternância ao lado de **Tornar o Microsoft Teams habilitado ou desabilitado para todos os usuários desse tipo** para **Habilitar** para ativar o acesso de convidados no Teams para a sua organização e, em seguida, escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0dcaf-117">Click or tap the toggle next to **Turn Microsoft Teams on or off for all users of this type** to **On** to turn on Teams and guest access for your organization, and then choose **Save**.</span></span> 
    
  

