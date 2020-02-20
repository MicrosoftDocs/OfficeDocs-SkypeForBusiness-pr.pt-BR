---
title: Configurar cenários do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Lync Server 2013 Scenarios
ms:assetid: 6705346b-1512-4af3-85e4-64dfa6ee6f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945596(v=OCS.15)
ms:contentKeyID: 51541420
ms.date: 12/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e706edf9d66e3a1e9ac76eeac32ab882365e5ab
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147784"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-scenarios"></a><span data-ttu-id="51bcd-102">Configurar cenários do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51bcd-102">Configure Lync Server 2013 Scenarios</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51bcd-103">_**Última modificação do tópico:** 2016-12-28_</span><span class="sxs-lookup"><span data-stu-id="51bcd-103">_**Topic Last Modified:** 2016-12-28_</span></span>

<span data-ttu-id="51bcd-104">Para executar a ferramenta de estresse e desempenho do Lync Server 2013 (LyncPerfTool), a topologia 2013 do Lync Server deve primeiro ser configurada para os cenários que serão executados.</span><span class="sxs-lookup"><span data-stu-id="51bcd-104">To run the Lync Server 2013 Stress and Performance Tool (LyncPerfTool), the Lync Server 2013 topology must first be configured for the scenarios that will be executed.</span></span> <span data-ttu-id="51bcd-105">Se o Lync Server 2013 não estiver configurado ou configurado incorretamente, a simulação de carga falhará na maioria dos casos.</span><span class="sxs-lookup"><span data-stu-id="51bcd-105">If Lync Server 2013 is not configured or is configured incorrectly, load simulation will fail in most cases.</span></span> <span data-ttu-id="51bcd-106">Com a ferramenta de estresse e desempenho do Lync Server 2013, fornecemos exemplos de scripts do Shell de gerenciamento do Lync Server e arquivos de recursos básicos que podem ser usados como ponto de partida para configurar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="51bcd-106">With the Lync Server 2013 Stress and Performance Tool, we have provided example Lync Server Management Shell scripts and basic resource files that can be used as a starting point for configuring Lync Server 2013.</span></span> <span data-ttu-id="51bcd-107">Este tópico descreve os exemplos do Windows PowerShell fornecidos.</span><span class="sxs-lookup"><span data-stu-id="51bcd-107">This topic describes the Windows PowerShell examples provided.</span></span> <span data-ttu-id="51bcd-108">Observe que não é o objetivo deste tópico descrever como configurar o Lync Server 2013 em geral.</span><span class="sxs-lookup"><span data-stu-id="51bcd-108">Note that it is not the goal of this topic to describe how to configure Lync Server 2013 in general.</span></span> <span data-ttu-id="51bcd-109">Para obter detalhes sobre como trabalhar com o Windows PowerShell no Lync Server 2013, consulte a documentação do Shell <https://technet.microsoft.com/library/gg398474.aspx>de gerenciamento do Lync Server em.</span><span class="sxs-lookup"><span data-stu-id="51bcd-109">For details about working with Windows PowerShell in Lync Server 2013, see the Lync Server Management Shell documentation at <https://technet.microsoft.com/library/gg398474.aspx>.</span></span>

<div>

## <a name="about-running-lync-server-management-shell-scripts"></a><span data-ttu-id="51bcd-110">Sobre a execução de scripts do Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="51bcd-110">About Running Lync Server Management Shell Scripts</span></span>

<span data-ttu-id="51bcd-111">Fornecemos exemplos de scripts do Shell de gerenciamento do Lync Server que podem ser usados em preparação para executar a simulação de carga.</span><span class="sxs-lookup"><span data-stu-id="51bcd-111">We have provided example Lync Server Management Shell scripts that may be used in preparation for running load simulation.</span></span> <span data-ttu-id="51bcd-112">Como os scripts se destinam à simulação de carga, eles são simples e permissivos e, portanto, podem não ser apropriados para produção.</span><span class="sxs-lookup"><span data-stu-id="51bcd-112">Because the scripts are intended for load simulation, they are simple and permissive, and therefore may not be appropriate for production.</span></span> <span data-ttu-id="51bcd-113">Todos os scripts são exemplos e devem ser revisados e, em alguns casos, modificados para refletir sua topologia.</span><span class="sxs-lookup"><span data-stu-id="51bcd-113">All scripts are examples and must be reviewed, and, in some cases, modified to reflect your topology.</span></span> <span data-ttu-id="51bcd-114">No mínimo, esperamos que o cenário do serviço de grupo de resposta (RGS) precise ser modificado para especificar os agentes atribuídos aos grupos de agentes.</span><span class="sxs-lookup"><span data-stu-id="51bcd-114">At a minimum, we expect that the Response Group Service (RGS) scenario would need to be modified to specify the agents that are assigned to the agent groups.</span></span> <span data-ttu-id="51bcd-115">No entanto, você tem a opção de não simular esse carregamento.</span><span class="sxs-lookup"><span data-stu-id="51bcd-115">However, you have the option to not simulate this load.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="51bcd-116">Tome cuidado ao examinar e compreender os exemplos fornecidos.</span><span class="sxs-lookup"><span data-stu-id="51bcd-116">Take care in reviewing and understanding the examples provided.</span></span> <span data-ttu-id="51bcd-117">Os scripts substituirão as configurações existentes na topologia.</span><span class="sxs-lookup"><span data-stu-id="51bcd-117">Scripts will overwrite any existing settings in the topology.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="51bcd-118">Para obter detalhes sobre como usar o Windows PowerShell e o Shell de gerenciamento do Lync Server, consulte o blog do <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A>lync Server 2013 Windows PowerShell em.</span><span class="sxs-lookup"><span data-stu-id="51bcd-118">For details about using Windows PowerShell and the Lync Server Management Shell, see the Lync Server 2013 Windows PowerShell Blog at <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A>.</span></span>



</div>

</div>

<div>

## <a name="stress-and-performance-tool-client-version-monikers"></a><span data-ttu-id="51bcd-119">Identificadores de versão do cliente da ferramenta de estresse e desempenho</span><span class="sxs-lookup"><span data-stu-id="51bcd-119">Stress and Performance Tool Client Version Monikers</span></span>

<span data-ttu-id="51bcd-120">Talvez seja necessário configurar a política de verificação de versão do cliente se você tiver alterado as configurações de valores padrão.</span><span class="sxs-lookup"><span data-stu-id="51bcd-120">You may need to configure the Client Version Check policy if you have changed the settings from the default values.</span></span> <span data-ttu-id="51bcd-121">Para obter detalhes, consulte "Configurando as versões <https://technet.microsoft.com/library/gg412832(v=ocs.15).aspx>de cliente com suporte" em.</span><span class="sxs-lookup"><span data-stu-id="51bcd-121">For details, see “Configuring supported client versions” at <https://technet.microsoft.com/library/gg412832(v=ocs.15).aspx>.</span></span> <span data-ttu-id="51bcd-122">A ferramenta de desempenho e stress do Lync Server 2013 usa as seguintes versões de agente de usuário por padrão ao se comunicar com o Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="51bcd-122">The Lync Server 2013 Stress and Performance Tool uses the following User Agent Versions by default when communicating with Lync Server 2013:</span></span>

  - <span data-ttu-id="51bcd-123">LSPT/15.0.0.0 (ferramenta de estresse e desempenho do Lync Server 2013)</span><span class="sxs-lookup"><span data-stu-id="51bcd-123">LSPT/15.0.0.0 (Lync Server 2013 Stress and Performance Tool)</span></span>

  - <span data-ttu-id="51bcd-124">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="51bcd-124">OCPHONE/.0.522</span></span>

<span data-ttu-id="51bcd-125">Eles são para o cliente de mobilidade (UCWA) no LyncPerfTool:</span><span class="sxs-lookup"><span data-stu-id="51bcd-125">These are for the Mobility (UCWA) client in LyncPerfTool:</span></span>

  - <span data-ttu-id="51bcd-126">Ferramenta de perf Ucwa/conferência da Web</span><span class="sxs-lookup"><span data-stu-id="51bcd-126">Ucwa Perf Tool/Web Conference</span></span>

  - <span data-ttu-id="51bcd-127">Ferramenta Ucwa perf/móvel</span><span class="sxs-lookup"><span data-stu-id="51bcd-127">Ucwa Perf Tool/Mobile</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

