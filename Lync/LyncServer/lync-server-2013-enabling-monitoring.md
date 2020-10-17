---
title: 'Lync Server 2013: Habilitando o monitoramento'
description: 'Lync Server 2013: Habilitando o monitoramento.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling monitoring
ms:assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687994(v=OCS.15)
ms:contentKeyID: 49733584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8995042bdc9b121dc5253940104bb167567ddcc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558477"
---
# <a name="enabling-monitoring-in-lync-server-2013"></a><span data-ttu-id="f890b-103">Habilitando o monitoramento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f890b-103">Enabling monitoring in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f890b-104">_**Última modificação do tópico:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="f890b-104">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="f890b-105">Embora os agentes de coleta de dados unificados sejam instalados e ativados automaticamente em cada servidor de front-end, isso não significa que você começará automaticamente a coletar dados de monitoramento no momento em que concluir a instalação do Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f890b-105">Although the unified data collection agents are automatically installed and activated on each Front End server, that does not mean that you will automatically begin to collect monitoring data the moment you finish installing Microsoft Lync Server 2013.</span></span> <span data-ttu-id="f890b-106">Ao invés disso, você deve fazer duas coisas: associar seus pools de servidores de Front-End/servidores de Front-end com um banco de dados de monitoramento e deve habilitar o registro de detalhes da chamada (CDR) e/ou monitoramento da Qualidade de Experiência (QoE) no escopo global e/ou local.</span><span class="sxs-lookup"><span data-stu-id="f890b-106">Instead, you must do two things: you must associate your Front End servers/Front End pools with a monitoring database, and you must enable call detail recording (CDR) and/or Quality of Experience (QoE) monitoring at the global scope and/or the site scope.</span></span>

<span data-ttu-id="f890b-107">Para obter instruções passo a passo sobre como associar servidores front-end ou pools de front-ends a um banco de dados de monitoramento, consulte o tópico [associando um repositório de monitoramento a um pool de front-ends no Lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) no guia de implantação.</span><span class="sxs-lookup"><span data-stu-id="f890b-107">For step-by-step instructions on associating Front End servers or Front End pools with a monitoring database, see the topic [Associating a monitoring store with a Front End pool in Lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) in the Deployment guide.</span></span> <span data-ttu-id="f890b-108">Após estas associações serem realizadas e após sua nova topologia do Lync Server ter sido publicada, você ainda não poderá coletar dados de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="f890b-108">After these associations have been made, and after your new Lync Server topology has been published, you will still not be able to collect monitoring data.</span></span> <span data-ttu-id="f890b-109">Isso ocorre porque, por padrão, a coleta de dados de CDR e QoE é desabilitada quando você instala o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f890b-109">That's because, by default, both CDR and QoE data collection is disabled when you install Lync Server 2013.</span></span>

<span data-ttu-id="f890b-110">Para poder começar a coletar dados necessários habilite o CDR e/ou monitoramento QoE.</span><span class="sxs-lookup"><span data-stu-id="f890b-110">In order to begin data collection you will need to enable CDR and/or QoE monitoring.</span></span> <span data-ttu-id="f890b-111">(Observe que você não precisa habilitar o monitoramento de CDR e QoE; se preferir, é possível habilitar um tipo de monitoramento enquanto deixa o outro tipo desabilitado.) Para habilitar o monitoramento de CDR no escopo global, execute o seguinte comando no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="f890b-111">(Note that you do not have to enable both CDR and QoE monitoring; if you prefer, you can enable one type of monitoring while leaving the other type disabled.) To enable CDR monitoring at the global scope run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

<span data-ttu-id="f890b-112">Como alternativa, você pode habilitar o monitoramento de CDR no painel de controle do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f890b-112">Alternatively, you can enable CDR monitoring from within the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="f890b-113">No painel de controle do Lync Server, conclua o procedimento a seguir:</span><span class="sxs-lookup"><span data-stu-id="f890b-113">From within the Lync Server Control Panel, complete the following procedure:</span></span>

1.  <span data-ttu-id="f890b-114">Clique em **Monitoramento**.</span><span class="sxs-lookup"><span data-stu-id="f890b-114">Click **Monitoring**.</span></span>

2.  <span data-ttu-id="f890b-115">Na guia **Registro de Detalhes da Chamada**, clique duas vezes na configuração **Global**.</span><span class="sxs-lookup"><span data-stu-id="f890b-115">On the **Call Detail Recording** tab, double-click the **Global** setting.</span></span>

3.  <span data-ttu-id="f890b-116">No painel **Editar configuração do registro de detalhe da chamada (CDR)**, selecione **Habilitar monitoramento de CDRs** e clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f890b-116">In the **Edit Call Detail Recording (CDR) Setting** pane, select **Enable monitoring of CDRs** and then click **Commit**.</span></span>

<span data-ttu-id="f890b-117">Para habilitar o monitoramento de QoE no escopo global, execute este comando no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="f890b-117">To enable QoE monitoring at the global scope, run this command from within the Lync Server Management Shell:</span></span>

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $True

<span data-ttu-id="f890b-118">Se preferir, você também pode habilitar o monitoramento de QoE no painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f890b-118">If you prefer, you can also enable QoE monitoring from within the Lync Server Control Panel.</span></span> <span data-ttu-id="f890b-119">No Painel de Controle, conclua o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="f890b-119">From within the Control Panel, complete the following procedure:</span></span>

1.  <span data-ttu-id="f890b-120">Clique em **Monitoramento**.</span><span class="sxs-lookup"><span data-stu-id="f890b-120">Click **Monitoring**.</span></span>

2.  <span data-ttu-id="f890b-121">Na guia **Dados da Qualidade da Experiência**, clique duas vezes na configuração **Global**.</span><span class="sxs-lookup"><span data-stu-id="f890b-121">On the **Quality of Experience Data** tab, double-click the **Global** setting.</span></span>

3.  <span data-ttu-id="f890b-122">No painel **Editar configuração da Qualidade da Experiência (QoE)**, selecione **Habilitar monitoramento de dados QoE** e clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f890b-122">In the **Edit Quality of Experience (QoE) Setting** pane, select **Enable monitoring of QoE data** and then click **Commit**.</span></span>

<span data-ttu-id="f890b-123">Como observado, os exemplos anteriores habilitam o monitoramento no escopo global; isto é, eles habilitam o monitoramento CDR e QoE através da sua organização.</span><span class="sxs-lookup"><span data-stu-id="f890b-123">As noted, the preceding examples enable monitoring at the global scope; that is, they enable CDR and QoE monitoring throughout your organization.</span></span> <span data-ttu-id="f890b-124">Em alternativa, é possível criar definições de configurações CDR e QoE separadas no escopo local e habilitar ou desabilitar seletivamente o monitoramento de cada local.</span><span class="sxs-lookup"><span data-stu-id="f890b-124">Alternatively, you can create separate CDR and QoE configuration settings at the site scope, and then selectively enable or disable monitoring for each site.</span></span> <span data-ttu-id="f890b-125">Por exemplo, é possível habilitar o monitoramento CDR para seu local Redmond, desabilitar o monitoramento CDR para Dublin.</span><span class="sxs-lookup"><span data-stu-id="f890b-125">For example, you could enable CDR monitoring for your Redmond site, yet disable CDR monitoring for your Dublin site.</span></span> <span data-ttu-id="f890b-126">Para obter mais informações sobre como gerenciar suas definições de configuração de monitoramento, consulte o tópico Deployment Guide [Configuring Call Detail Recording and Quality of Experience Settings in Lync Server 2013](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md).</span><span class="sxs-lookup"><span data-stu-id="f890b-126">For more information on managing your monitoring configuration settings, see the Deployment guide topic [Configuring call detail recording and Quality of Experience settings in Lync Server 2013](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

