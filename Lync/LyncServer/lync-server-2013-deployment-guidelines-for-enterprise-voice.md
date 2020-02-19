---
title: 'Lync Server 2013: diretrizes de implantação para o Enterprise Voice'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Enterprise Voice
ms:assetid: 8985bd93-7613-4cef-9c89-51df6049ed9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398694(v=OCS.15)
ms:contentKeyID: 48184733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fc2aee745a362e58003c62f483dda6c63ab244f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135848"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="10bf3-102">Diretrizes de implantação para o Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10bf3-102">Deployment guidelines for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10bf3-103">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="10bf3-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="10bf3-104">Este tópico descreve os pré-requisitos e outras diretrizes a serem consideradas ao planejar a implantação do Lync Server 2013 e da carga de trabalho do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="10bf3-104">This topic describes prerequisites and other guidelines to consider when you are planning to deploy Lync Server 2013 and the Enterprise Voice workload.</span></span>

<div>

## <a name="deployment-prerequisites"></a><span data-ttu-id="10bf3-105">Pré-requisitos de implantação</span><span class="sxs-lookup"><span data-stu-id="10bf3-105">Deployment Prerequisites</span></span>

<span data-ttu-id="10bf3-106">Para obter uma experiência ideal ao implantar o Enterprise Voice, verifique se a infraestrutura de ti, a rede e os sistemas atendem aos seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="10bf3-106">For an optimum experience when deploying Enterprise Voice, make sure that your IT infrastructure, network, and systems meet the following prerequisites:</span></span>

  - <span data-ttu-id="10bf3-107">O Lync Server 2013 Standard Edition ou Enterprise Edition está instalado e operacional em sua rede.</span><span class="sxs-lookup"><span data-stu-id="10bf3-107">Lync Server 2013 Standard Edition or Enterprise Edition is installed and operational on your network.</span></span>

  - <span data-ttu-id="10bf3-108">Todos os servidores de borda são implantados e operados em sua rede de perímetro, incluindo servidores de borda com serviço de borda de acesso, serviço de borda de A/V, serviço de borda de Webconferência e um proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="10bf3-108">All Edge Servers are deployed and operational in your perimeter network, including Edge Servers with Access Edge service, A/V Edge service, Web Conferencing Edge service, and a reverse proxy.</span></span>

  - <span data-ttu-id="10bf3-109">Um ou mais usuários foram criados e habilitados para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="10bf3-109">One or more users have been created and enabled for Lync Server.</span></span>

  - <span data-ttu-id="10bf3-110">O Microsoft Exchange Server 2007 Service Pack 1 (SP1) ou o Service Pack mais recente ou o Microsoft Exchange Server 2010 está instalado.</span><span class="sxs-lookup"><span data-stu-id="10bf3-110">Microsoft Exchange Server 2007 Service Pack 1 (SP1) or latest service pack, or Microsoft Exchange Server 2010 is installed.</span></span> <span data-ttu-id="10bf3-111">Um deles é necessário para integrar a Unificação de mensagens (UM) do Exchange com o Lync Server e fornecer notificações ricas e informações de log de chamadas para pontos de extremidade do cliente.</span><span class="sxs-lookup"><span data-stu-id="10bf3-111">One of these is required for integrating Exchange Unified Messaging (UM) with Lync Server and to provide rich notifications and call log information to client endpoints.</span></span>

  - <span data-ttu-id="10bf3-112">Um número de telefone principal exclusivo foi designado, normalizado e copiado para o atributo **msRTCSIP-line** para cada usuário que deve ser habilitado para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="10bf3-112">A unique primary phone number has been designated, normalized, and copied to the **msRTCSIP-line** attribute for each user who is to be enabled for Enterprise Voice.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="10bf3-113">O Lync Server suporta números e. 164 e números DID (discagem não direta interna).</span><span class="sxs-lookup"><span data-stu-id="10bf3-113">Lync Server supports E.164 numbers and non-Direct Inward Dialing (DID) numbers.</span></span> <span data-ttu-id="10bf3-114">Números não-DID podem ser representados no formato <STRONG> &lt;E. 164&gt;; ext =&lt;Extension&gt; </STRONG> ou como uma cadeia de caracteres de dígitos, com o requisito de que a extensão privada é exclusiva em toda a empresa.</span><span class="sxs-lookup"><span data-stu-id="10bf3-114">Non-DID numbers can be represented in the format <STRONG>&lt;E.164&gt;;ext=&lt;extension&gt;</STRONG> or as a string of digits, with the requirement that the private extension is unique across the enterprise.</span></span> <span data-ttu-id="10bf3-115">Por exemplo, um número particular de 1001 pode ser representado como <STRONG>+1425550100;ext=1001</STRONG>, ou como <STRONG>1001</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="10bf3-115">For example, a private number of 1001 can be represented as <STRONG>+1425550100;ext=1001</STRONG>, or as <STRONG>1001</STRONG>.</span></span> <span data-ttu-id="10bf3-116">Quando representado como <STRONG>1001</STRONG>, a expectativa é de que esse número particular seja exclusivo na empresa.</span><span class="sxs-lookup"><span data-stu-id="10bf3-116">When represented as <STRONG>1001</STRONG>, the expectation is that this private number is unique across the enterprise.</span></span>

    
    </div>

  - <span data-ttu-id="10bf3-117">Os administradores que implantam o Enterprise Voice devem ser membros do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="10bf3-117">Administrators who deploy Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>

  - <span data-ttu-id="10bf3-118">No mínimo, o Office Communicator 2007 é implantado com êxito.</span><span class="sxs-lookup"><span data-stu-id="10bf3-118">At a minimum, Office Communicator 2007 is successfully deployed.</span></span> <span data-ttu-id="10bf3-119">Para usar os recursos novos para esta versão, o Lync 2013 é implantado.</span><span class="sxs-lookup"><span data-stu-id="10bf3-119">To use features new to this release, Lync 2013 is deployed.</span></span>

  - <span data-ttu-id="10bf3-120">A Infraestrutura de chave gerenciada (MKI) é implantada e configurada usando uma infraestrutura da autoridade de certificação (CA) de terceiros ou da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="10bf3-120">Managed key infrastructure (MKI) is deployed and configured, using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>

  - <span data-ttu-id="10bf3-121">Cada computador no qual o Servidor de Mediação será instalado deve ser:</span><span class="sxs-lookup"><span data-stu-id="10bf3-121">Each computer on which you install Mediation Server must be:</span></span>
    
      - <span data-ttu-id="10bf3-122">Um servidor membro de um domínio e preparado para os serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="10bf3-122">A member server of a domain, and prepared for Active Directory Domain Services.</span></span> <span data-ttu-id="10bf3-123">Para obter os procedimentos de preparação dos serviços de domínio do Active Directory, consulte [preparação dos serviços de domínio do Active Directory para o Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="10bf3-123">For Active Directory Domain Services preparation procedures, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="10bf3-124">Executando um dos seguintes sistemas operacionais:</span><span class="sxs-lookup"><span data-stu-id="10bf3-124">Running one of the following operating systems:</span></span>
        
          - <span></span>  
            <span data-ttu-id="10bf3-125">A edição de 64 bits do sistema operacional Windows Server 2008 Standard</span><span class="sxs-lookup"><span data-stu-id="10bf3-125">The 64-bit edition of the Windows Server 2008 Standard operating system</span></span>
        
          - <span></span>  
            <span data-ttu-id="10bf3-126">A edição de 64 bits do sistema operacional Windows Server 2008 Enterprise</span><span class="sxs-lookup"><span data-stu-id="10bf3-126">The 64-bit edition of the Windows Server 2008 Enterprise operating system</span></span>

  - <span data-ttu-id="10bf3-p105">Se a conexão ao PBX ou PSTN ocorrer por meio de uma conexão de TDM (multiplexação de divisão de tempo), um ou mais gateways PSTN estarão disponíveis para implantação. Se a conexão ocorrer por meio de um tronco SIP, não é necessário ter um gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="10bf3-p105">If the connection to the public switched telephone network (PSTN) or private branch exchange (PBX) is by means of a Time Division Multiplexing (TDM) connection, one or more PSTN gateways are available for deployment. (If the connection is by means of a SIP trunk, a PSTN gateway is not required.)</span></span>

</div>

<div>

## <a name="power-network-or-telephone-service-outages"></a><span data-ttu-id="10bf3-129">Interrupções de energia, da rede ou dos serviços telefônicos</span><span class="sxs-lookup"><span data-stu-id="10bf3-129">Power, Network, or Telephone Service Outages</span></span>

<span data-ttu-id="10bf3-130">Se houver uma interrupção, interrupção ou outra degradação dos serviços de energia, rede ou telefone no seu local, a voz, as mensagens instantâneas, a presença e outros recursos do Lync Server e qualquer dispositivo conectado ao Lync Server poderão não funcionar corretamente.</span><span class="sxs-lookup"><span data-stu-id="10bf3-130">If there is an outage, disruption, or other degradation of the power, network, or telephone services at your location, the voice, instant messaging, presence, and other features of Lync Server and any device connected to Lync Server may not work properly.</span></span>

</div>

<div>

## <a name="enterprise-voice-depends-on-server-availability-and-voice-client-and-hardware-operability"></a><span data-ttu-id="10bf3-131">O Enterprise Voice depende da disponibilidade do servidor e da operabilidade do hardware e do cliente VoIP</span><span class="sxs-lookup"><span data-stu-id="10bf3-131">Enterprise Voice Depends on Server Availability and Voice Client and Hardware Operability</span></span>

<span data-ttu-id="10bf3-132">As comunicações de voz com o Lync Server dependem da disponibilidade do software do servidor e do funcionamento correto dos clientes de voz ou dos dispositivos de telefone de hardware que se conectam ao software do servidor.</span><span class="sxs-lookup"><span data-stu-id="10bf3-132">Voice communications with Lync Server depend upon the availability of the server software and the proper functioning of the voice clients or the hardware phone devices connecting to the server software.</span></span>

</div>

<div>

## <a name="alternative-means-of-accessing-emergency-services"></a><span data-ttu-id="10bf3-133">Meios alternativos de acessar serviços de emergência</span><span class="sxs-lookup"><span data-stu-id="10bf3-133">Alternative Means of Accessing Emergency Services</span></span>

<span data-ttu-id="10bf3-134">Para os locais onde você instala um cliente de voz (por exemplo, um computador que executa o Lync Client ou um dispositivo do Lync Phone Edition), recomendamos que você mantenha uma opção de backup para que os usuários liguem para os serviços de emergência (por exemplo, 911 ou 999) em caso de falha de energia , degradação da conectividade de rede, interrupção do serviço de telefone ou outro problema que pode inibir a operação de dispositivos do Lync Server, Lync ou Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="10bf3-134">For those locations where you install a voice client (for example, a PC running Lync client or an Lync Phone Edition device), we recommend that you maintain a backup option for users to call emergency services (for example, 911 or 999) in case of a power failure, network connectivity degradation, telephone service outage, or other issue that may inhibit operation of Lync Server, Lync, or Lync Phone Edition devices.</span></span> <span data-ttu-id="10bf3-135">Tais opções alternativas poderiam incluir um telefone conectado a uma linha de PSTNpadrão ou um telefone celular.</span><span class="sxs-lookup"><span data-stu-id="10bf3-135">Such alternative options could include a telephone connected to a standard public switched telephone network line or a cell phone.</span></span>

</div>

<div>

## <a name="emergency-calls-and-multi-line-telephone-systems"></a><span data-ttu-id="10bf3-136">Chamadas de emergência e sistemas telefônicos de várias linhas</span><span class="sxs-lookup"><span data-stu-id="10bf3-136">Emergency Calls and Multi-Line Telephone Systems</span></span>

<span data-ttu-id="10bf3-137">O uso de um sistema telefônico de várias linhas (MLTS) pode estar sujeito às leis federais dos EUA ou às leis de outros países/regiões que requerem que o sistema MLTS forneça o número de telefone do chamador, a extensão e/ou o local físico para os serviços de emergência aplicáveis quando um chamador chama serviços de emergência (por exemplo, ao discar um número de acesso de emergência, como 901).</span><span class="sxs-lookup"><span data-stu-id="10bf3-137">The use of a multiline telephone system (MLTS) may be subject to U.S state or federal laws or the laws of other countries/regions that require the MLTS to provide a caller’s telephone number, extension, and/or physical location to applicable emergency services when a caller is placed to emergency services (for example, when dialing an emergency access number such as 911 or 999).</span></span> <span data-ttu-id="10bf3-138">Nesta versão, o Lync Server pode ser configurado para fornecer o local físico de um chamador para um provedor de serviços de emergência, conforme descrito em [Planning for Emergency Services (E9-1-1) no Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span><span class="sxs-lookup"><span data-stu-id="10bf3-138">In this release, Lync Server can be configured to provide a caller’s physical location to an emergency services provider, as described in [Planning for emergency services (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span></span> <span data-ttu-id="10bf3-139">A conformidade com as leis do MLTS é a única responsabilidade do comprador de dispositivos do Lync Server, Lync Client e Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="10bf3-139">Compliance with MLTS laws is the sole responsibility of the purchaser of Lync Server, Lync client, and Lync Phone Edition devices.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

