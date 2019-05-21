---
title: Definir troncos adicionais no construtor de topologias no Skype for Business Server
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
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 'Resumo: saiba como definir um tronco adicional entre um servidor de mediação e um peer de gateway no construtor de topologias no Skype for Business Server.'
ms.openlocfilehash: de6cfd45c9e5f8440fcbcf6b6098a82edda752f0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303309"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="56ff6-103">Definir troncos adicionais no construtor de topologias no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="56ff6-103">Define additional trunks in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="56ff6-104">**Resumo:** Saiba como definir um tronco adicional entre um servidor de mediação e um peer de gateway no construtor de topologias no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="56ff6-104">**Summary:** Learn how to define an additional trunk between a Mediation Server and a gateway peer in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="56ff6-105">Siga estas etapas para definir um tronco adicional ao qual você pode associar um par com um servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="56ff6-105">Follow these steps to define an additional trunk to which you can associate a peer with a Mediation Server.</span></span> <span data-ttu-id="56ff6-106">Um par fornece aos usuários habilitados para o Enterprise Voice com conectividade com a rede telefônica pública comutada (PSTN).</span><span class="sxs-lookup"><span data-stu-id="56ff6-106">A peer provides users enabled for Enterprise Voice with connectivity to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="56ff6-107">Um ponto pode ser um gateway PSTN, um PBX IP ou um Controlador de Borda da Sessão (SBC) para um Provedor de Serviço Telefônico de Internet (ITSP).</span><span class="sxs-lookup"><span data-stu-id="56ff6-107">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span>
  
<span data-ttu-id="56ff6-108">Um tronco é uma conexão lógica entre um servidor de mediação e um gateway.</span><span class="sxs-lookup"><span data-stu-id="56ff6-108">A trunk is a logical connection between a Mediation Server and a gateway.</span></span>
  
> [!NOTE]
> <span data-ttu-id="56ff6-109">Este tópico pressupõe que você tenha configurado um gateway PSTN e um tronco raiz com pelo menos um servidor ou pool de mediação posicionado ou autônomo, conforme descrito em [definir um gateway no construtor de topologias no Skype for Business Server](define-a-gateway.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="56ff6-109">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in [Define a gateway in Topology Builder in Skype for Business Server](define-a-gateway.md) in the Deployment documentation.</span></span>
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="56ff6-110">Para definir um tronco adicional entre um servidor de mediação e um gateway de mesmo nível</span><span class="sxs-lookup"><span data-stu-id="56ff6-110">To define an additional trunk between a Mediation Server and a gateway peer</span></span>

1. <span data-ttu-id="56ff6-111">Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, clique em **Skype for Business Server 2015**e, em seguida, clique em **Skype for Business Server 2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="56ff6-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="56ff6-112">Em Skype for Business Server, o nome do seu site, **componentes compartilhados**, clique com \*\*\*\* o botão direito do mouse no nó troncos e, em seguida, clique em **novo tronco**.</span><span class="sxs-lookup"><span data-stu-id="56ff6-112">Under Skype for Business Server, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
   1. <span data-ttu-id="56ff6-113">Em **Definir Novo Tronco**, especifique um nome amigável para identificar exclusivamente o tronco.</span><span class="sxs-lookup"><span data-stu-id="56ff6-113">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="56ff6-114">Você não pode ter dois troncos com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="56ff6-114">You cannot have two trunks with the same name.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="56ff6-115">Se você especificar Transport Layer Security (TLS) como o tipo de transporte, você deve especificar o FQDN em vez do endereço IP do par do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="56ff6-115">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
3. <span data-ttu-id="56ff6-116">Sob **Gateway PSTN associado**, selecione o ponto de gateway PSTN para associar a este tronco.</span><span class="sxs-lookup"><span data-stu-id="56ff6-116">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    5. <span data-ttu-id="56ff6-117">Em **porta de escuta para gateway PSTN**, digite a porta de escuta que o par (gateway PSTN, PBX de IP ou SBC) receberá mensagens SIP do servidor de mediação que serão associadas a esse tronco.</span><span class="sxs-lookup"><span data-stu-id="56ff6-117">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="56ff6-118">As portas de ponto padrão são 5066 para TCP (Transmission Control Protocol) e 5067 para TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="56ff6-118">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="56ff6-119">As portas da ramificação sobreviventes padrão são 5081 para TCP e 5082 para TLS.</span><span class="sxs-lookup"><span data-stu-id="56ff6-119">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>
    
4. <span data-ttu-id="56ff6-120">Sob **Protocolo de Transporte SIP**, clique no tipo de transporte usado pelo ponto.</span><span class="sxs-lookup"><span data-stu-id="56ff6-120">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="56ff6-121">Por motivos de segurança, recomendamos enfaticamente que você implante um par para o servidor de mediação que possa usar TLS.</span><span class="sxs-lookup"><span data-stu-id="56ff6-121">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
5. <span data-ttu-id="56ff6-122">Em **servidor de mediação associado**, selecione o pool do servidor de mediação para associar ao tronco raiz desse par</span><span class="sxs-lookup"><span data-stu-id="56ff6-122">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>
    
6. <span data-ttu-id="56ff6-123">Em **porta do servidor de mediação associada**, digite a porta de escuta que o servidor de mediação receberá mensagens SIP do par.</span><span class="sxs-lookup"><span data-stu-id="56ff6-123">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="56ff6-124">Com o suporte a vários troncos no Skype for Business Server, dois troncos com diferentes nomes de tronco não podem ser configurados com a mesma **porta do servidor de mediação associada** e **porta de escuta do gateway IP/PSTN**</span><span class="sxs-lookup"><span data-stu-id="56ff6-124">With multiple trunk support in Skype for Business Server, two trunks with different trunk names cannot be configured with the same **Associated Mediation Server port** and **Listening Port for IP/PSTN gateway**</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="56ff6-125">Com o suporte a vários troncos no Skype for Business Server, várias portas de sinalização SIP podem ser definidas no servidor de mediação para comunicação com vários pares.</span><span class="sxs-lookup"><span data-stu-id="56ff6-125">With multiple trunk support in Skype for Business Server, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="56ff6-126">Ao definir um tronco, o número da **porta do servidor de mediação associado** deve estar dentro do intervalo das portas de escuta para o respectivo protocolo permitido pelo servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="56ff6-126">When defining a trunk, the **Associated Mediation Server port** number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="56ff6-127">Esse intervalo de porta é definido nos pools do Skype for Business Server e do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="56ff6-127">This port range is defined under Skype for Business Server and Mediation Server pools.</span></span> <span data-ttu-id="56ff6-128">Clique com o botão direito do mouse no pool do servidor de mediação relevante e selecione **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="56ff6-128">Right-click the relevant Mediation Server pool, and select **Edit Properties**.</span></span> <span data-ttu-id="56ff6-129">Specify the port range in the **Listening ports** field.</span><span class="sxs-lookup"><span data-stu-id="56ff6-129">Specify the port range in the **Listening ports** field.</span></span>
  
7. <span data-ttu-id="56ff6-130">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="56ff6-130">Click **OK**.</span></span> 
    

