---
title: 'Lync Server 2013: componentes de VoIP do servidor front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End Server VoIP components
ms:assetid: 310e81a7-da45-47d4-95d0-92837e386502
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425812(v=OCS.15)
ms:contentKeyID: 48183765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0be06c357fd3b02b2a44f4ba8f4aebfaab99f609
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147474"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="front-end-server-voip-components-for-lync-server-2013"></a><span data-ttu-id="0be21-102">Componentes VoIP do servidor front-end para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0be21-102">Front End Server VoIP components for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0be21-103">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="0be21-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="0be21-104">Os componentes VoIP localizados em servidores front-end são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="0be21-104">The VoIP components located on Front End Servers are as follows:</span></span>

  - <span data-ttu-id="0be21-105">Serviço de Conversão</span><span class="sxs-lookup"><span data-stu-id="0be21-105">Translation Service</span></span>

  - <span data-ttu-id="0be21-106">Componente de Roteamento de Entrada</span><span class="sxs-lookup"><span data-stu-id="0be21-106">Inbound Routing component</span></span>

  - <span data-ttu-id="0be21-107">Componente de Roteamento de Saída</span><span class="sxs-lookup"><span data-stu-id="0be21-107">Outbound Routing component</span></span>

  - <span data-ttu-id="0be21-108">Componente de Roteamento da UM do Exchange</span><span class="sxs-lookup"><span data-stu-id="0be21-108">Exchange UM Routing component</span></span>

  - <span data-ttu-id="0be21-109">Componente de roteamento entre clusters</span><span class="sxs-lookup"><span data-stu-id="0be21-109">Intercluster Routing component</span></span>

  - [<span data-ttu-id="0be21-110">Componente do servidor de mediação no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0be21-110">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)

<div>

## <a name="translation-service"></a><span data-ttu-id="0be21-111">Serviço de Conversão</span><span class="sxs-lookup"><span data-stu-id="0be21-111">Translation Service</span></span>

<span data-ttu-id="0be21-p101">O Serviço de Conversão é o componente de servidor responsável pela conversão de um número discado no formato E.164 ou em outro formato, de acordo com as regras de normalização definidas pelo administrador. Esse serviço pode fazer a conversão para formatos que não sejam o E.164, caso a sua organização use um sistema de numeração particular ou um gateway ou PBX que não dê suporte a E.164.</span><span class="sxs-lookup"><span data-stu-id="0be21-p101">The Translation Service is the server component that is responsible for translating a dialed number into the E.164 format or another format, according to the normalization rules that are defined by the administrator. The Translation Service can translate to formats other than E.164 if your organization uses a private numbering system or uses a gateway or PBX that does not support E.164.</span></span>

</div>

<div>

## <a name="inbound-routing-component"></a><span data-ttu-id="0be21-114">Componente de Roteamento de Entrada</span><span class="sxs-lookup"><span data-stu-id="0be21-114">Inbound Routing Component</span></span>

<span data-ttu-id="0be21-115">O componente de roteamento de entrada trata as chamadas de entrada em grande parte de acordo com as preferências especificadas pelos usuários em seus clientes corporativos de voz.</span><span class="sxs-lookup"><span data-stu-id="0be21-115">The Inbound Routing component handles incoming calls largely according to preferences that are specified by users on their Enterprise Voice clients.</span></span> <span data-ttu-id="0be21-116">Também facilita a delegação de chamada e chamada simultânea, se configurada pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="0be21-116">It also facilitates delegate ringing and simultaneous ringing, if configured by the user.</span></span> <span data-ttu-id="0be21-117">Por exemplo, os usuários especificam se as chamadas não atendidas são encaminhadas ou simplesmente conectadas para notificação.</span><span class="sxs-lookup"><span data-stu-id="0be21-117">For example, users specify whether unanswered calls are forwarded or simply logged for notification.</span></span> <span data-ttu-id="0be21-118">Se o encaminhamento de chamadas estiver habilitado, os usuários poderão especificar se as chamadas não atendidas devem ser encaminhadas para outro número ou para um servidor de UM do Exchange que tenha sido configurado para fornecer atendimento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="0be21-118">If call forwarding is enabled, users can specify whether unanswered calls should be forwarded to another number or to a Exchange UM server that has been configured to provide call answering.</span></span> <span data-ttu-id="0be21-119">O componente de roteamento de entrada é instalado por padrão em todos os servidores Standard Edition e front-end.</span><span class="sxs-lookup"><span data-stu-id="0be21-119">The Inbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

</div>

<div>

## <a name="outbound-routing-component"></a><span data-ttu-id="0be21-120">Componente de Roteamento de Saída</span><span class="sxs-lookup"><span data-stu-id="0be21-120">Outbound Routing Component</span></span>

<span data-ttu-id="0be21-121">O componente de Roteamento de Saída direciona as chamadas para destinos do PBX ou PSTN.</span><span class="sxs-lookup"><span data-stu-id="0be21-121">The Outbound Routing component routes calls to PBX or PSTN destinations.</span></span> <span data-ttu-id="0be21-122">Aplica regras de autorização de chamada, conforme definido pela política de voz do usuário, para ligadores e determina o melhor gateway PSTN para roteamento de cada chamada.</span><span class="sxs-lookup"><span data-stu-id="0be21-122">It applies call authorization rules, as defined by the user’s voice policy, to callers and determines the optimal PSTN gateway for routing each call.</span></span> <span data-ttu-id="0be21-123">O componente de roteamento de saída é instalado por padrão em todos os servidores Standard Edition e front-end.</span><span class="sxs-lookup"><span data-stu-id="0be21-123">The Outbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

<span data-ttu-id="0be21-124">A lógica de roteamento usada pelo Componente de Roteamento de Saída é, em grande parte, configurada pelos administradores de rede e de telefonia, de acordo com os requisitos das organizações.</span><span class="sxs-lookup"><span data-stu-id="0be21-124">The routing logic that is used by the Outbound Routing component is in large measure configured by network or telephony administrators according to the requirements of their organizations.</span></span>

</div>

<div>

## <a name="exchange-um-routing-component"></a><span data-ttu-id="0be21-125">Componente de Roteamento da UM do Exchange</span><span class="sxs-lookup"><span data-stu-id="0be21-125">Exchange UM Routing Component</span></span>

<span data-ttu-id="0be21-126">O componente de roteamento de UM do Exchange lida com o roteamento entre o Lync Server e servidores executando a Unificação de mensagens (UM) do Exchange para integrar o Lync Server com recursos de Unificação de mensagens</span><span class="sxs-lookup"><span data-stu-id="0be21-126">The Exchange UM routing component handles routing between Lync Server and servers running Exchange Unified Messaging (UM), to integrate Lync Server with Unified Messaging features.</span></span>

<span data-ttu-id="0be21-127">O componente de roteamento de UM do Exchange também gerencia o reencaminhamento de caixa postal sobre a PSTN se os servidores de UM do Exchange não estiverem disponíveis.</span><span class="sxs-lookup"><span data-stu-id="0be21-127">The Exchange UM routing component also handles rerouting of voice mail over the PSTN if Exchange UM servers are unavailable.</span></span> <span data-ttu-id="0be21-128">Se você tiver usuários do Enterprise Voice em sites de filial que não tenham um link de WAN resistente a um site central, o aparelho de filial persistente implantado no site de filial fornecerá persistência de caixa postal para os usuários da filial durante uma interrupção da WAN.</span><span class="sxs-lookup"><span data-stu-id="0be21-128">If you have Enterprise Voice users at branch sites that do not have a resilient WAN link to a central site, the Survivable Branch Appliance that you deploy at the branch site provides voice mail survivability for branch users during a WAN outage.</span></span> <span data-ttu-id="0be21-129">Quando o link WAN estiver indisponível, o aparelho de filial persistente fará o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0be21-129">When the WAN link is unavailable, the Survivable Branch Appliance does the following:</span></span>

  - <span data-ttu-id="0be21-130">faz um novo roteamento de chamadas não respondidas sobre o PSTN para o servidor de Unificação de Mensagens do Exchange no site central</span><span class="sxs-lookup"><span data-stu-id="0be21-130">reroutes unanswered calls over the PSTN to the Exchange Unified Messaging server in the central site</span></span>

  - <span data-ttu-id="0be21-131">fornece ao usuário a capacidade de recuperar mensagens de caixa postal sobre o PSTN</span><span class="sxs-lookup"><span data-stu-id="0be21-131">provides the ability for a user to retrieve voice mail messages over the PSTN</span></span>

  - <span data-ttu-id="0be21-132">coloca em fila notificações de chamada perdida e as carrega no servidor de UM do Exchange quando o link de WAN for restaurado.</span><span class="sxs-lookup"><span data-stu-id="0be21-132">queues missed call notifications, and then uploads them to the Exchange UM server when the WAN link is restored.</span></span>

<span data-ttu-id="0be21-133">Para habilitar o reencaminhamento de caixa postal, recomendamos que seu administrador do Exchange configure o atendedor automático da UM do Exchange (AA) para aceitar apenas mensagens.</span><span class="sxs-lookup"><span data-stu-id="0be21-133">To enable voice mail rerouting, we recommend that your Exchange administrator configure Exchange UM Auto Attendant (AA) to accept messages only.</span></span>

<span data-ttu-id="0be21-134">Para obter detalhes sobre esses recursos, consulte [Planning for Exchange Unified Messaging Integration in Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) e [Planning for Enterprise Voice resiliência no Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md), respectivamente.</span><span class="sxs-lookup"><span data-stu-id="0be21-134">For details about these features, see [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Planning for Enterprise Voice resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md), respectively.</span></span>

</div>

<div>

## <a name="intercluster-routing-component"></a><span data-ttu-id="0be21-135">Componente de roteamento entre clusters</span><span class="sxs-lookup"><span data-stu-id="0be21-135">Intercluster Routing Component</span></span>

<span data-ttu-id="0be21-p105">O componente de roteamento entre clusters é responsável por rotear chamadas ao pool de registradores principal do chamador. Se essa opção não estiver disponível, o componente roteará a chamada para o pool de registradores de backup de quem recebe a chamada. Se os pools de registradores principal e de backup de quem recebe a chamada não puderem ser acessados pela rede IP, o componente de roteamento entre clusters roteará novamente a chamada sobre o PSTN para o número de telefone do usuário.</span><span class="sxs-lookup"><span data-stu-id="0be21-p105">The Intercluster routing component is responsible for routing calls to the callee’s primary Registrar pool. If that is unavailable, the component routes the call to the callee’s backup Registrar pool. If the callee’s primary and backup Registrar pools are unreachable over the IP network, the Intercluster routing component reroutes the call over the PSTN to the user’s telephone number.</span></span>

</div>

<div>

## <a name="other-front-end-server-components-required-for-voip"></a><span data-ttu-id="0be21-139">Outros componentes de Servidor Front-End necessários ao VoIP</span><span class="sxs-lookup"><span data-stu-id="0be21-139">Other Front End Server Components Required for VoIP</span></span>

<span data-ttu-id="0be21-140">Outros componentes residentes no servidor de front-end ou diretor que oferecem suporte essencial para VoIP, mas não são componentes VoIP, incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0be21-140">Other components residing on the Front End Server or Director that provide essential support for VoIP, but are not themselves VoIP components, include the following:</span></span>

  - <span data-ttu-id="0be21-141">**Serviços do Usuário.**</span><span class="sxs-lookup"><span data-stu-id="0be21-141">**User Services.**</span></span> <span data-ttu-id="0be21-142">Realiza a pesquisa de número inverso no telefone de destino para cada chamada de entrada e corresponde esse número ao URI SIP do usuário de destino.</span><span class="sxs-lookup"><span data-stu-id="0be21-142">Perform reverse number lookup on the destination phone number of each incoming call and match that number to the SIP URI of the destination user.</span></span> <span data-ttu-id="0be21-143">Usando esta informação o componente de Roteamento de Entrada distribui a chamada para os pontos de extremidade SIP registrados do usuário.</span><span class="sxs-lookup"><span data-stu-id="0be21-143">Using this information, the Inbound Routing component distributes the call to that user’s registered SIP endpoints.</span></span> <span data-ttu-id="0be21-144">Serviços de usuário é um componente principal em todos os servidores front-end e diretores.</span><span class="sxs-lookup"><span data-stu-id="0be21-144">User Services is a core component on all Front End Servers and Directors.</span></span>

  - <span data-ttu-id="0be21-145">**Replicador do Usuário.**</span><span class="sxs-lookup"><span data-stu-id="0be21-145">**User Replicator.**</span></span> <span data-ttu-id="0be21-146">Extrai números de telefone do usuário dos serviços de domínio do Active Directory e os grava em tabelas no banco de dados RTC, onde eles estão disponíveis para os serviços de usuário e o servidor de catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="0be21-146">Extracts user phone numbers from Active Directory Domain Services and writes them to tables in the RTC database, where they are available to User Services and Address Book Server.</span></span> <span data-ttu-id="0be21-147">O replicador de usuários é um componente principal em todos os servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="0be21-147">User Replicator is a core component on all Front End Servers.</span></span>

  - <span data-ttu-id="0be21-148">**Servidor do Catálogo de Endereço.**</span><span class="sxs-lookup"><span data-stu-id="0be21-148">**Address Book Server.**</span></span> <span data-ttu-id="0be21-149">Fornece informações de lista de endereços global dos serviços de domínio do Active Directory para os clientes do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0be21-149">Provides global address list information from Active Directory Domain Services to Lync Server clients.</span></span> <span data-ttu-id="0be21-150">Ele também recupera as informações de contato e usuário do banco de dados RTC, grava as informações nos arquivos do catálogo de endereços e, em seguida, armazena os arquivos em uma pasta compartilhada onde eles são baixados pelos clientes do Lync.</span><span class="sxs-lookup"><span data-stu-id="0be21-150">It also retrieves user and contact information from the RTC database, writes the information to the Address Book files, and then stores the files on a shared folder where they are downloaded by Lync clients.</span></span> <span data-ttu-id="0be21-151">O servidor do catálogo de endereços grava as informações no banco de dados do RTCAb, que é usado pelo serviço de consulta à Web do catálogo de endereços para responder às consultas de pesquisa do usuário do Microsoft Lync 2010 Mobile.</span><span class="sxs-lookup"><span data-stu-id="0be21-151">The Address Book Server writes the information to the RTCAb database, which is used by the Address Book Web Query service to respond to user search queries from Microsoft Lync 2010 Mobile.</span></span> <span data-ttu-id="0be21-152">Opcionalmente normaliza os números de telefone do usuário da empresa que são gravados no banco de dados RTC para fins de provisionamento de contatos do usuário no Lync.</span><span class="sxs-lookup"><span data-stu-id="0be21-152">It optionally normalizes enterprise user phone numbers that are written to the RTC database for the purpose of provisioning user contacts in Lync.</span></span> <span data-ttu-id="0be21-153">O serviço de catálogo de endereços é instalado por padrão em todos os servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="0be21-153">The Address Book service is installed by default on all Front End Servers.</span></span> <span data-ttu-id="0be21-154">O serviço de consulta da Web do catálogo de endereços é instalado por padrão com os serviços Web em cada servidor de front-end.</span><span class="sxs-lookup"><span data-stu-id="0be21-154">The Address Book Web Query service is installed by default with the Web services on each Front End Servers.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

