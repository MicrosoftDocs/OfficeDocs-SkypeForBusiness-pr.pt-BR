---
title: 'Lync Server 2013: lista de verificação de implantação de controle de admissão de chamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control deployment checklist
ms:assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398928(v=OCS.15)
ms:contentKeyID: 48185525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75e5250bf82353876e36109a6b2e34442e5ef7dc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135027"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-admission-control-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="f5a25-102">Lista de verificação de implantação do controle de admissão de chamadas para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5a25-102">Call admission control deployment checklist for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5a25-103">_**Última modificação do tópico:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="f5a25-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="f5a25-104">Consulte a lista de verificação para confirmar se você concluiu todas as tarefas de configuração necessárias para a implantação do controle de admissão de chamadas.</span><span class="sxs-lookup"><span data-stu-id="f5a25-104">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy call admission control (CAC).</span></span>

  - <span data-ttu-id="f5a25-p101">Se um ou mais Servidores de Borda for implantado, cada endereço IP de interface externa precisa ser adicionado à lista de subredes nas configurações de rede, com uma bitmask de 32. Associe também essa sub-rede (endereço IP) ao ID do site de rede para o local geográfico onde o serviço Borda A/V está implantado.</span><span class="sxs-lookup"><span data-stu-id="f5a25-p101">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32. You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f5a25-107">Os Servidores de Borda não são necessários para implementar o CAC.</span><span class="sxs-lookup"><span data-stu-id="f5a25-107">Edge servers are not required to implement CAC.</span></span>

    
    </div>

  - <span data-ttu-id="f5a25-108">Certifique-se de que o CAC está habilitado, seja por meio do painel de controle do Lync Server ou executando o cmdlet conforme especificado em [habilitar controle de admissão de chamadas no Lync Server 2013](lync-server-2013-enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="f5a25-108">Make sure that CAC is enabled, either through Lync Server Control Panel or by running the cmdlet as specified in [Enable call admission control in Lync Server 2013](lync-server-2013-enable-call-admission-control.md).</span></span>

  - <span data-ttu-id="f5a25-109">Certifique-se de que o CAC está habilitado em todos os sites centrais.</span><span class="sxs-lookup"><span data-stu-id="f5a25-109">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="f5a25-110">Isso pode ser feito por meio do construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="f5a25-110">This can be done through the Topology Builder.</span></span> <span data-ttu-id="f5a25-111">Se um aviso é gerado ao publicar, *não* ignore-o.</span><span class="sxs-lookup"><span data-stu-id="f5a25-111">If a warning is generated when you publish, *do not* ignore it.</span></span>

  - <span data-ttu-id="f5a25-112">Certifique-se de que todas as subredes gerenciadas na rede empresarial estão definidas nas configurações de rede.</span><span class="sxs-lookup"><span data-stu-id="f5a25-112">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="f5a25-113">Também é essencial que todas as sub-redes estejam associadas a um site de rede, conforme explicado em [associar uma sub-rede a um site de rede no Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="f5a25-113">It is also essential that every subnet be associated to a network site, as explained in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

  - <span data-ttu-id="f5a25-114">Certifique-se de que a subrede ou os endereços IP de todos os Servidores de Front-End, Aparelhos de Filial Persistentes (SBAs), Servidores de Conferência de Áudio/Vídeo (se estiverem em um pool separado) e Servidores de Mediação estejam definidos nas configurações de rede.</span><span class="sxs-lookup"><span data-stu-id="f5a25-114">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

