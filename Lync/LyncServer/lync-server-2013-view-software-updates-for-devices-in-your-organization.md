---
title: 'Lync Server 2013: exibir atualizações de software para dispositivos em sua organização'
description: 'Lync Server 2013: exibir atualizações de software para dispositivos em sua organização.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View software updates for devices in your organization
ms:assetid: d2cca12b-ed43-4e1f-90ab-d14bca8b482c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182592(v=OCS.15)
ms:contentKeyID: 48185418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 833ab25315847b760271c63bbfca3ba8357e41c1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558827"
---
# <a name="view-software-updates-for-devices-in-lync-server-2013"></a><span data-ttu-id="719e0-103">Exibir atualizações de software para dispositivos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="719e0-103">View software updates for devices in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="719e0-104">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="719e0-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="719e0-105">Com o Lync Server 2013, você usa o serviço Web de atualização de dispositivo para exibir e gerenciar atualizações de software para os dispositivos de sua organização.</span><span class="sxs-lookup"><span data-stu-id="719e0-105">With Lync Server 2013, you use Device Update Web service to view and manage software updates for your organization’s devices.</span></span> <span data-ttu-id="719e0-106">Essas atualizações estão disponíveis em arquivos. cab (Cabinet) no site de suporte da Microsoft em [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091) .</span><span class="sxs-lookup"><span data-stu-id="719e0-106">These updates are available in .cab (cabinet) files from the Microsoft Support website at [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091).</span></span> <span data-ttu-id="719e0-107">Depois de baixar o arquivo. cab, execute o cmdlet **Import-CSDeviceUpdate** para importar as regras de atualização de dispositivo do arquivo. cab.</span><span class="sxs-lookup"><span data-stu-id="719e0-107">After you download the .cab file, run the **Import-CSDeviceUpdate** cmdlet to import the device update rules from the .cab file.</span></span> <span data-ttu-id="719e0-108">Para obter detalhes sobre o cmdlet **Import-CSDeviceUpdate** , consulte [Import-CSDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) na documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="719e0-108">For details about the **Import-CSDeviceUpdate** cmdlet, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) in the Lync Server Management Shell documentation.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="719e0-109">Antes de implantar uma nova atualização em sua organização, verifique se ele funciona corretamente em um dispositivo de teste.</span><span class="sxs-lookup"><span data-stu-id="719e0-109">Before deploying a new update to your organization, verify that it functions correctly on a test device.</span></span>



</div>

<div>

## <a name="to-view-software-updates-for-uc-devices"></a><span data-ttu-id="719e0-110">Para exibir as atualizações de software para dispositivos UC</span><span class="sxs-lookup"><span data-stu-id="719e0-110">To view software updates for UC devices</span></span>

1.  <span data-ttu-id="719e0-111">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="719e0-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="719e0-112">No site de suporte da Microsoft em [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091) , baixe o arquivo. cab para um local em um computador do Lync Server 2013 (por exemplo, C: \\ atualiza \\UCUpdates.cab).</span><span class="sxs-lookup"><span data-stu-id="719e0-112">From the Microsoft Support website at [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091), download the .cab file to a location on a Lync Server 2013 computer (for example, C:\\Updates\\UCUpdates.cab).</span></span>

3.  <span data-ttu-id="719e0-113">Importe as regras de atualização de dispositivo do arquivo C: \\ updates \\UCUpdates.cab executando um dos seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="719e0-113">Import the device update rules from the C:\\Updates\\UCUpdates.cab file by running one of the following cmdlets:</span></span>
    
      - <span data-ttu-id="719e0-114">Se o arquivo. cab estiver localizado no mesmo computador que está executando o serviço a ser atualizado (serviço: Redmond-websvc-2), execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="719e0-114">If the .cab file is located on the same computer as the one running the service to be updated (service:Redmond-websvc-2), run the following cmdlet:</span></span>
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - <span data-ttu-id="719e0-115">Se o arquivo. cab estiver localizado em um computador diferente do que está executando o serviço a ser atualizado (serviço: Redmond-websvc-3), execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="719e0-115">If the .cab file is located on a different computer than the one running the service to be updated (service:Redmond-websvc-3), run the following cmdlet:</span></span>
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  <span data-ttu-id="719e0-116">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="719e0-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="719e0-117">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="719e0-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

5.  <span data-ttu-id="719e0-118">Na barra de navegação esquerda, clique em **Cliente** e em **Atualização de Dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="719e0-118">In the left navigation bar, click **Clients**, and then click **Device Update**.</span></span>

6.  <span data-ttu-id="719e0-119">Na página **Atualização de Dispositivo**, clique em uma atualização na lista e execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="719e0-119">On the **Device Update** page, click an update in the list, and then do one of the following:</span></span>
    
      - <span data-ttu-id="719e0-p103">**Cancelar uma atualização pendente.** Para impedir que a atualização selecionada seja implantada nos dispositivos de sua organização, clique no menu **Ação** e clique em **Cancelar atualizações pendentes**.</span><span class="sxs-lookup"><span data-stu-id="719e0-p103">**Cancel a pending update.** To prevent the selected update from being deployed to your organization’s devices, click the **Action** menu, and then click **Cancel pending updates**.</span></span>
    
      - <span data-ttu-id="719e0-p104">**Aprovar uma atualização.** Para permitir que a atualização selecionada seja implantada em dispositivos de sua organização, clique no menu **Ação** e, em seguida, clique **Aprovar**.</span><span class="sxs-lookup"><span data-stu-id="719e0-p104">**Approve an update.** To allow the selected update to be deployed to your organization’s devices, click the **Action** menu, and then click **Approve**.</span></span>
    
      - <span data-ttu-id="719e0-p105">**Restaurar uma atualização.** Para permitir que uma atualização aprovada anteriormente seja implantada nos dispositivos de sua organização, clique no menu **Ação** e, em seguida, clique **Restaurar**.</span><span class="sxs-lookup"><span data-stu-id="719e0-p105">**Restore an update.** To allow a previously approved update to be deployed to your organization’s devices, click the **Action** menu, and then click **Restore**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="719e0-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="719e0-126">See Also</span></span>


[<span data-ttu-id="719e0-127">Gerenciando dispositivos, telefones e aplicativos cliente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="719e0-127">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

