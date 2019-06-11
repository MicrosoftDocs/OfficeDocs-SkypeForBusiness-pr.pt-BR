---
title: 'Lync Server 2013: mover usuários para outro pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move users to another pool
ms:assetid: e7b4968c-0e9d-4d56-b5f1-9edf0f7206f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182600(v=OCS.15)
ms:contentKeyID: 48185879
ms.date: 02/09/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fb716c0b551475a53cacf09be10ffdc039f5db8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826651"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-users-to-another-pool-in-lync-server-2013"></a><span data-ttu-id="062f5-102">Mover usuários para outro pool no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="062f5-102">Move users to another pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="062f5-103">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="062f5-103"></span></span>

<span data-ttu-id="062f5-104">_**Tópico da última modificação:** 2018-02-09_</span><span class="sxs-lookup"><span data-stu-id="062f5-104">_**Topic Last Modified:** 2018-02-09_</span></span>

<span data-ttu-id="062f5-105">Você pode usar o painel de controle do Lync Server para atribuir usuários a um servidor ou pool específico.</span><span class="sxs-lookup"><span data-stu-id="062f5-105">You can use Lync Server Control Panel to assign users to a specific server or pool.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="062f5-106">Mover todos os usuários existentes de um pool de origem que esteja executando o Lync Server 2010 ou anterior para um pool de destino do Lync Server 2013 em um ambiente complexo do Active Directory pode resultar em uma replicação mais lenta do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="062f5-106">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Lync Server 2013 destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="062f5-107">Para evitar isso, você pode usar filtros de pesquisa para mover os usuários de pools que executam o Lync Server 2010 ou anterior separadamente, ou você pode usar o Shell de gerenciamento do Lync Server para mover usuários com cmdlets.</span><span class="sxs-lookup"><span data-stu-id="062f5-107">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Lync Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="062f5-108">Além disso, a funcionalidade de filtro funciona com usuários do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="062f5-108">Also, the filter functionality works with Lync Server 2013 users.</span></span>



</div>

<div>

## <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="062f5-109">Para mover os usuários selecionados para um servidor ou pool diferente</span><span class="sxs-lookup"><span data-stu-id="062f5-109">To move selected users to a different server or pool</span></span>

1.  <span data-ttu-id="062f5-110">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="062f5-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="062f5-111">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="062f5-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="062f5-112">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="062f5-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="062f5-113">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="062f5-113">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="062f5-114">Na caixa **Pesquisar usuários** , digite toda ou a primeira parte do nome para exibição, nome, sobrenome, nome da conta do Gerenciador de contas de segurança (Sam), endereço SIP ou URI (Uniform Resource Identifier) da conta de usuário que você deseja e clique em \*\*Localizar \*\*.</span><span class="sxs-lookup"><span data-stu-id="062f5-114">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="062f5-115">Na tabela, selecione um usuário ou usuários específicos na lista.</span><span class="sxs-lookup"><span data-stu-id="062f5-115">In the table, select a specific user or users in the list.</span></span>

6.  <span data-ttu-id="062f5-116">No menu **ação** , clique em **mover usuários selecionados para o pool**.</span><span class="sxs-lookup"><span data-stu-id="062f5-116">On the **Action** menu, click **Move selected users to pool**.</span></span>

7.  <span data-ttu-id="062f5-117">Em **mover usuários**, selecione o pool para o qual você deseja mover os usuários no **pool**de registradores de destino.</span><span class="sxs-lookup"><span data-stu-id="062f5-117">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>

8.  <span data-ttu-id="062f5-118">Adicionais Se o servidor ou o pool de destino não estiver disponível, marque a caixa de seleção **forçar** .</span><span class="sxs-lookup"><span data-stu-id="062f5-118">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="062f5-119">Se você selecionar <STRONG>forçar</STRONG>, a conta do usuário será movida, mas os dados do usuário associados, conferências programadas e contatos não serão movidos.</span><span class="sxs-lookup"><span data-stu-id="062f5-119">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="062f5-120">Para mover todos os usuários de um servidor ou pool para um servidor ou pool diferente</span><span class="sxs-lookup"><span data-stu-id="062f5-120">To move all users from one server or pool to a different server or pool</span></span>

1.  <span data-ttu-id="062f5-121">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="062f5-121">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="062f5-122">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="062f5-122">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="062f5-123">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="062f5-123">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="062f5-124">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="062f5-124">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="062f5-125">No menu **ação** , clique em **mover todos os usuários para o pool**.</span><span class="sxs-lookup"><span data-stu-id="062f5-125">On the **Action** menu, click **Move all users to pool**.</span></span>

5.  <span data-ttu-id="062f5-126">Em **mover usuários**, selecione o pool que contém as contas de usuário que você deseja mover no **pool**de registradores de origem.</span><span class="sxs-lookup"><span data-stu-id="062f5-126">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>

6.  <span data-ttu-id="062f5-127">No **pool**de registradores de destino, selecione o pool para o qual você deseja mover os usuários.</span><span class="sxs-lookup"><span data-stu-id="062f5-127">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>

7.  <span data-ttu-id="062f5-128">Adicionais Se o servidor ou o pool de destino não estiver disponível, marque a caixa de seleção **forçar** .</span><span class="sxs-lookup"><span data-stu-id="062f5-128">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="062f5-129">Se você selecionar <STRONG>forçar</STRONG>, a conta do usuário será movida, mas os dados do usuário associados, conferências programadas e contatos não serão movidos.</span><span class="sxs-lookup"><span data-stu-id="062f5-129">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="062f5-130">Para mover os usuários de um pool para um pool diferente usando um filtro</span><span class="sxs-lookup"><span data-stu-id="062f5-130">To move users from one pool to a different pool by using a filter</span></span>

1.  <span data-ttu-id="062f5-131">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="062f5-131">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="062f5-132">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="062f5-132">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="062f5-133">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="062f5-133">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="062f5-134">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="062f5-134">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="062f5-135">Em **pesquisa de usuário**, clique em **Pesquisar**e, em seguida, clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="062f5-135">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>

5.  <span data-ttu-id="062f5-136">Nos critérios de pesquisa, selecione **pool**de registradores, selecione **igual a**, selecione o **FQDN do pool atual**e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="062f5-136">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>

6.  <span data-ttu-id="062f5-137">No menu **ação** , clique em **mover todos os usuários para o pool**.</span><span class="sxs-lookup"><span data-stu-id="062f5-137">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="062f5-138">Quando um filtro é aplicado a um conjunto de usuários existente, a opção <STRONG>mover todos os usuários para o pool</STRONG> está no contexto do subconjunto filtrado de usuários, e não <STRONG><EM>todos</EM></STRONG> os usuários possíveis.</span><span class="sxs-lookup"><span data-stu-id="062f5-138">When a filter is applied to an existing set of users, the option <STRONG>Move all users to pool</STRONG> is in the context of the filtered subset of users, not <STRONG><EM>all</EM></STRONG> possible users.</span></span>

    
    </div>

7.  <span data-ttu-id="062f5-139">Em **mover usuários**, selecione o pool que contém as contas de usuário que você deseja mover no **pool**de registradores de origem.</span><span class="sxs-lookup"><span data-stu-id="062f5-139">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>

8.  <span data-ttu-id="062f5-140">No **pool**de registradores de destino, selecione o pool para o qual você deseja mover os usuários.</span><span class="sxs-lookup"><span data-stu-id="062f5-140">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>

9.  <span data-ttu-id="062f5-141">Adicionais Se o servidor ou o pool de destino não estiver disponível, marque a caixa de seleção **forçar** .</span><span class="sxs-lookup"><span data-stu-id="062f5-141">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="062f5-142">Se você selecionar <STRONG>forçar</STRONG>, a conta do usuário será movida, mas os dados do usuário associados, conferências programadas e contatos não serão movidos.</span><span class="sxs-lookup"><span data-stu-id="062f5-142">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="062f5-143">Para mover os usuários de um pool para outro usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="062f5-143">To move users from one pool to another using Windows PowerShell cmdlets</span></span>

1.  <span data-ttu-id="062f5-144">Dependendo de como você executa comandos do Windows PowerShell (ou seja, local ou remotamente), você precisa fazer logon como membro das funções administrativas corretas do Lync Server 2013 da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="062f5-144">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Lync Server 2013 administrative roles as follows:</span></span>
    
    1.  <span data-ttu-id="062f5-145">Se você estiver executando os comandos no computador local (por exemplo, você fizer logon diretamente em um servidor front-end): faça logon no computador em que o Shell de gerenciamento do Lync Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários como descrito em [permissões de configuração de representante no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="062f5-145">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>
    
    2.  <span data-ttu-id="062f5-146">Se você estiver executando os comandos remotamente em outro computador (por exemplo, se conectar ao seu computador e executar os comandos remotamente em um servidor front-end Standard Edition): de uma conta de usuário atribuída à função CsUserAdministrator ou ao CsAdministrator , faça logon em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="062f5-146">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="062f5-147">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="062f5-147">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="062f5-148">Para mover usuários únicos, use o cmdlet Move-CsUser da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="062f5-148">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
        Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    
    <span data-ttu-id="062f5-149">Onde o usuário mover é o usuário pilar Alverca, e o usuário será movido do pool inicial atribuído no momento para o pool pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="062f5-149">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>

4.  <span data-ttu-id="062f5-150">Para mover um grande número de usuários, use filtros com o cmdlet **Get-CsUser** e passe o conjunto resultante de usuários para **mover-CsUser**:</span><span class="sxs-lookup"><span data-stu-id="062f5-150">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    
    <span data-ttu-id="062f5-151">Os comandos combinados do **Get-CsUser** e do **move-CsUser** podem fazer isso:</span><span class="sxs-lookup"><span data-stu-id="062f5-151">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="062f5-152">Confira também</span><span class="sxs-lookup"><span data-stu-id="062f5-152">See Also</span></span>


[<span data-ttu-id="062f5-153">Modificando Propriedades de conta de usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="062f5-153">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)  
  

<span data-ttu-id="062f5-154"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="062f5-154"></span></span></div>

