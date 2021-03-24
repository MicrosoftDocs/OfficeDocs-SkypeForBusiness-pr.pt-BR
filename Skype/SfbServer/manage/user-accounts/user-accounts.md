---
title: Gerenciar contas de usuário para o Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: As seções deste artigo descrevem como habilitar, desabilitar temporariamente ou remover usuários do Active Directory do Skype for Business Server.
ms.openlocfilehash: 0cf78b4ebe7023bc5a0f1b4af75c5d9e5a45db1b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103117"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a><span data-ttu-id="fbd3c-103">Gerenciar contas de usuário para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fbd3c-103">Manage user accounts for Skype for Business Server</span></span>

<span data-ttu-id="fbd3c-104">As seções deste artigo descrevem como habilitar, desabilitar temporariamente ou remover usuários do Active Directory do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-104">The sections in this article describe how to enable, temporarily disable, or remove Active Directory users from Skype for Business Server.</span></span>

<span data-ttu-id="fbd3c-105">Para obter informações sobre como habilitar um usuário do Active Directory, consulte [Create a New User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732336(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="fbd3c-105">For information on how to enable an Active Directory user, see [Create a New User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732336(v=ws.11)).</span></span> <span data-ttu-id="fbd3c-106">Para obter informações sobre como excluir um usuário do Active Directory, consulte [Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="fbd3c-106">For information on how to delete an Active Directory user, see [Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).</span></span>

<span data-ttu-id="fbd3c-107">Esses procedimentos devem ser executados durante uma janela de manutenção, quando o uso do Skype for Business for menor.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-107">These procedures should be performed during a maintenance window, when Skype for Business usage is lowest.</span></span> <span data-ttu-id="fbd3c-108">Se isso for feito em uma agenda diária ou semanal será determinado pelas necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-108">Whether this is done on a daily or weekly schedule will be determined by the needs of your organization.</span></span>

<span data-ttu-id="fbd3c-109">Este artigo contém os seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="fbd3c-109">This article contains the following procedures:</span></span>

- [<span data-ttu-id="fbd3c-110">Para pesquisar por um ou mais usuários</span><span class="sxs-lookup"><span data-stu-id="fbd3c-110">To search for one or more users</span></span>](user-accounts.md#Search)

- [<span data-ttu-id="fbd3c-111">Adicionar e habilitar um novo usuário do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fbd3c-111">Add and enable a new Skype for Business Server user</span></span>](user-accounts.md#Add)

- [<span data-ttu-id="fbd3c-112">Desabilitar ou reabilitar uma conta de usuário habilitada anteriormente para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fbd3c-112">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>](user-accounts.md#Disable)

- [<span data-ttu-id="fbd3c-113">Desabilitar um usuário para Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="fbd3c-113">Disable a user for Enterprise Voice</span></span>](user-accounts.md#Disable_EV)

- [<span data-ttu-id="fbd3c-114">Remover uma conta de usuário com o Shell de Gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fbd3c-114">Remove a user account with the Skype for Business Server Management Shell</span></span>](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="fbd3c-115">Para pesquisar por um ou mais usuários</span><span class="sxs-lookup"><span data-stu-id="fbd3c-115">To search for one or more users</span></span>
<span data-ttu-id="fbd3c-116"><a name="Search"> </a></span><span class="sxs-lookup"><span data-stu-id="fbd3c-116"><a name="Search"> </a></span></span>

<span data-ttu-id="fbd3c-117">Você pode usar os resultados de uma consulta de pesquisa para configurar usuários do Active Directory para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-117">You can use the results of a search query to configure Active Directory users for Skype for Business Server.</span></span> <span data-ttu-id="fbd3c-118">É possível pesquisar por usuários por nome de exibição, nome, sobrenome, nome de conta SAM (Gerenciador de contas de segurança), endereço SIP ou URI (Uniform Resource Identifier) de linha.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-118">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="fbd3c-119">Você pode pesquisar usuários usando o Painel de Controle do Skype for Business Server ou o snap-in Usuários e Computadores do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-119">You can search for users by using the Skype for Business Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="fbd3c-120">O procedimento a seguir descreve como usar o Painel de Controle do Skype for Business Server para pesquisar usuários.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-120">The following procedure describes how to use Skype for Business Server Control Panel to search for users.</span></span>

> [!NOTE]
> <span data-ttu-id="fbd3c-121">Em um ambiente com uma topologia de floresta central, os resultados da pesquisa podem não ser precisos quando você procura um usuário pelo endereço de email do usuário.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-121">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user's email address.</span></span> <span data-ttu-id="fbd3c-122">Em vez disso, você pode pesquisar usuários especificando um prefixo de endereço SIP, por exemplo, sip:name, adicionar um filtro de pesquisa e selecionar um endereço SIP que contenha um endereço de email parcial ou usar o cmdlet **Get-CSUser.**</span><span class="sxs-lookup"><span data-stu-id="fbd3c-122">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the **Get-CSUser** cmdlet.</span></span>

1. <span data-ttu-id="fbd3c-123">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="fbd3c-124">Abra uma janela do navegador e insira a URL do administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="fbd3c-125">Na barra de navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-125">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="fbd3c-126">Na  caixa Pesquisar usuários, digite todo ou a primeira parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta de usuário que você deseja pesquisar e clique em **Encontrar**.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-126">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5. <span data-ttu-id="fbd3c-127">(Opcional) Especifique critérios de busca adicionais para limitar os resultados:</span><span class="sxs-lookup"><span data-stu-id="fbd3c-127">(Optional) Specify additional search criteria to narrow the results:</span></span>

   <span data-ttu-id="fbd3c-128">a.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-128">a.</span></span> <span data-ttu-id="fbd3c-129">Clique no botão expandir seta no canto superior direito da tela acima **Resultados** da pesquisa e clique em **Adicionar Filtro**.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-129">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>

   <span data-ttu-id="fbd3c-130">b.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-130">b.</span></span> <span data-ttu-id="fbd3c-131">Insira a propriedade user digitando-a ou clicando na seta na listada para selecionar uma propriedade do usuário.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-131">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>

   <span data-ttu-id="fbd3c-132">c.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-132">c.</span></span> <span data-ttu-id="fbd3c-133">Na lista **Igual a,** clique em **Igual a** ou Não **igual a**.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-133">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>

   <span data-ttu-id="fbd3c-134">d.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-134">d.</span></span> <span data-ttu-id="fbd3c-135">Na caixa de texto, digite os critérios de pesquisa que você deseja usar para filtrar os resultados da pesquisa e clique em **Encontrar**.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-135">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6. <span data-ttu-id="fbd3c-136">Os resultados da pesquisa aparecem em **Resultados da Pesquisa**.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-136">The search results appear under **Search Results**.</span></span> <span data-ttu-id="fbd3c-137">Você pode selecionar qualquer um ou todos os usuários da lista e executar tarefas de configuração nos usuários selecionados.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-137">You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a><span data-ttu-id="fbd3c-138">Adicionar e habilitar um novo usuário do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fbd3c-138">Add and enable a new Skype for Business Server user</span></span>
<span data-ttu-id="fbd3c-139"><a name="Add"> </a></span><span class="sxs-lookup"><span data-stu-id="fbd3c-139"><a name="Add"> </a></span></span>

<span data-ttu-id="fbd3c-140">Depois de habilitar uma conta de usuário em Usuários e Computadores do Active Directory, você pode usar o Painel de Controle do Skype for Business Server para criar e habilitar novas contas de usuário do Skype for Business Server adicionando um usuário do Active Directory ao Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-140">After enabling a user account in Active Directory Users and Computers, you can use Skype for Business Server Control Panel to create and enable new Skype for Business Server user accounts by adding an Active Directory user to Skype for Business Server.</span></span>

<span data-ttu-id="fbd3c-141">Você também pode usar um cmdlet, especificamente [Enable-CsUser](/powershell/module/skype/enable-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="fbd3c-141">You can also use a cmdlet, specifically [Enable-CsUser](/powershell/module/skype/enable-csuser?view=skype-ps).</span></span>

1. <span data-ttu-id="fbd3c-142">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="fbd3c-143">Abra uma janela do navegador e insira a URL do administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="fbd3c-144">Na barra de navegação da esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-144">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="fbd3c-145">Clique em **Habilitar usuários**.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-145">Click **Enable users**.</span></span>

5. <span data-ttu-id="fbd3c-146">No diálogo **Novo Usuário do Lync Server**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-146">On the **New Lync Server User** dialog, click **Add**.</span></span>

6. <span data-ttu-id="fbd3c-147">Na caixa **Pesquisar usuários**, digite todo ou o primeiro nome, nome de exibição, nome, sobrenome, nome da conta SAM, endereço de email, UPN ou número de telefone da conta de usuário do Active Directory que você deseja e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-147">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7. <span data-ttu-id="fbd3c-148">Na tabela, selecione a conta que você deseja adicionar ao Skype for Business Server e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-148">In the table, select the account you want to add to Skype for Business Server, and then click **OK**.</span></span>

8. <span data-ttu-id="fbd3c-149">Atribua o usuário a um pool, especifique qualquer detalhe adicional, atribua as políticas ao usuário desejado e clique em **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-149">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a><span data-ttu-id="fbd3c-150">Desabilitar ou reabilitar uma conta de usuário habilitada anteriormente para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fbd3c-150">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>
<span data-ttu-id="fbd3c-151"><a name="Disable"> </a></span><span class="sxs-lookup"><span data-stu-id="fbd3c-151"><a name="Disable"> </a></span></span>

<span data-ttu-id="fbd3c-152">Você pode usar o procedimento a seguir para desabilitar uma conta de usuário habilitada anteriormente no Skype for Business Server sem perder as configurações do Skype for Business Server que você configurou para a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-152">You can use the following procedure to disable a previously enabled user account in Skype for Business Server without losing the Skype for Business Server settings that you configured for the user account.</span></span> <span data-ttu-id="fbd3c-153">Como você não perde as configurações da conta de usuário do Skype for Business Server, você pode habilitar novamente uma conta de usuário habilitada anteriormente sem precisar reconfigurar a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-153">Because you do not lose the Skype for Business Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

1. <span data-ttu-id="fbd3c-154">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-154">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="fbd3c-155">Abra uma janela do navegador e insira a URL do administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="fbd3c-156">Na barra de navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-156">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="fbd3c-157">Na caixa **Usuários de pesquisa**, digite todo ou a primeira parte do nome de exibição, primeiro nome, último nome, nome de conta do Gerenciador de contas de segurança (SAM), endereço SIP ou alinhe o Identificador de recurso uniforme (URI) da conta do usuário que você quer desabilitar ou reabilitar e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-157">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="fbd3c-158">Na tabela, clique na conta de usuário que você quer habilitar ou reabilitar.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-158">In the table, click the user account that you want to disable or re-enable.</span></span>

6. <span data-ttu-id="fbd3c-159">No menu **Ação**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fbd3c-159">On the **Action** menu, do one of the following:</span></span>

   - <span data-ttu-id="fbd3c-160">Para desabilitar temporariamente a conta de usuário do Skype for Business Server, clique em **Desabilitar temporariamente para o Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-160">To temporarily disable the user account for Skype for Business Server, click **Temporarily disable for Lync Server**.</span></span>

   - <span data-ttu-id="fbd3c-161">Para habilitar a conta de usuário do Skype for Business Server, clique **em Habilitar para o Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-161">To enable the user account for Skype for Business Server, click **Re-enable for Lync Server**.</span></span>

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="fbd3c-162">Usar o Windows Powershell para desabilitar ou habilitar contas de usuário</span><span class="sxs-lookup"><span data-stu-id="fbd3c-162">Use Windows Powershell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="fbd3c-163">As contas de usuário podem ser temporariamente desabilitadas e habilitadas posteriormente usando o cmdlet **Set-CsUser.**</span><span class="sxs-lookup"><span data-stu-id="fbd3c-163">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="fbd3c-164">Você pode executar esse cmdlet no Shell de Gerenciamento do Skype for Business Server ou em uma sessão remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-164">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="fbd3c-165">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo do blog "Início Rápido: Gerenciando o [Microsoft Lync Server 2010 usando o PowerShell Remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="fbd3c-165">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="fbd3c-166">O processo é o mesmo no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-166">The process is the same in Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account"></a><span data-ttu-id="fbd3c-167">Para desabilitar uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="fbd3c-167">To disable a user account</span></span>

- <span data-ttu-id="fbd3c-168">Para desabilitar uma conta temporariamente, defina o valor da propriedade Enabled como falso ($False).</span><span class="sxs-lookup"><span data-stu-id="fbd3c-168">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="fbd3c-169">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="fbd3c-169">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a><span data-ttu-id="fbd3c-170">Para habilitar uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="fbd3c-170">To re-enable a user account</span></span>

- <span data-ttu-id="fbd3c-171">Para reabilitar uma conta de usuário, defina o valor da propriedade Enabled como verdadeiro ($True).</span><span class="sxs-lookup"><span data-stu-id="fbd3c-171">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="fbd3c-172">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="fbd3c-172">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

<span data-ttu-id="fbd3c-173">Para obter mais informações, consulte o tópico de ajuda do cmdlet [Set-CsUser.](/powershell/module/skype/set-csuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="fbd3c-173">For more information, see the help topic for the [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="disable-a-user-for-enterprise-voice"></a><span data-ttu-id="fbd3c-174">Desabilitar um usuário para Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="fbd3c-174">Disable a user for Enterprise Voice</span></span>
<span data-ttu-id="fbd3c-175"><a name="Disable_EV"> </a></span><span class="sxs-lookup"><span data-stu-id="fbd3c-175"><a name="Disable_EV"> </a></span></span>

<span data-ttu-id="fbd3c-176">Use o procedimento a seguir para desabilitar Enterprise Voice para uma conta de usuário habilitada para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-176">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="fbd3c-177">Para desabilitar uma conta de usuário para Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="fbd3c-177">To disable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="fbd3c-178">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-178">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="fbd3c-179">Abra uma janela do navegador e insira a URL do administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-179">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="fbd3c-180">Na barra de navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-180">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="fbd3c-181">Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-181">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5. <span data-ttu-id="fbd3c-182">Na tabela, clique na conta de usuário que você deseja habilitar para Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-182">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6. <span data-ttu-id="fbd3c-183">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-183">On the **Edit** menu, click **Show details**.</span></span>

7. <span data-ttu-id="fbd3c-184">Na página **Editar usuário do servidor Lync**, sob **Telefonia**, clique em qualquer opção exceto **Enterprise Voice**.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-184">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fbd3c-185">Para restringir um usuário de fazer chamadas de áudio ou vídeo usando o Lync, em **Telefonia,** clique **em Áudio/vídeo desabilitado.**</span><span class="sxs-lookup"><span data-stu-id="fbd3c-185">To restrict a user from making audio or video calls by using Lync, under **Telephony**, click **Audio/video disabled**.</span></span>

8. <span data-ttu-id="fbd3c-186">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-186">Click **Commit**.</span></span>

<span data-ttu-id="fbd3c-187">O usuário agora não pode usar o recurso Enterprise Voice usuário.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-187">The user is now unable to use the Enterprise Voice feature.</span></span> <span data-ttu-id="fbd3c-188">Informações relacionadas:</span><span class="sxs-lookup"><span data-stu-id="fbd3c-188">Related information:</span></span> <br/>[<span data-ttu-id="fbd3c-189">Enterprise Voice e mobilidade</span><span class="sxs-lookup"><span data-stu-id="fbd3c-189">Enterprise Voice and mobility</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-managing-enterprise-voice-for-users)<br/> [<span data-ttu-id="fbd3c-190">Habilitar usuários para Enterprise Voice no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fbd3c-190">Enable users for Enterprise Voice in Skype for Business Server</span></span>](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [<span data-ttu-id="fbd3c-191">Shell de Gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fbd3c-191">Skype for Business Server Management Shell</span></span>](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a><span data-ttu-id="fbd3c-192">Remover uma conta de usuário com o Shell de Gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fbd3c-192">Remove a user account with the Skype for Business Server Management Shell</span></span>
<span data-ttu-id="fbd3c-193"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="fbd3c-193"><a name="Remove"> </a></span></span>

<span data-ttu-id="fbd3c-194">Você pode usar o procedimento a seguir para remover uma conta de usuário adicionada anteriormente no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-194">You can use the following procedure to remove a previously added user account in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="fbd3c-195">Remover um usuário pode causar a perda de qualquer configuração definida para a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-195">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="fbd3c-196">Se você quiser desabilitar temporariamente uma conta de usuário, consulte [Disable or re-enable a user account](user-accounts.md#Disable)previously enabled for Skype for Business Server .</span><span class="sxs-lookup"><span data-stu-id="fbd3c-196">If you would like to temporarily disable a user account instead, see [Disable or re-enable a user account previously enabled for Skype for Business Server](user-accounts.md#Disable).</span></span>

1. <span data-ttu-id="fbd3c-197">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-197">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="fbd3c-198">Abra uma janela do navegador e insira a URL do administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-198">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="fbd3c-199">Na barra de navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-199">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="fbd3c-200">Na caixa **Pesquisar usuários**, digite todo ou a primeira parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta de usuário que você deseja desabilitar ou reabilitar e clique em **Encontrar**.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-200">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="fbd3c-201">Na tabela, clique na conta de usuário que deseja remover.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-201">In the table, click the user account that you want to remove.</span></span>

6. <span data-ttu-id="fbd3c-202">No menu **Ação**, selecione **Remover do Lync Server** e uma caixa de diálogo aparece.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-202">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7. <span data-ttu-id="fbd3c-203">Na caixa de diálogo, selecione **OK** para remover o usuário.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-203">From the dialog box, select **OK** to remove the user.</span></span>

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a><span data-ttu-id="fbd3c-204">Remover contas de usuário com cmdlets do Windows Powershell</span><span class="sxs-lookup"><span data-stu-id="fbd3c-204">Remove user accounts with Windows Powershell cmdlets</span></span>

<span data-ttu-id="fbd3c-205">Você pode remover contas de usuário usando o Disable-CsUser cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-205">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="fbd3c-206">Esse cmdlet pode ser executado no Shell de Gerenciamento do Skype for Business Server ou em uma sessão remota Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-206">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="fbd3c-207">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo do blog "Início Rápido: Gerenciando o [Microsoft Lync Server 2010 usando o PowerShell Remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="fbd3c-207">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="fbd3c-208">O processo é o mesmo no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-208">The process is the same in Skype for Business Server.</span></span>

### <a name="to-remove-a-user-account"></a><span data-ttu-id="fbd3c-209">Para remover uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="fbd3c-209">To remove a user account</span></span>
<span data-ttu-id="fbd3c-210">Para remover uma conta de usuário, utilize o cmdlet Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="fbd3c-210">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="fbd3c-211">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="fbd3c-211">For example:</span></span>

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

<span data-ttu-id="fbd3c-212">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Disable-CsUser.](/powershell/module/skype/disable-csuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="fbd3c-212">For more information, see the help topic for the [Disable-CsUser](/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="fbd3c-213">Confira também</span><span class="sxs-lookup"><span data-stu-id="fbd3c-213">See also</span></span>
<span data-ttu-id="fbd3c-214"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="fbd3c-214"><a name="Remove"> </a></span></span>

[<span data-ttu-id="fbd3c-215">Enable-CsUser</span><span class="sxs-lookup"><span data-stu-id="fbd3c-215">Enable-CsUser</span></span>](/powershell/module/skype/enable-csuser?view=skype-ps)

[<span data-ttu-id="fbd3c-216">Disable-CsUser</span><span class="sxs-lookup"><span data-stu-id="fbd3c-216">Disable-CsUser</span></span>](/powershell/module/skype/disable-csuser?view=skype-ps)