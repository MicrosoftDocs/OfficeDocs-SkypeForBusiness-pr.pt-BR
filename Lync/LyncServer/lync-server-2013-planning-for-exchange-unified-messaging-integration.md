---
title: 'Lync Server 2013: Planejamento para integração de Unificação de Mensagens do Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Exchange Unified Messaging integration
ms:assetid: e7c63a71-2d99-4aa9-b649-36c1a431bdf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399031(v=OCS.15)
ms:contentKeyID: 48185880
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de7f3bc9a3e8a1330fc1a142c491e22a4407f104
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824859"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-exchange-unified-messaging-integration-in-lync-server-2013"></a><span data-ttu-id="d5c00-102">Planejamento para integração de Unificação de Mensagens do Exchange no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5c00-102">Planning for Exchange Unified Messaging integration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5c00-103">_**Tópico da última modificação:** 2012-10-13_</span><span class="sxs-lookup"><span data-stu-id="d5c00-103">_**Topic Last Modified:** 2012-10-13_</span></span>

<span data-ttu-id="d5c00-104">O Lync Server 2013 oferece suporte à integração com o Exchange Unified Messaging (UM) para combinar mensagens de voz e mensagens de email em uma única infra-estrutura de mensagens.</span><span class="sxs-lookup"><span data-stu-id="d5c00-104">Lync Server 2013 supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="d5c00-105">No Microsoft Exchange Server 2007 Service Pack 1 (SP1) e no Microsoft Exchange Server 2010, o Exchange Unified Messaging (UM) é uma das várias funções do Exchange Server que você pode instalar e configurar.</span><span class="sxs-lookup"><span data-stu-id="d5c00-105">In Microsoft Exchange Server 2007 Service Pack 1 (SP1) and Microsoft Exchange Server 2010, Exchange Unified Messaging (UM) is one of several Exchange server roles that you can install and configure.</span></span>

<span data-ttu-id="d5c00-106">No Microsoft Exchange Server 2013, o Exchange UM é executado como um serviço em um servidor de caixa de correio do Exchange.</span><span class="sxs-lookup"><span data-stu-id="d5c00-106">In Microsoft Exchange Server 2013, Exchange UM runs as a service on an Exchange Mailbox server.</span></span> <span data-ttu-id="d5c00-107">Para implantações do Lync Server 2013 Enterprise Voice, a Unificação de mensagens combina mensagens de voz e mensagens de email em uma única loja que está disponível em um telefone (Outlook Voice Access) ou computador.</span><span class="sxs-lookup"><span data-stu-id="d5c00-107">For Lync Server 2013 Enterprise Voice deployments, Unified Messaging combines voice messaging and email messaging into a single store that is available from a telephone (Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="d5c00-108">A Unificação de mensagens e o Lync Server 2013 trabalham juntos para fornecer atendimento de chamada, Outlook Voice Access e serviços de atendedor automático para usuários do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="d5c00-108">Unified Messaging and Lync Server 2013 work together to provide call answering, Outlook Voice Access, and auto-attendant services to users of Enterprise Voice.</span></span>

<span data-ttu-id="d5c00-109">Para obter mais informações sobre as mudanças de arquitetura no Microsoft Exchange Server 2013, consulte "mudanças de arquitetura de voz" na documentação do Microsoft [http://go.microsoft.com/fwlink/p/?LinkId=266730](http://go.microsoft.com/fwlink/p/?linkid=266730)exchange server 2013 em.</span><span class="sxs-lookup"><span data-stu-id="d5c00-109">For more information about the architecture changes in Microsoft Exchange Server 2013, see “Voice Architecture Changes” in the Microsoft Exchange Server 2013 documentation at [http://go.microsoft.com/fwlink/p/?LinkId=266730](http://go.microsoft.com/fwlink/p/?linkid=266730).</span></span>

<span data-ttu-id="d5c00-110">Para que esses recursos tenham suporte em uma implantação do Exchange UM local, você deve estar executando um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="d5c00-110">For these features to be supported in an on-premises Exchange UM deployment, you must be running one of the following:</span></span>

  - <span data-ttu-id="d5c00-111">Microsoft Exchange Server 2007 Service Pack 1 (SP1) ou Service Pack mais recente</span><span class="sxs-lookup"><span data-stu-id="d5c00-111">Microsoft Exchange Server 2007 Service Pack 1 (SP1) or latest service pack</span></span>

  - <span data-ttu-id="d5c00-112">Microsoft Exchange Server 2010 ou Service Pack mais recente</span><span class="sxs-lookup"><span data-stu-id="d5c00-112">Microsoft Exchange Server 2010 or latest service pack</span></span>

  - <span data-ttu-id="d5c00-113">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5c00-113">Microsoft Exchange Server 2013</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d5c00-114">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="d5c00-114">In This Section</span></span>

  - [<span data-ttu-id="d5c00-115">Recursos de Unificação de Mensagens integrada e do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5c00-115">Features of integrated Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-features-of-integrated-unified-messaging.md)

  - [<span data-ttu-id="d5c00-116">Componentes e topologias para o Sistema de Mensagens Instantâneas local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5c00-116">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [<span data-ttu-id="d5c00-117">Orientações para integração de Unificação de Mensagens local e Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5c00-117">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

  - [<span data-ttu-id="d5c00-118">Processo de implantação para integração de Unificação de Mensagens local com Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5c00-118">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

