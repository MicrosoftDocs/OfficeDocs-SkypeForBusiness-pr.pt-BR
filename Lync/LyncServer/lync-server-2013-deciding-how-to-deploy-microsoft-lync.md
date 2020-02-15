---
title: 'Lync Server 2013: decidindo como implantar o Microsoft Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deciding how to deploy Microsoft Lync
ms:assetid: 6ca677d3-745d-4935-8f05-19274a8bccf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204979(v=OCS.15)
ms:contentKeyID: 48184423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a731b4385dbe46da39fc195e1de6be13057e649d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044103"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deciding-how-to-deploy-lync-server-2013"></a><span data-ttu-id="6c7ab-102">Decidindo como implantar o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c7ab-102">Deciding how to deploy Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c7ab-103">_**Última modificação do tópico:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="6c7ab-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="6c7ab-104">Ao planejar o Lync, a primeira decisão importante é como implantar o Microsoft Lync: como Lync Server 2013 local ou Lync Online com o Microsoft Office 365 na nuvem.</span><span class="sxs-lookup"><span data-stu-id="6c7ab-104">When planning for Lync, the first major decision is how to deploy Microsoft Lync: as Lync Server 2013 on premises, or Lync Online with Microsoft Office 365 in the cloud.</span></span>

  - <span data-ttu-id="6c7ab-105">**Lync Server 2013 local** : essa opção oferece o conjunto de recursos completo do Lync e oferece a maior flexibilidade na configuração, personalização e operação da implantação.</span><span class="sxs-lookup"><span data-stu-id="6c7ab-105">**Lync Server 2013 on-premises** : This choice provides the complete Lync feature set and provides ultimate flexibility in configuring, customizing, and operating your deployment.</span></span> <span data-ttu-id="6c7ab-106">Todos os servidores são instalados no local e mantidos por sua organização.</span><span class="sxs-lookup"><span data-stu-id="6c7ab-106">All servers are installed onsite and maintained by your organization.</span></span> <span data-ttu-id="6c7ab-107">Uma implantação local fornece a gama completa de recursos do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6c7ab-107">An on-premises deployment provides the full range of Lync Server features.</span></span>

  - <span data-ttu-id="6c7ab-108">**Lync Online na nuvem** O Lync Online foi projetado para organizações que desejam os benefícios de custo e agilidade de mensagens instantâneas, presença e reuniões em nuvem sem sacrificar os recursos de classe de negócios do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6c7ab-108">**Lync Online in the cloud** Lync Online is designed for organizations that want the cost and agility benefits of cloud-based instant messaging, presence, and meetings without sacrificing the business-class capabilities of Lync Server.</span></span> <span data-ttu-id="6c7ab-109">Com o Lync Online, a Microsoft implanta e mantém a infraestrutura de servidor necessária e lida com manutenção, patches e atualizações em andamento.</span><span class="sxs-lookup"><span data-stu-id="6c7ab-109">With Lync Online, Microsoft deploys and maintains the required server infrastructure, and handles ongoing maintenance, patches, and upgrades.</span></span> <span data-ttu-id="6c7ab-110">Alguns recursos disponíveis em uma implantação local não estão disponíveis no Lync Online.</span><span class="sxs-lookup"><span data-stu-id="6c7ab-110">Some features available in an on-premises deployment are not available in Lync Online.</span></span>

<span data-ttu-id="6c7ab-111">O melhor tipo de implantação para você depende das cargas de trabalho que deseja implantar e da situação geográfica e de negócios de sua organização.</span><span class="sxs-lookup"><span data-stu-id="6c7ab-111">Which type of deployment would be best for you depends on the workloads you want to deploy, and your organization’s geographical and business status.</span></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="6c7ab-112">Lync Server</span><span class="sxs-lookup"><span data-stu-id="6c7ab-112">Lync Server</span></span>

<span data-ttu-id="6c7ab-113">Uma implantação do Lync Server no local é melhor nas seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="6c7ab-113">An on-premises Lync Server deployment is best for the following scenarios:</span></span>

  - <span data-ttu-id="6c7ab-114">**Recursos completos do Enterprise Voice**   se você planeja implantar uma solução Enterprise Voice completa para substituir seu PBX ou que usa recursos de chamada avançados, uma implantação do Lync Server local é necessária.</span><span class="sxs-lookup"><span data-stu-id="6c7ab-114">**Full Enterprise Voice Capabilities**   If you plan to deploy a full Enterprise Voice solution to replace your PBX or which uses advanced calling features, an on-premises Lync Server deployment is required.</span></span> <span data-ttu-id="6c7ab-115">Esse tipo de implantação oferece suporte a conectividade direta com sistemas e troncos PBX, além de recursos de telefonia avançados como grupos de resposta e estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="6c7ab-115">On-premises supports direct connectivity with PBX systems and trunks, and advanced phone features such as response groups and call park.</span></span> <span data-ttu-id="6c7ab-116">No momento, o Lync Online não dá suporte a esses recursos.</span><span class="sxs-lookup"><span data-stu-id="6c7ab-116">Lync Online does not currently support these features.</span></span>

  - <span data-ttu-id="6c7ab-117">**Controles de qualidade de mídia**   se você quiser a gama completa de recursos de garantia de qualidade de mídia, como o CAC (controle de admissão de chamadas) e recursos de QoS (qualidade de serviço), você deverá ter uma implantação local.</span><span class="sxs-lookup"><span data-stu-id="6c7ab-117">**Media Quality Controls**   If you want the full range of media quality assurance features, such as Call Admission Control (CAC) and Quality of Service (QoS) features, you will want an on-premises deployment .</span></span>

  - <span data-ttu-id="6c7ab-118">**Chat persistente se**   você precisar implantar o chat persistente para sua organização, você deve escolher uma implantação local.</span><span class="sxs-lookup"><span data-stu-id="6c7ab-118">**Persistent Chat**   If you need to deploy Persistent chat for your organization, you must choose an on-premises deployment.</span></span>

  - <span data-ttu-id="6c7ab-119">**aplicativos de servidor de terceiros**   apenas implantações locais podem funcionar com aplicativos de terceiros confiáveis que usam o Microsoft Unified Communications Managed API (UCMA).</span><span class="sxs-lookup"><span data-stu-id="6c7ab-119">**3rd-Party Server Applications**   Only on-premises deployments can work with trusted 3rd-party applications that use the Microsoft Unified Communications Managed API (UCMA).</span></span>

  - <span data-ttu-id="6c7ab-120">**Empresas multinacionais/multiregionals que precisam de suporte**   regional se você tiver data centers em vários países ou regiões e precisar que os servidores sejam implantados e gerenciados de forma regional, uma implantação local é melhor, pois fornece esse tipo de recurso de gerenciamento regional.</span><span class="sxs-lookup"><span data-stu-id="6c7ab-120">**Multi-National/Multi-Regional Companies Needing Regional Support**   If you have datacenters in multiple countries or regions and need servers to be deployed and managed on a regional basis, an on-premises deployment is best, as it provides this type of regional management capabilities.</span></span>

  - <span data-ttu-id="6c7ab-121">**Controle completo sobre políticas, relatórios e atualizações**   com uma implantação do Lync Server local, você tem acesso ao conjunto completo de políticas de servidor e cliente, monitoramento e outros relatórios e tempo de atualização.</span><span class="sxs-lookup"><span data-stu-id="6c7ab-121">**Complete control over policies, reports, and upgrades**   With an on premises Lync Server deployment, you have access to the full set of server and client policies, Monitoring and other reports, and timing of upgrades.</span></span> <span data-ttu-id="6c7ab-122">O Lync Online fornece um subconjunto de relatórios e configuração de política e fornece uma janela limitada, embora significativa, para aceitar atualizações.</span><span class="sxs-lookup"><span data-stu-id="6c7ab-122">Lync Online provides a subset of policy setting and reports, and provides a limited, though significant, window for accepting upgrades.</span></span>

</div>

<div>

## <a name="lync-online"></a><span data-ttu-id="6c7ab-123">Lync Online</span><span class="sxs-lookup"><span data-stu-id="6c7ab-123">Lync Online</span></span>

<span data-ttu-id="6c7ab-124">Caso nenhum dos fatores na lista anterior seja essencial para você, escolha o Lync Online, que possui implantação e gerenciamento mais simples.</span><span class="sxs-lookup"><span data-stu-id="6c7ab-124">If none of the factors in the preceding list are critical for you, you may want to choose Lync Online, for simpler deployment and manageability.</span></span> <span data-ttu-id="6c7ab-125">O Lync Online fornece um conjunto de recursos robusto de IM, presença e conferência, além de permitir chamadas de vídeo e voz sobre IP entre usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="6c7ab-125">Lync Online provides a robust IM, presence and conferencing feature set, and also enables voice and video calls over IP between users in your organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

