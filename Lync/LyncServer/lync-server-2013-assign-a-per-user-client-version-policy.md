---
title: 'Lync Server 2013: atribuir uma política de versão de cliente por usuário'
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
ms.openlocfilehash: e509427b6d2651f84b96a96c87fbe7cfd6177a7d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738371"
---
# <a name="assign-a-per-user-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="29e22-102">Atribuir uma política de versão de cliente por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29e22-102">Assign a per-user client version policy in Lync Server 2013</span></span>

 


<span data-ttu-id="29e22-103">A política de versão do cliente é uma das configurações individuais de uma conta de usuário que você pode configurar no painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="29e22-103">The client version policy is one of the individual settings of a user account that you can configure in the Lync Server Control Panel.</span></span>

<span data-ttu-id="29e22-104">A implantação de uma ou mais políticas de versão de cliente por usuário é opcional.</span><span class="sxs-lookup"><span data-stu-id="29e22-104">Deploying one or more per-user client version policies is optional.</span></span> <span data-ttu-id="29e22-105">Você também pode implantar apenas uma política de versão do cliente global ou nível do site ou políticas de versão do cliente no nível do grupo.</span><span class="sxs-lookup"><span data-stu-id="29e22-105">You can also deploy only a global-level client version policy, or site-level or pool-level client version policies.</span></span> <span data-ttu-id="29e22-106">Se você implantar políticas por usuário, deverá atribui-las explicitamente aos usuários, grupos ou objeto de contato.</span><span class="sxs-lookup"><span data-stu-id="29e22-106">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="29e22-107">Quando nenhuma política específica de nível de site, de nível de grupo ou por usuário é atribuída, os clientes padrão que têm permissão para se registrar no Lync Server 2013 são aqueles definidos na política de versão do cliente global.</span><span class="sxs-lookup"><span data-stu-id="29e22-107">When no specific site-level, pool-level, or per-user policy is assigned, the default clients that are allowed to register with Lync Server 2013 are those defined in the global-level client version policy.</span></span>

<span data-ttu-id="29e22-108">Depois de criar pelo menos uma política de versão de cliente por usuário, use os procedimentos neste tópico para atribuir a política que especifica as versões de cliente que você deseja permitir para se registrar no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="29e22-108">After creating at least one per-user client version policy, use the procedures in this topic to assign the policy that specifies the client versions that you want to allow to register with Lync Server.</span></span>

<span data-ttu-id="29e22-109">Para obter detalhes sobre como criar políticas de versão de cliente por usuário, consulte [especificando os aplicativos cliente que podem ser usados para fazer logon no Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="29e22-109">For details about creating per-user client version policies, see [Specifying the client applications that can be used to log on to Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).</span></span>

## <a name="to-assign-a-per-user-client-version-policy"></a><span data-ttu-id="29e22-110">Para atribuir uma política de versão de cliente por usuário</span><span class="sxs-lookup"><span data-stu-id="29e22-110">To assign a per-user client version policy</span></span>

1.  <span data-ttu-id="29e22-111">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="29e22-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="29e22-112">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="29e22-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="29e22-113">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="29e22-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="29e22-114">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="29e22-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="29e22-115">Use um dos seguintes métodos para localizar um usuário:</span><span class="sxs-lookup"><span data-stu-id="29e22-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="29e22-116">Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="29e22-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="29e22-117">Se você salvou uma consulta, clique no ícone **Abrir consulta**, use a caixa de diálogo **Abrir** para recuperar a consulta (um arquivo .usf) e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="29e22-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="29e22-118">(Opcional) Especifique o critério de pesquisa adicional para reduzir os resultados:</span><span class="sxs-lookup"><span data-stu-id="29e22-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="29e22-119">Clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="29e22-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="29e22-120">Insira a propriedade do usuário digitando ou clicando na seta da lista suspensa para selecionar a propriedade.</span><span class="sxs-lookup"><span data-stu-id="29e22-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="29e22-121">Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).</span><span class="sxs-lookup"><span data-stu-id="29e22-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="29e22-122">Dependendo da propriedade do usuário selecionada, insira o critério que deseja usar para filtrar os resultados de pesquisa digitando ou clicando na seta da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="29e22-122">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="29e22-123">Para adicionar cláusulas de pesquisa adicionais à sua consulta, clique em <STRONG>Adicionar filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="29e22-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="29e22-124">Clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="29e22-124">Click **Find**.</span></span>

6.  <span data-ttu-id="29e22-125">Clique em um usuário nos resultados da pesquisa, clique em **Ação** e em seguida, clique em **Atribuir políticas**.</span><span class="sxs-lookup"><span data-stu-id="29e22-125">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="29e22-126">Se quiser que a mesma política de versão de cliente por usuário seja aplicada a vários usuários, selecione vários usuários nos resultados da pesquisa, clique em <STRONG>ações</STRONG>e em <STRONG>atribuir políticas</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="29e22-126">If you want the same per-user client version policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="29e22-127">Em **atribuir políticas**, em **política de versão do cliente**, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="29e22-127">In **Assign Policies**, under **Client version policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="29e22-128">Como há várias diretivas que você pode configurar usando a caixa de diálogo <STRONG>atribuir políticas</STRONG> , <STRONG> &lt;manter como está&gt; </STRONG> selecionado por padrão para cada política na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="29e22-128">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="29e22-129">Continue usando a política atribuída anteriormente ao usuário não realizando alterações nesta configuração.</span><span class="sxs-lookup"><span data-stu-id="29e22-129">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="29e22-130">Permitir que o Lync Server escolha automaticamente a política de nível global ou, se definida, a política de nível de site ou política de nível de pool.</span><span class="sxs-lookup"><span data-stu-id="29e22-130">Allow Lync Server to automatically choose either the global-level policy or, if defined, the site-level policy or pool-level policy.</span></span>
    
      - <span data-ttu-id="29e22-131">Clique no nome de uma política de versão de cliente por usuário definida anteriormente na página de **política de versão do cliente** .</span><span class="sxs-lookup"><span data-stu-id="29e22-131">Click the name of a per-user client version policy you previously defined on the **Client Version Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="29e22-132">Para ajudar a decidir a política que deseja atribuir, após clicar no nome da política, clique em <STRONG>Exibir</STRONG> para visualizar os direitos e permissões do usuário definidos na política.</span><span class="sxs-lookup"><span data-stu-id="29e22-132">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="29e22-133">Ao concluir, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="29e22-133">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-client-version-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="29e22-134">Atribuir uma política de versão de cliente por usuário usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="29e22-134">Assigning a Per-User Client Version Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="29e22-135">Você pode atribuir políticas de versão de cliente por usuário usando o cmdlet Grant-CsClientVersionPolicy.</span><span class="sxs-lookup"><span data-stu-id="29e22-135">You can assign per-user client version policies by using the Grant-CsClientVersionPolicy cmdlet.</span></span> <span data-ttu-id="29e22-136">Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29e22-136">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="29e22-137">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="29e22-137">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-client-version-policy-to-a-single-user"></a><span data-ttu-id="29e22-138">Para atribuir uma política de versão de cliente por usuário a um único usuário</span><span class="sxs-lookup"><span data-stu-id="29e22-138">To assign a per-user client version policy to a single user</span></span>

  - <span data-ttu-id="29e22-139">O comando a seguir atribui a política de versão do cliente por usuário RedmondClientVersionPolicy ao usuário Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="29e22-139">The following command assigns the per-user client version policy RedmondClientVersionPolicy to the user Ken Myer.</span></span>
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName "RedmondClientVersionPolicy"

## <a name="to-assign-a-per-user-client-version-policy-to-multiple-users"></a><span data-ttu-id="29e22-140">Para atribuir uma política de versão de cliente por usuário a vários usuários</span><span class="sxs-lookup"><span data-stu-id="29e22-140">To assign a per-user client version policy to multiple users</span></span>

  - <span data-ttu-id="29e22-141">Esse comando atribui a política de política de cliente por usuário RedmondClientVersionPolicy a todos os usuários que atualmente recebem a política de voz RedmondVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="29e22-141">This command assigns the per-user client version policy RedmondClientVersionPolicy to all the users who are currently assigned the voice policy RedmondVoicePolicy.</span></span> <span data-ttu-id="29e22-142">Para obter mais informações sobre o parâmetro Filter usado neste comando, consulte a documentação do cmdlet [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="29e22-142">For more information on the Filter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -Filter {VoicePolicy -eq "RedmondVoicePolicy"} | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## <a name="to-unassign-a-per-user-client-version-policy"></a><span data-ttu-id="29e22-143">Para cancelar a atribuição de uma política de versão de cliente por usuário</span><span class="sxs-lookup"><span data-stu-id="29e22-143">To unassign a per-user client version policy</span></span>

  - <span data-ttu-id="29e22-144">O comando a seguir cancela a atribuição de qualquer política de versão de cliente por usuário atribuída anteriormente a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="29e22-144">The following command unassigns any per-user client version policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="29e22-145">Após a atribuição da política por usuário, Ken Myer será automaticamente gerenciado usando a política global, sua política de site local (se houver) ou a política de escopo de serviço atribuída ao registrador.</span><span class="sxs-lookup"><span data-stu-id="29e22-145">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy, his local site policy (if one exists), or the service-scope policy assigned to his Registrar.</span></span> <span data-ttu-id="29e22-146">Uma política de escopo de serviço tem precedência sobre qualquer política de site e uma política de site tem precedência sobre a política global.</span><span class="sxs-lookup"><span data-stu-id="29e22-146">A service scope policy takes precedence over any site policy, and a site policy takes precedence over the global policy.</span></span>
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="29e22-147">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Grant-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/gg412903\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="29e22-147">For more information, see the help topic for the [Grant-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/gg412903\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="29e22-148">Confira também</span><span class="sxs-lookup"><span data-stu-id="29e22-148">See Also</span></span>


[<span data-ttu-id="29e22-149">Como atribuir políticas por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29e22-149">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)  
[<span data-ttu-id="29e22-150">Gerenciando dispositivos, telefones e aplicativos do cliente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29e22-150">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)

