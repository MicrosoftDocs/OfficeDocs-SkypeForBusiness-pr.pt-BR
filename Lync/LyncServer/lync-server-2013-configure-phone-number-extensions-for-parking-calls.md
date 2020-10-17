---
title: 'Lync Server 2013: configurar extensões de números de telefone para estacionamento de chamadas'
description: 'Lync Server 2013: configurar extensões de números de telefone para estacionamento de chamadas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure phone number extensions for parking calls
ms:assetid: fbf97624-9587-42a6-b276-1b69c574a74d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182611(v=OCS.15)
ms:contentKeyID: 48185980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6219e04243d0c19bc37251f7d113f7ebdd09fb72
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548827"
---
# <a name="configure-phone-number-extensions-for-parking-calls-in-lync-server-2013"></a><span data-ttu-id="14868-103">Configurar extensões de número de telefone para estacionamento de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14868-103">Configure phone number extensions for parking calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14868-104">_**Última modificação do tópico:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="14868-104">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="14868-105">O aplicativo de estacionamento de chamada usa números de ramal na tabela de órbita de estacionamento de chamada para estacionar chamadas.</span><span class="sxs-lookup"><span data-stu-id="14868-105">The Call Park application uses extension numbers in the Call Park orbit table to park calls.</span></span> <span data-ttu-id="14868-106">Você precisa configurar a tabela de órbita de estacionamento de chamada com os intervalos de números de ramal que sua organização reserva para chamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="14868-106">You need to configure the Call Park orbit table with the ranges of extension numbers that your organization reserves for parked calls.</span></span> <span data-ttu-id="14868-107">Essas extensões precisam ser extensões virtuais (ou seja, extensões com nenhum usuário ou telefone atribuído a eles).</span><span class="sxs-lookup"><span data-stu-id="14868-107">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="14868-108">Cada pool do Lync Server onde um aplicativo de estacionamento de chamada é implantado e configurado pode ter um ou mais intervalos de órbita.</span><span class="sxs-lookup"><span data-stu-id="14868-108">Each Lync Server pool where a Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="14868-109">Os intervalos de órbita devem ser globalmente exclusivos na implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="14868-109">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="14868-110">Você deve marcar a caixa de seleção <STRONG>habilitar estacionamento de chamadas</STRONG> em sua política de voz antes de poder usar o estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="14868-110">You must select the <STRONG>Enable call park</STRONG> check box in your voice policy before you can use Call Park.</span></span> <span data-ttu-id="14868-111">Por padrão, essa opção não está selecionada.</span><span class="sxs-lookup"><span data-stu-id="14868-111">By default, this option is not selected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="14868-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="14868-112">In This Section</span></span>

  - [<span data-ttu-id="14868-113">Criar ou modificar um intervalo de órbita de estacionamento de chamada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14868-113">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

  - [<span data-ttu-id="14868-114">Excluir um intervalo de órbita de estacionamento de chamada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14868-114">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

