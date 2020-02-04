---
title: 'Lync Server 2013: excluir um intervalo do número de retirada de chamadas em grupo'
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
ms.openlocfilehash: 66b95df76c812b50ff9c220ea208406a5ab7cf2a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741021"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-group-call-pickup-number-range-in-lync-server-2013"></a><span data-ttu-id="6d9fe-102">Excluir um intervalo de números de retirada de chamadas em grupo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d9fe-102">Delete a Group Call Pickup number range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d9fe-103">_**Tópico da última modificação:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="6d9fe-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="6d9fe-104">Use o procedimento a seguir para excluir um intervalo de números de tira de chamada em grupo.</span><span class="sxs-lookup"><span data-stu-id="6d9fe-104">Use the following procedure to delete a Group Call Pickup number range.</span></span>

<div>

## <a name="to-delete-a-call-pickup-group-number-range"></a><span data-ttu-id="6d9fe-105">Para excluir um intervalo de números de grupo de recebimento de chamadas</span><span class="sxs-lookup"><span data-stu-id="6d9fe-105">To delete a call pickup group number range</span></span>

1.  <span data-ttu-id="6d9fe-106">Faça logon no computador em que o Shell de gerenciamento do Lync Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em [permissões de configuração de representante no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="6d9fe-106">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="6d9fe-107">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="6d9fe-107">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="6d9fe-108">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="6d9fe-108">At the command line, type:</span></span>
    
        Remove-CsCallParkOrbit -Identity "<group number range name>" 
    
    <span data-ttu-id="6d9fe-109">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="6d9fe-109">For example:</span></span>
    
        Remove-CsCallParkOrbit -Identity "Redmond call pickup"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6d9fe-110">Para obter detalhes sobre mais opções, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.</span><span class="sxs-lookup"><span data-stu-id="6d9fe-110">For details about more options, see <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6d9fe-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="6d9fe-111">See Also</span></span>


[<span data-ttu-id="6d9fe-112">Criar ou modificar uma faixa de opções do parque de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d9fe-112">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)  


[<span data-ttu-id="6d9fe-113">Remove-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="6d9fe-113">Remove-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit)  
[<span data-ttu-id="6d9fe-114">Get-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="6d9fe-114">Get-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

