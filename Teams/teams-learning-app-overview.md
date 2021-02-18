---
title: Instalar, gerenciar e atribuir permissões para o aplicativo Teams Learning (visualização privada)
author: ChuckEdmonson
ms.author: chucked
manager: pamgreenMSFT
ms.date: ''
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ChrisArnoldMSFT, LearningDocs2020
localization_priority: Normal
search.appverid: ''
ms.collection: ''
description: Use o aplicativo Microsoft Teams Learning para criar um hub central para aprender onde os funcionários podem compartilhar, atribuir e aprender com bibliotecas de conteúdo em toda a organização.
f1.keywords: ''
appliesto:
- Microsoft Teams
ms.custom: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 6dd82c786c30fb4f2ac2ae70f2df6810cfe5d6ad
ms.sourcegitcommit: 75d710e3858f79ef601cd92e435a4a29dae0aba0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50285615"
---
# <a name="install-manage-and-assign-permissions-for-the-teams-learning-app-private-preview"></a><span data-ttu-id="0c769-103">Instalar, gerenciar e atribuir permissões para o aplicativo Teams Learning (visualização privada)</span><span class="sxs-lookup"><span data-stu-id="0c769-103">Install, manage, and assign permissions for the Teams Learning app (private preview)</span></span>

<span data-ttu-id="0c769-104">*Este artigo contém conteúdo preliminar para o aplicativo Teams Learning, que está em visualização privada.*</span><span class="sxs-lookup"><span data-stu-id="0c769-104">*This article contains preliminary content for the Teams Learning app, which is in private preview.*</span></span>

<span data-ttu-id="0c769-105">O aplicativo Microsoft Teams Learning (visualização privada) capacita equipes e indivíduos em sua organização a tornar o aprendizado uma parte natural do seu dia.</span><span class="sxs-lookup"><span data-stu-id="0c769-105">The Microsoft Teams Learning app (private preview) empowers teams and individuals in your organization to make learning a natural part of their day.</span></span> <span data-ttu-id="0c769-106">O aplicativo cria um hub central no Teams onde os funcionários podem compartilhar, atribuir e aprender com bibliotecas de conteúdo em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="0c769-106">The app creates a central hub in Teams where employees can share, assign, and learn from content libraries across your organization.</span></span> <span data-ttu-id="0c769-107">Os administradores configuram permissões e permitem fontes de conteúdo de aprendizagem para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0c769-107">Admins set permissions and allow learning content sources for the app.</span></span> <span data-ttu-id="0c769-108">O conteúdo de aprendizagem pode incluir o LinkedIn Learning, o Microsoft Learn, o treinamento do Microsoft 365, o próprio conteúdo armazenado no SharePoint Online e provedores de terceiros que são suportados pelo aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0c769-108">Learning content can include LinkedIn Learning, Microsoft Learn, Microsoft 365 training, your organization's own content stored in SharePoint online, and third-party providers that are supported by the app.</span></span>

<span data-ttu-id="0c769-109">Para configurar o aplicativo Teams Learning (visualização privada), você precisará envolver:</span><span class="sxs-lookup"><span data-stu-id="0c769-109">To set up the Teams Learning app (private preview), you'll need to involve:</span></span>

-   <span data-ttu-id="0c769-110">Administrador do centro de administração do Teams</span><span class="sxs-lookup"><span data-stu-id="0c769-110">Teams admin center admin</span></span>
-   <span data-ttu-id="0c769-111">Administrador do Centro de administração do Microsoft 365 (ou seja, um administrador global)</span><span class="sxs-lookup"><span data-stu-id="0c769-111">Microsoft 365 admin center admin (that is, a global admin)</span></span>

## <a name="manage-the-teams-learning-app-private-preview-in-the-teams-admin-center"></a><span data-ttu-id="0c769-112">Gerenciar o aplicativo Teams Learning (visualização privada) no Centro de administração do Teams</span><span class="sxs-lookup"><span data-stu-id="0c769-112">Manage the Teams Learning app (private preview) in the Teams admin center</span></span>

<span data-ttu-id="0c769-113">O administrador do Teams instala o aplicativo Teams Learning (visualização privada) na loja de aplicativos e aplica políticas de configuração, gerenciamento e permissões de aplicativos por meio do Centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="0c769-113">The Teams admin installs the Teams Learning app (private preview) from the app store and applies app setup, manage, and permissions policies through the Teams admin center.</span></span>

### <a name="manage-the-teams-learning-app-private-preview"></a><span data-ttu-id="0c769-114">Gerenciar o aplicativo Teams Learning (visualização privada)</span><span class="sxs-lookup"><span data-stu-id="0c769-114">Manage the Teams Learning app (private preview)</span></span>

<span data-ttu-id="0c769-115">Para gerenciar as configurações do aplicativo, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="0c769-115">To manage settings for app, follow these steps:</span></span>

1. <span data-ttu-id="0c769-116">Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para Os **aplicativos do Teams**  >  **Gerenciar aplicativos.**</span><span class="sxs-lookup"><span data-stu-id="0c769-116">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![Navegação à esquerda no Centro de administração do Teams mostrando os aplicativos do Teams e a seção Gerenciar aplicativos](media/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="0c769-118">Na página **Gerenciar aplicativos,** na  caixa de pesquisa, digite o aprendizado para pesquisar o aplicativo Teams Learning (visualização privada).</span><span class="sxs-lookup"><span data-stu-id="0c769-118">On the **Manage apps** page, in the search box, type *learning* to search for the Teams Learning app (private preview).</span></span>

   ![Página Gerenciar aplicativos no Centro de administração do Teams mostrando a caixa de pesquisa](media/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="0c769-120">Na página **Aprendizagem:**</span><span class="sxs-lookup"><span data-stu-id="0c769-120">On the **Learning** page:</span></span>
   1. <span data-ttu-id="0c769-121">Em **Status,** selecione **Permitido** ativar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0c769-121">Under **Status**, select **Allowed** to turn on the app.</span></span>
   2. <span data-ttu-id="0c769-122">Na guia **Configurações,** na **seção** configurações do aplicativo, vá para o Centro de administração do Microsoft 365 para configurar fontes de conteúdo de aprendizagem.</span><span class="sxs-lookup"><span data-stu-id="0c769-122">On the **Settings** tab, in the **App settings** section, go to the Microsoft 365 admin center to configure learning content sources.</span></span>

   ![Página de aprendizagem no Centro de administração do Teams mostrando a seção De status e configurações do aplicativo](media/learning-app-teams-learning-page.png)

4. <span data-ttu-id="0c769-124">Depois **de gerenciar** as configurações do aplicativo, vá para Permissões e Configurar políticas para conceder permissão aos **funcionários** que devem ter acesso ao aplicativo como parte da participação da sua organização na visualização privada.</span><span class="sxs-lookup"><span data-stu-id="0c769-124">After **Manage app** settings, go to **Permissions and Set-up policies** to grant permission to employees who should have access to the app as part of your organization's participation in the private preview.</span></span>

> [!NOTE]
>  <span data-ttu-id="0c769-125">Se sua organização estiver no Ring 4.0 como parte do programa Teams TAP100, talvez seja necessário fazer o seguinte para habilitar os usuários aprovados no Ring 3.0 para acessar o aplicativo Teams Learning (visualização privada).</span><span class="sxs-lookup"><span data-stu-id="0c769-125">If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to do the following to enable approved users in Ring 3.0 to access the Teams Learning app (private preview).</span></span>

<span data-ttu-id="0c769-126">Como parte da visualização privada, o aplicativo Teams Learning (visualização privada) é lançado no Ring 3.0.</span><span class="sxs-lookup"><span data-stu-id="0c769-126">As part of private preview, the Teams Learning app (private preview) is released in Ring 3.0.</span></span> <span data-ttu-id="0c769-127">Se sua organização estiver no Ring 4.0, você não verá o aplicativo na loja de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="0c769-127">If your organization is in Ring 4.0, you won’t see the app in the app store.</span></span> <span data-ttu-id="0c769-128">Para testar o aplicativo, você precisa criar uma política de permissão de aplicativos personalizados, defini-la como Permitir todos os aplicativos e atribuí-la aos usuários aprovados do Ring 3.0.</span><span class="sxs-lookup"><span data-stu-id="0c769-128">To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users.</span></span>

   ![Página TAP-AppsPermission-Plcy mostrando Permitir todos os aplicativos selecionados](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a><span data-ttu-id="0c769-130">Configurar fontes de conteúdo de aprendizagem no Centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0c769-130">Configure learning content sources in the Microsoft 365 admin center</span></span>

<span data-ttu-id="0c769-131">Os administradores do Centro de administração do Microsoft 365 podem gerenciar as configurações relacionadas ao aplicativo Teams Learning (visualização privada) e podem configurar as fontes de conteúdo de aprendizagem.</span><span class="sxs-lookup"><span data-stu-id="0c769-131">The admins for the Microsoft 365 admin center can manage settings related to the Teams Learning app (private preview) and can configure the learning content sources.</span></span>

<span data-ttu-id="0c769-132">O administrador pode selecionar quais fontes de conteúdo de aprendizagem adicionais (por exemplo, o SharePoint ou fontes de provedores de conteúdo de terceiros) estarão disponíveis para os usuários do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0c769-132">The admin can select which additional learning content sources (for example, SharePoint or supported third-party content provider sources) will be available to users of the app.</span></span> <span data-ttu-id="0c769-133">Em seguida, o administrador configura essas fontes para garantir que o conteúdo está disponível para pesquisa e descoberta e pode ser navegado pelos funcionários que usam o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0c769-133">The admin then configures those sources to make sure the content is available for search and discovery and can be browsed by the employees who use the app.</span></span>

> [!NOTE]
>  <span data-ttu-id="0c769-134">Os usuários entrarão em aprendizados que não são da Microsoft e do LinkedIn Learning Pro em um navegador ou visualizador inserido.</span><span class="sxs-lookup"><span data-stu-id="0c769-134">Users sign in to non-Microsoft and LinkedIn Learning Pro learnings in a browser or embedded viewer.</span></span> <span data-ttu-id="0c769-135">Esse aprendizado configurado está sujeito à licença, privacidade e termos de serviço separados entre sua organização e o terceiro, e não aos termos de Aprendizagem (Visualização).</span><span class="sxs-lookup"><span data-stu-id="0c769-135">This configured learning is subject to the separate license, privacy and service terms between your organization and the third party, and not the Learning (Preview) terms.</span></span> <span data-ttu-id="0c769-136">Antes de selecionar esse aprendizado em Aprendizagem (Visualização), verifique se você tem um contrato em uso para sua organização e usuários.</span><span class="sxs-lookup"><span data-stu-id="0c769-136">Before selecting this learning in Learning (Preview), verify you have an agreement in place for your organization and users.</span></span>

### <a name="configure-settings-for-the-learning-content-sources-for-the-app"></a><span data-ttu-id="0c769-137">Definir configurações para as fontes de conteúdo de aprendizagem do aplicativo</span><span class="sxs-lookup"><span data-stu-id="0c769-137">Configure settings for the learning content sources for the app</span></span>

<span data-ttu-id="0c769-138">Estas etapas devem ser executadas pelo administrador do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0c769-138">These steps are to be performed by the Microsoft 365 admin.</span></span>

1.  <span data-ttu-id="0c769-139">Na navegação à esquerda do Centro de administração do Microsoft 365, vá para **Configurações**  >  **da Organização.**</span><span class="sxs-lookup"><span data-stu-id="0c769-139">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>

2.  <span data-ttu-id="0c769-140">Na página **Configurações,** na guia Serviços **& de complementos,** selecione **Aplicativo De aprendizagem.**</span><span class="sxs-lookup"><span data-stu-id="0c769-140">On the **Settings** page, on the **Services & add-ins** tab, select **Learning app**.</span></span>

   ![Página configurações no Centro de administração do Microsoft 365 mostrando o aplicativo De aprendizagem listado](media/learning-app-365-settings-page.png)

3.  <span data-ttu-id="0c769-142">No painel **do aplicativo Aprendizagem,** selecione as fontes de conteúdo de aprendizagem que você deseja configurar para a organização e, em seguida, **selecione Salvar.**</span><span class="sxs-lookup"><span data-stu-id="0c769-142">On the **Learning app** panel, select the learning content sources you want to configure for the organization, and then select **Save**.</span></span>

   ![Painel de aplicativos de aprendizagem no Centro de administração do Microsoft 365 mostrando opções de fontes de conteúdo](media/learning-app-365-settings-learning-app-panel.png)

<span data-ttu-id="0c769-144">Entre todas as fontes de aprendizagem existentes, algumas serão habilitadas por padrão.</span><span class="sxs-lookup"><span data-stu-id="0c769-144">Among all the learning sources that exist, some will be enabled by default.</span></span> <span data-ttu-id="0c769-145">Elas incluem:</span><span class="sxs-lookup"><span data-stu-id="0c769-145">These include:</span></span>

- <span data-ttu-id="0c769-146">LinkedIn Learning (conteúdo gratuito)</span><span class="sxs-lookup"><span data-stu-id="0c769-146">LinkedIn Learning (free content)</span></span>
- <span data-ttu-id="0c769-147">Microsoft Learn</span><span class="sxs-lookup"><span data-stu-id="0c769-147">Microsoft Learn</span></span>
- <span data-ttu-id="0c769-148">Treinamento do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0c769-148">Microsoft 365 Training</span></span>

> [!NOTE]
> <span data-ttu-id="0c769-149">Se sua organização tiver uma assinatura do LinkedIn Learning Standard ou Pro, o repositório de conteúdo será desbloqueado para os funcionários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="0c769-149">If your organization has a LinkedIn Learning Standard or Pro subscription, the content repository will be unlocked for the employees in your organization.</span></span> <span data-ttu-id="0c769-150">Somente os funcionários que têm permissão poderão usar todo o repositório de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="0c769-150">Only those employees who have permission will be able to use the entire content repository.</span></span>

<span data-ttu-id="0c769-151">Outras fontes podem precisar ser habilitadas ou configuradas manualmente.</span><span class="sxs-lookup"><span data-stu-id="0c769-151">Other sources might need to be enabled or configured manually.</span></span> <span data-ttu-id="0c769-152">As fontes de aprendizagem que não são da Microsoft são licenciadas separadamente entre sua organização e o terceiro.</span><span class="sxs-lookup"><span data-stu-id="0c769-152">Learning sources that are not from Microsoft are separately licensed between your organization and the third party.</span></span> <span data-ttu-id="0c769-153">Você precisará verificar se se inscreveu para o aprendizado deles para você e seus usuários.</span><span class="sxs-lookup"><span data-stu-id="0c769-153">You’ll need to verify you’ve signed up for their learning for you and your users.</span></span>

<span data-ttu-id="0c769-154">Para habilitar ou desabilitar uma fonte de conteúdo de aprendizagem, marque a caixa de seleção ao lado da fonte.</span><span class="sxs-lookup"><span data-stu-id="0c769-154">To enable or disable a learning content source, select the check box next to the source.</span></span> <span data-ttu-id="0c769-155">Se uma fonte estiver habilitada, uma marca de seleção ficará visível.</span><span class="sxs-lookup"><span data-stu-id="0c769-155">If a source is enabled, a check mark will be visible.</span></span>

## <a name="configure-sharepoint-as-a-learning-content-source-coming-soon"></a><span data-ttu-id="0c769-156">Configurar o SharePoint como uma fonte de conteúdo de aprendizagem (em breve)</span><span class="sxs-lookup"><span data-stu-id="0c769-156">Configure SharePoint as a learning content source (Coming Soon)</span></span>

<span data-ttu-id="0c769-157">Configure o SharePoint como uma fonte de conteúdo de aprendizagem para o aplicativo Teams Learning (visualização privada) no Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0c769-157">You configure SharePoint as a learning content source for the Teams Learning app (private preview) in the Microsoft 365 admin center.</span></span>

### <a name="overview"></a><span data-ttu-id="0c769-158">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="0c769-158">Overview</span></span>

<span data-ttu-id="0c769-159">O administrador fornece uma URL de site para o qual o Serviço de Aprendizagem pode criar um repositório de conteúdo de aprendizagem centralizado vazio na forma de uma lista estruturada do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0c769-159">The admin provides a site URL to where the Learning Service can create an empty centralized learning content repository in the form of a structured SharePoint list.</span></span> <span data-ttu-id="0c769-160">Essa lista pode ser usada pela organização para a casa de links para pastas do SharePoint entre empresas que contêm conteúdo de aprendizagem.</span><span class="sxs-lookup"><span data-stu-id="0c769-160">This list can be used by the organization to house links to cross-company SharePoint folders that contain learning content.</span></span> <span data-ttu-id="0c769-161">Os administradores são responsáveis por coletar e criar uma lista de URLs para pastas.</span><span class="sxs-lookup"><span data-stu-id="0c769-161">Admins are responsible for collecting and curating a list of URLs for folders.</span></span> <span data-ttu-id="0c769-162">Essas pastas só devem incluir conteúdo que pode ser disponibilizado no aplicativo Teams Learning (visualização privada).</span><span class="sxs-lookup"><span data-stu-id="0c769-162">These folders should only include content that can be made available in the Teams Learning app (private preview).</span></span>

### <a name="permissions"></a><span data-ttu-id="0c769-163">Permissões</span><span class="sxs-lookup"><span data-stu-id="0c769-163">Permissions</span></span>

<span data-ttu-id="0c769-164">As URLs de pastas podem ser coletadas de qualquer site do SharePoint na organização.</span><span class="sxs-lookup"><span data-stu-id="0c769-164">Folder URLs can be collected from any SharePoint site in the organization.</span></span> <span data-ttu-id="0c769-165">Qualquer conteúdo dentro dessas pastas será pesquisável, mas somente o conteúdo ao qual o funcionário individual tem permissões pode ser usado.</span><span class="sxs-lookup"><span data-stu-id="0c769-165">Any content within these folders will be searchable, but only content to which the individual employee has permissions can be used.</span></span>
 
### <a name="learning-service"></a><span data-ttu-id="0c769-166">Serviço de Aprendizagem</span><span class="sxs-lookup"><span data-stu-id="0c769-166">Learning Service</span></span>

<span data-ttu-id="0c769-167">O Serviço de Aprendizagem usa as URLs de pasta fornecidas para obter metadados de todo o conteúdo armazenado nessas pastas.</span><span class="sxs-lookup"><span data-stu-id="0c769-167">The Learning Service uses the provided folder URLs to get metadata from all content stored in those folders.</span></span> <span data-ttu-id="0c769-168">Dentro de 24 horas após o fornecimento da URL da pasta no repositório centralizado, os funcionários podem pesquisar e usar o conteúdo da empresa no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0c769-168">Within 24 hours of supplying the folder URL in the centralized repository, employees can search for and use the company’s content within the app.</span></span> <span data-ttu-id="0c769-169">A exclusão de conteúdo do repositório não tem suporte neste momento.</span><span class="sxs-lookup"><span data-stu-id="0c769-169">Content deletion from the repository isn't supported at this point.</span></span> <span data-ttu-id="0c769-170">O conteúdo não intencionalmente superfície só pode ser removido fornecendo uma nova URL de site do SharePoint no Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0c769-170">Unintentionally surfaced content can only be removed by supplying a new SharePoint site URL in the Microsoft 365 admin center.</span></span>

### <a name="configure-sharepoint-as-a-source"></a><span data-ttu-id="0c769-171">Configurar o SharePoint como fonte</span><span class="sxs-lookup"><span data-stu-id="0c769-171">Configure SharePoint as a source</span></span>

<span data-ttu-id="0c769-172">Estas etapas devem ser executadas pelo administrador do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0c769-172">These steps are to be performed by Microsoft 365 admin.</span></span>

1.  <span data-ttu-id="0c769-173">Na navegação à esquerda do Centro de administração do Microsoft 365, vá para **Configurações.**</span><span class="sxs-lookup"><span data-stu-id="0c769-173">In the left navigation of the Microsoft 365 admin center, go to **Settings**.</span></span>
 
2.  <span data-ttu-id="0c769-174">Na página **Configurações,** na guia Serviços **& de complementos,** selecione **Aplicativo De aprendizagem.**</span><span class="sxs-lookup"><span data-stu-id="0c769-174">On the **Settings** page, on the **Services & add-ins** tab, select **Learning app**.</span></span>

   ![Página configurações no Centro de administração do Microsoft 365 mostrando o aplicativo De aprendizagem listado](media/learning-app-365-settings-page.png)

3.  <span data-ttu-id="0c769-176">No painel **do aplicativo Aprendizagem,** forneça a URL do site para o site do SharePoint onde você deseja que o aplicativo crie um repositório centralizado.</span><span class="sxs-lookup"><span data-stu-id="0c769-176">On the **Learning app** panel, provide the site URL to the SharePoint site where you want the app to create a centralized repository.</span></span>

   ![Painel de aplicativos de aprendizagem no Centro de administração do Microsoft 365 mostrando o SharePoint selecionado](media/learning-app-365-panel-sharepoint-selected.png)

4.  <span data-ttu-id="0c769-178">Uma lista do SharePoint é criada automaticamente no site do SharePoint da organização fornecida.</span><span class="sxs-lookup"><span data-stu-id="0c769-178">A SharePoint list is created automatically within the provided organization’s SharePoint site.</span></span> <span data-ttu-id="0c769-179">Na navegação à esquerda do site do SharePoint, selecione Repositório de Conteúdo do **Aplicativo de Aprendizagem.**</span><span class="sxs-lookup"><span data-stu-id="0c769-179">In the left navigation of the SharePoint site, select **Learning App Content Repository**.</span></span> 

   ![Navegação à esquerda no SharePoint mostrando a seção Repositório de Conteúdo do Aplicativo de Aprendizagem](media/learning-app-content-repository-nav.png)

 
5. <span data-ttu-id="0c769-181">Na página **Repositório de Conteúdo do** Aplicativo de Aprendizagem, preencha a lista do SharePoint com URLs para as pastas de conteúdo de aprendizagem.</span><span class="sxs-lookup"><span data-stu-id="0c769-181">On the **Learning App Content Repository** page, populate the SharePoint list with URLs to the learning content folders.</span></span>

   1.   <span data-ttu-id="0c769-182">Selecione **Novo** para exibir o **painel Novo item.**</span><span class="sxs-lookup"><span data-stu-id="0c769-182">Select **New** to view the **New item** panel.</span></span> 

   ![Página Do Repositório de Conteúdo do Aplicativo de Aprendizagem no SharePoint mostrando a nova opção](media/learning-app-content-repository-new.png)
 
   2.   <span data-ttu-id="0c769-184">No painel **Novo item,** no campo **Título,** adicione um nome de diretório de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="0c769-184">On the **New item** panel, in the **Title** field, add a directory name of your choice.</span></span> <span data-ttu-id="0c769-185">No campo **URL da** Pasta, adicione a URL à pasta de conteúdo de aprendizagem.</span><span class="sxs-lookup"><span data-stu-id="0c769-185">In the **Folder URL** field, add the URL to the learning content folder.</span></span> <span data-ttu-id="0c769-186">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0c769-186">Select **Save**.</span></span>

   ![Painel Novo item no SharePoint mostrando os campos DE URL de Título e Pasta](media/learning-app-new-item-panel.png)

   3. <span data-ttu-id="0c769-188">A página Repositório de Conteúdo do Aplicativo de Aprendizagem é atualizada com o novo conteúdo de aprendizagem.</span><span class="sxs-lookup"><span data-stu-id="0c769-188">The Learning App Content Repository page is updated with the new learning content.</span></span>

   ![Página do Repositório de Conteúdo do Aplicativo de Aprendizagem no SharePoint mostrando as informações atualizadas](media/learning-app-content-repository-populated.png)


 


