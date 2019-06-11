---
title: 'Lync Server 2013: remover arquivos de atualização de dispositivo não associados a um dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remove Device Update files not associated with a device
ms:assetid: ecebbf73-b456-4990-a91d-308b84d39404
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994084(v=OCS.15)
ms:contentKeyID: 51803996
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ea26cd20826ed099e27c7287c53cc7ca79bef9c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823123"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-device-update-files-not-associated-with-a-device-in-lync-server-2013"></a><span data-ttu-id="5cadc-102">Remover arquivos de atualização de dispositivo não associados a um dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5cadc-102">Remove Device Update files not associated with a device in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5cadc-103">_**Tópico da última modificação:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="5cadc-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="5cadc-104">Sempre que novas atualizações de dispositivos são carregadas no sistema, uma regra de atualização de dispositivo correspondente é criada.</span><span class="sxs-lookup"><span data-stu-id="5cadc-104">Each time new device updates are uploaded to the system, a corresponding device update rule is created.</span></span> <span data-ttu-id="5cadc-105">Por padrão, essas novas regras de atualização de dispositivo são atribuídas ao estado pendente.</span><span class="sxs-lookup"><span data-stu-id="5cadc-105">By default, these new device update rules are assigned to the Pending state.</span></span> <span data-ttu-id="5cadc-106">Isso significa que as regras podem ser baixadas e instaladas em dispositivos de teste, mas não em dispositivos de produção, que permitem testar as atualizações antes de disponibilizá-las para os usuários.</span><span class="sxs-lookup"><span data-stu-id="5cadc-106">This means that the rules can be downloaded and installed on test devices, but not on production devices, which enables you to test the updates before making them available to users.</span></span> <span data-ttu-id="5cadc-107">Com base nos testes, você pode aceitar e implantar ou rejeitar e excluir a atualização.</span><span class="sxs-lookup"><span data-stu-id="5cadc-107">Based on the tests, you either accept and deploy or reject and delete the update.</span></span> <span data-ttu-id="5cadc-108">Quando você rejeita uma atualização, a atualização do dispositivo é desassociada da sua regra de atualização de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5cadc-108">When you reject an update, the device update is disassociated from its device update rule.</span></span>

<div>


<span data-ttu-id="5cadc-109">Os arquivos de atualização de dispositivo que não estão mais associados a um dispositivo podem ser removidos usando-se o Windows PowerShell e o cmdlet **Clear-CsDeviceUpdateFile** .</span><span class="sxs-lookup"><span data-stu-id="5cadc-109">Device update files that are no longer associated with a device can be removed by using Windows PowerShell and the **Clear-CsDeviceUpdateFile** cmdlet.</span></span> <span data-ttu-id="5cadc-110">Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5cadc-110">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5cadc-111">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="5cadc-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


  - <span data-ttu-id="5cadc-112">Por exemplo, o comando a seguir remove todas as regras de atualização de dispositivo no servidor Web atl-cs-001.litwareinc.com que não estão mais associadas a um dispositivo:</span><span class="sxs-lookup"><span data-stu-id="5cadc-112">For example, the following command removes any device update rules on the Web server atl-cs-001.litwareinc.com that are no longer associated with a device:</span></span>
    
        Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"

</div>

<span data-ttu-id="5cadc-113">Para obter detalhes, consulte o tópico da ajuda para o cmdlet [Clear-CsDeviceUpdateFile](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile) .</span><span class="sxs-lookup"><span data-stu-id="5cadc-113">For details, see the Help topic for the [Clear-CsDeviceUpdateFile](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

