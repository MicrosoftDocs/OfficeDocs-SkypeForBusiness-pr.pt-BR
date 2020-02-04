---
title: 'Lync Server 2013: topologias para telefones IP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies for IP phones
ms:assetid: 26ebffcf-43ff-4e70-847d-0fbc90e94e57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425740(v=OCS.15)
ms:contentKeyID: 48183662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e05a56d30167f2e20a383cde9fcfaaa70418e650
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745201"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-for-ip-phones-in-lync-server-2013"></a><span data-ttu-id="be45f-102">Topologias para telefones IP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be45f-102">Topologies for IP phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be45f-103">_**Tópico da última modificação:** 2012-06-21_</span><span class="sxs-lookup"><span data-stu-id="be45f-103">_**Topic Last Modified:** 2012-06-21_</span></span>

<span data-ttu-id="be45f-104">Esta seção fornece uma visão geral do processo de conectividade e explica as diferenças entre como um telefone IP se conecta a uma rede interna e externa.</span><span class="sxs-lookup"><span data-stu-id="be45f-104">This section provides an overview of the connectivity process and explains the differences between how an IP phone connects in an internal and external network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="be45f-105">O Lync Server oferece suporte para os seguintes telefones IP: o Aastra 6721ip Common Area Phone, Aastra 6725ip Desk Phone, HP 4110 IP Phone (Common Area Phone), HP 4120 IP Phone (Phone Desk), Polycom CX600 IP Desk Phone, Polycom CX700 IP Desk Phone, Polycom CX500 IP telefone de área comum e Polycom CX3000 de conferência IP.</span><span class="sxs-lookup"><span data-stu-id="be45f-105">Lync Server provides support for the following IP phones: the Aastra 6721ip common area phone, Aastra 6725ip desk phone, HP 4110 IP Phone (common area phone), HP 4120 IP Phone (desk phone), Polycom CX600 IP desk phone, Polycom CX700 IP desk phone, Polycom CX500 IP common area phone, and Polycom CX3000 IP conference phone.</span></span> <span data-ttu-id="be45f-106">Desses telefones, tudo menos o Polycom CX700 pode executar o Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="be45f-106">Of those phones, all but the Polycom CX700 can run Lync Phone Edition.</span></span>



</div>

<span data-ttu-id="be45f-107">O diagrama a seguir descreve todos os componentes envolvidos na conectividade do dispositivo no ambiente corporativo.</span><span class="sxs-lookup"><span data-stu-id="be45f-107">The following diagram describes all the components involved in device connectivity within the corporate environment.</span></span>

<span data-ttu-id="be45f-108">**Topologia interna**</span><span class="sxs-lookup"><span data-stu-id="be45f-108">**Internal Topology**</span></span>

<span data-ttu-id="be45f-109">![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")</span><span class="sxs-lookup"><span data-stu-id="be45f-109">![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="be45f-110">A figura anterior é uma representação lógica, não uma visão geral física.</span><span class="sxs-lookup"><span data-stu-id="be45f-110">The previous figure is a logical representation, not a physical overview.</span></span> <span data-ttu-id="be45f-111">Por exemplo, os serviços de domínio Active Directory (AD DS) raramente estão localizados na mesma máquina que qualquer componente do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="be45f-111">For example, Active Directory Domain Services (AD DS) is rarely located on the same machine as any Lync Server components.</span></span> <span data-ttu-id="be45f-112">O repositório de usuários pode estar localizado no servidor back-end ou nos servidores de arquivamento e monitoramento.</span><span class="sxs-lookup"><span data-stu-id="be45f-112">The user store can be located on the Back End Server or on the Archiving and Monitoring Servers.</span></span> <span data-ttu-id="be45f-113">O Shell de gerenciamento do Lync Server, o servidor Web e os serviços de atualização são parte da função de servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="be45f-113">The Lync Server Management Shell, web server, and update services are all part of the Front End Server role.</span></span>



</div>

<span data-ttu-id="be45f-114">O diagrama a seguir fornece uma visão geral dos componentes envolvidos quando o dispositivo está localizado fora da rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="be45f-114">The following diagram provides an overview of the components involved when the device is located outside the corporate network.</span></span>

<span data-ttu-id="be45f-115">**Topologia externa**</span><span class="sxs-lookup"><span data-stu-id="be45f-115">**External Topology**</span></span>

<span data-ttu-id="be45f-116">![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")</span><span class="sxs-lookup"><span data-stu-id="be45f-116">![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="be45f-117">O serviço Web de atualização de dispositivo fornece um site externo e externo, mas somente o externo é mostrado aqui.</span><span class="sxs-lookup"><span data-stu-id="be45f-117">The Device Update Web service provides an external and internal website, but only the external one is shown here.</span></span><BR><span data-ttu-id="be45f-118">A localização do registrador e a URL do serviço Web de atualização de dispositivo para a organização devem ser publicadas no DNS se o acesso externo estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="be45f-118">The location of the Registrar and the URL of the Device Update Web service for the organization must be published in DNS if external access is to be enabled.</span></span> <span data-ttu-id="be45f-119">Além disso, o servidor de borda deve ser implantado e configurado corretamente para permitir comunicações externas do dispositivo para o ambiente corporativo e para trás.</span><span class="sxs-lookup"><span data-stu-id="be45f-119">Additionally, the Edge Server must be deployed and correctly configured to allow external communications from the device to the corporate environment and back.</span></span> <span data-ttu-id="be45f-120">Isso é omitido do diagrama anterior porque a implantação de borda não é específica da conectividade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="be45f-120">This is omitted from the previous diagram because Edge deployment is not specific to device connectivity.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

