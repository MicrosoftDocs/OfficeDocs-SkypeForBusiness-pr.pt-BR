---
title: 'Lync Server 2013: implantando servidores de mediação e definindo pares'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Mediation Servers and defining peers
ms:assetid: a684f1da-6671-4011-adf6-2db49e2528e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412780(v=OCS.15)
ms:contentKeyID: 48185077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03eca427f644d6f94ae7a52900b80320e2517ed2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195324"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-mediation-servers-and-defining-peers-in-lync-server-2013"></a><span data-ttu-id="5164e-102">Implantando servidores de mediação e definindo pares no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5164e-102">Deploying Mediation Servers and defining peers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5164e-103">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="5164e-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="5164e-104">A carga de trabalho do Enterprise Voice, conferência discada e aplicativos avançados do Enterprise Voice (aplicativo de grupo de resposta, aplicativo de estacionamento de chamada, controle de admissão de chamadas (CAC) e assim por diante), estão disponíveis em pools de front-ends.</span><span class="sxs-lookup"><span data-stu-id="5164e-104">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="5164e-105">Com o Lync Server 2013, a funcionalidade do servidor de mediação está incorporada ao servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="5164e-105">With Lync Server 2013, the functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="5164e-106">Um servidor de mediação autônomo separado não é mais necessário.</span><span class="sxs-lookup"><span data-stu-id="5164e-106">A separate stand-alone Mediation Server is no longer necessary.</span></span> <span data-ttu-id="5164e-107">Os pools de front-ends podem se comunicar diretamente com os gateways com suporte (um gateway PSTN (rede telefônica pública comutada) ou um IP-PBX, removendo a necessidade de um servidor de mediação servir como intermediário.</span><span class="sxs-lookup"><span data-stu-id="5164e-107">Front End pools can communicate directly with supported gateways (a public switched telephone network (PSTN) gateway or an IP-PBX), removing the need for a Mediation Server to serve as an intermediary.</span></span>

<span data-ttu-id="5164e-108">A única exceção é se você configurar um tronco SIP para se conectar a um Controlador de Borda de Sessão de um Provedor de Serviços de Telefonia e Internet.</span><span class="sxs-lookup"><span data-stu-id="5164e-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="5164e-109">Para conectar sua infraestrutura do Enterprise Voice ao seu provedor de tronco SIP, um servidor de mediação separado deve ser implantado.</span><span class="sxs-lookup"><span data-stu-id="5164e-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>

<span data-ttu-id="5164e-110">A conexão entre o Lync Server (o componente do servidor de mediação em um pool de front-ends ou servidor de mediação autônomo) e um gateway é definido como uma associação lógica chamada de *tronco*.</span><span class="sxs-lookup"><span data-stu-id="5164e-110">The connection between Lync Server (the Mediation Server component on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a *trunk*.</span></span> <span data-ttu-id="5164e-111">Os tópicos nesta seção descrevem como definir um tronco e como implantar um Servidor de Mediação autônomo, se você se conectar a um tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="5164e-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5164e-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="5164e-112">In This Section</span></span>

  - [<span data-ttu-id="5164e-113">Definir um servidor de mediação no construtor de topologias no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5164e-113">Define a Mediation Server in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [<span data-ttu-id="5164e-114">Definir um gateway no construtor de topologia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5164e-114">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [<span data-ttu-id="5164e-115">Instalar os arquivos para o servidor de mediação no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5164e-115">Install the files for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-install-the-files-for-mediation-server.md)

  - [<span data-ttu-id="5164e-116">Definir troncos adicionais no construtor de topologias no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5164e-116">Define additional trunks in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-additional-trunks-in-topology-builder.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="5164e-117">Seções Relacionadas</span><span class="sxs-lookup"><span data-stu-id="5164e-117">Related Sections</span></span>

[<span data-ttu-id="5164e-118">Configurando a conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5164e-118">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

