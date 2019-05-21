---
title: Definir um gateway no construtor de topologias no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 'Resumo: saiba como definir um gateway PSTN no construtor de topologias no Skype for Business Server.'
ms.openlocfilehash: 39e2bdf041055e392b88cc25594b45c2529161d3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286166"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="5cd28-103">Definir um gateway no construtor de topologias no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5cd28-103">Define a gateway in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="5cd28-104">**Resumo:** Saiba como definir um gateway PSTN no construtor de topologias no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5cd28-104">**Summary:** Learn how to define a PSTN gateway in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="5cd28-105">Siga estas etapas para usar o construtor de topologias para definir um par com o qual você pode associar um servidor de mediação para fornecer conectividade à rede telefônica pública comutada (PSTN) para usuários habilitados para Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="5cd28-105">Follow these steps to use Topology Builder to define a peer with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="5cd28-106">Um peer para o servidor de mediação pode ser um gateway PSTN, um IP-PBX ou um controlador de borda de sessão (SBC) para um provedor de serviços de telefonia pela Internet (ITSP) ao qual você se conecta Configurando um tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="5cd28-106">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>
  
### <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="5cd28-107">Para definir um ponto para o Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="5cd28-107">To define a peer for the Mediation Server</span></span>

1. <span data-ttu-id="5cd28-108">Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, clique em **Skype for Business Server 2015**e, em seguida, clique em **Skype for Business Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="5cd28-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="5cd28-109">Em Skype for Business Server, o nome do seu site, componentes compartilhados, clique com o botão direito do mouse no nó **gateways PSTN** e clique em **novo gateway PSTN**.</span><span class="sxs-lookup"><span data-stu-id="5cd28-109">Under Skype for Business Server, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
3. <span data-ttu-id="5cd28-110">Em **Definir Novo Gateway IP/PSTN**, digite o nome de domínio totalmente qualificado (FQDN) ou o endereço IP do ponto e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5cd28-110">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5cd28-111">Se você especificar Transport Layer Security (TLS) como o tipo de transporte, você deve especificar o FQDN em vez do endereço IP do par do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="5cd28-111">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
4. <span data-ttu-id="5cd28-112">Defina um modo de ouvinte (IPv4 ou IPv6) ou o endereço IP do seu novo gateway PSTN e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5cd28-112">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>

5. <span data-ttu-id="5cd28-113">Defina um tronco raiz para o gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="5cd28-113">Define a root trunk for the PSTN gateway.</span></span> <span data-ttu-id="5cd28-114">Um tronco é uma conexão lógica entre um servidor de mediação e um gateway identificado exclusivamente pela tupla.</span><span class="sxs-lookup"><span data-stu-id="5cd28-114">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="5cd28-115">{Servidor de mediação do FQDN, porta de escuta do servidor de mediação (TLS ou TCP): IP e FQDN do gateway, porta de escuta do gateway}</span><span class="sxs-lookup"><span data-stu-id="5cd28-115">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
     - <span data-ttu-id="5cd28-116">Ao definir um gateway PSTN no construtor de topologias, você deve definir um tronco raiz para adicionar com êxito o gateway PSTN à sua topologia.</span><span class="sxs-lookup"><span data-stu-id="5cd28-116">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
     - <span data-ttu-id="5cd28-117">A árvore de raiz não pode ser removida até que o gateway PSTN associado seja removido.</span><span class="sxs-lookup"><span data-stu-id="5cd28-117">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
6. <span data-ttu-id="5cd28-118">Em **porta de escuta para gateway IP/PSTN**, digite a porta de escuta que o gateway, PBX ou SBC usará para mensagens SIP do servidor de mediação que serão associadas ao tronco raiz do gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="5cd28-118">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="5cd28-119">(Por padrão, as portas são 5066 para protocolo TCP e 5067 para protocolo TLS em um gateway PSTN, PBX ou SBC.</span><span class="sxs-lookup"><span data-stu-id="5cd28-119">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="5cd28-120">Em um aparelho de ramificação sobreviventes em um site de filial, as portas padrão são 5081 para TCP e 5082 para TLS.)</span><span class="sxs-lookup"><span data-stu-id="5cd28-120">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>
    
7. <span data-ttu-id="5cd28-121">Em **Protocolo de Transporte SIP**, clique no tipo de transporte que o ponto usa e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5cd28-121">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5cd28-122">Por motivos de segurança, recomendamos enfaticamente que você implante um par para o servidor de mediação que possa usar TLS.</span><span class="sxs-lookup"><span data-stu-id="5cd28-122">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
8. <span data-ttu-id="5cd28-123">Em **servidor de mediação associado**, selecione o pool do servidor de mediação para associar ao tronco raiz desse gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="5cd28-123">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>
    
9. <span data-ttu-id="5cd28-124">Em **porta do servidor de mediação associada**, digite a porta de escuta que o servidor de mediação usará para mensagens SIP do gateway.</span><span class="sxs-lookup"><span data-stu-id="5cd28-124">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5cd28-125">Com o suporte a vários troncos no Skype for Business Server, você pode definir várias portas de sinalização SIP no servidor de mediação para comunicação com vários gateways PSTN.</span><span class="sxs-lookup"><span data-stu-id="5cd28-125">With multiple trunk support in Skype for Business Server, you can define multiple SIP signaling ports on the Mediation Server for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="5cd28-126">Ao definir um tronco, a **porta do servidor de mediação associada** deve estar dentro do intervalo das portas de escuta do respectivo protocolo permitido pelo servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="5cd28-126">When defining a trunk, the **Associated Mediation Server port** must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="5cd28-127">Esse intervalo de porta é definido no Skype for Business Server e em pools de mediação.</span><span class="sxs-lookup"><span data-stu-id="5cd28-127">This port range is defined under Skype for Business Server and Mediation Pools.</span></span> <span data-ttu-id="5cd28-128">Clique com o botão direito do mouse no pool de servidores de mediação de interesse e selecione **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="5cd28-128">Right-click the Mediation Server pool of interest, and select **Edit Properties**.</span></span> <span data-ttu-id="5cd28-129">Specify the port range in the **Listening ports** field.</span><span class="sxs-lookup"><span data-stu-id="5cd28-129">Specify the port range in the **Listening ports** field.</span></span>
  
10. <span data-ttu-id="5cd28-130">Verifique se o ponto definido está funcionando e usando o FQDN ou o endereço IP que você especificou.</span><span class="sxs-lookup"><span data-stu-id="5cd28-130">Be sure that the peer you defined is running and using the FQDN or IP address that you specified.</span></span> <span data-ttu-id="5cd28-131">Depois, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="5cd28-131">Then click **Finish**.</span></span>
    
11. <span data-ttu-id="5cd28-132">Clique com o botão direito no nó **Skype for Business Server** e, em seguida, clique em **Publicar Topologia**.</span><span class="sxs-lookup"><span data-stu-id="5cd28-132">Right-click the **Skype for Business Server** node, and then click **Publish Topology**.</span></span>
    

