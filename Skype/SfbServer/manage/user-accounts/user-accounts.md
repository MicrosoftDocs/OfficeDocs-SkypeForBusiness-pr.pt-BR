---
title: Gerenciar contas de usuário para o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: As seções neste artigo descrevem como habilitar, desabilitar temporariamente ou remover usuários do Active Directory do Skype for Business Server.
ms.openlocfilehash: aa1ed16c39141cbcd6542f2c7e254a278c345826
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009634"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a><span data-ttu-id="b28b1-103">Gerenciar contas de usuário para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b28b1-103">Manage user accounts for Skype for Business Server</span></span>

<span data-ttu-id="b28b1-104">As seções neste artigo descrevem como habilitar, desabilitar temporariamente ou remover usuários do Active Directory do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b28b1-104">The sections in this article describe how to enable, temporarily disable, or remove Active Directory users from Skype for Business Server.</span></span>

<span data-ttu-id="b28b1-105">Para obter informações sobre como habilitar um usuário do Active Directory, consulte [criar uma nova conta de usuário](https://technet.microsoft.com/library/cc732336%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="b28b1-105">For information on how to enable an Active Directory user, see [Create a New User Account](https://technet.microsoft.com/library/cc732336%28v=ws.11%29.aspx).</span></span> <span data-ttu-id="b28b1-106">Para obter informações sobre como excluir um usuário do Active Directory, consulte [excluir uma conta de usuário](https://technet.microsoft.com/library/cc753730%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="b28b1-106">For information on how to delete an Active Directory user, see [Delete a User Account](https://technet.microsoft.com/library/cc753730%28v=ws.11%29.aspx).</span></span>

<span data-ttu-id="b28b1-107">Esses procedimentos devem ser executados durante uma janela de manutenção, quando o uso do Skype for Business for o mais baixo.</span><span class="sxs-lookup"><span data-stu-id="b28b1-107">These procedures should be performed during a maintenance window, when Skype for Business usage is lowest.</span></span> <span data-ttu-id="b28b1-108">O fato de isso ser feito em uma agenda diária ou semanal será determinado pelas necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="b28b1-108">Whether this is done on a daily or weekly schedule will be determined by the needs of your organization.</span></span>

<span data-ttu-id="b28b1-109">Este artigo contém os seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="b28b1-109">This article contains the following procedures:</span></span>

- [<span data-ttu-id="b28b1-110">Para procurar um ou mais usuários</span><span class="sxs-lookup"><span data-stu-id="b28b1-110">To search for one or more users</span></span>](user-accounts.md#Search)

- [<span data-ttu-id="b28b1-111">Adicionar e habilitar um novo usuário do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b28b1-111">Add and enable a new Skype for Business Server user</span></span>](user-accounts.md#Add)

- [<span data-ttu-id="b28b1-112">Desabilitar ou reabilitar uma conta de usuário habilitada anteriormente para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b28b1-112">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>](user-accounts.md#Disable)

- [<span data-ttu-id="b28b1-113">Desabilitar um usuário para o Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="b28b1-113">Disable a user for Enterprise Voice</span></span>](user-accounts.md#Disable_EV)

- [<span data-ttu-id="b28b1-114">Remover uma conta de usuário com o Shell de gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b28b1-114">Remove a user account with the Skype for Business Server Management Shell</span></span>](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="b28b1-115">Para procurar um ou mais usuários</span><span class="sxs-lookup"><span data-stu-id="b28b1-115">To search for one or more users</span></span>
<span data-ttu-id="b28b1-116"><a name="Search"> </a></span><span class="sxs-lookup"><span data-stu-id="b28b1-116"><a name="Search"> </a></span></span>

<span data-ttu-id="b28b1-117">Você pode usar os resultados de uma consulta de pesquisa para configurar usuários do Active Directory para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b28b1-117">You can use the results of a search query to configure Active Directory users for Skype for Business Server.</span></span> <span data-ttu-id="b28b1-118">É possível pesquisar por usuários por nome de exibição, nome, sobrenome, nome de conta SAM (Gerenciador de contas de segurança), endereço SIP ou URI (Uniform Resource Identifier) de linha.</span><span class="sxs-lookup"><span data-stu-id="b28b1-118">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="b28b1-119">Você pode pesquisar usuários usando o painel de controle do Skype for Business Server ou o snap-in usuários e computadores do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b28b1-119">You can search for users by using the Skype for Business Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="b28b1-120">O procedimento a seguir descreve como usar o painel de controle do Skype for Business Server para pesquisar usuários.</span><span class="sxs-lookup"><span data-stu-id="b28b1-120">The following procedure describes how to use Skype for Business Server Control Panel to search for users.</span></span>

> [!NOTE]
> <span data-ttu-id="b28b1-121">Em um ambiente com uma topologia de floresta central, os resultados da pesquisa podem não ser precisos quando você procura por um usuário pelo endereço de email do usuário.</span><span class="sxs-lookup"><span data-stu-id="b28b1-121">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user's email address.</span></span> <span data-ttu-id="b28b1-122">Em vez disso, você pode pesquisar usuários especificando um prefixo de endereço SIP, por exemplo, SIP: nome, adicione um filtro de pesquisa e selecione um endereço SIP que contenha um endereço de email parcial ou use o cmdlet **Get-CSUser** .</span><span class="sxs-lookup"><span data-stu-id="b28b1-122">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the **Get-CSUser** cmdlet.</span></span>

1. <span data-ttu-id="b28b1-123">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="b28b1-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="b28b1-124">Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b28b1-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="b28b1-125">Na barra de navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="b28b1-125">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="b28b1-126">Na caixa **Pesquisar usuários** , digite todo ou a primeira parte do nome de exibição, nome, sobrenome, nome da conta Sam, endereço SIP ou URI de linha da conta de usuário que você deseja pesquisar e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="b28b1-126">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5. <span data-ttu-id="b28b1-127">(Opcional) Especifique critérios de busca adicionais para limitar os resultados:</span><span class="sxs-lookup"><span data-stu-id="b28b1-127">(Optional) Specify additional search criteria to narrow the results:</span></span>

   <span data-ttu-id="b28b1-128">a.</span><span class="sxs-lookup"><span data-stu-id="b28b1-128">a.</span></span> <span data-ttu-id="b28b1-129">Clique no botão de seta de expansão no canto superior direito da tela acima **resultados da pesquisa**e, em seguida, clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="b28b1-129">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>

   <span data-ttu-id="b28b1-130">b.</span><span class="sxs-lookup"><span data-stu-id="b28b1-130">b.</span></span> <span data-ttu-id="b28b1-131">Insira a propriedade do usuário digitando-a ou clicando na seta na lista suspensa para selecionar uma propriedade do usuário.</span><span class="sxs-lookup"><span data-stu-id="b28b1-131">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>

   <span data-ttu-id="b28b1-132">c.</span><span class="sxs-lookup"><span data-stu-id="b28b1-132">c.</span></span> <span data-ttu-id="b28b1-133">Na lista **igual a** , clique em **igual a** ou diferente **de**.</span><span class="sxs-lookup"><span data-stu-id="b28b1-133">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>

   <span data-ttu-id="b28b1-134">d.</span><span class="sxs-lookup"><span data-stu-id="b28b1-134">d.</span></span> <span data-ttu-id="b28b1-135">Na caixa de texto, digite os critérios de pesquisa que você deseja usar para filtrar os resultados da pesquisa e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="b28b1-135">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6. <span data-ttu-id="b28b1-136">Os resultados da pesquisa são exibidos em **resultados da pesquisa**.</span><span class="sxs-lookup"><span data-stu-id="b28b1-136">The search results appear under **Search Results**.</span></span> <span data-ttu-id="b28b1-137">Você pode selecionar qualquer um ou todos os usuários na lista e realizar tarefas de configuração nos usuários selecionados.</span><span class="sxs-lookup"><span data-stu-id="b28b1-137">You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a><span data-ttu-id="b28b1-138">Adicionar e habilitar um novo usuário do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b28b1-138">Add and enable a new Skype for Business Server user</span></span>
<span data-ttu-id="b28b1-139"><a name="Add"> </a></span><span class="sxs-lookup"><span data-stu-id="b28b1-139"><a name="Add"> </a></span></span>

<span data-ttu-id="b28b1-140">Depois de habilitar uma conta de usuário em usuários e computadores do Active Directory, você pode usar o painel de controle do Skype for Business Server para criar e habilitar novas contas de usuário do Skype for Business Server adicionando um usuário do Active Directory ao Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b28b1-140">After enabling a user account in Active Directory Users and Computers, you can use Skype for Business Server Control Panel to create and enable new Skype for Business Server user accounts by adding an Active Directory user to Skype for Business Server.</span></span>

<span data-ttu-id="b28b1-141">Você também pode usar um cmdlet, especificamente [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b28b1-141">You can also use a cmdlet, specifically [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span></span>

1. <span data-ttu-id="b28b1-142">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="b28b1-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="b28b1-143">Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b28b1-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="b28b1-144">Na barra de navegação da esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="b28b1-144">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="b28b1-145">Clique em **Habilitar usuários**.</span><span class="sxs-lookup"><span data-stu-id="b28b1-145">Click **Enable users**.</span></span>

5. <span data-ttu-id="b28b1-146">No diálogo **Novo Usuário do Lync Server**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b28b1-146">On the **New Lync Server User** dialog, click **Add**.</span></span>

6. <span data-ttu-id="b28b1-147">Na caixa \*\*Pesquisar usuários \*\*, digite todo ou o primeiro nome, nome de exibição, nome, sobrenome, nome da conta SAM, endereço de email, UPN ou número de telefone da conta de usuário do Active Directory que você deseja e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="b28b1-147">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7. <span data-ttu-id="b28b1-148">Na tabela, selecione a conta que você deseja adicionar ao Skype for Business Server e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b28b1-148">In the table, select the account you want to add to Skype for Business Server, and then click **OK**.</span></span>

8. <span data-ttu-id="b28b1-149">Atribua o usuário a um pool, especifique qualquer detalhe adicional, atribua as políticas ao usuário desejado e clique em **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="b28b1-149">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a><span data-ttu-id="b28b1-150">Desabilitar ou reabilitar uma conta de usuário habilitada anteriormente para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b28b1-150">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>
<span data-ttu-id="b28b1-151"><a name="Disable"> </a></span><span class="sxs-lookup"><span data-stu-id="b28b1-151"><a name="Disable"> </a></span></span>

<span data-ttu-id="b28b1-152">Você pode usar o procedimento a seguir para desabilitar uma conta de usuário previamente habilitada no Skype for Business Server sem perder as configurações do Skype for Business Server que você configurou para a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="b28b1-152">You can use the following procedure to disable a previously enabled user account in Skype for Business Server without losing the Skype for Business Server settings that you configured for the user account.</span></span> <span data-ttu-id="b28b1-153">Como você não perde as configurações da conta de usuário do Skype for Business Server, você pode reabilitar uma conta de usuário previamente habilitada sem precisar reconfigurar a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="b28b1-153">Because you do not lose the Skype for Business Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

1. <span data-ttu-id="b28b1-154">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="b28b1-154">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="b28b1-155">Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b28b1-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="b28b1-156">Na barra de navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="b28b1-156">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="b28b1-157">Na caixa **Usuários de pesquisa**, digite todo ou a primeira parte do nome de exibição, primeiro nome, último nome, nome de conta do Gerenciador de contas de segurança (SAM), endereço SIP ou alinhe o Identificador de recurso uniforme (URI) da conta do usuário que você quer desabilitar ou reabilitar e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="b28b1-157">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="b28b1-158">Na tabela, clique na conta de usuário que você quer habilitar ou reabilitar.</span><span class="sxs-lookup"><span data-stu-id="b28b1-158">In the table, click the user account that you want to disable or re-enable.</span></span>

6. <span data-ttu-id="b28b1-159">No menu **Ação**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b28b1-159">On the **Action** menu, do one of the following:</span></span>

   - <span data-ttu-id="b28b1-160">Para desabilitar temporariamente a conta de usuário para o Skype for Business Server, clique em **desabilitar temporariamente para o Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b28b1-160">To temporarily disable the user account for Skype for Business Server, click **Temporarily disable for Lync Server**.</span></span>

   - <span data-ttu-id="b28b1-161">Para habilitar a conta de usuário do Skype for Business Server, clique em **reabilitar para o Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b28b1-161">To enable the user account for Skype for Business Server, click **Re-enable for Lync Server**.</span></span>

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="b28b1-162">Usar o Windows PowerShell para desabilitar ou reabilitar contas de usuário</span><span class="sxs-lookup"><span data-stu-id="b28b1-162">Use Windows Powershell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="b28b1-163">As contas de usuário podem ser desabilitadas temporariamente e, posteriormente, habilitadas novamente, usando o cmdlet **set-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="b28b1-163">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="b28b1-164">Você pode executar esse cmdlet a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b28b1-164">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b28b1-165">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo do blog ["início rápido: Gerenciando o Microsoft Lync Server 2010 usando o PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="b28b1-165">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="b28b1-166">O processo é o mesmo no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b28b1-166">The process is the same in Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account"></a><span data-ttu-id="b28b1-167">Para desabilitar uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="b28b1-167">To disable a user account</span></span>

- <span data-ttu-id="b28b1-168">Para desabilitar uma conta temporariamente, defina o valor da propriedade Enabled como falso ($False).</span><span class="sxs-lookup"><span data-stu-id="b28b1-168">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="b28b1-169">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b28b1-169">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a><span data-ttu-id="b28b1-170">Para reabilitar uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="b28b1-170">To re-enable a user account</span></span>

- <span data-ttu-id="b28b1-171">Para reabilitar uma conta de usuário, defina o valor da propriedade Enabled como verdadeiro ($True).</span><span class="sxs-lookup"><span data-stu-id="b28b1-171">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="b28b1-172">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b28b1-172">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

<span data-ttu-id="b28b1-173">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="b28b1-173">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="disable-a-user-for-enterprise-voice"></a><span data-ttu-id="b28b1-174">Desabilitar um usuário para o Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="b28b1-174">Disable a user for Enterprise Voice</span></span>
<span data-ttu-id="b28b1-175"><a name="Disable_EV"> </a></span><span class="sxs-lookup"><span data-stu-id="b28b1-175"><a name="Disable_EV"> </a></span></span>

<span data-ttu-id="b28b1-176">Use o procedimento a seguir para desabilitar o Enterprise Voice para uma conta de usuário habilitada para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b28b1-176">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="b28b1-177">Para desabilitar uma conta de usuário para o Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="b28b1-177">To disable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="b28b1-178">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="b28b1-178">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="b28b1-179">Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b28b1-179">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="b28b1-180">Na barra de navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="b28b1-180">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="b28b1-181">Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="b28b1-181">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5. <span data-ttu-id="b28b1-182">Na tabela, clique na conta de usuário que você deseja habilitar para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="b28b1-182">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6. <span data-ttu-id="b28b1-183">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="b28b1-183">On the **Edit** menu, click **Show details**.</span></span>

7. <span data-ttu-id="b28b1-184">Na página **Editar usuário do servidor Lync**, sob **Telefonia**, clique em qualquer opção exceto **Enterprise Voice**.</span><span class="sxs-lookup"><span data-stu-id="b28b1-184">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b28b1-185">Para impedir que um usuário faça chamadas de áudio ou vídeo usando o Lync, em **telefonia**, clique em **áudio/vídeo desabilitado**.</span><span class="sxs-lookup"><span data-stu-id="b28b1-185">To restrict a user from making audio or video calls by using Lync, under **Telephony**, click **Audio/video disabled**.</span></span>

8. <span data-ttu-id="b28b1-186">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="b28b1-186">Click **Commit**.</span></span>

<span data-ttu-id="b28b1-187">O usuário agora não pode usar o recurso Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="b28b1-187">The user is now unable to use the Enterprise Voice feature.</span></span> <span data-ttu-id="b28b1-188">Informações relacionadas:</span><span class="sxs-lookup"><span data-stu-id="b28b1-188">Related information:</span></span> <br/>[<span data-ttu-id="b28b1-189">Enterprise Voice e mobilidade</span><span class="sxs-lookup"><span data-stu-id="b28b1-189">Enterprise Voice and mobility</span></span>](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [<span data-ttu-id="b28b1-190">Habilitar usuários para o Enterprise Voice no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b28b1-190">Enable users for Enterprise Voice in Skype for Business Server</span></span>](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [<span data-ttu-id="b28b1-191">Shell de Gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b28b1-191">Skype for Business Server Management Shell</span></span>](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a><span data-ttu-id="b28b1-192">Remover uma conta de usuário com o Shell de gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b28b1-192">Remove a user account with the Skype for Business Server Management Shell</span></span>
<span data-ttu-id="b28b1-193"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="b28b1-193"><a name="Remove"> </a></span></span>

<span data-ttu-id="b28b1-194">Você pode usar o procedimento a seguir para remover uma conta de usuário adicionada anteriormente no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b28b1-194">You can use the following procedure to remove a previously added user account in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="b28b1-195">Remover um usuário pode causar a perda de qualquer configuração definida para a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="b28b1-195">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="b28b1-196">Se quiser desabilitar temporariamente uma conta de usuário, confira [desabilitar ou reabilitar uma conta de usuário habilitada anteriormente para o Skype for Business Server](user-accounts.md#Disable).</span><span class="sxs-lookup"><span data-stu-id="b28b1-196">If you would like to temporarily disable a user account instead, see [Disable or re-enable a user account previously enabled for Skype for Business Server](user-accounts.md#Disable).</span></span>

1. <span data-ttu-id="b28b1-197">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="b28b1-197">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="b28b1-198">Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b28b1-198">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="b28b1-199">Na barra de navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="b28b1-199">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="b28b1-200">Na caixa **Pesquisar usuários**, digite todo ou a primeira parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta de usuário que você deseja desabilitar ou reabilitar e clique em **Encontrar**.</span><span class="sxs-lookup"><span data-stu-id="b28b1-200">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="b28b1-201">Na tabela, clique na conta de usuário que deseja remover.</span><span class="sxs-lookup"><span data-stu-id="b28b1-201">In the table, click the user account that you want to remove.</span></span>

6. <span data-ttu-id="b28b1-202">No menu **Ação**, selecione **Remover do Lync Server** e uma caixa de diálogo aparece.</span><span class="sxs-lookup"><span data-stu-id="b28b1-202">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7. <span data-ttu-id="b28b1-203">Na caixa de diálogo, selecione **OK** para remover o usuário.</span><span class="sxs-lookup"><span data-stu-id="b28b1-203">From the dialog box, select **OK** to remove the user.</span></span>

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a><span data-ttu-id="b28b1-204">Remover contas de usuário com cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b28b1-204">Remove user accounts with Windows Powershell cmdlets</span></span>

<span data-ttu-id="b28b1-205">Você pode remover contas de usuário usando o cmdlet Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="b28b1-205">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="b28b1-206">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b28b1-206">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="b28b1-207">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo do blog ["início rápido: Gerenciando o Microsoft Lync Server 2010 usando o PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="b28b1-207">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="b28b1-208">O processo é o mesmo no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b28b1-208">The process is the same in Skype for Business Server.</span></span>

### <a name="to-remove-a-user-account"></a><span data-ttu-id="b28b1-209">Para remover uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="b28b1-209">To remove a user account</span></span>
<span data-ttu-id="b28b1-210">Para remover uma conta de usuário, utilize o cmdlet Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="b28b1-210">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="b28b1-211">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b28b1-211">For example:</span></span>

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

<span data-ttu-id="b28b1-212">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="b28b1-212">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="b28b1-213">Confira também</span><span class="sxs-lookup"><span data-stu-id="b28b1-213">See also</span></span>
<span data-ttu-id="b28b1-214"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="b28b1-214"><a name="Remove"> </a></span></span>

[<span data-ttu-id="b28b1-215">Enable-CsUser</span><span class="sxs-lookup"><span data-stu-id="b28b1-215">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[<span data-ttu-id="b28b1-216">Disable-CsUser</span><span class="sxs-lookup"><span data-stu-id="b28b1-216">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)
