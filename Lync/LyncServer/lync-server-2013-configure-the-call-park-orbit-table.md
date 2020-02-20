---
title: 'Lync Server 2013: configurar a tabela de órbita de estacionamento de chamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the Call Park orbit table
ms:assetid: e5cc0c19-7b2c-48e7-a21d-cfb23c842f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399020(v=OCS.15)
ms:contentKeyID: 48185666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03cb3556ab0111d7bc61de6bc0914b5a3514a7cd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145670"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-call-park-orbit-table-in-lync-server-2013"></a><span data-ttu-id="72ab3-102">Configurar a tabela de órbita de estacionamento de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72ab3-102">Configure the Call Park orbit table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72ab3-103">_**Última modificação do tópico:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="72ab3-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="72ab3-104">O estacionamento de chamada usa órbitas para estacionamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="72ab3-104">Call Park uses orbits for parking calls.</span></span> <span data-ttu-id="72ab3-105">Antes que os usuários possam estacionar e recuperar chamadas, você deve configurar a tabela de órbita de estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="72ab3-105">Before users can park and retrieve calls, you must configure the Call Park orbit table.</span></span> <span data-ttu-id="72ab3-106">Você precisa especificar os intervalos de números de ramal (órbitas) que sua organização irá reservar para estacionamento de chamadas e definir o roteamento desses intervalos especificando o pool de estacionamento de chamadas que trata cada intervalo.</span><span class="sxs-lookup"><span data-stu-id="72ab3-106">You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range.</span></span> <span data-ttu-id="72ab3-107">Quando você define intervalos de órbita, a meta é ter órbitas suficientes para que qualquer uma das órbitas não seja reutilizada muito rapidamente, mas não muitas órbitas que você limite o número de extensões disponíveis para usuários ou outros serviços.</span><span class="sxs-lookup"><span data-stu-id="72ab3-107">When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services.</span></span> <span data-ttu-id="72ab3-108">Você pode criar vários intervalos de órbita de estacionamento de chamadas para cada pool do Lync Server onde o aplicativo de estacionamento de chamada é implantado.</span><span class="sxs-lookup"><span data-stu-id="72ab3-108">You can create multiple Call Park orbit ranges for each Lync Server pool where the Call Park application is deployed.</span></span> <span data-ttu-id="72ab3-109">Cada intervalo de órbita de estacionamento de chamadas deve ter um nome globalmente exclusivo e um conjunto exclusivo de extensões.</span><span class="sxs-lookup"><span data-stu-id="72ab3-109">Each Call Park orbit range must have a globally unique name and a unique set of extensions.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="72ab3-p102">Normalmente, um intervalo de órbitas engloba 100 órbitas ou menos. Cada intervalo pode ser muito maior, contanto que seja menor do que o máximo de 10.000 órbitas por intervalo e tenha menos de 50.000 órbitas por pool. Se o intervalo for muito pequeno, as órbitas serão reutilizadas mais rapidamente.</span><span class="sxs-lookup"><span data-stu-id="72ab3-p102">An orbit range typically encompasses 100 or fewer orbits. Each range can be much larger, as long as it is smaller than the maximum of 10,000 orbits per range and you have fewer than 50,000 orbits per pool. If a range is too small, the orbits are reused more quickly.</span></span>



</div>

<span data-ttu-id="72ab3-113">Use blocos de extensões virtuais (extensões sem um usuário ou telefone atribuído a elas) para intervalos de órbita.</span><span class="sxs-lookup"><span data-stu-id="72ab3-113">Use blocks of virtual extensions (extensions that have no user or phone assigned to them) for your orbit ranges.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="72ab3-114">Não há suporte para a atribuição de números DID (discagem direta interna) como números de órbita na tabela de órbita de estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="72ab3-114">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the Call Park orbit table is not supported.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="72ab3-115">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="72ab3-115">In This Section</span></span>

[<span data-ttu-id="72ab3-116">Criar ou modificar um intervalo de órbita de estacionamento de chamada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72ab3-116">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

