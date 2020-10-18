---
title: 'Lync Server 2013: Diretrizes para integração da Unificação de mensagens local'
description: 'Lync Server 2013: Diretrizes para integração da Unificação de mensagens local.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Guidelines for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 829ac017-6907-40f9-be22-787a28eae0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398656(v=OCS.15)
ms:contentKeyID: 48184681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 814c927aa36199737712328d3b92c64a8e967a55
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576637"
---
# <a name="guidelines-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="02bd5-103">Diretrizes para integrar a Unificação de mensagens local e o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02bd5-103">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02bd5-104">_**Última modificação do tópico:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="02bd5-104">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="02bd5-105">Veja a seguir as diretrizes e práticas recomendadas a serem consideradas ao implantar o Enterprise Voice:</span><span class="sxs-lookup"><span data-stu-id="02bd5-105">The following are guidelines and best practices to consider when you deploy Enterprise Voice:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="02bd5-106">A Unificação de mensagens (UM) do Exchange oferece suporte a IPv6 somente se você também estiver usando o UCMA 4.</span><span class="sxs-lookup"><span data-stu-id="02bd5-106">Exchange Unified Messaging (UM) supports IPv6 only if you are also using UCMA 4.</span></span>



</div>

  - <span data-ttu-id="02bd5-107">Implantar um servidor do Lync Server 2013 Standard Edition ou um pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="02bd5-107">Deploy a Lync Server 2013 Standard Edition server or a Front End pool.</span></span> <span data-ttu-id="02bd5-108">Para obter detalhes sobre a instalação, consulte [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="02bd5-108">For details about installation, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="02bd5-109">Trabalhar com os administradores do Exchange para confirmar que tarefas cada um executará para garantir uma integração tranqüila e bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="02bd5-109">Work with Exchange administrators to confirm which tasks each of you will perform to assure a smooth and successful integration.</span></span>

  - <span data-ttu-id="02bd5-110">Implante as funções de servidor de caixa de correio do Exchange em cada floresta de UM (Unificação de mensagens) do Exchange onde você deseja habilitar usuários para UM do Exchange.</span><span class="sxs-lookup"><span data-stu-id="02bd5-110">Deploy the Exchange Mailbox server roles in each Exchange Unified Messaging (UM) forest where you want to enable users for Exchange UM.</span></span> <span data-ttu-id="02bd5-111">Para obter detalhes sobre como instalar as funções do Exchange Server, consulte a documentação do Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="02bd5-111">For details about installing Exchange server roles, see the Microsoft Exchange Server 2013 documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="02bd5-112">Quando a Unificação de mensagens (UM) do Exchange está instalada, ela é configurada para usar um certificado autoassinado.</span><span class="sxs-lookup"><span data-stu-id="02bd5-112">When Exchange Unified Messaging (UM) is installed, it is configured to use a self-signed certificate.</span></span><BR><span data-ttu-id="02bd5-113">No entanto, o certificado autoassinado não permite que o Lync Server 2013 e o Exchange UM confiem uns com os outros, o que é necessário para solicitar um certificado separado de uma autoridade de certificação em que ambos os servidores confiem.</span><span class="sxs-lookup"><span data-stu-id="02bd5-113">The self-signed certificate, however, does not enable Lync Server 2013 and Exchange UM to trust each other, which is why it is necessary to request a separate certificate from a certification authority that both servers trust.</span></span>

    
    </div>

  - <span data-ttu-id="02bd5-114">Se o Lync Server 2013 e o Exchange UM estiverem instalados em florestas diferentes, configure cada floresta do Exchange para confiar na floresta do Lync Server 2013 e na floresta do Lync Server 2013 para confiar em cada floresta do Exchange.</span><span class="sxs-lookup"><span data-stu-id="02bd5-114">If Lync Server 2013 and Exchange UM are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest and the Lync Server 2013 forest to trust each Exchange forest.</span></span> <span data-ttu-id="02bd5-115">Além disso, defina as configurações de UM do Exchange do usuário nos objetos de usuário na floresta do Lync Server 2013, normalmente usando um script ou uma ferramenta entre florestas, como o Identity Lifecycle Manager (ILM).</span><span class="sxs-lookup"><span data-stu-id="02bd5-115">Also, set the users’ Exchange UM settings on the user objects in the Lync Server 2013 forest, typically by using a script or a cross-forest tool, such as Identity Lifecycle Manager (ILM).</span></span>

  - <span data-ttu-id="02bd5-116">Se necessário, instale o Console de Gerenciamento do Exchange para gerenciar os servidores de Unificação de mensagens.</span><span class="sxs-lookup"><span data-stu-id="02bd5-116">If necessary, install the Exchange Management Console to manage your Unified Messaging servers.</span></span>

  - <span data-ttu-id="02bd5-117">Obtenha números de telefone válidos para o Outlook Voice Access e o atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="02bd5-117">Obtain valid phone numbers for Outlook Voice Access and auto attendant.</span></span>

  - <span data-ttu-id="02bd5-118">Se você estiver usando uma versão do UM do Exchange anterior ao Microsoft Exchange Server 2010 Service Pack 1 (SP1), coordene nomes para planos de discagem URI SIP de UM do Exchange e planos de discagem do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="02bd5-118">If you are using a version of Exchange UM earlier than Microsoft Exchange Server 2010 Service Pack 1 (SP1), coordinate names for Exchange UM SIP URI dial plans and Enterprise Voice dial plans.</span></span>

<div>

## <a name="deploying-redundant-exchange-um-servers"></a><span data-ttu-id="02bd5-119">Implantando Servidores Redundantes UM do Exchange</span><span class="sxs-lookup"><span data-stu-id="02bd5-119">Deploying Redundant Exchange UM Servers</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="02bd5-120">Recomendamos que você implante um mínimo de dois servidores nos quais os serviços de UM do Exchange estão sendo executados para cada plano de discagem de URI SIP da UM do Exchange que você configura para sua organização.</span><span class="sxs-lookup"><span data-stu-id="02bd5-120">We recommend that you deploy a minimum of two servers on which Exchange UM services is running for each Exchange UM SIP URI dial plan that you configure for your organization.</span></span> <span data-ttu-id="02bd5-121">Além de fornecer capacidade expandida, a implantação de servidores redundantes oferece alta disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="02bd5-121">In addition to providing expanded capacity, deploying redundant servers provides high availability.</span></span> <span data-ttu-id="02bd5-122">No caso de uma falha de servidor, o Lync Server 2013 pode ser configurado para fazer failover para outro servidor.</span><span class="sxs-lookup"><span data-stu-id="02bd5-122">In the event of an server failure, Lync Server 2013 can be configured to fail over to another server.</span></span>



</div>

<span data-ttu-id="02bd5-123">As seguintes configurações de exemplo fornecem resiliência de UM do Exchange.</span><span class="sxs-lookup"><span data-stu-id="02bd5-123">The following example configurations provide Exchange UM resiliency.</span></span>

<span data-ttu-id="02bd5-124">**Exemplo 1: resiliência de UM do Exchange**</span><span class="sxs-lookup"><span data-stu-id="02bd5-124">**Example 1: Exchange UM Resiliency**</span></span>

<span data-ttu-id="02bd5-125">![Exemplo 1 de UM do Exchange](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Exemplo 1 de UM do Exchange")</span><span class="sxs-lookup"><span data-stu-id="02bd5-125">![Exchange UM Example 1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Exchange UM Example 1")</span></span>

<span data-ttu-id="02bd5-126">No exemplo 1, os servidores UM 1 e 2 do Exchange são ativados no data center de Tukwila e os servidores UM 3 e 4 do Exchange são ativados no data center de Dublin.</span><span class="sxs-lookup"><span data-stu-id="02bd5-126">In Example 1, Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center.</span></span> <span data-ttu-id="02bd5-127">No caso de uma paralisação um do Exchange no Tukwila, o sistema de nomes de domínio (DNS) um registro para os servidores 1 e 2 deve ser configurado para apontar para os servidores 3 e 4, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="02bd5-127">In the event of an Exchange UM outage in Tukwila, the Domain Name System (DNS) A records for servers 1 and 2 should be configured to point to servers 3 and 4, respectively.</span></span> <span data-ttu-id="02bd5-128">No caso de uma paralisação um do Exchange em Dublin, os registros DNS A para os servidores 3 e 4 devem ser configurados para apontar para os servidores 1 e 2, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="02bd5-128">In the event of an Exchange UM outage in Dublin, the DNS A records for servers 3 and 4 should be configured to point to servers 1 and 2, respectively.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="02bd5-129">Para o exemplo 1, você deve também atribuir um dos seguintes certificados em cada servidor UM do Exchange:</span><span class="sxs-lookup"><span data-stu-id="02bd5-129">For Example 1, you should also assign one of following certificate on each Exchange UM server:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="02bd5-130">Use um certificado com um caractere curinga no nome de alternativo da entidade (SAN).</span><span class="sxs-lookup"><span data-stu-id="02bd5-130">Use a certificate with a wildcard in the Subject Alternative Name (SAN).</span></span></P>
> <LI>
> <P><span data-ttu-id="02bd5-131">Coloque o FQDN (nome de domínio totalmente qualificado) de cada um dos quatro servidores de UM do Exchange na SAN.</span><span class="sxs-lookup"><span data-stu-id="02bd5-131">Put the fully qualified domain name (FQDN) of each of the four Exchange UM servers in the SAN.</span></span></P></LI></UL>



</div>

<span data-ttu-id="02bd5-132">**Exemplo 2: resiliência de UM do Exchange**</span><span class="sxs-lookup"><span data-stu-id="02bd5-132">**Example 2: Exchange UM Resiliency**</span></span>

<span data-ttu-id="02bd5-133">![Exemplo 2 de UM do Exchange](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Exemplo 2 de UM do Exchange")</span><span class="sxs-lookup"><span data-stu-id="02bd5-133">![Exchange UM Example 2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Exchange UM Example 2")</span></span>

<span data-ttu-id="02bd5-p106">No exemplo 2, sob condições operacionais comuns, os servidores UM 1 e 2 do Exchange são ativados no data center de Tukwila e os servidores UM 3 e 4 do Exchange são ativados no data center de Dublin. Os quatro servidores estão incluídos no plano de discagem de URI do SIP dos usuários de Tukwila; no entanto, os servidores 3 e 4 estão desativados. No caso de uma paralisação UM Exchange em Tukwila, por exemplo, os servidores UM 1 e 2 do Exchange devem ser desativados e os servidores UM 3 e 4 do Exchange devem ser habilitados para que o tráfego UM do Exchange de Tukwila seja roteado para os servidores em Dublin.</span><span class="sxs-lookup"><span data-stu-id="02bd5-p106">In Example 2, under ordinary operating conditions Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center. All four servers are included in the Tukwila users' SIP URI dial plan; however, servers 3 and 4 are disabled. In the event of an Exchange UM outage in Tukwila, for example, Exchange UM servers 1 and 2 should be disabled and Exchange UM servers 3 and 4 should be enabled so the Tukwila Exchange UM traffic will be routed to the servers in Dublin.</span></span>

<span data-ttu-id="02bd5-137">Para obter detalhes sobre como habilitar ou desabilitar a Unificação de mensagens no Exchange 2013, consulte "integrar o Exchange 2013 UM com Lync Server" em [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372) .</span><span class="sxs-lookup"><span data-stu-id="02bd5-137">For details about how to enable or disable Unified Messaging on Exchange 2013, see “Integrate Exchange 2013 UM with Lync Server” at [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372).</span></span>

<span data-ttu-id="02bd5-138">Para obter detalhes sobre como habilitar ou desabilitar a Unificação de mensagens no Microsoft Exchange Server 2010, consulte:</span><span class="sxs-lookup"><span data-stu-id="02bd5-138">For details about how to enable or disable Unified Messaging on Microsoft Exchange Server 2010, see:</span></span>

  - <span data-ttu-id="02bd5-139">"Habilitar a Unificação de mensagens no Exchange 2010" em [https://go.microsoft.com/fwlink/p/?LinkId=204418](https://go.microsoft.com/fwlink/p/?linkid=204418) .</span><span class="sxs-lookup"><span data-stu-id="02bd5-139">"Enable Unified Messaging on Exchange 2010" at [https://go.microsoft.com/fwlink/p/?LinkId=204418](https://go.microsoft.com/fwlink/p/?linkid=204418).</span></span>

  - <span data-ttu-id="02bd5-140">"Desabilitar a Unificação de mensagens no Exchange 2010" em [https://go.microsoft.com/fwlink/p/?LinkId=204416](https://go.microsoft.com/fwlink/p/?linkid=204416) .</span><span class="sxs-lookup"><span data-stu-id="02bd5-140">"Disable Unified Messaging on Exchange 2010" at [https://go.microsoft.com/fwlink/p/?LinkId=204416](https://go.microsoft.com/fwlink/p/?linkid=204416).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="02bd5-141">Confira também</span><span class="sxs-lookup"><span data-stu-id="02bd5-141">See Also</span></span>


[<span data-ttu-id="02bd5-142">Processo de implantação para integração de Unificação de mensagens local e Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02bd5-142">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

