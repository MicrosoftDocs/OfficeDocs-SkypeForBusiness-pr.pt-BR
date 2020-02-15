---
title: 'Lync Server 2013: atribuir uma política de local por usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user location policy
ms:assetid: 343f2de3-a0ae-4403-8456-6e520b579d32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520974(v=OCS.15)
ms:contentKeyID: 48183794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ec78fd434706ec3e1c5f28c256b38a5f4463ac7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044023"
---
# <a name="assign-a-per-user-location-policy-in-lync-server-2013"></a><span data-ttu-id="8635f-102">Atribuir uma política de local por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8635f-102">Assign a per-user location policy in Lync Server 2013</span></span>

 


<span data-ttu-id="8635f-103">A política de local é uma das configurações individuais de uma conta de usuário que você pode configurar no painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8635f-103">The location policy is one of the individual settings of a user account that you can configure in the Lync Server Control Panel.</span></span>

<span data-ttu-id="8635f-p101">Implantar uma ou mais políticas de local por usuário é opcional. Você também pode implantar somente uma política local nos níveis global ou de sub-rede. Se você implantar políticas por usuário, deverá atribui-las explicitamente a usuários, grupos ou objetos de contato. As configurações aprimoradas do 9-1-1 (E9-1-1) usam por padrão automaticamente as definidas na política de local de nível global, quando nenhuma política específica no nível da sub-rede ou por usuário é atribuída.</span><span class="sxs-lookup"><span data-stu-id="8635f-p101">Deploying one or more per-user location policies is optional. You can also deploy only a global-level location policy or subnet-level location policy. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object. Enhanced 9-1-1 (E9-1-1) settings automatically default to those defined in the global-level location policy when no specific subnet-level or per-user policy is assigned.</span></span>

<span data-ttu-id="8635f-108">Depois de criar pelo menos uma política de local por usuário, use os procedimentos deste tópico para atribuir à política que determina as configurações que o servidor deverá aplicar às chamadas de emergência feitas por um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="8635f-108">After creating at least one per-user location policy, use the procedures in this topic to assign to the policy that specifies the settings that you want the server to apply for emergency calls placed by a particular user.</span></span>

<span data-ttu-id="8635f-109">Para obter uma lista de todas as configurações de política de local disponíveis, consulte [definindo a política de local para o Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="8635f-109">For a list of all available location policy settings, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span>

<span data-ttu-id="8635f-110">Para obter detalhes sobre como criar políticas de local, consulte [Create Location Policies in Lync Server 2013](lync-server-2013-create-location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8635f-110">For details about creating location policies, see [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md).</span></span>

## <a name="to-assign-a-per-user-location-policy-with-the-lync-server-control-panel"></a><span data-ttu-id="8635f-111">Para atribuir uma política de local por usuário com o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="8635f-111">To assign a per-user location policy with the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="8635f-112">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="8635f-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8635f-113">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8635f-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8635f-114">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8635f-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8635f-115">Na barra de navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="8635f-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="8635f-116">Utilize um dos métodos a seguir para localizar um usuário:</span><span class="sxs-lookup"><span data-stu-id="8635f-116">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="8635f-117">Na caixa **Buscar usuários**, digite toda ou a primeira parte do nome de exibição, nome, sobrenome, nome da conta do Gerenciador de Contas de Segurança (SAM), endereço SIP ou linha do Uniform Resource Identifier (URI) da conta de usuário, e então clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="8635f-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="8635f-118">Se você tiver uma consulta salva, clique no ícone **Abrir consulta**, utilize a caixa de diálogo **Abrir**  para obter a consulta (um arquivo .usf) e, então, clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="8635f-118">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="8635f-119">(Opcional) Especifique critérios de busca adicionais para limitar os resultados:</span><span class="sxs-lookup"><span data-stu-id="8635f-119">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="8635f-120">Clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="8635f-120">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="8635f-121">Insira a propriedade de usuário digitando ou clicando na seta na lista suspensa para selecionar a propriedade.</span><span class="sxs-lookup"><span data-stu-id="8635f-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="8635f-122">Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).</span><span class="sxs-lookup"><span data-stu-id="8635f-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="8635f-123">Dependendo da propriedade do usuário selecionada, insira os critérios que você deseja usar para filtrar os resultados pesquisa, digitando-os ou clicando na seta na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="8635f-123">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="8635f-124">Para adicionar cláusulas de pesquisa à sua consulta, clique em <STRONG>Adicionar filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="8635f-124">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="8635f-125">Clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="8635f-125">Click **Find**.</span></span>

6.  <span data-ttu-id="8635f-126">Clique em um usuário nos resultados da pesquisa, clique em **Ação** e em **Atribuir políticas**.</span><span class="sxs-lookup"><span data-stu-id="8635f-126">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="8635f-127">Se você deseja aplicar a mesma política de local para usuários múltiplos, selecione os usuários nos resultados da pesquisa e clique em <STRONG>Ações</STRONG> e em <STRONG>Atribuir políticas</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="8635f-127">If you want the same per-user location policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="8635f-128">Em **Atribuir políticas**, em **Política de local**, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="8635f-128">In **Assign Policies**, under **Location policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="8635f-129">Como há várias políticas que você pode configurar usando a caixa de diálogo <STRONG>atribuir políticas</STRONG> , <STRONG> &lt;manter como está&gt; </STRONG> selecionada por padrão para todas as políticas da caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="8635f-129">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="8635f-130">Para continuar usando a política previamente atribuída ao usuário, basta não fazer nenhuma alteração nessa configuração.</span><span class="sxs-lookup"><span data-stu-id="8635f-130">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="8635f-131">Permitir que o Lync Server 2013 escolha automaticamente a política de nível global ou, se definida, a política de nível de sub-rede.</span><span class="sxs-lookup"><span data-stu-id="8635f-131">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the subnet-level policy.</span></span>
    
      - <span data-ttu-id="8635f-132">Clique no nome de uma política de local por usuário que você definiu previamente, executando o cmdlet **New-CsLocationPolicy**.</span><span class="sxs-lookup"><span data-stu-id="8635f-132">Click the name of a per-user location policy you previously defined by running the **New-CsLocationPolicy** cmdlet.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="8635f-133">Para ajudar a decidir qual política você deseja atribuir, depois de clicar no nome da política, clique em <STRONG>Exibir</STRONG> para ver os direitos de usuário e as permissões definidas.</span><span class="sxs-lookup"><span data-stu-id="8635f-133">To help you decide the policy that you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="8635f-134">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8635f-134">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-location-policy-by-using-lync-server-management-shell-cmdlets"></a><span data-ttu-id="8635f-135">Atribuindo uma política de local por usuário usando cmdlets do Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="8635f-135">Assigning a Per-User Location Policy by Using Lync Server Management Shell Cmdlets</span></span>

<span data-ttu-id="8635f-136">Você pode atribuir políticas de local por usuário usando o cmdlet Grant-CsLocationPolicy.</span><span class="sxs-lookup"><span data-stu-id="8635f-136">You can assign per-user location policies by using the Grant-CsLocationPolicy cmdlet.</span></span> <span data-ttu-id="8635f-137">Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8635f-137">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8635f-138">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="8635f-138">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-location-policy-to-a-single-user"></a><span data-ttu-id="8635f-139">Para atribuir um política de local por usuário a um único usuário</span><span class="sxs-lookup"><span data-stu-id="8635f-139">To assign a per-user location policy to a single user</span></span>

  - <span data-ttu-id="8635f-140">O comando a seguir atribui a política de local por usuário RedmondLocationPolicy ao usuário Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="8635f-140">The following command assigns the per-user location policy RedmondLocationPolicy to the user Ken Myer.</span></span>
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName "RedmondLocationPolicy"

## <a name="to-assign-a-per-user-location-policy-to-multiple-users"></a><span data-ttu-id="8635f-141">Para atribuir uma política de local por usuário a vários usuários</span><span class="sxs-lookup"><span data-stu-id="8635f-141">To assign a per-user location policy to multiple users</span></span>

  - <span data-ttu-id="8635f-142">Este comando atribui a política de local por usuário AccountingDepartmentLocationPolicy a todos os usuários que trabalham no departamento contábil.</span><span class="sxs-lookup"><span data-stu-id="8635f-142">This command assigns the per-user location policy AccountingDepartmentLocationPolicy to all the users who work for the Accounting department.</span></span> <span data-ttu-id="8635f-143">Para obter mais informações sobre o parâmetro LdapFilter usado neste comando, consulte a documentação do cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="8635f-143">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=Accounting" | Grant-CsLocationPolicy -PolicyName "AccountingDepartmentLocationPolicy"

## <a name="to-unassign-a-per-user-location-policy"></a><span data-ttu-id="8635f-144">Para desfazer a atribuição de uma política de local por usuário</span><span class="sxs-lookup"><span data-stu-id="8635f-144">To unassign a per-user location policy</span></span>

  - <span data-ttu-id="8635f-p106">O comando a seguir desfaz a atribuição de qualquer política de local por usuário atribuída a Ken Myer. Depois que a atribuição da política for desfeita, Ken Myer será automaticamente gerenciado usando a política global ou, se houver, sua política de site local. Uma política de site tem preferência sobre a política global.</span><span class="sxs-lookup"><span data-stu-id="8635f-p106">The following command unassigns any per-user location policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="8635f-148">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Grant-CsLocationPolicy](https://technet.microsoft.com/library/gg413049\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="8635f-148">For more information, see the help topic for the [Grant-CsLocationPolicy](https://technet.microsoft.com/library/gg413049\(v=ocs.15\)) cmdlet.</span></span>

