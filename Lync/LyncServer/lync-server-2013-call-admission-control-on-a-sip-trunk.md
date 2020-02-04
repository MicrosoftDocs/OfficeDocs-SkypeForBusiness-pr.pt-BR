---
title: 'Lync Server 2013: Controle de admissão de chamada em um tronco SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control on a SIP trunk
ms:assetid: 7eada098-3d47-4be2-839f-8f87d582efe8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398632(v=OCS.15)
ms:contentKeyID: 48184623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab8196070bbb7992aed915cf188d67e95912524a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742401"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-on-a-sip-trunk-in-lync-server-2013"></a><span data-ttu-id="38f89-102">Controle de admissão de chamada em um tronco SIP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38f89-102">Call admission control on a SIP trunk in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38f89-103">_**Tópico da última modificação:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="38f89-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="38f89-p101">Para implantar o controle de admissão de chamadas em um tronco SIP, crie um local de rede para representar o ITSP (provedor de serviço de telefonia da Internet). Para aplicar valores de política de largura de banda no tronco SIP, crie uma política entre locais entre o local de rede na sua empresa e o local de rede criado para representar o ITSP.</span><span class="sxs-lookup"><span data-stu-id="38f89-p101">To deploy call admission control (CAC) on a SIP trunk, you create a network site to represent the Internet telephony service provider (ITSP). To apply bandwidth policy values on the SIP trunk, you create an inter-site policy between the network site in your enterprise and the network site that you create to represent the ITSP.</span></span>

<span data-ttu-id="38f89-106">A figura a seguir mostra um exemplo de implantação do CAC em um tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="38f89-106">The following figure shows an example CAC deployment on a SIP trunk.</span></span>

<span data-ttu-id="38f89-107">**Configuração do CAC em um tronco SIP**</span><span class="sxs-lookup"><span data-stu-id="38f89-107">**CAC configuration on a SIP trunk**</span></span>

<span data-ttu-id="38f89-108">![Diagrama de entroncamento SIP do controle de admissão de chamadas](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "Diagrama de entroncamento SIP do controle de admissão de chamadas")</span><span class="sxs-lookup"><span data-stu-id="38f89-108">![Call Admission Control SIP Trunking diagram](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "Call Admission Control SIP Trunking diagram")</span></span>

<span data-ttu-id="38f89-109">Para configurar o CAC em um tronco SIP, você terá que executar as seguintes tarefas durante a implantação do CAC:</span><span class="sxs-lookup"><span data-stu-id="38f89-109">To configure CAC on a SIP trunk, you will have to perform the following tasks during CAC deployment:</span></span>

1.  <span data-ttu-id="38f89-110">Crie um site de rede para representar o ITSP.</span><span class="sxs-lookup"><span data-stu-id="38f89-110">Create a network site to represent the ITSP.</span></span> <span data-ttu-id="38f89-111">Associe o site de rede a uma região de rede apropriada e aloque a largura de banda de zero para áudio e vídeo para este site de rede.</span><span class="sxs-lookup"><span data-stu-id="38f89-111">Associate the network site to an appropriate network region, and allocate bandwidth of zero for audio and video for this network site.</span></span> <span data-ttu-id="38f89-112">Para obter detalhes, consulte [configurar sites de rede para o CAC no Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="38f89-112">For details, see [Configure network sites for CAC in Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38f89-113">Para o ITSP, essa configuração de site de rede não funciona.</span><span class="sxs-lookup"><span data-stu-id="38f89-113">For the ITSP, this network site configuration is not functional.</span></span> <span data-ttu-id="38f89-114">Os valores da política de largura de banda são, na verdade, aplicados na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="38f89-114">Bandwidth policy values are actually applied in step 2.</span></span>

    
    </div>

2.  <span data-ttu-id="38f89-115">Crie um link entre sites para o tronco SIP usando os valores de parâmetro relevantes para o site criado na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="38f89-115">Create an inter-site link for the SIP trunk using the relevant parameter values for the site you created in step 1.</span></span> <span data-ttu-id="38f89-116">Por exemplo, use o nome do site de rede na sua empresa como o valor do parâmetro NetworkSiteID1 e o site de rede ITSP como o valor do parâmetro NetworkSiteID2.</span><span class="sxs-lookup"><span data-stu-id="38f89-116">For example, use the name of the network site in your enterprise as the value of the NetworkSiteID1 parameter, and the ITSP network site as the value of the NetworkSiteID2 parameter.</span></span> <span data-ttu-id="38f89-117">Para obter detalhes, consulte [criar políticas entre sites de rede no Lync Server 2013](lync-server-2013-create-network-intersite-policies.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="38f89-117">For details, see [Create network intersite policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="38f89-118">Consulte também a documentação do Shell de gerenciamento do Lync Server para o cmdlet New-CsNetworkInterSitePolicy.</span><span class="sxs-lookup"><span data-stu-id="38f89-118">Also see the Lync Server Management Shell documentation for the New-CsNetworkInterSitePolicy cmdlet.</span></span>

3.  <span data-ttu-id="38f89-119">Obtenha o endereço IP do ponto de terminação de mídia do SCB (controlador de borda da sessão) no seu ITSP.</span><span class="sxs-lookup"><span data-stu-id="38f89-119">Get the IP address of the Session Border Controller’s (SCB) Media Termination Point from your ITSP.</span></span> <span data-ttu-id="38f89-120">Adicione o endereço IP com uma máscara de sub-rede de 32 para o site de rede que representa o ITSP.</span><span class="sxs-lookup"><span data-stu-id="38f89-120">Add that IP address with a subnet mask of 32 to the network site that represents the ITSP.</span></span> <span data-ttu-id="38f89-121">Para obter detalhes, consulte [associar uma sub-rede a um site de rede no Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="38f89-121">For details, see [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

