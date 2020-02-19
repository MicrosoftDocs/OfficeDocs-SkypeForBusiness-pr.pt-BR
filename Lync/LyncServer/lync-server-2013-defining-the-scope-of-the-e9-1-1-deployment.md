---
title: 'Lync Server 2013: definindo o escopo da implantação de E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the scope of the E9-1-1 deployment
ms:assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425775(v=OCS.15)
ms:contentKeyID: 48183707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c84c6519ab561fef034fbe0990854087f22b2e41
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-the-scope-of-the-e9-1-1-deployment-in-lync-server-2013"></a><span data-ttu-id="d5d4d-102">Definindo o escopo da implantação do E9-1-1 no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5d4d-102">Defining the scope of the E9-1-1 deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5d4d-103">_**Última modificação do tópico:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="d5d4d-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="d5d4d-104">Antes de configurar o Microsoft Lync Server 2013 para E9-1-1, você precisa planejar sua implantação do E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-104">Before you configure Microsoft Lync Server 2013 for E9-1-1, you need to plan your E9-1-1 deployment.</span></span> <span data-ttu-id="d5d4d-105">Algumas das questões a serem consideradas são:</span><span class="sxs-lookup"><span data-stu-id="d5d4d-105">Some of the questions to consider include:</span></span>

  - <span data-ttu-id="d5d4d-106">**Qual é a política de sua organização e as obrigações locais com relação ao E9-1-1?**</span><span class="sxs-lookup"><span data-stu-id="d5d4d-106">**What are your organization’s policy and legal obligations with regard to E9-1-1?**</span></span>  
    <span data-ttu-id="d5d4d-107">Os requisitos legais de E9-1-1 para PBXs (chamados de Multi-line Telephone Systems, ou MLTS, no linguajar de E9-1-1) diferem de acordo com o estado.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-107">E9-1-1 legal requirements for PBXs (called Multi-line Telephone Systems, or MLTS, in E9-1-1 parlance) differ from state to state.</span></span> <span data-ttu-id="d5d4d-108">Você deve consultar sua equipe jurídica para entender as obrigações que podem se aplicar à sua implantação do Lync Server em suas geografias relevantes.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-108">You should consult with your legal team to understand the obligations that may apply to your deployment of Lync Server in your relevant geographies.</span></span>

<!-- end list -->

  - <span data-ttu-id="d5d4d-109">**Quais áreas dentro de sua empresa precisam estar habilitadas para E9-1-1?**</span><span class="sxs-lookup"><span data-stu-id="d5d4d-109">**What areas within your enterprise need to be enabled for E9-1-1?**</span></span>  
    <span data-ttu-id="d5d4d-p103">É possível habilitar o E9-1-1 para toda a empresa ou para locais selecionados. Por exemplo, talvez você tenha requisitos variados de E9-1-1 para escritórios em estados diferentes ou queira excluir sites fora dos EUA.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-p103">You can enable E9-1-1 for the entire enterprise or for selected locations. For example, you may have varying E9-1-1 requirements for offices in different states, or you may want to exclude sites outside the U.S.</span></span>

<!-- end list -->

  - <span data-ttu-id="d5d4d-112">**Como você implantará o E9-1-1 em sites de filiais?**</span><span class="sxs-lookup"><span data-stu-id="d5d4d-112">**How will you deploy E9-1-1 to branch sites?**</span></span>  
    <span data-ttu-id="d5d4d-113">A resiliência de voz é um conceito importante para compreender quando implantar o E9-1-1 no site local.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-113">Voice resiliency is an important concept to understand when deploying E9-1-1 at a branch site.</span></span> <span data-ttu-id="d5d4d-114">Se houver troncos SIP e-9-1-1 intercentralizados e ocorrer uma interrupção de WAN, os clientes que estiverem entrando podem não conseguir obter um local do serviço de informações de local ou para se conectarem ao provedor de serviços de emergência.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-114">If you have centralized E-9-1-1 SIP trunks and a WAN outage occurs, clients signing in may not be able to obtain a location from Location Information service or to connect to the emergency services service provider.</span></span> <span data-ttu-id="d5d4d-115">O Lync Server oferece várias estratégias para lidar com a resiliência de voz em filiais, incluindo: redes de dados resistentes, implantação de um tronco SIP em cada filial ou envio de chamadas de emergência para o gateway local durante interrupções.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-115">Lync Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing emergency calls out to the local gateway during outages.</span></span> <span data-ttu-id="d5d4d-116">Para obter detalhes, consulte [Planning for Branch-site Voice resiliência no Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span><span class="sxs-lookup"><span data-stu-id="d5d4d-116">For details, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span></span>

<!-- end list -->

  - <span data-ttu-id="d5d4d-117">**Você habilitará o E9-1-1 para usuários trabalhando fora da rede?**</span><span class="sxs-lookup"><span data-stu-id="d5d4d-117">**Will you enable E9-1-1 for users working outside the network?**</span></span>  
    <span data-ttu-id="d5d4d-p105">A aquisição automática de local fica disponível somente para clientes localizados dentro da rede da organização, portanto, sua organização precisa decidir se suportará chamadas de E9-1-1 feitas de clientes Lync no local. Por exemplo, você habilitará usuários para fazer chamadas de emergência se eles estiverem trabalhando de cada ou no local de um cliente? Se um cliente estiver localizado fora da rede empresarial, ele poderá ser configurado para solicitar ao usuário um local. No entanto, como esses locais fornecidos pelo usuário não podem ser pré-validados com base no MSAG (Catálogo de Endereços Principal), o despachante do provedor de serviços de emergência necessitarão confirmar a validade do local verbalmente com o chamador antes de rotear a chamada para o PSAP (ponto de atendimento público seguro).</span><span class="sxs-lookup"><span data-stu-id="d5d4d-p105">Automatic location acquisition is available only for clients located inside the organization’s network, so your organization needs to decide whether it will support E9-1-1 calls made from Lync clients while off-premises. For example, will you enable users to place emergency calls if they are working from home or from a customer site? If a client is located outside the enterprise network, the client can be configured to prompt the user for a location. However, because these user-provided locations cannot be prevalidated against the Master Street Address Guide (MSAG), the emergency services service provider dispatcher will need to confirm the validity of the location verbally with the caller before routing the call to the Public Safety Answering Point (PSAP).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d5d4d-122">Os clientes do Lync de usuários que se conectam à rede da sua organização usando a VPN podem pegar informações de endereço IP interno, mas como esses endereços não podem ser usados para identificar o local real do usuário, é essencial que sub-redes VPN sejam excluídas do Serviço de informações de local.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-122">Lync clients of users who connect to your organization’s network by using VPN can pick up internal IP address information, but because these addresses cannot be used to identify the user’s actual location, it is essential that VPN subnets are excluded from the Location Information service.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="d5d4d-123">**Você deseja fornecer roteamento de chamada de emergência para sites fora dos EUA?**</span><span class="sxs-lookup"><span data-stu-id="d5d4d-123">**Do you want to provide emergency call routing to sites outside the U.S.?**</span></span>  
    <span data-ttu-id="d5d4d-p106">Talvez você queira fornecer roteamento de emergência para áreas de sua empresa que não são atendidas por um provedor de serviços de emergência (por exemplo, locais internacionais). Para fazer isso, crie um novo site e atribua políticas de voz aos sites que se referem a um uso do PSTN que roteia a chamada pelo gateway PSTN local.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-p106">You may want to provide emergency routing to areas of your company not served by an emergency services service provider (for example, international locations). To do this, create a new site, and then assign voice policies to the sites that refer to a PSTN usage that routes the call through the local PSTN gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

