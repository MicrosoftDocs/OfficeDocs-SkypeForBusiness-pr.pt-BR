---
title: 'Lync Server 2013: (opcional) verificar a implantação do estacionamento de chamada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify Call Park deployment
ms:assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413076(v=OCS.15)
ms:contentKeyID: 48185952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9a22d48e823526f3b4e4b7e6b321ed640328ecd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530808"
---
# <a name="optional-verify-call-park-deployment-in-lync-server-2013"></a><span data-ttu-id="74f7c-102">Opcion Verificar a implantação do estacionamento de chamada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74f7c-102">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74f7c-103">_**Última modificação do tópico:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="74f7c-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="74f7c-104">Após instalar e configurar o estacionamento de chamadas, você precisa verificar a configuração para garantir que o estacionamento e a recuperação de chamadas funcione conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="74f7c-104">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="74f7c-105">No mínimo, verifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="74f7c-105">At minimum, verify the following:</span></span>

  - <span data-ttu-id="74f7c-106">Ligue para um usuário que tem o estacionamento de chamadas habilitado e faça com que o usuário disquem a chamada.</span><span class="sxs-lookup"><span data-stu-id="74f7c-106">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="74f7c-107">Se você habilitou o estacionamento de chamada na política de voz antes de executar esse teste, o usuário que estiver estacionando a chamada precisa sair do Lync Server e entrar novamente para poder ver a opção de estacionamento de chamada na lista de chamadas de transferência.</span><span class="sxs-lookup"><span data-stu-id="74f7c-107">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Lync Server, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span>

    
    </div>

  - <span data-ttu-id="74f7c-108">Disque o número de órbita para recuperar a chamada.</span><span class="sxs-lookup"><span data-stu-id="74f7c-108">Dial the orbit number to retrieve the call.</span></span>

  - <span data-ttu-id="74f7c-p102">Estacione outra chamada, permita que o tempo da chamada estacionada esgote e não pegue o retorno de chamada. Verifique se a chamada que atingiu o tempo limite será corretamente roteada para o destino de fallback especificado para \*\*OnTimeoutURI \*\*.</span><span class="sxs-lookup"><span data-stu-id="74f7c-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

