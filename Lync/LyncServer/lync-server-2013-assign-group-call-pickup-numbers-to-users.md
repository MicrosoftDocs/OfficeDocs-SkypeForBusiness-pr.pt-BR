---
title: 'Lync Server 2013: atribuir números de recebimento de chamadas de grupo aos usuários'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign Group Call Pickup numbers to users
ms:assetid: b8e79275-8e7e-4799-b908-f34f61df22f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945647(v=OCS.15)
ms:contentKeyID: 51541508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 172a91c1a1417db6ffd938a48360c7d4bce3533c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149270"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assign-group-call-pickup-numbers-to-users-in-lync-server-2013"></a><span data-ttu-id="faf93-102">Atribuir números de recebimento de chamadas de grupo aos usuários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="faf93-102">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="faf93-103">_**Última modificação do tópico:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="faf93-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="faf93-104">Após adicionar os números de grupo de recebimento de chamada de grupo à tabela de órbita de estacionamento de chamada, você pode atribuir os grupos aos usuários.</span><span class="sxs-lookup"><span data-stu-id="faf93-104">After you add Group Call Pickup group numbers to the call park orbit table, you can assign the groups to users.</span></span> <span data-ttu-id="faf93-105">Use a ferramenta de ativação de recursos de extensão secundária (SEFAUtil) para atribuir grupos de recebimento de chamadas aos usuários.</span><span class="sxs-lookup"><span data-stu-id="faf93-105">Use the secondary extension feature activation (SEFAUtil ) resource kit tool to assign call pickup groups to users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="faf93-106">Em uma implantação híbrida, não atribua um grupo de recebimento de chamadas de grupo aos usuários hospedados online.</span><span class="sxs-lookup"><span data-stu-id="faf93-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="faf93-107">Os usuários hospedados online não podem participar do recebimento de chamadas em grupo.</span><span class="sxs-lookup"><span data-stu-id="faf93-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="faf93-108">Ou seja, suas chamadas não podem ser atendidas por outros usuários e não podem responder chamadas para outros usuários.</span><span class="sxs-lookup"><span data-stu-id="faf93-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>



</div>

<div>

## <a name="to-assign-a-group-call-pickup-group-to-a-user"></a><span data-ttu-id="faf93-109">Para atribuir um grupo de recebimento de chamadas de grupo a um usuário</span><span class="sxs-lookup"><span data-stu-id="faf93-109">To assign a Group Call Pickup group to a user</span></span>

1.  <span data-ttu-id="faf93-110">Faça logon no computador em que você instalou a ferramenta SEFAUtil com direitos de administrador.</span><span class="sxs-lookup"><span data-stu-id="faf93-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="faf93-111">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="faf93-111">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="faf93-112">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="faf93-112">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="faf93-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="faf93-113">See Also</span></span>


[<span data-ttu-id="faf93-114">Habilitar o recebimento de chamadas em grupo para usuários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="faf93-114">Enable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-enable-group-call-pickup-for-users.md)  
[<span data-ttu-id="faf93-115">Desabilitar o recebimento de chamadas em grupo para usuários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="faf93-115">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

