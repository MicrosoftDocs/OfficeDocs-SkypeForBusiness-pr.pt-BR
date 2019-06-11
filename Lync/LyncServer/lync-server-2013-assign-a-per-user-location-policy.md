---
title: 'Lync Server 2013: atribuir uma política de local por usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user location policy
ms:assetid: 343f2de3-a0ae-4403-8456-6e520b579d32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520974(v=OCS.15)
ms:contentKeyID: 48183794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a387d0f603addea31bd1e3ee6b591e06a26b2c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845035"
---
# <a name="assign-a-per-user-location-policy-in-lync-server-2013"></a><span data-ttu-id="b3c4c-102">Atribuir uma política de localização por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3c4c-102">Assign a per-user location policy in Lync Server 2013</span></span>

 


<span data-ttu-id="b3c4c-103">A política de localização é uma das configurações individuais de uma conta de usuário que você pode configurar no painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b3c4c-103">The location policy is one of the individual settings of a user account that you can configure in the Lync Server Control Panel.</span></span>

<span data-ttu-id="b3c4c-104">Implantar uma ou mais políticas de localização por usuário é opcional.</span><span class="sxs-lookup"><span data-stu-id="b3c4c-104">Deploying one or more per-user location policies is optional.</span></span> <span data-ttu-id="b3c4c-105">Você também pode implantar apenas uma política de localização de nível global ou uma política de localização em nível de sub-rede.</span><span class="sxs-lookup"><span data-stu-id="b3c4c-105">You can also deploy only a global-level location policy or subnet-level location policy.</span></span> <span data-ttu-id="b3c4c-106">Se você implantar políticas por usuário, deverá atribui-las explicitamente aos usuários, grupos ou objeto de contato.</span><span class="sxs-lookup"><span data-stu-id="b3c4c-106">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="b3c4c-107">As configurações avançadas do 9-1-1 (E9-1-1) são automaticamente padrão para as definidas na política de localização de nível global quando nenhuma política específica de nível de sub-rede ou por usuário é atribuída.</span><span class="sxs-lookup"><span data-stu-id="b3c4c-107">Enhanced 9-1-1 (E9-1-1) settings automatically default to those defined in the global-level location policy when no specific subnet-level or per-user policy is assigned.</span></span>

<span data-ttu-id="b3c4c-108">Depois de criar pelo menos uma política de localização por usuário, use os procedimentos deste tópico para atribuir à política que especifica as configurações que você deseja que o servidor aplique para as chamadas de emergência feitas por um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="b3c4c-108">After creating at least one per-user location policy, use the procedures in this topic to assign to the policy that specifies the settings that you want the server to apply for emergency calls placed by a particular user.</span></span>

<span data-ttu-id="b3c4c-109">Para obter uma lista de todas as configurações de política de localização disponíveis, consulte [definindo a política de localização do Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="b3c4c-109">For a list of all available location policy settings, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span>

<span data-ttu-id="b3c4c-110">Para obter detalhes sobre como criar políticas de localização, consulte [criar políticas de localização no Lync Server 2013](lync-server-2013-create-location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b3c4c-110">For details about creating location policies, see [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md).</span></span>

## <a name="to-assign-a-per-user-location-policy-with-the-lync-server-control-panel"></a><span data-ttu-id="b3c4c-111">Para atribuir uma política de local por usuário com o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="b3c4c-111">To assign a per-user location policy with the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b3c4c-112">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="b3c4c-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b3c4c-113">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b3c4c-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b3c4c-114">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b3c4c-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b3c4c-115">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="b3c4c-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="b3c4c-116">Use um dos seguintes métodos para localizar um usuário:</span><span class="sxs-lookup"><span data-stu-id="b3c4c-116">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="b3c4c-117">Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="b3c4c-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="b3c4c-118">Se você salvou uma consulta, clique no ícone **Abrir consulta**, use a caixa de diálogo **Abrir** para recuperar a consulta (um arquivo .usf) e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="b3c4c-118">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="b3c4c-119">(Opcional) Especifique o critério de pesquisa adicional para reduzir os resultados:</span><span class="sxs-lookup"><span data-stu-id="b3c4c-119">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="b3c4c-120">Clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="b3c4c-120">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="b3c4c-121">Insira a propriedade do usuário digitando ou clicando na seta da lista suspensa para selecionar a propriedade.</span><span class="sxs-lookup"><span data-stu-id="b3c4c-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="b3c4c-122">Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).</span><span class="sxs-lookup"><span data-stu-id="b3c4c-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="b3c4c-123">Dependendo da propriedade do usuário selecionada, insira o critério que deseja usar para filtrar os resultados de pesquisa digitando ou clicando na seta da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="b3c4c-123">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="b3c4c-124">Para adicionar cláusulas de pesquisa adicionais à sua consulta, clique em <STRONG>Adicionar filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b3c4c-124">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="b3c4c-125">Clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="b3c4c-125">Click **Find**.</span></span>

6.  <span data-ttu-id="b3c4c-126">Clique em um usuário nos resultados da pesquisa, clique em **Ação** e em seguida, clique em **Atribuir políticas**.</span><span class="sxs-lookup"><span data-stu-id="b3c4c-126">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="b3c4c-127">Se você quiser que a mesma política de localização por usuário seja aplicada a vários usuários, selecione vários usuários nos resultados da pesquisa, clique em <STRONG>ações</STRONG>e, em seguida, clique em <STRONG>atribuir políticas</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b3c4c-127">If you want the same per-user location policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="b3c4c-128">Em **atribuir políticas**, em **política de localização**, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="b3c4c-128">In **Assign Policies**, under **Location policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="b3c4c-129">Como há várias diretivas que você pode configurar usando a caixa de diálogo <STRONG>atribuir políticas</STRONG> , <STRONG> &lt;manter como está&gt; </STRONG> selecionado por padrão para cada política na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b3c4c-129">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="b3c4c-130">Continue usando a política atribuída anteriormente ao usuário não realizando alterações nesta configuração.</span><span class="sxs-lookup"><span data-stu-id="b3c4c-130">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="b3c4c-131">Permitir que o Lync Server 2013 escolha automaticamente a política de nível global ou, se definida, a política de nível de sub-rede.</span><span class="sxs-lookup"><span data-stu-id="b3c4c-131">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the subnet-level policy.</span></span>
    
      - <span data-ttu-id="b3c4c-132">Clique no nome de uma política de local por usuário que você definiu anteriormente executando o cmdlet **New-CsLocationPolicy** .</span><span class="sxs-lookup"><span data-stu-id="b3c4c-132">Click the name of a per-user location policy you previously defined by running the **New-CsLocationPolicy** cmdlet.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="b3c4c-133">Para ajudá-lo a decidir a política que você deseja atribuir, depois de clicar no nome da política, clique em <STRONG>Exibir</STRONG> para ver os direitos do usuário e as permissões definidas na política.</span><span class="sxs-lookup"><span data-stu-id="b3c4c-133">To help you decide the policy that you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="b3c4c-134">Ao concluir, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3c4c-134">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-location-policy-by-using-lync-server-management-shell-cmdlets"></a><span data-ttu-id="b3c4c-135">Atribuir uma política de local por usuário usando cmdlets do Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="b3c4c-135">Assigning a Per-User Location Policy by Using Lync Server Management Shell Cmdlets</span></span>

<span data-ttu-id="b3c4c-136">Você pode atribuir políticas de localização por usuário usando o cmdlet Grant-CsLocationPolicy.</span><span class="sxs-lookup"><span data-stu-id="b3c4c-136">You can assign per-user location policies by using the Grant-CsLocationPolicy cmdlet.</span></span> <span data-ttu-id="b3c4c-137">Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b3c4c-137">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b3c4c-138">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="b3c4c-138">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-location-policy-to-a-single-user"></a><span data-ttu-id="b3c4c-139">Para atribuir uma política de localização por usuário a um único usuário</span><span class="sxs-lookup"><span data-stu-id="b3c4c-139">To assign a per-user location policy to a single user</span></span>

  - <span data-ttu-id="b3c4c-140">O comando a seguir atribui a RedmondLocationPolicy de política de localização por usuário ao usuário Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="b3c4c-140">The following command assigns the per-user location policy RedmondLocationPolicy to the user Ken Myer.</span></span>
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName "RedmondLocationPolicy"

## <a name="to-assign-a-per-user-location-policy-to-multiple-users"></a><span data-ttu-id="b3c4c-141">Para atribuir uma política de local por usuário a vários usuários</span><span class="sxs-lookup"><span data-stu-id="b3c4c-141">To assign a per-user location policy to multiple users</span></span>

  - <span data-ttu-id="b3c4c-142">Esse comando atribui a política de localização por usuário AccountingDepartmentLocationPolicy a todos os usuários que trabalham para o departamento de contabilidade.</span><span class="sxs-lookup"><span data-stu-id="b3c4c-142">This command assigns the per-user location policy AccountingDepartmentLocationPolicy to all the users who work for the Accounting department.</span></span> <span data-ttu-id="b3c4c-143">Para obter mais informações sobre o parâmetro LdapFilter usado neste comando, consulte a documentação do cmdlet [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="b3c4c-143">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=Accounting" | Grant-CsLocationPolicy -PolicyName "AccountingDepartmentLocationPolicy"

## <a name="to-unassign-a-per-user-location-policy"></a><span data-ttu-id="b3c4c-144">Para cancelar a atribuição de uma política de local por usuário</span><span class="sxs-lookup"><span data-stu-id="b3c4c-144">To unassign a per-user location policy</span></span>

  - <span data-ttu-id="b3c4c-145">O comando a seguir não atribui atribuições de política de local por usuário anteriormente atribuídas a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="b3c4c-145">The following command unassigns any per-user location policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="b3c4c-146">Após a política por usuário ser retirada, Ken irá automaticamente ser gerenciado usando a política global ou, se existir, sua política de site local.</span><span class="sxs-lookup"><span data-stu-id="b3c4c-146">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="b3c4c-147">Uma política de site tem precedência sobre a política global.</span><span class="sxs-lookup"><span data-stu-id="b3c4c-147">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="b3c4c-148">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Grant-CsLocationPolicy](https://technet.microsoft.com/en-us/library/gg413049\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="b3c4c-148">For more information, see the help topic for the [Grant-CsLocationPolicy](https://technet.microsoft.com/en-us/library/gg413049\(v=ocs.15\)) cmdlet.</span></span>

