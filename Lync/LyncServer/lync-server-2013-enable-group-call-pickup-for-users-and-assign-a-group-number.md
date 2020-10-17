---
title: 'Lync Server 2013: habilitar o recebimento de chamadas em grupo para usuários e atribuir um número de grupo'
description: 'Lync Server 2013: habilitar o recebimento de chamadas em grupo para usuários e atribuir um número de grupo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Group Call Pickup for users and assign a group number
ms:assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945650(v=OCS.15)
ms:contentKeyID: 51541517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a03fcb20bfd88842dc8b29100b9ece595bf76254
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559637"
---
# <a name="enable-group-call-pickup-for-users-in-lync-server-2013-and-assign-a-group-number"></a><span data-ttu-id="b4456-103">Habilitar o recebimento de chamadas em grupo para usuários no Lync Server 2013 e atribuir um número de grupo</span><span class="sxs-lookup"><span data-stu-id="b4456-103">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4456-104">_**Última modificação do tópico:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="b4456-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="b4456-105">Após adicionar os números de grupo de recebimento de chamada à tabela de órbita de estacionamento de chamada, você atribui os números de grupo aos usuários e habilita o recebimento de chamadas em grupo para eles.</span><span class="sxs-lookup"><span data-stu-id="b4456-105">After you add call pickup group numbers to the call park orbit table, you assign the group numbers to users and enable Group Call Pickup for them.</span></span> <span data-ttu-id="b4456-106">Use a ferramenta de ativação de recursos de extensão secundária (SEFAUtil) para atribuir números de grupo e habilitar o recebimento de chamadas em grupo.</span><span class="sxs-lookup"><span data-stu-id="b4456-106">Use the secondary extension feature activation (SEFAUtil) resource kit tool to assign group numbers and enable Group Call Pickup.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b4456-107">Em uma implantação híbrida, não atribua um grupo de recebimento de chamadas de grupo aos usuários hospedados online.</span><span class="sxs-lookup"><span data-stu-id="b4456-107">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="b4456-108">Os usuários hospedados online não podem participar do recebimento de chamadas em grupo.</span><span class="sxs-lookup"><span data-stu-id="b4456-108">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="b4456-109">Ou seja, suas chamadas não podem ser atendidas por outros usuários e não podem responder chamadas para outros usuários.</span><span class="sxs-lookup"><span data-stu-id="b4456-109">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>



</div>

<div>

## <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="b4456-110">Para atribuir um número de grupo e habilitar o recebimento de chamadas em grupo para um usuário</span><span class="sxs-lookup"><span data-stu-id="b4456-110">To assign a group number and enable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="b4456-111">Faça logon no computador em que você instalou a ferramenta SEFAUtil com direitos de administrador.</span><span class="sxs-lookup"><span data-stu-id="b4456-111">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="b4456-112">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="b4456-112">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="b4456-113">Por exemplo, para atribuir o número de grupo 199 a um usuário:</span><span class="sxs-lookup"><span data-stu-id="b4456-113">For example, to assign group number 199 to a user:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b4456-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="b4456-114">See Also</span></span>


[<span data-ttu-id="b4456-115">Desabilitar o recebimento de chamadas em grupo para usuários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4456-115">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

