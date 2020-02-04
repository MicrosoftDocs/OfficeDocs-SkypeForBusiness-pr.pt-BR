---
title: 'Lync Server 2013: exibir atualizações de software para dispositivos em sua organização'
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
ms.openlocfilehash: d9a969aac4559f02ee7d05f36bece84e40f65aca
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757415"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-software-updates-for-devices-in-lync-server-2013"></a><span data-ttu-id="c8dbe-102">Exibir atualizações de software para dispositivos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8dbe-102">View software updates for devices in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8dbe-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c8dbe-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c8dbe-104">Com o Lync Server 2013, você usa o serviço Web de atualização de dispositivo para exibir e gerenciar atualizações de software para os dispositivos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="c8dbe-104">With Lync Server 2013, you use Device Update Web service to view and manage software updates for your organization’s devices.</span></span> <span data-ttu-id="c8dbe-105">Essas atualizações estão disponíveis em arquivos. cab (Cabinet) a partir do website de suporte [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091)da Microsoft em.</span><span class="sxs-lookup"><span data-stu-id="c8dbe-105">These updates are available in .cab (cabinet) files from the Microsoft Support website at [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091).</span></span> <span data-ttu-id="c8dbe-106">Depois de baixar o arquivo. cab, execute o cmdlet **Import-CSDeviceUpdate** para importar as regras de atualização de dispositivo do arquivo. cab.</span><span class="sxs-lookup"><span data-stu-id="c8dbe-106">After you download the .cab file, run the **Import-CSDeviceUpdate** cmdlet to import the device update rules from the .cab file.</span></span> <span data-ttu-id="c8dbe-107">Para obter detalhes sobre o cmdlet **Import-CSDeviceUpdate** , consulte [importar-CSDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) na documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c8dbe-107">For details about the **Import-CSDeviceUpdate** cmdlet, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) in the Lync Server Management Shell documentation.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="c8dbe-108">Antes de implantar uma nova atualização em sua organização, verifique se ela funciona corretamente em um dispositivo de teste.</span><span class="sxs-lookup"><span data-stu-id="c8dbe-108">Before deploying a new update to your organization, verify that it functions correctly on a test device.</span></span>



</div>

<div>

## <a name="to-view-software-updates-for-uc-devices"></a><span data-ttu-id="c8dbe-109">Para exibir atualizações de software para dispositivos de comunicação unificada</span><span class="sxs-lookup"><span data-stu-id="c8dbe-109">To view software updates for UC devices</span></span>

1.  <span data-ttu-id="c8dbe-110">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="c8dbe-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c8dbe-111">No site de suporte da Microsoft [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091)em, baixe o arquivo. cab para um local em um computador com o Lync Server 2013 (por exemplo\\,\\C: atualiza UCUpdates. cab).</span><span class="sxs-lookup"><span data-stu-id="c8dbe-111">From the Microsoft Support website at [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091), download the .cab file to a location on a Lync Server 2013 computer (for example, C:\\Updates\\UCUpdates.cab).</span></span>

3.  <span data-ttu-id="c8dbe-112">Importe as regras de atualização de dispositivo do arquivo\\C\\: updates UCUpdates. cab executando um dos seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="c8dbe-112">Import the device update rules from the C:\\Updates\\UCUpdates.cab file by running one of the following cmdlets:</span></span>
    
      - <span data-ttu-id="c8dbe-113">Se o arquivo. cab estiver localizado no mesmo computador que está executando o serviço a ser atualizado (serviço: Redmond-websvc-2), execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c8dbe-113">If the .cab file is located on the same computer as the one running the service to be updated (service:Redmond-websvc-2), run the following cmdlet:</span></span>
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - <span data-ttu-id="c8dbe-114">Se o arquivo. cab estiver localizado em um computador diferente do que o que está executando o serviço a ser atualizado (serviço: Redmond-websvc-3), execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c8dbe-114">If the .cab file is located on a different computer than the one running the service to be updated (service:Redmond-websvc-3), run the following cmdlet:</span></span>
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  <span data-ttu-id="c8dbe-115">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c8dbe-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c8dbe-116">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c8dbe-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

5.  <span data-ttu-id="c8dbe-117">Na barra de navegação à esquerda, clique em **clientes**e em **atualização de dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="c8dbe-117">In the left navigation bar, click **Clients**, and then click **Device Update**.</span></span>

6.  <span data-ttu-id="c8dbe-118">Na página **atualização do dispositivo** , clique em uma atualização na lista e siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="c8dbe-118">On the **Device Update** page, click an update in the list, and then do one of the following:</span></span>
    
      - <span data-ttu-id="c8dbe-119">**Cancelar uma atualização pendente.**</span><span class="sxs-lookup"><span data-stu-id="c8dbe-119">**Cancel a pending update.**</span></span> <span data-ttu-id="c8dbe-120">Para impedir que a atualização selecionada seja implantada nos dispositivos da sua organização, clique no menu **ação** e, em seguida, clique em **cancelar atualizações pendentes**.</span><span class="sxs-lookup"><span data-stu-id="c8dbe-120">To prevent the selected update from being deployed to your organization’s devices, click the **Action** menu, and then click **Cancel pending updates**.</span></span>
    
      - <span data-ttu-id="c8dbe-121">**Aprove uma atualização.**</span><span class="sxs-lookup"><span data-stu-id="c8dbe-121">**Approve an update.**</span></span> <span data-ttu-id="c8dbe-122">Para permitir que a atualização selecionada seja implantada nos dispositivos da sua organização, clique no menu **ação** e, em seguida, clique em **aprovar**.</span><span class="sxs-lookup"><span data-stu-id="c8dbe-122">To allow the selected update to be deployed to your organization’s devices, click the **Action** menu, and then click **Approve**.</span></span>
    
      - <span data-ttu-id="c8dbe-123">**Restaurar uma atualização.**</span><span class="sxs-lookup"><span data-stu-id="c8dbe-123">**Restore an update.**</span></span> <span data-ttu-id="c8dbe-124">Para permitir que uma atualização aprovada anteriormente seja implantada nos dispositivos da sua organização, clique no menu **ação** e, em seguida, clique em **restaurar**.</span><span class="sxs-lookup"><span data-stu-id="c8dbe-124">To allow a previously approved update to be deployed to your organization’s devices, click the **Action** menu, and then click **Restore**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c8dbe-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="c8dbe-125">See Also</span></span>


[<span data-ttu-id="c8dbe-126">Gerenciando dispositivos, telefones e aplicativos do cliente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8dbe-126">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

