---
title: Recursos do Microsoft Teams para administradores de Educação
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Passo a passo do licenciamento do Microsoft Teams para EDU.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
appliesto:
- Microsoft Teams
ms.openlocfilehash: 83448f32ddfc96800a14b5a599ef9cb7af52bb9b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119230"
---
# <a name="assign-microsoft-teams-licenses-for-edu"></a><span data-ttu-id="ca313-103">Atribuir licenças do Microsoft Teams para EDU</span><span class="sxs-lookup"><span data-stu-id="ca313-103">Assign Microsoft Teams licenses for EDU</span></span>

<span data-ttu-id="ca313-104">O Microsoft Teams é um hub digital que reúne conversas, conteúdo e os aplicativos em um só lugar.</span><span class="sxs-lookup"><span data-stu-id="ca313-104">Microsoft Teams is a digital hub that brings conversations, content, and apps together in one place.</span></span> <span data-ttu-id="ca313-105">Como ele foi criado no Office 365, as escolas se beneficiam da integração com seus aplicativos e serviços do Office conhecidos.</span><span class="sxs-lookup"><span data-stu-id="ca313-105">Because it's built on Office 365, schools benefit from integration with their familiar Office apps and services.</span></span> <span data-ttu-id="ca313-106">Sua instituição pode usar o Microsoft Teams para criar salas de aula colaborativas, conectar-se a comunidades de aprendizagem profissional e comunicar-se com a equipe da escola, tudo em uma única experiência no Office 365 para educação.</span><span class="sxs-lookup"><span data-stu-id="ca313-106">Your institution can use Microsoft Teams to create collaborative classrooms, connect in professional learning communities, and communicate with school staff all from a single experience in Office 365 for Education.</span></span>

<span data-ttu-id="ca313-107">Para começar, os administradores de TI precisam usar o Centro de Administração do Microsoft 365 para [habilitar o Microsoft Teams para a sua escola](/microsoft-365/education/intune-edu-trial/enable-microsoft-teams).</span><span class="sxs-lookup"><span data-stu-id="ca313-107">To get started, IT administrators need to use the Microsoft 365 Admin Center to [enable Microsoft Teams for your school](/microsoft-365/education/intune-edu-trial/enable-microsoft-teams).</span></span>
<span data-ttu-id="ca313-108">Quando concluído, você deve atribuir licenças às contas dos usuários para que seus professores, funcionários e alunos possam acessar os serviços do Office 365, como o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ca313-108">Once complete, you must assign licenses to user accounts so your faculty, staff, and students can access Office 365 services, such as Microsoft Teams.</span></span>

<span data-ttu-id="ca313-109">Você pode atribuir licenças a contas de usuários individualmente ou automaticamente por meio da associação de grupo.</span><span class="sxs-lookup"><span data-stu-id="ca313-109">You can assign licenses to user accounts either individually or automatically through group membership.</span></span> <span data-ttu-id="ca313-110">Este artigo o orientará sobre como atribuir licenças do Office 365 a uma pessoa ou um pequeno conjunto de contas de usuários por meio do centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ca313-110">This article will walk you through how to assign Office 365 licenses to an individual or a small set of user accounts via the Microsoft 365 admin center.</span></span> <span data-ttu-id="ca313-111">Para atribuir licenças automaticamente por meio da associação de grupo, confira um dos nossos artigos de suporte:</span><span class="sxs-lookup"><span data-stu-id="ca313-111">To assign licenses automatically through group membership, see one of our supporting articles:</span></span>

- [<span data-ttu-id="ca313-112">Office 365 Powershell</span><span class="sxs-lookup"><span data-stu-id="ca313-112">Office 365 Powershell</span></span>](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)
- [<span data-ttu-id="ca313-113">Licenciamento baseado em grupo no Active Directory</span><span class="sxs-lookup"><span data-stu-id="ca313-113">Group-based Licensing in Active Directory</span></span>](/azure/active-directory/users-groups-roles/licensing-groups-assign)

<span data-ttu-id="ca313-114">Você pode atribuir licenças a usuários na página de **Licenças** ou na página de **Usuários Ativos**.</span><span class="sxs-lookup"><span data-stu-id="ca313-114">You can assign licenses to users on either the **Licenses** page, or on the **Active Users** page.</span></span> <span data-ttu-id="ca313-115">O método a ser usado dependerá de você desejar atribuir licenças de produto a usuários específicos ou atribuir licenças de usuários a produtos específicos.</span><span class="sxs-lookup"><span data-stu-id="ca313-115">Which method you use depends on whether you want to assign product licenses to specific users, or assign users licenses to specific products.</span></span>

> [!NOTE]
> <span data-ttu-id="ca313-116">Se não estiver usando o novo centro de administração do Microsoft 365, você poderá ativá-lo selecionando a alternância **Experimentar o novo centro de administração** localizado na parte superior da Home Page.</span><span class="sxs-lookup"><span data-stu-id="ca313-116">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

## <a name="assign-licenses-to-users-on-the-licenses-page"></a><span data-ttu-id="ca313-117">Atribuir licenças a usuários na página de Licenças</span><span class="sxs-lookup"><span data-stu-id="ca313-117">Assign licenses to users on the Licenses page</span></span>

> [!NOTE]
> <span data-ttu-id="ca313-118">Você precisa ser um Administrador global, um Administrador de Cobrança ou um Administrador de Gerenciamento de Usuários. Saiba mais em [Sobre as funções de administrador do Office 365](/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="ca313-118">You must be a Global admin, Billing admin, License admin, or User management admin. For more information, see [About Office 365 admin roles](/microsoft-365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="ca313-119">Ao usar a página de **Licenças** para atribuir licenças, você atribui licenças de um produto específico para até 20 usuários.</span><span class="sxs-lookup"><span data-stu-id="ca313-119">When you use the **Licenses** page to assign licenses, you assign licenses for a specific product for up to 20 users.</span></span> <span data-ttu-id="ca313-120">Na página de **Licenças**, há uma lista de todos os produtos para os quais você tem assinaturas, juntamente com o número total de licenças para cada produto, quantas licenças estão atribuídas e quantas estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="ca313-120">On the **Licenses** page, you see a list of all the products you have subscriptions for, together with the total number of licenses for each product, how many licenses are assigned, and how many are available.</span></span>

1. <span data-ttu-id="ca313-121">No centro de administração, vá para a página **Cobrança** > [Licenças](https://go.microsoft.com/fwlink/p/?linkid=842264).</span><span class="sxs-lookup"><span data-stu-id="ca313-121">In the admin center, go to the **Billing** > [Licenses](https://go.microsoft.com/fwlink/p/?linkid=842264) page.</span></span>

   ![Captura de tela da janela de cobrança e opções de menu.](media/EDU-Lic-Billing-License.png)
2. <span data-ttu-id="ca313-123">Selecione um produto para o qual você deseja atribuir licenças.</span><span class="sxs-lookup"><span data-stu-id="ca313-123">Select a product for which you want to assign licenses.</span></span> <span data-ttu-id="ca313-124">O Microsoft Teams é parte do SKU gratuito do Office 365 a1 para estudantes.</span><span class="sxs-lookup"><span data-stu-id="ca313-124">Microsoft Teams is part of the free Office 365 A1 for Students SKU.</span></span>

   ![Captura de tela com os produtos disponíveis para os quais é possível atribuir licenças.](media/EDU-Lic-Licenses-Products.png)
3. <span data-ttu-id="ca313-126">Selecione **Atribuir licenças**.</span><span class="sxs-lookup"><span data-stu-id="ca313-126">Select **Assign licenses**.</span></span>

   ![Captura de tela da seção Usuários da página e da opção Atribuir Licenças com um sinal de adição na frente dela.](media/EDU-Lic-Assign-Licenses.png)
4. <span data-ttu-id="ca313-128">No painel **Atribuir licenças a usuários**, comece a digitar um nome, o que deve gerar uma lista de nomes.</span><span class="sxs-lookup"><span data-stu-id="ca313-128">In the **Assign licenses to users** pane, begin typing a name, which should generate a list of names.</span></span> <span data-ttu-id="ca313-129">Escolha o nome que está procurando nos resultados para adicioná-lo à lista.</span><span class="sxs-lookup"><span data-stu-id="ca313-129">Choose the name you're looking for from the results to add it to the list.</span></span> <span data-ttu-id="ca313-130">É possível selecionar até 20 usuários de cada vez.</span><span class="sxs-lookup"><span data-stu-id="ca313-130">You can add up to 20 users at a time.</span></span>

   ![Captura de tela da página atribuir licenças a usuários, com um nome parcial digitado, mostrando os resultados da pesquisa para esse nome parcial.](media/EDU-Lic-Assign-Licenses-Users.png)
5. <span data-ttu-id="ca313-132">Selecione **Ativar ou desativar os aplicativos e serviços** para atribuir ou remover o acesso a itens específicos, como o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ca313-132">Select **Turn apps and services on or off** to assign or remove access to specific items, such as Microsoft Teams.</span></span> <span data-ttu-id="ca313-133">Certifique-se de que o **Microsoft Teams** e o **Office para a Web (Educação)** estejam selecionados.</span><span class="sxs-lookup"><span data-stu-id="ca313-133">Ensure **Microsoft Teams** and **Office for the web (Education)** are selected.</span></span>
6. <span data-ttu-id="ca313-134">Quando tiver terminado, selecione **Atribuir**, e então selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="ca313-134">When you're finished, select **Assign**, then select **Close**.</span></span>

<span data-ttu-id="ca313-135">Para alterar os aplicativos e serviços aos quais o usuário tem acesso:</span><span class="sxs-lookup"><span data-stu-id="ca313-135">To change the apps and services a user has access to:</span></span>

1. <span data-ttu-id="ca313-136">Selecione a linha que contém o usuário.</span><span class="sxs-lookup"><span data-stu-id="ca313-136">Select the row that contains the user.</span></span>
1. <span data-ttu-id="ca313-137">No painel direito, marque ou desmarque os aplicativos e serviços aos quais você deseja conceder acesso ou remover o acesso.</span><span class="sxs-lookup"><span data-stu-id="ca313-137">In the right pane, select or deselect the apps and services that you want to give access to, or remove access from.</span></span>
1. <span data-ttu-id="ca313-138">Quando tiver terminado, selecione **Salvar**, e então selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="ca313-138">When you're finished, select **Save**, then select **Close**.</span></span>

## <a name="assign-licenses-to-an-individual-or-multiple-users-on-the-active-users-page"></a><span data-ttu-id="ca313-139">Atribuir licenças a um usuário ou vários usuários na página Usuários Ativos</span><span class="sxs-lookup"><span data-stu-id="ca313-139">Assign licenses to an individual or multiple users on the Active users page</span></span>

1. <span data-ttu-id="ca313-140">No centro de administração, vá para a página **Usuários**  > [Usuários ativos](https://go.microsoft.com/fwlink/p/?linkid=834822).</span><span class="sxs-lookup"><span data-stu-id="ca313-140">In the admin center, go to the **Users** > [Active users](https://go.microsoft.com/fwlink/p/?linkid=834822) page.</span></span>

   ![Captura de tela da opção de menu usuários ativos no centro de administração do Microsoft O365.](media/EDU-Lic-Active-Users.png)
2. <span data-ttu-id="ca313-142">Selecione os círculos ao lado do(s) nome(s) do(s) usuário(s) aos quais você deseja atribuir a(s) licença(s).</span><span class="sxs-lookup"><span data-stu-id="ca313-142">Select the circles next to the name(s) of the user(s) you want to assign license(s) to.</span></span>

   ![Captura de tela da página usuários ativos e de uma lista de usuários ativos na página, com alguns usuários selecionados porque círculos ao lado dos nomes estão preenchidos.](media/EDU-Lic-Active-Users-List.png)
3. <span data-ttu-id="ca313-144">Na parte superior, selecione **Gerenciar licenças de produtos**.</span><span class="sxs-lookup"><span data-stu-id="ca313-144">At the top select **Manage product licenses**.</span></span>

   ![Captura de tela da guia Gerenciar Licenças de Produtos e um usuário abaixo, listado como não licenciado.](media/EDU-Lic-Manage-Product-Licenses.png)
4. <span data-ttu-id="ca313-146">No painel **Gerenciar licenças de produtos**, selecione **Adicionar a atribuições de licença de produto existentes** > **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ca313-146">In the **Manage product licenses** pane, select **Add to existing product license assignments** > **Next**.</span></span>

   ![Captura de tela da janela Gerenciar licenças de produto, com o botão de opção Adicionar às atribuições de licença de produto existentes selecionado.](media/EDU-Lic-Add-Existing-Product.png)
5. <span data-ttu-id="ca313-148">No painel **Adicionar a produtos existentes**, alterne o botão para a posição **Ativado** nas licenças que você deseja que os usuários selecionados tenham.</span><span class="sxs-lookup"><span data-stu-id="ca313-148">In the **Add to existing products** pane, switch the toggle to the **On** position for the license that you want the selected users to have.</span></span> <span data-ttu-id="ca313-149">Certifique-se de que o **Microsoft Teams** e o **Office para a Web (Educação)** estejam selecionados.</span><span class="sxs-lookup"><span data-stu-id="ca313-149">Ensure **Microsoft Teams** and **Office for the web (Education)** are selected.</span></span>

   ![Captura de tela do Microsoft Teams e do Office para a Web, Educação, selecionado na guia Adicionar aos produtos existentes.](media/EDU-Lic-Add-Existing-Products.png)

   <span data-ttu-id="ca313-151">Por padrão, todos os serviços associados a essa licença são atribuídos automaticamente ao(s) usuário(s).</span><span class="sxs-lookup"><span data-stu-id="ca313-151">By default, all services associated with those license(s) are automatically assigned to the user(s).</span></span> <span data-ttu-id="ca313-152">Você pode limitar quais serviços estão disponíveis para os usuários.</span><span class="sxs-lookup"><span data-stu-id="ca313-152">You can limit which services are available to the users.</span></span> <span data-ttu-id="ca313-153">Alterne o botão para a posição **Desativado** para os serviços que você não deseja que os usuários tenham.</span><span class="sxs-lookup"><span data-stu-id="ca313-153">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="ca313-154">Na parte inferior do painel, selecione Adicionar > Fechar.</span><span class="sxs-lookup"><span data-stu-id="ca313-154">At the bottom of the pane, select Add > Close.</span></span>