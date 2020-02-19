---
title: 'Lync Server 2013: planejamento para integração de Unificação de mensagens do Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Exchange Unified Messaging integration
ms:assetid: e7c63a71-2d99-4aa9-b649-36c1a431bdf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399031(v=OCS.15)
ms:contentKeyID: 48185880
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e5e9c4e4e4a1e77f3ca7badc0a4549cb04cee94
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139844"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-exchange-unified-messaging-integration-in-lync-server-2013"></a><span data-ttu-id="33cc3-102">Planejamento da integração de Unificação de mensagens do Exchange no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33cc3-102">Planning for Exchange Unified Messaging integration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33cc3-103">_**Última modificação do tópico:** 2012-10-13_</span><span class="sxs-lookup"><span data-stu-id="33cc3-103">_**Topic Last Modified:** 2012-10-13_</span></span>

<span data-ttu-id="33cc3-104">O Lync Server 2013 oferece suporte à integração com a Unificação de mensagens (UM) do Exchange para combinar mensagens de voz e mensagens de email em uma única infraestrutura de mensagens.</span><span class="sxs-lookup"><span data-stu-id="33cc3-104">Lync Server 2013 supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="33cc3-105">No Microsoft Exchange Server 2007 Service Pack 1 (SP1) e no Microsoft Exchange Server 2010, a Unificação de mensagens (UM) do Exchange é uma das várias funções de servidor do Exchange que você pode instalar e configurar.</span><span class="sxs-lookup"><span data-stu-id="33cc3-105">In Microsoft Exchange Server 2007 Service Pack 1 (SP1) and Microsoft Exchange Server 2010, Exchange Unified Messaging (UM) is one of several Exchange server roles that you can install and configure.</span></span>

<span data-ttu-id="33cc3-106">No Microsoft Exchange Server 2013, o UM do Exchange é executado como um serviço em um servidor de caixa de correio do Exchange.</span><span class="sxs-lookup"><span data-stu-id="33cc3-106">In Microsoft Exchange Server 2013, Exchange UM runs as a service on an Exchange Mailbox server.</span></span> <span data-ttu-id="33cc3-107">Para implantações do Lync Server 2013 Enterprise Voice, a Unificação de mensagens combina mensagens de voz e mensagens de email em um único repositório disponível em um telefone (Outlook Voice Access) ou um computador.</span><span class="sxs-lookup"><span data-stu-id="33cc3-107">For Lync Server 2013 Enterprise Voice deployments, Unified Messaging combines voice messaging and email messaging into a single store that is available from a telephone (Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="33cc3-108">A Unificação de mensagens e o Lync Server 2013 trabalham juntos para fornecer atendimento de chamadas, Outlook Voice Access e serviços de atendedor automático para usuários do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="33cc3-108">Unified Messaging and Lync Server 2013 work together to provide call answering, Outlook Voice Access, and auto-attendant services to users of Enterprise Voice.</span></span>

<span data-ttu-id="33cc3-109">Para obter mais informações sobre as alterações de arquitetura no Microsoft Exchange Server 2013, consulte "mudanças de arquitetura de voz" na documentação do Microsoft [https://go.microsoft.com/fwlink/p/?LinkId=266730](https://go.microsoft.com/fwlink/p/?linkid=266730)Exchange Server 2013 em.</span><span class="sxs-lookup"><span data-stu-id="33cc3-109">For more information about the architecture changes in Microsoft Exchange Server 2013, see “Voice Architecture Changes” in the Microsoft Exchange Server 2013 documentation at [https://go.microsoft.com/fwlink/p/?LinkId=266730](https://go.microsoft.com/fwlink/p/?linkid=266730).</span></span>

<span data-ttu-id="33cc3-110">Para que esses recursos sejam suportados em uma implantação local do UM do Exchange, você deve estar executando um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="33cc3-110">For these features to be supported in an on-premises Exchange UM deployment, you must be running one of the following:</span></span>

  - <span data-ttu-id="33cc3-111">Microsoft Exchange Server 2007 Service Pack 1 (SP1) ou Service Pack mais recente</span><span class="sxs-lookup"><span data-stu-id="33cc3-111">Microsoft Exchange Server 2007 Service Pack 1 (SP1) or latest service pack</span></span>

  - <span data-ttu-id="33cc3-112">Microsoft Exchange Server 2010 ou Service Pack mais recente</span><span class="sxs-lookup"><span data-stu-id="33cc3-112">Microsoft Exchange Server 2010 or latest service pack</span></span>

  - <span data-ttu-id="33cc3-113">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="33cc3-113">Microsoft Exchange Server 2013</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="33cc3-114">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="33cc3-114">In This Section</span></span>

  - [<span data-ttu-id="33cc3-115">Recursos de Unificação de mensagens integrada e Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33cc3-115">Features of integrated Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-features-of-integrated-unified-messaging.md)

  - [<span data-ttu-id="33cc3-116">Componentes e topologias para Unificação de mensagens no local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33cc3-116">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [<span data-ttu-id="33cc3-117">Diretrizes para integrar a Unificação de mensagens local e o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33cc3-117">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

  - [<span data-ttu-id="33cc3-118">Processo de implantação para integração de Unificação de mensagens local e Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33cc3-118">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

