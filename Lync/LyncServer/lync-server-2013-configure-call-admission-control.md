---
title: 'Lync Server 2013: configurar controle de admissão de chamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure call admission control
ms:assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398870(v=OCS.15)
ms:contentKeyID: 48185464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1edac7fe7b3b56cdaa5324f1c6e976bfb0b746fe
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517658"
---
# <a name="configure-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="202cf-102">Configurar o controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="202cf-102">Configure call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="202cf-103">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="202cf-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="202cf-104">O controle de admissão de chamadas é uma solução que determina se uma sessão em tempo real pode ou não ser estabelecida com base na largura de banda disponível, para ajudar a evitar uma qualidade audiovisual ruim para os usuários em redes congestionadas.</span><span class="sxs-lookup"><span data-stu-id="202cf-104">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="202cf-105">O controle de admissão de chamadas controla o tráfego em tempo real somente de áudio e vídeo e não afeta o tráfego de dados.</span><span class="sxs-lookup"><span data-stu-id="202cf-105">CAC controls real-time traffic only for audio and video, and does not affect data traffic.</span></span> <span data-ttu-id="202cf-106">O controle de admissão de chamadas pode rotear a chamada através de um caminho da Internet quando o caminho WAN padrão não tem a largura de banda necessária.</span><span class="sxs-lookup"><span data-stu-id="202cf-106">CAC may route the call through an Internet path when the default WAN path does not have the required bandwidth.</span></span> <span data-ttu-id="202cf-107">Para obter detalhes, consulte [Planning for Call Admission Control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="202cf-107">For details, see [Planning for call admission control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="202cf-108">Esta seção fornece um conjunto de procedimentos de exemplo que ilustram como implantar e gerenciar o CAC em sua rede.</span><span class="sxs-lookup"><span data-stu-id="202cf-108">This section provides a set of example procedures that illustrate how to deploy and manage CAC in your network.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="202cf-109">Antes de implantar o CAC, você deve coletar todas as informações necessárias para sua topologia de rede corporativa, conforme descrito em <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">exemplo: reunindo seus requisitos para controle de admissão de chamadas no Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="202cf-109">Before you deploy CAC, you must gather all of the required information for your enterprise network topology, as described in <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">Example: Gathering your requirements for call admission control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="202cf-110">Além disso, certifique-se de que os componentes do CAC foram instalados e ativados, conforme descrito em <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definir e configurar um pool de front-ends ou servidor Standard Edition no Lync server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="202cf-110">Also be sure that CAC components have been installed and activated, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="202cf-111">Todos os exemplos de implantação e gerenciamento do CAC nesta seção são executados usando o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="202cf-111">All CAC deployment and management examples in this section are performed by using the Lync Server Management Shell.</span></span> <span data-ttu-id="202cf-112">Como alternativa, você também pode usar a seção <STRONG>configuração de rede</STRONG> do painel de controle do Lync Server para gerenciar o CAC.</span><span class="sxs-lookup"><span data-stu-id="202cf-112">As an alternative, you can also use the <STRONG>Network Configuration</STRONG> section of Lync Server Control Panel to manage CAC.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="202cf-113">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="202cf-113">In This Section</span></span>

  - [<span data-ttu-id="202cf-114">Configurar regiões de rede para CAC no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="202cf-114">Configure network regions for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-regions-for-cac.md)

  - [<span data-ttu-id="202cf-115">Criar perfis de política de largura de banda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="202cf-115">Create bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [<span data-ttu-id="202cf-116">Configurar sites de rede para CAC no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="202cf-116">Configure network sites for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-sites-for-cac.md)

  - [<span data-ttu-id="202cf-117">Associar sub-redes a sites de rede para CAC no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="202cf-117">Associate subnets with network sites for CAC in Lync Server 2013</span></span>](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [<span data-ttu-id="202cf-118">Criar links de região de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="202cf-118">Create network region links in Lync Server 2013</span></span>](lync-server-2013-create-network-region-links.md)

  - [<span data-ttu-id="202cf-119">Criar rotas entre regiões de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="202cf-119">Create network interregion routes in Lync Server 2013</span></span>](lync-server-2013;-create-network-interregion-routes.md)

  - [<span data-ttu-id="202cf-120">Criar políticas entre sites de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="202cf-120">Create network intersite policies in Lync Server 2013</span></span>](lync-server-2013-create-network-intersite-policies.md)

  - [<span data-ttu-id="202cf-121">Habilitar controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="202cf-121">Enable call admission control in Lync Server 2013</span></span>](lync-server-2013-enable-call-admission-control.md)

  - [<span data-ttu-id="202cf-122">Lista de verificação de implantação do controle de admissão de chamadas para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="202cf-122">Call admission control deployment checklist for Lync Server 2013</span></span>](lync-server-2013-call-admission-control-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

