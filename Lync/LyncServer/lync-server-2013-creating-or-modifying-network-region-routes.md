---
title: 'Lync Server 2013: Criando ou modificando rotas de região de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network region routes
ms:assetid: 76993daa-76c2-4cec-8363-de8aebef0145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521016(v=OCS.15)
ms:contentKeyID: 48184540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cdc05978b6fb8d81c81995d7b089d14ed4bec3b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516738"
---
# <a name="creating-or-modifying-network-region-routes-in-lync-server-2013"></a><span data-ttu-id="59b84-102">Criando ou modificando rotas de região de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59b84-102">Creating or modifying network region routes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59b84-103">_**Última modificação do tópico:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="59b84-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="59b84-104">Cada região de um configuração de CAC (controle de admissão de chamadas) deve ter alguma forma de acessar todas as outras regiões.</span><span class="sxs-lookup"><span data-stu-id="59b84-104">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="59b84-105">Enquanto os links da região definem limitações nas conexões entre regiões e representam também os links físicos, uma rota determina o caminho vinculado que a conexão percorrerá de uma região a outra.</span><span class="sxs-lookup"><span data-stu-id="59b84-105">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="59b84-106">Você pode usar o painel de controle do Lync Server para configurar rotas de região de rede.</span><span class="sxs-lookup"><span data-stu-id="59b84-106">You can use Lync Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="59b84-107">No painel de controle do Lync Server, você pode criar, modificar ou excluir uma rota de região de rede.</span><span class="sxs-lookup"><span data-stu-id="59b84-107">From Lync Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="59b84-108">Use este tópico para criar ou modificar uma rota de região de rede.</span><span class="sxs-lookup"><span data-stu-id="59b84-108">Use this topic to create or modify a network region route.</span></span> <span data-ttu-id="59b84-109">Para obter detalhes sobre como excluir rotas de região de rede existentes, consulte [excluindo rotas de região de rede existentes no Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md).</span><span class="sxs-lookup"><span data-stu-id="59b84-109">For details about deleting an existing network region routes, see [Deleting existing network region routes in Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md).</span></span>

<div>

## <a name="to-create-a-network-region-route"></a><span data-ttu-id="59b84-110">Para criar uma rota de região de rede</span><span class="sxs-lookup"><span data-stu-id="59b84-110">To create a network region route</span></span>

1.  <span data-ttu-id="59b84-111">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="59b84-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="59b84-112">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="59b84-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="59b84-113">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="59b84-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="59b84-114">Na barra de navegação esquerda, clique em **Configuração de Rede** e em **Rota de Região**.</span><span class="sxs-lookup"><span data-stu-id="59b84-114">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="59b84-115">Na página **Rota de Região**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="59b84-115">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="59b84-116">Em **Nova Rota de Região**, digite um valor no campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="59b84-116">In **New Region Route**, type a value in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="59b84-117">Esse valor deve ser exclusivo na sua implantação do Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="59b84-117">This value must be unique within your Microsoft Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="59b84-118">Na lista suspensa **região de rede \# 1** , selecione uma das duas regiões que serão conectadas por essa rota.</span><span class="sxs-lookup"><span data-stu-id="59b84-118">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="59b84-119">Na lista suspensa **região de rede \# 2** , selecione a outra região para esta rota.</span><span class="sxs-lookup"><span data-stu-id="59b84-119">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="59b84-120">Essa região deve ser diferente da região selecionada para a região de rede \# 1.</span><span class="sxs-lookup"><span data-stu-id="59b84-120">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="59b84-p104">Use a caixa de listagem **Links de região de rede** para adicionar os links de região para a rota. Clique no botão **Adicionar** para exibir a página **Link de Região**. Clique em um link de região para adicionar a esta rota e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="59b84-p104">Use the **Network region links** list box to add region links to the route. Click the **Add** button to display the **Region Link** page. Click a region link to add to this route, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="59b84-124">Continue a clicar no botão <STRONG>Adicionar</STRONG> para adicionar mais links, ou selecione um link e clique em <STRONG>Remover</STRONG> para remover um link.</span><span class="sxs-lookup"><span data-stu-id="59b84-124">Continue to click the <STRONG>Add</STRONG> button to add more links, or select a link and click <STRONG>Remove</STRONG> to remove a link.</span></span>

    
    </div>

9.  <span data-ttu-id="59b84-125">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="59b84-125">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-route"></a><span data-ttu-id="59b84-126">Para modificar uma rota de região de rede</span><span class="sxs-lookup"><span data-stu-id="59b84-126">To modify a network region route</span></span>

1.  <span data-ttu-id="59b84-127">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="59b84-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="59b84-128">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="59b84-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="59b84-129">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="59b84-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="59b84-130">Na barra de navegação esquerda, clique em **Configuração de Rede** e em **Rota de Região**.</span><span class="sxs-lookup"><span data-stu-id="59b84-130">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="59b84-131">Na página **Rota de Região**, clique no roteiro de região que você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="59b84-131">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="59b84-132">No menu **Editar**, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="59b84-132">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="59b84-133">Em **Editar rota de região**, você pode alterar as regiões associadas por essa rota e os links de região associados ao roteiro.</span><span class="sxs-lookup"><span data-stu-id="59b84-133">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="59b84-134">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="59b84-134">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="59b84-135">Confira também</span><span class="sxs-lookup"><span data-stu-id="59b84-135">See Also</span></span>


[<span data-ttu-id="59b84-136">Excluindo rotas de região de rede existentes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59b84-136">Deleting existing network region routes in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

