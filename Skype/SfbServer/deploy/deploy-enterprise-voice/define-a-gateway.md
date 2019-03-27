---
title: Definir um gateway no construtor de topologia no Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 'Resumo: Saiba como definir um gateway PSTN no construtor de topologia no Skype para Business Server.'
ms.openlocfilehash: 036c6805ab2c4821ee1bb0544b75553ab40c7100
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876317"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="b3efd-103">Definir um gateway no construtor de topologia no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="b3efd-103">Define a gateway in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="b3efd-104">**Resumo:** Saiba como definir um gateway PSTN no construtor de topologia no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="b3efd-104">**Summary:** Learn how to define a PSTN gateway in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="b3efd-105">Siga estas etapas para usar o construtor de topologias para definir um ponto com os quais você pode associar um servidor de mediação para fornecer conectividade com a rede telefônica pública comutada (PSTN) para usuários habilitados para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="b3efd-105">Follow these steps to use Topology Builder to define a peer with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="b3efd-106">Um par ao servidor de mediação pode ser um gateway PSTN, um IP-PBX ou um controlador de borda de sessão (SBC) para um Internet telefonia serviço provedor (ITSP) ao qual você se conecta Configurando um tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="b3efd-106">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>
  
### <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="b3efd-107">Para definir um ponto para o Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="b3efd-107">To define a peer for the Mediation Server</span></span>

1. <span data-ttu-id="b3efd-108">Inicie o construtor de topologia: Clique em **Iniciar**, clique em **Todos os programas**, clique em **Skype para Business Server 2015**e clique **Skype para Business Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="b3efd-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="b3efd-109">Em Skype para Business Server, o nome do seu site, componentes compartilhados, clique com botão direito no nó **Gateways PSTN** e clique em **Novo Gateway PSTN**.</span><span class="sxs-lookup"><span data-stu-id="b3efd-109">Under Skype for Business Server, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
3. <span data-ttu-id="b3efd-110">Em **Definir Novo Gateway IP/PSTN**, digite o nome de domínio totalmente qualificado (FQDN) ou o endereço IP do ponto e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b3efd-110">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b3efd-111">Se você especificar a segurança de camada de transporte (TLS) como o tipo de transporte, você deve especificar o FQDN ao invés do endereço IP do ponto do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="b3efd-111">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
4. <span data-ttu-id="b3efd-112">Defina um modo de ouvinte (IPv4 ou IPv6) ou o endereço IP do seu novo gateway PSTN e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b3efd-112">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>

5. <span data-ttu-id="b3efd-113">Defina um tronco raiz para o gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="b3efd-113">Define a root trunk for the PSTN gateway.</span></span> <span data-ttu-id="b3efd-114">Um tronco é uma conexão lógica entre um servidor de mediação e um gateway exclusivamente identificado pela tupla.</span><span class="sxs-lookup"><span data-stu-id="b3efd-114">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="b3efd-115">{FQDN do servidor de mediação, porta de escuta do servidor de mediação (TLS ou TCP): gateway IP e FQDN, porta de escuta do gateway}</span><span class="sxs-lookup"><span data-stu-id="b3efd-115">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
     - <span data-ttu-id="b3efd-116">Ao definir um gateway PSTN no construtor de topologia, você deve definir um tronco raiz para adicionar com sucesso o gateway PSTN à sua topologia.</span><span class="sxs-lookup"><span data-stu-id="b3efd-116">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
     - <span data-ttu-id="b3efd-117">A árvore de raiz não pode ser removida até que o gateway PSTN associado seja removido.</span><span class="sxs-lookup"><span data-stu-id="b3efd-117">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
6. <span data-ttu-id="b3efd-118">Em **Porta de escuta do Gateway IP/PSTN**, digite a porta de escuta do gateway, PBX ou SBC usarão para mensagens SIP do servidor de mediação que será associado ao tronco raiz do gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="b3efd-118">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="b3efd-119">(Por padrão, as portas são 5066 para protocolo TCP e 5067 para protocolo TLS em um gateway PSTN, PBX ou SBC.</span><span class="sxs-lookup"><span data-stu-id="b3efd-119">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="b3efd-120">Em um aparelho de filial persistente em um site de filial, as portas padrão são 5081 para TCP e 5082 para TLS.)</span><span class="sxs-lookup"><span data-stu-id="b3efd-120">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>
    
7. <span data-ttu-id="b3efd-121">Em **Protocolo de Transporte SIP**, clique no tipo de transporte que o ponto usa e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3efd-121">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b3efd-122">Por motivos de segurança, é altamente recomendável que você implante um par ao servidor de mediação que possa utilizar TLS.</span><span class="sxs-lookup"><span data-stu-id="b3efd-122">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
8. <span data-ttu-id="b3efd-123">Em **Servidor de mediação associado**, selecione o pool de servidor de mediação para associar o tronco raiz deste Gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="b3efd-123">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>
    
9. <span data-ttu-id="b3efd-124">Em **porta do servidor de mediação associado**, digite a porta de escuta do servidor de mediação usará para mensagens SIP do gateway.</span><span class="sxs-lookup"><span data-stu-id="b3efd-124">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b3efd-125">Com suporte a troncos múltiplos no Skype para Business Server, você pode definir várias portas no servidor de mediação para comunicação com vários gateways PSTN de sinalização do SIP.</span><span class="sxs-lookup"><span data-stu-id="b3efd-125">With multiple trunk support in Skype for Business Server, you can define multiple SIP signaling ports on the Mediation Server for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="b3efd-126">Ao definir um tronco, a **porta do servidor de mediação associado** deve estar dentro do intervalo das portas de escuta para o protocolo respectivo permitidos pelo servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="b3efd-126">When defining a trunk, the **Associated Mediation Server port** must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="b3efd-127">Esse intervalo de portas é definido em Skype para Business Server e os Pools de mediação.</span><span class="sxs-lookup"><span data-stu-id="b3efd-127">This port range is defined under Skype for Business Server and Mediation Pools.</span></span> <span data-ttu-id="b3efd-128">O pool do servidor de mediação de interesse do mouse em e selecione **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="b3efd-128">Right-click the Mediation Server pool of interest, and select **Edit Properties**.</span></span> <span data-ttu-id="b3efd-129">Specify the port range in the **Listening ports** field.</span><span class="sxs-lookup"><span data-stu-id="b3efd-129">Specify the port range in the **Listening ports** field.</span></span>
  
10. <span data-ttu-id="b3efd-130">Verifique se o ponto definido está funcionando e usando o FQDN ou o endereço IP que você especificou.</span><span class="sxs-lookup"><span data-stu-id="b3efd-130">Be sure that the peer you defined is running and using the FQDN or IP address that you specified.</span></span> <span data-ttu-id="b3efd-131">Depois, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="b3efd-131">Then click **Finish**.</span></span>
    
11. <span data-ttu-id="b3efd-132">Clique com o botão direito no nó **Skype for Business Server** e, em seguida, clique em **Publicar Topologia**.</span><span class="sxs-lookup"><span data-stu-id="b3efd-132">Right-click the **Skype for Business Server** node, and then click **Publish Topology**.</span></span>
    

