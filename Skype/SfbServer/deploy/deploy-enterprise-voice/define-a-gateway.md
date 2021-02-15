---
title: Definir um gateway no Construtor de Topologias no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 'Resumo: saiba como definir um gateway PSTN no Construtor de Topologias no Skype for Business Server.'
ms.openlocfilehash: be68c853cdcd530b05ad4b0949f722788e77d0df
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837021"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="ff7c6-103">Definir um gateway no Construtor de Topologias no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ff7c6-103">Define a gateway in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="ff7c6-104">**Resumo:** Saiba como definir um gateway PSTN no Construtor de Topologias no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ff7c6-104">**Summary:** Learn how to define a PSTN gateway in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="ff7c6-105">Siga estas etapas para usar o Construtor de Topologias para definir um ponto ao qual você pode associar um Servidor de Mediação para fornecer conectividade à PSTN (rede telefônica pública comuada) para usuários habilitados para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="ff7c6-105">Follow these steps to use Topology Builder to define a peer with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="ff7c6-106">Um ponto para o Servidor de Mediação pode ser um gateway PSTN, um IP-PBX ou um SBC (Controlador de Borda de Sessão) para um ITSP (Provedor de Serviços de Telefonia da Internet) ao qual você se conecta configurando um tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="ff7c6-106">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>
  
### <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="ff7c6-107">Para definir um par para o Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="ff7c6-107">To define a peer for the Mediation Server</span></span>

1. <span data-ttu-id="ff7c6-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="ff7c6-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="ff7c6-109">No Skype for Business Server, seu nome de site, Componentes Compartilhados, clique com o botão direito do mouse no nó **Gateways PSTN** e clique em **Novo Gateway PSTN.**</span><span class="sxs-lookup"><span data-stu-id="ff7c6-109">Under Skype for Business Server, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
3. <span data-ttu-id="ff7c6-110">Em **Definir Novo Gateway IP/PSTN**, digite o nome de domínio totalmente qualificado (FQDN) ou o endereço IP do ponto e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ff7c6-110">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ff7c6-111">Se você especificar o protocolo TLS como o tipo de transporte, deverá especificar o FQDN em vez do endereço IP do ponto do Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="ff7c6-111">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
4. <span data-ttu-id="ff7c6-112">Defina um modo de ouvinte (IPv4 ou IPv6) ou o endereço IP do seu novo gateway PSTN e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ff7c6-112">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>

5. <span data-ttu-id="ff7c6-113">Defina um tronco raiz par ao gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="ff7c6-113">Define a root trunk for the PSTN gateway.</span></span> <span data-ttu-id="ff7c6-114">Um tronco é uma conexão lógica entre um Servidor de Mediação e um gateway identificado exclusivamente pela tupla.</span><span class="sxs-lookup"><span data-stu-id="ff7c6-114">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="ff7c6-115">{FQDN do Servidor de Mediação, porta de escuta do Servidor de Mediação (TLS ou TCP) : IP do gateway e FQDN, porta de escuta de gateway}</span><span class="sxs-lookup"><span data-stu-id="ff7c6-115">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
     - <span data-ttu-id="ff7c6-116">Ao definir um gateway PSTN no Construtor de Topologias, você deve definir um tronco raiz para adicionar com êxito o gateway PSTN à sua topologia.</span><span class="sxs-lookup"><span data-stu-id="ff7c6-116">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
     - <span data-ttu-id="ff7c6-117">A árvore de raiz não pode ser removida até que o gateway PSTN associado seja removido.</span><span class="sxs-lookup"><span data-stu-id="ff7c6-117">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
6. <span data-ttu-id="ff7c6-118">Em Porta de Escuta para **Gateway IP/PSTN,** digite a porta de escuta que o gateway, PBX ou SBC usará para mensagens SIP do Servidor de Mediação que serão associadas ao tronco raiz do gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="ff7c6-118">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="ff7c6-119">(Por padrão, as portas são 5066 para protocolo TCP e 5067 para protocolo TLS em um gateway PSTN, PBX ou SBC.</span><span class="sxs-lookup"><span data-stu-id="ff7c6-119">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="ff7c6-120">Em um Aparelho de Filial Survivível em um site de filial, as portas padrão são 5081 para TCP e 5082 para TLS.)</span><span class="sxs-lookup"><span data-stu-id="ff7c6-120">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>
    
7. <span data-ttu-id="ff7c6-121">Em **Protocolo de Transporte SIP**, clique no tipo de transporte que o ponto usa e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ff7c6-121">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ff7c6-122">Por motivos de segurança, recomendamos que você implante um par para o Servidor de Mediação que possa usar TLS.</span><span class="sxs-lookup"><span data-stu-id="ff7c6-122">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
8. <span data-ttu-id="ff7c6-123">Em **Servidor de Mediação Associado,** selecione o pool do Servidor de Mediação a ser associado ao tronco raiz deste Gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="ff7c6-123">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>
    
9. <span data-ttu-id="ff7c6-124">Em **Porta do Servidor de Mediação** Associado, digite a porta de escuta que o Servidor de Mediação usará para mensagens SIP do gateway.</span><span class="sxs-lookup"><span data-stu-id="ff7c6-124">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ff7c6-125">Com suporte a vários troncos no Skype for Business Server, você pode definir várias portas de sinalização SIP no Servidor de Mediação para comunicação com vários gateways PSTN.</span><span class="sxs-lookup"><span data-stu-id="ff7c6-125">With multiple trunk support in Skype for Business Server, you can define multiple SIP signaling ports on the Mediation Server for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="ff7c6-126">Ao definir um tronco, a porta do Servidor de Mediação Associado deve estar dentro do intervalo das portas de escuta para o respectivo protocolo permitido pelo Servidor de Mediação. </span><span class="sxs-lookup"><span data-stu-id="ff7c6-126">When defining a trunk, the **Associated Mediation Server port** must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="ff7c6-127">Esse intervalo de portas é definido no Skype for Business Server e nos Pools de Mediação.</span><span class="sxs-lookup"><span data-stu-id="ff7c6-127">This port range is defined under Skype for Business Server and Mediation Pools.</span></span> <span data-ttu-id="ff7c6-128">Clique com o botão direito do mouse no pool de interesse do Servidor de Mediação e selecione **Editar Propriedades.**</span><span class="sxs-lookup"><span data-stu-id="ff7c6-128">Right-click the Mediation Server pool of interest, and select **Edit Properties**.</span></span> <span data-ttu-id="ff7c6-129">Especifique a faixa de porta no campo **Portas de ouvinte**.</span><span class="sxs-lookup"><span data-stu-id="ff7c6-129">Specify the port range in the **Listening ports** field.</span></span>
  
10. <span data-ttu-id="ff7c6-130">Certifique-se de que o par definido está em execução e usando o FQDN ou endereço IP especificado.</span><span class="sxs-lookup"><span data-stu-id="ff7c6-130">Be sure that the peer you defined is running and using the FQDN or IP address that you specified.</span></span> <span data-ttu-id="ff7c6-131">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="ff7c6-131">Then click **Finish**.</span></span>
    
11. <span data-ttu-id="ff7c6-132">Clique com o botão direito do mouse **no nó do Skype for Business Server** e clique em Publicar **Topologia.**</span><span class="sxs-lookup"><span data-stu-id="ff7c6-132">Right-click the **Skype for Business Server** node, and then click **Publish Topology**.</span></span>
    

