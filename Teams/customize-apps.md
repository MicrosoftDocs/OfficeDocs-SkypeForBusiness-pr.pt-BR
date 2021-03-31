---
title: Personalizar aplicativos da Microsoft no Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: vaagarw
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
description: Saiba como personalizar aplicativos no Microsoft Teams.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: b2e924da384b5bff54e63872aa7026d2da456311
ms.sourcegitcommit: 88cb2362d07bca88402cf771a6f366c972e26001
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "51471495"
---
# <a name="customize-apps-in-microsoft-teams"></a><span data-ttu-id="0f48a-103">Personalizar aplicativos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0f48a-103">Customize apps in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

 <span data-ttu-id="0f48a-104">O Microsoft Teams fornece personalização de aplicativos para aprimorar a experiência do Teams.</span><span class="sxs-lookup"><span data-stu-id="0f48a-104">Microsoft Teams provides app customization to enhance the Teams experience.</span></span> <span data-ttu-id="0f48a-105">Alguns desenvolvedores de aplicativos permitem que um aplicativo seja personalizado pelo administrador do Teams. O administrador pode personalizar ou renomear as propriedades do aplicativo com base nas necessidades organizacionais usando a página Gerenciar **aplicativos** do Centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="0f48a-105">Some app developers allow an app to be customized by the Teams admin. The admin can customize or rebrand the app properties based on the organizational needs using the Teams admin center **Manage apps** page.</span></span> <span data-ttu-id="0f48a-106">Os detalhes que você pode personalizar são:</span><span class="sxs-lookup"><span data-stu-id="0f48a-106">The details you can customize are:</span></span>

- <span data-ttu-id="0f48a-107">Nome curto</span><span class="sxs-lookup"><span data-stu-id="0f48a-107">Short name</span></span>
- <span data-ttu-id="0f48a-108">Descrição curta</span><span class="sxs-lookup"><span data-stu-id="0f48a-108">Short description</span></span>
- <span data-ttu-id="0f48a-109">Descrição completa</span><span class="sxs-lookup"><span data-stu-id="0f48a-109">Full description</span></span>
- <span data-ttu-id="0f48a-110">URL da política de privacidade</span><span class="sxs-lookup"><span data-stu-id="0f48a-110">Privacy policy URL</span></span>
- <span data-ttu-id="0f48a-111">URL do site</span><span class="sxs-lookup"><span data-stu-id="0f48a-111">Website URL</span></span>
- <span data-ttu-id="0f48a-112">URL de termos de uso</span><span class="sxs-lookup"><span data-stu-id="0f48a-112">Terms of use URL</span></span>
- <span data-ttu-id="0f48a-113">Ícone de cor</span><span class="sxs-lookup"><span data-stu-id="0f48a-113">Color icon</span></span>
- <span data-ttu-id="0f48a-114">Ícone de outline</span><span class="sxs-lookup"><span data-stu-id="0f48a-114">Outline icon</span></span>
- <span data-ttu-id="0f48a-115">Cor do destaque</span><span class="sxs-lookup"><span data-stu-id="0f48a-115">Accent color</span></span>

<span data-ttu-id="0f48a-116">Consulte o [esquema de Manifesto do Teams](https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema) para obter detalhes sobre os campos que você pode personalizar.</span><span class="sxs-lookup"><span data-stu-id="0f48a-116">See the [Teams Manifest schema](https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema) for details about the fields that you can customize.</span></span>

## <a name="customize-the-apps-details"></a><span data-ttu-id="0f48a-117">Personalizar os detalhes do aplicativo</span><span class="sxs-lookup"><span data-stu-id="0f48a-117">Customize the app's details</span></span>

<span data-ttu-id="0f48a-118">Para começar a personalizar um aplicativo, conclua as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="0f48a-118">To start customizing an app, complete the following steps:</span></span>

1. <span data-ttu-id="0f48a-119">Entre no Centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="0f48a-119">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="0f48a-120">Expanda **Aplicativos do Teams** e selecione **Gerenciar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="0f48a-120">Expand **Teams Apps** and select **Manage apps**.</span></span>
3. <span data-ttu-id="0f48a-121">Verifique a **coluna Personalizável** da lista de aplicativos e classificar por aplicativos personalizáveis.</span><span class="sxs-lookup"><span data-stu-id="0f48a-121">Check the **Customizable** column of the apps list and sort by apps that are customizable.</span></span>

   ![A coluna personalizar que está ordenada](media/customize-column.png)

   <span data-ttu-id="0f48a-123">Há três pontos de entrada para acessar o recurso personalizar:</span><span class="sxs-lookup"><span data-stu-id="0f48a-123">There are three entry points to access the customize feature:</span></span>

   - <span data-ttu-id="0f48a-124">Selecione ao lado do aplicativo que você deseja personalizar e selecione **Personalizar**.</span><span class="sxs-lookup"><span data-stu-id="0f48a-124">Select next to the app that you want to customize, and then select **Customize**.</span></span>

     ![A opção de seleção de personalização 1](media/select-app-to-customize1.png)

   - <span data-ttu-id="0f48a-126">Selecione o nome do aplicativo e **personalizável**.</span><span class="sxs-lookup"><span data-stu-id="0f48a-126">Select the app name and then **Customizable**.</span></span>

     ![A opção personalizar seleção 2](media/app-details-customizable.png)

   - <span data-ttu-id="0f48a-128">Selecione o nome do aplicativo e selecione **Personalizar** no menu suspenso **Ações.**</span><span class="sxs-lookup"><span data-stu-id="0f48a-128">Select the app name, and then select **Customize** from the **Actions** dropdown.</span></span>

     ![A opção personalizar seleção 3](media/customize-action-menu.png)

4. <span data-ttu-id="0f48a-130">Expanda **a seção Detalhes** e personalize os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="0f48a-130">Expand the **Details** section and customize the following fields:</span></span>

    - <span data-ttu-id="0f48a-131">Nome curto</span><span class="sxs-lookup"><span data-stu-id="0f48a-131">Short name</span></span>
    - <span data-ttu-id="0f48a-132">Descrição curta</span><span class="sxs-lookup"><span data-stu-id="0f48a-132">Short description</span></span>
    - <span data-ttu-id="0f48a-133">Descrição completa</span><span class="sxs-lookup"><span data-stu-id="0f48a-133">Full description</span></span>
    - <span data-ttu-id="0f48a-134">Site</span><span class="sxs-lookup"><span data-stu-id="0f48a-134">Website</span></span>
    - <span data-ttu-id="0f48a-135">URL da política de privacidade</span><span class="sxs-lookup"><span data-stu-id="0f48a-135">Privacy policy URL</span></span>
    - <span data-ttu-id="0f48a-136">URL de termos de uso</span><span class="sxs-lookup"><span data-stu-id="0f48a-136">Terms of use URL</span></span>

   ![As configurações de personalização](media/customize-settings.png)

> [!Note]
> <span data-ttu-id="0f48a-138">Somente os campos atribuídos pelo desenvolvedor de aplicativos como personalizáveis estarão visíveis.</span><span class="sxs-lookup"><span data-stu-id="0f48a-138">Only the fields that the app developer has assigned as customizable will be visible.</span></span>

5. <span data-ttu-id="0f48a-139">Expanda **a seção Ícone.**</span><span class="sxs-lookup"><span data-stu-id="0f48a-139">Expand the **Icon** section.</span></span>

   <span data-ttu-id="0f48a-140">a.</span><span class="sxs-lookup"><span data-stu-id="0f48a-140">a.</span></span> <span data-ttu-id="0f48a-141">Carregar um ícone.</span><span class="sxs-lookup"><span data-stu-id="0f48a-141">Upload an icon.</span></span> <span data-ttu-id="0f48a-142">Use um ícone de cor completa (192 x 192) pixel no formato PNG.</span><span class="sxs-lookup"><span data-stu-id="0f48a-142">Use one full-color icon (192x192) pixel in PNG format.</span></span>

   <span data-ttu-id="0f48a-143">b.</span><span class="sxs-lookup"><span data-stu-id="0f48a-143">b.</span></span> <span data-ttu-id="0f48a-144">Escolha uma cor de contorno de ícone.</span><span class="sxs-lookup"><span data-stu-id="0f48a-144">Choose an icon outline color.</span></span> <span data-ttu-id="0f48a-145">Use um pixel de contorno transparente (32x32) no formato PNG.</span><span class="sxs-lookup"><span data-stu-id="0f48a-145">Use one transparent outline (32x32) pixel in PNG format.</span></span>

   <span data-ttu-id="0f48a-146">c.</span><span class="sxs-lookup"><span data-stu-id="0f48a-146">c.</span></span> <span data-ttu-id="0f48a-147">Selecione uma cor de destaque do aplicativo que corresponde ao ícone.</span><span class="sxs-lookup"><span data-stu-id="0f48a-147">Select an app accent color that matches the icon.</span></span>

    ![Personalizar as opções de cores do painel de ícones](media/customize-app-colors.png)

6. <span data-ttu-id="0f48a-149">Depois que seu aplicativo tiver sido personalizado, selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="0f48a-149">Once your app has been customized, select **Apply**.</span></span>

7. <span data-ttu-id="0f48a-150">Selecione **Publicar** para publicar o aplicativo personalizado.</span><span class="sxs-lookup"><span data-stu-id="0f48a-150">Select **Publish** to publish the customized app.</span></span>

   <span data-ttu-id="0f48a-151">O aplicativo personalizado agora está listado na página **Gerenciar aplicativos.**</span><span class="sxs-lookup"><span data-stu-id="0f48a-151">The customized app is now listed in your **Manage apps** page.</span></span> <span data-ttu-id="0f48a-152">Você terá apenas uma versão do aplicativo, já que a personalização dos recursos do aplicativo não cria uma cópia do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0f48a-152">You'll have only one version of the app, since customizing the app features doesn't create a copy of the app.</span></span>

<span data-ttu-id="0f48a-153">Agora, os usuários finais do Teams podem abrir o cliente do Teams para ver o aplicativo personalizado.</span><span class="sxs-lookup"><span data-stu-id="0f48a-153">Now your Teams end users can open their Teams client to see the customized app.</span></span>

   ![Aplicativo personalizado no cliente do Teams](media/find-customized-app.png)

### <a name="special-considerations-for-customizing-an-app"></a><span data-ttu-id="0f48a-155">Considerações especiais para personalizar um aplicativo</span><span class="sxs-lookup"><span data-stu-id="0f48a-155">Special considerations for customizing an app</span></span>

<span data-ttu-id="0f48a-156">A observação a seguir inclui detalhes importantes sobre como personalizar um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0f48a-156">The following note includes important details about customizing an app.</span></span>

> [!Note]
> - <span data-ttu-id="0f48a-157">Ao personalizar aplicativos e qualquer descrição relacionada a um aplicativo, certifique-se de seguir as Diretrizes de Personalização fornecidas pelo editor de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="0f48a-157">When you customize apps and any description related to an app, ensure that you follow the Customization Guidelines provided by the app publisher.</span></span> <span data-ttu-id="0f48a-158">Você é responsável por respeitar os direitos de outras pessoas em relação a imagens de terceiros que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="0f48a-158">You're responsible for respecting the rights of others regarding third-party images you might use.</span></span>
> - <span data-ttu-id="0f48a-159">Os dados de personalização fornecidos pelo administrador são armazenados no Store de Configurações na região mais próxima.</span><span class="sxs-lookup"><span data-stu-id="0f48a-159">Admin-provided customization data is stored in the Settings Store in the nearest region.</span></span> <span data-ttu-id="0f48a-160">Não está necessariamente em qualquer implantação do GoLocal Cloud Teams.</span><span class="sxs-lookup"><span data-stu-id="0f48a-160">It isn't necessarily in any GoLocal Cloud Teams deployment.</span></span>
> - <span data-ttu-id="0f48a-161">Você é responsável por garantir que os links para os termos de uso ou política de privacidade sejam válidos.</span><span class="sxs-lookup"><span data-stu-id="0f48a-161">You're responsible for ensuring that the links to the terms of use or privacy policy are valid.</span></span> <span data-ttu-id="0f48a-162">Você deve fornecer o gerenciamento apropriado das alterações feitas (ou permitir que sejam feitas) aos metadados do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0f48a-162">You must provide appropriate management of the changes they make (or allow to be made) to app metadata.</span></span> <span data-ttu-id="0f48a-163">A implementação atual fornecerá suporte para ajudá-lo a reverter para URLs fornecidas pelo desenvolvedor.</span><span class="sxs-lookup"><span data-stu-id="0f48a-163">Current implementation will provide support to help you to revert to developer-provided URLs.</span></span> <span data-ttu-id="0f48a-164">Você pode não configurar o aplicativo sem uma URL (se o aplicativo permitir a personalização das URLs).</span><span class="sxs-lookup"><span data-stu-id="0f48a-164">You may not configure the app without a URL (if the app allows customization of the URLs).</span></span>
> - <span data-ttu-id="0f48a-165">Caso o editor de aplicativos não permita mais que um campo seja personalizável, uma mensagem será exibida na página de detalhes do aplicativo notificando o administrador sobre os campos que não podem mais ser personalizados.</span><span class="sxs-lookup"><span data-stu-id="0f48a-165">In case the app publisher no longer allows a field to be customizable, a message appears on the app details page notifying the admin about the fields that can't be customized any longer.</span></span> <span data-ttu-id="0f48a-166">Todas as alterações feitas nesse campo serão revertidas para os valores originais.</span><span class="sxs-lookup"><span data-stu-id="0f48a-166">All the changes made to that field will be reverted to the original values.</span></span>
> - <span data-ttu-id="0f48a-167">As alterações na identidade visual podem exigir até 24 horas para os usuários verem as alterações.</span><span class="sxs-lookup"><span data-stu-id="0f48a-167">Changes to branding might require up to 24 hours for the users to see the changes.</span></span>

## <a name="review-app-details"></a><span data-ttu-id="0f48a-168">Revisar detalhes do aplicativo</span><span class="sxs-lookup"><span data-stu-id="0f48a-168">Review app details</span></span>

<span data-ttu-id="0f48a-169">Talvez você queira ver os detalhes do aplicativo para revisar as informações.</span><span class="sxs-lookup"><span data-stu-id="0f48a-169">You might want to see the app details to review the information.</span></span>

1. <span data-ttu-id="0f48a-170">Entre no Centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="0f48a-170">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="0f48a-171">Expanda **aplicativos Teams** e selecione **Gerenciar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="0f48a-171">Expand **Teams apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="0f48a-172">Selecione o nome do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0f48a-172">Select the app name.</span></span>

4. <span data-ttu-id="0f48a-173">Exibir os detalhes do aplicativo, incluindo o nome do aplicativo original **Nome curto do editor**.</span><span class="sxs-lookup"><span data-stu-id="0f48a-173">View the app details, including the original app name **Short name from publisher**.</span></span>

   ![Personalizar o nome do aplicativo do painel de ícones](media/app-details-original-name.png)

   <span data-ttu-id="0f48a-175">O **nome curto do campo editor** só será visível se você tiver alterado o nome curto do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0f48a-175">The **Short name from publisher** field is only visible if you've changed the app's short name.</span></span>

## <a name="reset-app-details-to-default"></a><span data-ttu-id="0f48a-176">Redefinir os detalhes do aplicativo como padrão</span><span class="sxs-lookup"><span data-stu-id="0f48a-176">Reset app details to default</span></span>

<span data-ttu-id="0f48a-177">A qualquer momento, você pode redefinir os detalhes do aplicativo para as configurações originais.</span><span class="sxs-lookup"><span data-stu-id="0f48a-177">At any time, you can reset the app details to the original settings.</span></span>

1. <span data-ttu-id="0f48a-178">Entre no Centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="0f48a-178">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="0f48a-179">Expanda **Aplicativos do Teams** e selecione **Gerenciar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="0f48a-179">Expand **Teams Apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="0f48a-180">Selecione o nome do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0f48a-180">Select the app name.</span></span>

4. <span data-ttu-id="0f48a-181">Selecione **Redefinir como padrão** no menu suspenso **Ações.**</span><span class="sxs-lookup"><span data-stu-id="0f48a-181">Select **Reset to default** from the **Actions** dropdown.</span></span>

   ![Selecione redefinir para o padrão realçado](media/select-reset.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="0f48a-183">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="0f48a-183">Frequently asked questions</span></span>

<span data-ttu-id="0f48a-184">**Quanto tempo levará para meus usuários verem o aplicativo personalizado?**</span><span class="sxs-lookup"><span data-stu-id="0f48a-184">**How long will it take for my users to see the customized app?**</span></span>

<span data-ttu-id="0f48a-185">Embora o administrador possa ver imediatamente as alterações no Centro de Administração do Teams, pode levar até 24 horas para os usuários finais verem as alterações.</span><span class="sxs-lookup"><span data-stu-id="0f48a-185">Although the admin can immediately see the changes in Teams Admin Center, it might take up to 24 hours for the end users to see the changes.</span></span>  

<span data-ttu-id="0f48a-186">**O provedor de aplicativos pode personalizar o aplicativo para seus clientes?**</span><span class="sxs-lookup"><span data-stu-id="0f48a-186">**Can the app provider customize the app for its customers?**</span></span>

 <span data-ttu-id="0f48a-187">Não, o administrador de um locatário precisa personalizar o aplicativo para seu locatário usando o Centro de Administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="0f48a-187">No, the admin of a tenant needs to customize the app for their tenant using the Teams Admin Center.</span></span>

<span data-ttu-id="0f48a-188">**O aplicativo personalizado será implantado automaticamente para substituir meu aplicativo personalizado atual em um locatário?**</span><span class="sxs-lookup"><span data-stu-id="0f48a-188">**Will the customized app automatically get deployed to replace my current custom app in a tenant?**</span></span>

<span data-ttu-id="0f48a-189">Não, os administradores de locatários terão que remover manualmente qualquer aplicativo personalizado e publicar a versão personalizada do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0f48a-189">No, the tenant admins will have to manually remove any custom app and publish the customized version of the app.</span></span> <span data-ttu-id="0f48a-190">Se você tiver personalizado um aplicativo e publicado como um aplicativo personalizado, o novo aplicativo personalizado usando o recurso de personalização do aplicativo não substituirá o aplicativo personalizado atual.</span><span class="sxs-lookup"><span data-stu-id="0f48a-190">If you have customized an app and published it as a custom app, the new app customized using the app customization feature won't replace the current custom app.</span></span>  

<span data-ttu-id="0f48a-191">**O relatório de uso do aplicativo também mostrará os valores personalizados, como nome curto personalizado?**</span><span class="sxs-lookup"><span data-stu-id="0f48a-191">**Will the app usage report also show the customized values such as customized short name?**</span></span>

 <span data-ttu-id="0f48a-192">Não, o relatório de uso do aplicativo ainda mostrará o nome original do aplicativo enviado do editor.</span><span class="sxs-lookup"><span data-stu-id="0f48a-192">No, the app usage report will still show the original name of the app sent from the publisher.</span></span>

<span data-ttu-id="0f48a-193">**Quais aplicativos posso personalizar usando o recurso de personalização do aplicativo?**</span><span class="sxs-lookup"><span data-stu-id="0f48a-193">**Which apps can I customize using the app customization feature?**</span></span>

<span data-ttu-id="0f48a-194">Você só pode personalizar aplicativos que tenham permissão para serem personalizáveis pelo editor de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="0f48a-194">You can only customize apps that have been allowed to be customizable by the app publisher.</span></span> <span data-ttu-id="0f48a-195">O editor de aplicativos precisará optar por permitir que seus clientes personalizem o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0f48a-195">The app publisher will need to opt in to allow its customers to customize the app.</span></span>

<span data-ttu-id="0f48a-196">**As propriedades personalizadas aparecerão na tela de consentimento de permissão do gráfico?**</span><span class="sxs-lookup"><span data-stu-id="0f48a-196">**Will the customized properties show up on the graph permission consent screen?**</span></span>

<span data-ttu-id="0f48a-197">Não, a tela de consentimento de permissão ainda mostrará o valor original enviado pelo editor.</span><span class="sxs-lookup"><span data-stu-id="0f48a-197">No, the permission consent screen will still show the original value sent by the publisher.</span></span>

## <a name="related-article"></a><span data-ttu-id="0f48a-198">Artigo relacionado</span><span class="sxs-lookup"><span data-stu-id="0f48a-198">Related article</span></span>

- [<span data-ttu-id="0f48a-199">Gerenciar aplicativos</span><span class="sxs-lookup"><span data-stu-id="0f48a-199">Manage apps</span></span>](manage-apps.md)
- [<span data-ttu-id="0f48a-200">Personalizar sua loja de aplicativos</span><span class="sxs-lookup"><span data-stu-id="0f48a-200">Customize your app store</span></span>](customize-your-app-store.md)
