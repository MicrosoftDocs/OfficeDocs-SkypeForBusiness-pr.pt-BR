---
title: 'Lync Server 2013: Implantando Servidores de Mediação e definindo pares'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Mediation Servers and defining peers
ms:assetid: a684f1da-6671-4011-adf6-2db49e2528e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412780(v=OCS.15)
ms:contentKeyID: 48185077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b01ccf2e3822933842249df012877b13d10baef3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-mediation-servers-and-defining-peers-in-lync-server-2013"></a><span data-ttu-id="c4297-102">Implantando Servidores de Mediação e definindo pares no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4297-102">Deploying Mediation Servers and defining peers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4297-103">_**Tópico da última modificação:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="c4297-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="c4297-104">A carga de trabalho do Enterprise Voice, a conferência discada e os aplicativos avançados do Enterprise Voice (aplicativo do grupo de resposta, o aplicativo de estacionamento de chamadas, o controle de admissão de chamadas (CAC) e assim por diante) estão disponíveis em pools front-ends.</span><span class="sxs-lookup"><span data-stu-id="c4297-104">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="c4297-105">Com o Lync Server 2013, a funcionalidade do servidor de mediação é incorporada ao servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="c4297-105">With Lync Server 2013, the functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="c4297-106">Um servidor de mediação autônomo separado não é mais necessário.</span><span class="sxs-lookup"><span data-stu-id="c4297-106">A separate stand-alone Mediation Server is no longer necessary.</span></span> <span data-ttu-id="c4297-107">Os pools front-ends podem se comunicar diretamente com gateways compatíveis (um gateway PSTN (rede telefônica pública comutada) ou um IP-PBX, removendo a necessidade de um servidor de mediação funcionar como intermediário.</span><span class="sxs-lookup"><span data-stu-id="c4297-107">Front End pools can communicate directly with supported gateways (a public switched telephone network (PSTN) gateway or an IP-PBX), removing the need for a Mediation Server to serve as an intermediary.</span></span>

<span data-ttu-id="c4297-108">A única exceção é se você configurar um tronco SIP para se conectar a um Controlador de Borda de Sessão de um Provedor de Serviços de Telefonia e Internet.</span><span class="sxs-lookup"><span data-stu-id="c4297-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="c4297-109">Para conectar sua infraestrutura do Enterprise Voice ao seu provedor de tronco SIP, um servidor de mediação separado deve ser implantado.</span><span class="sxs-lookup"><span data-stu-id="c4297-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>

<span data-ttu-id="c4297-110">A conexão entre o Lync Server (o componente do servidor de mediação em um pool de front-end ou um servidor de mediação autônomo) e um gateway é definido como uma associação lógica chamada de *tronco*.</span><span class="sxs-lookup"><span data-stu-id="c4297-110">The connection between Lync Server (the Mediation Server component on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a *trunk*.</span></span> <span data-ttu-id="c4297-111">Os tópicos desta seção descrevem como definir um tronco e como implantar um servidor de mediação autônomo, se você se conectar a um tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="c4297-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c4297-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="c4297-112">In This Section</span></span>

  - [<span data-ttu-id="c4297-113">Definir um servidor de mediação no construtor de topologias no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4297-113">Define a Mediation Server in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [<span data-ttu-id="c4297-114">Definir um gateway no construtor de topologias no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4297-114">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [<span data-ttu-id="c4297-115">Instalar os arquivos do servidor de mediação no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4297-115">Install the files for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-install-the-files-for-mediation-server.md)

  - [<span data-ttu-id="c4297-116">Definir troncos adicionais no construtor de topologias no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4297-116">Define additional trunks in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-additional-trunks-in-topology-builder.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="c4297-117">Seções Relacionadas</span><span class="sxs-lookup"><span data-stu-id="c4297-117">Related Sections</span></span>

[<span data-ttu-id="c4297-118">Configurando conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4297-118">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

