---
title: Mover um único usuário para o pool piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move a single user to the pilot pool
ms:assetid: 80d5b365-f153-4c61-a148-f9e18ce6e027
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688109(v=OCS.15)
ms:contentKeyID: 49733708
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 086af622644f8d8285ef5f7be8e17f75ff436000
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844234"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="4e2a9-102">Mover um único usuário para o pool piloto</span><span class="sxs-lookup"><span data-stu-id="4e2a9-102">Move a single user to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e2a9-103">_**Tópico da última modificação:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="4e2a9-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="4e2a9-104">Você pode mover um usuário do pool do Office Communications Server 2007 R2 para o pool piloto do Lync Server 2013 usando o painel de controle do Lync Server 2013 ou o Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e2a9-104">You can move a user from your Office Communications Server 2007 R2 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="4e2a9-105">No exemplo a seguir, na coluna pool de registradores, \*\* \<o Office\> Communications Server\*\* é o pool do Office Communications Server 2007 R2 e todos os seis usuários estão conectados a esse pool.</span><span class="sxs-lookup"><span data-stu-id="4e2a9-105">In the example below, in the Registrar pool column, **\<Office Communications Server\>** is the Office Communications Server 2007 R2 pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="4e2a9-106">Use os procedimentos a seguir para mover um usuário para o pool do Lync Server 2013 usando o painel de controle do Lync Server 2013 e o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4e2a9-106">Use the following procedures to move a user to your Lync Server 2013 pool using Lync Server 2013 Control Panel and Lync Server Management Shell.</span></span>

<span data-ttu-id="4e2a9-107">![Pesquisar usuários do OCS no painel de controle do Lync Server] (images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Pesquisar usuários do OCS no painel de controle do Lync Server")</span><span class="sxs-lookup"><span data-stu-id="4e2a9-107">![Search for OCS users in Lync Server Control Panel](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Search for OCS users in Lync Server Control Panel")</span></span>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="4e2a9-108">Para mover um usuário usando o painel de controle do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e2a9-108">To move a user by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="4e2a9-109">Faça logon no Servidor Front-end com uma conta que seja membro do grupo de RTCUniversalServerAdmins ou membro da função administrativa do CsAdministrator ou CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="4e2a9-109">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="4e2a9-110">Abra o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4e2a9-110">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="4e2a9-111">Clique em **usuários**.</span><span class="sxs-lookup"><span data-stu-id="4e2a9-111">Click **Users**.</span></span>

4.  <span data-ttu-id="4e2a9-112">Na guia **pesquisa de usuário** , clique no botão **Pesquisar** .</span><span class="sxs-lookup"><span data-stu-id="4e2a9-112">From the **User Search** tab, click the **Search** button.</span></span>

5.  <span data-ttu-id="4e2a9-113">Em seguida, clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="4e2a9-113">Next, click **Add Filter**.</span></span>

6.  <span data-ttu-id="4e2a9-114">Crie um filtro onde o **usuário do Office Communications Server** é igual a **true**.</span><span class="sxs-lookup"><span data-stu-id="4e2a9-114">Create a filter where **Office Communications Server user** is equal to **True**.</span></span>

7.  <span data-ttu-id="4e2a9-115">Clique em **Localizar** para pesquisar usuários herdados do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="4e2a9-115">Click **Find** to search for legacy Office Communications Server 2007 R2 users.</span></span>
    
    <span data-ttu-id="4e2a9-116">![Pesquisar usuários do OCS no painel de controle do Lync Server] (images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Pesquisar usuários do OCS no painel de controle do Lync Server")</span><span class="sxs-lookup"><span data-stu-id="4e2a9-116">![Search for OCS users in Lync Server Control Panel](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Search for OCS users in Lync Server Control Panel")</span></span>  

8.  <span data-ttu-id="4e2a9-117">Selecione o usuário que você deseja mover para o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e2a9-117">Select a user that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="4e2a9-118">Neste exemplo, moveremos a usuária Sara Davis.</span><span class="sxs-lookup"><span data-stu-id="4e2a9-118">In this example, we will move user Sara Davis.</span></span>

9.  <span data-ttu-id="4e2a9-119">No menu **Ação**, selecione **Mover usuários selecionados para o pool**.</span><span class="sxs-lookup"><span data-stu-id="4e2a9-119">On the **Action** menu, select **Move selected users to pool**.</span></span>

10. <span data-ttu-id="4e2a9-120">Na lista suspensa, selecione o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e2a9-120">From the drop-down list, select the Lync Server 2013 pool.</span></span>

11. <span data-ttu-id="4e2a9-121">Clique em **Ação** e em **Mover usuários selecionados para o pool**.</span><span class="sxs-lookup"><span data-stu-id="4e2a9-121">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="4e2a9-122">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4e2a9-122">Click **OK**.</span></span>
    
    <span data-ttu-id="4e2a9-123">![Configurando o pool de destino na caixa de diálogo mover usuários] (images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "Configurando o pool de destino na caixa de diálogo mover usuários")</span><span class="sxs-lookup"><span data-stu-id="4e2a9-123">![Setting the Destination pool in Move Users dialog](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "Setting the Destination pool in Move Users dialog")</span></span>  

12. <span data-ttu-id="4e2a9-124">Verifique se a coluna do **pool** de registradores do usuário agora contém o pool do Lync Server 2013, que indica que o usuário foi movido com êxito</span><span class="sxs-lookup"><span data-stu-id="4e2a9-124">Verify that the **Registrar pool** column for the user now contains the Lync Server 2013 pool, which indicates that the user has been successfully moved</span></span>

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="4e2a9-125">Para mover um usuário usando o Shell de gerenciamento do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e2a9-125">To move a user by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="4e2a9-126">Abra o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4e2a9-126">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="4e2a9-127">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4e2a9-127">At the command line, type the following:</span></span>
    
        Move-CsLegacyUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  <span data-ttu-id="4e2a9-128">Em seguida, na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4e2a9-128">Next, at the command line, type the following:</span></span>
    
        Get-CsUser -Identity "David Pelton"

4.  <span data-ttu-id="4e2a9-129">A identidade **RegistrarPool** agora aponta para o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e2a9-129">The **RegistrarPool** identity now points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="4e2a9-130">A presença dessa identidade confirma que o usuário foi movido com êxito.</span><span class="sxs-lookup"><span data-stu-id="4e2a9-130">The presence of this identity confirms that the user has been successfully moved.</span></span>
    
    <span data-ttu-id="4e2a9-131">![Saída do cmdlet Get-CsUser com filtro de identidade] (images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Saída do cmdlet Get-CsUser com filtro de identidade")</span><span class="sxs-lookup"><span data-stu-id="4e2a9-131">![Output from Get-CsUser cmdlet with Identity filter](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Output from Get-CsUser cmdlet with Identity filter")</span></span>  
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4e2a9-132">Para obter detalhes sobre o cmdlet <STRONG>Get-CsUser</STRONG> , execute: <STRONG>Get-Help Get-CsUser – detailed</STRONG></span><span class="sxs-lookup"><span data-stu-id="4e2a9-132">For details about the <STRONG>Get-CsUser</STRONG> cmdlet, run: <STRONG>Get-Help Get-CsUser –Detailed</STRONG></span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

