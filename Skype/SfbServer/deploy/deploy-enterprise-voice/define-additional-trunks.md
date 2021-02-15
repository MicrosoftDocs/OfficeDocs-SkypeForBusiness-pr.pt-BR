---
title: Definir troncos adicionais no Construtor de Topologias no Skype for Business Server
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
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 'Resumo: saiba como definir um tronco adicional entre um Servidor de Mediação e um par de gateway no Construtor de Topologias no Skype for Business Server.'
ms.openlocfilehash: 3aab744761420ab631f17e6b56391f1fab120ccf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836991"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="97d3a-103">Definir troncos adicionais no Construtor de Topologias no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="97d3a-103">Define additional trunks in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="97d3a-104">**Resumo:** Saiba como definir um tronco adicional entre um Servidor de Mediação e um par de gateway no Construtor de Topologias no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="97d3a-104">**Summary:** Learn how to define an additional trunk between a Mediation Server and a gateway peer in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="97d3a-105">Siga estas etapas para definir um tronco adicional ao qual você pode associar um par a um Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="97d3a-105">Follow these steps to define an additional trunk to which you can associate a peer with a Mediation Server.</span></span> <span data-ttu-id="97d3a-106">Um par fornece aos usuários habilitados para o Enterprise Voice a conectividade com a Rede Telefônica Pública Comuada (PSTN).</span><span class="sxs-lookup"><span data-stu-id="97d3a-106">A peer provides users enabled for Enterprise Voice with connectivity to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="97d3a-107">Um par pode ser um gateway PSTN, um IP-PBX ou um Controlador de Borda de Sessão (SBC) para um ITSP (Provedor de Serviços de Telefonia da Internet).</span><span class="sxs-lookup"><span data-stu-id="97d3a-107">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span>
  
<span data-ttu-id="97d3a-108">Um tronco é uma conexão lógica entre um Servidor de Mediação e um gateway.</span><span class="sxs-lookup"><span data-stu-id="97d3a-108">A trunk is a logical connection between a Mediation Server and a gateway.</span></span>
  
> [!NOTE]
> <span data-ttu-id="97d3a-109">Este tópico presume que você tenha configurado um gateway PSTN e um tronco raiz com pelo menos um Servidor de Mediação ou pool autônomo ou colocal, conforme descrito em [Define a gateway in Topology Builder in Skype for Business Server](define-a-gateway.md) na documentação de Implantação.</span><span class="sxs-lookup"><span data-stu-id="97d3a-109">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in [Define a gateway in Topology Builder in Skype for Business Server](define-a-gateway.md) in the Deployment documentation.</span></span>
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="97d3a-110">Para definir um tronco adicional entre um Servidor de Mediação e um par de gateway</span><span class="sxs-lookup"><span data-stu-id="97d3a-110">To define an additional trunk between a Mediation Server and a gateway peer</span></span>

1. <span data-ttu-id="97d3a-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="97d3a-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="97d3a-112">Em Skype for Business Server, seu nome de **site,** **Componentes Compartilhados** , clique com o botão direito do mouse no nó Troncos e clique em **Novo Tronco.**</span><span class="sxs-lookup"><span data-stu-id="97d3a-112">Under Skype for Business Server, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
   1. <span data-ttu-id="97d3a-113">Em **Definir Novo Tronco,** especifique um nome amigável para identificar exclusivamente o tronco.</span><span class="sxs-lookup"><span data-stu-id="97d3a-113">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="97d3a-114">Não é possível ter dois troncos com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="97d3a-114">You cannot have two trunks with the same name.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="97d3a-115">Se você especificar o protocolo TLS como o tipo de transporte, deverá especificar o FQDN em vez do endereço IP do ponto do Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="97d3a-115">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
3. <span data-ttu-id="97d3a-116">Em **Gateway PSTN Associado,** selecione o par de gateway PSTN a ser associado a esse tronco.</span><span class="sxs-lookup"><span data-stu-id="97d3a-116">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    5. <span data-ttu-id="97d3a-117">Em Porta de Escuta para **gateway PSTN,** digite a porta de escuta que o par (gateway PSTN, IP-PBX ou SBC) receberá mensagens SIP do Servidor de Mediação que será associado a esse tronco.</span><span class="sxs-lookup"><span data-stu-id="97d3a-117">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="97d3a-118">As portas pares padrão são 5066 para Protocolo de Controle de Transmissão (TCP) e 5067 para TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="97d3a-118">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="97d3a-119">As portas padrão do Aparelho de Filial São 5081 para TCP e 5082 para TLS.</span><span class="sxs-lookup"><span data-stu-id="97d3a-119">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>
    
4. <span data-ttu-id="97d3a-120">Em **Protocolo de Transporte SIP,** clique no tipo de transporte que o par usa.</span><span class="sxs-lookup"><span data-stu-id="97d3a-120">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="97d3a-121">Por motivos de segurança, recomendamos que você implante um par para o Servidor de Mediação que possa usar TLS.</span><span class="sxs-lookup"><span data-stu-id="97d3a-121">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
5. <span data-ttu-id="97d3a-122">Em **Servidor de Mediação Associado,** selecione o pool do Servidor de Mediação a ser associado ao tronco raiz deste par</span><span class="sxs-lookup"><span data-stu-id="97d3a-122">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>
    
6. <span data-ttu-id="97d3a-123">Em **Porta do Servidor de Mediação** Associado, digite a porta de escuta que o Servidor de Mediação receberá mensagens SIP do par.</span><span class="sxs-lookup"><span data-stu-id="97d3a-123">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="97d3a-124">Com suporte a vários troncos no Skype for Business Server, dois  troncos com nomes de tronco diferentes não podem ser configurados com a mesma porta do Servidor de Mediação Associada e Porta de Escuta para **gateway IP/PSTN**</span><span class="sxs-lookup"><span data-stu-id="97d3a-124">With multiple trunk support in Skype for Business Server, two trunks with different trunk names cannot be configured with the same **Associated Mediation Server port** and **Listening Port for IP/PSTN gateway**</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="97d3a-125">Com suporte a vários troncos no Skype for Business Server, várias portas de sinalização SIP podem ser definidas no Servidor de Mediação para comunicação com vários pares.</span><span class="sxs-lookup"><span data-stu-id="97d3a-125">With multiple trunk support in Skype for Business Server, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="97d3a-126">Ao definir um tronco, o número da porta do Servidor de Mediação Associado deve estar dentro do intervalo das portas de escuta para o respectivo protocolo permitido pelo Servidor de Mediação. </span><span class="sxs-lookup"><span data-stu-id="97d3a-126">When defining a trunk, the **Associated Mediation Server port** number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="97d3a-127">Esse intervalo de portas é definido em pools do Skype for Business Server e do Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="97d3a-127">This port range is defined under Skype for Business Server and Mediation Server pools.</span></span> <span data-ttu-id="97d3a-128">Clique com o botão direito do mouse no pool do Servidor de Mediação relevante e selecione **Editar Propriedades.**</span><span class="sxs-lookup"><span data-stu-id="97d3a-128">Right-click the relevant Mediation Server pool, and select **Edit Properties**.</span></span> <span data-ttu-id="97d3a-129">Especifique a faixa de porta no campo **Portas de ouvinte**.</span><span class="sxs-lookup"><span data-stu-id="97d3a-129">Specify the port range in the **Listening ports** field.</span></span>
  
7. <span data-ttu-id="97d3a-130">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="97d3a-130">Click **OK**.</span></span> 
    

