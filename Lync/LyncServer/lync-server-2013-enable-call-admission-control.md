---
title: 'Lync Server 2013: habilitar controle de admissão de chamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable call admission control
ms:assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398642(v=OCS.15)
ms:contentKeyID: 48184650
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc2b31e399ba43f9e6b02ea66466da74e39d63a8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197324"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="3edcc-102">Habilitar controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3edcc-102">Enable call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3edcc-103">_**Última modificação do tópico:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="3edcc-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="3edcc-104">Após definir as configurações de rede para a implantação do serviço de controle de admissão de chamadas, habilite o CAC para que as políticas de largura de banda entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="3edcc-104">After you have configured your network settings for call admission control deployment, you must enable CAC to put your bandwidth policies into effect.</span></span>

<span data-ttu-id="3edcc-105">Para obter detalhes, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="3edcc-105">For details, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="3edcc-106">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="3edcc-106">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)

  - [<span data-ttu-id="3edcc-107">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="3edcc-107">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)

  - [<span data-ttu-id="3edcc-108">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="3edcc-108">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)

<div>

## <a name="to-enable-call-admission-control-by-using-management-shell"></a><span data-ttu-id="3edcc-109">Para habilitar o controle de admissão de chamada usando o Shell de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="3edcc-109">To enable call admission control by using Management Shell</span></span>

1.  <span data-ttu-id="3edcc-110">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="3edcc-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="3edcc-p101">Execute o cmdlet Set-CsNetworkConfiguration para ativar o CAC na rede. Por exemplo, execute:</span><span class="sxs-lookup"><span data-stu-id="3edcc-p101">Run the Set-CsNetworkConfiguration cmdlet to enable CAC in your network. For example, run:</span></span>
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
    
    <span data-ttu-id="3edcc-113">Se você deseja desativar o CAC na rede, execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3edcc-113">If you want to disable CAC in your network, run the following:</span></span>
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0

</div>

<div>

## <a name="to-enable-call-admission-control-by-using-lync-server-control-panel"></a><span data-ttu-id="3edcc-114">Para habilitar o controle de admissão de chamada usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="3edcc-114">To enable call admission control by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="3edcc-115">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3edcc-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3edcc-116">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3edcc-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="3edcc-117">Na barra de navegação esquerda, clique em **Configuração de Rede**.</span><span class="sxs-lookup"><span data-stu-id="3edcc-117">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="3edcc-118">Clique no botão de navegação **Global**.</span><span class="sxs-lookup"><span data-stu-id="3edcc-118">Click the **Global** navigation button.</span></span>

4.  <span data-ttu-id="3edcc-119">Clique em **Global** na lista e selecione **Exibir detalhes**    no menu **Editar**.</span><span class="sxs-lookup"><span data-stu-id="3edcc-119">Click **Global** in the list, and then select **Show Details** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="3edcc-120">Na página **Editar Configurações Globais**, marque a caixa de seleção **Ativar controle de admissão de chamada**.</span><span class="sxs-lookup"><span data-stu-id="3edcc-120">On the **Edit Global Settings** page, select the **Enable call admission control** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3edcc-121">Se você deseja desativar o controle de admissão de chamada durante a implantação, desmarque esta caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="3edcc-121">If you want to disable call admission control throughout your deployment, clear this check box.</span></span>

    
    </div>

6.  <span data-ttu-id="3edcc-122">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="3edcc-122">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

