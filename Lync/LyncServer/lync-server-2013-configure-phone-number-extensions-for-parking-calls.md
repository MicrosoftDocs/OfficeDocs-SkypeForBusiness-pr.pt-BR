---
title: 'Lync Server 2013: configurar extensões de número de telefone para chamadas de estacionamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure phone number extensions for parking calls
ms:assetid: fbf97624-9587-42a6-b276-1b69c574a74d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182611(v=OCS.15)
ms:contentKeyID: 48185980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0a0fd55b851715fe8aef238797392af6317dff0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836338"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-phone-number-extensions-for-parking-calls-in-lync-server-2013"></a><span data-ttu-id="d3a9d-102">Configurar extensões de número de telefone para chamadas com estacionamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3a9d-102">Configure phone number extensions for parking calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3a9d-103">_**Tópico da última modificação:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="d3a9d-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="d3a9d-104">O aplicativo parque de chamadas usa números de extensão na tabela órbita do estacionamento de chamada para estacionar chamadas.</span><span class="sxs-lookup"><span data-stu-id="d3a9d-104">The Call Park application uses extension numbers in the Call Park orbit table to park calls.</span></span> <span data-ttu-id="d3a9d-105">Você precisa configurar a tabela órbita do estacionamento de chamada com os intervalos de números de ramal que a sua organização reserva para fazer chamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="d3a9d-105">You need to configure the Call Park orbit table with the ranges of extension numbers that your organization reserves for parked calls.</span></span> <span data-ttu-id="d3a9d-106">Essas extensões precisam ser extensões virtuais (ou seja, extensões sem usuário ou telefone atribuídas a ela).</span><span class="sxs-lookup"><span data-stu-id="d3a9d-106">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="d3a9d-107">Cada pool do Lync Server onde um aplicativo de estacionamento de chamada é implantado e configurado pode ter um ou mais intervalos de órbita.</span><span class="sxs-lookup"><span data-stu-id="d3a9d-107">Each Lync Server pool where a Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="d3a9d-108">As faixas órbitas devem ser globalmente exclusivas entre a implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d3a9d-108">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d3a9d-109">Você deve marcar a caixa de seleção <STRONG>habilitar o parque de chamadas</STRONG> na sua política de voz para poder usar o parque de chamadas.</span><span class="sxs-lookup"><span data-stu-id="d3a9d-109">You must select the <STRONG>Enable call park</STRONG> check box in your voice policy before you can use Call Park.</span></span> <span data-ttu-id="d3a9d-110">Por padrão, essa opção não é selecionada.</span><span class="sxs-lookup"><span data-stu-id="d3a9d-110">By default, this option is not selected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d3a9d-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="d3a9d-111">In This Section</span></span>

  - [<span data-ttu-id="d3a9d-112">Criar ou modificar uma faixa de opções do parque de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3a9d-112">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

  - [<span data-ttu-id="d3a9d-113">Excluir uma faixa de opções do parque de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3a9d-113">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

