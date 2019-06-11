---
title: 'Lync Server 2013: atribuir uma política de arquivamento por usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user archiving policy
ms:assetid: a12ca483-b235-460f-b3fe-130fb3087264
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182560(v=OCS.15)
ms:contentKeyID: 48185014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f82b2398002a1c2536c9a57b18f9276a9d138903
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836758"
---
# <a name="assign-a-per-user-archiving-policy-in-lync-server-2013"></a><span data-ttu-id="681cb-102">Atribuir uma política de arquivamento por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="681cb-102">Assign a per-user archiving policy in Lync Server 2013</span></span>

 


<span data-ttu-id="681cb-103">A política de arquivamento é uma das configurações individuais de uma conta de usuário que você pode configurar no painel de controle do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="681cb-103">The archiving policy is one of the individual settings of a user account that you can configure in the Lync Server 2013 Control Panel.</span></span>

<span data-ttu-id="681cb-104">A implantação de uma ou mais políticas de arquivamento por usuário é opcional.</span><span class="sxs-lookup"><span data-stu-id="681cb-104">Deploying one or more per-user archiving policies is optional.</span></span> <span data-ttu-id="681cb-105">Você também pode implantar apenas uma política de arquivamento de nível global ou política de arquivamento em nível de site.</span><span class="sxs-lookup"><span data-stu-id="681cb-105">You can also deploy only a global-level archiving policy or site-level archiving policy.</span></span> <span data-ttu-id="681cb-106">Se você implantar políticas por usuário, deverá atribui-las explicitamente aos usuários, grupos ou objeto de contato.</span><span class="sxs-lookup"><span data-stu-id="681cb-106">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="681cb-107">Os requisitos de arquivamento são automaticamente padrão para aqueles definidos na política de conferência de nível global, quando nenhuma política específica de nível de site ou por usuário é atribuída.</span><span class="sxs-lookup"><span data-stu-id="681cb-107">Archiving requirements automatically default to those defined in the global-level conferencing policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="681cb-108">Depois de criar pelo menos uma política de arquivamento por usuário, use os procedimentos neste tópico para atribuir a política que especifica apropriadamente se as comunicações internas de um determinado usuário, as comunicações externas ou ambas, serão arquivadas pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="681cb-108">After creating at least one per-user archiving policy, use the procedures in this topic to assign the policy that appropriately specifies whether a particular user’s internal communications, external communications, or both, will be archived by the server.</span></span>

<span data-ttu-id="681cb-109">Para obter detalhes sobre como criar políticas de arquivamento por usuário, consulte [criando uma política de arquivamento no Lync Server 2013 para habilitar ou desabilitar o arquivamento de comunicações internas ou externas para sites ou usuários específicos](lync-server-2013-creating-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-specific-sites-or-users.md).</span><span class="sxs-lookup"><span data-stu-id="681cb-109">For details about creating per-user archiving policies, see [Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of Internal or external communications for specific sites or users](lync-server-2013-creating-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-specific-sites-or-users.md).</span></span>

## <a name="to-assign-a-per-user-archiving-policy"></a><span data-ttu-id="681cb-110">Para atribuir uma política de arquivamento por usuário</span><span class="sxs-lookup"><span data-stu-id="681cb-110">To assign a per-user archiving policy</span></span>

1.  <span data-ttu-id="681cb-111">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="681cb-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="681cb-112">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="681cb-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="681cb-113">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="681cb-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="681cb-114">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="681cb-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="681cb-115">Use um dos seguintes métodos para localizar um usuário:</span><span class="sxs-lookup"><span data-stu-id="681cb-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="681cb-116">Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="681cb-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="681cb-117">Se você salvou uma consulta, clique no ícone **Abrir consulta**, use a caixa de diálogo **Abrir** para recuperar a consulta (um arquivo .usf) e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="681cb-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="681cb-118">(Opcional) Especifique o critério de pesquisa adicional para reduzir os resultados:</span><span class="sxs-lookup"><span data-stu-id="681cb-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="681cb-119">Clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="681cb-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="681cb-120">Insira a propriedade do usuário digitando ou clicando na seta da lista suspensa para selecionar a propriedade.</span><span class="sxs-lookup"><span data-stu-id="681cb-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="681cb-121">Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).</span><span class="sxs-lookup"><span data-stu-id="681cb-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="681cb-122">Dependendo da propriedade do usuário selecionada, insira o critério que deseja usar para filtrar os resultados de pesquisa digitando ou clicando na seta da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="681cb-122">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="681cb-123">Para adicionar cláusulas de pesquisa adicionais à sua consulta, clique em <STRONG>Adicionar filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="681cb-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="681cb-124">Clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="681cb-124">Click **Find**.</span></span>

6.  <span data-ttu-id="681cb-125">Clique em um usuário nos resultados da pesquisa, clique em **Ação** e em seguida, clique em **Atribuir políticas**.</span><span class="sxs-lookup"><span data-stu-id="681cb-125">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="681cb-126">Se você quiser que a mesma política de arquivamento por usuário seja aplicada a vários usuários, selecione vários usuários nos resultados da pesquisa, clique em <STRONG>ações</STRONG>e, em seguida, clique em <STRONG>atribuir políticas</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="681cb-126">If you want the same per-user archiving policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="681cb-127">Em **atribuir políticas**, em **política**de arquivamento, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="681cb-127">In **Assign Policies**, under **Archiving policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="681cb-128">Como há várias diretivas que você pode configurar usando a caixa de diálogo <STRONG>atribuir políticas</STRONG> , <STRONG> &lt;manter como está&gt; </STRONG> selecionado por padrão para cada política na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="681cb-128">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="681cb-129">Continue usando a política atribuída anteriormente ao usuário não realizando alterações nesta configuração.</span><span class="sxs-lookup"><span data-stu-id="681cb-129">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="681cb-130">Permitir que o Lync Server 2013 escolha automaticamente a política de nível global ou, se definida, a política de nível de site.</span><span class="sxs-lookup"><span data-stu-id="681cb-130">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="681cb-131">Clique no nome de uma política de arquivamento por usuário definida anteriormente na página **política** de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="681cb-131">Click the name of a per-user archiving policy you previously defined on the **Archiving Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="681cb-132">Para ajudá-lo a decidir a política que você deseja atribuir, depois de clicar no nome da política, clique em <STRONG>Exibir</STRONG> para ver os direitos do usuário e as permissões definidas na política.</span><span class="sxs-lookup"><span data-stu-id="681cb-132">To help you decide the policy that you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="681cb-133">Ao concluir, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="681cb-133">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="681cb-134">Atribuir uma política de arquivamento por usuário usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="681cb-134">Assigning a Per-User Archiving Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="681cb-135">Você pode atribuir políticas de arquivamento por usuário usando o Windows PowerShell e o cmdlet **Grant-CsArchivingPolicy** .</span><span class="sxs-lookup"><span data-stu-id="681cb-135">You can assign per-user archiving policies by using Windows PowerShell and the **Grant-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="681cb-136">Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="681cb-136">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="681cb-137">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="681cb-137">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a><span data-ttu-id="681cb-138">Para atribuir uma política de arquivamento por usuário a um único usuário</span><span class="sxs-lookup"><span data-stu-id="681cb-138">To assign a per-user archiving policy to a single user</span></span>

  - <span data-ttu-id="681cb-139">O comando a seguir atribui a política de arquivamento por usuário RedmondArchivingPolicy ao usuário Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="681cb-139">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a><span data-ttu-id="681cb-140">Para atribuir uma política de arquivamento por usuário a vários usuários</span><span class="sxs-lookup"><span data-stu-id="681cb-140">To assign a per-user archiving policy to multiple users</span></span>

  - <span data-ttu-id="681cb-141">Esse comando atribui a política de arquivamento por usuário RedmondArchivingPolicy a todos os usuários que têm contas hospedadas no pool de registradores atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="681cb-141">This command assigns the per-user archiving policy RedmondArchivingPolicy to all the users who have accounts homed on the Registrar pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="681cb-142">Para obter mais informações sobre o parâmetro Filter usado neste comando, consulte a documentação do cmdlet [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="681cb-142">For more information on the Filter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

## <a name="to-unassign-a-per-user-archiving-policy"></a><span data-ttu-id="681cb-143">Para cancelar a atribuição de uma política de arquivamento por usuário</span><span class="sxs-lookup"><span data-stu-id="681cb-143">To unassign a per-user archiving policy</span></span>

  - <span data-ttu-id="681cb-144">O comando a seguir cancela a atribuição de qualquer política de arquivamento por usuário atribuída anteriormente a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="681cb-144">The following command unassigns any per-user archiving policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="681cb-145">Após a política por usuário ser retirada, Ken irá automaticamente ser gerenciado usando a política global ou, se existir, sua política de site local.</span><span class="sxs-lookup"><span data-stu-id="681cb-145">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="681cb-146">Uma política de site tem precedência sobre a política global.</span><span class="sxs-lookup"><span data-stu-id="681cb-146">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="681cb-147">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Grant-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/gg398475\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="681cb-147">For more information, see the help topic for the [Grant-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/gg398475\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="681cb-148">Confira também</span><span class="sxs-lookup"><span data-stu-id="681cb-148">See Also</span></span>


[<span data-ttu-id="681cb-149">Criar uma política de arquivamento no Lync Server 2013 para habilitar ou desabilitar o arquivamento de comunicações internas ou externas para sites ou usuários específicos</span><span class="sxs-lookup"><span data-stu-id="681cb-149">Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of Internal or external communications for specific sites or users</span></span>](lync-server-2013-creating-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-specific-sites-or-users.md)  


[<span data-ttu-id="681cb-150">Como atribuir políticas por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="681cb-150">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

