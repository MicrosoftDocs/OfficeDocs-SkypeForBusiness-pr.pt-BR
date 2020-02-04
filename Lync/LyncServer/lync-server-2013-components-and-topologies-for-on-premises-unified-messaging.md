---
title: 'Lync Server 2013: Componentes e topologias para o Sistema de Mensagens Instantâneas local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for on-premises Unified Messaging
ms:assetid: 22fc87cf-a7e5-4c8c-bb9b-101e5380cdcf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425711(v=OCS.15)
ms:contentKeyID: 48183619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1739dbb7d603f112af72c78032c46b94470302bb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-on-premises-unified-messaging-in-lync-server-2013"></a><span data-ttu-id="9e157-102">Componentes e topologias para o Sistema de Mensagens Instantâneas local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e157-102">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e157-103">_**Tópico da última modificação:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="9e157-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="9e157-104">Este tópico descreve os componentes do Microsoft Exchange Server 2013 necessários para fornecer recursos de UM (Unificação de mensagens) do Exchange à implantação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9e157-104">This topic describes the Microsoft Exchange Server 2013 components required to provide Exchange Unified Messaging (UM) features to Lync Server 2013 deployment.</span></span> <span data-ttu-id="9e157-105">Ele também descreve as topologias com suporte para a integração de UM local do Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="9e157-105">It also describes the supported topologies for on-premises Exchange UM integration.</span></span>

<div>

## <a name="exchange-server-components"></a><span data-ttu-id="9e157-106">Componentes de Exchange Server</span><span class="sxs-lookup"><span data-stu-id="9e157-106">Exchange Server Components</span></span>

<span data-ttu-id="9e157-107">Para fornecer os recursos e os serviços do Exchange UM descritos em [recursos de Unificação de mensagens integrada e Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md) para usuários do Enterprise Voice em sua organização, você deve implantar um servidor de caixa de correio do Microsoft Exchange e um servidor de acesso para cliente, que hospeda caixas de correio de usuários e fornece um único local de armazenamento para email e caixa postal.</span><span class="sxs-lookup"><span data-stu-id="9e157-107">To provide the Exchange UM features and services described in [Features of integrated Unified Messaging and Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md) to Enterprise Voice users in your organization, you must deploy an Microsoft Exchange Mailbox server and Client Access server, which hosts user mailboxes and provides a single storage location for email and voice mail.</span></span> <span data-ttu-id="9e157-108">O Exchange UM é executado como um serviço na caixa de correio do Exchange e nos servidores de acesso para cliente.</span><span class="sxs-lookup"><span data-stu-id="9e157-108">Exchange UM runs as a service on Exchange Mailbox and Client Access servers.</span></span>

<span data-ttu-id="9e157-109">Para obter detalhes sobre os componentes de UM do Exchange no Microsoft Exchange Server 2007 e no Microsoft Exchange Server 2010, consulte [implantando o Exchange um local para fornecer o Lync Server 2013 voice mail](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="9e157-109">For details about Exchange UM components in Microsoft Exchange Server 2007 and Microsoft Exchange Server 2010, see [Deploying on-premises Exchange UM to provide Lync Server 2013 voice mail](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="9e157-110">Topologias suportadas</span><span class="sxs-lookup"><span data-stu-id="9e157-110">Supported Topologies</span></span>

<span data-ttu-id="9e157-111">Você pode implantar o Lync Server 2013 e o Exchange Unified Messaging (UM) na mesma floresta ou em várias florestas.</span><span class="sxs-lookup"><span data-stu-id="9e157-111">You can deploy Lync Server 2013 and Exchange Unified Messaging (UM) in the same forest or multiple forests.</span></span> <span data-ttu-id="9e157-112">Se a implantação abranger várias florestas, você deve executar as etapas de integração do Exchange para cada floresta do Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="9e157-112">If the deployment spans multiple forests, you must perform the Exchange integration steps for each Exchange UM forest.</span></span> <span data-ttu-id="9e157-113">Além disso, você deve configurar cada floresta do Microsoft Exchange para confiar na floresta do Lync Server 2013 e na floresta do Lync Server 2013 para confiar em cada floresta do Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="9e157-113">Furthermore, you must configure each Microsoft Exchange forest to trust the Lync Server 2013 forest and the Lync Server 2013 forest to trust each Exchange UM forest.</span></span> <span data-ttu-id="9e157-114">Além dessa relação de confiança de floresta, as configurações de UM do Exchange UM para todos os usuários devem ser definidas nos objetos de usuário da floresta do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9e157-114">In addition to this forest trust, the Exchange UM settings for all users must be set on the user objects in the Lync Server 2013 forest.</span></span>

<span data-ttu-id="9e157-115">O Lync Server 2013 oferece suporte às seguintes topologias para a integração de UM do Exchange UM:</span><span class="sxs-lookup"><span data-stu-id="9e157-115">Lync Server 2013 supports the following topologies for Exchange UM integration:</span></span>

  - <span data-ttu-id="9e157-116">Floresta única</span><span class="sxs-lookup"><span data-stu-id="9e157-116">Single forest</span></span>

  - <span data-ttu-id="9e157-117">Domínio único (ou seja, uma única floresta com um único domínio).</span><span class="sxs-lookup"><span data-stu-id="9e157-117">Single domain (that is, a single forest with a single domain).</span></span> <span data-ttu-id="9e157-118">O Lync Server 2013, o Microsoft Exchange e os usuários residem no mesmo domínio.</span><span class="sxs-lookup"><span data-stu-id="9e157-118">Lync Server 2013, Microsoft Exchange, and users all reside in the same domain.</span></span>

  - <span data-ttu-id="9e157-119">Vários domínios (ou seja, um domínio raiz com um ou mais domínios filhos).</span><span class="sxs-lookup"><span data-stu-id="9e157-119">Multiple domain (that is, a root domain with one or more child domains).</span></span> <span data-ttu-id="9e157-120">O Lync Server 2013 e o Microsoft Exchange Server são implantados em domínios diferentes do domínio em que você cria usuários.</span><span class="sxs-lookup"><span data-stu-id="9e157-120">Lync Server 2013, and Microsoft Exchange servers are deployed in different domains from the domain where you create users.</span></span> <span data-ttu-id="9e157-121">Os servidores Exchange UM podem ser implantados em diferentes domínios do Lync Server 2013 pool suportados.</span><span class="sxs-lookup"><span data-stu-id="9e157-121">Exchange UM servers can be deployed in different domains from the Lync Server 2013 pool they support.</span></span>

  - <span data-ttu-id="9e157-122">Várias floresta (ou seja, floresta de recursos).</span><span class="sxs-lookup"><span data-stu-id="9e157-122">Multiple forest (that is, resource forest).</span></span> <span data-ttu-id="9e157-123">O Lync Server 2013 é implantado em uma única floresta e os usuários são distribuídos em várias florestas.</span><span class="sxs-lookup"><span data-stu-id="9e157-123">Lync Server 2013 is deployed in a single forest, and then users are distributed across multiple forests.</span></span> <span data-ttu-id="9e157-124">Os atributos de UM dos usuários do Exchange devem ser replicados para a floresta do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9e157-124">The users’ Exchange UM attributes must be replicated over to the Lync Server 2013 forest.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9e157-125">O Exchange pode ser implantado em várias florestas.</span><span class="sxs-lookup"><span data-stu-id="9e157-125">Exchange can be deployed in multiple forests.</span></span> <span data-ttu-id="9e157-126">Cada organização do Exchange pode fornecer ao Exchange UM para seus usuários ou o Exchange UM pode ser implantado na mesma floresta do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9e157-126">Each Exchange organization can provide Exchange UM to its users, or Exchange UM can be deployed in the same forest as Lync Server 2013.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

