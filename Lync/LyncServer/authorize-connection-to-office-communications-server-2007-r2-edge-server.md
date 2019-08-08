---
title: Autorizar conexão com o servidor de borda do Office Communications Server 2007 R2
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Authorize connection to Office Communications Server 2007 R2 Edge Server
ms:assetid: 14f6798a-28d6-4b3d-8734-942192e1bbf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204702(v=OCS.15)
ms:contentKeyID: 48183493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04bc5d92b45f65c864da046951ce7ebd42155ed2
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36232923"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="c382a-102">Autorizar conexão com o servidor de borda do Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="c382a-102">Authorize connection to Office Communications Server 2007 R2 Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c382a-103">_**Tópico da última modificação:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="c382a-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="c382a-104">Para cada servidor front-end do Lync Server 2013 ou Standard Edition no pool piloto, você deve atualizar a lista de servidores internos que têm autorização para se conectar ao servidor do Office Communications Server 2007 R2 Edge Server.</span><span class="sxs-lookup"><span data-stu-id="c382a-104">For each Lync Server 2013 Front End Server or Standard Edition server in your pilot pool, you must update the list of internal servers that are authorized to connect to the Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="c382a-105">Sem essas atualizações, a conferência de áudio/visual (A/V) externa para usuários que ingressarem usando o servidor de borda herdada não funcionará.</span><span class="sxs-lookup"><span data-stu-id="c382a-105">Without these updates, external audio/visual (A/V) conferencing for users joining by using the legacy Edge Server will not work.</span></span>

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="c382a-106">Para autorizar a conexão com o servidor de borda do Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="c382a-106">To Authorize Connection to Office Communications Server 2007 R2 Edge Server</span></span>

1.  <span data-ttu-id="c382a-107">No servidor do Office Communications Server 2007 R2 Edge, a partir do grupo **Ferramentas administrativas** , abra o snap-in **Gerenciamento do computador** .</span><span class="sxs-lookup"><span data-stu-id="c382a-107">From the Office Communications Server 2007 R2 Edge Server, from the **Administrative Tools** group, open the **Computer Management** snap-in.</span></span>

2.  <span data-ttu-id="c382a-108">Na árvore de console, expanda **serviços e aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="c382a-108">In the console tree, expand **Services and Applications**.</span></span>

3.  <span data-ttu-id="c382a-109">Clique com o botão direito do mouse em **Office Communications Server 2007 R2**e, em seguida, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="c382a-109">Right-click **Office Communications Server 2007 R2**, and then click **Properties**.</span></span>

4.  <span data-ttu-id="c382a-110">Clique na guia **interno** .</span><span class="sxs-lookup"><span data-stu-id="c382a-110">Click the **Internal** tab.</span></span>

5.  <span data-ttu-id="c382a-111">Em **Adicionar servidor**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c382a-111">Under **Add Server**, click **Add**.</span></span>

6.  <span data-ttu-id="c382a-112">Na caixa de diálogo **Adicionar o Office Communications Server** , insira as informações apropriadas:</span><span class="sxs-lookup"><span data-stu-id="c382a-112">In the **Add Office Communications Server** dialog box, enter the appropriate information:</span></span>
    
      - <span data-ttu-id="c382a-113">Especifique o nome de domínio totalmente qualificado (FQDN) de cada servidor front-end do Lync Server 2013 ou do servidor Standard Edition e do Lync Server 2013 pool.</span><span class="sxs-lookup"><span data-stu-id="c382a-113">Specify the fully qualified domain name (FQDN) of each Lync Server 2013 Front End Server or Standard Edition server, and Lync Server 2013 pool.</span></span>
    
      - <span data-ttu-id="c382a-114">Especifique o FQDN do diretor do Lync Server 2013 se você configurou uma rota estática no pool que especifica o próximo nó do computador pelo seu FQDN.</span><span class="sxs-lookup"><span data-stu-id="c382a-114">Specify the FQDN of the Lync Server 2013 Director if you configured a static route on the pool that specifies the next hop computer by its FQDN.</span></span>

7.  <span data-ttu-id="c382a-115">Depois de adicionar uma entrada para cada Lync Server 2013, servidor front-end, servidor Standard Edition, pool e diretor, clique em **aplicar** e, em seguida, clique em **OK** para fechar a página Propriedades.</span><span class="sxs-lookup"><span data-stu-id="c382a-115">After you have added an entry for each Lync Server 2013, Front End Server, Standard Edition server, pool, and Director, click **Apply** and then click **OK** to close the Properties page.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

