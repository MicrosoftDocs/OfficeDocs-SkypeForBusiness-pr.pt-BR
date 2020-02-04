---
title: 'Lync Server 2013: desabilitar a retirada de chamadas em grupo para usuários'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable Group Call Pickup for users
ms:assetid: 91b06f9e-2840-45a2-bbb3-6a29179b9a9f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945638(v=OCS.15)
ms:contentKeyID: 51541492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7e47b5c3b12997bd05f3721555a5dfdfe692bbc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-group-call-pickup-for-users-in-lync-server-2013"></a><span data-ttu-id="a7e3f-102">Desabilitar a retirada de chamadas em grupo para usuários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7e3f-102">Disable Group Call Pickup for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7e3f-103">_**Tópico da última modificação:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="a7e3f-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="a7e3f-104">Use o procedimento a seguir para desabilitar o recebimento de chamadas em grupo para um usuário.</span><span class="sxs-lookup"><span data-stu-id="a7e3f-104">Use the following procedure to disable Group Call Pickup for a user.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a7e3f-105">Quando você desativa o recurso de recebimento de chamadas em grupo para um usuário, o número do grupo de recebimento de chamadas atribuído ao usuário não é mantido.</span><span class="sxs-lookup"><span data-stu-id="a7e3f-105">When you disable Group Call Pickup for a user, the call pickup group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="a7e3f-106">Se, em seguida, você quiser reabilitar o recebimento de chamadas em grupo para esse usuário, será necessário atribuir novamente o número do grupo de recebimento de chamada com o parâmetro/enablegrouppickup.</span><span class="sxs-lookup"><span data-stu-id="a7e3f-106">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the call pickup group number again with the /enablegrouppickup parameter.</span></span>



</div>

<div>

## <a name="to-disable-group-call-pickup-for-a-user"></a><span data-ttu-id="a7e3f-107">Para desabilitar a retirada de chamadas em grupo para um usuário</span><span class="sxs-lookup"><span data-stu-id="a7e3f-107">To disable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="a7e3f-108">Realize logon no computador em que você instalou a ferramenta SEFAUtil com direitos de administrador.</span><span class="sxs-lookup"><span data-stu-id="a7e3f-108">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="a7e3f-109">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="a7e3f-109">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    <span data-ttu-id="a7e3f-110">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a7e3f-110">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a7e3f-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="a7e3f-111">See Also</span></span>


[<span data-ttu-id="a7e3f-112">Atribuir números de recebimento de chamadas em grupo aos usuários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7e3f-112">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[<span data-ttu-id="a7e3f-113">Habilitar a retirada de chamadas em grupo para usuários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7e3f-113">Enable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-enable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

