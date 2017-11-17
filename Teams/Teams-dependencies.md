---
title: Autorizar acesso de convidados no Microsoft Teams
author: LaithAlShamri
ms.author: laal
manager: lolaj
ms.date: 11/10/17
ms.topic: article
ms.service: msteams
description: "Gerenciar recursos e funcionalidades de acesso de convidados no Microsoft Teams por meio de quatro níveis diferentes de autorização."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 8faf2e13efb0c4c031fabea11185f1e3cdd353d1
ms.sourcegitcommit: 4a396557d51c7fb246144cd682bcf5e6a2c823be
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2017
---
<a name="authorize-guest-access-in-microsoft-teams"></a><span data-ttu-id="e45fa-103">Autorizar acesso de convidados no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e45fa-103">Manage guest access in Microsoft Teams</span></span>
===========================================

<span data-ttu-id="e45fa-104">Para atender às exigências de sua organização, você pode gerenciar os recursos e as funcionalidades de acesso de convidados no Microsoft Teams por meio de quatro níveis diferentes de autorização.</span><span class="sxs-lookup"><span data-stu-id="e45fa-104">To satisfy your organization’s requirements, you can manage Microsoft Teams guest access features and capabilities through four different levels of authorization.</span></span> <span data-ttu-id="e45fa-105">Todos os níveis de autorização são aplicáveis ao seu locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="e45fa-105">All the authorization levels apply to your Office 365 tenant.</span></span> <span data-ttu-id="e45fa-106">Cada nível de autorização controla a experiência do convidado conforme mostrado a seguir:</span><span class="sxs-lookup"><span data-stu-id="e45fa-106">Each authorization level controls the guest experience as shown below:</span></span>
- <span data-ttu-id="e45fa-107">**Azure Active Directory**: O acesso de convidados no Microsoft Teams usa a plataforma B2B (entre empresas) do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e45fa-107">**Azure Active Directory**: Guest access in Microsoft Teams relies on the Azure AD business-to-business (B2B) platform.</span></span> <span data-ttu-id="e45fa-108">Controla a experiência dos convidados no nível de diretório, locatário e aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e45fa-108">Controls the guest experience at the directory, tenant, and application level.</span></span> 
- <span data-ttu-id="e45fa-109">**Microsoft Teams**: Controla somente o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e45fa-109">**Microsoft Teams**: Controls Microsoft Teams only.</span></span> 
- <span data-ttu-id="e45fa-110">**Grupos do Office 365**: Controla a experiência dos convidados nos Grupos do Office 365 e no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e45fa-110">**Office 365 Groups**: Controls the guest experience in Office 365 Groups and Microsoft Teams.</span></span>
- <span data-ttu-id="e45fa-111">**SharePoint Online e OneDrive for Business**: Controla a experiência dos convidados no SharePoint Online, no OneDrive for Business, nos Grupos do Office 365 e no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e45fa-111">**SharePoint Online and OneDrive for Business**: Controls the guest experience in SharePoint Online, OneDrive for Business, Office 365 Groups, and Microsoft Teams.</span></span>

<span data-ttu-id="e45fa-112">Esses níveis diferentes de autorização fornecem flexibilidade para a forma como você configura o acesso de convidados para sua organização.</span><span class="sxs-lookup"><span data-stu-id="e45fa-112">These different authorization levels provide you with flexibility in how you set up guest access for your organization.</span></span> <span data-ttu-id="e45fa-113">Por exemplo, se você não deseja permitir usuários convidados em sua organização do Microsoft Teams, basta desativar o acesso de convidados no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e45fa-113">For example, if you don’t want to allow guest users in your Microsoft Teams organization, just turn off guest access in Microsoft Teams.</span></span> <span data-ttu-id="e45fa-114">Outro exemplo: Você pode habilitar o acesso de convidados no AAD, no Microsoft Teams e nos Grupos do Office 365, mas depois desabilitar a adição de usuários convidados em equipes selecionadas que correspondam a um ou mais critérios, como classificação de dados correspondente à confidencial.</span><span class="sxs-lookup"><span data-stu-id="e45fa-114">Another example: You could enable guest access at the AAD, Teams, and Groups levels, but then disable guest users' addition on selected teams that match one or more criteria such as data classification equals confidential.</span></span> <span data-ttu-id="e45fa-115">E, talvez, você não use os Grupos do Office 365.</span><span class="sxs-lookup"><span data-stu-id="e45fa-115">And, perhaps you don’t use Office 365 Groups.</span></span> <span data-ttu-id="e45fa-116">O SharePoint Online e o OneDrive for Business têm suas próprias configurações de acesso de convidados que não dependem dos Grupos do Office 365.</span><span class="sxs-lookup"><span data-stu-id="e45fa-116">SharePoint Online and OneDrive for Business have their own guest access settings that don't rely on Office 365 Groups.</span></span> 

> [!NOTE]
> <span data-ttu-id="e45fa-117">Os convidados estão sujeitos aos limites de serviço do [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) e do [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).</span><span class="sxs-lookup"><span data-stu-id="e45fa-117">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span> 

  <span data-ttu-id="e45fa-118">O diagrama a seguir mostra como a dependência de autorização de acesso de convidados é concedida e integrada entre o Azure Active Directory, o Microsoft Teams e o Office 365.</span><span class="sxs-lookup"><span data-stu-id="e45fa-118">The following diagram shows how guest access authorization dependency is granted and integrated between Azure Active Directory, Microsoft Teams, and Office 365.</span></span>


![Diagrama de dependências de autorização para acesso de convidados.](media/teams_dependencies_image1.png)


##<a name="azure-active-directory"></a><span data-ttu-id="e45fa-120">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e45fa-120">Azure Active Directory</span></span>

<span data-ttu-id="e45fa-121">Com a colaboração B2B do Azure AD, o envio de convites para usuários convidados potenciais não é restrito aos administradores de locatários.</span><span class="sxs-lookup"><span data-stu-id="e45fa-121">With Azure AD business-to-business (B2B) collaboration, sending invitations to potential guest users isn’t restricted to tenant admins.</span></span> <span data-ttu-id="e45fa-122">Em vez disso, você pode usar políticas para delegar o envio de convites a usuários cujas funções permitem o envio de convites.</span><span class="sxs-lookup"><span data-stu-id="e45fa-122">Instead, you can use policies to delegate sending invitations to users whose roles allow them to send invitations.</span></span>

<span data-ttu-id="e45fa-123">As configurações de convites são aplicáveis no nível do locatário e controlam a experiência dos convidados no nível de diretório, locatário e aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e45fa-123">The settings for invitations apply at the tenant level and control the guest experience at the directory, tenant, and application level.</span></span>


![Captura de tela das Configurações do usuário no portal do Azure Active Directory.](media/teams_dependencies_image2.png)


<span data-ttu-id="e45fa-125">Você pode definir as seguintes políticas de convite:</span><span class="sxs-lookup"><span data-stu-id="e45fa-125">You can set the following parameters:</span></span>
- <span data-ttu-id="e45fa-126">Desativar convites.</span><span class="sxs-lookup"><span data-stu-id="e45fa-126">Turn off invitations.</span></span>
- <span data-ttu-id="e45fa-127">Somente administradores e usuários com a função de emissor de convite para convidados podem convidar.</span><span class="sxs-lookup"><span data-stu-id="e45fa-127">Only admins and users in the guest inviter role can invite.</span></span>
- <span data-ttu-id="e45fa-128">Administradores, usuários com função de emissor de convite para convidados e membros podem convidar.</span><span class="sxs-lookup"><span data-stu-id="e45fa-128">Admins, the guest inviter role, and members can invite.</span></span>
- <span data-ttu-id="e45fa-129">Todos os usuários, incluindo convidados, podem convidar.</span><span class="sxs-lookup"><span data-stu-id="e45fa-129">All users, including guests, can invite.</span></span> <span data-ttu-id="e45fa-130">(Esta é a política padrão para os locatários.)</span><span class="sxs-lookup"><span data-stu-id="e45fa-130">(This is the default policy for tenants.)</span></span>


##<a name="microsoft-teams"></a><span data-ttu-id="e45fa-131">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e45fa-131">Microsoft Teams</span></span>

<span data-ttu-id="e45fa-132">No Microsoft Teams, você pode controlar se a experiência do convidado será habilitada ou desabilitada para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="e45fa-132">In Microsoft Teams, you can control whether the guest experience is enabled or disabled for your organization.</span></span> <span data-ttu-id="e45fa-133">A configuração é desabilitada por padrão e é aplicável no nível do locatário somente no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e45fa-133">The setting is disabled by default and applies at the tenant level for Microsoft Teams only.</span></span>



<span data-ttu-id="e45fa-134">Você pode gerenciar as configurações de acesso de convidados do Microsoft Teams no Centro de administração do Office 365.</span><span class="sxs-lookup"><span data-stu-id="e45fa-134">You can manage Microsoft Teams guest access settings from the Office 365 admin center.</span></span> <span data-ttu-id="e45fa-135">Para obter mais detalhes, consulte [Habilitar ou desabilitar o acesso de convidados no Microsoft Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="e45fa-135">For more details, see "Turn on or off guest access for Microsoft Teams."</span></span> 


##<a name="office-365-groups"></a><span data-ttu-id="e45fa-136">Grupos do Office 365</span><span class="sxs-lookup"><span data-stu-id="e45fa-136">Office 365 groups</span></span>

<span data-ttu-id="e45fa-137">Nos Grupos do Office 365, você pode controlar a adição de usuários convidados e o acesso de convidados a todos os grupos do Office 365 e ao Microsoft Teams em sua organização.</span><span class="sxs-lookup"><span data-stu-id="e45fa-137">From Office 365 Groups, you can control adding guest users and guest access to all Office 365 groups and Microsoft Teams in your organization.</span></span>

1. <span data-ttu-id="e45fa-138">Inicie sessão na sua conta de administrador global do Office 365 em [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="e45fa-138">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="e45fa-139">No menu de navegação, escolha **Configurações** e, em seguida, selecione **Serviços &amp; complementos**.</span><span class="sxs-lookup"><span data-stu-id="e45fa-139">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
  
3. <span data-ttu-id="e45fa-140">Selecione **Grupos do Office 365**.</span><span class="sxs-lookup"><span data-stu-id="e45fa-140">Select **Office 365 Groups**.</span></span>
    
     ![Grupos do Office 365](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  

  

  
4. <span data-ttu-id="e45fa-142">Na página de grupos do Office 365, selecione o botão de alternância para **Habilitar** ou **Desabilitar**, dependendo se desejar permitir que os proprietários de equipes e de grupos de fora de sua organização acessem os grupos do Office 365.</span><span class="sxs-lookup"><span data-stu-id="e45fa-142">On the Office 365 Groups page, set the toggle to **On** or **Off**, depending if you want to let team and group owners outside your organization access Office 365 groups.</span></span> <span data-ttu-id="e45fa-143">Clique ou toque no botão de alternância para **Habilitar** ao lado de **Permitir que proprietários de grupos adicionem aos grupos pessoas externas à organização**.</span><span class="sxs-lookup"><span data-stu-id="e45fa-143">Click or tap the toggle to **On** next to **Let group owners add people outside the organization to groups**.</span></span> <span data-ttu-id="e45fa-144">Se você definir este botão de alternância como Ativar, verá outra opção para permitir ou não que os proprietários de grupos e equipes adicionem pessoas fora de sua organização aos Grupos do Office 365 e ao Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e45fa-144">If you turn this toggle to On, you'll see another option to control whether you want to let group and team owners add people outside your organization to Office 365 groups and Microsoft teams.</span></span> <span data-ttu-id="e45fa-145">Defina este botão de alternância como Ativar, se você deseja permitir que proprietários de grupos e equipes adicionem usuários convidados.</span><span class="sxs-lookup"><span data-stu-id="e45fa-145">Set this toggle to On if you want to let group and team owners add guest users.</span></span> <span data-ttu-id="e45fa-146">![A captura de tela mostra o painel de Grupos do Office 365 com as opções habilitadas para permitir que membros de grupo de fora da organização acessem o conteúdo do grupo e para permitir que proprietários de grupos adicionem aos grupos pessoas externas à organização.](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)</span><span class="sxs-lookup"><span data-stu-id="e45fa-146">![Screenshot shows the Office 365 Groups panel with the options turned on to let group members outside the organization access group content and to let group owners add people outside the organization to groups.](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)</span></span>




<span data-ttu-id="e45fa-147">As configurações anteriores são aplicáveis no nível de locatário e controlam a experiência dos convidados nos Grupos do Office 365 e no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e45fa-147">The above settings apply at the tenant level and control the guest experience in Office 365 Groups and Microsoft Teams.</span></span>


##<a name="sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="e45fa-148">SharePoint Online e OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="e45fa-148">See How SharePoint Online and OneDrive for Business interact with Teams</span></span>

<span data-ttu-id="e45fa-149">O Teams depende do SharePoint Online e do OneDrive for Business para armazenar arquivos e documentos para canais e conversas de bate-papo.</span><span class="sxs-lookup"><span data-stu-id="e45fa-149">Teams relies on SharePoint Online and OneDrive for Business to store files and documents for channels and chat conversations.</span></span>  
  
    
    
<span data-ttu-id="e45fa-150">Para habilitar a experiência completa de acesso de convidados no Teams, os administradores do Office 365 precisam selecionar **Habilitar** nas seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="e45fa-150">To enable the full Teams guest access experience, Office 365 admins need to select **On** for the following settings:</span></span>
  
    
    

- <span data-ttu-id="e45fa-151">No SharePoint Online: **Permitir apenas compartilhamento com usuários externos já constantes do diretório**</span><span class="sxs-lookup"><span data-stu-id="e45fa-151">In SharePoint Online: **Only allow sharing with external users already in the directory**</span></span>
    
    <span data-ttu-id="e45fa-152">Para obter mais informações, consulte [Gerenciar compartilhamento externo para o seu ambiente do SharePoint Online](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85).</span><span class="sxs-lookup"><span data-stu-id="e45fa-152">For more information, see [Manage external sharing for your SharePoint Online environment](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85).</span></span>
    
  
- <span data-ttu-id="e45fa-153">Nos grupos do Office 365: **Permitir que proprietários de grupos adicionem aos grupos pessoas externas à organização**</span><span class="sxs-lookup"><span data-stu-id="e45fa-153">In Office 365 groups: **Let group owners add people outside the organization to groups**</span></span>
    
    <span data-ttu-id="e45fa-154">Para obter mais informações, consulte [Controle do acesso de convidados no Microsoft Teams](#controlguest).</span><span class="sxs-lookup"><span data-stu-id="e45fa-154">For more information, see [Control guest access to Microsoft Teams](#controlguest).</span></span>
  

<span data-ttu-id="e45fa-155">As configurações anteriores são aplicáveis no nível de locatário e controlam a experiência dos convidados no SharePoint Online, no OneDrive for Business, nos Grupos do Office 365 e no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e45fa-155">The above settings apply at the tenant level and control the guest experience at SharePoint Online, OneDrive for Business, Office 365 Groups and Microsoft Teams.</span></span>


<span data-ttu-id="e45fa-156">Você pode gerenciar as configurações de usuário externo do SharePoint Online para o site de equipe conectado ao Teams.</span><span class="sxs-lookup"><span data-stu-id="e45fa-156">You can manage SharePoint Online external user settings for the Teams connected team site.</span></span> <span data-ttu-id="e45fa-157">Para obter mais detalhes, veja [Gerenciar as configurações do site da sua equipe do SharePoint](https://support.office.com/en-us/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span><span class="sxs-lookup"><span data-stu-id="e45fa-157">For more details, see  [Manage your SharePoint team site settings](https://support.office.com/en-us/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span></span>