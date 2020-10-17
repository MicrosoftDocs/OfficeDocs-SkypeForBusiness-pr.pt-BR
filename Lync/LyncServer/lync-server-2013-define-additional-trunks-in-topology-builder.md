---
title: 'Lync Server 2013: definir troncos adicionais no construtor de topologias'
description: 'Lync Server 2013: definir troncos adicionais no construtor de topologias.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define additional trunks in Topology Builder
ms:assetid: e68b8377-50a2-452a-bf5c-910929e34236
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721915(v=OCS.15)
ms:contentKeyID: 49733849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57983d3e4d6a47c14f2dcdc153fe6872a33eb6e9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567557"
---
# <a name="define-additional-trunks-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="a63b4-103">Definir troncos adicionais no construtor de topologias no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a63b4-103">Define additional trunks in Topology Builder in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a63b4-104">_**Última modificação do tópico:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="a63b4-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="a63b4-105">Siga estas etapas para usar o construtor de topologias para definir um tronco adicional ao qual você pode associar um *ponto* a um servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="a63b4-105">Follow these steps to use Topology Builder to define an additional trunk to which you can associate a *peer* with a Mediation Server.</span></span> <span data-ttu-id="a63b4-106">Um ponto fornece aos usuários habilitados para o Enterprise Voice com conectividade com a rede telefônica pública comutada (PSTN).</span><span class="sxs-lookup"><span data-stu-id="a63b4-106">A peer provides users enabled for Enterprise Voice with connectivity to the public switched telephone network (PSTN).</span></span> <span data-ttu-id="a63b4-107">Um ponto pode ser um gateway PSTN, um IP-PBX ou um controlador de borda da sessão (SBC) para um provedor de serviços de telefonia da Internet (ITSP).</span><span class="sxs-lookup"><span data-stu-id="a63b4-107">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span> <span data-ttu-id="a63b4-108">O tronco define essa conexão entre o servidor de mediação e o ponto.</span><span class="sxs-lookup"><span data-stu-id="a63b4-108">The trunk defines this connection between the Mediation Server and peer.</span></span> <span data-ttu-id="a63b4-109">Vários troncos podem ser definidos por servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="a63b4-109">Multiple trunks can be defined per Mediation Server.</span></span> <span data-ttu-id="a63b4-110">Um servidor de mediação pode ser associado a vários pares.</span><span class="sxs-lookup"><span data-stu-id="a63b4-110">A Mediation Server can be associated with multiple peers.</span></span>

<span data-ttu-id="a63b4-111">Um tronco é uma conexão lógica entre um servidor de mediação e um gateway identificado exclusivamente pela tupla:</span><span class="sxs-lookup"><span data-stu-id="a63b4-111">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple:</span></span>

<span data-ttu-id="a63b4-112">{Servidor de mediação FQDN, porta de escuta do servidor de mediação (TLS ou TCP): IP e FQDN do gateway, porta de escuta do gateway}</span><span class="sxs-lookup"><span data-stu-id="a63b4-112">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a63b4-113">Este tópico pressupõe que você tenha configurado um gateway PSTN e um tronco raiz com pelo menos um servidor ou pool de mediação autônomo ou localizado, conforme descrito em <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">definir um gateway no construtor de topologias no Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="a63b4-113">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Define a gateway in Topology Builder in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="a63b4-114">Este tópico pressupõe que você tenha configurado pelo menos um pool de front-ends ou servidor Standard Edition em pelo menos um site central, conforme descrito em <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">define and configure a front end pool or Standard Edition Server in Lync server 2013</A> e <A href="lync-server-2013-publish-the-topology.md">publish the Topology in Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="a63b4-114">This topic assumes that you have set up at least one Front End pool or Standard Edition server in at least one central site, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="a63b4-115">Para definir um tronco adicional entre um servidor de mediação e um ponto de gateway</span><span class="sxs-lookup"><span data-stu-id="a63b4-115">To Define an additional Trunk between a Mediation Server and a Gateway Peer</span></span>

1.  <span data-ttu-id="a63b4-116">Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a63b4-116">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="a63b4-117">Em Lync Server 2013, o nome do site, **componentes compartilhados**, clique com o botão direito do mouse no nó **troncos** e, em seguida, clique em **novo tronco**.</span><span class="sxs-lookup"><span data-stu-id="a63b4-117">Under Lync Server 2013, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
    
    <span data-ttu-id="a63b4-118">![Tela da estrutura de arquivos do construtor de topologias do Lync Server](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Tela da estrutura de arquivos do construtor de topologias do Lync Server")</span><span class="sxs-lookup"><span data-stu-id="a63b4-118">![Lync Server Topology Builder file structure screen](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Lync Server Topology Builder file structure screen")</span></span>

3.  <span data-ttu-id="a63b4-119">Em **definir novo tronco**, especifique um nome amigável para identificar exclusivamente o tronco.</span><span class="sxs-lookup"><span data-stu-id="a63b4-119">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="a63b4-120">Não é possível ter dois troncos com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="a63b4-120">You cannot have two trunks with the same name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a63b4-121">Se você especificar Transport Layer Security (TLS) como o tipo de transporte, deverá especificar o FQDN em vez do endereço IP do par do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="a63b4-121">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span>

    
    </div>

4.  <span data-ttu-id="a63b4-122">Em **Gateway PSTN associado**, selecione o ponto de gateway PSTN para associar a este tronco.</span><span class="sxs-lookup"><span data-stu-id="a63b4-122">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    
    <span data-ttu-id="a63b4-123">![Configurações de propriedade para o par de gateway PSTN para o tronco](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Configurações de propriedade para o par de gateway PSTN para o tronco")</span><span class="sxs-lookup"><span data-stu-id="a63b4-123">![Property settings for PSTN gateway peer for trunk](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Property settings for PSTN gateway peer for trunk")</span></span>

5.  <span data-ttu-id="a63b4-124">Em **porta de escuta para gateway PSTN**, digite a porta de escuta que o par (gateway PSTN, IP-PBX ou SBC) receberá mensagens SIP do servidor de mediação que serão associadas a esse tronco.</span><span class="sxs-lookup"><span data-stu-id="a63b4-124">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="a63b4-125">As portas de par padrão são 5066 para TCP (Transmission Control Protocol) e 5067 para TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="a63b4-125">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="a63b4-126">As portas do aparelho de filial persistente padrão são 5081 para TCP e 5082 para TLS.</span><span class="sxs-lookup"><span data-stu-id="a63b4-126">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>

6.  <span data-ttu-id="a63b4-127">Em **protocolo de transporte SIP**, clique no tipo de transporte que o ponto usa.</span><span class="sxs-lookup"><span data-stu-id="a63b4-127">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a63b4-128">Por motivos de segurança, é altamente recomendável implantar um ponto no servidor de mediação que possa usar o TLS.</span><span class="sxs-lookup"><span data-stu-id="a63b4-128">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span>

    
    </div>

7.  <span data-ttu-id="a63b4-129">Em **servidor de mediação associado**, selecione o pool do servidor de mediação a ser associado ao tronco raiz deste ponto</span><span class="sxs-lookup"><span data-stu-id="a63b4-129">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>

8.  <span data-ttu-id="a63b4-130">Em **porta de servidor de mediação associada**, digite a porta de escuta que o servidor de mediação receberá mensagens SIP do ponto.</span><span class="sxs-lookup"><span data-stu-id="a63b4-130">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a63b4-131">Com suporte a vários troncos no Lync Server 2013, dois troncos com nomes de tronco diferentes não podem ser configurados com a mesma <STRONG>porta de servidor de mediação associada</STRONG> e <STRONG>porta de escuta para gateway IP/PSTN</STRONG></span><span class="sxs-lookup"><span data-stu-id="a63b4-131">With multiple trunk support in Lync Server 2013, two trunks with different trunk names cannot be configured with the same <STRONG>Associated Mediation Server port</STRONG> and <STRONG>Listening Port for IP/PSTN gateway</STRONG></span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a63b4-132">Com suporte a vários troncos no Lync Server 2013, várias portas de sinalização SIP podem ser definidas no servidor de mediação para comunicação com vários pares.</span><span class="sxs-lookup"><span data-stu-id="a63b4-132">With multiple trunk support in Lync Server 2013, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="a63b4-133">Ao definir um tronco, o número da <STRONG>porta do servidor de mediação associado</STRONG> deve estar dentro do intervalo das portas de escuta para o respectivo protocolo permitido pelo servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="a63b4-133">When defining a trunk, the <STRONG>Associated Mediation Server port</STRONG> number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="a63b4-134">Esse intervalo de porta é definido em pools do Lync Server 2013 e do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="a63b4-134">This port range is defined under Lync Server 2013 and Mediation Server pools.</span></span> <span data-ttu-id="a63b4-135">Clique com o botão direito do mouse no pool do servidor de mediação relevante e selecione <STRONG>Editar propriedades</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a63b4-135">Right-click the relevant Mediation Server pool, and select <STRONG>Edit Properties</STRONG>.</span></span> <span data-ttu-id="a63b4-136">Especifique a faixa de porta no campo <STRONG>Portas de ouvinte</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a63b4-136">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span></span>

    
    </div>

9.  <span data-ttu-id="a63b4-137">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a63b4-137">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a63b4-138">Confira também</span><span class="sxs-lookup"><span data-stu-id="a63b4-138">See Also</span></span>


[<span data-ttu-id="a63b4-139">Modificar um tronco no construtor de topologia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a63b4-139">Modify a trunk in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

