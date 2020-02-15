---
title: Mover vários usuários para o pool piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 9492797f-2a26-4773-8ad2-97cb53fa68fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688143(v=OCS.15)
ms:contentKeyID: 49733745
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d659e879b821f27c159cee874dae9db0796f079b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="e19ef-102">Mover vários usuários para o pool piloto</span><span class="sxs-lookup"><span data-stu-id="e19ef-102">Move multiple users to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e19ef-103">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="e19ef-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e19ef-104">Você pode mover vários usuários do pool do Office Communications Server 2007 R2 para o pool piloto do Lync Server 2013 usando o painel de controle do Lync Server 2013 ou o Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e19ef-104">You can move multiple users from your Office Communications Server 2007 R2 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="e19ef-105">Para mover vários usuários usando o painel de controle do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e19ef-105">To move multiple users by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="e19ef-106">Abrir **Painel de Controle do Lync Server**</span><span class="sxs-lookup"><span data-stu-id="e19ef-106">Open **Lync Server Control Panel**.</span></span>

2.  <span data-ttu-id="e19ef-107">Na guia **Pesquisa de Usuário**, clique no botão **Pesquisar**.</span><span class="sxs-lookup"><span data-stu-id="e19ef-107">From the **User Search** tab, click the **Search** button.</span></span>

3.  <span data-ttu-id="e19ef-108">Em seguida, clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="e19ef-108">Next, click **Add Filter**.</span></span>

4.  <span data-ttu-id="e19ef-109">Crie um filtro onde o **usuário do Office Communications Server** for igual a **Verdadeiro**.</span><span class="sxs-lookup"><span data-stu-id="e19ef-109">Create a filter where **Office Communications Server user** is equal to **True**.</span></span>

5.  <span data-ttu-id="e19ef-110">Clique em **Localizar** para pesquisar usuários herdados do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e19ef-110">Click **Find** to search for legacy Office Communications Server 2007 R2 users.</span></span>

6.  <span data-ttu-id="e19ef-111">Selecione dois usuários que você deseja mover para o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e19ef-111">Select two users that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="e19ef-112">Neste exemplo, vamos mover os usuários Chen Yang e Claus Hansen.</span><span class="sxs-lookup"><span data-stu-id="e19ef-112">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
    <span data-ttu-id="e19ef-113">![Lista de usuários exibida na pesquisa de usuários do OCS](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "Lista de usuários exibida na pesquisa de usuários do OCS")</span><span class="sxs-lookup"><span data-stu-id="e19ef-113">![User list displayed from searching for OCS users](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "User list displayed from searching for OCS users")</span></span>  

7.  <span data-ttu-id="e19ef-114">No menu **Ação**, selecione **Mover usuários selecionados para o pool**.</span><span class="sxs-lookup"><span data-stu-id="e19ef-114">From the **Action** menu, select **Move selected users to pool**.</span></span>

8.  <span data-ttu-id="e19ef-115">Na lista suspensa, selecione o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e19ef-115">From the drop-down list, select the Lync Server 2013 pool.</span></span>

9.  <span data-ttu-id="e19ef-116">Clique em **Ação** e depois em **Mover usuários selecionados para o pool**.</span><span class="sxs-lookup"><span data-stu-id="e19ef-116">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="e19ef-117">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="e19ef-117">Click OK.</span></span>
    
    <span data-ttu-id="e19ef-118">![Caixa de diálogo mover usuários, pool de registradores de destino](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Caixa de diálogo mover usuários, pool de registradores de destino")</span><span class="sxs-lookup"><span data-stu-id="e19ef-118">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

10. <span data-ttu-id="e19ef-119">Verifique se a coluna **pool do registrador** dos usuários agora contém o pool do Lync Server 2013, que indica que os usuários foram movidos com êxito.</span><span class="sxs-lookup"><span data-stu-id="e19ef-119">Verify that the **Registrar pool** column for the users now contains the Lync Server 2013 pool, which indicates that the users have been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="e19ef-120">Para mover vários usuários usando o Shell de gerenciamento do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e19ef-120">To move multiple users by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="e19ef-121">Abra o Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e19ef-121">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="e19ef-122">Na linha de comando, digite o seguinte e substitua **Usuário1** e **Usuário2** com nomes de usuário específicos que você deseja mover e substituir o **FQDN do\_pool** pelo nome do pool de destino.</span><span class="sxs-lookup"><span data-stu-id="e19ef-122">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move and replace **pool\_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="e19ef-123">Neste exemplo, vamos mover os usuários Hao Chen e Katie Jordan.</span><span class="sxs-lookup"><span data-stu-id="e19ef-123">In this example we will move users Hao Chen and Katie Jordan.</span></span>
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsLegacyUser -Target "pool_FQDN"
    
    <span data-ttu-id="e19ef-124">![Cmdlet de exemplo para mover um usuário herdado](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "Cmdlet de exemplo para mover um usuário herdado")</span><span class="sxs-lookup"><span data-stu-id="e19ef-124">![Example cmdlet to move a legacy user](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "Example cmdlet to move a legacy user")</span></span>  

3.  <span data-ttu-id="e19ef-125">Na linha de comando, digite o seguinte</span><span class="sxs-lookup"><span data-stu-id="e19ef-125">At the command line, type the following</span></span>
    
        Get-CsUser -Identity "User1"

4.  <span data-ttu-id="e19ef-126">A identidade do **pool do registrador** agora deve apontar para o pool que você especificou como **FQDN do pool\_** na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="e19ef-126">The **Registrar Pool** identity should now point to the pool you specified as **pool\_FQDN** in the previous step.</span></span> <span data-ttu-id="e19ef-127">A presença dessa identidade confirma que o usuário foi movido com sucesso.</span><span class="sxs-lookup"><span data-stu-id="e19ef-127">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="e19ef-128">Repita a etapa para verificar se o **User2** foi movido.</span><span class="sxs-lookup"><span data-stu-id="e19ef-128">Repeat step to verify **User2** has been moved.</span></span>
    
    <span data-ttu-id="e19ef-129">![Saída do cmdlet Get-UsUser-Identity do PowerShell](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Saída do cmdlet Get-UsUser-Identity do PowerShell")</span><span class="sxs-lookup"><span data-stu-id="e19ef-129">![Output of PowerShell Get-UsUser -Identity cmdlet](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Output of PowerShell Get-UsUser -Identity  cmdlet")</span></span>  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="e19ef-130">Para mover todos os usuários ao mesmo tempo usando o Shell de gerenciamento do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e19ef-130">To move all users at the same time by using the Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="e19ef-131">Neste exemplo, todos os usuários foram retornados para o pool do Office Communications Server 2007 R2 (pool01.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="e19ef-131">In this example, all users have been returned to the Office Communications Server 2007 R2 pool (pool01.contoso.net).</span></span> <span data-ttu-id="e19ef-132">Usando o Shell de gerenciamento do Lync Server 2013, todos os usuários serão movidos ao mesmo tempo para o pool do Lync Server 2013 (pool02.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="e19ef-132">Using the Lync Server 2013 Management Shell, we will move all users at the same time to the Lync Server 2013 pool (pool02.contoso.net).</span></span>

1.  <span data-ttu-id="e19ef-133">Abra o **Shell de gerenciamento do Lync Server 2013**.</span><span class="sxs-lookup"><span data-stu-id="e19ef-133">Open the **Lync Server 2013 Management Shell**.</span></span>

2.  <span data-ttu-id="e19ef-134">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e19ef-134">At the command line, type the following:</span></span>
    
        Get-CsUser -OnOfficeCommunicationServer | Move-CsLegacyUser -Target "pool_FQDN"
    
    <span data-ttu-id="e19ef-135">![Cmdlet de exemplo para mover todos os usuários herdados em um pool](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "Cmdlet de exemplo para mover todos os usuários herdados em um pool")</span><span class="sxs-lookup"><span data-stu-id="e19ef-135">![Example cmdlet to move all legacy users in a pool](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "Example cmdlet to move all legacy users in a pool")</span></span>  

3.  <span data-ttu-id="e19ef-136">Depois, execute **Get-CsUser** de um dos usuários piloto.</span><span class="sxs-lookup"><span data-stu-id="e19ef-136">Next, run **Get-CsUser** for one of the pilot users.</span></span>
    
        Get-CsUser -Identity "Hao Chen"

4.  <span data-ttu-id="e19ef-137">A identidade do **pool de registradores** para cada usuário agora aponta para o pool que você\_especificou como "FQDN do pool" na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="e19ef-137">The **Registrar Pool** identity for each user now points to the pool you specified as “pool\_FQDN” in the previous step.</span></span> <span data-ttu-id="e19ef-138">A presença dessa identidade confirma que o usuário foi movido com sucesso.</span><span class="sxs-lookup"><span data-stu-id="e19ef-138">The presence of this identity confirms that the user has been successfully moved.</span></span>

5.  <span data-ttu-id="e19ef-139">Além disso, podemos exibir a lista de usuários no painel de controle do Lync Server 2013 e verificar se o valor do pool do registrador agora aponta para o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e19ef-139">Additionally, we can view the list of users in the Lync Server 2013 Control Panel and verify that the Registrar Pool value now points to the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="e19ef-140">![Lista de usuários do painel de controle do Lync Server 2013](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lista de usuários do painel de controle do Lync Server 2013")</span><span class="sxs-lookup"><span data-stu-id="e19ef-140">![Lync Server 2013 Control Panel user list](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 Control Panel user list")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

