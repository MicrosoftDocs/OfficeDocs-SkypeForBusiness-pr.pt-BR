---
title: 'Lync Server 2013: Habilitando o monitoramento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling monitoring
ms:assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687994(v=OCS.15)
ms:contentKeyID: 49733584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2b13028390328e93a9e90636962dedea8ea8ec9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-monitoring-in-lync-server-2013"></a><span data-ttu-id="046de-102">Habilitando o monitoramento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="046de-102">Enabling monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="046de-103">_**Tópico da última modificação:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="046de-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="046de-104">Embora os agentes de coleta de dados unificados sejam automaticamente instalados e ativados em cada servidor front-end, isso não significa que você começará a coletar dados de monitoramento automaticamente no momento em que você terminar de instalar o Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="046de-104">Although the unified data collection agents are automatically installed and activated on each Front End server, that does not mean that you will automatically begin to collect monitoring data the moment you finish installing Microsoft Lync Server 2013.</span></span> <span data-ttu-id="046de-105">Em vez disso, você deve fazer duas coisas: você deve associar seus servidores de front-end/pools front-end a um banco de dados de monitoramento e deve habilitar a monitoração de detalhes de chamadas (CDR) e/ou Quality of Experience (QoE) no escopo global e/ou no escopo do site.</span><span class="sxs-lookup"><span data-stu-id="046de-105">Instead, you must do two things: you must associate your Front End servers/Front End pools with a monitoring database, and you must enable call detail recording (CDR) and/or Quality of Experience (QoE) monitoring at the global scope and/or the site scope.</span></span>

<span data-ttu-id="046de-106">Para obter instruções passo a passo sobre como associar servidores de front-end ou pools de front-end a um banco de dados de monitoramento, consulte o tópico [associando um repositório de monitoramento a um pool de front-end no Lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) no guia de implantação.</span><span class="sxs-lookup"><span data-stu-id="046de-106">For step-by-step instructions on associating Front End servers or Front End pools with a monitoring database, see the topic [Associating a monitoring store with a Front End pool in Lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) in the Deployment guide.</span></span> <span data-ttu-id="046de-107">Depois que essas associações tiverem sido feitas e após a publicação da nova topologia do Lync Server, você ainda não poderá coletar os dados de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="046de-107">After these associations have been made, and after your new Lync Server topology has been published, you will still not be able to collect monitoring data.</span></span> <span data-ttu-id="046de-108">Isso ocorre porque, por padrão, a coleta de dados CDR e QoE é desativada quando você instala o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="046de-108">That's because, by default, both CDR and QoE data collection is disabled when you install Lync Server 2013.</span></span>

<span data-ttu-id="046de-109">Para começar a coleta de dados, você precisará habilitar o CDR e/ou o monitoramento QoE.</span><span class="sxs-lookup"><span data-stu-id="046de-109">In order to begin data collection you will need to enable CDR and/or QoE monitoring.</span></span> <span data-ttu-id="046de-110">(Observe que você não precisa habilitar o monitoramento de CDR e QoE; se preferir, você pode habilitar um tipo de monitoramento enquanto deixa o outro tipo desabilitado.) Para habilitar o monitoramento de CDR no escopo global, execute o seguinte comando no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="046de-110">(Note that you do not have to enable both CDR and QoE monitoring; if you prefer, you can enable one type of monitoring while leaving the other type disabled.) To enable CDR monitoring at the global scope run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

<span data-ttu-id="046de-111">Você também pode habilitar o monitoramento de CDR no painel de controle do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="046de-111">Alternatively, you can enable CDR monitoring from within the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="046de-112">No painel de controle do Lync Server, conclua o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="046de-112">From within the Lync Server Control Panel, complete the following procedure:</span></span>

1.  <span data-ttu-id="046de-113">Clique em **Monitoramento**.</span><span class="sxs-lookup"><span data-stu-id="046de-113">Click **Monitoring**.</span></span>

2.  <span data-ttu-id="046de-114">Na guia **Registro de Detalhes das Chamadas**, clique duas vezes na configuração **Global**.</span><span class="sxs-lookup"><span data-stu-id="046de-114">On the **Call Detail Recording** tab, double-click the **Global** setting.</span></span>

3.  <span data-ttu-id="046de-115">No painel **Editar configuração do registro de detalhes das chamadas (CDR)**, selecione **Habilitar monitoramento de CDRs** e clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="046de-115">In the **Edit Call Detail Recording (CDR) Setting** pane, select **Enable monitoring of CDRs** and then click **Commit**.</span></span>

<span data-ttu-id="046de-116">Para habilitar o monitoramento de QoE no escopo global, execute este comando dentro do Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="046de-116">To enable QoE monitoring at the global scope, run this command from within the Lync Server Management Shell:</span></span>

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $True

<span data-ttu-id="046de-117">Se preferir, você também pode habilitar o monitoramento de QoE no painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="046de-117">If you prefer, you can also enable QoE monitoring from within the Lync Server Control Panel.</span></span> <span data-ttu-id="046de-118">No Painel de Controle, execute o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="046de-118">From within the Control Panel, complete the following procedure:</span></span>

1.  <span data-ttu-id="046de-119">Clique em **Monitoramento**.</span><span class="sxs-lookup"><span data-stu-id="046de-119">Click **Monitoring**.</span></span>

2.  <span data-ttu-id="046de-120">Na guia **Dados da Qualidade da Experiência**, clique duas vezes na configuração **Global**.</span><span class="sxs-lookup"><span data-stu-id="046de-120">On the **Quality of Experience Data** tab, double-click the **Global** setting.</span></span>

3.  <span data-ttu-id="046de-121">No painel **Editar configuração da Qualidade da Experiência (QoE)**, selecione **Habilitar monitoramento de dados QoE** e clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="046de-121">In the **Edit Quality of Experience (QoE) Setting** pane, select **Enable monitoring of QoE data** and then click **Commit**.</span></span>

<span data-ttu-id="046de-122">Como observado, os exemplos precedentes habilitam o monitoramento no escopo global; isto é, eles habilitam o monitoramento CDR e QoE em toda a sua organização.</span><span class="sxs-lookup"><span data-stu-id="046de-122">As noted, the preceding examples enable monitoring at the global scope; that is, they enable CDR and QoE monitoring throughout your organization.</span></span> <span data-ttu-id="046de-123">Como alternativa, é possível criar definições de configurações CDR e QoE separadas no escopo local e habilitar ou desabilitar seletivamente o monitoramento de cada local.</span><span class="sxs-lookup"><span data-stu-id="046de-123">Alternatively, you can create separate CDR and QoE configuration settings at the site scope, and then selectively enable or disable monitoring for each site.</span></span> <span data-ttu-id="046de-124">Por exemplo, é possível habilitar o monitoramento CDR para seu local Redmond e desabilitar o monitoramento CDR para Dublin.</span><span class="sxs-lookup"><span data-stu-id="046de-124">For example, you could enable CDR monitoring for your Redmond site, yet disable CDR monitoring for your Dublin site.</span></span> <span data-ttu-id="046de-125">Para obter mais informações sobre como gerenciar suas configurações de monitoramento de configuração, consulte o tópico do guia de implantação Configurando a [gravação de detalhes da chamada e as configurações de qualidade de experiência no Lync Server 2013](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md).</span><span class="sxs-lookup"><span data-stu-id="046de-125">For more information on managing your monitoring configuration settings, see the Deployment guide topic [Configuring call detail recording and Quality of Experience settings in Lync Server 2013](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

