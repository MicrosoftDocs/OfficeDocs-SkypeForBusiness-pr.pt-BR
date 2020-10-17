---
title: 'Lync Server 2013: habilitar a qualidade da experiência'
description: 'Lync Server 2013: habilitar a qualidade da experiência.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Quality of Experience
ms:assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182583(v=OCS.15)
ms:contentKeyID: 48185385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43746227395477596ff5e39809cf819c110287ab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547867"
---
# <a name="enable-quality-of-experience-in-lync-server-2013"></a><span data-ttu-id="67a6c-103">Habilitar a qualidade da experiência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67a6c-103">Enable Quality of Experience in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67a6c-104">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="67a6c-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="67a6c-105">A QoE (Qualidade da Experiência) registra dados numéricos que indicam a qualidade da mídia e informações sobre participantes, nomes de dispositivo, drivers, endereços IP e tipos de ponto de extremidade envolvidos em chamadas e sessões.</span><span class="sxs-lookup"><span data-stu-id="67a6c-105">Quality of Experience (QoE) records numeric data that indicates the media quality and information about participants, device names, drivers, IP addresses, and endpoint types involved in calls and sessions.</span></span> <span data-ttu-id="67a6c-106">Para obter detalhes, consulte [Planning for monitoring in Lync Server 2013](lync-server-2013-planning-for-monitoring.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="67a6c-106">For details, see [Planning for monitoring in Lync Server 2013](lync-server-2013-planning-for-monitoring.md) in the Planning documentation.</span></span>

<span data-ttu-id="67a6c-107">Use o procedimento a seguir para habilitar QoE para toda sua organização ou para cada site em sua organização.</span><span class="sxs-lookup"><span data-stu-id="67a6c-107">Use the following procedure to enable QoE for your whole organization or each site in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="67a6c-108">Para habilitar o QoE, é necessário primeiro configurar o monitoramento e um back-end de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="67a6c-108">To enable QoE, you must first configure monitoring and a monitoring back-end database.</span></span> <span data-ttu-id="67a6c-109">Para obter detalhes, consulte <A href="lync-server-2013-deploying-monitoring.md">Deploying Monitoring in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="67a6c-109">For details, see <A href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-qoe-by-using-lync-server-control-panel"></a><span data-ttu-id="67a6c-110">Para habilitar a QoE usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="67a6c-110">To enable QoE by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="67a6c-111">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="67a6c-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="67a6c-112">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="67a6c-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="67a6c-113">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="67a6c-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="67a6c-114">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e em **Dados da Qualidade da Experiência**.</span><span class="sxs-lookup"><span data-stu-id="67a6c-114">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="67a6c-115">Na página **Dados da Qualidade da Experiência**, clique no conjunto adequado na tabela, clique em **Ação** e em **habilitar QoE**.</span><span class="sxs-lookup"><span data-stu-id="67a6c-115">On the **Quality of Experience Data** page, click the appropriate collection from the table, click **Action**, and then click **Enable QoE**.</span></span>

</div>

<div>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="67a6c-116">Habilitando o QoE usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="67a6c-116">Enabling QoE by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="67a6c-117">Você pode habilitar o QoE usando o Windows PowerShell e o cmdlet **set-CsQoEConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="67a6c-117">You can enable QoE by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="67a6c-118">Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="67a6c-118">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="67a6c-119">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="67a6c-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-qoe-for-a-single-location"></a><span data-ttu-id="67a6c-120">Para habilitar o QoE para um único local</span><span class="sxs-lookup"><span data-stu-id="67a6c-120">To enable QoE for a single location</span></span>

  - <span data-ttu-id="67a6c-121">Para habilitar o QoE, defina o parâmetro EnableQoE para True ($True).</span><span class="sxs-lookup"><span data-stu-id="67a6c-121">To enable QoE, set the EnableQoE parameter to True ($True).</span></span>
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True

</div>

<div>

## <a name="to-disable-qoe-for-a-single-location"></a><span data-ttu-id="67a6c-122">Para desabilitar o QoE para um único local</span><span class="sxs-lookup"><span data-stu-id="67a6c-122">To disable QoE for a single location</span></span>

  - <span data-ttu-id="67a6c-p105">Para desabilitar o QoE, defina o parâmetro EnableQoE para False ($False). Isto não desinstala o monitoramento. Pausa o conjunto e armazena os dados do QoE.</span><span class="sxs-lookup"><span data-stu-id="67a6c-p105">To disable QoE, set the EnableQoE parameter to False ($False). This does not uninstall monitoring. It pauses the collection and storage of QoE data.</span></span>
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a><span data-ttu-id="67a6c-126">Para usar um único comando para habilitar o QoE em vários locais</span><span class="sxs-lookup"><span data-stu-id="67a6c-126">To use a single command to enable QoE in multiple locations</span></span>

  - <span data-ttu-id="67a6c-127">Este comando habilita o QoE para todas as definições de configuração do QoE atualmente em uso na sua organização.</span><span class="sxs-lookup"><span data-stu-id="67a6c-127">This command enables QoE for all the QoE configuration settings currently in use in your organization.</span></span>
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True

</div>

<span data-ttu-id="67a6c-128">Para obter detalhes, consulte [set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration).</span><span class="sxs-lookup"><span data-stu-id="67a6c-128">For details, see [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="67a6c-129">Confira também</span><span class="sxs-lookup"><span data-stu-id="67a6c-129">See Also</span></span>


[<span data-ttu-id="67a6c-130">Planejamento de monitoramento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67a6c-130">Planning for monitoring in Lync Server 2013</span></span>](lync-server-2013-planning-for-monitoring.md)  
[<span data-ttu-id="67a6c-131">Implantando o monitoramento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67a6c-131">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

