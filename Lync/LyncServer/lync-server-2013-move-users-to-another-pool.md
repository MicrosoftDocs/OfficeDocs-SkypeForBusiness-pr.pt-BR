---
title: 'Lync Server 2013: mover usuários para outro pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to another pool
ms:assetid: e7b4968c-0e9d-4d56-b5f1-9edf0f7206f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182600(v=OCS.15)
ms:contentKeyID: 48185879
ms.date: 02/09/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d2702e744fbadc5d51ea42095d7bd3d60f6f010
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153623"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-users-to-another-pool-in-lync-server-2013"></a><span data-ttu-id="3b599-102">Mover usuários para outro pool no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b599-102">Move users to another pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="3b599-103">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="3b599-103">

<span> </span></span></span>

<span data-ttu-id="3b599-104">_**Última modificação do tópico:** 2018-02-09_</span><span class="sxs-lookup"><span data-stu-id="3b599-104">_**Topic Last Modified:** 2018-02-09_</span></span>

<span data-ttu-id="3b599-105">Você pode usar o painel de controle do Lync Server para atribuir usuários a um servidor ou pool específico.</span><span class="sxs-lookup"><span data-stu-id="3b599-105">You can use Lync Server Control Panel to assign users to a specific server or pool.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="3b599-106">Mover todos os usuários existentes de um pool de origem que esteja executando o Lync Server 2010 ou anterior para um pool de destino do Lync Server 2013 em um ambiente do Active Directory complexo pode resultar em uma replicação mais lenta do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3b599-106">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Lync Server 2013 destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="3b599-107">Para evitar isso, você pode usar filtros de pesquisa para mover os usuários de pools que estão executando o Lync Server 2010 ou anterior separadamente ou pode usar o Shell de gerenciamento do Lync Server para mover usuários com cmdlets.</span><span class="sxs-lookup"><span data-stu-id="3b599-107">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Lync Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="3b599-108">Além disso, a funcionalidade de filtro funciona com os usuários do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3b599-108">Also, the filter functionality works with Lync Server 2013 users.</span></span>



</div>

<div>

## <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="3b599-109">Para mover os usuários selecionados para um outro servidor ou pool</span><span class="sxs-lookup"><span data-stu-id="3b599-109">To move selected users to a different server or pool</span></span>

1.  <span data-ttu-id="3b599-110">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="3b599-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3b599-111">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3b599-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3b599-112">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3b599-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3b599-113">Na barra de navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="3b599-113">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="3b599-114">Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome de conta do SAM (Gerenciador de contas de segurança), endereço SIP ou URI (Uniform Resource Identifier) da linha da conta de usuário que você deseja e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="3b599-114">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="3b599-115">Na tabela, selecione um usuário específico ou usuários na lista.</span><span class="sxs-lookup"><span data-stu-id="3b599-115">In the table, select a specific user or users in the list.</span></span>

6.  <span data-ttu-id="3b599-116">No menu **Ação**, clique em **Mover usuários selecionados para o pool**.</span><span class="sxs-lookup"><span data-stu-id="3b599-116">On the **Action** menu, click **Move selected users to pool**.</span></span>

7.  <span data-ttu-id="3b599-117">Em **Mover Usuários**, selecione o pool para o qual você deseja mover os usuários em **Pool de registradores de destino**.</span><span class="sxs-lookup"><span data-stu-id="3b599-117">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>

8.  <span data-ttu-id="3b599-118">(Opcional) Se o pool ou o servidor de destino não estiver disponível, marque a caixa de seleção **Forçar**.</span><span class="sxs-lookup"><span data-stu-id="3b599-118">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="3b599-119">Se você selecionar <STRONG>forçar</STRONG>, a conta do usuário será movida, mas os dados do usuário associados, conferências e contatos agendados não serão movidos.</span><span class="sxs-lookup"><span data-stu-id="3b599-119">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="3b599-120">Para mover todos os usuários de um servidor ou pool para outro servidor ou pool</span><span class="sxs-lookup"><span data-stu-id="3b599-120">To move all users from one server or pool to a different server or pool</span></span>

1.  <span data-ttu-id="3b599-121">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="3b599-121">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3b599-122">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3b599-122">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3b599-123">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3b599-123">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3b599-124">Na barra de navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="3b599-124">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="3b599-125">No menu **Ação**, clique em **Mover todos os usuários para o pool**.</span><span class="sxs-lookup"><span data-stu-id="3b599-125">On the **Action** menu, click **Move all users to pool**.</span></span>

5.  <span data-ttu-id="3b599-126">Em **Mover Usuários**, selecione o pool que contém as contas de usuário que você deseja mover para o **Pool de registradores de origem**.</span><span class="sxs-lookup"><span data-stu-id="3b599-126">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>

6.  <span data-ttu-id="3b599-127">Em \*\*Pool de registradores de destino \*\*, selecione o pool para o qual você deseja mover os usuários.</span><span class="sxs-lookup"><span data-stu-id="3b599-127">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>

7.  <span data-ttu-id="3b599-128">(Opcional) Se o pool ou o servidor de destino estiver indisponível, selecione a caixa de diálogo **Forçar**.</span><span class="sxs-lookup"><span data-stu-id="3b599-128">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="3b599-129">Se você selecionar <STRONG>forçar</STRONG>, a conta do usuário será movida, mas os dados do usuário associados, conferências e contatos agendados não serão movidos.</span><span class="sxs-lookup"><span data-stu-id="3b599-129">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="3b599-130">Para mover usuários de um pool para um pool diferente usando um filtro</span><span class="sxs-lookup"><span data-stu-id="3b599-130">To move users from one pool to a different pool by using a filter</span></span>

1.  <span data-ttu-id="3b599-131">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="3b599-131">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3b599-132">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3b599-132">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3b599-133">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3b599-133">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3b599-134">Na barra de navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="3b599-134">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="3b599-135">Em **pesquisa de usuário**, clique em **Pesquisar**e, em seguida, clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="3b599-135">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>

5.  <span data-ttu-id="3b599-136">Nos Critérios de pesquisa, selecione **Pool de Registradores**, selecione **Igual a**, selecione **FQDN Atual do Pool** e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="3b599-136">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>

6.  <span data-ttu-id="3b599-137">No menu **Ação**, clique em **Mover todos os usuários para o pool**.</span><span class="sxs-lookup"><span data-stu-id="3b599-137">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3b599-138">Quando um filtro é aplicado a um conjunto existente de usuários, a opção <STRONG>mover todos os usuários para o pool</STRONG> está no contexto do subconjunto filtrado de usuários, e não de <STRONG><EM>todos</EM></STRONG> os usuários possíveis.</span><span class="sxs-lookup"><span data-stu-id="3b599-138">When a filter is applied to an existing set of users, the option <STRONG>Move all users to pool</STRONG> is in the context of the filtered subset of users, not <STRONG><EM>all</EM></STRONG> possible users.</span></span>

    
    </div>

7.  <span data-ttu-id="3b599-139">Em **Mover Usuários**, selecione o pool que contenha as contas de usuário que você deseja mover no **Pool de registradores de origem**.</span><span class="sxs-lookup"><span data-stu-id="3b599-139">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>

8.  <span data-ttu-id="3b599-140">Em \*\*Pool de registradores de destino \*\*, selecione o pool para o qual você deseja mover os usuários.</span><span class="sxs-lookup"><span data-stu-id="3b599-140">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>

9.  <span data-ttu-id="3b599-141">(Opcional) Se o pool ou o servidor de destino não estiver disponível, marque a caixa de seleção **Forçar**.</span><span class="sxs-lookup"><span data-stu-id="3b599-141">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="3b599-142">Se você selecionar <STRONG>forçar</STRONG>, a conta do usuário será movida, mas os dados do usuário associados, conferências e contatos agendados não serão movidos.</span><span class="sxs-lookup"><span data-stu-id="3b599-142">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="3b599-143">Para mover usuários de um pool para outro usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3b599-143">To move users from one pool to another using Windows PowerShell cmdlets</span></span>

1.  <span data-ttu-id="3b599-144">Dependendo de como você executa os comandos do Windows PowerShell (ou seja, local ou remotamente), você precisa fazer logon como um membro das funções administrativas corretas do Lync Server 2013, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="3b599-144">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Lync Server 2013 administrative roles as follows:</span></span>
    
    1.  <span data-ttu-id="3b599-145">Se você estiver executando os comandos na máquina local (por exemplo, você faz logon diretamente em um servidor front-end): faça logon no computador onde o Shell de gerenciamento do Lync Server está instalado como um membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="3b599-145">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>
    
    2.  <span data-ttu-id="3b599-146">Se você estiver executando os comandos remotamente em outro computador (por exemplo, você faz logon no seu computador e executa os comandos remotamente em um servidor front-end Standard Edition): de uma conta de usuário atribuída à função CsUserAdministrator ou à CsAdministrator função, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="3b599-146">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3b599-147">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="3b599-147">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="3b599-148">Para mover usuários único, use o cmdlet Move-CsUser da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="3b599-148">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
        Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    
    <span data-ttu-id="3b599-149">Quando o usuário a ser movido for Pilar Ackerman, e for movido de seu pool doméstico atribuído atualmente para o pool pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="3b599-149">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>

4.  <span data-ttu-id="3b599-150">Para mover muitos usuários, use os filtros com o cmdlet **Get-CsUser** e passe o conjunto resultante de usuários para **Move-CsUser**:</span><span class="sxs-lookup"><span data-stu-id="3b599-150">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    
    <span data-ttu-id="3b599-151">Os comandos combinados do **Get-CsUser** e do **Move-CsUser** podem resultar nisto:</span><span class="sxs-lookup"><span data-stu-id="3b599-151">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3b599-152">Confira também</span><span class="sxs-lookup"><span data-stu-id="3b599-152">See Also</span></span>


[<span data-ttu-id="3b599-153">Modificando Propriedades da conta de usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b599-153">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)  
  

<span data-ttu-id="3b599-154"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="3b599-154"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

