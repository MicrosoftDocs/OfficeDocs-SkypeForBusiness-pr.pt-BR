---
title: 'Lync Server 2013: Configurando a Unificação de mensagens no Microsoft Exchange Server para funcionar com o Lync Server'
description: 'Lync Server 2013: Configurando a Unificação de mensagens no Microsoft Exchange Server para funcionar com o Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013
ms:assetid: 058da9c4-23af-4ddb-9f63-70133a8aafc6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398106(v=OCS.15)
ms:contentKeyID: 48183289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53c303f0ae659536aafcbdfcd829ed236e35a0ba
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548237"
---
# <a name="configuring-unified-messaging-on-microsoft-exchange-server-to-work-with-lync-server-2013"></a><span data-ttu-id="9df3e-103">Configurando a Unificação de mensagens no Microsoft Exchange Server para funcionar com o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9df3e-103">Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9df3e-104">_**Última modificação do tópico:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="9df3e-104">_**Topic Last Modified:** 2012-10-11_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9df3e-105">Se você quiser usar a Unificação de mensagens (UM) do Exchange para fornecer atendimento de chamadas, Outlook Voice Access ou serviços de atendedor automático para usuários do Enterprise Voice, leia <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">planejamento para a integração de Unificação de mensagens do Exchange no Lync Server 2013</A> na documentação de planejamento e siga as instruções desta seção.</span><span class="sxs-lookup"><span data-stu-id="9df3e-105">If you want to use Exchange Unified Messaging (UM) to provide call answering, Outlook Voice Access, or auto-attendant services for Enterprise Voice users, read <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Planning for Exchange Unified Messaging integration in Lync Server 2013</A> in the Planning documentation, and then follow the instructions in this section.</span></span>



</div>

<span data-ttu-id="9df3e-106">Para configurar a Unificação de mensagens (UM) do Exchange para trabalhar com o Enterprise Voice, você precisará executar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="9df3e-106">To configure Exchange Unified Messaging (UM) to work with Enterprise Voice, you’ll need to perform the following tasks:</span></span>

  - <span data-ttu-id="9df3e-107">Configurar certificados no servidor que executa os serviços de Unificação de mensagens (UM) do Exchange</span><span class="sxs-lookup"><span data-stu-id="9df3e-107">Configure certificates on the server running Exchange Unified Messaging (UM) services</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9df3e-108">Adicione todos os servidores de acesso para cliente e caixa de correio a todos os planos de discagem URI SIP.</span><span class="sxs-lookup"><span data-stu-id="9df3e-108">Add all Client Access and Mailbox servers to all UM SIP URI dial plans.</span></span> <span data-ttu-id="9df3e-109">Caso contrário, o roteamento de chamadas de saída não funcionará conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="9df3e-109">If not, outbound call routing won’t work as expected.</span></span>

    
    </div>

  - <span data-ttu-id="9df3e-110">Crie um ou mais planos de discagem de URI SIP de UM, junto com os números de telefone de acesso do Assinante, conforme necessário, e crie planos de discagem do Lync Server correspondentes.</span><span class="sxs-lookup"><span data-stu-id="9df3e-110">Create one or more UM SIP URI dial plans, along with the subscriber access phone numbers, as needed, and then create corresponding Lync Server dial plans.</span></span>

  - <span data-ttu-id="9df3e-111">Use o **exchucutil.ps1** script para:</span><span class="sxs-lookup"><span data-stu-id="9df3e-111">Use the **exchucutil.ps1** script to:</span></span>
    
      - <span data-ttu-id="9df3e-112">Criar gateways IP da UM.</span><span class="sxs-lookup"><span data-stu-id="9df3e-112">Create UM IP gateways.</span></span>
    
      - <span data-ttu-id="9df3e-113">Criar grupos de busca da UM.</span><span class="sxs-lookup"><span data-stu-id="9df3e-113">Create UM hunt groups.</span></span>
    
      - <span data-ttu-id="9df3e-114">Conceder ao Lync Server 2013 permissão para ler objetos dos serviços de domínio de UM Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9df3e-114">Grant Lync Server 2013 permission to read UM Active Directory Domain Services objects.</span></span>

  - <span data-ttu-id="9df3e-115">Criar um objeto de atendedor automático da UM.</span><span class="sxs-lookup"><span data-stu-id="9df3e-115">Create a UM auto-attendant object.</span></span>

  - <span data-ttu-id="9df3e-116">Criar um objeto de acesso ao Assinante.</span><span class="sxs-lookup"><span data-stu-id="9df3e-116">Create a subscriber access object.</span></span>

  - <span data-ttu-id="9df3e-117">Criar um URI SIP para cada usuário e associar usuários a um plano de discagem URI SIP de UM.</span><span class="sxs-lookup"><span data-stu-id="9df3e-117">Create a SIP URI for each user and associating users with a UM SIP URI dial plan.</span></span>

<div>

## <a name="requirements-and-recommendations"></a><span data-ttu-id="9df3e-118">Requisitos e recomendações</span><span class="sxs-lookup"><span data-stu-id="9df3e-118">Requirements and Recommendations</span></span>

<span data-ttu-id="9df3e-119">Antes de começar, a documentação desta seção pressupõe que você implantou as seguintes funções do Exchange 2013: acesso para cliente e caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="9df3e-119">Before you begin, the documentation in this section assumes that you have deployed the following Exchange 2013 roles: Client Access and Mailbox.</span></span> <span data-ttu-id="9df3e-120">No Microsoft Exchange Server 2013, o UM do Exchange é executado como um serviço nesses servidores.</span><span class="sxs-lookup"><span data-stu-id="9df3e-120">In Microsoft Exchange Server 2013, Exchange UM runs as a service on these servers.</span></span>

<span data-ttu-id="9df3e-121">Para obter detalhes sobre a implantação do Exchange 2013, consulte a biblioteca do Exchange 2013 TechNet em [https://go.microsoft.com/fwlink/p/?LinkId=266637](https://go.microsoft.com/fwlink/p/?linkid=266637)</span><span class="sxs-lookup"><span data-stu-id="9df3e-121">For details about deploying Exchange 2013, see the Exchange 2013 TechNet Library at [https://go.microsoft.com/fwlink/p/?LinkId=266637](https://go.microsoft.com/fwlink/p/?linkid=266637)</span></span>

<span data-ttu-id="9df3e-122">Também observe o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9df3e-122">Also note the following:</span></span>

  - <span data-ttu-id="9df3e-123">Se o UM do Exchange estiver instalado em várias florestas, as etapas de integração do Exchange Server deverão ser realizadas para cada floresta da UM.</span><span class="sxs-lookup"><span data-stu-id="9df3e-123">If Exchange UM is installed in multiple forests, the Exchange Server integration steps must be performed for each UM forest.</span></span> <span data-ttu-id="9df3e-124">Além disso, cada floresta de UM deve ser configurada para confiar na floresta em que o Lync Server 2013 está implantado e a floresta na qual o Lync Server 2013 está implantado deve ser configurada para confiar em cada floresta da UM.</span><span class="sxs-lookup"><span data-stu-id="9df3e-124">In addition, each UM forest must be configured to trust the forest in which Lync Server 2013 is deployed, and the forest in which Lync Server 2013 is deployed must be configured to trust each UM forest.</span></span>

  - <span data-ttu-id="9df3e-125">As etapas de integração são realizadas nas funções de servidor do Exchange em que os serviços de Unificação de mensagens estão sendo executados e no servidor que executa o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9df3e-125">Integration steps are performed on both the Exchange Server roles where Unified Messaging services are running, and on the server running Lync Server 2013.</span></span> <span data-ttu-id="9df3e-126">Você deve executar as etapas de integração de Unificação de mensagens do Exchange Server antes de realizar as etapas de integração do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9df3e-126">You should perform the Exchange Server Unified Messaging integration steps before you perform the Lync Server 2013 integration steps.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9df3e-127">Para ver quais etapas de integração são executadas em quais servidores e por quais funções de administrador, consulte <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">processo de implantação para integração de Unificação de mensagens local e Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9df3e-127">To see which integration steps are performed on which servers and by which administrator roles, see <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</A>.</span></span>

    
    </div>

<span data-ttu-id="9df3e-128">As seguintes ferramentas devem estar disponíveis em cada servidor que executa o UM do Exchange:</span><span class="sxs-lookup"><span data-stu-id="9df3e-128">The following tools must be available on each server running Exchange UM:</span></span>

  - <span data-ttu-id="9df3e-129">Shell de Gerenciamento do Exchange</span><span class="sxs-lookup"><span data-stu-id="9df3e-129">Exchange Management Shell</span></span>

  - <span data-ttu-id="9df3e-130">O script **exchucutil.ps1**, o qual realiza as tarefas a seguir:</span><span class="sxs-lookup"><span data-stu-id="9df3e-130">The script **exchucutil.ps1**, which performs the following tasks:</span></span>
    
      - <span data-ttu-id="9df3e-131">Cria um gateway IP da UM para cada Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9df3e-131">Creates a UM IP gateway for each Lync Server 2013.</span></span>
    
      - <span data-ttu-id="9df3e-132">Cria um grupo de busca para cada gateway.</span><span class="sxs-lookup"><span data-stu-id="9df3e-132">Creates a hunt group for each gateway.</span></span> <span data-ttu-id="9df3e-133">O identificador piloto de cada grupo de busca especifica o plano de discagem de URI SIP de UM usado pelo pool de front-ends ou servidor Standard Edition associado ao gateway.</span><span class="sxs-lookup"><span data-stu-id="9df3e-133">The pilot identifier of each hunt group specifies the UM SIP URI dial plan used by the Front End pool or Standard Edition server that is associated with the gateway.</span></span>
    
      - <span data-ttu-id="9df3e-134">Concede permissão do Lync Server 2013 para ler objetos da UM do Exchange nos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9df3e-134">Grants Lync Server 2013 permission to read Exchange UM objects in Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9df3e-135">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="9df3e-135">In This Section</span></span>

  - [<span data-ttu-id="9df3e-136">Configurar certificados no servidor que executa a Unificação de mensagens do Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="9df3e-136">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</span></span>](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [<span data-ttu-id="9df3e-137">Configurar a Unificação de mensagens no Microsoft Exchange para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9df3e-137">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</span></span>](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

