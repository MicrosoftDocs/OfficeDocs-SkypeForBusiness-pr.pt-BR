---
title: Configurar clientes para migração
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure clients for migration
ms:assetid: 8f17862b-d9d1-47f6-b248-51f4710f5030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688130(v=OCS.15)
ms:contentKeyID: 49733729
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 399320fd840391b8d0483b3dc45b62c83311d91f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836082"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-clients-for-migration"></a><span data-ttu-id="33ead-102">Configurar clientes para migração</span><span class="sxs-lookup"><span data-stu-id="33ead-102">Configure clients for migration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33ead-103">_**Tópico da última modificação:** 2013-11-21_</span><span class="sxs-lookup"><span data-stu-id="33ead-103">_**Topic Last Modified:** 2013-11-21_</span></span>

<span data-ttu-id="33ead-104">Este tópico contém as etapas de implantação de cliente recomendadas que você deve tomar antes de migrar para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="33ead-104">This topic contains the recommended client deployment steps you should take prior to migrating to Lync Server 2013.</span></span> <span data-ttu-id="33ead-105">Essas alterações de configuração devem ser feitas no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="33ead-105">These configuration changes should be made on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="33ead-106">É muito importante executar essas etapas antes de migrar.</span><span class="sxs-lookup"><span data-stu-id="33ead-106">It is very important that you perform these steps prior to migrating.</span></span> <span data-ttu-id="33ead-107">Para obter detalhes, consulte [planejando para clientes e dispositivos no Lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).</span><span class="sxs-lookup"><span data-stu-id="33ead-107">For details, see [Planning for clients and devices in Lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).</span></span>

<div>

## <a name="to-configure-clients-prior-to-migration"></a><span data-ttu-id="33ead-108">Para configurar clientes antes da migração</span><span class="sxs-lookup"><span data-stu-id="33ead-108">To configure clients prior to migration</span></span>

1.  <span data-ttu-id="33ead-109">Implantar as atualizações mais recentes do Office Communications Server 2007 R2 Server, do cliente e do dispositivo (hotfixes):</span><span class="sxs-lookup"><span data-stu-id="33ead-109">Deploy the most recent Office Communications Server 2007 R2 server, client, and device updates (hotfixes):</span></span>
    
      - [<span data-ttu-id="33ead-110">Aplicar atualizações do Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="33ead-110">Apply Office Communications Server 2007 R2 updates</span></span>](apply-office-communications-server-2007-r2-updates.md)
    
      - [<span data-ttu-id="33ead-111">Descrição do pacote de atualizações cumulativas do Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="33ead-111">Description of the cumulative update package for Communicator 2007 R2</span></span>](http://go.microsoft.com/fwlink/p/?linkid=335808)
    
      - [<span data-ttu-id="33ead-112">Obtendo atualizações de software para dispositivos</span><span class="sxs-lookup"><span data-stu-id="33ead-112">Obtaining Software Updates for Devices</span></span>](http://go.microsoft.com/fwlink/?linkid=335809)

2.  <span data-ttu-id="33ead-113">No Office Communications Server 2007 R2, use a filtragem de versão do cliente para permitir somente clientes do Office Communications Server 2007 R2 com as atualizações mais recentes instaladas para entrar.</span><span class="sxs-lookup"><span data-stu-id="33ead-113">On Office Communications Server 2007 R2, use Client Version Filtering to allow only Office Communications Server 2007 R2 clients with the most current updates installed to sign in.</span></span>

3.  <span data-ttu-id="33ead-114">No Office Communications Server 2007 R2, use a filtragem de versão do cliente para impedir que os clientes do Lync Server 2013 entrem em entrar.</span><span class="sxs-lookup"><span data-stu-id="33ead-114">On Office Communications Server 2007 R2, use Client Version Filtering to block Lync Server 2013 clients from signing in.</span></span> <span data-ttu-id="33ead-115">Siga as etapas descritas em Configurando a [http://go.microsoft.com/fwlink/p/?linkId=202488](http://go.microsoft.com/fwlink/p/?linkid=202488) filtragem de versão do **cliente** em para adicionar os filtros de versão listados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="33ead-115">Follow the steps described in **Configuring Client Version Filtering** at [http://go.microsoft.com/fwlink/p/?linkId=202488](http://go.microsoft.com/fwlink/p/?linkid=202488) to add the version filters listed in the following table.</span></span> <span data-ttu-id="33ead-116">Para cada filtro de versão, atribua o **bloco**de ação.</span><span class="sxs-lookup"><span data-stu-id="33ead-116">For each version filter, assign the action **Block**.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="33ead-117">Cliente</span><span class="sxs-lookup"><span data-stu-id="33ead-117">Client</span></span></th>
    <th><span data-ttu-id="33ead-118">Cabeçalho do agente do usuário</span><span class="sxs-lookup"><span data-stu-id="33ead-118">User agent header</span></span></th>
    <th><span data-ttu-id="33ead-119">Versão</span><span class="sxs-lookup"><span data-stu-id="33ead-119">Version</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="33ead-120">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="33ead-120">Lync 2013</span></span></p></td>
    <td><p><span data-ttu-id="33ead-121">OC</span><span class="sxs-lookup"><span data-stu-id="33ead-121">OC</span></span></p></td>
    <td><p><span data-ttu-id="33ead-122">15.*.*. \*</span><span class="sxs-lookup"><span data-stu-id="33ead-122">15.*.*.\*</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="33ead-123">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="33ead-123">Lync Web App</span></span></p></td>
    <td><p><span data-ttu-id="33ead-124">CWA</span><span class="sxs-lookup"><span data-stu-id="33ead-124">CWA</span></span></p></td>
    <td><p><span data-ttu-id="33ead-125">5.*.*. \*</span><span class="sxs-lookup"><span data-stu-id="33ead-125">5.*.*.\*</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="33ead-126">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="33ead-126">Lync Phone Edition</span></span></p></td>
    <td><p><span data-ttu-id="33ead-127">OCPhone</span><span class="sxs-lookup"><span data-stu-id="33ead-127">OCPhone</span></span></p></td>
    <td><p><span data-ttu-id="33ead-128">4.*.*. \*</span><span class="sxs-lookup"><span data-stu-id="33ead-128">4.*.*.\*</span></span></p></td>
    </tr>
    </tbody>
    </table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

