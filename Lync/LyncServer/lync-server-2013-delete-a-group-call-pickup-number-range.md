---
title: 'Lync Server 2013: excluir um grupo intervalo de números de recebimento de chamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a Group Call Pickup number range
ms:assetid: 521891f3-7a5d-45de-92dc-d57025453159
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945629(v=OCS.15)
ms:contentKeyID: 51541475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 179bde8b8e23cc21fb95fa93e3c6cbeb7f381630
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006327"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-group-call-pickup-number-range-in-lync-server-2013"></a><span data-ttu-id="1d4d4-102">Excluir um intervalo de números de recebimento de chamadas em grupo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d4d4-102">Delete a Group Call Pickup number range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d4d4-103">_**Última modificação do tópico:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="1d4d4-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="1d4d4-104">Use o procedimento a seguir para excluir um intervalo de números de recebimento de chamadas em grupo.</span><span class="sxs-lookup"><span data-stu-id="1d4d4-104">Use the following procedure to delete a Group Call Pickup number range.</span></span>

<div>

## <a name="to-delete-a-call-pickup-group-number-range"></a><span data-ttu-id="1d4d4-105">Para excluir um intervalo de números do grupo de recebimento de chamadas</span><span class="sxs-lookup"><span data-stu-id="1d4d4-105">To delete a call pickup group number range</span></span>

1.  <span data-ttu-id="1d4d4-106">Faça logon no computador onde o Shell de gerenciamento do Lync Server está instalado como um membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="1d4d4-106">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="1d4d4-107">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="1d4d4-107">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="1d4d4-108">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="1d4d4-108">At the command line, type:</span></span>
    
        Remove-CsCallParkOrbit -Identity "<group number range name>" 
    
    <span data-ttu-id="1d4d4-109">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1d4d4-109">For example:</span></span>
    
        Remove-CsCallParkOrbit -Identity "Redmond call pickup"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1d4d4-110">Para obter detalhes sobre mais opções, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.</span><span class="sxs-lookup"><span data-stu-id="1d4d4-110">For details about more options, see <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1d4d4-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="1d4d4-111">See Also</span></span>


[<span data-ttu-id="1d4d4-112">Criar ou modificar um intervalo de órbita de estacionamento de chamada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d4d4-112">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)  


[<span data-ttu-id="1d4d4-113">Remove-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="1d4d4-113">Remove-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit)  
[<span data-ttu-id="1d4d4-114">Get-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="1d4d4-114">Get-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

