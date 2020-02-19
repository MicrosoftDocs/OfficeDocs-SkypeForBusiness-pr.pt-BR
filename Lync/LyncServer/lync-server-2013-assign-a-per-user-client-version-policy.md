---
title: 'Lync Server 2013: atribuir uma política de versão do cliente por usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user client version policy
ms:assetid: f7e8ba2f-62dc-4e7d-8b63-682986f10240
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182607(v=OCS.15)
ms:contentKeyID: 48185868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77b84c4550d44a09e786d09d093e64cbc1901d91
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134457"
---
# <a name="assign-a-per-user-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="42980-102">Atribuir uma política de versão de cliente por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42980-102">Assign a per-user client version policy in Lync Server 2013</span></span>

 


<span data-ttu-id="42980-103">A política de versão do cliente é uma das configurações individuais de uma conta de usuário que você pode configurar no painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="42980-103">The client version policy is one of the individual settings of a user account that you can configure in the Lync Server Control Panel.</span></span>

<span data-ttu-id="42980-104">Implantar uma ou mais políticas de versão do cliente por usuário é opcional.</span><span class="sxs-lookup"><span data-stu-id="42980-104">Deploying one or more per-user client version policies is optional.</span></span> <span data-ttu-id="42980-105">Também é possível implantar apenas uma política de versão do cliente a nível global ou políticas de versão do cliente a nível do pool ou a nível do site.</span><span class="sxs-lookup"><span data-stu-id="42980-105">You can also deploy only a global-level client version policy, or site-level or pool-level client version policies.</span></span> <span data-ttu-id="42980-106">Se você implantar políticas por usuário, deve atribui-las explicitamente aos usuários, grupos ou objeto de contato.</span><span class="sxs-lookup"><span data-stu-id="42980-106">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="42980-107">Quando nenhuma política específica no nível do site, no nível do pool ou por usuário é atribuída, os clientes padrão que têm permissão para se registrar no Lync Server 2013 são aqueles definidos na política de versão do cliente de nível global.</span><span class="sxs-lookup"><span data-stu-id="42980-107">When no specific site-level, pool-level, or per-user policy is assigned, the default clients that are allowed to register with Lync Server 2013 are those defined in the global-level client version policy.</span></span>

<span data-ttu-id="42980-108">Depois de criar pelo menos uma política de versão do cliente por usuário, use os procedimentos neste tópico para atribuir a política que especifica as versões do cliente que você deseja permitir o registro no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="42980-108">After creating at least one per-user client version policy, use the procedures in this topic to assign the policy that specifies the client versions that you want to allow to register with Lync Server.</span></span>

<span data-ttu-id="42980-109">Para obter detalhes sobre como criar políticas de versão do cliente por usuário, consulte [especificando os aplicativos cliente que podem ser usados para fazer logon no Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="42980-109">For details about creating per-user client version policies, see [Specifying the client applications that can be used to log on to Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).</span></span>

## <a name="to-assign-a-per-user-client-version-policy"></a><span data-ttu-id="42980-110">Para atribuir uma política de versão do cliente por usuário</span><span class="sxs-lookup"><span data-stu-id="42980-110">To assign a per-user client version policy</span></span>

1.  <span data-ttu-id="42980-111">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="42980-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="42980-112">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="42980-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="42980-113">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="42980-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="42980-114">Na barra de navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="42980-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="42980-115">Utilize um dos métodos a seguir para localizar um usuário:</span><span class="sxs-lookup"><span data-stu-id="42980-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="42980-116">Na caixa **Buscar usuários**, digite toda ou a primeira parte do nome de exibição, nome, sobrenome, nome da conta do Gerenciador de Contas de Segurança (SAM), endereço SIP ou linha do Uniform Resource Identifier (URI) da conta de usuário, e então clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="42980-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="42980-117">Se você tiver uma consulta salva, clique no ícone **Abrir consulta**, utilize a caixa de diálogo **Abrir**  para obter a consulta (um arquivo .usf) e, então, clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="42980-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="42980-118">(Opcional) Especifique critérios de busca adicionais para limitar os resultados:</span><span class="sxs-lookup"><span data-stu-id="42980-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="42980-119">Clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="42980-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="42980-120">Insira a propriedade de usuário digitando ou clicando na seta na lista suspensa para selecionar a propriedade.</span><span class="sxs-lookup"><span data-stu-id="42980-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="42980-121">Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).</span><span class="sxs-lookup"><span data-stu-id="42980-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="42980-122">Dependendo da propriedade do usuário selecionada, insira os critérios que você deseja usar para filtrar os resultados pesquisa, digitando-os ou clicando na seta na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="42980-122">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="42980-123">Para adicionar cláusulas de pesquisa à sua consulta, clique em <STRONG>Adicionar filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="42980-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="42980-124">Clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="42980-124">Click **Find**.</span></span>

6.  <span data-ttu-id="42980-125">Clique em um usuário nos resultados da pesquisa, clique em **Ação** e em **Atribuir políticas**.</span><span class="sxs-lookup"><span data-stu-id="42980-125">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="42980-126">Se você deseja que a mesma política de versão do cliente por usuário seja aplicada a vários usuários, selecione vários usuários nos resultados da pesquisa, clique em <STRONG>Ações</STRONG> e em <STRONG>Atribuir políticas</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="42980-126">If you want the same per-user client version policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="42980-127">Em **Atribuir políticas**, em **Política de versão do cliente**, faça um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="42980-127">In **Assign Policies**, under **Client version policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="42980-128">Como há várias políticas que você pode configurar usando a caixa de diálogo <STRONG>atribuir políticas</STRONG> , <STRONG> &lt;manter como está&gt; </STRONG> selecionada por padrão para todas as políticas da caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="42980-128">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="42980-129">Para continuar usando a política previamente atribuída ao usuário, basta não fazer nenhuma alteração nessa configuração.</span><span class="sxs-lookup"><span data-stu-id="42980-129">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="42980-130">Permitir que o Lync Server escolha automaticamente a política de nível global ou, se definida, a política de nível de site ou política de nível de pool.</span><span class="sxs-lookup"><span data-stu-id="42980-130">Allow Lync Server to automatically choose either the global-level policy or, if defined, the site-level policy or pool-level policy.</span></span>
    
      - <span data-ttu-id="42980-131">Clique no nome de uma política de versão do cliente por usuário definida anteriormente na página **Política de versão do cliente**.</span><span class="sxs-lookup"><span data-stu-id="42980-131">Click the name of a per-user client version policy you previously defined on the **Client Version Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="42980-132">Para ajudar a decidir a política que deseja atribuir, após clicar no nome da política, clique em <STRONG>Exibir</STRONG> para ver os direitos e permissões do usuário definidos na política.</span><span class="sxs-lookup"><span data-stu-id="42980-132">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="42980-133">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="42980-133">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-client-version-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="42980-134">Atribuindo uma política de versão do cliente por usuário usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="42980-134">Assigning a Per-User Client Version Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="42980-135">Também é possível atribuir políticas de versão do cliente específicas do usuário usando o cmdlet Grant-CsClientVersionPolicy.</span><span class="sxs-lookup"><span data-stu-id="42980-135">You can assign per-user client version policies by using the Grant-CsClientVersionPolicy cmdlet.</span></span> <span data-ttu-id="42980-136">Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="42980-136">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="42980-137">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="42980-137">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-client-version-policy-to-a-single-user"></a><span data-ttu-id="42980-138">Para atribuir uma política de versão do cliente específica do usuário</span><span class="sxs-lookup"><span data-stu-id="42980-138">To assign a per-user client version policy to a single user</span></span>

  - <span data-ttu-id="42980-139">O comando a seguir atribui a política de versão do cliente RedmondClientVersionPolicy ao usuário Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="42980-139">The following command assigns the per-user client version policy RedmondClientVersionPolicy to the user Ken Myer.</span></span>
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName "RedmondClientVersionPolicy"

## <a name="to-assign-a-per-user-client-version-policy-to-multiple-users"></a><span data-ttu-id="42980-140">Para atribuir uma política de versão do cliente específica do usuário a vários usuários</span><span class="sxs-lookup"><span data-stu-id="42980-140">To assign a per-user client version policy to multiple users</span></span>

  - <span data-ttu-id="42980-141">Este comando atribui a política de versão do cliente RedmondClientVersionPolicy a todos os usuários aos quais a política de voz RedmondVoicePolicy tiver sido anteriormente atribuída.</span><span class="sxs-lookup"><span data-stu-id="42980-141">This command assigns the per-user client version policy RedmondClientVersionPolicy to all the users who are currently assigned the voice policy RedmondVoicePolicy.</span></span> <span data-ttu-id="42980-142">Para obter mais informações sobre o parâmetro Filter usado nesse comando, consulte a documentação do cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="42980-142">For more information on the Filter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -Filter {VoicePolicy -eq "RedmondVoicePolicy"} | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## <a name="to-unassign-a-per-user-client-version-policy"></a><span data-ttu-id="42980-143">Para cancelar a atribuição de uma política de versão do cliente específica do usuário</span><span class="sxs-lookup"><span data-stu-id="42980-143">To unassign a per-user client version policy</span></span>

  - <span data-ttu-id="42980-p106">O comando a seguir cancela a atribuição de uma política de versão do cliente específica do usuário atribuída anteriormente a Ken Myer. Após cancelar a atribuição de uma política específica do usuário, o Ken Myer será automaticamente gerenciado usando a política global, sua política do site local (se existir) ou a política de escopo de serviço atribuída ao seu Registrar. Uma política de escopo de serviço tem precedência sobre qualquer política de site e a política de site tem precedência sobre a política global.</span><span class="sxs-lookup"><span data-stu-id="42980-p106">The following command unassigns any per-user client version policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy, his local site policy (if one exists), or the service-scope policy assigned to his Registrar. A service scope policy takes precedence over any site policy, and a site policy takes precedence over the global policy.</span></span>
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="42980-147">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Grant-CsClientVersionPolicy](https://technet.microsoft.com/library/gg412903\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="42980-147">For more information, see the help topic for the [Grant-CsClientVersionPolicy](https://technet.microsoft.com/library/gg412903\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="42980-148">Confira também</span><span class="sxs-lookup"><span data-stu-id="42980-148">See Also</span></span>


[<span data-ttu-id="42980-149">Atribuindo políticas por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42980-149">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)  
[<span data-ttu-id="42980-150">Gerenciando dispositivos, telefones e aplicativos cliente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42980-150">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)

