---
title: Autorizar conexão com o servidor de borda do Office Communications Server 2007 R2
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Authorize connection to Office Communications Server 2007 R2 Edge Server
ms:assetid: 14f6798a-28d6-4b3d-8734-942192e1bbf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204702(v=OCS.15)
ms:contentKeyID: 48183493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64786c29027c99de2f3b5e01846a5283ec57a084
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42003976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="52baf-102">Autorizar conexão com o servidor de borda do Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="52baf-102">Authorize connection to Office Communications Server 2007 R2 Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52baf-103">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="52baf-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="52baf-104">Para cada servidor front-end do Lync Server 2013 ou servidor Standard Edition no pool piloto, você deve atualizar a lista de servidores internos que estão autorizados a se conectar ao servidor de borda do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="52baf-104">For each Lync Server 2013 Front End Server or Standard Edition server in your pilot pool, you must update the list of internal servers that are authorized to connect to the Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="52baf-105">Sem estas atualizações, conferências A/V (audiovisual) externas para usuários ingressando usando o Servidor de Borda herdado não irão funcionar.</span><span class="sxs-lookup"><span data-stu-id="52baf-105">Without these updates, external audio/visual (A/V) conferencing for users joining by using the legacy Edge Server will not work.</span></span>

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="52baf-106">Para autorizar a conexão com o servidor de borda do Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="52baf-106">To Authorize Connection to Office Communications Server 2007 R2 Edge Server</span></span>

1.  <span data-ttu-id="52baf-107">No servidor de borda do Office Communications Server 2007 R2, no grupo **Ferramentas administrativas** , abra o snap-in **Gerenciamento do computador** .</span><span class="sxs-lookup"><span data-stu-id="52baf-107">From the Office Communications Server 2007 R2 Edge Server, from the **Administrative Tools** group, open the **Computer Management** snap-in.</span></span>

2.  <span data-ttu-id="52baf-108">Na árvore do console, expanda **Serviços e Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="52baf-108">In the console tree, expand **Services and Applications**.</span></span>

3.  <span data-ttu-id="52baf-109">Clique com o botão direito do mouse em **Office Communications Server 2007 R2**e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="52baf-109">Right-click **Office Communications Server 2007 R2**, and then click **Properties**.</span></span>

4.  <span data-ttu-id="52baf-110">Clique na guia **Interno**.</span><span class="sxs-lookup"><span data-stu-id="52baf-110">Click the **Internal** tab.</span></span>

5.  <span data-ttu-id="52baf-111">Em **Adicionar Servidor**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="52baf-111">Under **Add Server**, click **Add**.</span></span>

6.  <span data-ttu-id="52baf-112">Na caixa de diálogo **Adicionar Office Communications Server**, insira as informações apropriadas:</span><span class="sxs-lookup"><span data-stu-id="52baf-112">In the **Add Office Communications Server** dialog box, enter the appropriate information:</span></span>
    
      - <span data-ttu-id="52baf-113">Especifique o FQDN (nome de domínio totalmente qualificado) de cada servidor front-end do Lync Server 2013 ou servidor Standard Edition e o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52baf-113">Specify the fully qualified domain name (FQDN) of each Lync Server 2013 Front End Server or Standard Edition server, and Lync Server 2013 pool.</span></span>
    
      - <span data-ttu-id="52baf-114">Especifique o FQDN do diretor do Lync Server 2013 se você configurou uma rota estática no pool que especifica o próximo computador de salto por seu FQDN.</span><span class="sxs-lookup"><span data-stu-id="52baf-114">Specify the FQDN of the Lync Server 2013 Director if you configured a static route on the pool that specifies the next hop computer by its FQDN.</span></span>

7.  <span data-ttu-id="52baf-115">Após adicionar uma entrada para cada Lync Server 2013, servidor front-end, servidor Standard Edition, pool e diretor, clique em **aplicar** e clique em **OK** para fechar a página Propriedades.</span><span class="sxs-lookup"><span data-stu-id="52baf-115">After you have added an entry for each Lync Server 2013, Front End Server, Standard Edition server, pool, and Director, click **Apply** and then click **OK** to close the Properties page.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

