---
title: Instalar, gerenciar e atribuir permissões para o Microsoft Viva Learning (visualização privada)
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
description: Use o Microsoft Viva Learning (visualização privada) para criar um hub central para aprender onde os funcionários podem compartilhar, atribuir e aprender com bibliotecas de conteúdo em uma organização.
f1.keywords: ''
appliesto:
- Microsoft Teams
ms.custom: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 3b99cdcd49dc35a558d6217e28bf57bbb8563827
ms.sourcegitcommit: b56727299d7ea47e23807114a4f5881e289c0b6a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/17/2021
ms.locfileid: "51880320"
---
# <a name="install-manage-and-assign-permissions-for-microsoft-viva-learning-private-preview"></a><span data-ttu-id="6b16d-103">Instalar, gerenciar e atribuir permissões para o Microsoft Viva Learning (visualização privada)</span><span class="sxs-lookup"><span data-stu-id="6b16d-103">Install, manage, and assign permissions for Microsoft Viva Learning (private preview)</span></span>

<span data-ttu-id="6b16d-104">*Este artigo contém conteúdo preliminar para o Microsoft Viva Learning, que está em visualização privada.*</span><span class="sxs-lookup"><span data-stu-id="6b16d-104">*This article contains preliminary content for Microsoft Viva Learning, which is in private preview.*</span></span>

<span data-ttu-id="6b16d-105">O Microsoft Viva Learning (visualização privada) capacita equipes e indivíduos em sua organização a tornar o aprendizado uma parte natural do seu dia.</span><span class="sxs-lookup"><span data-stu-id="6b16d-105">Microsoft Viva Learning (private preview) empowers teams and individuals in your organization to make learning a natural part of their day.</span></span> <span data-ttu-id="6b16d-106">O aplicativo cria um hub central no Teams onde os funcionários podem compartilhar, atribuir e aprender com bibliotecas de conteúdo em toda a sua organização.</span><span class="sxs-lookup"><span data-stu-id="6b16d-106">The app creates a central hub in Teams where employees can share, assign, and learn from content libraries across your organization.</span></span>

<span data-ttu-id="6b16d-107">Os administradores configuram permissões e permitem fontes de conteúdo de aprendizagem para o Viva Learning (visualização privada).</span><span class="sxs-lookup"><span data-stu-id="6b16d-107">Admins set permissions and allow learning content sources for Viva Learning (private preview).</span></span> <span data-ttu-id="6b16d-108">O conteúdo de aprendizagem pode incluir o LinkedIn Learning, o Microsoft Learn, o treinamento do Microsoft 365, o próprio conteúdo da sua organização armazenado no SharePoint online e provedores de terceiros que são suportados pelo Viva Learning (visualização privada).</span><span class="sxs-lookup"><span data-stu-id="6b16d-108">Learning content can include LinkedIn Learning, Microsoft Learn, Microsoft 365 training, your organization's own content stored in SharePoint online, and third-party providers that are supported by Viva Learning (private preview).</span></span>

## <a name="admin-roles"></a><span data-ttu-id="6b16d-109">Funções de administrador</span><span class="sxs-lookup"><span data-stu-id="6b16d-109">Admin roles</span></span>

<span data-ttu-id="6b16d-110">Para configurar o Viva Learning (visualização privada), você precisará de permissões como:</span><span class="sxs-lookup"><span data-stu-id="6b16d-110">To set up Viva Learning (private preview), you'll need permissions as:</span></span>

- <span data-ttu-id="6b16d-111">Administrador do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6b16d-111">Microsoft Teams admin</span></span>
- <span data-ttu-id="6b16d-112">Administrador global do Microsoft 365 ou administrador do SharePoint</span><span class="sxs-lookup"><span data-stu-id="6b16d-112">Microsoft 365 global administrator or SharePoint administrator</span></span>
- <span data-ttu-id="6b16d-113">Administrador de conhecimento — essa é uma nova função no Centro de administração do Microsoft 365 que pode ser atribuída a qualquer pessoa na organização.</span><span class="sxs-lookup"><span data-stu-id="6b16d-113">Knowledge admin — This is a new role in the Microsoft 365 admin center that can be assigned to anyone in the organization.</span></span> <span data-ttu-id="6b16d-114">Essa função gerencia as fontes de conteúdo de aprendizado da organização por meio do Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6b16d-114">This role manages the organization’s learning content sources through the Microsoft 365 admin center.</span></span> 

> [!TIP]
> <span data-ttu-id="6b16d-115">O administrador de conhecimento deve ser moderadamente técnico e ter credenciais de administrador do SharePoint existentes, de preferência alguém que seja bem versado na parte de educação, aprendizado, treinamento ou experiência de funcionários da organização.</span><span class="sxs-lookup"><span data-stu-id="6b16d-115">The knowledge admin should be moderately technical and have existing SharePoint admin credentials, preferably someone who is well-versed in the education, learning, training, or employee experience part of the organization.</span></span>
 
## <a name="manage-viva-learning-private-preview-in-the-teams-admin-center"></a><span data-ttu-id="6b16d-116">Gerenciar o Viva Learning (visualização privada) no centro de administração do Teams</span><span class="sxs-lookup"><span data-stu-id="6b16d-116">Manage Viva Learning (private preview) in the Teams admin center</span></span>

<span data-ttu-id="6b16d-117">O administrador do Teams instala o Viva Learning (visualização privada) na loja de aplicativos e aplica políticas de configuração, gerenciamento e permissão por meio do Centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="6b16d-117">The Teams admin installs Viva Learning (private preview) from the app store, and then applies setup, manage, and permission policies through the Teams admin center.</span></span>

### <a name="manage-settings-for-viva-learning-private-preview"></a><span data-ttu-id="6b16d-118">Gerenciar configurações para o Viva Learning (visualização privada)</span><span class="sxs-lookup"><span data-stu-id="6b16d-118">Manage settings for Viva Learning (private preview)</span></span>

<span data-ttu-id="6b16d-119">Você deve ser um administrador no Centro de administração do Teams para executar essas tarefas.</span><span class="sxs-lookup"><span data-stu-id="6b16d-119">You must be an administrator in the Teams admin center to perform these tasks.</span></span>

<span data-ttu-id="6b16d-120">Para gerenciar configurações para o Viva Learning, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="6b16d-120">To manage settings for Viva Learning, follow these steps:</span></span>

1. <span data-ttu-id="6b16d-121">Na navegação à esquerda do Centro de administração do Teams, vá para **Aplicativos do Teams**  >  **Gerenciar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="6b16d-121">In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![Navegação à esquerda no centro de administração do Teams mostrando aplicativos do Teams e Seção Gerenciar aplicativos](media/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="6b16d-123">Na página **Gerenciar aplicativos,** na caixa de pesquisa, digite aprendizagem *para* pesquisar o aplicativo Teams Learning (visualização privada).</span><span class="sxs-lookup"><span data-stu-id="6b16d-123">On the **Manage apps** page, in the search box, type *learning* to search for the Teams Learning app (private preview).</span></span>

   ![Gerenciar a página aplicativos no centro de administração do Teams mostrando a caixa de pesquisa](media/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="6b16d-125">Na página **Aprendizagem:**</span><span class="sxs-lookup"><span data-stu-id="6b16d-125">On the **Learning** page:</span></span>
   1. <span data-ttu-id="6b16d-126">Em **Status**, selecione **Permitido** ativar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6b16d-126">Under **Status**, select **Allowed** to turn on the app.</span></span>
   2. <span data-ttu-id="6b16d-127">Na guia **Configurações,** na **seção** Configurações do aplicativo, vá para o Centro de administração do Microsoft 365 para configurar fontes de conteúdo de aprendizado.</span><span class="sxs-lookup"><span data-stu-id="6b16d-127">On the **Settings** tab, in the **App settings** section, go to the Microsoft 365 admin center to configure learning content sources.</span></span>

   ![Página de aprendizado no centro de administração do Teams mostrando configurações de Status e Aplicativo](media/learning-app-teams-learning-page.png)

4. <span data-ttu-id="6b16d-129">Depois **de Gerenciar** configurações de aplicativo, acesse Permissões e Políticas de Configuração para conceder permissão aos **funcionários** que devem ter acesso ao aplicativo como parte da participação da sua organização na visualização privada.</span><span class="sxs-lookup"><span data-stu-id="6b16d-129">After **Manage app** settings, go to **Permissions and Set-up policies** to grant permission to employees who should have access to the app as part of your organization's participation in the private preview.</span></span>

> [!NOTE]
>  <span data-ttu-id="6b16d-130">Se sua organização estiver no Ring 4.0 como parte do programa Do Teams TAP100, talvez seja necessário fazer o seguinte para habilitar usuários aprovados no Anel 3.0 para acessar o Viva Learning (visualização privada).</span><span class="sxs-lookup"><span data-stu-id="6b16d-130">If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to do the following to enable approved users in Ring 3.0 to access Viva Learning (private preview).</span></span>

<span data-ttu-id="6b16d-131">Como parte da visualização privada, o Viva Learning (visualização privada) é lançado no Ring 3.0.</span><span class="sxs-lookup"><span data-stu-id="6b16d-131">As part of private preview, Viva Learning (private preview) is released in Ring 3.0.</span></span> <span data-ttu-id="6b16d-132">Se sua organização estiver no Ring 4.0, você não verá o aplicativo na loja de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="6b16d-132">If your organization is in Ring 4.0, you won’t see the app in the app store.</span></span> <span data-ttu-id="6b16d-133">Para testar o aplicativo, você precisa criar uma política de permissão de aplicativos personalizados, defini-la como **Permitir** todos os aplicativos e atribuí-lo aos usuários aprovados do Anel 3.0.</span><span class="sxs-lookup"><span data-stu-id="6b16d-133">To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users.</span></span>

   ![Página TAP-AppsPermission-Plcy mostrando Permitir todos os aplicativos selecionados](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a><span data-ttu-id="6b16d-135">Configurar fontes de conteúdo de aprendizagem no centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6b16d-135">Configure learning content sources in the Microsoft 365 admin center</span></span>

<span data-ttu-id="6b16d-136">Os administradores do Centro de administração do Microsoft 365 , por conta própria ou atribuindo a função de administrador de conhecimento a indivíduos selecionados em sua organização, podem gerenciar configurações relacionadas ao Viva Learning (visualização privada) e podem configurar as fontes de conteúdo de aprendizagem.</span><span class="sxs-lookup"><span data-stu-id="6b16d-136">The administrators for the Microsoft 365 admin center—either by themselves or by assigning the knowledge admin role to selected individuals in your organization—can manage settings related to Viva Learning (private preview) and can configure the learning content sources.</span></span>

<span data-ttu-id="6b16d-137">O administrador seleciona quais fontes de conteúdo de aprendizado adicionais (por exemplo, o SharePoint ou fontes de provedores de conteúdo de terceiros) estarão disponíveis para os usuários do Viva Learning (visualização privada).</span><span class="sxs-lookup"><span data-stu-id="6b16d-137">The administrator selects which additional learning content sources (for example, SharePoint or supported third-party content provider sources) will be available to users of Viva Learning (private preview).</span></span> <span data-ttu-id="6b16d-138">Em seguida, o administrador configura essas fontes para garantir que o conteúdo está disponível para pesquisa e descoberta e pode ser navegado pelos funcionários que usam o Viva Learning (visualização privada).</span><span class="sxs-lookup"><span data-stu-id="6b16d-138">The admin then configures those sources to make sure the content is available for search and discovery and can be browsed by the employees who use Viva Learning (private preview).</span></span>

> [!NOTE]
>  <span data-ttu-id="6b16d-139">Os usuários entrarão em aprendizados que não são da Microsoft e do LinkedIn Learning Pro em um navegador ou visualizador incorporado.</span><span class="sxs-lookup"><span data-stu-id="6b16d-139">Users sign in to non-Microsoft and LinkedIn Learning Pro learnings in a browser or embedded viewer.</span></span> <span data-ttu-id="6b16d-140">Esse aprendizado configurado está sujeito aos termos separados de licença, privacidade e serviço entre sua organização e terceiros e não os termos do Viva Learning (visualização privada).</span><span class="sxs-lookup"><span data-stu-id="6b16d-140">This configured learning is subject to the separate license, privacy and service terms between your organization and the third party, and not the Viva Learning (private preview) terms.</span></span> <span data-ttu-id="6b16d-141">Antes de selecionar esse tipo de aprendizado, verifique se você tem um contrato para sua organização e usuários.</span><span class="sxs-lookup"><span data-stu-id="6b16d-141">Before selecting this type of learning, verify you have an agreement in place for your organization and users.</span></span>

### <a name="assign-the-knowledge-admin-role-optional"></a><span data-ttu-id="6b16d-142">Atribuir a função de administrador de conhecimento [Opcional]</span><span class="sxs-lookup"><span data-stu-id="6b16d-142">Assign the knowledge admin role [Optional]</span></span>

<span data-ttu-id="6b16d-143">Você deve ser um administrador global do Microsoft 365 para executar essas tarefas.</span><span class="sxs-lookup"><span data-stu-id="6b16d-143">You must be a Microsoft 365 global administrator to perform these tasks.</span></span>

<span data-ttu-id="6b16d-144">Para atribuir um administrador de conhecimento para o Viva Learning, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="6b16d-144">To assign a knowledge admin for Viva Learning, follow these steps:</span></span>

1.  <span data-ttu-id="6b16d-145">Na navegação à esquerda do Centro de administração do Microsoft 365, vá para **Funções**.</span><span class="sxs-lookup"><span data-stu-id="6b16d-145">In the left navigation of the Microsoft 365 admin center, go to **Roles**.</span></span>

2.  <span data-ttu-id="6b16d-146">Na página **Funções,** na guia **Azure AD,** selecione **Administrador de conhecimento**.</span><span class="sxs-lookup"><span data-stu-id="6b16d-146">On the **Roles** page, on the **Azure AD** tab, select **Knowledge admin**.</span></span>
 
3.  <span data-ttu-id="6b16d-147">Na página **Administrador de** Conhecimento, na seção Administradores **Atribuídos,** selecione **Adicionar** e adicione a pessoa escolhida para a função.</span><span class="sxs-lookup"><span data-stu-id="6b16d-147">On the **Knowledge admin** page, in the **Assigned Admins** section, select **Add**, and then add the person you choose for the role.</span></span>

### <a name="configure-settings-for-the-learning-content-sources-for-viva-learning-private-preview"></a><span data-ttu-id="6b16d-148">Configurar configurações para as fontes de conteúdo de aprendizagem para o Viva Learning (visualização privada)</span><span class="sxs-lookup"><span data-stu-id="6b16d-148">Configure settings for the learning content sources for Viva Learning (private preview)</span></span>

<span data-ttu-id="6b16d-149">Você deve ser um administrador global do Microsoft 365 ou administrador de conhecimento para executar essas tarefas.</span><span class="sxs-lookup"><span data-stu-id="6b16d-149">You must be a Microsoft 365 global administrator or knowledge admin to perform these tasks.</span></span>

<span data-ttu-id="6b16d-150">Para definir configurações para aprender fontes de conteúdo no Viva Learning, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="6b16d-150">To configure settings for learning content sources in Viva Learning, follow these steps:</span></span>

1.  <span data-ttu-id="6b16d-151">Na navegação à esquerda do Centro de administração do Microsoft 365, acesse **Configurações**  >  **da Organização configurações**.</span><span class="sxs-lookup"><span data-stu-id="6b16d-151">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>

2.  <span data-ttu-id="6b16d-152">Na página **Configurações da** Organização, na guia **Serviços,** selecione **Aplicativo de aprendizagem (Visualização)**.</span><span class="sxs-lookup"><span data-stu-id="6b16d-152">On the **Org settings** page, on the **Services** tab, select **Learning app (Preview)**.</span></span>

     ![Página configurações no Centro de administração do Microsoft 365 mostrando o aplicativo de aprendizagem listado](media/learning-sharepoint-configure1.png)

3.  <span data-ttu-id="6b16d-154">No painel **Aplicativo de Aprendizagem (Visualização),** selecione as fontes de conteúdo de aprendizagem que você deseja configurar para a organização e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="6b16d-154">On the **Learning app (Preview)** panel, select the learning content sources you want to configure for the organization, and then select **Save**.</span></span>

     ![Painel de aprendizagem no Centro de administração do Microsoft 365 mostrando opções de fontes de conteúdo](media/learning-sharepoint-configure2.png)

<span data-ttu-id="6b16d-156">Entre todas as fontes de aprendizado existentes, algumas serão habilitadas por padrão.</span><span class="sxs-lookup"><span data-stu-id="6b16d-156">Among all the learning sources that exist, some will be enabled by default.</span></span> <span data-ttu-id="6b16d-157">Elas incluem:</span><span class="sxs-lookup"><span data-stu-id="6b16d-157">These include:</span></span>

- <span data-ttu-id="6b16d-158">LinkedIn Learning (conteúdo gratuito)</span><span class="sxs-lookup"><span data-stu-id="6b16d-158">LinkedIn Learning (free content)</span></span>
- <span data-ttu-id="6b16d-159">Microsoft Learn</span><span class="sxs-lookup"><span data-stu-id="6b16d-159">Microsoft Learn</span></span>
- <span data-ttu-id="6b16d-160">Treinamento do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6b16d-160">Microsoft 365 Training</span></span>

> [!NOTE]
> <span data-ttu-id="6b16d-161">Se sua organização tiver uma assinatura do LinkedIn Learning Standard ou Pro, o repositório de conteúdo será desbloqueado para os funcionários da sua organização.</span><span class="sxs-lookup"><span data-stu-id="6b16d-161">If your organization has a LinkedIn Learning Standard or Pro subscription, the content repository will be unlocked for the employees in your organization.</span></span> <span data-ttu-id="6b16d-162">Somente os funcionários que têm permissão poderão usar todo o repositório de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="6b16d-162">Only those employees who have permission will be able to use the entire content repository.</span></span> <br><span data-ttu-id="6b16d-163">Outras fontes podem precisar ser habilitadas ou configuradas manualmente.</span><span class="sxs-lookup"><span data-stu-id="6b16d-163">Other sources might need to be enabled or configured manually.</span></span> <span data-ttu-id="6b16d-164">As fontes de aprendizado que não são da Microsoft são licenciadas separadamente entre sua organização e terceiros.</span><span class="sxs-lookup"><span data-stu-id="6b16d-164">Learning sources that are not from Microsoft are separately licensed between your organization and the third party.</span></span> <span data-ttu-id="6b16d-165">Você precisará verificar se se inscreveu para o aprendizado deles para você e seus usuários.</span><span class="sxs-lookup"><span data-stu-id="6b16d-165">You’ll need to verify you’ve signed up for their learning for you and your users.</span></span>

<span data-ttu-id="6b16d-166">Para habilitar ou desabilitar uma fonte de conteúdo de aprendizagem, selecione a caixa de seleção ao lado da fonte.</span><span class="sxs-lookup"><span data-stu-id="6b16d-166">To enable or disable a learning content source, select the check box next to the source.</span></span> <span data-ttu-id="6b16d-167">Se uma fonte estiver habilitada, uma marca de seleção ficará visível.</span><span class="sxs-lookup"><span data-stu-id="6b16d-167">If a source is enabled, a check mark will be visible.</span></span>

## <a name="configure-sharepoint-as-a-learning-content-source"></a><span data-ttu-id="6b16d-168">Configurar o SharePoint como uma fonte de conteúdo de aprendizagem</span><span class="sxs-lookup"><span data-stu-id="6b16d-168">Configure SharePoint as a learning content source</span></span>

<span data-ttu-id="6b16d-169">Você pode configurar o SharePoint como uma fonte de conteúdo de aprendizagem para disponibilizar o próprio conteúdo da sua organização no Viva Learning (visualização privada).</span><span class="sxs-lookup"><span data-stu-id="6b16d-169">You can configure SharePoint as a learning content source to make your organization's own content available in Viva Learning (private preview).</span></span>

### <a name="overview"></a><span data-ttu-id="6b16d-170">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="6b16d-170">Overview</span></span>

<span data-ttu-id="6b16d-171">O administrador de conhecimento (ou administrador global) fornece uma URL de site para a qual o Serviço de Aprendizagem pode criar um local centralizado vazio, o Repositório de Conteúdo do Aplicativo de Aprendizagem, na forma de uma lista estruturada do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6b16d-171">The knowledge admin (or global administrator) provides a site URL to where the Learning Service can create an empty centralized location—the Learning App Content Repository—in the form of a structured SharePoint list.</span></span> <span data-ttu-id="6b16d-172">Essa lista pode ser usada pela sua organização para abrigar links para pastas do SharePoint entre empresas que contêm conteúdo de aprendizagem.</span><span class="sxs-lookup"><span data-stu-id="6b16d-172">This list can be used by your organization to house links to cross-company SharePoint folders that contain learning content.</span></span> <span data-ttu-id="6b16d-173">Os administradores são responsáveis por coletar e fazer a curadoria de uma lista de URLs para pastas.</span><span class="sxs-lookup"><span data-stu-id="6b16d-173">Admins are responsible for collecting and curating a list of URLs for folders.</span></span> <span data-ttu-id="6b16d-174">Essas pastas só devem incluir conteúdo que pode ser disponibilizado no Viva Learning (visualização privada).</span><span class="sxs-lookup"><span data-stu-id="6b16d-174">These folders should only include content that can be made available in Viva Learning (private preview).</span></span>

<span data-ttu-id="6b16d-175">O Viva Learning (visualização privada) dá suporte aos seguintes tipos de documento:</span><span class="sxs-lookup"><span data-stu-id="6b16d-175">Viva Learning (private preview) supports the following document types:</span></span>

- <span data-ttu-id="6b16d-176">Word, PowerPoint, Excel, PDF</span><span class="sxs-lookup"><span data-stu-id="6b16d-176">Word, PowerPoint, Excel, PDF</span></span>
- <span data-ttu-id="6b16d-177">Áudio (.m4a)</span><span class="sxs-lookup"><span data-stu-id="6b16d-177">Audio (.m4a)</span></span>
- <span data-ttu-id="6b16d-178">Vídeo (.mov, .mp4, .avi)</span><span class="sxs-lookup"><span data-stu-id="6b16d-178">Video (.mov, .mp4, .avi)</span></span>

<span data-ttu-id="6b16d-179">Para obter mais informações, consulte a [documentação do SharePoint Online.](https://docs.microsoft.com/sharepoint/introductionlink)</span><span class="sxs-lookup"><span data-stu-id="6b16d-179">For more information, see the [SharePoint Online documentation](https://docs.microsoft.com/sharepoint/introductionlink).</span></span> 

### <a name="permissions"></a><span data-ttu-id="6b16d-180">Permissões</span><span class="sxs-lookup"><span data-stu-id="6b16d-180">Permissions</span></span>

<span data-ttu-id="6b16d-181">As URLs da pasta da biblioteca de documentos podem ser coletadas de qualquer site do SharePoint na organização.</span><span class="sxs-lookup"><span data-stu-id="6b16d-181">Document library folder URLs can be collected from any SharePoint site in the organization.</span></span> <span data-ttu-id="6b16d-182">O Viva Learning (visualização privada) segue todas as permissões de conteúdo existentes.</span><span class="sxs-lookup"><span data-stu-id="6b16d-182">Viva Learning (private preview) follows all existing content permissions.</span></span> <span data-ttu-id="6b16d-183">Portanto, somente o conteúdo para o qual um usuário tem permissão para acessar é pesquisável e visável no Viva Learning (visualização privada).</span><span class="sxs-lookup"><span data-stu-id="6b16d-183">Therefore, only content for which a user has permission to access is searchable and visable within Viva Learning (private preview).</span></span> <span data-ttu-id="6b16d-184">Qualquer conteúdo dentro dessas pastas será pesquisável, mas somente o conteúdo para o qual o funcionário individual tem permissões pode ser usado.</span><span class="sxs-lookup"><span data-stu-id="6b16d-184">Any content within these folders will be searchable, but only content to which the individual employee has permissions can be used.</span></span>

<span data-ttu-id="6b16d-185">A exclusão de conteúdo do repositório da sua organização não é suportada no momento.</span><span class="sxs-lookup"><span data-stu-id="6b16d-185">Content deletion from your organization’s repository is not currently supported.</span></span>

<span data-ttu-id="6b16d-186">Para remover conteúdo não intencionalmente à superfície, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="6b16d-186">To remove unintentionally surfaced content, follow these steps:</span></span>

1.  <span data-ttu-id="6b16d-187">Para restringir o acesso à biblioteca de documentos, selecione a opção **Mostrar ações** e selecione **Gerenciar acesso**.</span><span class="sxs-lookup"><span data-stu-id="6b16d-187">To restrict access on the document library, select the **Show actions** option, and then select **Manage access**.</span></span>
     
     ![Página da biblioteca de documentos no SharePoint mostrando a opção Mostrar ações com Gerenciar acesso com alta qualificação.](media/learning-sharepoint-permissions2.png)

2.  <span data-ttu-id="6b16d-189">Exclua o documento original na biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="6b16d-189">Delete the original document within the document library.</span></span>

<span data-ttu-id="6b16d-190">Para obter mais informações, consulte [Compartilhamento e permissões na experiência moderna do SharePoint.](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions)</span><span class="sxs-lookup"><span data-stu-id="6b16d-190">For more information, see [Sharing and permissions in the SharePoint modern experience](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span> 

### <a name="learning-service"></a><span data-ttu-id="6b16d-191">Serviço de Aprendizagem</span><span class="sxs-lookup"><span data-stu-id="6b16d-191">Learning Service</span></span>

<span data-ttu-id="6b16d-192">O Serviço de Aprendizagem usa as URLs de pasta fornecidas para obter metadados de todo o conteúdo armazenado nessas pastas.</span><span class="sxs-lookup"><span data-stu-id="6b16d-192">The Learning Service uses the provided folder URLs to get metadata from all content stored in those folders.</span></span> <span data-ttu-id="6b16d-193">Dentro de 24 horas após fornecer a URL da pasta no repositório centralizado, os funcionários podem pesquisar e usar o conteúdo da sua organização no Viva Learning (visualização privada).</span><span class="sxs-lookup"><span data-stu-id="6b16d-193">Within 24 hours of supplying the folder URL in the centralized repository, employees can search for and use your organization’s content within Viva Learning (private preview).</span></span> <span data-ttu-id="6b16d-194">Todas as alterações no conteúdo, incluindo metadados e permissões atualizadas, também serão aplicadas no Serviço de Aprendizagem dentro de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="6b16d-194">All changes to content, including updated metadata and permissions, will also be applied in the Learning Service within 24 hours.</span></span>

### <a name="configure-sharepoint-as-a-source"></a><span data-ttu-id="6b16d-195">Configurar o SharePoint como fonte</span><span class="sxs-lookup"><span data-stu-id="6b16d-195">Configure SharePoint as a source</span></span>

<span data-ttu-id="6b16d-196">Você deve ser um administrador global do Microsoft 365, administrador do SharePoint ou administrador de conhecimento para executar essas tarefas.</span><span class="sxs-lookup"><span data-stu-id="6b16d-196">You must be a Microsoft 365 global administrator, SharePoint administrator, or knowledge admin to perform these tasks.</span></span>

<span data-ttu-id="6b16d-197">Para configurar o SharePoint como fontes de conteúdo de aprendizagem no Viva Learning (visualização privada), siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="6b16d-197">To configure SharePoint as a learning content sources in for Viva Learning (private preview), follow these steps:</span></span>

1.  <span data-ttu-id="6b16d-198">Na navegação à esquerda do Centro de administração do Microsoft 365, acesse **Configurações**  >  **da Organização configurações**.</span><span class="sxs-lookup"><span data-stu-id="6b16d-198">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>
 
2.  <span data-ttu-id="6b16d-199">Na página **Configurações da** Organização, na guia **Serviços,** selecione **Aplicativo de aprendizagem (Visualização)**.</span><span class="sxs-lookup"><span data-stu-id="6b16d-199">On the **Org settings** page, on the **Services** tab, select **Learning app (Preview)**.</span></span>

     ![Página de configurações no Centro de administração do Microsoft 365 mostrando o Viva Learning listado.](media/learning-sharepoint-configure1.png)

3.  <span data-ttu-id="6b16d-201">No painel Aplicativo de Aprendizagem **(Visualização),** em **SharePoint**, forneça a URL do site para o site do SharePoint onde você deseja que o Viva Learning crie um repositório centralizado.</span><span class="sxs-lookup"><span data-stu-id="6b16d-201">On the **Learning app (Preview)** panel, under **SharePoint**, provide the site URL to the SharePoint site where you want Viva Learning to create a centralized repository.</span></span>

     ![Painel de aprendizagem no Centro de administração do Microsoft 365 mostrando o SharePoint selecionado.](media/learning-sharepoint-configure2.png)

4.  <span data-ttu-id="6b16d-203">Uma lista do SharePoint é criada automaticamente no site do SharePoint fornecido.</span><span class="sxs-lookup"><span data-stu-id="6b16d-203">A SharePoint list is created automatically within the provided SharePoint site.</span></span>

     ![Lista do SharePoint recém-criada no site do SharePoint.](media/learning-sharepoint-configure3.png)

     <span data-ttu-id="6b16d-205">Na navegação à esquerda do site do SharePoint, selecione Conteúdo do **site**  >  **Aprendendo Repositório de Conteúdo do Aplicativo.**</span><span class="sxs-lookup"><span data-stu-id="6b16d-205">In the left navigation of the SharePoint site, select **Site contents** > **Learning App Content Repository**.</span></span> 

     ![Lista do SharePoint mostrando a navegação de conteúdo do site e a seção Repositório de Conteúdo do Aplicativo de Aprendizagem.](media/learning-sharepoint-configure4.png) 

5. <span data-ttu-id="6b16d-207">Na página **Repositório de Conteúdo do Aplicativo** de Aprendizagem, preencha a lista do SharePoint com URLs para as pastas de conteúdo de aprendizagem.</span><span class="sxs-lookup"><span data-stu-id="6b16d-207">On the **Learning App Content Repository** page, populate the SharePoint list with URLs to the learning content folders.</span></span>

   1. <span data-ttu-id="6b16d-208">Selecione **Novo** para exibir o **painel Novo item.**</span><span class="sxs-lookup"><span data-stu-id="6b16d-208">Select **New** to view the **New item** panel.</span></span> 

       ![Aprendendo a página Repositório de Conteúdo no SharePoint mostrando a opção Nova.](media/learning-sharepoint-configure5.png)
 
   2. <span data-ttu-id="6b16d-210">No painel **Novo item,** no campo **Título,** adicione um nome de diretório de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="6b16d-210">On the **New item** panel, in the **Title** field, add a directory name of your choice.</span></span> <span data-ttu-id="6b16d-211">No campo **URL da pasta,** adicione a URL à pasta de conteúdo de aprendizagem.</span><span class="sxs-lookup"><span data-stu-id="6b16d-211">In the **Folder URL** field, add the URL to the learning content folder.</span></span> <span data-ttu-id="6b16d-212">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="6b16d-212">Select **Save**.</span></span>

       ![Novo painel de itens no SharePoint mostrando os campos de URL título e pasta.](media/learning-sharepoint-configure6.png)

   3. <span data-ttu-id="6b16d-214">A **página Repositório de Conteúdo do Aplicativo** de Aprendizagem é atualizada com o novo conteúdo de aprendizado.</span><span class="sxs-lookup"><span data-stu-id="6b16d-214">The **Learning App Content Repository** page is updated with the new learning content.</span></span>

       ![Página Do Repositório de Conteúdo no SharePoint mostrando as informações atualizadas.](media/learning-sharepoint-configure7.png)

> [!NOTE]
> <span data-ttu-id="6b16d-216">Para permitir acesso mais amplo ao Repositório de Conteúdo do Aplicativo de Aprendizagem, um link para a lista em breve estará disponível na interface do Viva Learning (visualização privada), onde os usuários podem solicitar acesso e, em última análise, ajudar a preencher a lista.</span><span class="sxs-lookup"><span data-stu-id="6b16d-216">To allow for broader access to the Learning App Content Repository, a link to the list soon will be available in the Viva Learning (private preview) interface where users can request access and ultimately help populate the list.</span></span> <span data-ttu-id="6b16d-217">Os proprietários de sites e administradores globais serão necessários para conceder acesso à lista.</span><span class="sxs-lookup"><span data-stu-id="6b16d-217">Site owners and global administrators will be required to grant access to the list.</span></span> <span data-ttu-id="6b16d-218">O Access é específico apenas para a lista e não se aplica ao site onde a lista está armazenada.</span><span class="sxs-lookup"><span data-stu-id="6b16d-218">Access is specific to the list only and does not apply to the site where the list is stored.</span></span>

### <a name="folder-url-document-library-curation"></a><span data-ttu-id="6b16d-219">Curação da biblioteca de documentos da URL da pasta</span><span class="sxs-lookup"><span data-stu-id="6b16d-219">Folder URL document library curation</span></span>

<span data-ttu-id="6b16d-220">Os metadados padrão (como data modificada, criada por, nome do documento, tipo de conteúdo e nome da organização) são automaticamente retirados para o Viva Learning (visualização privada) pela API do Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="6b16d-220">Default metadata (such as modified date, created by, document name, content type, and organization name) is automatically pulled into Viva Learning (private preview) by the Microsoft Graph API.</span></span>
 
<span data-ttu-id="6b16d-221">Para melhorar a relevância geral da descoberta e da pesquisa do conteúdo, recomendamos adicionar uma coluna **Descrição.**</span><span class="sxs-lookup"><span data-stu-id="6b16d-221">To improve overall discovery and search relevance of the content, we recommend adding a **Description** column.</span></span>

<span data-ttu-id="6b16d-222">Para adicionar uma **coluna Descrição** à página da biblioteca de documentos, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="6b16d-222">To add a **Description** column to the document library page, follow these steps:</span></span>

1.  <span data-ttu-id="6b16d-223">Na página **Documentos,** selecione **Adicionar coluna**.</span><span class="sxs-lookup"><span data-stu-id="6b16d-223">On the **Documents** page, select **Add column**.</span></span>

2. <span data-ttu-id="6b16d-224">Selecione a **opção Mostrar ações** e selecione Linha única de **texto**.</span><span class="sxs-lookup"><span data-stu-id="6b16d-224">Select the **Show actions** option, and then select **Single line of text**.</span></span>

     ![Página Documentos no SharePoint mostrando as opções Mostrar ações com linha única de texto realçada.](media/learning-sharepoint-curation1.png)

3. <span data-ttu-id="6b16d-226">No painel **Criar uma coluna,** no campo **Nome,** adicione um nome descritivo para a coluna.</span><span class="sxs-lookup"><span data-stu-id="6b16d-226">On the **Create a column** panel, in the **Name** field, add a descriptive name for the column.</span></span> <span data-ttu-id="6b16d-227">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="6b16d-227">Select **Save**.</span></span>

     ![Crie um painel de colunas no SharePoint mostrando o Nome e outros campos.](media/learning-sharepoint-curation2.png)
 
4. <span data-ttu-id="6b16d-229">Na página **Documentos,** na coluna **Descrição,** adicione descrições personalizadas para cada item.</span><span class="sxs-lookup"><span data-stu-id="6b16d-229">On the **Documents** page, in the **Description** column, add custom descriptions for each item.</span></span> <span data-ttu-id="6b16d-230">Se nenhuma descrição for fornecida, o Viva Learning (visualização privada) fornecerá uma mensagem padrão que realça o conteúdo como sendo de sua própria biblioteca do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6b16d-230">If no description is supplied, Viva Learning (private preview) will provide a default message that highlights the content as being from your own SharePoint library.</span></span> 

     ![Página Documentos no SharePoint mostrando as descrições na coluna Descrição.](media/learning-sharepoint-curation3.png)
 
