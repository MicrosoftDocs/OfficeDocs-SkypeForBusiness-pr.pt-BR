---
title: Atribuir uma política pin por usuário no Skype for Business Server
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
ms.collection: IT_Skype16
ms.assetid: d8211c64-0b63-4193-a074-673da7d14287
description: 'Resumo: Estágio AV e certificados OAuth para Skype for Business Server.'
ms.openlocfilehash: 6a0d0a1824e809a70dfee419fb5da1f663d8d779
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828521"
---
# <a name="assign-a-per-user-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="00556-103">Atribuir uma política pin por usuário no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="00556-103">Assign a per-user PIN policy in Skype for Business Server</span></span>

<span data-ttu-id="00556-104">**Resumo:** Stage AV and OAuth certificates for Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="00556-104">**Summary:** Stage AV and OAuth certificates for Skype for Business Server.</span></span>
  
<span data-ttu-id="00556-105">A política de PIN (número de identificação pessoal) de conferência discada é uma das configurações individuais de uma conta de usuário que podem ser configuradas no Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="00556-105">The dial-in conferencing personal identification number (PIN) policy is one of the individual settings of a user account that can be configured in the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="00556-p101">A implantação de uma ou mais políticas de PIN por usuário é opcional. Também é possível implantar somente uma política de PIN de nível global ou política de PIN de nível de site. Se você implantar políticas por usuário, deverá atribui-las explicitamente aos usuários, grupos ou objeto de contato. Direitos e permissões do usuário relacionados ao uso de PINs para conferência discada assumem automaticamente o padrão daqueles definidos na política de PIN de nível global quando nenhuma política específica de nível de site ou por usuário é atribuída.</span><span class="sxs-lookup"><span data-stu-id="00556-p101">Deploying one or more per-user PIN policies is optional. You can also deploy only a global-level PIN policy or site-level PIN policy. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object. User rights and permissions regarding the use of PINs for dial-in conferencing automatically default to those defined in the global-level PIN policy when no specific site-level or per-user policy is assigned.</span></span>
  
<span data-ttu-id="00556-110">Após a criação de pelo menos uma política de PIN por usuário, use o procedimento neste tópico para atribuir a política que especifica as restrições que você deseja que o servidor imponha sobre os PINs criados e usados por um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="00556-110">After creating at least one per-user PIN policy, use the procedures in this topic to assign the policy that specifies the constraints you want the server to impose on the PINs created by and used by a particular user.</span></span>
  
### <a name="to-assign-a-per-user-pin-policy"></a><span data-ttu-id="00556-111">Para atribuir uma política de PIN por usuário</span><span class="sxs-lookup"><span data-stu-id="00556-111">To assign a per-user PIN policy</span></span>

1. <span data-ttu-id="00556-112">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="00556-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="00556-113">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="00556-113">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="00556-114">Na barra de navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="00556-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="00556-115">Utilize um dos métodos a seguir para localizar um usuário:</span><span class="sxs-lookup"><span data-stu-id="00556-115">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="00556-116">Na caixa **Buscar usuários**, digite toda ou a primeira parte do nome de exibição, nome, sobrenome, nome da conta do Gerenciador de Contas de Segurança (SAM), endereço SIP ou linha do Uniform Resource Identifier (URI) da conta de usuário, e então clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="00556-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="00556-117">Se você tiver uma consulta salva, clique no ícone **Abrir consulta**, utilize a caixa de diálogo **Abrir**  para obter a consulta (um arquivo .usf) e, então, clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="00556-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="00556-118">(Opcional) Especifique critérios de busca adicionais para limitar os resultados:</span><span class="sxs-lookup"><span data-stu-id="00556-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="00556-119">a.</span><span class="sxs-lookup"><span data-stu-id="00556-119">a.</span></span> <span data-ttu-id="00556-120">Clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="00556-120">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="00556-121">b.</span><span class="sxs-lookup"><span data-stu-id="00556-121">b.</span></span> <span data-ttu-id="00556-122">Insira a propriedade de usuário digitando ou clicando na seta na lista suspensa para selecionar a propriedade.</span><span class="sxs-lookup"><span data-stu-id="00556-122">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="00556-123">c.</span><span class="sxs-lookup"><span data-stu-id="00556-123">c.</span></span> <span data-ttu-id="00556-124">Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).</span><span class="sxs-lookup"><span data-stu-id="00556-124">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="00556-125">d.</span><span class="sxs-lookup"><span data-stu-id="00556-125">d.</span></span> <span data-ttu-id="00556-126">Dependendo da propriedade do usuário selecionada, insira os critérios que você deseja usar para filtrar os resultados pesquisa, digitando-os ou clicando na seta na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="00556-126">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="00556-127">Para adicionar cláusulas de pesquisa à sua consulta, clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="00556-127">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="00556-128">e.</span><span class="sxs-lookup"><span data-stu-id="00556-128">e.</span></span> <span data-ttu-id="00556-129">Clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="00556-129">Click **Find**.</span></span>
    
6. <span data-ttu-id="00556-130">Clique em um usuário nos resultados da pesquisa, clique em **Ação** e clique em **Atribuir políticas**.</span><span class="sxs-lookup"><span data-stu-id="00556-130">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="00556-131">Se você quiser a mesma política de PIN por usuário aplicada a diversos usuários, selecione múltiplos usuários nos resultados da pesquisa e clique em **Ações** e em **Atribuir políticas**.</span><span class="sxs-lookup"><span data-stu-id="00556-131">If you want the same per-user PIN policy to apply to multiple users, select multiple users in the search results, then click **Actions**, and then click **Assign policies**.</span></span> 
  
7. <span data-ttu-id="00556-132">Em **Atribuir Políticas**, em **Política de PIN**, execute uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="00556-132">In **Assign Policies**, under **PIN policy**, do one of the following:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="00556-133">Como há várias políticas que você  pode configurar usando a caixa de diálogo Atribuir Políticas, ela é selecionada por padrão para cada política **\<Keep as is\>** na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="00556-133">Because there are multiple policies that you can configure by using the **Assign Policies** dialog box, **\<Keep as is\>** is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="00556-134">Para continuar usando a política previamente atribuída ao usuário, basta não fazer nenhuma alteração nessa configuração.</span><span class="sxs-lookup"><span data-stu-id="00556-134">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>
  
   - <span data-ttu-id="00556-135">Permita que o Skype for Business Server escolha automaticamente a política de nível global ou, se definida, a política de nível de site.</span><span class="sxs-lookup"><span data-stu-id="00556-135">Allow Skype for Business Server to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
   - <span data-ttu-id="00556-136">Clique no nome de uma política PIN por usuário definida anteriormente na página **Política de PIN**.</span><span class="sxs-lookup"><span data-stu-id="00556-136">Click the name of a per-user PIN policy you previously defined on the **PIN Policy** page.</span></span>
    
     > [!TIP]
     > <span data-ttu-id="00556-137">Para ajudá-lo a decidir a política que você deseja atribuir, após clicar em um nome de política, clique em **Exibir** para exibir os direitos e permissões de usuário definidos na política.</span><span class="sxs-lookup"><span data-stu-id="00556-137">To help you decide the policy you want to assign, after you click a policy name, click **View** to view the user rights and permissions defined in the policy.</span></span>
  
8. <span data-ttu-id="00556-138">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="00556-138">When you are finished, click **OK**.</span></span>
    
## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="00556-139">Atribuindo uma política Per-User PIN usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="00556-139">Assigning a Per-User PIN Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="00556-140">Você pode atribuir políticas de PIN por usuário usando o Windows PowerShell e o cmdlet **Grant-CsPinPolicy.**</span><span class="sxs-lookup"><span data-stu-id="00556-140">You can assign per-user PIN policies by using Windows PowerShell and the **Grant-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="00556-141">Você pode executar este cmdlet usando o Shell de gerenciamento do Skype for Business Server ou uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="00556-141">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="00556-142">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo do blog ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="00556-142">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="00556-143">O processo é o mesmo no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="00556-143">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a><span data-ttu-id="00556-144">Para atribuir uma política PIN por usuário para um único usuário</span><span class="sxs-lookup"><span data-stu-id="00556-144">To assign a per-user PIN policy to a single user</span></span>

- <span data-ttu-id="00556-145">O seguinte comando atribui a política PIN por usuário RedmondPinPolicy para o usuário Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="00556-145">The following command assigns the per-user PIN policy RedmondPinPolicy to the user Ken Myer.</span></span>
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"
  ```

### <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a><span data-ttu-id="00556-146">Para atribuir uma política PIN por usuário a vários usuários</span><span class="sxs-lookup"><span data-stu-id="00556-146">To assign a per-user PIN policy to multiple users</span></span>

- <span data-ttu-id="00556-147">O seguinte comando atribui a política PIN por usuário RedmondUsersPinPolicy para todos os usuários que trabalham na cidade de Redmond.</span><span class="sxs-lookup"><span data-stu-id="00556-147">The following command assigns the per-user PIN policy RedmondUsersPinPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="00556-148">Para obter detalhes sobre o parâmetro LdapFilter usado neste comando, [consulte Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="00556-148">For details about the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```PowerShell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"
  ```

### <a name="to-unassign-a-per-user-pin-policy"></a><span data-ttu-id="00556-149">Para retirar a atribuição de uma política PIN por usuário</span><span class="sxs-lookup"><span data-stu-id="00556-149">To unassign a per-user PIN policy</span></span>

- <span data-ttu-id="00556-p110">O seguinte comando retira a atribuição de qualquer política PIN por usuário anteriormente atribuído ao Ken Myer. Após a política por usuário ser retirada, Ken irá automaticamente ser gerenciado usando a política global ou, se existir, sua política de site local. Uma política de site tem precedência sobre a política global.</span><span class="sxs-lookup"><span data-stu-id="00556-p110">The following command unassigns any per-user PIN policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

<span data-ttu-id="00556-153">Para obter detalhes, [consulte Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="00556-153">For details, see [Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="00556-154">Confira também</span><span class="sxs-lookup"><span data-stu-id="00556-154">See also</span></span>

[<span data-ttu-id="00556-155">Criar uma nova política de PIN no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="00556-155">Create a new PIN policy in Skype for Business Server</span></span>](create-a-new-pin-policy.md)
