---
title: Instalar, gerenciar e atribuir permissões para o aplicativo Teams Learning (visualização particular)
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
description: Use o aplicativo Microsoft Teams Learning para criar um hub central para aprender onde os funcionários podem compartilhar, atribuir e aprender nas bibliotecas de conteúdo em toda a organização.
f1.keywords: ''
appliesto:
- Microsoft Teams
ms.custom: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a8fe0d3b4f86de34accb1519c80a391a9e395fbe
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49703395"
---
# <a name="install-manage-and-assign-permissions-for-the-teams-learning-app-private-preview"></a><span data-ttu-id="94c07-103">Instalar, gerenciar e atribuir permissões para o aplicativo Teams Learning (visualização particular)</span><span class="sxs-lookup"><span data-stu-id="94c07-103">Install, manage, and assign permissions for the Teams Learning app (private preview)</span></span>

<span data-ttu-id="94c07-104">*Este artigo contém conteúdo preliminar para o aplicativo Teams Learning, que está em visualização particular.*</span><span class="sxs-lookup"><span data-stu-id="94c07-104">*This article contains preliminary content for the Teams Learning app, which is in private preview.*</span></span>

<span data-ttu-id="94c07-105">O aplicativo Microsoft Teams Learning (visualização privada) permite que equipes e indivíduos em sua organização aprendam uma parte natural do dia.</span><span class="sxs-lookup"><span data-stu-id="94c07-105">The Microsoft Teams Learning app (private preview) empowers teams and individuals in your organization to make learning a natural part of their day.</span></span> <span data-ttu-id="94c07-106">O aplicativo cria um hub central no Teams em que os funcionários podem compartilhar, atribuir e aprender nas bibliotecas de conteúdo em toda a sua organização.</span><span class="sxs-lookup"><span data-stu-id="94c07-106">The app creates a central hub in Teams where employees can share, assign, and learn from content libraries across your organization.</span></span> <span data-ttu-id="94c07-107">Administradores definem permissões e permitem que as fontes de conteúdo de aprendizagem do aplicativo sejam aprendidas.</span><span class="sxs-lookup"><span data-stu-id="94c07-107">Admins set permissions and allow learning content sources for the app.</span></span> <span data-ttu-id="94c07-108">O conteúdo de aprendizagem pode incluir o LinkedIn Learning, o Microsoft learn, o treinamento do Microsoft 365, o conteúdo próprio da sua organização armazenado no SharePoint Online e provedores de terceiros que são compatíveis com o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="94c07-108">Learning content can include LinkedIn Learning, Microsoft Learn, Microsoft 365 training, your organization's own content stored in SharePoint online, and third-party providers that are supported by the app.</span></span>

<span data-ttu-id="94c07-109">Para configurar o aplicativo Teams Learning (visualização particular), você precisará envolver:</span><span class="sxs-lookup"><span data-stu-id="94c07-109">To set up the Teams Learning app (private preview), you'll need to involve:</span></span>

-   <span data-ttu-id="94c07-110">Administrador do centro de administração do teams</span><span class="sxs-lookup"><span data-stu-id="94c07-110">Teams admin center admin</span></span>
-   <span data-ttu-id="94c07-111">Administrador do centro de administração do Microsoft 365 (ou seja, um administrador global)</span><span class="sxs-lookup"><span data-stu-id="94c07-111">Microsoft 365 admin center admin (that is, a global admin)</span></span>
-   <span data-ttu-id="94c07-112">Administrador de conhecimento (uma nova função no centro de administração do Microsoft 365 que um administrador global (também conhecido como administrador de ti ou administrador do Microsoft 365) pode atribuir a qualquer pessoa na organização.</span><span class="sxs-lookup"><span data-stu-id="94c07-112">Knowledge admin (a new role in the Microsoft 365 admin center that a global admin (also known as IT admin or Microsoft 365 admin) can assign to anyone in the organization.</span></span> <span data-ttu-id="94c07-113">Esta função gerencia as fontes de conteúdo de aprendizagem da organização por meio do centro de administração do Microsoft 365.)</span><span class="sxs-lookup"><span data-stu-id="94c07-113">This role manages the organization’s learning content sources through the Microsoft 365 admin center.)</span></span> 

## <a name="manage-the-teams-learning-app-private-preview-in-the-teams-admin-center"></a><span data-ttu-id="94c07-114">Gerenciar o aplicativo Teams Learning (visualização particular) no centro de administração do teams</span><span class="sxs-lookup"><span data-stu-id="94c07-114">Manage the Teams Learning app (private preview) in the Teams admin center</span></span>

<span data-ttu-id="94c07-115">O administrador do teams instala o aplicativo Teams Learning (visualização particular) na App Store e aplica a configuração do aplicativo, gerenciar e políticas de permissões por meio do centro de administração do teams.</span><span class="sxs-lookup"><span data-stu-id="94c07-115">The Teams admin installs the Teams Learning app (private preview) from the app store and applies app setup, manage, and permissions policies through the Teams admin center.</span></span>

### <a name="manage-the-teams-learning-app-private-preview"></a><span data-ttu-id="94c07-116">Gerenciar o aplicativo Teams Learning (visualização particular)</span><span class="sxs-lookup"><span data-stu-id="94c07-116">Manage the Teams Learning app (private preview)</span></span>

<span data-ttu-id="94c07-117">Para gerenciar as configurações do aplicativo, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="94c07-117">To manage settings for app, follow these steps:</span></span>

1. <span data-ttu-id="94c07-118">Na navegação à esquerda do centro de administração do Microsoft Teams, vá até **Team apps**  >  **gerenciar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="94c07-118">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![Navegação à esquerda no centro de administração do teams mostrando a seção aplicativos Teams e gerenciar aplicativos](media/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="94c07-120">Na página **gerenciar aplicativos** , na caixa de pesquisa, digite *Learning* para pesquisar o aplicativo Teams Learning (visualização particular).</span><span class="sxs-lookup"><span data-stu-id="94c07-120">On the **Manage apps** page, in the search box, type *learning* to search for the Teams Learning app (private preview).</span></span>

   ![Página Gerenciar aplicativos no centro de administração do teams mostrando a caixa de pesquisa](media/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="94c07-122">Na página de **aprendizagem** :</span><span class="sxs-lookup"><span data-stu-id="94c07-122">On the **Learning** page:</span></span>
   1. <span data-ttu-id="94c07-123">Em **status**, selecione **permitido** para ativar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="94c07-123">Under **Status**, select **Allowed** to turn on the app.</span></span>
   2. <span data-ttu-id="94c07-124">Na guia **configurações** , na seção **configurações do aplicativo** , vá para o centro de administração do Microsoft 365 para configurar as fontes de conteúdo de aprendizagem.</span><span class="sxs-lookup"><span data-stu-id="94c07-124">On the **Settings** tab, in the **App settings** section, go to the Microsoft 365 admin center to configure learning content sources.</span></span>

   ![Página de aprendizagem no centro de administração do teams mostrando a seção de configurações de status e de aplicativo](media/learning-app-teams-learning-page.png)

4. <span data-ttu-id="94c07-126">Após **gerenciar** as configurações do aplicativo, vá para **permissões e políticas de configuração** para conceder permissão a funcionários que devem ter acesso ao aplicativo como parte da participação da sua organização na visualização particular.</span><span class="sxs-lookup"><span data-stu-id="94c07-126">After **Manage app** settings, go to **Permissions and Set-up policies** to grant permission to employees who should have access to the app as part of your organization's participation in the private preview.</span></span>

> [!NOTE]
>  <span data-ttu-id="94c07-127">Se a sua organização estiver em anel 4,0 como parte do programa Teams TAP100, talvez seja necessário fazer o seguinte para habilitar os usuários aprovados no Ring 3,0 para acessar o aplicativo Teams Learning (visualização particular).</span><span class="sxs-lookup"><span data-stu-id="94c07-127">If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to do the following to enable approved users in Ring 3.0 to access the Teams Learning app (private preview).</span></span>

<span data-ttu-id="94c07-128">Como parte da visualização particular, o aplicativo Teams Learning (visualização privada) é lançado em Ring 3,0.</span><span class="sxs-lookup"><span data-stu-id="94c07-128">As part of private preview, the Teams Learning app (private preview) is released in Ring 3.0.</span></span> <span data-ttu-id="94c07-129">Se sua organização estiver em anel 4,0, você não verá o aplicativo na App Store.</span><span class="sxs-lookup"><span data-stu-id="94c07-129">If your organization is in Ring 4.0, you won’t see the app in the app store.</span></span> <span data-ttu-id="94c07-130">Para testar o aplicativo, você precisa criar uma política de permissão de aplicativos personalizados, defini-la para **permitir todos os aplicativos** e atribuí-la a usuários aprovados do Ring 3,0.</span><span class="sxs-lookup"><span data-stu-id="94c07-130">To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users.</span></span>

   ![TOQUE em-AppsPermission-Plcy página mostrar permitir todos os aplicativos selecionados](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a><span data-ttu-id="94c07-132">Configurar fontes de conteúdo de aprendizagem no centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="94c07-132">Configure learning content sources in the Microsoft 365 admin center</span></span>

<span data-ttu-id="94c07-133">Os administradores do centro de administração do Microsoft 365, por si só, ou atribuindo a função de administrador de conhecimento às pessoas selecionadas em sua organização, podem gerenciar as configurações relacionadas ao aplicativo Teams Learning (visualização particular) e pode configurar as fontes de conteúdo de aprendizagem.</span><span class="sxs-lookup"><span data-stu-id="94c07-133">The admins for the Microsoft 365 admin center—either by themselves or by assigning the Knowledge admin role to selected individuals in your organization—can manage settings related to the Teams Learning app (private preview) and can configure the learning content sources.</span></span>

> [!TIP]
> <span data-ttu-id="94c07-134">O administrador de conhecimento deve ser moderado de forma moderada e ter credenciais de administrador existentes do SharePoint, de preferência a alguém que tenha uma boa conversa na educação, aprendizagem, treinamento ou experiência do funcionário da organização.</span><span class="sxs-lookup"><span data-stu-id="94c07-134">The Knowledge admin should be moderately technical and have existing SharePoint admin credentials, preferably someone who is well-versed in the education, learning, training, or employee experience part of the organization.</span></span>
 
<span data-ttu-id="94c07-135">O administrador seleciona quais fontes de conteúdo de aprendizagem (como o LinkedIn Learning ou o SharePoint) estará disponível no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="94c07-135">The admin selects which learning content sources (such as LinkedIn Learning or SharePoint) will be available in the app.</span></span> <span data-ttu-id="94c07-136">Em seguida, o administrador configura essas fontes para garantir que o conteúdo esteja disponível para pesquisa e descoberta e possa ser acessado pelos funcionários que usam o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="94c07-136">The admin then configures those sources to make sure the content is available for search and discovery and can be browsed by the employees who use the app.</span></span>

### <a name="assign-the-knowledge-admin-role-optional"></a><span data-ttu-id="94c07-137">Atribuir a função de administrador de conhecimento [opcional]</span><span class="sxs-lookup"><span data-stu-id="94c07-137">Assign the Knowledge admin role [Optional]</span></span>

<span data-ttu-id="94c07-138">Essas etapas devem ser executadas pelo administrador do centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="94c07-138">These steps are to be performed by the admin for the Microsoft 365 admin center.</span></span>

1.  <span data-ttu-id="94c07-139">Na navegação à esquerda do centro de administração do Microsoft 365, vá para **funções**.</span><span class="sxs-lookup"><span data-stu-id="94c07-139">In the left navigation of the Microsoft 365 admin center, go to **Roles**.</span></span>

2.  <span data-ttu-id="94c07-140">Na página **funções** , na guia **Azure ad** , selecione administrador de **conhecimento**.</span><span class="sxs-lookup"><span data-stu-id="94c07-140">On the **Roles** page, on the **Azure AD** tab, select **Knowledge admin**.</span></span>
 
3.  <span data-ttu-id="94c07-141">Na página **administrador de conhecimento** , na seção **Administradores atribuídos** , selecione **Adicionar** e adicione a pessoa que você escolher para a função.</span><span class="sxs-lookup"><span data-stu-id="94c07-141">On the **Knowledge admin** page, in the **Assigned Admins** section, select **Add**, and then add the person you choose for the role.</span></span>

### <a name="configure-settings-for-the-learning-content-sources-for-the-app"></a><span data-ttu-id="94c07-142">Definir configurações para as fontes de conteúdo de aprendizagem do aplicativo</span><span class="sxs-lookup"><span data-stu-id="94c07-142">Configure settings for the learning content sources for the app</span></span>

<span data-ttu-id="94c07-143">Essas etapas devem ser realizadas pelo administrador do Microsoft 365 ou pelo administrador de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="94c07-143">These steps are to be performed by the Microsoft 365 admin or the Knowledge admin.</span></span>

1.  <span data-ttu-id="94c07-144">Na navegação à esquerda do centro de administração do Microsoft 365, vá para **configurações**  >  **organização** de configurações.</span><span class="sxs-lookup"><span data-stu-id="94c07-144">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>

2.  <span data-ttu-id="94c07-145">Na página **configurações** , na guia **Serviços & suplementos** , selecione **aplicativo de aprendizagem**.</span><span class="sxs-lookup"><span data-stu-id="94c07-145">On the **Settings** page, on the **Services & add-ins** tab, select **Learning app**.</span></span>

   ![Página configurações no centro de administração do Microsoft 365 mostrando o aplicativo de aprendizagem listado](media/learning-app-365-settings-page.png)

3.  <span data-ttu-id="94c07-147">No painel do **aplicativo de aprendizagem** , selecione as fontes de conteúdo de aprendizagem que você deseja configurar para a organização e, em seguida, selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="94c07-147">On the **Learning app** panel, select the learning content sources you want to configure for the organization, and then select **Save**.</span></span>

   ![Painel do aplicativo de aprendizagem no centro de administração do Microsoft 365 mostrando opções de fontes de conteúdo](media/learning-app-365-settings-learning-app-panel.png)

<span data-ttu-id="94c07-149">Entre todas as fontes de aprendizagem existentes, algumas serão habilitadas por padrão.</span><span class="sxs-lookup"><span data-stu-id="94c07-149">Among all the learning sources that exist, some will be enabled by default.</span></span> <span data-ttu-id="94c07-150">Elas incluem:</span><span class="sxs-lookup"><span data-stu-id="94c07-150">These include:</span></span>

- <span data-ttu-id="94c07-151">LinkedIn Learning (conteúdo gratuito)</span><span class="sxs-lookup"><span data-stu-id="94c07-151">LinkedIn Learning (free content)</span></span>
- <span data-ttu-id="94c07-152">Microsoft Learn</span><span class="sxs-lookup"><span data-stu-id="94c07-152">Microsoft Learn</span></span>
- <span data-ttu-id="94c07-153">Treinamento do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="94c07-153">Microsoft 365 Training</span></span>

> [!NOTE]
> <span data-ttu-id="94c07-154">Se a sua organização tiver uma assinatura do LinkedIn Learning Standard ou pro, o repositório de conteúdo será desbloqueado para os funcionários da sua organização.</span><span class="sxs-lookup"><span data-stu-id="94c07-154">If your organization has a LinkedIn Learning Standard or Pro subscription, the content repository will be unlocked for the employees in your organization.</span></span> <span data-ttu-id="94c07-155">Somente os funcionários que têm permissão poderão usar todo o repositório de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="94c07-155">Only those employees who have permission will be able to use the entire content repository.</span></span>

<span data-ttu-id="94c07-156">Outras fontes podem precisar ser habilitadas ou configuradas manualmente.</span><span class="sxs-lookup"><span data-stu-id="94c07-156">Other sources might need to be enabled or configured manually.</span></span> <span data-ttu-id="94c07-157">As fontes de aprendizagem que não são da Microsoft são licenciadas separadamente entre a sua organização e a outra.</span><span class="sxs-lookup"><span data-stu-id="94c07-157">Learning sources that are not from Microsoft are separately licensed between your organization and the third party.</span></span> <span data-ttu-id="94c07-158">Você precisará verificar se inscreveu-se para seu aprendizado e seus usuários.</span><span class="sxs-lookup"><span data-stu-id="94c07-158">You’ll need to verify you’ve signed up for their learning for you and your users.</span></span>

<span data-ttu-id="94c07-159">Para habilitar ou desabilitar uma fonte de conteúdo de aprendizagem, marque a caixa de seleção ao lado da fonte.</span><span class="sxs-lookup"><span data-stu-id="94c07-159">To enable or disable a learning content source, select the check box next to the source.</span></span> <span data-ttu-id="94c07-160">Se uma fonte estiver habilitada, uma marca de seleção estará visível.</span><span class="sxs-lookup"><span data-stu-id="94c07-160">If a source is enabled, a check mark will be visible.</span></span>

## <a name="configure-sharepoint-as-a-learning-content-source"></a><span data-ttu-id="94c07-161">Configurar o SharePoint como uma fonte de conteúdo de aprendizagem</span><span class="sxs-lookup"><span data-stu-id="94c07-161">Configure SharePoint as a learning content source</span></span>

<span data-ttu-id="94c07-162">Você configura o SharePoint como uma fonte de conteúdo de aprendizagem para o aplicativo Teams Learning (visualização particular) no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="94c07-162">You configure SharePoint as a learning content source for the Teams Learning app (private preview) in the Microsoft 365 admin center.</span></span>

### <a name="overview"></a><span data-ttu-id="94c07-163">Visão geral</span><span class="sxs-lookup"><span data-stu-id="94c07-163">Overview</span></span>

<span data-ttu-id="94c07-164">O administrador de conhecimento fornece uma URL de site onde o serviço de aprendizagem pode criar um repositório de conteúdo de aprendizagem centralizado vazio na forma de uma lista estruturada do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="94c07-164">The Knowledge admin provides a site URL to where the Learning Service can create an empty centralized learning content repository in the form of a structured SharePoint list.</span></span> <span data-ttu-id="94c07-165">Esta lista pode ser usada pela organização para armazenar links para pastas interempresariais do SharePoint que contenham conteúdo de aprendizagem.</span><span class="sxs-lookup"><span data-stu-id="94c07-165">This list can be used by the organization to house links to cross-company SharePoint folders that contain learning content.</span></span> <span data-ttu-id="94c07-166">Os administradores são responsáveis por coletar e selecionar uma lista de URLs para pastas.</span><span class="sxs-lookup"><span data-stu-id="94c07-166">Admins are responsible for collecting and curating a list of URLs for folders.</span></span> <span data-ttu-id="94c07-167">Essas pastas só devem incluir conteúdo que possa ser disponibilizado no aplicativo Teams Learning (visualização particular).</span><span class="sxs-lookup"><span data-stu-id="94c07-167">These folders should only include content that can be made available in the Teams Learning app (private preview).</span></span>

### <a name="permissions"></a><span data-ttu-id="94c07-168">Permissões</span><span class="sxs-lookup"><span data-stu-id="94c07-168">Permissions</span></span>

<span data-ttu-id="94c07-169">As URLs de pastas podem ser coletadas de qualquer site do SharePoint na organização.</span><span class="sxs-lookup"><span data-stu-id="94c07-169">Folder URLs can be collected from any SharePoint site in the organization.</span></span> <span data-ttu-id="94c07-170">Qualquer conteúdo dentro dessas pastas será pesquisável, mas somente conteúdo para o qual o funcionário individual tem permissões pode ser usado.</span><span class="sxs-lookup"><span data-stu-id="94c07-170">Any content within these folders will be searchable, but only content to which the individual employee has permissions can be used.</span></span>
 
### <a name="learning-service"></a><span data-ttu-id="94c07-171">Serviço de aprendizagem</span><span class="sxs-lookup"><span data-stu-id="94c07-171">Learning Service</span></span>

<span data-ttu-id="94c07-172">O serviço de aprendizagem usa as URLs de pastas fornecidas para obter metadados de todo o conteúdo armazenado nessas pastas.</span><span class="sxs-lookup"><span data-stu-id="94c07-172">The Learning Service uses the provided folder URLs to get metadata from all content stored in those folders.</span></span> <span data-ttu-id="94c07-173">Dentro de 24 horas de fornecimento da URL da pasta no repositório centralizado, os funcionários podem pesquisar e usar o conteúdo da empresa dentro do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="94c07-173">Within 24 hours of supplying the folder URL in the centralized repository, employees can search for and use the company’s content within the app.</span></span> <span data-ttu-id="94c07-174">Não há suporte para a exclusão de conteúdo do repositório neste ponto.</span><span class="sxs-lookup"><span data-stu-id="94c07-174">Content deletion from the repository isn't supported at this point.</span></span> <span data-ttu-id="94c07-175">O conteúdo na superfície não intencional pode ser removido apenas fornecendo uma nova URL de site do SharePoint no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="94c07-175">Unintentionally surfaced content can only be removed by supplying a new SharePoint site URL in the Microsoft 365 admin center.</span></span>

### <a name="configure-sharepoint-as-a-source"></a><span data-ttu-id="94c07-176">Configurar o SharePoint como uma origem</span><span class="sxs-lookup"><span data-stu-id="94c07-176">Configure SharePoint as a source</span></span>

<span data-ttu-id="94c07-177">Essas etapas devem ser realizadas pelo administrador do Microsoft 365 ou pelo administrador de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="94c07-177">These steps are to be performed by Microsoft 365 admin or the Knowledge admin.</span></span>

1.  <span data-ttu-id="94c07-178">Na navegação à esquerda do centro de administração do Microsoft 365, vá para **configurações**.</span><span class="sxs-lookup"><span data-stu-id="94c07-178">In the left navigation of the Microsoft 365 admin center, go to **Settings**.</span></span>
 
2.  <span data-ttu-id="94c07-179">Na página **configurações** , na guia **Serviços & suplementos** , selecione **aplicativo de aprendizagem**.</span><span class="sxs-lookup"><span data-stu-id="94c07-179">On the **Settings** page, on the **Services & add-ins** tab, select **Learning app**.</span></span>

   ![Página configurações no centro de administração do Microsoft 365 mostrando o aplicativo de aprendizagem listado](media/learning-app-365-settings-page.png)

3.  <span data-ttu-id="94c07-181">No painel do **aplicativo de aprendizagem** , forneça a URL do site para o site do SharePoint onde você deseja que o aplicativo crie um repositório centralizado.</span><span class="sxs-lookup"><span data-stu-id="94c07-181">On the **Learning app** panel, provide the site URL to the SharePoint site where you want the app to create a centralized repository.</span></span>

   ![Painel do aplicativo de aprendizagem no centro de administração do Microsoft 365 mostrando o SharePoint selecionado](media/learning-app-365-panel-sharepoint-selected.png)

4.  <span data-ttu-id="94c07-183">Uma lista do SharePoint é criada automaticamente dentro do site do SharePoint da organização fornecida.</span><span class="sxs-lookup"><span data-stu-id="94c07-183">A SharePoint list is created automatically within the provided organization’s SharePoint site.</span></span> <span data-ttu-id="94c07-184">Na navegação à esquerda do site do SharePoint, selecione o **repositório de conteúdo do aplicativo de aprendizagem**.</span><span class="sxs-lookup"><span data-stu-id="94c07-184">In the left navigation of the SharePoint site, select **Learning App Content Repository**.</span></span> 

   ![Navegação à esquerda no SharePoint mostrando a seção repositório de conteúdo do aplicativo de aprendizagem](media/learning-app-content-repository-nav.png)

 
5. <span data-ttu-id="94c07-186">Na página **repositório de conteúdo do aplicativo de aprendizagem** , preencha a lista do SharePoint com URLs para as pastas de conteúdo de aprendizagem.</span><span class="sxs-lookup"><span data-stu-id="94c07-186">On the **Learning App Content Repository** page, populate the SharePoint list with URLs to the learning content folders.</span></span>

   1.   <span data-ttu-id="94c07-187">Selecione **novo** para exibir o **novo** painel de itens.</span><span class="sxs-lookup"><span data-stu-id="94c07-187">Select **New** to view the **New item** panel.</span></span> 

   ![Página de repositório de conteúdo do aplicativo de aprendizagem no SharePoint mostrando a nova opção](media/learning-app-content-repository-new.png)
 
   2.   <span data-ttu-id="94c07-189">No painel **novo item** , no campo **título** , adicione o nome de um diretório de sua preferência.</span><span class="sxs-lookup"><span data-stu-id="94c07-189">On the **New item** panel, in the **Title** field, add a directory name of your choice.</span></span> <span data-ttu-id="94c07-190">No campo **URL da pasta** , adicione a URL à pasta de conteúdo de aprendizagem.</span><span class="sxs-lookup"><span data-stu-id="94c07-190">In the **Folder URL** field, add the URL to the learning content folder.</span></span> <span data-ttu-id="94c07-191">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="94c07-191">Select **Save**.</span></span>

   ![Painel novo item no SharePoint mostrando os campos de URL título e pasta](media/learning-app-new-item-panel.png)

   3. <span data-ttu-id="94c07-193">A página do repositório de conteúdo do aplicativo de aprendizagem é atualizada com o novo conteúdo de aprendizagem.</span><span class="sxs-lookup"><span data-stu-id="94c07-193">The Learning App Content Repository page is updated with the new learning content.</span></span>

   ![Página de repositório de conteúdo do aplicativo de aprendizagem no SharePoint mostrando as informações atualizadas](media/learning-app-content-repository-populated.png)


 


