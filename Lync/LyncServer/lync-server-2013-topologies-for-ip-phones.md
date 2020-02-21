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
ms.openlocfilehash: 36afef4fe357e79f1d6c9579273262b265d2c0ad
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193564"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="topologies-for-ip-phones-in-lync-server-2013"></a><span data-ttu-id="5dee8-102">Topologias para telefones IP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5dee8-102">Topologies for IP phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5dee8-103">_**Última modificação do tópico:** 2012-06-21_</span><span class="sxs-lookup"><span data-stu-id="5dee8-103">_**Topic Last Modified:** 2012-06-21_</span></span>

<span data-ttu-id="5dee8-104">Esta seção fornece uma visão geral do processo de conectividade e explica as diferenças entre como um telefone IP se conecta em uma rede interna e externa.</span><span class="sxs-lookup"><span data-stu-id="5dee8-104">This section provides an overview of the connectivity process and explains the differences between how an IP phone connects in an internal and external network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5dee8-105">O Lync Server oferece suporte para os seguintes telefones IP: o telefone de área comum do Aastra 6721ip, Aastra 6725ip de telefone, telefone IP HP 4110 (telefone de área comum), HP 4120 IP Phone (telefone de mesa), telefone de mesa de IP de Polycom CX600, telefone de rede IP do Polycom CX700, Polycom CX500 IP telefone de área comum e telefone de conferência IP Polycom CX3000.</span><span class="sxs-lookup"><span data-stu-id="5dee8-105">Lync Server provides support for the following IP phones: the Aastra 6721ip common area phone, Aastra 6725ip desk phone, HP 4110 IP Phone (common area phone), HP 4120 IP Phone (desk phone), Polycom CX600 IP desk phone, Polycom CX700 IP desk phone, Polycom CX500 IP common area phone, and Polycom CX3000 IP conference phone.</span></span> <span data-ttu-id="5dee8-106">Desses telefones, todos exceto o Polycom CX700 podem executar o Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="5dee8-106">Of those phones, all but the Polycom CX700 can run Lync Phone Edition.</span></span>



</div>

<span data-ttu-id="5dee8-107">O diagrama a seguir descreve todos os componentes envolvidos na conectividade do dispositivo dentro do ambiente empresarial.</span><span class="sxs-lookup"><span data-stu-id="5dee8-107">The following diagram describes all the components involved in device connectivity within the corporate environment.</span></span>

<span data-ttu-id="5dee8-108">**Topologia Interna**</span><span class="sxs-lookup"><span data-stu-id="5dee8-108">**Internal Topology**</span></span>

<span data-ttu-id="5dee8-109">![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")</span><span class="sxs-lookup"><span data-stu-id="5dee8-109">![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5dee8-110">A figura anterior é uma representação local, não visão geral física.</span><span class="sxs-lookup"><span data-stu-id="5dee8-110">The previous figure is a logical representation, not a physical overview.</span></span> <span data-ttu-id="5dee8-111">Por exemplo, os serviços de domínio do Active Directory (AD DS) raramente estão localizados na mesma máquina que os componentes do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5dee8-111">For example, Active Directory Domain Services (AD DS) is rarely located on the same machine as any Lync Server components.</span></span> <span data-ttu-id="5dee8-112">O repositório de usuários pode estar localizado no Servidor de Back-End ou nos Servidores de Arquivamento e Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="5dee8-112">The user store can be located on the Back End Server or on the Archiving and Monitoring Servers.</span></span> <span data-ttu-id="5dee8-113">O Shell de gerenciamento do Lync Server, o servidor Web e os serviços de atualização são todos parte da função de servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="5dee8-113">The Lync Server Management Shell, web server, and update services are all part of the Front End Server role.</span></span>



</div>

<span data-ttu-id="5dee8-114">O diagrama a seguir fornece uma visão geral dos componentes envolvidos quando o dispositivo está localizado fora da rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="5dee8-114">The following diagram provides an overview of the components involved when the device is located outside the corporate network.</span></span>

<span data-ttu-id="5dee8-115">**Topologia Externa**</span><span class="sxs-lookup"><span data-stu-id="5dee8-115">**External Topology**</span></span>

<span data-ttu-id="5dee8-116">![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")</span><span class="sxs-lookup"><span data-stu-id="5dee8-116">![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5dee8-117">O serviço da Web de Atualização de Dispositivo oferece um site externo e interno, mas apenas o externo é mostrado aqui.</span><span class="sxs-lookup"><span data-stu-id="5dee8-117">The Device Update Web service provides an external and internal website, but only the external one is shown here.</span></span><BR><span data-ttu-id="5dee8-p103">O local do Registrador e a URL do Web Service de atualização de dispositivos para a organização devem ser publicados no DNS se o acesso externo deve ser habilitado. Além disso, o Servidor de Borda deve implantado e configurado corretamente para permitir comunicações externas do dispositivo para o ambiente corporativo e vice-versa. Isto é omitido no diagrama anterior porque a implantação de Borda não é específica para conectividade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5dee8-p103">The location of the Registrar and the URL of the Device Update Web service for the organization must be published in DNS if external access is to be enabled. Additionally, the Edge Server must be deployed and correctly configured to allow external communications from the device to the corporate environment and back. This is omitted from the previous diagram because Edge deployment is not specific to device connectivity.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

