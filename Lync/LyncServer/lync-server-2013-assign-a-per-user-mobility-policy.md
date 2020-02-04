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
ms.openlocfilehash: 20b5929959e87f4a39c69ab09f7836a471e16b66
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722841"
---
# <a name="assign-a-per-user-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="54703-102">Atribuir uma política de mobilidade por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54703-102">Assign a per-user mobility policy in Lync Server 2013</span></span>

 


<span data-ttu-id="54703-103">A política de mobilidade é uma das configurações individuais de uma conta de usuário que você pode configurar no painel de controle do Lync Server ou no Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="54703-103">The mobility policy is one of the individual settings of a user account that you can configure in Lync Server Control Panel or Lync Server Management Shell.</span></span>

## <a name="to-assign-a-per-user-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="54703-104">Para atribuir uma política de mobilidade por usuário com o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="54703-104">To assign a per-user mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="54703-105">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="54703-105">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="54703-106">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="54703-106">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="54703-107">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="54703-107">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="54703-108">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="54703-108">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="54703-109">Use um dos seguintes métodos para localizar um usuário:</span><span class="sxs-lookup"><span data-stu-id="54703-109">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="54703-110">Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="54703-110">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="54703-111">Se você salvou uma consulta, clique no ícone **Abrir consulta**, use a caixa de diálogo **Abrir** para recuperar a consulta (um arquivo .usf) e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="54703-111">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="54703-112">(Opcional) Especifique o critério de pesquisa adicional para reduzir os resultados:</span><span class="sxs-lookup"><span data-stu-id="54703-112">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="54703-113">Clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="54703-113">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="54703-114">Insira a propriedade do usuário digitando ou clicando na seta da lista suspensa para selecionar a propriedade.</span><span class="sxs-lookup"><span data-stu-id="54703-114">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="54703-115">Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).</span><span class="sxs-lookup"><span data-stu-id="54703-115">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="54703-116">Dependendo da propriedade do usuário selecionada, insira o critério que deseja usar para filtrar os resultados de pesquisa digitando ou clicando na seta da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="54703-116">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="54703-117">Para adicionar cláusulas de pesquisa adicionais à sua consulta, clique em <STRONG>Adicionar filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="54703-117">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="54703-118">Clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="54703-118">Click **Find**.</span></span>

6.  <span data-ttu-id="54703-119">Clique em um usuário nos resultados da pesquisa, clique em **Ação** e em seguida, clique em **Atribuir políticas**.</span><span class="sxs-lookup"><span data-stu-id="54703-119">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="54703-120">Se quiser que a mesma política de mobilidade por usuário seja aplicada a vários usuários, selecione vários usuários nos resultados da pesquisa, clique em <STRONG>ações</STRONG>e, em seguida, clique em <STRONG>atribuir políticas</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="54703-120">If you want the same per-user mobility policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="54703-121">Em **atribuir políticas**, em **política de mobilidade**, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="54703-121">In **Assign Policies**, under **Mobility policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="54703-122">Como há várias políticas que você pode configurar em <STRONG>atribuir políticas</STRONG>, <STRONG> &lt;manter como está&gt; </STRONG> selecionado por padrão para cada política na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="54703-122">Because there are multiple policies that you can configure in <STRONG>Assign Policies</STRONG>, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="54703-123">Continue usando a política atribuída anteriormente ao usuário não realizando alterações nesta configuração.</span><span class="sxs-lookup"><span data-stu-id="54703-123">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="54703-124">Selecione \*\* \<automático\> \*\* para permitir que o Lync Server 2013 escolha automaticamente a política de nível global ou, se definida, a política de nível de site.</span><span class="sxs-lookup"><span data-stu-id="54703-124">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="54703-125">Clique no nome de uma política de mobilidade por usuário definida anteriormente na página da **política de mobilidade** .</span><span class="sxs-lookup"><span data-stu-id="54703-125">Click the name of a per-user mobility policy you previously defined on the **Mobility Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="54703-126">Para ajudar a decidir a política que deseja atribuir, após clicar no nome da política, clique em <STRONG>Exibir</STRONG> para visualizar os direitos e permissões do usuário definidos na política.</span><span class="sxs-lookup"><span data-stu-id="54703-126">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="54703-127">Ao concluir, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="54703-127">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-mobility-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="54703-128">Atribuir uma política de mobilidade por usuário usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="54703-128">Assigning a Per-User Mobility Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="54703-129">Você pode atribuir políticas de mobilidade por usuário usando o Windows PowerShell e o cmdlet **Grant-CsMobilityPolicy** .</span><span class="sxs-lookup"><span data-stu-id="54703-129">You can assign per-user mobility policies by using Windows PowerShell and the **Grant-CsMobilityPolicy** cmdlet.</span></span> <span data-ttu-id="54703-130">Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="54703-130">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="54703-131">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="54703-131">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-mobility-policy-to-a-single-user"></a><span data-ttu-id="54703-132">Para atribuir uma política de mobilidade por usuário a um único usuário</span><span class="sxs-lookup"><span data-stu-id="54703-132">To assign a per-user mobility policy to a single user</span></span>

  - <span data-ttu-id="54703-133">O comando a seguir atribui a RedmondMobilityPolicy de política de mobilidade por usuário ao usuário Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="54703-133">The following command assigns the per-user mobility policy RedmondMobilityPolicy to the user Ken Myer.</span></span>
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName "RedmondMobilityPolicy"

## <a name="to-assign-a-per-user-mobility-policy-to-multiple-users"></a><span data-ttu-id="54703-134">Para atribuir uma política de mobilidade por usuário a vários usuários</span><span class="sxs-lookup"><span data-stu-id="54703-134">To assign a per-user mobility policy to multiple users</span></span>

  - <span data-ttu-id="54703-135">O comando a seguir atribui a política de mobilidade por usuário RedmondMobilityPolicy a todos os usuários que atualmente recebem a política NorthAmericaMobilityPolicy.</span><span class="sxs-lookup"><span data-stu-id="54703-135">The following command assigns the per-user mobility policy RedmondMobilityPolicy to all the users who are currently assigned the policy NorthAmericaMobilityPolicy.</span></span> <span data-ttu-id="54703-136">Para obter detalhes sobre o parâmetro de filtro usado neste comando, consulte [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="54703-136">For details about the Filter parameter used in this command, see [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)).</span></span>
    
        Get-CsUser -Filter {MobilityPolicy -eq "NorthAmericaMobilityPolicy"} | Grant-CsMobilityPolicy -PolicyName "RedmondMobilityPolicy"

## <a name="to-unassign-a-per-user-mobility-policy"></a><span data-ttu-id="54703-137">Para cancelar a atribuição de uma política de mobilidade por usuário</span><span class="sxs-lookup"><span data-stu-id="54703-137">To unassign a per-user mobility policy</span></span>

  - <span data-ttu-id="54703-138">O comando a seguir não atribui atribuições de política de mobilidade por usuário anteriormente atribuídas a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="54703-138">The following command unassigns any per-user mobility policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="54703-139">Após a política por usuário ser retirada, Ken irá automaticamente ser gerenciado usando a política global ou, se existir, sua política de site local.</span><span class="sxs-lookup"><span data-stu-id="54703-139">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="54703-140">Uma política de site tem precedência sobre a política global.</span><span class="sxs-lookup"><span data-stu-id="54703-140">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="54703-141">Para obter detalhes, consulte [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/hh690038\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="54703-141">For details, see [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/hh690038\(v=ocs.15\)).</span></span>

## <a name="see-also"></a><span data-ttu-id="54703-142">Confira também</span><span class="sxs-lookup"><span data-stu-id="54703-142">See Also</span></span>


[<span data-ttu-id="54703-143">Configurando a política de mobilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54703-143">Configuring mobility policy in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-policy.md)

