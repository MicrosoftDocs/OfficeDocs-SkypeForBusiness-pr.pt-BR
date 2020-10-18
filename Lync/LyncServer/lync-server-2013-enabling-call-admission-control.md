---
title: 'Lync Server 2013: habilitar controle de admissão de chamadas'
description: 'Lync Server 2013: habilitando controle de admissão de chamadas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling call admission control
ms:assetid: 015f5c8f-2f90-4b9e-8149-b33767e90582
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520942(v=OCS.15)
ms:contentKeyID: 48183228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2f5737f83a1965b920f2a23e1aabbbaec2af7b3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572637"
---
# <a name="enabling-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="6deb1-103">Habilitar o controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6deb1-103">Enabling call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6deb1-104">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6deb1-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6deb1-105">O serviço de controle de admissão de chamadas (CAC) é uma rede de regiões, sites e sub-redes que permite impor restrições às transmissões de áudio e vídeo com base na largura de banda disponível.</span><span class="sxs-lookup"><span data-stu-id="6deb1-105">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="6deb1-106">Após configurar a rede CAC, habilite o CAC para impor as limitações de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="6deb1-106">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="6deb1-107">Você pode usar o painel de controle do Lync Server para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="6deb1-107">You can use Lync Server Control Panel to do this.</span></span>

<div>

## <a name="to-enable-cac-from-lync-server-control-panel"></a><span data-ttu-id="6deb1-108">Para habilitar o CAC do painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="6deb1-108">To enable CAC from Lync Server Control Panel</span></span>

1.  <span data-ttu-id="6deb1-109">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="6deb1-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6deb1-110">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6deb1-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6deb1-111">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6deb1-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6deb1-112">Na barra de navegação à esquerda, clique em **Configuração da Rede** e clique em **Global**.</span><span class="sxs-lookup"><span data-stu-id="6deb1-112">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="6deb1-113">Na página **Global**, clique na configuração **Global**.</span><span class="sxs-lookup"><span data-stu-id="6deb1-113">On the **Global** page, click the **Global** configuration.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6deb1-114">Somente uma rede pode ser configurada para qualquer implantação do Microsoft Lync Server 2013, portanto, nunca haverá mais de uma configuração de rede na lista.</span><span class="sxs-lookup"><span data-stu-id="6deb1-114">Only one network can be configured for any Microsoft Lync Server 2013 deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="6deb1-115">Você não pode renomear a configuração Global.</span><span class="sxs-lookup"><span data-stu-id="6deb1-115">You cannot rename the Global configuration.</span></span>

    
    </div>

5.  <span data-ttu-id="6deb1-116">No menu **Editar**, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="6deb1-116">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="6deb1-117">Na página **Editar Configuração Global**, marque a caixa de seleção **Habilitar controle de admissão de chamadas** e então clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="6deb1-117">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="6deb1-p104">Quando você clica em **Confirmar**, você executa um teste da configuração. A caixa de diálogo **Editar Configurações Globais** é fechada, retornando você à página **Global**. Você receberá uma viso sobre qualquer erro ou inconsistência descoberta em sua configuração de rede que a impeça de funcionar corretamente (por exemplo, se cada região não estiver conectada às outras regiões através de uma rota intrarregional).</span><span class="sxs-lookup"><span data-stu-id="6deb1-p104">When you click **Commit**, you run a test of the configuration. The **Edit Global Settings** dialog box closes, returning you to the **Global** page. You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="6deb1-p105">Caso faça alterações em sua configuração de rede, você pode executar a verificação de validação novamente abrindo a configuração Global e clicando em **Confirmar**. Você não precisa desativar o CAC primeiro: deixe a caixa de seleção marcada e clique em **Confirmar**. Você pode fazer isso a qualquer hora sem fazer nenhuma alteração na configuração.</span><span class="sxs-lookup"><span data-stu-id="6deb1-p105">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**. You do not need to disable CAC first: leave the check box checked and click **Commit**. You can do this at any time without making any configuration changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6deb1-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="6deb1-124">See Also</span></span>


[<span data-ttu-id="6deb1-125">Visão geral do controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6deb1-125">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)  


[<span data-ttu-id="6deb1-126">Planejando o controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6deb1-126">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)  
[<span data-ttu-id="6deb1-127">Configurar o controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6deb1-127">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="6deb1-128">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="6deb1-128">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  
[<span data-ttu-id="6deb1-129">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="6deb1-129">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  
[<span data-ttu-id="6deb1-130">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="6deb1-130">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

