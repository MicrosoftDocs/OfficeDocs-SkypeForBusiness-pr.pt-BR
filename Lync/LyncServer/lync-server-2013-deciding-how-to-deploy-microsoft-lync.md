---
title: 'Lync Server 2013: Decidindo como implantar o Microsoft Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deciding how to deploy Microsoft Lync
ms:assetid: 6ca677d3-745d-4935-8f05-19274a8bccf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204979(v=OCS.15)
ms:contentKeyID: 48184423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d641f4da1884c1fb6e84eefb2127490f2ed3c4a9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829730"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deciding-how-to-deploy-lync-server-2013"></a><span data-ttu-id="cccd2-102">Decidindo como implantar o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cccd2-102">Deciding how to deploy Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cccd2-103">_**Tópico da última modificação:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="cccd2-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="cccd2-104">Ao planejar o Lync, a primeira decisão importante é como implantar o Microsoft Lync: como o Lync Server 2013 local ou o Lync Online com o Microsoft Office 365 na nuvem.</span><span class="sxs-lookup"><span data-stu-id="cccd2-104">When planning for Lync, the first major decision is how to deploy Microsoft Lync: as Lync Server 2013 on premises, or Lync Online with Microsoft Office 365 in the cloud.</span></span>

  - <span data-ttu-id="cccd2-105">**Lync Server 2013 local** : esta opção fornece o conjunto de recursos completo do Lync e fornece a flexibilidade máxima para configurar, personalizar e operar a implantação.</span><span class="sxs-lookup"><span data-stu-id="cccd2-105">**Lync Server 2013 on-premises** : This choice provides the complete Lync feature set and provides ultimate flexibility in configuring, customizing, and operating your deployment.</span></span> <span data-ttu-id="cccd2-106">Todos os servidores são instalados no local e mantidos pela sua organização.</span><span class="sxs-lookup"><span data-stu-id="cccd2-106">All servers are installed onsite and maintained by your organization.</span></span> <span data-ttu-id="cccd2-107">Uma implantação local fornece a gama completa de recursos do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cccd2-107">An on-premises deployment provides the full range of Lync Server features.</span></span>

  - <span data-ttu-id="cccd2-108">**Lync Online na nuvem** O Lync Online foi projetado para organizações que desejam os benefícios de custo e agilidade das mensagens instantâneas, presença e reuniões em nuvem sem sacrificar os recursos de classe empresarial do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cccd2-108">**Lync Online in the cloud** Lync Online is designed for organizations that want the cost and agility benefits of cloud-based instant messaging, presence, and meetings without sacrificing the business-class capabilities of Lync Server.</span></span> <span data-ttu-id="cccd2-109">Com o Lync Online, a Microsoft implanta e mantém a infraestrutura de servidor necessária e manipula manutenção, patches e atualizações contínuas.</span><span class="sxs-lookup"><span data-stu-id="cccd2-109">With Lync Online, Microsoft deploys and maintains the required server infrastructure, and handles ongoing maintenance, patches, and upgrades.</span></span> <span data-ttu-id="cccd2-110">Alguns recursos disponíveis em uma implantação local não estão disponíveis no Lync Online.</span><span class="sxs-lookup"><span data-stu-id="cccd2-110">Some features available in an on-premises deployment are not available in Lync Online.</span></span>

<span data-ttu-id="cccd2-111">Qual tipo de implantação seria melhor para você depende das cargas de trabalho que você deseja implantar e o status geográfico e comercial da sua organização.</span><span class="sxs-lookup"><span data-stu-id="cccd2-111">Which type of deployment would be best for you depends on the workloads you want to deploy, and your organization’s geographical and business status.</span></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="cccd2-112">Servidor Lync</span><span class="sxs-lookup"><span data-stu-id="cccd2-112">Lync Server</span></span>

<span data-ttu-id="cccd2-113">Uma implantação do Lync Server local é melhor para os seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="cccd2-113">An on-premises Lync Server deployment is best for the following scenarios:</span></span>

  - <span data-ttu-id="cccd2-114">**Recursos de voz de toda a empresa**   se você planeja implantar uma solução completa de voz empresarial para substituir seu PBX ou que usa recursos de chamada avançados, uma implantação do Lync Server local é necessária.</span><span class="sxs-lookup"><span data-stu-id="cccd2-114">**Full Enterprise Voice Capabilities**   If you plan to deploy a full Enterprise Voice solution to replace your PBX or which uses advanced calling features, an on-premises Lync Server deployment is required.</span></span> <span data-ttu-id="cccd2-115">O local é compatível com a conectividade direta com sistemas PBX e troncos e recursos de telefone avançados, como grupos de resposta e estacionamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="cccd2-115">On-premises supports direct connectivity with PBX systems and trunks, and advanced phone features such as response groups and call park.</span></span> <span data-ttu-id="cccd2-116">No momento, o Lync Online não oferece suporte a esses recursos.</span><span class="sxs-lookup"><span data-stu-id="cccd2-116">Lync Online does not currently support these features.</span></span>

  - <span data-ttu-id="cccd2-117">**Controles de qualidade de mídia**   se você quiser uma gama completa de recursos de garantia de qualidade de mídia, como o controle de admissão de chamadas (CAC) e os recursos de qualidade do serviço (QoS), será necessário uma implantação local.</span><span class="sxs-lookup"><span data-stu-id="cccd2-117">**Media Quality Controls**   If you want the full range of media quality assurance features, such as Call Admission Control (CAC) and Quality of Service (QoS) features, you will want an on-premises deployment .</span></span>

  - <span data-ttu-id="cccd2-118">**Chat persistente se**   você precisar implantar o chat persistente para a sua organização, você deve escolher uma implantação local.</span><span class="sxs-lookup"><span data-stu-id="cccd2-118">**Persistent Chat**   If you need to deploy Persistent chat for your organization, you must choose an on-premises deployment.</span></span>

  - <span data-ttu-id="cccd2-119">**aplicativos de servidor de terceiros**   somente implantações locais podem funcionar com aplicativos de terceiros confiáveis que usam a API gerenciada de comunicação unificada da Microsoft (UCMA).</span><span class="sxs-lookup"><span data-stu-id="cccd2-119">**3rd-Party Server Applications**   Only on-premises deployments can work with trusted 3rd-party applications that use the Microsoft Unified Communications Managed API (UCMA).</span></span>

  - <span data-ttu-id="cccd2-120">**Empresas multinacionais/multinacionais que precisam de suporte**   regional se você tiver datacenters em vários países ou regiões e precisar que os servidores sejam implantados e gerenciados de forma regional, uma implantação local é melhor, pois fornece esse tipo de recursos de gerenciamento regional.</span><span class="sxs-lookup"><span data-stu-id="cccd2-120">**Multi-National/Multi-Regional Companies Needing Regional Support**   If you have datacenters in multiple countries or regions and need servers to be deployed and managed on a regional basis, an on-premises deployment is best, as it provides this type of regional management capabilities.</span></span>

  - <span data-ttu-id="cccd2-121">**Controle completo sobre políticas, relatórios e atualizações**   com uma implantação local do Lync Server, você tem acesso ao conjunto completo de políticas de servidor e de cliente, monitoramento e outros relatórios e tempo de atualizações.</span><span class="sxs-lookup"><span data-stu-id="cccd2-121">**Complete control over policies, reports, and upgrades**   With an on premises Lync Server deployment, you have access to the full set of server and client policies, Monitoring and other reports, and timing of upgrades.</span></span> <span data-ttu-id="cccd2-122">O Lync Online fornece um subconjunto de relatórios e configurações de política e fornece uma janela limitada, embora significativa, para aceitar atualizações.</span><span class="sxs-lookup"><span data-stu-id="cccd2-122">Lync Online provides a subset of policy setting and reports, and provides a limited, though significant, window for accepting upgrades.</span></span>

</div>

<div>

## <a name="lync-online"></a><span data-ttu-id="cccd2-123">Lync Online</span><span class="sxs-lookup"><span data-stu-id="cccd2-123">Lync Online</span></span>

<span data-ttu-id="cccd2-124">Se nenhum dos fatores na lista anterior for essencial para você, talvez você queira escolher o Lync Online, para implantação e gerenciamento mais simples.</span><span class="sxs-lookup"><span data-stu-id="cccd2-124">If none of the factors in the preceding list are critical for you, you may want to choose Lync Online, for simpler deployment and manageability.</span></span> <span data-ttu-id="cccd2-125">O Lync Online oferece um conjunto robusto de recursos de chat, presença e conferência e também permite chamadas de voz e vídeo por IP entre os usuários da sua organização.</span><span class="sxs-lookup"><span data-stu-id="cccd2-125">Lync Online provides a robust IM, presence and conferencing feature set, and also enables voice and video calls over IP between users in your organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

