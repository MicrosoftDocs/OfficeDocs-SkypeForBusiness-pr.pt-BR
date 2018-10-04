---
title: Definir troncos adicionais no construtor de topologia no Skype para Business Server
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
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 'Resumo: Saiba como definir um tronco adicional entre um servidor de mediação e um par de gateway no construtor de topologia no Skype para Business Server.'
ms.openlocfilehash: 1f70a1d99ebff1bbc1fbd162b322185b3cd21690
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370656"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="8793d-103">Definir troncos adicionais no construtor de topologia no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="8793d-103">Define additional trunks in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="8793d-104">**Resumo:** Saiba como definir um tronco adicional entre um servidor de mediação e um par de gateway no construtor de topologia no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="8793d-104">**Summary:** Learn how to define an additional trunk between a Mediation Server and a gateway peer in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="8793d-105">Siga estas etapas para definir um tronco adicional para o qual você pode associar um ponto com um servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="8793d-105">Follow these steps to define an additional trunk to which you can associate a peer with a Mediation Server.</span></span> <span data-ttu-id="8793d-106">Um ponto fornece aos usuários habilitados para o Enterprise Voice com conectividade para a comutação telefônica PSTN (rede pública).</span><span class="sxs-lookup"><span data-stu-id="8793d-106">A peer provides users enabled for Enterprise Voice with connectivity to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="8793d-107">Um ponto pode ser um gateway PSTN, um PBX IP ou um Controlador de Borda da Sessão (SBC) para um Provedor de Serviço Telefônico de Internet (ITSP).</span><span class="sxs-lookup"><span data-stu-id="8793d-107">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span>
  
<span data-ttu-id="8793d-108">Um tronco é uma conexão lógica entre um servidor de mediação e um gateway.</span><span class="sxs-lookup"><span data-stu-id="8793d-108">A trunk is a logical connection between a Mediation Server and a gateway.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8793d-109">Este tópico pressupõe que você tenha o programa de instalação um gateway PSTN e tronco raiz com pelo menos um servidor de mediação autônomo ou posicionado pool ou, conforme descrito em [definir um gateway no construtor de topologia no Skype para Business Server](define-a-gateway.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="8793d-109">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in [Define a gateway in Topology Builder in Skype for Business Server](define-a-gateway.md) in the Deployment documentation.</span></span>
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="8793d-110">Para definir um tronco adicional entre um servidor de mediação e um par de gateway</span><span class="sxs-lookup"><span data-stu-id="8793d-110">To define an additional trunk between a Mediation Server and a gateway peer</span></span>

1. <span data-ttu-id="8793d-111">Inicie o construtor de topologia: Clique em **Iniciar**, clique em **Todos os programas**, clique em **Skype para Business Server 2015**e clique **Skype para Business Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="8793d-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="8793d-112">Em Skype para Business Server, o nome do seu site, **Componentes compartilhados**, clique com botão direito no nó **troncos** e clique em **Novo tronco**.</span><span class="sxs-lookup"><span data-stu-id="8793d-112">Under Skype for Business Server, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
   1. <span data-ttu-id="8793d-p102">Em **Definir Novo Tronco**, especifique um nome amigável para identificar exclusivamente o tronco. Você não pode ter dois troncos com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="8793d-p102">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk. You cannot have two trunks with the same name.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="8793d-115">Se você especificar a segurança de camada de transporte (TLS) como o tipo de transporte, você deve especificar o FQDN ao invés do endereço IP do ponto do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="8793d-115">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
3. <span data-ttu-id="8793d-116">Sob **Gateway PSTN associado**, selecione o ponto de gateway PSTN para associar a este tronco.</span><span class="sxs-lookup"><span data-stu-id="8793d-116">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    5. <span data-ttu-id="8793d-117">Em **Porta de escuta do gateway PSTN**, digite a porta de escuta do ponto (gateway PSTN, IP-PBX ou SBC) receberá mensagens SIP do servidor de mediação que deve ser associado esse tronco.</span><span class="sxs-lookup"><span data-stu-id="8793d-117">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="8793d-118">As portas de ponto padrão são 5066 para TCP (Transmission Control Protocol) e 5067 para TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="8793d-118">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="8793d-119">As portas de aparelho de filial persistente padrão são 5081 para TCP e 5082 para TLS.</span><span class="sxs-lookup"><span data-stu-id="8793d-119">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>
    
4. <span data-ttu-id="8793d-120">Sob **Protocolo de Transporte SIP**, clique no tipo de transporte usado pelo ponto.</span><span class="sxs-lookup"><span data-stu-id="8793d-120">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8793d-121">Por motivos de segurança, é altamente recomendável que você implante um par ao servidor de mediação que possa utilizar TLS.</span><span class="sxs-lookup"><span data-stu-id="8793d-121">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
5. <span data-ttu-id="8793d-122">Em **Servidor de mediação associado**, selecione o pool de servidor de mediação para associar o tronco raiz deste ponto</span><span class="sxs-lookup"><span data-stu-id="8793d-122">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>
    
6. <span data-ttu-id="8793d-123">Em **porta do servidor de mediação associado**, digite a porta de escuta do servidor de mediação receberá mensagens SIP do ponto.</span><span class="sxs-lookup"><span data-stu-id="8793d-123">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8793d-124">Com suporte a troncos múltiplos no Skype para Business Server, dois troncos com nomes de tronco diferentes podem ser configurados com a mesma **porta do servidor de mediação associado** e **Porta de escuta do gateway IP/PSTN**</span><span class="sxs-lookup"><span data-stu-id="8793d-124">With multiple trunk support in Skype for Business Server, two trunks with different trunk names cannot be configured with the same **Associated Mediation Server port** and **Listening Port for IP/PSTN gateway**</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="8793d-125">Com suporte a troncos múltiplos no Skype para Business Server, as portas de sinalização do SIP de vários pode ser definido no servidor de mediação para comunicação com vários correspondentes.</span><span class="sxs-lookup"><span data-stu-id="8793d-125">With multiple trunk support in Skype for Business Server, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="8793d-126">Ao definir um tronco, o número da **porta do servidor de mediação associado** deve ser dentro do intervalo das portas de escuta para o protocolo respectivo permitidos pelo servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="8793d-126">When defining a trunk, the **Associated Mediation Server port** number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="8793d-127">Esse intervalo de portas é definido em Skype para pools Business Server e o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="8793d-127">This port range is defined under Skype for Business Server and Mediation Server pools.</span></span> <span data-ttu-id="8793d-128">O pool do servidor de mediação relevante do mouse em e selecione **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="8793d-128">Right-click the relevant Mediation Server pool, and select **Edit Properties**.</span></span> <span data-ttu-id="8793d-129">Especifique o intervalo de portas no campo **Portas de escuta**.</span><span class="sxs-lookup"><span data-stu-id="8793d-129">Specify the port range in the **Listening ports** field.</span></span>
  
7. <span data-ttu-id="8793d-130">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8793d-130">Click **OK**.</span></span> 
    

