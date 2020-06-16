---
title: Mover vários usuários para o pool piloto
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 90d0590c-922c-4933-b778-9dd850b59310
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205096(v=OCS.15)
ms:contentKeyID: 48184838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a5a92b0438e72be0ecb5acaa1b8e1886768ad59
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="36f26-102">Mover vários usuários para o pool piloto</span><span class="sxs-lookup"><span data-stu-id="36f26-102">Move multiple users to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36f26-103">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="36f26-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="36f26-104">Você pode mover vários usuários do pool do Lync Server 2010 para o pool piloto do Lync Server 2013 usando o painel de controle do Lync Server 2013 ou o Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="36f26-104">You can move multiple users from your Lync Server 2010 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="36f26-105">Para mover vários usuários usando o painel de controle do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36f26-105">To move multiple users by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="36f26-106">Abra o **Painel de Controle do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="36f26-106">Open **Lync Server Control Panel**.</span></span>

2.  <span data-ttu-id="36f26-107">Clique em **Usuários**, em Pesquisar e em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="36f26-107">Click **Users**, click Search, and then click **Find**.</span></span>

3.  <span data-ttu-id="36f26-108">Selecione dois usuários que você deseja mover para o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="36f26-108">Select two users that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="36f26-109">Neste exemplo, vamos mover os usuários Chen Yang e Claus Hansen.</span><span class="sxs-lookup"><span data-stu-id="36f26-109">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
    <span data-ttu-id="36f26-110">![Mover usuários para o pool de registro específico](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "Mover usuários para o pool de registro específico")</span><span class="sxs-lookup"><span data-stu-id="36f26-110">![Move users to specific register pool](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "Move users to specific register pool")</span></span>  

4.  <span data-ttu-id="36f26-111">No menu **Ação**, selecione **Mover usuários selecionados para o pool**.</span><span class="sxs-lookup"><span data-stu-id="36f26-111">From the **Action** menu, select **Move selected users to pool**.</span></span>

5.  <span data-ttu-id="36f26-112">Na lista suspensa, selecione o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="36f26-112">From the drop-down list, select the Lync Server 2013 pool.</span></span>

6.  <span data-ttu-id="36f26-113">Clique em **Ação** e depois em **Mover usuários selecionados para o pool**.</span><span class="sxs-lookup"><span data-stu-id="36f26-113">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="36f26-114">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="36f26-114">Click OK.</span></span>
    
    <span data-ttu-id="36f26-115">![Caixa de diálogo mover usuários, pool de registradores de destino](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Caixa de diálogo mover usuários, pool de registradores de destino")</span><span class="sxs-lookup"><span data-stu-id="36f26-115">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

7.  <span data-ttu-id="36f26-116">Verifique se a coluna **pool do registrador** dos usuários agora contém o pool do Lync Server 2013, que indica que os usuários foram movidos com êxito.</span><span class="sxs-lookup"><span data-stu-id="36f26-116">Verify that the **Registrar pool** column for the users now contains the Lync Server 2013 pool, which indicates that the users have been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="36f26-117">Para mover vários usuários usando o Shell de gerenciamento do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36f26-117">To move multiple users by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="36f26-118">Abra o Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="36f26-118">Open the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="36f26-119">Na linha de comando, digite o seguinte e substitua **Usuário1** e **Usuário2** com nomes de usuário específicos que você deseja mover e substituir o \*\* \_ FQDN do pool\*\* pelo nome do pool de destino.</span><span class="sxs-lookup"><span data-stu-id="36f26-119">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move and replace **pool\_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="36f26-120">Neste exemplo, vamos mover os usuários Hao Chen e Katie Jordan.</span><span class="sxs-lookup"><span data-stu-id="36f26-120">In this example we will move users Hao Chen and Katie Jordan.</span></span>
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
    
    <span data-ttu-id="36f26-121">![Exemplo de cmdlet Get-CsUser do PowerShell](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Exemplo de cmdlet Get-CsUser do PowerShell")</span><span class="sxs-lookup"><span data-stu-id="36f26-121">![Example of PowerShell Get-CsUser cmdlet](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Example of PowerShell Get-CsUser cmdlet")</span></span>  

3.  <span data-ttu-id="36f26-122">Na linha de comando, digite o seguinte</span><span class="sxs-lookup"><span data-stu-id="36f26-122">At the command line, type the following</span></span>
    
        Get-CsUser -Identity "User1"

4.  <span data-ttu-id="36f26-123">A identidade do **pool do registrador** agora deve apontar para o pool que você especificou como \*\* \_ FQDN do pool\*\* na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="36f26-123">The **Registrar Pool** identity should now point to the pool you specified as **pool\_FQDN** in the previous step.</span></span> <span data-ttu-id="36f26-124">A presença dessa identidade confirma que o usuário foi movido com sucesso.</span><span class="sxs-lookup"><span data-stu-id="36f26-124">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="36f26-125">Repita a etapa para verificar se o **User2** foi movido.</span><span class="sxs-lookup"><span data-stu-id="36f26-125">Repeat step to verify **User2** has been moved.</span></span>
    
    <span data-ttu-id="36f26-126">![Saída do cmdlet Get-UsUser-Identity do PowerShell](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Saída do cmdlet Get-UsUser-Identity do PowerShell")</span><span class="sxs-lookup"><span data-stu-id="36f26-126">![Output of PowerShell Get-UsUser -Identity cmdlet](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Output of PowerShell Get-UsUser -Identity  cmdlet")</span></span>  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="36f26-127">Para mover todos os usuários ao mesmo tempo usando o Shell de gerenciamento do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36f26-127">To move all users at the same time by using the Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="36f26-128">Neste exemplo, todos os usuários foram retornados para o pool do Lync Server 2010 (pool01.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="36f26-128">In this example, all users have been returned to the Lync Server 2010 pool (pool01.contoso.net).</span></span> <span data-ttu-id="36f26-129">Usando o Shell de gerenciamento do Lync Server 2013, todos os usuários serão movidos ao mesmo tempo para o pool do Lync Server 2013 (pool02.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="36f26-129">Using the Lync Server 2013 Management Shell, we will move all users at the same time to the Lync Server 2013 pool (pool02.contoso.net).</span></span>

1.  <span data-ttu-id="36f26-130">Abra o **Shell de gerenciamento do Lync Server 2013**.</span><span class="sxs-lookup"><span data-stu-id="36f26-130">Open the **Lync Server 2013 Management Shell**.</span></span>

2.  <span data-ttu-id="36f26-131">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="36f26-131">At the command line, type the following:</span></span>
    
        Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
    
    <span data-ttu-id="36f26-132">![Cmdlet do PowerShell e resultados no Shell de gerenciamento](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "Cmdlet do PowerShell e resultados no Shell de gerenciamento")</span><span class="sxs-lookup"><span data-stu-id="36f26-132">![PowerShell cmdlet and results in Management Shell](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "PowerShell cmdlet and results in Management Shell")</span></span>  

3.  <span data-ttu-id="36f26-133">Depois, execute **Get-CsUser** de um dos usuários piloto.</span><span class="sxs-lookup"><span data-stu-id="36f26-133">Next, run **Get-CsUser** for one of the pilot users.</span></span>
    
        Get-CsUser -Identity "Hao Chen"

4.  <span data-ttu-id="36f26-134">A identidade do **pool de registradores** para cada usuário agora aponta para o pool que você especificou como " \_ FQDN do pool" na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="36f26-134">The **Registrar Pool** identity for each user now points to the pool you specified as “pool\_FQDN” in the previous step.</span></span> <span data-ttu-id="36f26-135">A presença dessa identidade confirma que o usuário foi movido com sucesso.</span><span class="sxs-lookup"><span data-stu-id="36f26-135">The presence of this identity confirms that the user has been successfully moved.</span></span>

5.  <span data-ttu-id="36f26-136">Além disso, podemos exibir a lista de usuários no painel de controle do Lync Server 2013 e verificar se o valor do pool do registrador agora aponta para o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="36f26-136">Additionally, we can view the list of users in the Lync Server 2013 Control Panel and verify that the Registrar Pool value now points to the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="36f26-137">![Lista de usuários do painel de controle do Lync Server 2013](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lista de usuários do painel de controle do Lync Server 2013")</span><span class="sxs-lookup"><span data-stu-id="36f26-137">![Lync Server 2013 Control Panel user list](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 Control Panel user list")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

