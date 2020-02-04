---
title: 'Lync Server 2013: atribuir uma política de PIN por usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user PIN policy
ms:assetid: d8211c64-0b63-4193-a074-673da7d14287
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182594(v=OCS.15)
ms:contentKeyID: 48185475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0864fdf4d2356ee04e1084c2f6b0149b2a6ebd5a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722811"
---
# <a name="assign-a-per-user-pin-policy-in-lync-server-2013"></a><span data-ttu-id="23729-102">Atribuir uma política de PIN por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23729-102">Assign a per-user PIN policy in Lync Server 2013</span></span>

 


<span data-ttu-id="23729-103">A política de número de identificação pessoal (PIN) da conferência discada é uma das configurações individuais de uma conta de usuário que pode ser configurada no painel de controle do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="23729-103">The dial-in conferencing personal identification number (PIN) policy is one of the individual settings of a user account that can be configured in the Lync Server 2013 Control Panel.</span></span>

<span data-ttu-id="23729-p101">A implantação de uma ou mais políticas de PIN por usuário é opcional. Também é possível implantar somente uma política de PIN de nível global ou política de PIN de nível de site. Se você implantar políticas por usuário, deverá atribui-las explicitamente aos usuários, grupos ou objeto de contato. Direitos e permissões do usuário relacionados ao uso de PINs para conferência discada assumem automaticamente o padrão daqueles definidos na política de PIN de nível global quando nenhuma política específica de nível de site ou por usuário é atribuída.</span><span class="sxs-lookup"><span data-stu-id="23729-p101">Deploying one or more per-user PIN policies is optional. You can also deploy only a global-level PIN policy or site-level PIN policy. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object. User rights and permissions regarding the use of PINs for dial-in conferencing automatically default to those defined in the global-level PIN policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="23729-108">Após a criação de pelo menos uma política de PIN por usuário, use o procedimento neste tópico para atribuir a política que especifica as restrições que você deseja que o servidor imponha sobre os PINs criados e usados por um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="23729-108">After creating at least one per-user PIN policy, use the procedures in this topic to assign the policy that specifies the constraints you want the server to impose on the PINs created by and used by a particular user.</span></span>

<span data-ttu-id="23729-109">Para obter detalhes sobre como criar políticas de PIN de conferência discada do usuário, consulte [criar ou modificar as configurações de PIN de conferência discada no Lync Server 2013 para um site ou grupo de usuários](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).</span><span class="sxs-lookup"><span data-stu-id="23729-109">For details about creating per-user dial-in conferencing PIN policies, see [Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).</span></span>

## <a name="to-assign-a-per-user-pin-policy"></a><span data-ttu-id="23729-110">Para atribuir uma política de PIN por usuário</span><span class="sxs-lookup"><span data-stu-id="23729-110">To assign a per-user PIN policy</span></span>

1.  <span data-ttu-id="23729-111">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="23729-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="23729-112">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="23729-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="23729-113">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="23729-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="23729-114">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="23729-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="23729-115">Use um dos seguintes métodos para localizar um usuário:</span><span class="sxs-lookup"><span data-stu-id="23729-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="23729-116">Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="23729-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="23729-117">Se você salvou uma consulta, clique no ícone **Abrir consulta**, use a caixa de diálogo **Abrir** para recuperar a consulta (um arquivo .usf) e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="23729-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="23729-118">(Opcional) Especifique o critério de pesquisa adicional para reduzir os resultados:</span><span class="sxs-lookup"><span data-stu-id="23729-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="23729-119">Clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="23729-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="23729-120">Insira a propriedade do usuário digitando ou clicando na seta da lista suspensa para selecionar a propriedade.</span><span class="sxs-lookup"><span data-stu-id="23729-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="23729-121">Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).</span><span class="sxs-lookup"><span data-stu-id="23729-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="23729-122">Dependendo da propriedade do usuário selecionada, insira o critério que deseja usar para filtrar os resultados de pesquisa digitando ou clicando na seta da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="23729-122">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="23729-123">Para adicionar cláusulas de pesquisa adicionais à sua consulta, clique em <STRONG>Adicionar filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="23729-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="23729-124">Clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="23729-124">Click **Find**.</span></span>

6.  <span data-ttu-id="23729-125">Clique em um usuário nos resultados da pesquisa, clique em **Ação** e em seguida, clique em **Atribuir políticas**.</span><span class="sxs-lookup"><span data-stu-id="23729-125">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="23729-126">Se você quiser a mesma política de PIN por usuário aplicada a diversos usuários, selecione múltiplos usuários nos resultados da pesquisa e clique em  <STRONG>Ações</STRONG>e em <STRONG>Atribuir políticas</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="23729-126">If you want the same per-user PIN policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="23729-127">Em **Atribuir Políticas**, em **Política de PIN**, execute uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="23729-127">In **Assign Policies**, under **PIN policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="23729-128">Como há várias diretivas que você pode configurar usando a caixa de diálogo <STRONG>atribuir políticas</STRONG> , <STRONG> &lt;manter como está&gt; </STRONG> selecionado por padrão para cada política na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="23729-128">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="23729-129">Continue usando a política atribuída anteriormente ao usuário não realizando alterações nesta configuração.</span><span class="sxs-lookup"><span data-stu-id="23729-129">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="23729-130">Permitir que o Lync Server 2013 escolha automaticamente a política de nível global ou, se definida, a política de nível de site.</span><span class="sxs-lookup"><span data-stu-id="23729-130">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="23729-131">Clique no nome de uma política PIN por usuário definida anteriormente na página  **Política de PIN**.</span><span class="sxs-lookup"><span data-stu-id="23729-131">Click the name of a per-user PIN policy you previously defined on the **PIN Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="23729-132">Para ajudar a decidir a política que deseja atribuir, após clicar no nome da política, clique em <STRONG>Exibir</STRONG> para visualizar os direitos e permissões do usuário definidos na política.</span><span class="sxs-lookup"><span data-stu-id="23729-132">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="23729-133">Ao concluir, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="23729-133">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="23729-134">Atribuindo uma política de PIN por usuário usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="23729-134">Assigning a Per-User PIN Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="23729-135">Você pode atribuir políticas de PIN por usuário usando o Windows PowerShell e o cmdlet **Grant-CsPinPolicy** .</span><span class="sxs-lookup"><span data-stu-id="23729-135">You can assign per-user PIN policies by using Windows PowerShell and the **Grant-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="23729-136">Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23729-136">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="23729-137">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="23729-137">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a><span data-ttu-id="23729-138">Para atribuir uma política PIN por usuário a um único usuário</span><span class="sxs-lookup"><span data-stu-id="23729-138">To assign a per-user PIN policy to a single user</span></span>

  - <span data-ttu-id="23729-139">O seguinte comando atribui a política PIN por usuário RedmondPinPolicy ao usuário Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="23729-139">The following command assigns the per-user PIN policy RedmondPinPolicy to the user Ken Myer.</span></span>
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"

## <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a><span data-ttu-id="23729-140">Para atribuir uma política PIN por usuário a vários usuários</span><span class="sxs-lookup"><span data-stu-id="23729-140">To assign a per-user PIN policy to multiple users</span></span>

  - <span data-ttu-id="23729-141">O seguinte comando atribui a política PIN por usuário RedmondUsersPinPolicy a todos os usuários que trabalham na cidade de Redmond.</span><span class="sxs-lookup"><span data-stu-id="23729-141">The following command assigns the per-user PIN policy RedmondUsersPinPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="23729-142">Para obter detalhes sobre o parâmetro LdapFilter usado neste comando, consulte [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="23729-142">For details about the LdapFilter parameter used in this command, see [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)).</span></span>
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"

## <a name="to-unassign-a-per-user-pin-policy"></a><span data-ttu-id="23729-143">Para retirar a atribuição de uma política PIN por usuário</span><span class="sxs-lookup"><span data-stu-id="23729-143">To unassign a per-user PIN policy</span></span>

  - <span data-ttu-id="23729-p106">O seguinte comando retira a atribuição de qualquer política PIN por usuário anteriormente atribuída a Ken Myer. Após a política por usuário ser retirada, Ken irá automaticamente ser gerenciado usando a política global ou, se existir, sua política de site local. Uma política de site tem precedência sobre a política global.</span><span class="sxs-lookup"><span data-stu-id="23729-p106">The following command unassigns any per-user PIN policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="23729-147">Para obter detalhes, consulte [Grant-CsPinPolicy](https://technet.microsoft.com/en-us/library/gg398871\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="23729-147">For details, see [Grant-CsPinPolicy](https://technet.microsoft.com/en-us/library/gg398871\(v=ocs.15\)).</span></span>

## <a name="see-also"></a><span data-ttu-id="23729-148">Confira também</span><span class="sxs-lookup"><span data-stu-id="23729-148">See Also</span></span>


[<span data-ttu-id="23729-149">Criar uma nova política de PIN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23729-149">Create a new PIN policy in Lync Server 2013</span></span>](lync-server-2013-create-a-new-pin-policy.md)  


[<span data-ttu-id="23729-150">Como atribuir políticas por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23729-150">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

