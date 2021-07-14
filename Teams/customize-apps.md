---
title: Personalizar aplicativos no Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: v-tbasra
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como personalizar aplicativos em Microsoft Teams.
ms.openlocfilehash: e2a217648abbcec4075e942b303542621f7d317a
ms.sourcegitcommit: f3e9989cbcc2f9f83ff94204bdd75b1e6ad43b5e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/13/2021
ms.locfileid: "53408740"
---
# <a name="customize-apps-in-microsoft-teams"></a><span data-ttu-id="061fc-103">Personalizar aplicativos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="061fc-103">Customize apps in Microsoft Teams</span></span>

 <span data-ttu-id="061fc-104">Microsoft Teams oferece personalização de aplicativo para aprimorar a experiência Teams aplicativo.</span><span class="sxs-lookup"><span data-stu-id="061fc-104">Microsoft Teams provides app customization to enhance the Teams experience.</span></span> <span data-ttu-id="061fc-105">Alguns desenvolvedores de aplicativos permitem que um aplicativo seja personalizado pelo Teams administrador. O administrador pode personalizar ou renomear as propriedades do aplicativo com base nas necessidades organizacionais usando a página Gerenciar aplicativos Teams **centro** de administração.</span><span class="sxs-lookup"><span data-stu-id="061fc-105">Some app developers allow an app to be customized by the Teams admin. The admin can customize or rebrand the app properties based on the organizational needs using the Teams admin center **Manage apps** page.</span></span> <span data-ttu-id="061fc-106">Os detalhes que você pode personalizar são:</span><span class="sxs-lookup"><span data-stu-id="061fc-106">The details you can customize are:</span></span>

- <span data-ttu-id="061fc-107">Nome curto</span><span class="sxs-lookup"><span data-stu-id="061fc-107">Short name</span></span>
- <span data-ttu-id="061fc-108">Descrição curta</span><span class="sxs-lookup"><span data-stu-id="061fc-108">Short description</span></span>
- <span data-ttu-id="061fc-109">Descrição completa</span><span class="sxs-lookup"><span data-stu-id="061fc-109">Full description</span></span>
- <span data-ttu-id="061fc-110">URL da política de privacidade</span><span class="sxs-lookup"><span data-stu-id="061fc-110">Privacy policy URL</span></span>
- <span data-ttu-id="061fc-111">URL do site</span><span class="sxs-lookup"><span data-stu-id="061fc-111">Website URL</span></span>
- <span data-ttu-id="061fc-112">URL de termos de uso</span><span class="sxs-lookup"><span data-stu-id="061fc-112">Terms of use URL</span></span>
- <span data-ttu-id="061fc-113">Ícone de cor</span><span class="sxs-lookup"><span data-stu-id="061fc-113">Color icon</span></span>
- <span data-ttu-id="061fc-114">Ícone de outline</span><span class="sxs-lookup"><span data-stu-id="061fc-114">Outline icon</span></span>
- <span data-ttu-id="061fc-115">Cor do destaque</span><span class="sxs-lookup"><span data-stu-id="061fc-115">Accent color</span></span>

<span data-ttu-id="061fc-116">Consulte o [Teams de manifesto para](/microsoftteams/platform/resources/schema/manifest-schema) obter detalhes sobre os campos que você pode personalizar.</span><span class="sxs-lookup"><span data-stu-id="061fc-116">See the [Teams Manifest schema](/microsoftteams/platform/resources/schema/manifest-schema) for details about the fields that you can customize.</span></span>

> [!NOTE]
> <span data-ttu-id="061fc-117">Não há suporte para personalização de aplicativos Nuvem da Comunidade Governamental High (GCCH) ou Departamento de Defesa (DoD) neste momento.</span><span class="sxs-lookup"><span data-stu-id="061fc-117">Customizing apps isn't supported in Government Community Cloud High (GCCH) or Department of Defense (DoD) at this time.</span></span>
> <span data-ttu-id="061fc-118">Atualmente, esse recurso não está disponível para aplicativos Microsoft Teams sideload.</span><span class="sxs-lookup"><span data-stu-id="061fc-118">Currently, this feature is not available for sideloaded Microsoft Teams apps.</span></span>

## <a name="customize-the-apps-details"></a><span data-ttu-id="061fc-119">Personalizar os detalhes do aplicativo</span><span class="sxs-lookup"><span data-stu-id="061fc-119">Customize the app's details</span></span>

<span data-ttu-id="061fc-120">Para começar a personalizar um aplicativo, conclua as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="061fc-120">To start customizing an app, complete the following steps:</span></span>

1. <span data-ttu-id="061fc-121">Entre no Centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="061fc-121">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="061fc-122">Expanda **Teams Aplicativos** e selecione **Gerenciar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="061fc-122">Expand **Teams Apps** and select **Manage apps**.</span></span>
3. <span data-ttu-id="061fc-123">Verifique a **coluna Personalizável** da lista de aplicativos e classificar por aplicativos personalizáveis.</span><span class="sxs-lookup"><span data-stu-id="061fc-123">Check the **Customizable** column of the apps list and sort by apps that are customizable.</span></span>

   ![A coluna personalizar que está ordenada](media/customize-column.png)

   <span data-ttu-id="061fc-125">Há três pontos de entrada para acessar o recurso personalizar:</span><span class="sxs-lookup"><span data-stu-id="061fc-125">There are three entry points to access the customize feature:</span></span>

   - <span data-ttu-id="061fc-126">Selecione ao lado do aplicativo que você deseja personalizar e selecione **Personalizar**.</span><span class="sxs-lookup"><span data-stu-id="061fc-126">Select next to the app that you want to customize, and then select **Customize**.</span></span>

     ![A opção de seleção de personalização 1](media/select-app-to-customize1.png)

   - <span data-ttu-id="061fc-128">Selecione o nome do aplicativo e **personalizável**.</span><span class="sxs-lookup"><span data-stu-id="061fc-128">Select the app name and then **Customizable**.</span></span>

     ![A opção personalizar seleção 2](media/app-details-customizable.png)

   - <span data-ttu-id="061fc-130">Selecione o nome do aplicativo e selecione **Personalizar** no menu suspenso **Ações.**</span><span class="sxs-lookup"><span data-stu-id="061fc-130">Select the app name, and then select **Customize** from the **Actions** dropdown.</span></span>

     ![A opção personalizar seleção 3](media/customize-action-menu.png)

4. <span data-ttu-id="061fc-132">Expanda **a seção Detalhes** e personalize os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="061fc-132">Expand the **Details** section and customize the following fields:</span></span>

    - <span data-ttu-id="061fc-133">Nome curto</span><span class="sxs-lookup"><span data-stu-id="061fc-133">Short name</span></span>
    - <span data-ttu-id="061fc-134">Descrição curta</span><span class="sxs-lookup"><span data-stu-id="061fc-134">Short description</span></span>
    - <span data-ttu-id="061fc-135">Descrição completa</span><span class="sxs-lookup"><span data-stu-id="061fc-135">Full description</span></span>
    - <span data-ttu-id="061fc-136">Site</span><span class="sxs-lookup"><span data-stu-id="061fc-136">Website</span></span>
    - <span data-ttu-id="061fc-137">URL da política de privacidade</span><span class="sxs-lookup"><span data-stu-id="061fc-137">Privacy policy URL</span></span>
    - <span data-ttu-id="061fc-138">URL de termos de uso</span><span class="sxs-lookup"><span data-stu-id="061fc-138">Terms of use URL</span></span>

   ![As configurações de personalização](media/customize-settings.png)

> [!Note]
> <span data-ttu-id="061fc-140">Somente os campos atribuídos pelo desenvolvedor de aplicativos como personalizáveis estarão visíveis.</span><span class="sxs-lookup"><span data-stu-id="061fc-140">Only the fields that the app developer has assigned as customizable will be visible.</span></span>

5. <span data-ttu-id="061fc-141">Expanda **a seção Ícone.**</span><span class="sxs-lookup"><span data-stu-id="061fc-141">Expand the **Icon** section.</span></span>

   <span data-ttu-id="061fc-142">a.</span><span class="sxs-lookup"><span data-stu-id="061fc-142">a.</span></span> <span data-ttu-id="061fc-143">Upload um ícone.</span><span class="sxs-lookup"><span data-stu-id="061fc-143">Upload an icon.</span></span> <span data-ttu-id="061fc-144">Use um ícone de cor completa (192 x 192) pixel no formato PNG.</span><span class="sxs-lookup"><span data-stu-id="061fc-144">Use one full-color icon (192x192) pixel in PNG format.</span></span>

   <span data-ttu-id="061fc-145">b.</span><span class="sxs-lookup"><span data-stu-id="061fc-145">b.</span></span> <span data-ttu-id="061fc-146">Escolha uma cor de contorno de ícone.</span><span class="sxs-lookup"><span data-stu-id="061fc-146">Choose an icon outline color.</span></span> <span data-ttu-id="061fc-147">Use um pixel de contorno transparente (32x32) no formato PNG.</span><span class="sxs-lookup"><span data-stu-id="061fc-147">Use one transparent outline (32x32) pixel in PNG format.</span></span>

   <span data-ttu-id="061fc-148">c.</span><span class="sxs-lookup"><span data-stu-id="061fc-148">c.</span></span> <span data-ttu-id="061fc-149">Selecione uma cor de destaque do aplicativo que corresponde ao ícone.</span><span class="sxs-lookup"><span data-stu-id="061fc-149">Select an app accent color that matches the icon.</span></span>

    ![Personalizar as opções de cores do painel de ícones](media/customize-app-colors.png)

6. <span data-ttu-id="061fc-151">Depois que seu aplicativo tiver sido personalizado, selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="061fc-151">Once your app has been customized, select **Apply**.</span></span>

7. <span data-ttu-id="061fc-152">Selecione **Publicar** para publicar o aplicativo personalizado.</span><span class="sxs-lookup"><span data-stu-id="061fc-152">Select **Publish** to publish the customized app.</span></span>

   <span data-ttu-id="061fc-153">O aplicativo personalizado agora está listado na página **Gerenciar aplicativos.**</span><span class="sxs-lookup"><span data-stu-id="061fc-153">The customized app is now listed in your **Manage apps** page.</span></span> <span data-ttu-id="061fc-154">Você terá apenas uma versão do aplicativo, já que a personalização dos recursos do aplicativo não cria uma cópia do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="061fc-154">You'll have only one version of the app, since customizing the app features doesn't create a copy of the app.</span></span>

<span data-ttu-id="061fc-155">Agora, Teams usuários finais podem abrir o cliente Teams para ver o aplicativo personalizado.</span><span class="sxs-lookup"><span data-stu-id="061fc-155">Now your Teams end users can open their Teams client to see the customized app.</span></span>

   ![Aplicativo personalizado no Teams cliente](media/contoso-app.png)

### <a name="special-considerations-for-customizing-an-app"></a><span data-ttu-id="061fc-157">Considerações especiais para personalizar um aplicativo</span><span class="sxs-lookup"><span data-stu-id="061fc-157">Special considerations for customizing an app</span></span>

<span data-ttu-id="061fc-158">A observação a seguir inclui detalhes importantes sobre como personalizar um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="061fc-158">The following note includes important details about customizing an app.</span></span>

> [!Note]
> - <span data-ttu-id="061fc-159">Ao personalizar aplicativos e qualquer descrição relacionada a um aplicativo, certifique-se de seguir quaisquer diretrizes de personalização, se fornecidos pelo editor de aplicativos em sua documentação ou termos de uso.</span><span class="sxs-lookup"><span data-stu-id="061fc-159">When you customize apps, and any description related to an app, ensure that you follow any customization guidelines if provided by the app publisher in their documentation or terms of use.</span></span> <span data-ttu-id="061fc-160">Você também é responsável por respeitar os direitos de outras pessoas em relação a quaisquer imagens de terceiros que você possa usar.</span><span class="sxs-lookup"><span data-stu-id="061fc-160">You're also responsible for respecting the rights of others regarding any third-party images you might use.</span></span>
> - <span data-ttu-id="061fc-161">Os dados de personalização fornecidos pelo administrador são armazenados na região mais próxima.</span><span class="sxs-lookup"><span data-stu-id="061fc-161">Admin-provided customization data is stored in the nearest region.</span></span>
> - <span data-ttu-id="061fc-162">Você é responsável por garantir que os links para termos de uso ou política de privacidade sejam válidos.</span><span class="sxs-lookup"><span data-stu-id="061fc-162">You are responsible for ensuring that links to terms of use or privacy policy are valid.</span></span>
> - <span data-ttu-id="061fc-163">Caso o editor de aplicativos não permita mais que um campo seja personalizável, uma mensagem será exibida na página de detalhes do aplicativo notificando o administrador sobre os campos que não podem mais ser personalizados.</span><span class="sxs-lookup"><span data-stu-id="061fc-163">In case the app publisher no longer allows a field to be customizable, a message appears on the app details page notifying the admin about the fields that can't be customized any longer.</span></span> <span data-ttu-id="061fc-164">Todas as alterações feitas nesse campo serão revertidas para os valores originais.</span><span class="sxs-lookup"><span data-stu-id="061fc-164">All the changes made to that field will be reverted to the original values.</span></span>
> - <span data-ttu-id="061fc-165">Recomendamos testar as alterações de personalização do aplicativo em um Teams de teste antes de fazer essas alterações em seu ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="061fc-165">We recommend testing app customization changes in a Teams test tenant before making these changes in your production environment.</span></span>
> - <span data-ttu-id="061fc-166">As alterações na identidade visual podem exigir até 24 horas para os usuários verem as alterações.</span><span class="sxs-lookup"><span data-stu-id="061fc-166">Changes to branding might require up to 24 hours for the users to see the changes.</span></span>

## <a name="review-app-details"></a><span data-ttu-id="061fc-167">Revisar detalhes do aplicativo</span><span class="sxs-lookup"><span data-stu-id="061fc-167">Review app details</span></span>

<span data-ttu-id="061fc-168">Talvez você queira ver os detalhes do aplicativo para revisar as informações.</span><span class="sxs-lookup"><span data-stu-id="061fc-168">You might want to see the app details to review the information.</span></span>

1. <span data-ttu-id="061fc-169">Entre no Centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="061fc-169">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="061fc-170">Expanda **aplicativos Teams** e selecione **Gerenciar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="061fc-170">Expand **Teams apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="061fc-171">Selecione o nome do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="061fc-171">Select the app name.</span></span>

4. <span data-ttu-id="061fc-172">Exibir os detalhes do aplicativo, incluindo o nome do aplicativo original **Nome curto do editor**.</span><span class="sxs-lookup"><span data-stu-id="061fc-172">View the app details, including the original app name **Short name from publisher**.</span></span>

   ![Personalizar o nome do aplicativo do painel de ícones](media/original-app-version.png)

   <span data-ttu-id="061fc-174">O **nome curto do campo editor** só será visível se você tiver alterado o nome curto do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="061fc-174">The **Short name from publisher** field is only visible if you've changed the app's short name.</span></span>

## <a name="reset-app-details-to-default"></a><span data-ttu-id="061fc-175">Redefinir os detalhes do aplicativo como padrão</span><span class="sxs-lookup"><span data-stu-id="061fc-175">Reset app details to default</span></span>

<span data-ttu-id="061fc-176">A qualquer momento, você pode redefinir os detalhes do aplicativo para as configurações originais.</span><span class="sxs-lookup"><span data-stu-id="061fc-176">At any time, you can reset the app details to the original settings.</span></span>

1. <span data-ttu-id="061fc-177">Entre no Centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="061fc-177">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="061fc-178">Expanda **Teams Aplicativos** e selecione **Gerenciar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="061fc-178">Expand **Teams Apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="061fc-179">Selecione o nome do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="061fc-179">Select the app name.</span></span>

4. <span data-ttu-id="061fc-180">Selecione **Redefinir como padrão** no menu suspenso **Ações.**</span><span class="sxs-lookup"><span data-stu-id="061fc-180">Select **Reset to default** from the **Actions** dropdown.</span></span>

   ![Selecione redefinir para o padrão realçado](media/select-reset.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="061fc-182">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="061fc-182">Frequently asked questions</span></span>

<span data-ttu-id="061fc-183">**Quanto tempo levará para meus usuários verem o aplicativo personalizado?**</span><span class="sxs-lookup"><span data-stu-id="061fc-183">**How long will it take for my users to see the customized app?**</span></span>

<span data-ttu-id="061fc-184">Embora o administrador possa ver imediatamente as alterações no Teams Admin Center, pode levar até 24 horas para os usuários finais verem as alterações.</span><span class="sxs-lookup"><span data-stu-id="061fc-184">Although the admin can immediately see the changes in Teams Admin Center, it might take up to 24 hours for the end users to see the changes.</span></span>  

<span data-ttu-id="061fc-185">**O provedor de aplicativos pode personalizar o aplicativo para seus clientes?**</span><span class="sxs-lookup"><span data-stu-id="061fc-185">**Can the app provider customize the app for its customers?**</span></span>

 <span data-ttu-id="061fc-186">Não, o administrador de um locatário precisa personalizar o aplicativo para seu locatário usando o Teams Admin Center.</span><span class="sxs-lookup"><span data-stu-id="061fc-186">No, the admin of a tenant needs to customize the app for their tenant using the Teams Admin Center.</span></span>

<span data-ttu-id="061fc-187">**O aplicativo personalizado será implantado automaticamente para substituir meu aplicativo personalizado atual em um locatário?**</span><span class="sxs-lookup"><span data-stu-id="061fc-187">**Will the customized app automatically get deployed to replace my current custom app in a tenant?**</span></span>

<span data-ttu-id="061fc-188">Não, os administradores de locatários terão que remover manualmente qualquer aplicativo personalizado e publicar a versão personalizada do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="061fc-188">No, the tenant admins will have to manually remove any custom app and publish the customized version of the app.</span></span> <span data-ttu-id="061fc-189">Se você tiver personalizado um aplicativo e publicado como um aplicativo personalizado, o novo aplicativo personalizado usando o recurso de personalização do aplicativo não substituirá o aplicativo personalizado atual.</span><span class="sxs-lookup"><span data-stu-id="061fc-189">If you have customized an app and published it as a custom app, the new app customized using the app customization feature won't replace the current custom app.</span></span>  

<span data-ttu-id="061fc-190">**O relatório de uso do aplicativo também mostrará os valores personalizados, como nome curto personalizado?**</span><span class="sxs-lookup"><span data-stu-id="061fc-190">**Will the app usage report also show the customized values such as customized short name?**</span></span>

 <span data-ttu-id="061fc-191">Não, o relatório de uso do aplicativo ainda mostrará o nome original do aplicativo enviado do editor.</span><span class="sxs-lookup"><span data-stu-id="061fc-191">No, the app usage report will still show the original name of the app sent from the publisher.</span></span>

<span data-ttu-id="061fc-192">**Quais aplicativos posso personalizar usando o recurso de personalização do aplicativo?**</span><span class="sxs-lookup"><span data-stu-id="061fc-192">**Which apps can I customize using the app customization feature?**</span></span>

<span data-ttu-id="061fc-193">Você só pode personalizar aplicativos que tenham permissão para serem personalizáveis pelo editor de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="061fc-193">You can only customize apps that have been allowed to be customizable by the app publisher.</span></span> <span data-ttu-id="061fc-194">O editor de aplicativos precisará optar por permitir que seus clientes personalizem o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="061fc-194">The app publisher will need to opt in to allow its customers to customize the app.</span></span>

<span data-ttu-id="061fc-195">**As propriedades personalizadas aparecerão na tela de consentimento de permissão do gráfico?**</span><span class="sxs-lookup"><span data-stu-id="061fc-195">**Will the customized properties show up on the graph permission consent screen?**</span></span>

<span data-ttu-id="061fc-196">Não, a tela de consentimento de permissão ainda mostrará o valor original enviado pelo editor.</span><span class="sxs-lookup"><span data-stu-id="061fc-196">No, the permission consent screen will still show the original value sent by the publisher.</span></span>

## <a name="related-article"></a><span data-ttu-id="061fc-197">Artigo relacionado</span><span class="sxs-lookup"><span data-stu-id="061fc-197">Related article</span></span>

- [<span data-ttu-id="061fc-198">Gerenciar aplicativos</span><span class="sxs-lookup"><span data-stu-id="061fc-198">Manage apps</span></span>](manage-apps.md)
- [<span data-ttu-id="061fc-199">Personalizar sua loja de aplicativos</span><span class="sxs-lookup"><span data-stu-id="061fc-199">Customize your app store</span></span>](customize-your-app-store.md)
- [<span data-ttu-id="061fc-200">Renomear seus aplicativos</span><span class="sxs-lookup"><span data-stu-id="061fc-200">Rebrand your apps</span></span>](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/rebrand-apps-to-your-own-organization-s-branding-with-app/ba-p/2376296)
