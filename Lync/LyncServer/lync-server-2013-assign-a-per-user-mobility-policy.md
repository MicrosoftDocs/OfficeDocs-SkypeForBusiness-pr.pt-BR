---
title: 'Lync Server 2013: atribuir uma política de mobilidade por usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user mobility policy
ms:assetid: d8bf997f-4bc7-48d3-973b-323505f55e9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721902(v=OCS.15)
ms:contentKeyID: 49733836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b9a5a1bf5132fb78086fdd424714e03af2caab5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134417"
---
# <a name="assign-a-per-user-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="23122-102">Atribuir uma política de mobilidade por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23122-102">Assign a per-user mobility policy in Lync Server 2013</span></span>

 


<span data-ttu-id="23122-103">A política de mobilidade é uma das configurações individuais de uma conta de usuário que você pode configurar no painel de controle do Lync Server ou no Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="23122-103">The mobility policy is one of the individual settings of a user account that you can configure in Lync Server Control Panel or Lync Server Management Shell.</span></span>

## <a name="to-assign-a-per-user-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="23122-104">Para atribuir uma política de mobilidade por usuário com o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="23122-104">To assign a per-user mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="23122-105">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="23122-105">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="23122-106">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="23122-106">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="23122-107">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="23122-107">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="23122-108">Na barra de navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="23122-108">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="23122-109">Utilize um dos métodos a seguir para localizar um usuário:</span><span class="sxs-lookup"><span data-stu-id="23122-109">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="23122-110">Na caixa **Buscar usuários**, digite toda ou a primeira parte do nome de exibição, nome, sobrenome, nome da conta do Gerenciador de Contas de Segurança (SAM), endereço SIP ou linha do Uniform Resource Identifier (URI) da conta de usuário, e então clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="23122-110">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="23122-111">Se você tiver uma consulta salva, clique no ícone **Abrir consulta**, utilize a caixa de diálogo **Abrir**  para obter a consulta (um arquivo .usf) e, então, clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="23122-111">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="23122-112">(Opcional) Especifique critérios de busca adicionais para limitar os resultados:</span><span class="sxs-lookup"><span data-stu-id="23122-112">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="23122-113">Clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="23122-113">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="23122-114">Insira a propriedade de usuário digitando ou clicando na seta na lista suspensa para selecionar a propriedade.</span><span class="sxs-lookup"><span data-stu-id="23122-114">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="23122-115">Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).</span><span class="sxs-lookup"><span data-stu-id="23122-115">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="23122-116">Dependendo da propriedade do usuário selecionada, insira os critérios que você deseja usar para filtrar os resultados pesquisa, digitando-os ou clicando na seta na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="23122-116">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="23122-117">Para adicionar cláusulas de pesquisa à sua consulta, clique em <STRONG>Adicionar filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="23122-117">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="23122-118">Clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="23122-118">Click **Find**.</span></span>

6.  <span data-ttu-id="23122-119">Clique em um usuário nos resultados da pesquisa, clique em **Ação** e em **Atribuir políticas**.</span><span class="sxs-lookup"><span data-stu-id="23122-119">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="23122-120">Se você deseja aplicar a mesma política de mobilidade para usuários múltiplos, selecione os usuários nos resultados da pesquisa e clique em <STRONG>Ações</STRONG> e em <STRONG>Atribuir políticas</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="23122-120">If you want the same per-user mobility policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="23122-121">Em **Atribuir políticas**, em **Política de mobilidade**, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="23122-121">In **Assign Policies**, under **Mobility policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="23122-122">Como há várias políticas que você pode configurar em <STRONG>atribuir políticas</STRONG>, <STRONG> &lt;manter como está&gt; </STRONG> selecionada por padrão para todas as políticas da caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="23122-122">Because there are multiple policies that you can configure in <STRONG>Assign Policies</STRONG>, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="23122-123">Para continuar usando a política previamente atribuída ao usuário, basta não fazer nenhuma alteração nessa configuração.</span><span class="sxs-lookup"><span data-stu-id="23122-123">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="23122-124">Selecione \*\* \<automático\> \*\* para permitir que o Lync Server 2013 escolha automaticamente a política de nível global ou, se definida, a política de nível de site.</span><span class="sxs-lookup"><span data-stu-id="23122-124">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="23122-125">Clique no nome de uma política de mobilidade por usuário definida anteriormente na página **Política de mobilidade**.</span><span class="sxs-lookup"><span data-stu-id="23122-125">Click the name of a per-user mobility policy you previously defined on the **Mobility Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="23122-126">Para ajudar a decidir a política que deseja atribuir, após clicar no nome da política, clique em <STRONG>Exibir</STRONG> para ver os direitos e permissões do usuário definidos na política.</span><span class="sxs-lookup"><span data-stu-id="23122-126">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="23122-127">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="23122-127">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-mobility-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="23122-128">Atribuindo uma política de mobilidade por usuário usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="23122-128">Assigning a Per-User Mobility Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="23122-129">Você pode atribuir políticas de mobilidade por usuário usando o Windows PowerShell e o cmdlet **Grant-CsMobilityPolicy** .</span><span class="sxs-lookup"><span data-stu-id="23122-129">You can assign per-user mobility policies by using Windows PowerShell and the **Grant-CsMobilityPolicy** cmdlet.</span></span> <span data-ttu-id="23122-130">Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23122-130">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="23122-131">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="23122-131">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-mobility-policy-to-a-single-user"></a><span data-ttu-id="23122-132">Para atribuir uma política de mobilidade por usuário a um único usuário</span><span class="sxs-lookup"><span data-stu-id="23122-132">To assign a per-user mobility policy to a single user</span></span>

  - <span data-ttu-id="23122-133">O seguinte comando atribui a política de mobilidade por usuário RedmondMobilityPolicy ao usuário Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="23122-133">The following command assigns the per-user mobility policy RedmondMobilityPolicy to the user Ken Myer.</span></span>
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName "RedmondMobilityPolicy"

## <a name="to-assign-a-per-user-mobility-policy-to-multiple-users"></a><span data-ttu-id="23122-134">Para atribuir uma política de mobilidade por usuário a vários usuários</span><span class="sxs-lookup"><span data-stu-id="23122-134">To assign a per-user mobility policy to multiple users</span></span>

  - <span data-ttu-id="23122-135">O seguinte comando atribui a política de mobilidade por usuário RedmondMobilityPolicy para todos os usuários atualmente atribuídos com a política NorthAmericaMobilityPolicy.</span><span class="sxs-lookup"><span data-stu-id="23122-135">The following command assigns the per-user mobility policy RedmondMobilityPolicy to all the users who are currently assigned the policy NorthAmericaMobilityPolicy.</span></span> <span data-ttu-id="23122-136">Para obter detalhes sobre o parâmetro Filter usado nesse comando, consulte [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="23122-136">For details about the Filter parameter used in this command, see [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)).</span></span>
    
        Get-CsUser -Filter {MobilityPolicy -eq "NorthAmericaMobilityPolicy"} | Grant-CsMobilityPolicy -PolicyName "RedmondMobilityPolicy"

## <a name="to-unassign-a-per-user-mobility-policy"></a><span data-ttu-id="23122-137">Para retirar a atribuição de uma política de mobilidade por usuário</span><span class="sxs-lookup"><span data-stu-id="23122-137">To unassign a per-user mobility policy</span></span>

  - <span data-ttu-id="23122-p105">O seguinte comando retira a atribuição de qualquer política de mobilidade por usuário atribuída anteriormente a Ken Myer. Após a política por usuário ser retirada, Ken Myer será automaticamente gerenciado utilizando a política global ou, se existir, sua política de site local. Uma política de site tem precedência sobre a política global.</span><span class="sxs-lookup"><span data-stu-id="23122-p105">The following command unassigns any per-user mobility policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="23122-141">Para obter detalhes, consulte [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/hh690038\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="23122-141">For details, see [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/hh690038\(v=ocs.15\)).</span></span>

## <a name="see-also"></a><span data-ttu-id="23122-142">Confira também</span><span class="sxs-lookup"><span data-stu-id="23122-142">See Also</span></span>


[<span data-ttu-id="23122-143">Configurando a política de mobilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23122-143">Configuring mobility policy in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-policy.md)

