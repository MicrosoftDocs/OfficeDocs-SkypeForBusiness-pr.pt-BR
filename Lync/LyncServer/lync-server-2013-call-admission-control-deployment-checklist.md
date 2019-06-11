---
title: 'Lync Server 2013: lista de verificação de implantação de controle de admissão de chamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call admission control deployment checklist
ms:assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398928(v=OCS.15)
ms:contentKeyID: 48185525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cdda2e5231beb9f8303684ff29075c6322654945
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836716"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="14da2-102">Lista de verificação de implantação de controle de admissão de chamadas para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14da2-102">Call admission control deployment checklist for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14da2-103">_**Tópico da última modificação:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="14da2-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="14da2-104">Use a lista de verificação a seguir para verificar se você concluiu todas as tarefas de configuração necessárias para implantar o controle de admissão de chamadas (CAC).</span><span class="sxs-lookup"><span data-stu-id="14da2-104">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy call admission control (CAC).</span></span>

  - <span data-ttu-id="14da2-105">Se um ou mais servidores Edge estiverem implantados, cada endereço IP de interface externa precisará ser adicionado à lista de sub-rede nas configurações de configuração de rede, com uma máscara de bits de 32.</span><span class="sxs-lookup"><span data-stu-id="14da2-105">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32.</span></span> <span data-ttu-id="14da2-106">Associe também essa sub-rede (endereço IP) ao ID do site da rede para o local geográfico onde o serviço de Borda A/V está implantado.</span><span class="sxs-lookup"><span data-stu-id="14da2-106">You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="14da2-107">Os servidores de borda não precisam implementar o CAC.</span><span class="sxs-lookup"><span data-stu-id="14da2-107">Edge servers are not required to implement CAC.</span></span>

    
    </div>

  - <span data-ttu-id="14da2-108">Verifique se o CAC está habilitado, seja por meio do painel de controle do Lync Server ou executando o cmdlet conforme especificado em [habilitar o controle de admissão de chamadas no Lync Server 2013](lync-server-2013-enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="14da2-108">Make sure that CAC is enabled, either through Lync Server Control Panel or by running the cmdlet as specified in [Enable call admission control in Lync Server 2013](lync-server-2013-enable-call-admission-control.md).</span></span>

  - <span data-ttu-id="14da2-109">Certifique-se de que o CAC está habilitado em todos os sites centrais.</span><span class="sxs-lookup"><span data-stu-id="14da2-109">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="14da2-110">Isso pode ser feito por meio do construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="14da2-110">This can be done through the Topology Builder.</span></span> <span data-ttu-id="14da2-111">Se um aviso for gerado durante a publicação, *não* ignore-o.</span><span class="sxs-lookup"><span data-stu-id="14da2-111">If a warning is generated when you publish, *do not* ignore it.</span></span>

  - <span data-ttu-id="14da2-112">Certifique-se de que todas as subredes gerenciadas na rede corporativa estão definidas nas configurações de rede.</span><span class="sxs-lookup"><span data-stu-id="14da2-112">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="14da2-113">Também é essencial que cada sub-rede seja associada a um site de rede, conforme explicado em [associar uma sub-rede a um site de rede no Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="14da2-113">It is also essential that every subnet be associated to a network site, as explained in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

  - <span data-ttu-id="14da2-114">Certifique-se de que a subrede ou os endereços IP de todos os Servidores Front-End, Aparelhos de Filial Persistentes (SBAs), Servidores de Conferência de Áudio/Vídeo (se estiverem em um pool separado) e Servidores de Mediação estejam definidos nas configurações de rede.</span><span class="sxs-lookup"><span data-stu-id="14da2-114">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

