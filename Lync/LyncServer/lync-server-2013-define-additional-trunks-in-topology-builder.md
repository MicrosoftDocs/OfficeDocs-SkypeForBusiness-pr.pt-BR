---
title: 'Lync Server 2013: definir troncos adicionais no construtor de topologias'
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
ms.openlocfilehash: c55e8073bd1ad1bb2db69096e4e58aa2b148e775
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728481"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-additional-trunks-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="db51a-102">Definir troncos adicionais no construtor de topologias no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db51a-102">Define additional trunks in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db51a-103">_**Tópico da última modificação:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="db51a-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="db51a-104">Siga estas etapas para usar o construtor de topologias para definir um tronco adicional ao qual você pode associar um *par* com um servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="db51a-104">Follow these steps to use Topology Builder to define an additional trunk to which you can associate a *peer* with a Mediation Server.</span></span> <span data-ttu-id="db51a-105">Um par fornece aos usuários habilitados para o Enterprise Voice com conectividade com a rede telefônica pública comutada (PSTN).</span><span class="sxs-lookup"><span data-stu-id="db51a-105">A peer provides users enabled for Enterprise Voice with connectivity to the public switched telephone network (PSTN).</span></span> <span data-ttu-id="db51a-106">Um ponto pode ser um gateway PSTN, um PBX IP ou um Controlador de Borda da Sessão (SBC) para um Provedor de Serviço Telefônico de Internet (ITSP).</span><span class="sxs-lookup"><span data-stu-id="db51a-106">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span> <span data-ttu-id="db51a-107">O tronco define essa conexão entre o servidor de mediação e o par.</span><span class="sxs-lookup"><span data-stu-id="db51a-107">The trunk defines this connection between the Mediation Server and peer.</span></span> <span data-ttu-id="db51a-108">Vários troncos podem ser definidos por servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="db51a-108">Multiple trunks can be defined per Mediation Server.</span></span> <span data-ttu-id="db51a-109">Um servidor de mediação pode ser associado a vários pares.</span><span class="sxs-lookup"><span data-stu-id="db51a-109">A Mediation Server can be associated with multiple peers.</span></span>

<span data-ttu-id="db51a-110">Um tronco é uma conexão lógica entre um servidor de mediação e um gateway identificado exclusivamente pela tupla:</span><span class="sxs-lookup"><span data-stu-id="db51a-110">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple:</span></span>

<span data-ttu-id="db51a-111">{Servidor de mediação do FQDN, porta de escuta do servidor de mediação (TLS ou TCP): IP e FQDN do gateway, porta de escuta do gateway}</span><span class="sxs-lookup"><span data-stu-id="db51a-111">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="db51a-112">Este tópico pressupõe que você tenha configurado um gateway PSTN e um tronco raiz com pelo menos um servidor ou pool de mediação posicionado ou autônomo, conforme descrito em <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">definir um gateway no construtor de topologias no Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="db51a-112">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Define a gateway in Topology Builder in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="db51a-113">Este tópico pressupõe que você tenha configurado pelo menos um servidor front-end ou um servidor Standard Edition em pelo menos um site central, conforme descrito em <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definir e configurar um servidor front-end ou um servidor Standard Edition no Lync server 2013</A> e <A href="lync-server-2013-publish-the-topology.md">publicar a topologia no Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="db51a-113">This topic assumes that you have set up at least one Front End pool or Standard Edition server in at least one central site, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="db51a-114">Para definir um tronco adicional entre um servidor de mediação e um gateway de mesmo nível</span><span class="sxs-lookup"><span data-stu-id="db51a-114">To Define an additional Trunk between a Mediation Server and a Gateway Peer</span></span>

1.  <span data-ttu-id="db51a-115">Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="db51a-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="db51a-116">Em Lync Server 2013, o nome do seu site, **componentes compartilhados**, clique com o botão direito do mouse no nó **troncos** e, em seguida, clique em **novo tronco**.</span><span class="sxs-lookup"><span data-stu-id="db51a-116">Under Lync Server 2013, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
    
    <span data-ttu-id="db51a-117">![Tela de estrutura de arquivos do Lync Server Topology Builder](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Tela de estrutura de arquivos do Lync Server Topology Builder")</span><span class="sxs-lookup"><span data-stu-id="db51a-117">![Lync Server Topology Builder file structure screen](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Lync Server Topology Builder file structure screen")</span></span>

3.  <span data-ttu-id="db51a-118">Em **Definir Novo Tronco**, especifique um nome amigável para identificar exclusivamente o tronco.</span><span class="sxs-lookup"><span data-stu-id="db51a-118">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="db51a-119">Você não pode ter dois troncos com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="db51a-119">You cannot have two trunks with the same name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="db51a-120">Se você especificar Transport Layer Security (TLS) como o tipo de transporte, você deve especificar o FQDN em vez do endereço IP do par do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="db51a-120">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span>

    
    </div>

4.  <span data-ttu-id="db51a-121">Sob **Gateway PSTN associado**, selecione o ponto de gateway PSTN para associar a este tronco.</span><span class="sxs-lookup"><span data-stu-id="db51a-121">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    
    <span data-ttu-id="db51a-122">![Configurações de Propriedade do par de gateway PSTN para o tronco](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Configurações de Propriedade do par de gateway PSTN para o tronco")</span><span class="sxs-lookup"><span data-stu-id="db51a-122">![Property settings for PSTN gateway peer for trunk](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Property settings for PSTN gateway peer for trunk")</span></span>

5.  <span data-ttu-id="db51a-123">Em **porta de escuta para gateway PSTN**, digite a porta de escuta que o par (gateway PSTN, PBX de IP ou SBC) receberá mensagens SIP do servidor de mediação que serão associadas a esse tronco.</span><span class="sxs-lookup"><span data-stu-id="db51a-123">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="db51a-124">As portas de ponto padrão são 5066 para TCP (Transmission Control Protocol) e 5067 para TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="db51a-124">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="db51a-125">As portas da ramificação sobreviventes padrão são 5081 para TCP e 5082 para TLS.</span><span class="sxs-lookup"><span data-stu-id="db51a-125">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>

6.  <span data-ttu-id="db51a-126">Sob **Protocolo de Transporte SIP**, clique no tipo de transporte usado pelo ponto.</span><span class="sxs-lookup"><span data-stu-id="db51a-126">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="db51a-127">Por motivos de segurança, recomendamos enfaticamente que você implante um par para o servidor de mediação que possa usar TLS.</span><span class="sxs-lookup"><span data-stu-id="db51a-127">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span>

    
    </div>

7.  <span data-ttu-id="db51a-128">Em **servidor de mediação associado**, selecione o pool do servidor de mediação para associar ao tronco raiz desse par</span><span class="sxs-lookup"><span data-stu-id="db51a-128">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>

8.  <span data-ttu-id="db51a-129">Em **porta do servidor de mediação associada**, digite a porta de escuta que o servidor de mediação receberá mensagens SIP do par.</span><span class="sxs-lookup"><span data-stu-id="db51a-129">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="db51a-130">Com o suporte a vários troncos no Lync Server 2013, dois troncos com diferentes nomes de tronco não podem ser configurados com a mesma <STRONG>porta do servidor de mediação associada</STRONG> e <STRONG>porta de escuta do gateway IP/PSTN</STRONG></span><span class="sxs-lookup"><span data-stu-id="db51a-130">With multiple trunk support in Lync Server 2013, two trunks with different trunk names cannot be configured with the same <STRONG>Associated Mediation Server port</STRONG> and <STRONG>Listening Port for IP/PSTN gateway</STRONG></span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="db51a-131">Com o suporte a vários troncos no Lync Server 2013, várias portas de sinalização SIP podem ser definidas no servidor de mediação para comunicação com vários pares.</span><span class="sxs-lookup"><span data-stu-id="db51a-131">With multiple trunk support in Lync Server 2013, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="db51a-132">Ao definir um tronco, o número da <STRONG>porta do servidor de mediação associado</STRONG> deve estar dentro do intervalo das portas de escuta para o respectivo protocolo permitido pelo servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="db51a-132">When defining a trunk, the <STRONG>Associated Mediation Server port</STRONG> number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="db51a-133">Esse intervalo de porta é definido nos pools do Lync Server 2013 e do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="db51a-133">This port range is defined under Lync Server 2013 and Mediation Server pools.</span></span> <span data-ttu-id="db51a-134">Clique com o botão direito do mouse no pool do servidor de mediação relevante e selecione <STRONG>Editar propriedades</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="db51a-134">Right-click the relevant Mediation Server pool, and select <STRONG>Edit Properties</STRONG>.</span></span> <span data-ttu-id="db51a-135">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span><span class="sxs-lookup"><span data-stu-id="db51a-135">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span></span>

    
    </div>

9.  <span data-ttu-id="db51a-136">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="db51a-136">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="db51a-137">Confira também</span><span class="sxs-lookup"><span data-stu-id="db51a-137">See Also</span></span>


[<span data-ttu-id="db51a-138">Modificar um tronco no construtor de topologias no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db51a-138">Modify a trunk in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

