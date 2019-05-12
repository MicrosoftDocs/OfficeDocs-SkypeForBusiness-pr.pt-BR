---
title: Gerenciar contas de usuário do Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: As seções deste artigo descrevem como habilitar, desabilitar temporariamente ou remover usuários do Active Directory do Skype para Business Server.
ms.openlocfilehash: 8aeebafc0e221cd51df76233f6dce1f1e53fb429
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897314"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a><span data-ttu-id="113e5-103">Gerenciar contas de usuário do Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="113e5-103">Manage user accounts for Skype for Business Server</span></span>

<span data-ttu-id="113e5-104">As seções deste artigo descrevem como habilitar, desabilitar temporariamente ou remover usuários do Active Directory do Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="113e5-104">The sections in this article describe how to enable, temporarily disable, or remove Active Directory users from Skype for Business Server.</span></span>

<span data-ttu-id="113e5-105">Para obter informações sobre como habilitar um usuário do Active Directory, consulte [criar uma nova conta de usuário](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="113e5-105">For information on how to enable an Active Directory user, see [Create a New User Account](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx).</span></span> <span data-ttu-id="113e5-106">Para obter informações sobre como excluir um usuário do Active Directory, consulte [Excluir uma conta de usuário](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="113e5-106">For information on how to delete an Active Directory user, see [Delete a User Account](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).</span></span>

<span data-ttu-id="113e5-107">Estes procedimentos devem ser realizados durante um período de manutenção, quando Skype para uso de negócios é mais baixa.</span><span class="sxs-lookup"><span data-stu-id="113e5-107">These procedures should be performed during a maintenance window, when Skype for Business usage is lowest.</span></span> <span data-ttu-id="113e5-108">Se isso é feito em uma agenda diária ou semanal será determinado pelas necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="113e5-108">Whether this is done on a daily or weekly schedule will be determined by the needs of your organization.</span></span>

<span data-ttu-id="113e5-109">Este artigo contém os seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="113e5-109">This article contains the following procedures:</span></span>

- [<span data-ttu-id="113e5-110">Para procurar um ou mais usuários</span><span class="sxs-lookup"><span data-stu-id="113e5-110">To search for one or more users</span></span>](user-accounts.md#Search)

- [<span data-ttu-id="113e5-111">Adicionar e habilitar um novo Skype para usuário Business Server</span><span class="sxs-lookup"><span data-stu-id="113e5-111">Add and enable a new Skype for Business Server user</span></span>](user-accounts.md#Add)

- [<span data-ttu-id="113e5-112">Desabilitar ou reabilitar uma conta de usuário que antes estavam habilitada para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="113e5-112">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>](user-accounts.md#Disable)

- [<span data-ttu-id="113e5-113">Desabilitar um usuário para o Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="113e5-113">Disable a user for Enterprise Voice</span></span>](user-accounts.md#Disable_EV)

- [<span data-ttu-id="113e5-114">Remover uma conta de usuário com o Skype do Shell de gerenciamento do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="113e5-114">Remove a user account with the Skype for Business Server Management Shell</span></span>](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="113e5-115">Para procurar um ou mais usuários</span><span class="sxs-lookup"><span data-stu-id="113e5-115">To search for one or more users</span></span>
<span data-ttu-id="113e5-116"><a name="Search"> </a></span><span class="sxs-lookup"><span data-stu-id="113e5-116"></span></span>

<span data-ttu-id="113e5-117">Você pode usar os resultados de uma consulta de pesquisa para configurar usuários do Active Directory para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="113e5-117">You can use the results of a search query to configure Active Directory users for Skype for Business Server.</span></span> <span data-ttu-id="113e5-118">É possível pesquisar por usuários por nome de exibição, nome, sobrenome, nome de conta SAM (Gerenciador de contas de segurança), endereço SIP ou URI (Uniform Resource Identifier) de linha.</span><span class="sxs-lookup"><span data-stu-id="113e5-118">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="113e5-119">Você pode pesquisar usando o Skype para o painel de controle de servidor de negócios ou os usuários do Active Directory para usuários e computadores snap-in.</span><span class="sxs-lookup"><span data-stu-id="113e5-119">You can search for users by using the Skype for Business Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="113e5-120">O procedimento a seguir descreve como usar o Skype para painel de controle do servidor de negócios para procurar usuários.</span><span class="sxs-lookup"><span data-stu-id="113e5-120">The following procedure describes how to use Skype for Business Server Control Panel to search for users.</span></span>

> [!NOTE]
> <span data-ttu-id="113e5-121">Em um ambiente com uma topologia de floresta central, os resultados da pesquisa podem não ser precisos quando você procurar um usuário pelo endereço de email do usuário.</span><span class="sxs-lookup"><span data-stu-id="113e5-121">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user's email address.</span></span> <span data-ttu-id="113e5-122">Em vez disso, você pode procurar usuários especificando-se um prefixo de endereço SIP, por exemplo, sip: name, adicionar um filtro de pesquisa e selecione um endereço SIP que contém um endereço de email parcial ou use o cmdlet **Get-CSUser** .</span><span class="sxs-lookup"><span data-stu-id="113e5-122">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the **Get-CSUser** cmdlet.</span></span>

1. <span data-ttu-id="113e5-123">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="113e5-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="113e5-124">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="113e5-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="113e5-125">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="113e5-125">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="113e5-126">Na caixa **Pesquisar usuários** , digite todo ou a primeira parte do nome para exibição, nome, sobrenome, nome de conta SAM, endereço SIP ou URI de linha da conta de usuário que você deseja pesquisar e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="113e5-126">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5. <span data-ttu-id="113e5-127">(Opcional) Especifique o critério de pesquisa adicional para reduzir os resultados:</span><span class="sxs-lookup"><span data-stu-id="113e5-127">(Optional) Specify additional search criteria to narrow the results:</span></span>

   <span data-ttu-id="113e5-128">a.</span><span class="sxs-lookup"><span data-stu-id="113e5-128">a.</span></span> <span data-ttu-id="113e5-129">Clique no botão de seta de expansão no canto superior direito da tela acima **resultados da pesquisa**e, em seguida, clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="113e5-129">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>

   <span data-ttu-id="113e5-130">b.</span><span class="sxs-lookup"><span data-stu-id="113e5-130">b.</span></span> <span data-ttu-id="113e5-131">Insira a propriedade de usuário digitando-lo ou clicando na seta na lista suspensa para selecionar uma propriedade de usuário.</span><span class="sxs-lookup"><span data-stu-id="113e5-131">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>

   <span data-ttu-id="113e5-132">c.</span><span class="sxs-lookup"><span data-stu-id="113e5-132">c.</span></span> <span data-ttu-id="113e5-133">Na lista **igual a** , clique em **igual a** ou **não igual a**.</span><span class="sxs-lookup"><span data-stu-id="113e5-133">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>

   <span data-ttu-id="113e5-134">d.</span><span class="sxs-lookup"><span data-stu-id="113e5-134">d.</span></span> <span data-ttu-id="113e5-135">Na caixa de texto, digite os critérios de pesquisa que você deseja usar para filtrar os resultados da pesquisa e, em seguida, clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="113e5-135">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6. <span data-ttu-id="113e5-136">Os resultados da pesquisa aparecem em **Resultados da pesquisa**.</span><span class="sxs-lookup"><span data-stu-id="113e5-136">The search results appear under **Search Results**.</span></span> <span data-ttu-id="113e5-137">Você pode selecionar qualquer um ou todos os usuários na lista e executar tarefas de configuração sobre os usuários selecionados.</span><span class="sxs-lookup"><span data-stu-id="113e5-137">You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a><span data-ttu-id="113e5-138">Adicionar e habilitar um novo Skype para usuário Business Server</span><span class="sxs-lookup"><span data-stu-id="113e5-138">Add and enable a new Skype for Business Server user</span></span>
<span data-ttu-id="113e5-139"><a name="Add"> </a></span><span class="sxs-lookup"><span data-stu-id="113e5-139"></span></span>

<span data-ttu-id="113e5-140">Após habilitar uma conta de usuário no Active Directory Users and Computers, você pode usar o Skype para painel de controle do Business Server para criar e habilitar nova Skype para contas de usuário do servidor de negócios, adicionando um usuário do Active Directory à Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="113e5-140">After enabling a user account in Active Directory Users and Computers, you can use Skype for Business Server Control Panel to create and enable new Skype for Business Server user accounts by adding an Active Directory user to Skype for Business Server.</span></span>

<span data-ttu-id="113e5-141">Você também pode usar um cmdlet, especificamente [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="113e5-141">You can also use a cmdlet, specifically [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span></span>

1. <span data-ttu-id="113e5-142">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="113e5-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="113e5-143">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="113e5-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="113e5-144">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="113e5-144">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="113e5-145">Clique em **Permitir que os usuários**.</span><span class="sxs-lookup"><span data-stu-id="113e5-145">Click **Enable users**.</span></span>

5. <span data-ttu-id="113e5-146">Na caixa de diálogo **Novo usuário do Lync Server** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="113e5-146">On the **New Lync Server User** dialog, click **Add**.</span></span>

6. <span data-ttu-id="113e5-147">Na caixa **Pesquisar usuários** , digite todo ou a primeira parte do nome, exibir o nome, nome, sobrenome, nome de conta do Gerenciador de contas de segurança (SAM), endereço de email, Nome Principal do usuário (UPN) ou número de telefone da conta de usuário do Active Directory que você deseja e, em seguida, clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="113e5-147">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7. <span data-ttu-id="113e5-148">Na tabela, selecione a conta que você deseja adicionar ao Skype para Business Server e clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="113e5-148">In the table, select the account you want to add to Skype for Business Server, and then click **OK**.</span></span>

8. <span data-ttu-id="113e5-149">Atribuir ao usuário a um pool, especifique qualquer detalhe adicional, atribua as políticas ao usuário desejado e clique em **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="113e5-149">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a><span data-ttu-id="113e5-150">Desabilitar ou reabilitar uma conta de usuário que antes estavam habilitada para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="113e5-150">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>
<span data-ttu-id="113e5-151"><a name="Disable"> </a></span><span class="sxs-lookup"><span data-stu-id="113e5-151"></span></span>

<span data-ttu-id="113e5-152">Você pode usar o procedimento a seguir para desabilitar uma conta de usuário habilitada anteriormente no Skype para Business Server sem perder o Skype pelas configurações do servidor de negócios que você configurou para a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="113e5-152">You can use the following procedure to disable a previously enabled user account in Skype for Business Server without losing the Skype for Business Server settings that you configured for the user account.</span></span> <span data-ttu-id="113e5-153">Porque você não perca o Skype para configurações de conta de usuário do Business Server, você pode reativar uma conta de usuário habilitada anteriormente novamente sem a necessidade de reconfigurar a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="113e5-153">Because you do not lose the Skype for Business Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

1. <span data-ttu-id="113e5-154">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="113e5-154">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="113e5-155">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="113e5-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="113e5-156">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="113e5-156">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="113e5-157">Na caixa **Pesquisar usuários** , digite todo ou a primeira parte do nome para exibição, nome, sobrenome, nome de conta do Gerenciador de contas de segurança (SAM), endereço SIP ou linha identificador URI (Uniform Resource) da conta de usuário que você deseja desabilitar ou reabilitar, e, em seguida, clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="113e5-157">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="113e5-158">Na tabela, clique na conta de usuário que você deseja desabilitar ou reabilitar.</span><span class="sxs-lookup"><span data-stu-id="113e5-158">In the table, click the user account that you want to disable or re-enable.</span></span>

6. <span data-ttu-id="113e5-159">No menu **ação** , siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="113e5-159">On the **Action** menu, do one of the following:</span></span>

   - <span data-ttu-id="113e5-160">Para desabilitar temporariamente a conta de usuário para Skype para Business Server, clique em **desabilitar temporariamente para o Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="113e5-160">To temporarily disable the user account for Skype for Business Server, click **Temporarily disable for Lync Server**.</span></span>

   - <span data-ttu-id="113e5-161">Para habilitar a conta de usuário para Skype para Business Server, clique em **reabilitar para o Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="113e5-161">To enable the user account for Skype for Business Server, click **Re-enable for Lync Server**.</span></span>

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="113e5-162">Usar o Windows Powershell para desabilitar ou reabilitar em contas de usuário</span><span class="sxs-lookup"><span data-stu-id="113e5-162">Use Windows Powershell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="113e5-163">Contas de usuário podem ser temporariamente desabilitadas e então posteriormente reabilitadas, usando o cmdlet **Set-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="113e5-163">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="113e5-164">Você pode executar este cmdlet do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="113e5-164">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="113e5-165">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype para Business Server, consulte o artigo do blog ["rápida iniciar: Gerenciando Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="113e5-165">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="113e5-166">O processo é o mesmo em Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="113e5-166">The process is the same in Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account"></a><span data-ttu-id="113e5-167">Para desativar uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="113e5-167">To disable a user account</span></span>

- <span data-ttu-id="113e5-168">Para desabilitar temporariamente uma conta de usuário, defina o valor da propriedade Enabled como False ($False).</span><span class="sxs-lookup"><span data-stu-id="113e5-168">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="113e5-169">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="113e5-169">For example:</span></span>

  ```
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a><span data-ttu-id="113e5-170">Para reabilitar uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="113e5-170">To re-enable a user account</span></span>

- <span data-ttu-id="113e5-171">Para reativar uma conta de usuário desabilitada, defina o valor da propriedade Enabled como True ($True).</span><span class="sxs-lookup"><span data-stu-id="113e5-171">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="113e5-172">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="113e5-172">For example:</span></span>

  ```
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

<span data-ttu-id="113e5-173">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="113e5-173">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="disable-a-user-for-enterprise-voice"></a><span data-ttu-id="113e5-174">Desabilitar um usuário para o Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="113e5-174">Disable a user for Enterprise Voice</span></span>
<span data-ttu-id="113e5-175"><a name="Disable_EV"> </a></span><span class="sxs-lookup"><span data-stu-id="113e5-175"></span></span>

<span data-ttu-id="113e5-176">Use o procedimento a seguir para desabilitar o Enterprise Voice para uma conta de usuário que está habilitada para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="113e5-176">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="113e5-177">Para desativar uma conta de usuário para o Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="113e5-177">To disable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="113e5-178">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="113e5-178">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="113e5-179">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="113e5-179">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="113e5-180">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="113e5-180">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="113e5-181">Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="113e5-181">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5. <span data-ttu-id="113e5-182">Na tabela, clique na conta de usuário que você deseja habilitar para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="113e5-182">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6. <span data-ttu-id="113e5-183">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="113e5-183">On the **Edit** menu, click **Show details**.</span></span>

7. <span data-ttu-id="113e5-184">Na página **Editar usuário do Lync Server** , em **telefonia**, clique em qualquer opção exceto **Enterprise Voice**.</span><span class="sxs-lookup"><span data-stu-id="113e5-184">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="113e5-185">Para impedir que um usuário fazer chamadas de áudio ou vídeos usando o Lync, em **telefonia**, clique em **áudio/vídeo desabilitado**.</span><span class="sxs-lookup"><span data-stu-id="113e5-185">To restrict a user from making audio or video calls by using Lync, under **Telephony**, click **Audio/video disabled**.</span></span>

8. <span data-ttu-id="113e5-186">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="113e5-186">Click **Commit**.</span></span>

<span data-ttu-id="113e5-187">O usuário agora está apto a usar o recurso de Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="113e5-187">The user is now unable to use the Enterprise Voice feature.</span></span> <span data-ttu-id="113e5-188">Informações relacionadas:</span><span class="sxs-lookup"><span data-stu-id="113e5-188">Related information:</span></span> <br/>[<span data-ttu-id="113e5-189">Enterprise Voice e mobilidade</span><span class="sxs-lookup"><span data-stu-id="113e5-189">Enterprise Voice and mobility</span></span>](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [<span data-ttu-id="113e5-190">Habilitar usuários para o Enterprise Voice no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="113e5-190">Enable users for Enterprise Voice in Skype for Business Server</span></span>](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [<span data-ttu-id="113e5-191">Shell de Gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="113e5-191">Skype for Business Server Management Shell</span></span>](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a><span data-ttu-id="113e5-192">Remover uma conta de usuário com o Skype do Shell de gerenciamento do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="113e5-192">Remove a user account with the Skype for Business Server Management Shell</span></span>
<span data-ttu-id="113e5-193"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="113e5-193"></span></span>

<span data-ttu-id="113e5-194">Você pode usar o procedimento a seguir para remover uma conta de usuário adicionada anteriormente no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="113e5-194">You can use the following procedure to remove a previously added user account in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="113e5-195">Remover um usuário fará com que a perda de quaisquer configurações que você configurou para a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="113e5-195">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="113e5-196">Se você quiser desabilitar temporariamente uma conta de usuário em vez disso, consulte [desabilitar ou reabilitar uma conta de usuário que antes estavam habilitada para Skype para Business Server](user-accounts.md#Disable).</span><span class="sxs-lookup"><span data-stu-id="113e5-196">If you would like to temporarily disable a user account instead, see [Disable or re-enable a user account previously enabled for Skype for Business Server](user-accounts.md#Disable).</span></span>

1. <span data-ttu-id="113e5-197">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="113e5-197">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="113e5-198">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="113e5-198">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="113e5-199">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="113e5-199">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="113e5-200">Na caixa **Pesquisar usuários** , digite todo ou a primeira parte do nome para exibição, nome, sobrenome, nome de conta do Gerenciador de contas de segurança (SAM), endereço SIP ou linha identificador URI (Uniform Resource) da conta de usuário que você deseja desabilitar ou reabilitar, e, em seguida, clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="113e5-200">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="113e5-201">Na tabela, clique na conta de usuário que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="113e5-201">In the table, click the user account that you want to remove.</span></span>

6. <span data-ttu-id="113e5-202">No menu **ação** , selecione **Remover do Lync Server**e uma caixa de diálogo caixa é exibida.</span><span class="sxs-lookup"><span data-stu-id="113e5-202">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7. <span data-ttu-id="113e5-203">Na caixa de diálogo, selecione **Okey** para remover o usuário.</span><span class="sxs-lookup"><span data-stu-id="113e5-203">From the dialog box, select **OK** to remove the user.</span></span>

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a><span data-ttu-id="113e5-204">Remover contas de usuário com os cmdlets do Windows Powershell</span><span class="sxs-lookup"><span data-stu-id="113e5-204">Remove user accounts with Windows Powershell cmdlets</span></span>

<span data-ttu-id="113e5-205">Você pode remover as contas de usuário usando o cmdlet Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="113e5-205">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="113e5-206">Este cmdlet pode ser executado a partir do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="113e5-206">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="113e5-207">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype para Business Server, consulte o artigo do blog ["rápida iniciar: Gerenciando Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="113e5-207">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="113e5-208">O processo é o mesmo em Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="113e5-208">The process is the same in Skype for Business Server.</span></span>

### <a name="to-remove-a-user-account"></a><span data-ttu-id="113e5-209">Para remover uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="113e5-209">To remove a user account</span></span>
<span data-ttu-id="113e5-210">Para remover uma conta de usuário, use o cmdlet Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="113e5-210">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="113e5-211">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="113e5-211">For example:</span></span>

  ```
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

<span data-ttu-id="113e5-212">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="113e5-212">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="113e5-213">Confira também</span><span class="sxs-lookup"><span data-stu-id="113e5-213">See also</span></span>
<span data-ttu-id="113e5-214"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="113e5-214"></span></span>

[<span data-ttu-id="113e5-215">Enable-CsUser</span><span class="sxs-lookup"><span data-stu-id="113e5-215">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[<span data-ttu-id="113e5-216">Disable-CsUser</span><span class="sxs-lookup"><span data-stu-id="113e5-216">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)
