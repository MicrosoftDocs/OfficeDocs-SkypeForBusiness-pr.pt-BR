---
title: 'Lync Server 2013: Configurando a Unificação de Mensagens no Microsoft Exchange Server para funcionar com o Lync Server'
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
ms.openlocfilehash: 5e2bc41d4fa0411c4184c0edda35d6d0cd98df9a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734471"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-unified-messaging-on-microsoft-exchange-server-to-work-with-lync-server-2013"></a><span data-ttu-id="12e74-102">Configurando a Unificação de Mensagens no Microsoft Exchange Server para funcionar com o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12e74-102">Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12e74-103">_**Tópico da última modificação:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="12e74-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="12e74-104">Se você quiser usar a UM (Unificação de mensagens) do Exchange para fornecer atendimento de chamada, Outlook Voice Access ou serviços de atendedor automático para usuários de Enterprise Voice, leia <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">planejando a integração de Unificação de mensagens do Exchange no Lync Server 2013</A> na documentação de planejamento e siga as instruções desta seção.</span><span class="sxs-lookup"><span data-stu-id="12e74-104">If you want to use Exchange Unified Messaging (UM) to provide call answering, Outlook Voice Access, or auto-attendant services for Enterprise Voice users, read <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Planning for Exchange Unified Messaging integration in Lync Server 2013</A> in the Planning documentation, and then follow the instructions in this section.</span></span>



</div>

<span data-ttu-id="12e74-105">Para configurar a UM (Exchange Unified Messaging) para funcionar com o Enterprise Voice, você precisará executar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="12e74-105">To configure Exchange Unified Messaging (UM) to work with Enterprise Voice, you’ll need to perform the following tasks:</span></span>

  - <span data-ttu-id="12e74-106">Configurar certificados no servidor que executa os serviços da Unificação de mensagens (UM) do Exchange</span><span class="sxs-lookup"><span data-stu-id="12e74-106">Configure certificates on the server running Exchange Unified Messaging (UM) services</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="12e74-107">Adicione todos os servidores de caixa de correio e acesso de cliente a todos os planos de discagem URI de UM SIP.</span><span class="sxs-lookup"><span data-stu-id="12e74-107">Add all Client Access and Mailbox servers to all UM SIP URI dial plans.</span></span> <span data-ttu-id="12e74-108">Caso contrário, o roteamento de chamadas de saída não funcionará como esperado.</span><span class="sxs-lookup"><span data-stu-id="12e74-108">If not, outbound call routing won’t work as expected.</span></span>

    
    </div>

  - <span data-ttu-id="12e74-109">Crie um ou mais planos de discagem de URI SIP do UM, juntamente com os números de telefone de acesso do Assinante, conforme necessário e, em seguida, crie os planos de discagem do Lync Server correspondentes.</span><span class="sxs-lookup"><span data-stu-id="12e74-109">Create one or more UM SIP URI dial plans, along with the subscriber access phone numbers, as needed, and then create corresponding Lync Server dial plans.</span></span>

  - <span data-ttu-id="12e74-110">Use o script **ExchUCUtil. ps1** para:</span><span class="sxs-lookup"><span data-stu-id="12e74-110">Use the **exchucutil.ps1** script to:</span></span>
    
      - <span data-ttu-id="12e74-111">Crie gateways IP de UM.</span><span class="sxs-lookup"><span data-stu-id="12e74-111">Create UM IP gateways.</span></span>
    
      - <span data-ttu-id="12e74-112">Criar grupos de números coletivos da UM.</span><span class="sxs-lookup"><span data-stu-id="12e74-112">Create UM hunt groups.</span></span>
    
      - <span data-ttu-id="12e74-113">Conceder ao Lync Server 2013 permissão para ler objetos dos serviços de domínio do Active Directory da UM.</span><span class="sxs-lookup"><span data-stu-id="12e74-113">Grant Lync Server 2013 permission to read UM Active Directory Domain Services objects.</span></span>

  - <span data-ttu-id="12e74-114">Criar um objeto de atendedor automático da UM.</span><span class="sxs-lookup"><span data-stu-id="12e74-114">Create a UM auto-attendant object.</span></span>

  - <span data-ttu-id="12e74-115">Crie um objeto de acesso do Assinante.</span><span class="sxs-lookup"><span data-stu-id="12e74-115">Create a subscriber access object.</span></span>

  - <span data-ttu-id="12e74-116">Crie um URI SIP para cada usuário e associando os usuários a um plano de discagem URI do UM SIP.</span><span class="sxs-lookup"><span data-stu-id="12e74-116">Create a SIP URI for each user and associating users with a UM SIP URI dial plan.</span></span>

<div>

## <a name="requirements-and-recommendations"></a><span data-ttu-id="12e74-117">Requisitos e recomendações</span><span class="sxs-lookup"><span data-stu-id="12e74-117">Requirements and Recommendations</span></span>

<span data-ttu-id="12e74-118">Antes de começar, a documentação desta seção pressupõe que você implantou as seguintes funções do Exchange 2013: acesso de cliente e caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="12e74-118">Before you begin, the documentation in this section assumes that you have deployed the following Exchange 2013 roles: Client Access and Mailbox.</span></span> <span data-ttu-id="12e74-119">No Microsoft Exchange Server 2013, o Exchange UM é executado como um serviço nesses servidores.</span><span class="sxs-lookup"><span data-stu-id="12e74-119">In Microsoft Exchange Server 2013, Exchange UM runs as a service on these servers.</span></span>

<span data-ttu-id="12e74-120">Para obter detalhes sobre a implantação do Exchange 2013, consulte a biblioteca do Exchange 2013 TechNet em[http://go.microsoft.com/fwlink/p/?LinkId=266637](http://go.microsoft.com/fwlink/p/?linkid=266637)</span><span class="sxs-lookup"><span data-stu-id="12e74-120">For details about deploying Exchange 2013, see the Exchange 2013 TechNet Library at [http://go.microsoft.com/fwlink/p/?LinkId=266637](http://go.microsoft.com/fwlink/p/?linkid=266637)</span></span>

<span data-ttu-id="12e74-121">Observe também o seguinte:</span><span class="sxs-lookup"><span data-stu-id="12e74-121">Also note the following:</span></span>

  - <span data-ttu-id="12e74-122">Se o Exchange UM estiver instalado em várias florestas, as etapas de integração do Exchange Server deverão ser realizadas para cada floresta do UM.</span><span class="sxs-lookup"><span data-stu-id="12e74-122">If Exchange UM is installed in multiple forests, the Exchange Server integration steps must be performed for each UM forest.</span></span> <span data-ttu-id="12e74-123">Além disso, cada floresta do UM deve ser configurada para confiar na floresta na qual o Lync Server 2013 é implantado, e a floresta em que o Lync Server 2013 é implantado deve ser configurada para confiar em cada floresta do UM.</span><span class="sxs-lookup"><span data-stu-id="12e74-123">In addition, each UM forest must be configured to trust the forest in which Lync Server 2013 is deployed, and the forest in which Lync Server 2013 is deployed must be configured to trust each UM forest.</span></span>

  - <span data-ttu-id="12e74-124">As etapas de integração são executadas nas funções do Exchange Server em que os serviços de mensagens unificadas estão em execução e no servidor que executa o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12e74-124">Integration steps are performed on both the Exchange Server roles where Unified Messaging services are running, and on the server running Lync Server 2013.</span></span> <span data-ttu-id="12e74-125">Você deve executar as etapas de integração de Unificação de mensagens do Exchange Server antes de executar as etapas de integração do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12e74-125">You should perform the Exchange Server Unified Messaging integration steps before you perform the Lync Server 2013 integration steps.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="12e74-126">Para ver quais etapas de integração são executadas em quais servidores e com quais funções de administrador, consulte <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">processo de implantação para integrar a Unificação de mensagens locais e Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="12e74-126">To see which integration steps are performed on which servers and by which administrator roles, see <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</A>.</span></span>

    
    </div>

<span data-ttu-id="12e74-127">As seguintes ferramentas devem estar disponíveis em cada servidor que executa o Exchange UM:</span><span class="sxs-lookup"><span data-stu-id="12e74-127">The following tools must be available on each server running Exchange UM:</span></span>

  - <span data-ttu-id="12e74-128">Shell de gerenciamento do Exchange</span><span class="sxs-lookup"><span data-stu-id="12e74-128">Exchange Management Shell</span></span>

  - <span data-ttu-id="12e74-129">O script **ExchUCUtil. ps1**, que executa as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="12e74-129">The script **exchucutil.ps1**, which performs the following tasks:</span></span>
    
      - <span data-ttu-id="12e74-130">Cria um gateway IP de UM para cada Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12e74-130">Creates a UM IP gateway for each Lync Server 2013.</span></span>
    
      - <span data-ttu-id="12e74-131">Cria um grupo coletivo para cada gateway.</span><span class="sxs-lookup"><span data-stu-id="12e74-131">Creates a hunt group for each gateway.</span></span> <span data-ttu-id="12e74-132">O identificador piloto de cada número coletivo especifica o plano de discagem do URI SIP usado pelo pool de front-ends ou do servidor Standard Edition associado ao gateway.</span><span class="sxs-lookup"><span data-stu-id="12e74-132">The pilot identifier of each hunt group specifies the UM SIP URI dial plan used by the Front End pool or Standard Edition server that is associated with the gateway.</span></span>
    
      - <span data-ttu-id="12e74-133">Concede permissão do Lync Server 2013 para ler objetos do Exchange UM nos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="12e74-133">Grants Lync Server 2013 permission to read Exchange UM objects in Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="12e74-134">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="12e74-134">In This Section</span></span>

  - [<span data-ttu-id="12e74-135">Configurar certificados no servidor que executa o Microsoft Exchange Server Unified Messaging</span><span class="sxs-lookup"><span data-stu-id="12e74-135">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</span></span>](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [<span data-ttu-id="12e74-136">Configurar a Unificação de mensagens no Microsoft Exchange para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12e74-136">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</span></span>](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

