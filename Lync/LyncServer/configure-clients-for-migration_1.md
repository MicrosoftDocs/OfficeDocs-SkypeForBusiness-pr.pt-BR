---
title: Configurar os clientes para migração
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure clients for migration
ms:assetid: 8f17862b-d9d1-47f6-b248-51f4710f5030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688130(v=OCS.15)
ms:contentKeyID: 49733729
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99a0b7bfead8f74e27d8539038cf768b1a85b72e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499558"
---
# <a name="configure-clients-for-migration"></a><span data-ttu-id="4d468-102">Configurar os clientes para migração</span><span class="sxs-lookup"><span data-stu-id="4d468-102">Configure clients for migration</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d468-103">_**Última modificação do tópico:** 2013-11-21_</span><span class="sxs-lookup"><span data-stu-id="4d468-103">_**Topic Last Modified:** 2013-11-21_</span></span>

<span data-ttu-id="4d468-104">Este tópico contém as etapas de implantação de cliente recomendadas que você deve tomar antes de migrar para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4d468-104">This topic contains the recommended client deployment steps you should take prior to migrating to Lync Server 2013.</span></span> <span data-ttu-id="4d468-105">Essas alterações de configuração devem ser feitas no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="4d468-105">These configuration changes should be made on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="4d468-106">É muito importante que essas etapas sejam executadas antes da migração.</span><span class="sxs-lookup"><span data-stu-id="4d468-106">It is very important that you perform these steps prior to migrating.</span></span> <span data-ttu-id="4d468-107">Para obter detalhes, consulte [Planning for clients and Devices in Lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).</span><span class="sxs-lookup"><span data-stu-id="4d468-107">For details, see [Planning for clients and devices in Lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).</span></span>

<div>

## <a name="to-configure-clients-prior-to-migration"></a><span data-ttu-id="4d468-108">Para configurar clientes antes da migração</span><span class="sxs-lookup"><span data-stu-id="4d468-108">To configure clients prior to migration</span></span>

1.  <span data-ttu-id="4d468-109">Implantar as atualizações mais recentes do servidor do Office Communications Server 2007 R2, cliente e dispositivo (hotfixes):</span><span class="sxs-lookup"><span data-stu-id="4d468-109">Deploy the most recent Office Communications Server 2007 R2 server, client, and device updates (hotfixes):</span></span>
    
      - [<span data-ttu-id="4d468-110">Aplicar atualizações do Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="4d468-110">Apply Office Communications Server 2007 R2 updates</span></span>](apply-office-communications-server-2007-r2-updates.md)
    
      - [<span data-ttu-id="4d468-111">Descrição do pacote de atualização cumulativa para o Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="4d468-111">Description of the cumulative update package for Communicator 2007 R2</span></span>](https://go.microsoft.com/fwlink/p/?linkid=335808)
    
      - [<span data-ttu-id="4d468-112">Obtendo atualizações de software para dispositivos</span><span class="sxs-lookup"><span data-stu-id="4d468-112">Obtaining Software Updates for Devices</span></span>](https://go.microsoft.com/fwlink/?linkid=335809)

2.  <span data-ttu-id="4d468-113">No Office Communications Server 2007 R2, use filtragem de versão de cliente para permitir que somente os clientes do Office Communications Server 2007 R2 com as atualizações mais recentes instaladas entrem.</span><span class="sxs-lookup"><span data-stu-id="4d468-113">On Office Communications Server 2007 R2, use Client Version Filtering to allow only Office Communications Server 2007 R2 clients with the most current updates installed to sign in.</span></span>

3.  <span data-ttu-id="4d468-114">No Office Communications Server 2007 R2, use filtragem de versão de cliente para bloquear clientes do Lync Server 2013 de entrar.</span><span class="sxs-lookup"><span data-stu-id="4d468-114">On Office Communications Server 2007 R2, use Client Version Filtering to block Lync Server 2013 clients from signing in.</span></span> <span data-ttu-id="4d468-115">Siga as etapas descritas em **Configurando a filtragem de versão do cliente** em [https://go.microsoft.com/fwlink/p/?linkId=202488](https://go.microsoft.com/fwlink/p/?linkid=202488) para adicionar os filtros de versão listados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="4d468-115">Follow the steps described in **Configuring Client Version Filtering** at [https://go.microsoft.com/fwlink/p/?linkId=202488](https://go.microsoft.com/fwlink/p/?linkid=202488) to add the version filters listed in the following table.</span></span> <span data-ttu-id="4d468-116">Para cada filtro de versão, atribua a ação **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="4d468-116">For each version filter, assign the action **Block**.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="4d468-117">Cliente</span><span class="sxs-lookup"><span data-stu-id="4d468-117">Client</span></span></th>
    <th><span data-ttu-id="4d468-118">Cabeçalho do agente do usuário</span><span class="sxs-lookup"><span data-stu-id="4d468-118">User agent header</span></span></th>
    <th><span data-ttu-id="4d468-119">Versão</span><span class="sxs-lookup"><span data-stu-id="4d468-119">Version</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="4d468-120">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="4d468-120">Lync 2013</span></span></p></td>
    <td><p><span data-ttu-id="4d468-121">OC</span><span class="sxs-lookup"><span data-stu-id="4d468-121">OC</span></span></p></td>
    <td><p><span data-ttu-id="4d468-122">15.*.*. \*</span><span class="sxs-lookup"><span data-stu-id="4d468-122">15.*.*.\*</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="4d468-123">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="4d468-123">Lync Web App</span></span></p></td>
    <td><p><span data-ttu-id="4d468-124">CWA</span><span class="sxs-lookup"><span data-stu-id="4d468-124">CWA</span></span></p></td>
    <td><p><span data-ttu-id="4d468-125">5.*.*. \*</span><span class="sxs-lookup"><span data-stu-id="4d468-125">5.*.*.\*</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="4d468-126">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="4d468-126">Lync Phone Edition</span></span></p></td>
    <td><p><span data-ttu-id="4d468-127">OCPhone</span><span class="sxs-lookup"><span data-stu-id="4d468-127">OCPhone</span></span></p></td>
    <td><p><span data-ttu-id="4d468-128">4.*.*. \*</span><span class="sxs-lookup"><span data-stu-id="4d468-128">4.*.*.\*</span></span></p></td>
    </tr>
    </tbody>
    </table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

