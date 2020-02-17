---
title: 'Lync Server 2013: atribuir uma política de conferência por usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user conferencing policy
ms:assetid: 72f12c72-65f7-44fe-ab81-0f57cb2f87d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521015(v=OCS.15)
ms:contentKeyID: 48184475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c4fbef02553d4ba390dcf94f96f55936e2661b1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043313"
---
# <a name="assign-a-per-user-conferencing-policy-in-lync-server-2013"></a><span data-ttu-id="721aa-102">Atribuir uma política de conferência por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="721aa-102">Assign a per-user conferencing policy in Lync Server 2013</span></span>

 


<span data-ttu-id="721aa-103">A política de conferência é uma das configurações individuais de uma conta de usuário que você pode configurar no painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="721aa-103">The conferencing policy is one of the individual settings of a user account that you can configure in Lync Server Control Panel.</span></span>

<span data-ttu-id="721aa-p101">A implantação de uma ou mais políticas de conferência por usuário é opcional. Você também pode implantar somente uma política de conferência a nível global ou política de conferência a nível de site. Se você implantar políticas por usuário, deverá explicitamente atribuí-las a usuários, grupos ou objetos de contato. As permissões e direitos de usuário de conferência são automaticamente padrão para os que estão definidos na política de conferência a nível global, quando nenhuma política específica a nível de site ou por usuário é atribuída.</span><span class="sxs-lookup"><span data-stu-id="721aa-p101">Deploying one or more per-user conferencing policies is optional. You can also deploy only a global-level conferencing policy or site-level conferencing policy. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact objects. Conferencing user rights and permissions automatically default to those defined in the global-level conferencing policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="721aa-108">Depois de criar pelo menos uma política de conferência por usuário, use os procedimentos neste tópico para atribuir a política que especifica os direitos e permissões que você deseja que o servidor conceda a reuniões organizadas por um determinado usuário.</span><span class="sxs-lookup"><span data-stu-id="721aa-108">After creating at least one per-user conferencing policy, use the procedures in this topic to assign the policy that specifies the user rights and permissions that you want the server to grant to the meetings organized by a particular user.</span></span>

<span data-ttu-id="721aa-109">Para obter uma lista de todas as configurações de política de conferência disponíveis, consulte [referência de configurações de política de conferência para o Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span><span class="sxs-lookup"><span data-stu-id="721aa-109">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<span data-ttu-id="721aa-110">Para obter detalhes sobre como criar políticas de conferência, consulte [create or Modify a Conferencing Policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span><span class="sxs-lookup"><span data-stu-id="721aa-110">For details about creating conferencing policies, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span>

## <a name="to-assign-a-per-user-conferencing-policy"></a><span data-ttu-id="721aa-111">Para atribuir uma plítica de conferência por usuário</span><span class="sxs-lookup"><span data-stu-id="721aa-111">To assign a per-user conferencing policy</span></span>

1.  <span data-ttu-id="721aa-112">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="721aa-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="721aa-113">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="721aa-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="721aa-114">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="721aa-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="721aa-115">Na barra de navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="721aa-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="721aa-116">Utilize um dos métodos a seguir para localizar um usuário:</span><span class="sxs-lookup"><span data-stu-id="721aa-116">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="721aa-117">Na caixa **Buscar usuários**, digite toda ou a primeira parte do nome de exibição, nome, sobrenome, nome da conta do Gerenciador de Contas de Segurança (SAM), endereço SIP ou linha do Uniform Resource Identifier (URI) da conta de usuário, e então clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="721aa-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="721aa-118">Se você tiver uma consulta salva, clique no ícone **Abrir consulta**, utilize a caixa de diálogo **Abrir**  para obter a consulta (um arquivo .usf) e, então, clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="721aa-118">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="721aa-119">(Opcional) Especifique critérios de busca adicionais para limitar os resultados:</span><span class="sxs-lookup"><span data-stu-id="721aa-119">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="721aa-120">Clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="721aa-120">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="721aa-121">Insira a propriedade de usuário digitando ou clicando na seta na lista suspensa para selecionar a propriedade.</span><span class="sxs-lookup"><span data-stu-id="721aa-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="721aa-122">Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).</span><span class="sxs-lookup"><span data-stu-id="721aa-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="721aa-123">Dependendo da propriedade do usuário selecionada, insira os critérios que você deseja usar para filtrar os resultados pesquisa, digitando-os ou clicando na seta na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="721aa-123">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="721aa-124">Para adicionar cláusulas de pesquisa à sua consulta, clique em <STRONG>Adicionar filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="721aa-124">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="721aa-125">Clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="721aa-125">Click **Find**.</span></span>

6.  <span data-ttu-id="721aa-126">Clique em um usuário nos resultados da pesquisa, em **Ação** e em **Atribuir políticas**.</span><span class="sxs-lookup"><span data-stu-id="721aa-126">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="721aa-127">Se deseja que a mesma política de conferência por usuário seja aplicada a vários usuários, selecione vários usuários nos resultados da pesquisa e clique em <STRONG>Ações</STRONG> e em <STRONG>Atribuir políticas</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="721aa-127">If you want the same per-user conferencing policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="721aa-128">Em **Atribuir políticas**, na **Política de conferência**, faça o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="721aa-128">In **Assign Policies**, under **Conferencing policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="721aa-129">Como há várias políticas que você pode configurar em <STRONG>atribuir políticas</STRONG>, <STRONG> &lt;manter como está&gt; </STRONG> selecionada por padrão para todas as políticas da caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="721aa-129">Because there are multiple policies that you can configure in <STRONG>Assign Policies</STRONG>, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="721aa-130">Para continuar usando a política previamente atribuída ao usuário, basta não fazer nenhuma alteração nessa configuração.</span><span class="sxs-lookup"><span data-stu-id="721aa-130">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="721aa-131">Selecione \*\* \<automático\> \*\* para permitir que o Lync Server 2013 escolha automaticamente a política de nível global ou, se definida, a política de nível de site.</span><span class="sxs-lookup"><span data-stu-id="721aa-131">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="721aa-132">Clique no nome de uma política de conferência por usuário previamente definida na página **Política de conferência**.</span><span class="sxs-lookup"><span data-stu-id="721aa-132">Click the name of a per-user conferencing policy you previously defined on the **Conferencing Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="721aa-133">Para ajudar você a decidir a política que deseja atribuir, após clicar no nome da política, clique em <STRONG>Exibir</STRONG> para exibir os direitos e permissões do usuário definidos na política.</span><span class="sxs-lookup"><span data-stu-id="721aa-133">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="721aa-134">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="721aa-134">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-conferencing-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="721aa-135">Atribuindo uma política de conferência por usuário usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="721aa-135">Assigning a Per-User Conferencing Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="721aa-136">As políticas de conferência por usuário podem ser atribuídas usando o Windows PowerShell e o cmdlet Grant-CsConferencingPolicy.</span><span class="sxs-lookup"><span data-stu-id="721aa-136">Per-user conferencing policies can be assigned by using Windows PowerShell and the Grant-CsConferencingPolicy cmdlet.</span></span> <span data-ttu-id="721aa-137">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="721aa-137">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="721aa-138">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="721aa-138">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-conferencing-policy-to-a-single-user"></a><span data-ttu-id="721aa-139">Para atribuir uma política de conferência por usuário a um único usuário</span><span class="sxs-lookup"><span data-stu-id="721aa-139">To assign a per-user conferencing policy to a single user</span></span>

  - <span data-ttu-id="721aa-140">O comando a seguir atribui a política de conferência por usuário RedmondConferencingPolicy ao usuário Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="721aa-140">The following command assigns the per-user conferencing policy RedmondConferencingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName "RedmondConferencingPolicy"

## <a name="to-assign-a-per-user-conferencing-policy-to-multiple-users"></a><span data-ttu-id="721aa-141">Para atribuir uma política de conferência por usuário a vários usuários</span><span class="sxs-lookup"><span data-stu-id="721aa-141">To assign a per-user conferencing policy to multiple users</span></span>

  - <span data-ttu-id="721aa-142">Este comando atribui a política de conferência por usuário HRConferencingPolicy a todos os usuários que trabalham para o departamento de Recursos Humanos.</span><span class="sxs-lookup"><span data-stu-id="721aa-142">This command assigns the per-user conferencing policy HRConferencingPolicy to all the users who work for the Human Resources department.</span></span> <span data-ttu-id="721aa-143">Para obter mais informações sobre o parâmetro LdapFilter usado neste comando, consulte a documentação do cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="721aa-143">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=Human Resources" | Grant-CsConferencingPolicy -PolicyName "HRConferencingPolicy"

## <a name="to-unassign-a-per-user-conferencing-policy"></a><span data-ttu-id="721aa-144">Para cancelar a atribuição de uma política de conferência por usuário</span><span class="sxs-lookup"><span data-stu-id="721aa-144">To unassign a per-user conferencing policy</span></span>

  - <span data-ttu-id="721aa-p106">O comando a seguir cancela a atribuição de qualquer política de conferência por usuário atribuída a Ken Myer. Após o cancelamento da atribuição da política por usuário, Ken Myer será automaticamente gerenciado usando a política global ou a política de site local (se houver). Um política de site tem prioridade sobre a política global.</span><span class="sxs-lookup"><span data-stu-id="721aa-p106">The following command unassigns any per-user conferencing policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="721aa-148">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="721aa-148">For more information, see the help topic for the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="721aa-149">Confira Também</span><span class="sxs-lookup"><span data-stu-id="721aa-149">See Also</span></span>


[<span data-ttu-id="721aa-150">Criar ou modificar uma política de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="721aa-150">Create or modify a conferencing policy in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-conferencing-policy.md)  


[<span data-ttu-id="721aa-151">Atribuindo políticas por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="721aa-151">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

