---
title: 'Lync Server 2013: definir um gateway no construtor de topologias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a gateway in Topology Builder
ms:assetid: 456e5a96-d9f6-42a6-862c-a69464391628
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425945(v=OCS.15)
ms:contentKeyID: 48184036
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23286d5bb6cd8b1a1b695776258ad5e131743b8d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-gateway-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="85786-102">Definir um gateway no construtor de topologia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85786-102">Define a gateway in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85786-103">_**Última modificação do tópico:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="85786-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="85786-104">Siga estas etapas para usar o construtor de topologias a fim de definir um *ponto* com o qual você pode associar um servidor de mediação para fornecer conectividade à rede telefônica pública comutada (PSTN) para usuários habilitados para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="85786-104">Follow these steps to use Topology Builder to define a *peer* with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="85786-105">Um ponto para o servidor de mediação pode ser um gateway PSTN, um IP-PBX ou um controlador de borda da sessão (SBC) para um provedor de serviços de telefonia da Internet (ITSP) ao qual você se conecta Configurando um tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="85786-105">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="85786-106">Este tópico pressupõe que você tenha configurado pelo menos um pool de front-ends interno ou servidor Standard Edition em pelo menos um site central com um servidor de mediação posicionado ou autônomo, conforme descrito em <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">define and configure a front end pool or Standard Edition Server in Lync server 2013</A> e <A href="lync-server-2013-publish-the-topology.md">publish the Topology in Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="85786-106">This topic assumes that you have set up at least one internal Front End pool or Standard Edition server in at least one central site with a collocated or stand-alone Mediation Server, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation.</span></span> <span data-ttu-id="85786-107">Este tópico também pressupõe que você verificou que sua infraestrutura atende aos pré-requisitos descritos nos <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">pré-requisitos de software para o Enterprise Voice no Lync server 2013</A> e <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">pré-requisitos de segurança e configuração para o Enterprise Voice no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="85786-107">This topic also assumes that you have verified that your infrastructure meets the prerequisites described in <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software prerequisites for Enterprise Voice in Lync Server 2013</A> and <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="85786-108">Definir um ponto para o Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="85786-108">To Define a Peer for the Mediation Server</span></span>

1.  <span data-ttu-id="85786-109">Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="85786-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="85786-110">Em Lync Server 2013, o nome do site, componentes compartilhados, clique com o botão direito do mouse no nó **gateways PSTN** e clique em **novo gateway PSTN**.</span><span class="sxs-lookup"><span data-stu-id="85786-110">Under Lync Server 2013, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
    
    <span data-ttu-id="85786-111">![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")</span><span class="sxs-lookup"><span data-stu-id="85786-111">![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")</span></span>

3.  <span data-ttu-id="85786-112">Em **Definir Novo Gateway IP/PSTN**, digite o nome de domínio totalmente qualificado (FQDN) ou o endereço IP do ponto e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="85786-112">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    <span data-ttu-id="85786-113">![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")</span><span class="sxs-lookup"><span data-stu-id="85786-113">![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="85786-114">Se você especificar Transport Layer Security (TLS) como o tipo de transporte, deverá especificar o FQDN em vez do endereço IP do par do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="85786-114">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span>

    
    </div>

4.  <span data-ttu-id="85786-115">Defina um modo de ouvinte (IPv4 ou IPv6) ou o endereço IP do seu novo gateway PSTN e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="85786-115">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>
    
    <span data-ttu-id="85786-116">![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")</span><span class="sxs-lookup"><span data-stu-id="85786-116">![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")</span></span>

5.  <span data-ttu-id="85786-117">Defina um *tronco raiz* par ao gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="85786-117">Define a *root trunk* for the PSTN gateway.</span></span> <span data-ttu-id="85786-118">Um tronco é uma conexão lógica entre um servidor de mediação e um gateway identificado exclusivamente pela tupla.</span><span class="sxs-lookup"><span data-stu-id="85786-118">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="85786-119">{Servidor de mediação FQDN, porta de escuta do servidor de mediação (TLS ou TCP): IP e FQDN do gateway, porta de escuta do gateway}</span><span class="sxs-lookup"><span data-stu-id="85786-119">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
      - <span data-ttu-id="85786-120">Ao definir um gateway PSTN no construtor de topologia, você deve definir um tronco de raiz para adicionar com sucesso o gateway PSTN à sua topologia.</span><span class="sxs-lookup"><span data-stu-id="85786-120">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
      - <span data-ttu-id="85786-121">A árvore de raiz não pode ser removida até que o gateway PSTN associado seja removido.</span><span class="sxs-lookup"><span data-stu-id="85786-121">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
    <span data-ttu-id="85786-122">![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")</span><span class="sxs-lookup"><span data-stu-id="85786-122">![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")</span></span>

6.  <span data-ttu-id="85786-123">Em **porta de escuta para gateway IP/PSTN**, digite a porta de escuta que o gateway, PBX ou SBC usará para mensagens SIP do servidor de mediação que serão associadas ao tronco raiz do gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="85786-123">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="85786-124">(Por padrão, as portas são 5066 para protocolo TCP e 5067 para protocolo TLS em um gateway PSTN, PBX ou SBC.</span><span class="sxs-lookup"><span data-stu-id="85786-124">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="85786-125">Em um aparelho de filial persistente em um site de filial, as portas padrão são 5081 para TCP e 5082 para TLS.</span><span class="sxs-lookup"><span data-stu-id="85786-125">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>

7.  <span data-ttu-id="85786-126">Em **Protocolo de Transporte SIP**, clique no tipo de transporte que o ponto usa e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="85786-126">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="85786-127">Por motivos de segurança, é altamente recomendável implantar um ponto no servidor de mediação que possa usar o TLS.</span><span class="sxs-lookup"><span data-stu-id="85786-127">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span>

    
    </div>

8.  <span data-ttu-id="85786-128">Em **servidor de mediação associado**, selecione o pool do servidor de mediação a ser associado ao tronco raiz desse gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="85786-128">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>

9.  <span data-ttu-id="85786-129">Em **porta de servidor de mediação associada**, digite a porta de escuta que o servidor de mediação usará para mensagens SIP do gateway.</span><span class="sxs-lookup"><span data-stu-id="85786-129">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="85786-130">Com suporte a vários troncos no Lync Server 2013, várias portas de sinalização SIP podem ser definidas no servidor de mediação a ser usado para comunicação com vários gateways PSTN.</span><span class="sxs-lookup"><span data-stu-id="85786-130">With multiple trunk support in Lync Server 2013, multiple SIP signaling ports can be defined on the Mediation Server to be used for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="85786-131">Ao definir um tronco, a <STRONG>porta do servidor de mediação associada</STRONG> deve estar dentro do intervalo das portas de escuta para o respectivo protocolo permitido pelo servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="85786-131">When defining a trunk, the <STRONG>Associated Mediation Server port</STRONG> must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="85786-132">Esse intervalo de porta é definido em pools do Lync Server 2013 e Mediation.</span><span class="sxs-lookup"><span data-stu-id="85786-132">This port range is defined under Lync Server 2013 and Mediation Pools.</span></span> <span data-ttu-id="85786-133">Clique com o botão direito do mouse no pool de servidores de mediação de interesse e selecione <STRONG>Editar propriedades</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="85786-133">Right-click the Mediation Server pool of interest, and select <STRONG>Edit Properties</STRONG>.</span></span> <span data-ttu-id="85786-134">Especifique a faixa de porta no campo <STRONG>Portas de ouvinte</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="85786-134">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span></span>

    
    </div>

10. <span data-ttu-id="85786-135">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="85786-135">Click **Finish**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="85786-136">Antes de finalizar esta etapa, certifique-se se o ponto definido está funcionando e usando o FQDN ou o endereço IP que você especificou.</span><span class="sxs-lookup"><span data-stu-id="85786-136">Before you finish this step, be sure that the peer that you defined is running and using the FQDN or IP address that you specified.</span></span>



</div>

<span data-ttu-id="85786-137">Em seguida, para adicionar o par à topologia, siga os procedimentos em [publicar a topologia no Lync Server 2013](lync-server-2013-publish-the-topology.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="85786-137">Next, to add the peer to the topology, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation.</span></span> <span data-ttu-id="85786-138">Você deve publicar sua topologia cada vez que usar o construtor de topologias para criar ou modificar sua topologia, para que os dados possam ser usados para instalar os arquivos para servidores que estão executando o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="85786-138">You must publish your topology each time that you use Topology Builder to build or modify your topology, so that the data can be used to install the files for servers that are running Lync Server.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="85786-139">Confira Também</span><span class="sxs-lookup"><span data-stu-id="85786-139">See Also</span></span>


[<span data-ttu-id="85786-140">Modificar um tronco no construtor de topologia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85786-140">Modify a trunk in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

