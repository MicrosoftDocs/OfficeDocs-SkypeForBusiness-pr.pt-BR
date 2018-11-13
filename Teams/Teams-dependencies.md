---
title: Autorizar acesso de convidados no Microsoft Teams
author: lolaj
ms.author: sbhatta
manager: serdars
ms.date: 11/10/17
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: sbhatta
search.appverid: MET150
description: Gerenciar recursos e funcionalidades de acesso de convidados no Microsoft Teams por meio de quatro níveis diferentes de autorização.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f5b0acd36c83f59b1883115a76d6295e1e9cb454
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26293635"
---
<a name="authorize-guest-access-in-microsoft-teams"></a><span data-ttu-id="397f7-103">Autorizar acesso de convidados no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="397f7-103">Authorize guest access in Microsoft Teams</span></span>
===========================================

<span data-ttu-id="397f7-104">Para atender às exigências de sua organização, você pode gerenciar os recursos e as funcionalidades de acesso de convidados no Microsoft Teams por meio de quatro níveis diferentes de autorização.</span><span class="sxs-lookup"><span data-stu-id="397f7-104">To satisfy your organization’s requirements, you can manage Microsoft Teams guest access features and capabilities through four different levels of authorization.</span></span> <span data-ttu-id="397f7-105">Todos os níveis de autorização são aplicáveis ao seu locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="397f7-105">All the authorization levels apply to your Office 365 tenant.</span></span> <span data-ttu-id="397f7-106">Cada nível de autorização controla a experiência do convidado conforme mostrado a seguir:</span><span class="sxs-lookup"><span data-stu-id="397f7-106">Each authorization level controls the guest experience as shown below:</span></span>
- <span data-ttu-id="397f7-107">**Azure Active Directory**: O acesso de convidados no Microsoft Teams usa a plataforma B2B (entre empresas) do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="397f7-107">**Azure Active Directory**: Guest access in Microsoft Teams relies on the Azure AD business-to-business (B2B) platform.</span></span> <span data-ttu-id="397f7-108">Controla a experiência dos convidados no nível de diretório, locatário e aplicativo.</span><span class="sxs-lookup"><span data-stu-id="397f7-108">Controls the guest experience at the directory, tenant, and application level.</span></span> 
- <span data-ttu-id="397f7-109">**Microsoft Teams**: Controla somente o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="397f7-109">**Microsoft Teams**: Controls Microsoft Teams only.</span></span> 
- <span data-ttu-id="397f7-110">**Grupos do Office 365**: Controla a experiência dos convidados nos Grupos do Office 365 e no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="397f7-110">**Office 365 Groups**: Controls the guest experience in Office 365 Groups and Microsoft Teams.</span></span>
- <span data-ttu-id="397f7-111">**SharePoint Online e OneDrive for Business**: Controla a experiência dos convidados no SharePoint Online, no OneDrive for Business, nos Grupos do Office 365 e no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="397f7-111">**SharePoint Online and OneDrive for Business**: Controls the guest experience in SharePoint Online, OneDrive for Business, Office 365 Groups, and Microsoft Teams.</span></span>

<span data-ttu-id="397f7-112">Esses níveis diferentes de autorização fornecem flexibilidade para a forma como você configura o acesso de convidados para sua organização.</span><span class="sxs-lookup"><span data-stu-id="397f7-112">These different authorization levels provide you with flexibility in how you set up guest access for your organization.</span></span> <span data-ttu-id="397f7-113">Por exemplo, se você não deseja permitir usuários convidados em sua organização do Microsoft Teams, basta desativar o acesso de convidados no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="397f7-113">For example, if you don’t want to allow guest users in your Microsoft Teams organization, just turn off guest access in Microsoft Teams.</span></span> <span data-ttu-id="397f7-114">Outro exemplo: Você pode habilitar o acesso de convidados no AAD, no Microsoft Teams e nos Grupos do Office 365, mas depois desabilitar a adição de usuários convidados em equipes selecionadas que correspondam a um ou mais critérios, como classificação de dados correspondente à confidencial.</span><span class="sxs-lookup"><span data-stu-id="397f7-114">Another example: You could enable guest access at the AAD, Teams, and Groups levels, but then disable guest users' addition on selected teams that match one or more criteria such as data classification equals confidential.</span></span> <span data-ttu-id="397f7-115">E, talvez, você não use os Grupos do Office 365.</span><span class="sxs-lookup"><span data-stu-id="397f7-115">And, perhaps you don’t use Office 365 Groups.</span></span> <span data-ttu-id="397f7-116">O SharePoint Online e o OneDrive for Business têm suas próprias configurações de acesso de convidados que não dependem dos Grupos do Office 365.</span><span class="sxs-lookup"><span data-stu-id="397f7-116">SharePoint Online and OneDrive for Business have their own guest access settings that don't rely on Office 365 Groups.</span></span> 

> [!NOTE]
> <span data-ttu-id="397f7-117">Os convidados estão sujeitos aos limites de serviço do [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) e do [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).</span><span class="sxs-lookup"><span data-stu-id="397f7-117">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span> 

  <span data-ttu-id="397f7-118">O diagrama a seguir mostra como a dependência de autorização de acesso de convidados é concedida e integrada entre o Azure Active Directory, o Microsoft Teams e o Office 365.</span><span class="sxs-lookup"><span data-stu-id="397f7-118">The following diagram shows how guest access authorization dependency is granted and integrated between Azure Active Directory, Microsoft Teams, and Office 365.</span></span>


![Diagrama de dependências de autorização para acesso de convidados.](media/teams_dependencies_image1.png)


## <a name="azure-active-directory"></a><span data-ttu-id="397f7-120">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="397f7-120">Azure Active Directory</span></span>

<span data-ttu-id="397f7-121">Com a colaboração B2B do Azure AD, o envio de convites para usuários convidados potenciais não é restrito aos administradores de locatários.</span><span class="sxs-lookup"><span data-stu-id="397f7-121">With Azure AD business-to-business (B2B) collaboration, sending invitations to potential guest users isn’t restricted to tenant admins.</span></span> <span data-ttu-id="397f7-122">Em vez disso, você pode usar políticas para delegar o envio de convites a usuários cujas funções permitem o envio de convites.</span><span class="sxs-lookup"><span data-stu-id="397f7-122">Instead, you can use policies to delegate sending invitations to users whose roles allow them to send invitations.</span></span>

<span data-ttu-id="397f7-123">As configurações de convites são aplicáveis no nível do locatário e controlam a experiência dos convidados no nível de diretório, locatário e aplicativo.</span><span class="sxs-lookup"><span data-stu-id="397f7-123">The settings for invitations apply at the tenant level and control the guest experience at the directory, tenant, and application level.</span></span> <span data-ttu-id="397f7-124">No mínimo para dar suporte a convidados, **os membros podem convidar** deve ser definida como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="397f7-124">At a minimum to support guests, **Members can invite** must be set to **Yes**.</span></span>


![Captura de tela das Configurações do usuário no portal do Azure Active Directory.](media/teams_dependencies_image2.png)

<span data-ttu-id="397f7-126">Azure AD inclui as configurações a seguir para configurar usuários externos:</span><span class="sxs-lookup"><span data-stu-id="397f7-126">Azure AD includes the following settings to configure external users:</span></span>
- <span data-ttu-id="397f7-127">**Permissões de usuário convidado estão limitadas**: **Sim** , significa que os convidados não têm permissão para determinadas tarefas de diretório, como enumerar os usuários, grupos ou outros recursos de diretório.</span><span class="sxs-lookup"><span data-stu-id="397f7-127">**Guest user permissions are limited**: **Yes** means that guests don't have permission for certain directory tasks, such as enumerate users, groups, or other directory resources.</span></span> <span data-ttu-id="397f7-128">Além disso, os convidados não podem ser atribuídos às funções administrativas em seu diretório.</span><span class="sxs-lookup"><span data-stu-id="397f7-128">In addition, guests can't be assigned to administrative roles in your directory.</span></span> <span data-ttu-id="397f7-129">**Não** significa que os clientes por ter o mesmo acesso aos dados de diretório que usuários regulares tem em seu diretório.</span><span class="sxs-lookup"><span data-stu-id="397f7-129">**No** means that guests have the same access to directory data that regular users have in your directory.</span></span>
- <span data-ttu-id="397f7-130">**Administradores e usuários à função do autor do convite convidado podem convidar**: **Sim** , significa que a administradores e usuários à função de "Convidado quem convida" será capazes de convidar as pessoas para o inquilino.</span><span class="sxs-lookup"><span data-stu-id="397f7-130">**Admins and users in the guest inviter role can invite**: **Yes** means that admins and users in the "Guest Inviter" role will be able to invite guests to the tenant.</span></span> <span data-ttu-id="397f7-131">**Não** significa que os administradores e os usuários não podem convidar as pessoas para o inquilino.</span><span class="sxs-lookup"><span data-stu-id="397f7-131">**No** means admins and users can't invite guests to the tenant.</span></span>
- <span data-ttu-id="397f7-132">**Os membros podem convidar**: **Sim** , significa que não seja o administrador membros de seu diretório podem convidar as pessoas para colaborar nos recursos protegidos por sua Azure AD, como sites do SharePoint ou recursos do Windows Azure.</span><span class="sxs-lookup"><span data-stu-id="397f7-132">**Members can invite**: **Yes** means that non-admin members of your directory can invite guests to collaborate on resources secured by your Azure AD, such as SharePoint sites or Azure resources.</span></span> <span data-ttu-id="397f7-133">**Não** significa que somente os administradores podem convidar clientes por ao seu diretório.</span><span class="sxs-lookup"><span data-stu-id="397f7-133">**No** means that only admins can invite guests to your directory.</span></span>
- <span data-ttu-id="397f7-134">**Convidados podem convidar**: **Sim** significa que convidados em seu diretório, sozinhos, podem convidar outro convidado para colaborar nos recursos protegidos por sua Azure AD, como sites do SharePoint ou recursos do Windows Azure.</span><span class="sxs-lookup"><span data-stu-id="397f7-134">**Guests can invite**: **Yes** means that guests in your directory can themselves invite other guest to collaborate on resources secured by your Azure AD, such as SharePoint sites or Azure resources.</span></span> <span data-ttu-id="397f7-135">**Não** significa que os clientes por não pode convidar outros convidados para colaborar com sua organização.</span><span class="sxs-lookup"><span data-stu-id="397f7-135">**No** means that guests can't invite other guests to collaborate with your organization.</span></span>
 


> [!NOTE]
> <span data-ttu-id="397f7-136">Também é possível gerenciar quais domínios podem ser convidados para seu locatário como convidados.</span><span class="sxs-lookup"><span data-stu-id="397f7-136">You can also manage which domains can be invited into your tenant as guests.</span></span> <span data-ttu-id="397f7-137">Consulte [permitir/bloquear o acesso de convidado a grupos do Office 365](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="397f7-137">See [Allow/Block guest access to Office 365 groups](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups).</span></span> 

## <a name="microsoft-teams"></a><span data-ttu-id="397f7-138">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="397f7-138">Microsoft Teams</span></span>
<span data-ttu-id="397f7-139">No Microsoft Teams, você pode controlar se a experiência do convidado será habilitada ou desabilitada para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="397f7-139">In Microsoft Teams, you can control whether the guest experience is enabled or disabled for your organization.</span></span> <span data-ttu-id="397f7-140">A configuração é desabilitada por padrão e é aplicável no nível do locatário somente no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="397f7-140">The setting is disabled by default and applies at the tenant level for Microsoft Teams only.</span></span>



<span data-ttu-id="397f7-141">Você pode gerenciar as configurações de acesso de convidados do Microsoft Teams no Centro de administração do Office 365.</span><span class="sxs-lookup"><span data-stu-id="397f7-141">You can manage Microsoft Teams guest access settings from the Office 365 admin center.</span></span> <span data-ttu-id="397f7-142">Para obter mais detalhes, consulte [Habilitar ou desabilitar o acesso de convidados no Microsoft Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="397f7-142">For more information, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span> 


## <a name="office-365-groups"></a><span data-ttu-id="397f7-143">Grupos do Office 365</span><span class="sxs-lookup"><span data-stu-id="397f7-143">Office 365 Groups</span></span>

<span data-ttu-id="397f7-144">Nos Grupos do Office 365, você pode controlar a adição de usuários convidados e o acesso de convidados a todos os grupos do Office 365 e ao Microsoft Teams em sua organização.</span><span class="sxs-lookup"><span data-stu-id="397f7-144">From Office 365 Groups, you can control adding guest users and guest access to all Office 365 groups and Microsoft Teams in your organization.</span></span>

1. <span data-ttu-id="397f7-145">Entre usando sua conta de administrador global do Office 365 em [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="397f7-145">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="397f7-146">No menu de navegação, escolha **Configurações** e, em seguida, selecione **Serviços &amp; complementos**.</span><span class="sxs-lookup"><span data-stu-id="397f7-146">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
  
3. <span data-ttu-id="397f7-147">Selecione **Grupos do Office 365**.</span><span class="sxs-lookup"><span data-stu-id="397f7-147">Select **Office 365 Groups**.</span></span>
    
     ![Grupos do Office 365](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  

  

  
4. <span data-ttu-id="397f7-149">Na página de grupos do Office 365, selecione o botão de alternância para **Habilitar** ou **Desabilitar**, dependendo se desejar permitir que os proprietários de equipes e de grupos de fora de sua organização acessem os grupos do Office 365.</span><span class="sxs-lookup"><span data-stu-id="397f7-149">On the Office 365 Groups page, set the toggle to **On** or **Off**, depending if you want to let team and group owners outside your organization access Office 365 groups.</span></span> <span data-ttu-id="397f7-150">Clique ou toque no botão de alternância para **Habilitar** ao lado de **Permitir que proprietários de grupos adicionem aos grupos pessoas externas à organização**.</span><span class="sxs-lookup"><span data-stu-id="397f7-150">Click or tap the toggle to **On** next to **Let group owners add people outside the organization to groups**.</span></span> <span data-ttu-id="397f7-151">Se você definir este botão de alternância como Ativar, verá outra opção para permitir ou não que os proprietários de grupos e equipes adicionem pessoas fora de sua organização aos Grupos do Office 365 e ao Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="397f7-151">If you turn this toggle to On, you'll see another option to control whether you want to let group and team owners add people outside your organization to Office 365 groups and Microsoft teams.</span></span> <span data-ttu-id="397f7-152">Defina este botão de alternância como Ativar, se você deseja permitir que proprietários de grupos e equipes adicionem usuários convidados.</span><span class="sxs-lookup"><span data-stu-id="397f7-152">Set this toggle to On if you want to let group and team owners add guest users.</span></span> <span data-ttu-id="397f7-153">![A captura de tela mostra o painel de Grupos do Office 365 com as opções habilitadas para permitir que membros de grupo de fora da organização acessem o conteúdo do grupo e para permitir que proprietários de grupos adicionem aos grupos pessoas externas à organização.](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)</span><span class="sxs-lookup"><span data-stu-id="397f7-153">![Screenshot shows the Office 365 Groups panel with the options turned on to let group members outside the organization access group content and to let group owners add people outside the organization to groups.](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)</span></span>




<span data-ttu-id="397f7-154">As configurações anteriores são aplicáveis no nível de locatário e controlam a experiência dos convidados nos Grupos do Office 365 e no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="397f7-154">The above settings apply at the tenant level and control the guest experience in Office 365 Groups and Microsoft Teams.</span></span>


## <a name="sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="397f7-155">SharePoint Online e OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="397f7-155">SharePoint Online and OneDrive for Business</span></span>

<span data-ttu-id="397f7-156">O Teams depende do SharePoint Online e do OneDrive for Business para armazenar arquivos e documentos para canais e conversas de bate-papo.</span><span class="sxs-lookup"><span data-stu-id="397f7-156">Teams relies on SharePoint Online and OneDrive for Business to store files and documents for channels and chat conversations.</span></span>  
  
    
    
<span data-ttu-id="397f7-157">Para habilitar a experiência completa de acesso de convidados no Teams, os administradores do Office 365 precisam selecionar **Habilitar** nas seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="397f7-157">To enable the full Teams guest access experience, Office 365 admins need to select **On** for the following settings:</span></span>
  
    
    

- <span data-ttu-id="397f7-158">No SharePoint Online: **Permitir apenas compartilhamento com usuários externos já constantes do diretório**</span><span class="sxs-lookup"><span data-stu-id="397f7-158">In SharePoint Online: **Only allow sharing with external users already in the directory**</span></span>
    
    <span data-ttu-id="397f7-159">Para obter mais informações, consulte [Gerenciar compartilhamento externo para o seu ambiente do SharePoint Online](https://docs.microsoft.com/sharepoint/external-sharing-overview).</span><span class="sxs-lookup"><span data-stu-id="397f7-159">For more information, see [Manage external sharing for your SharePoint Online environment](https://docs.microsoft.com/sharepoint/external-sharing-overview).</span></span>
    
  
- <span data-ttu-id="397f7-160">Nos grupos do Office 365: **Permitir que proprietários de grupos adicionem aos grupos pessoas externas à organização**</span><span class="sxs-lookup"><span data-stu-id="397f7-160">In Office 365 groups: **Let group owners add people outside the organization to groups**</span></span>
    
    <span data-ttu-id="397f7-161">Para obter mais informações, consulte [Controle do acesso de convidados no Microsoft Teams](#controlguest).</span><span class="sxs-lookup"><span data-stu-id="397f7-161">For more information, see [Control guest access to Microsoft Teams](#controlguest).</span></span>
  

<span data-ttu-id="397f7-162">As configurações anteriores são aplicáveis no nível de locatário e controlam a experiência dos convidados no SharePoint Online, no OneDrive for Business, nos Grupos do Office 365 e no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="397f7-162">The above settings apply at the tenant level and control the guest experience at SharePoint Online, OneDrive for Business, Office 365 Groups and Microsoft Teams.</span></span>


<span data-ttu-id="397f7-163">Você pode gerenciar as configurações de usuário externo do SharePoint Online para o site de equipe conectado ao Teams.</span><span class="sxs-lookup"><span data-stu-id="397f7-163">You can manage SharePoint Online external user settings for the Teams connected team site.</span></span> <span data-ttu-id="397f7-164">Para obter mais detalhes, veja [Gerenciar as configurações do site da sua equipe do SharePoint](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span><span class="sxs-lookup"><span data-stu-id="397f7-164">For more details, see  [Manage your SharePoint team site settings](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span></span>
