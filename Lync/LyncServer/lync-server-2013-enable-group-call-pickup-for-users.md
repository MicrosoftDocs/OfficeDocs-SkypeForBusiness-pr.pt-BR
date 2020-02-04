---
title: 'Lync Server 2013: habilitar o recebimento de chamadas em grupo para usuários'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Group Call Pickup for users
ms:assetid: 20ec5f41-6ba2-4156-82ed-b91d05b62a6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945620(v=OCS.15)
ms:contentKeyID: 51541457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fc2f513960371d0115b63260d35180f319bd923
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736261"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013"></a><span data-ttu-id="3a27d-102">Habilitar a retirada de chamadas em grupo para usuários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a27d-102">Enable Group Call Pickup for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a27d-103">_**Tópico da última modificação:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="3a27d-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="3a27d-104">Use a ferramenta kit de recursos do SEFAUtil para habilitar o recurso de recebimento de chamadas em grupo para usuários.</span><span class="sxs-lookup"><span data-stu-id="3a27d-104">Use the SEFAUtil resource kit tool to enable Group Call Pickup for users.</span></span> <span data-ttu-id="3a27d-105">Os usuários devem receber um número de grupo com o tipo GroupPickup na tabela órbita do estacionamento de chamada para que a retirada de chamadas em grupo seja habilitada.</span><span class="sxs-lookup"><span data-stu-id="3a27d-105">Users must be assigned a group number with type GroupPickup in the call park orbit table to have Group Call Pickup enabled.</span></span> <span data-ttu-id="3a27d-106">Você atribui um número de grupo de recebimento de chamada e habilita o recebimento de chamadas em grupo ao mesmo tempo usando o parâmetro/enablegrouppickup quando você executa o SEFAUtil. exe.</span><span class="sxs-lookup"><span data-stu-id="3a27d-106">You assign a call pickup group number and enable Group Call Pickup at the same time by using the /enablegrouppickup parameter when you run SEFAUtil.exe.</span></span>

<div>

## <a name="to-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="3a27d-107">Para habilitar a retirada de chamadas em grupo para um usuário</span><span class="sxs-lookup"><span data-stu-id="3a27d-107">To enable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="3a27d-108">Realize logon no computador em que você instalou a ferramenta SEFAUtil com direitos de administrador.</span><span class="sxs-lookup"><span data-stu-id="3a27d-108">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="3a27d-109">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="3a27d-109">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="3a27d-110">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3a27d-110">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3a27d-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="3a27d-111">See Also</span></span>


[<span data-ttu-id="3a27d-112">Atribuir números de recebimento de chamadas em grupo aos usuários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a27d-112">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[<span data-ttu-id="3a27d-113">Desabilitar a retirada de chamadas em grupo para usuários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a27d-113">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

