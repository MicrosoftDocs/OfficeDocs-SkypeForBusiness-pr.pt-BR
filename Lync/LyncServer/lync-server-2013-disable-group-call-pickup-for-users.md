---
title: 'Lync Server 2013: desabilitar o recebimento de chamadas em grupo para usuários'
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
ms.openlocfilehash: c03242cf0b3521dada944ccaba30946306c1ff24
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-group-call-pickup-for-users-in-lync-server-2013"></a><span data-ttu-id="e8a50-102">Desabilitar o recebimento de chamadas em grupo para usuários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8a50-102">Disable Group Call Pickup for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8a50-103">_**Última modificação do tópico:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="e8a50-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="e8a50-104">Use o procedimento a seguir para desabilitar o recebimento de chamadas em grupo para um usuário.</span><span class="sxs-lookup"><span data-stu-id="e8a50-104">Use the following procedure to disable Group Call Pickup for a user.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e8a50-105">Quando você desabilita o recebimento de chamadas em grupo para um usuário, o número do grupo de recebimento de chamada que foi atribuído ao usuário não é mantido.</span><span class="sxs-lookup"><span data-stu-id="e8a50-105">When you disable Group Call Pickup for a user, the call pickup group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="e8a50-106">Se, posteriormente, você quiser habilitar novamente o recebimento de chamadas em grupo para esse usuário, você deve atribuir o número de grupo de recebimento de chamada novamente com o parâmetro/enablegrouppickup.</span><span class="sxs-lookup"><span data-stu-id="e8a50-106">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the call pickup group number again with the /enablegrouppickup parameter.</span></span>



</div>

<div>

## <a name="to-disable-group-call-pickup-for-a-user"></a><span data-ttu-id="e8a50-107">Para desabilitar o recebimento de chamadas em grupo para um usuário</span><span class="sxs-lookup"><span data-stu-id="e8a50-107">To disable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="e8a50-108">Faça logon no computador em que você instalou a ferramenta SEFAUtil com direitos de administrador.</span><span class="sxs-lookup"><span data-stu-id="e8a50-108">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="e8a50-109">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="e8a50-109">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    <span data-ttu-id="e8a50-110">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e8a50-110">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e8a50-111">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e8a50-111">See Also</span></span>


[<span data-ttu-id="e8a50-112">Atribuir números de recebimento de chamadas de grupo aos usuários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8a50-112">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[<span data-ttu-id="e8a50-113">Habilitar o recebimento de chamadas em grupo para usuários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8a50-113">Enable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-enable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

