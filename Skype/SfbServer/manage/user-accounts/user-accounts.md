---
title: Gerenciar contas de usuário do Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: As seções neste artigo descrevem como habilitar, desabilitar ou remover temporariamente usuários do Active Directory do Skype for Business Server.
ms.openlocfilehash: 45217593dd010c4daf73d6b5edcbf6f5f4e681a5
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992398"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a><span data-ttu-id="ce664-103">Gerenciar contas de usuário do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ce664-103">Manage user accounts for Skype for Business Server</span></span>

<span data-ttu-id="ce664-104">As seções neste artigo descrevem como habilitar, desabilitar ou remover temporariamente usuários do Active Directory do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ce664-104">The sections in this article describe how to enable, temporarily disable, or remove Active Directory users from Skype for Business Server.</span></span>

<span data-ttu-id="ce664-105">Para obter informações sobre como habilitar um usuário do Active Directory, consulte [criar uma nova conta de usuário](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="ce664-105">For information on how to enable an Active Directory user, see [Create a New User Account](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx).</span></span> <span data-ttu-id="ce664-106">Para obter informações sobre como excluir um usuário do Active Directory, consulte [excluir uma conta de usuário](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="ce664-106">For information on how to delete an Active Directory user, see [Delete a User Account](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).</span></span>

<span data-ttu-id="ce664-107">Esses procedimentos devem ser executados durante uma janela de manutenção, quando o uso do Skype for Business for o mais baixo.</span><span class="sxs-lookup"><span data-stu-id="ce664-107">These procedures should be performed during a maintenance window, when Skype for Business usage is lowest.</span></span> <span data-ttu-id="ce664-108">O fato de isso ser feito em um cronograma diário ou semanal será determinado pelas necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="ce664-108">Whether this is done on a daily or weekly schedule will be determined by the needs of your organization.</span></span>

<span data-ttu-id="ce664-109">Este artigo contém os seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="ce664-109">This article contains the following procedures:</span></span>

- [<span data-ttu-id="ce664-110">Para procurar um ou mais usuários</span><span class="sxs-lookup"><span data-stu-id="ce664-110">To search for one or more users</span></span>](user-accounts.md#Search)

- [<span data-ttu-id="ce664-111">Adicionar e habilitar um novo usuário do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ce664-111">Add and enable a new Skype for Business Server user</span></span>](user-accounts.md#Add)

- [<span data-ttu-id="ce664-112">Desabilitar ou habilitar novamente uma conta de usuário habilitada anteriormente para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ce664-112">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>](user-accounts.md#Disable)

- [<span data-ttu-id="ce664-113">Desabilitar um usuário para Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="ce664-113">Disable a user for Enterprise Voice</span></span>](user-accounts.md#Disable_EV)

- [<span data-ttu-id="ce664-114">Remover uma conta de usuário com o Shell de gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ce664-114">Remove a user account with the Skype for Business Server Management Shell</span></span>](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="ce664-115">Para procurar um ou mais usuários</span><span class="sxs-lookup"><span data-stu-id="ce664-115">To search for one or more users</span></span>
<span data-ttu-id="ce664-116"><a name="Search"> </a></span><span class="sxs-lookup"><span data-stu-id="ce664-116"></span></span>

<span data-ttu-id="ce664-117">Você pode usar os resultados de uma consulta de pesquisa para configurar usuários do Active Directory para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ce664-117">You can use the results of a search query to configure Active Directory users for Skype for Business Server.</span></span> <span data-ttu-id="ce664-118">É possível pesquisar por usuários por nome de exibição, nome, sobrenome, nome de conta SAM (Gerenciador de contas de segurança), endereço SIP ou URI (Uniform Resource Identifier) de linha.</span><span class="sxs-lookup"><span data-stu-id="ce664-118">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="ce664-119">Você pode pesquisar usuários usando o painel de controle do Skype for Business Server ou o snap-in usuários e computadores do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ce664-119">You can search for users by using the Skype for Business Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="ce664-120">O procedimento a seguir descreve como usar o painel de controle do Skype for Business Server para pesquisar usuários.</span><span class="sxs-lookup"><span data-stu-id="ce664-120">The following procedure describes how to use Skype for Business Server Control Panel to search for users.</span></span>

> [!NOTE]
> <span data-ttu-id="ce664-121">Em um ambiente com uma topologia de floresta central, os resultados da pesquisa podem não ser precisos ao pesquisar por um usuário pelo endereço de email do usuário.</span><span class="sxs-lookup"><span data-stu-id="ce664-121">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user's email address.</span></span> <span data-ttu-id="ce664-122">Em vez disso, você pode procurar usuários especificando um prefixo de endereço SIP, por exemplo, SIP: Name, adicionar um filtro de pesquisa e selecionar um endereço SIP que contenha um endereço de email parcial ou usar o cmdlet **Get-CSUser** .</span><span class="sxs-lookup"><span data-stu-id="ce664-122">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the **Get-CSUser** cmdlet.</span></span>

1. <span data-ttu-id="ce664-123">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="ce664-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="ce664-124">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ce664-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="ce664-125">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="ce664-125">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="ce664-126">Na caixa **Pesquisar usuários** , digite toda ou a primeira parte do nome para exibição, nome, sobrenome, nome da conta Sam, endereço SIP ou URI da linha da conta de usuário que você deseja pesquisar e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="ce664-126">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5. <span data-ttu-id="ce664-127">(Opcional) Especifique o critério de pesquisa adicional para reduzir os resultados:</span><span class="sxs-lookup"><span data-stu-id="ce664-127">(Optional) Specify additional search criteria to narrow the results:</span></span>

   <span data-ttu-id="ce664-128">a.</span><span class="sxs-lookup"><span data-stu-id="ce664-128">a.</span></span> <span data-ttu-id="ce664-129">Clique no botão de seta de expansão no canto superior direito da tela acima de **resultados da pesquisa**e, em seguida, clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="ce664-129">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>

   <span data-ttu-id="ce664-130">b.</span><span class="sxs-lookup"><span data-stu-id="ce664-130">b.</span></span> <span data-ttu-id="ce664-131">Digite a propriedade do usuário digitando-a ou clicando na seta na lista suspensa para selecionar uma propriedade de usuário.</span><span class="sxs-lookup"><span data-stu-id="ce664-131">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>

   <span data-ttu-id="ce664-132">c.</span><span class="sxs-lookup"><span data-stu-id="ce664-132">c.</span></span> <span data-ttu-id="ce664-133">Na lista **igual a** , clique em **igual** ou **não igual a**.</span><span class="sxs-lookup"><span data-stu-id="ce664-133">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>

   <span data-ttu-id="ce664-134">d.</span><span class="sxs-lookup"><span data-stu-id="ce664-134">d.</span></span> <span data-ttu-id="ce664-135">Na caixa de texto, digite os critérios de pesquisa que você deseja usar para filtrar os resultados da pesquisa e, em seguida, clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="ce664-135">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6. <span data-ttu-id="ce664-136">Os resultados da pesquisa são exibidos em **resultados da pesquisa**.</span><span class="sxs-lookup"><span data-stu-id="ce664-136">The search results appear under **Search Results**.</span></span> <span data-ttu-id="ce664-137">Você pode selecionar qualquer um dos usuários na lista e executar tarefas de configuração nos usuários selecionados.</span><span class="sxs-lookup"><span data-stu-id="ce664-137">You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a><span data-ttu-id="ce664-138">Adicionar e habilitar um novo usuário do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ce664-138">Add and enable a new Skype for Business Server user</span></span>
<span data-ttu-id="ce664-139"><a name="Add"> </a></span><span class="sxs-lookup"><span data-stu-id="ce664-139"></span></span>

<span data-ttu-id="ce664-140">Depois de habilitar uma conta de usuário em usuários e computadores do Active Directory, você pode usar o painel de controle do Skype for Business Server para criar e habilitar novas contas de usuário do Skype for Business Server ao adicionar um usuário do Active Directory ao Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ce664-140">After enabling a user account in Active Directory Users and Computers, you can use Skype for Business Server Control Panel to create and enable new Skype for Business Server user accounts by adding an Active Directory user to Skype for Business Server.</span></span>

<span data-ttu-id="ce664-141">Você também pode usar um cmdlet, [habilite-o especificamente para CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="ce664-141">You can also use a cmdlet, specifically [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span></span>

1. <span data-ttu-id="ce664-142">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="ce664-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="ce664-143">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ce664-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="ce664-144">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="ce664-144">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="ce664-145">Clique em **habilitar usuários**.</span><span class="sxs-lookup"><span data-stu-id="ce664-145">Click **Enable users**.</span></span>

5. <span data-ttu-id="ce664-146">Na caixa de diálogo **novo usuário do Lync Server** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="ce664-146">On the **New Lync Server User** dialog, click **Add**.</span></span>

6. <span data-ttu-id="ce664-147">Na caixa **Pesquisar usuários** , digite toda ou a primeira parte do nome, nome para exibição, nome, sobrenome, nome da conta do Gerenciador de contas de segurança (Sam) nome da conta, endereço de email, nome UPN ou número de telefone da conta de usuário do Active Directory que você deseja e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="ce664-147">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7. <span data-ttu-id="ce664-148">Na tabela, selecione a conta que você deseja adicionar ao Skype for Business Server e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ce664-148">In the table, select the account you want to add to Skype for Business Server, and then click **OK**.</span></span>

8. <span data-ttu-id="ce664-149">Atribua o usuário a um pool, especifique os detalhes adicionais e atribua as políticas ao usuário desejado e, em seguida, clique em **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="ce664-149">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a><span data-ttu-id="ce664-150">Desabilitar ou habilitar novamente uma conta de usuário habilitada anteriormente para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ce664-150">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>
<span data-ttu-id="ce664-151"><a name="Disable"> </a></span><span class="sxs-lookup"><span data-stu-id="ce664-151"></span></span>

<span data-ttu-id="ce664-152">Você pode usar o procedimento a seguir para desabilitar uma conta de usuário habilitada anteriormente no Skype for Business Server sem perder as configurações do Skype for Business Server que você configurou para a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="ce664-152">You can use the following procedure to disable a previously enabled user account in Skype for Business Server without losing the Skype for Business Server settings that you configured for the user account.</span></span> <span data-ttu-id="ce664-153">Como você não perde as configurações da conta de usuário do Skype for Business Server, é possível habilitar novamente uma conta de usuário habilitada anteriormente sem precisar reconfigurar a conta do usuário.</span><span class="sxs-lookup"><span data-stu-id="ce664-153">Because you do not lose the Skype for Business Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

1. <span data-ttu-id="ce664-154">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="ce664-154">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="ce664-155">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ce664-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="ce664-156">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="ce664-156">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="ce664-157">Na caixa **Pesquisar usuários** , digite toda ou a primeira parte do nome para exibição, nome, sobrenome, nome da conta do Gerenciador de contas de segurança (Sam), endereço SIP ou URI (Uniform Resource Identifier) da conta de usuário que você deseja desabilitar ou reabilitar e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="ce664-157">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="ce664-158">Na tabela, clique na conta de usuário que você deseja desabilitar ou habilitar novamente.</span><span class="sxs-lookup"><span data-stu-id="ce664-158">In the table, click the user account that you want to disable or re-enable.</span></span>

6. <span data-ttu-id="ce664-159">No menu **ação** , siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="ce664-159">On the **Action** menu, do one of the following:</span></span>

   - <span data-ttu-id="ce664-160">Para desativar temporariamente a conta de usuário do Skype for Business Server, clique em **desativar temporariamente para Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ce664-160">To temporarily disable the user account for Skype for Business Server, click **Temporarily disable for Lync Server**.</span></span>

   - <span data-ttu-id="ce664-161">Para habilitar a conta de usuário do Skype for Business Server, clique em **habilitar novamente para Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ce664-161">To enable the user account for Skype for Business Server, click **Re-enable for Lync Server**.</span></span>

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="ce664-162">Usar o Windows PowerShell para desabilitar ou habilitar novamente as contas de usuário</span><span class="sxs-lookup"><span data-stu-id="ce664-162">Use Windows Powershell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="ce664-163">As contas de usuário podem ser desabilitadas temporariamente e, em seguida, reativadas posteriormente usando-se o cmdlet **set-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="ce664-163">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="ce664-164">Você pode executar esse cmdlet a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ce664-164">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ce664-165">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo ["início rápido: Gerenciando o Microsoft Lync Server 2010 usando o PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="ce664-165">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="ce664-166">O processo é o mesmo no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ce664-166">The process is the same in Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account"></a><span data-ttu-id="ce664-167">Para desabilitar uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="ce664-167">To disable a user account</span></span>

- <span data-ttu-id="ce664-168">Para desativar temporariamente uma conta de usuário, defina o valor da propriedade Enabled como false ($False).</span><span class="sxs-lookup"><span data-stu-id="ce664-168">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="ce664-169">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ce664-169">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a><span data-ttu-id="ce664-170">Para habilitar novamente uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="ce664-170">To re-enable a user account</span></span>

- <span data-ttu-id="ce664-171">Para habilitar novamente uma conta de usuário desabilitada, defina o valor da propriedade Enabled como true ($True).</span><span class="sxs-lookup"><span data-stu-id="ce664-171">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="ce664-172">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ce664-172">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

<span data-ttu-id="ce664-173">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="ce664-173">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="disable-a-user-for-enterprise-voice"></a><span data-ttu-id="ce664-174">Desabilitar um usuário para Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="ce664-174">Disable a user for Enterprise Voice</span></span>
<span data-ttu-id="ce664-175"><a name="Disable_EV"> </a></span><span class="sxs-lookup"><span data-stu-id="ce664-175"></span></span>

<span data-ttu-id="ce664-176">Use o procedimento a seguir para desabilitar o Enterprise Voice para uma conta de usuário habilitada para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ce664-176">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="ce664-177">Para desabilitar uma conta de usuário para o Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="ce664-177">To disable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="ce664-178">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="ce664-178">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="ce664-179">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ce664-179">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="ce664-180">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="ce664-180">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="ce664-181">Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="ce664-181">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5. <span data-ttu-id="ce664-182">Na tabela, clique na conta de usuário que você deseja habilitar para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="ce664-182">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6. <span data-ttu-id="ce664-183">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="ce664-183">On the **Edit** menu, click **Show details**.</span></span>

7. <span data-ttu-id="ce664-184">Na página **Editar usuário do Lync Server** , em **telefonia**, clique em qualquer opção exceto **Enterprise Voice**.</span><span class="sxs-lookup"><span data-stu-id="ce664-184">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ce664-185">Para impedir que um usuário faça chamadas de áudio ou vídeo usando o Lync, em **telefonia**, clique em **áudio/vídeo desabilitado**.</span><span class="sxs-lookup"><span data-stu-id="ce664-185">To restrict a user from making audio or video calls by using Lync, under **Telephony**, click **Audio/video disabled**.</span></span>

8. <span data-ttu-id="ce664-186">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ce664-186">Click **Commit**.</span></span>

<span data-ttu-id="ce664-187">O usuário agora não pode usar o recurso Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="ce664-187">The user is now unable to use the Enterprise Voice feature.</span></span> <span data-ttu-id="ce664-188">Informações relacionadas:</span><span class="sxs-lookup"><span data-stu-id="ce664-188">Related information:</span></span> <br/>[<span data-ttu-id="ce664-189">Enterprise Voice and Mobility</span><span class="sxs-lookup"><span data-stu-id="ce664-189">Enterprise Voice and mobility</span></span>](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [<span data-ttu-id="ce664-190">Habilitar usuários do Enterprise Voice no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ce664-190">Enable users for Enterprise Voice in Skype for Business Server</span></span>](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [<span data-ttu-id="ce664-191">Shell de Gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ce664-191">Skype for Business Server Management Shell</span></span>](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a><span data-ttu-id="ce664-192">Remover uma conta de usuário com o Shell de gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ce664-192">Remove a user account with the Skype for Business Server Management Shell</span></span>
<span data-ttu-id="ce664-193"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="ce664-193"></span></span>

<span data-ttu-id="ce664-194">Você pode usar o procedimento a seguir para remover uma conta de usuário adicionada anteriormente no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ce664-194">You can use the following procedure to remove a previously added user account in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="ce664-195">A remoção de um usuário fará com que você perca todas as configurações que você configurou para a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="ce664-195">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="ce664-196">Se quiser desabilitar temporariamente uma conta de usuário, confira [desabilitar ou habilitar novamente uma conta de usuário habilitada anteriormente para o Skype for Business Server](user-accounts.md#Disable).</span><span class="sxs-lookup"><span data-stu-id="ce664-196">If you would like to temporarily disable a user account instead, see [Disable or re-enable a user account previously enabled for Skype for Business Server](user-accounts.md#Disable).</span></span>

1. <span data-ttu-id="ce664-197">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="ce664-197">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="ce664-198">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ce664-198">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="ce664-199">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="ce664-199">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="ce664-200">Na caixa **Pesquisar usuários** , digite toda ou a primeira parte do nome para exibição, nome, sobrenome, nome da conta do Gerenciador de contas de segurança (Sam), endereço SIP ou URI (Uniform Resource Identifier) da conta de usuário que você deseja desabilitar ou reabilitar e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="ce664-200">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="ce664-201">Na tabela, clique na conta de usuário que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="ce664-201">In the table, click the user account that you want to remove.</span></span>

6. <span data-ttu-id="ce664-202">No menu **ação** , selecione **remover do Lync Server**, e uma caixa de diálogo será exibida.</span><span class="sxs-lookup"><span data-stu-id="ce664-202">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7. <span data-ttu-id="ce664-203">Na caixa de diálogo, selecione **OK** para remover o usuário.</span><span class="sxs-lookup"><span data-stu-id="ce664-203">From the dialog box, select **OK** to remove the user.</span></span>

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a><span data-ttu-id="ce664-204">Remover contas de usuário com cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ce664-204">Remove user accounts with Windows Powershell cmdlets</span></span>

<span data-ttu-id="ce664-205">Você pode remover contas de usuário usando o cmdlet Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="ce664-205">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="ce664-206">Esse cmdlet pode ser executado do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ce664-206">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="ce664-207">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo ["início rápido: Gerenciando o Microsoft Lync Server 2010 usando o PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="ce664-207">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="ce664-208">O processo é o mesmo no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ce664-208">The process is the same in Skype for Business Server.</span></span>

### <a name="to-remove-a-user-account"></a><span data-ttu-id="ce664-209">Para remover uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="ce664-209">To remove a user account</span></span>
<span data-ttu-id="ce664-210">Para remover uma conta de usuário, use o cmdlet Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="ce664-210">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="ce664-211">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ce664-211">For example:</span></span>

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

<span data-ttu-id="ce664-212">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="ce664-212">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="ce664-213">Confira também</span><span class="sxs-lookup"><span data-stu-id="ce664-213">See also</span></span>
<span data-ttu-id="ce664-214"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="ce664-214"></span></span>

[<span data-ttu-id="ce664-215">Enable-CsUser</span><span class="sxs-lookup"><span data-stu-id="ce664-215">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[<span data-ttu-id="ce664-216">Disable-CsUser</span><span class="sxs-lookup"><span data-stu-id="ce664-216">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)
