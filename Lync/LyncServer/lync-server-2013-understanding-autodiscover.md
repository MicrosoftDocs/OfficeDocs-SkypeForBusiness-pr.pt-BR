---
title: 'Lync Server 2013: compreendendo a descoberta automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding Autodiscover
ms:assetid: d70a15b7-750b-4e0f-9a7f-0254d6d486c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945654(v=OCS.15)
ms:contentKeyID: 51541522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b63e29608dd8c3a0187b17c03e6ba9373b31f08f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527758"
---
# <a name="understanding-autodiscover-in-lync-server-2013"></a><span data-ttu-id="cc1b1-102">Compreendendo a descoberta automática no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc1b1-102">Understanding Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc1b1-103">_**Última modificação do tópico:** 2013-06-03_</span><span class="sxs-lookup"><span data-stu-id="cc1b1-103">_**Topic Last Modified:** 2013-06-03_</span></span>

<span data-ttu-id="cc1b1-104">O serviço de descoberta automática do Lync Server 2013 é um recurso introduzido originalmente no Microsoft Lync Server 2010 como parte da atualização cumulativa do Lync Server 2010: novembro de 2011.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-104">The Lync Server 2013 Autodiscover Service is a feature that was originally introduced in Microsoft Lync Server 2010 as part of the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="cc1b1-105">Além de correções, esta atualização cumulativa fornece suporte para clientes Lync Mobile e Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-105">In addition to fixes, this cumulative update delivered support for Lync Mobile and Lync 2013 clients.</span></span>

<span data-ttu-id="cc1b1-106">No Lync Server 2013, o serviço de descoberta automática é parte integrante da operação de clientes móveis externos e internos, e a descoberta automática também é estendida para novos clientes, como o aplicativo Lync Windows Store recentemente introduzido para o Windows 8.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-106">In Lync Server 2013, the Autodiscover Service is an integral part of the operation of external and internal mobile clients, and Autodiscover is also extended to new clients, such as the recently introduced Lync Windows Store app for Windows 8.</span></span> <span data-ttu-id="cc1b1-107">A descoberta automática também é usada pelos clientes de desktop do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-107">Autodiscover is also used by the Lync 2013 desktop clients.</span></span> <span data-ttu-id="cc1b1-108">A descoberta automática é reconhecida no Lync Server pelos registros do sistema de nomes de domínio (DNS) necessários \*\*lyncdiscover. \<domain\> \*\*</span><span class="sxs-lookup"><span data-stu-id="cc1b1-108">Autodiscover is recognized in Lync Server by the required domain name system (DNS) records **lyncdiscover.\<domain\>**</span></span> <span data-ttu-id="cc1b1-109">e \*\*lyncdiscoverinternal. \<domain\> \*\*.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-109">and **lyncdiscoverinternal.\<domain\>**.</span></span> <span data-ttu-id="cc1b1-110">Além disso, as versões mais recentes do cliente de área de trabalho Lync 2010 e Lync 2013 preferem a descoberta automática sobre os registros SRV do DNS (sistema de nomes de domínio), usando registros SRV DNS somente se o lyncdiscover.\<domain\></span><span class="sxs-lookup"><span data-stu-id="cc1b1-110">Additionally, newer versions of the Lync 2010 and Lync 2013 desktop client prefer Autodiscover over the domain name system (DNS) SRV records, using DNS SRV records only if lyncdiscover.\<domain\></span></span> <span data-ttu-id="cc1b1-111">ou lyncdiscoverinternal.\<domain\></span><span class="sxs-lookup"><span data-stu-id="cc1b1-111">or lyncdiscoverinternal.\<domain\></span></span> <span data-ttu-id="cc1b1-112">Não responde ou não resolve.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-112">does not respond or does not resolve.</span></span> <span data-ttu-id="cc1b1-113">O aplicativo Lync da Windows Store para Windows 8 e Lync Mobile usa descoberta automática exclusivamente e não fará referência aos Registros SRV DNS tradicionais.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-113">The Lync Windows Store app for Windows 8 and Lync Mobile uses Autodiscover exclusively and will not refer to the traditional DNS SRV records.</span></span>

<span data-ttu-id="cc1b1-114">No Lync Server 2013, a descoberta automática é expandida para comunicar ao cliente quais elementos, recursos e métodos de comunicação estão disponíveis para o cliente.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-114">In Lync Server 2013, Autodiscover is expanded to communicate to the client which elements, features, and communication methods are available to the client.</span></span> <span data-ttu-id="cc1b1-115">As informações são comunicadas por meio de uma solicitação que é enviada do cliente e os serviços Web do Lync Server respondem com uma resposta definida claramente que nomeia o que está disponível para o cliente e como entrar em contato com esses recursos no formato do documento de resposta de descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-115">The information is communicated through a request that is sent from the client, and the Lync Server web services responds with a clearly defined response that names what is available to the client, and how to contact those features in the format of the Autodiscover Response document.</span></span>

<span data-ttu-id="cc1b1-116">A melhor maneira de entender o documento de resposta de descoberta automática, incluindo como os serviços Web comunicam os recursos para os clientes por meio deste documento, é Dissect e definir cada linha em uma resposta típica do documento de resposta de descoberta automática do Lync Web Service.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-116">The best way to understand the Autodiscover response document, including how the web services communicate features to clients through this document, is to dissect and define each line in a typical response from the Lync web service Autodiscover response document.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="cc1b1-117">Nos detalhes a seguir, o usuário já foi autenticado no servidor primário respondendo a uma solicitação de autenticação.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-117">In the details that follow, the user has already authenticated to the home server by responding to an authentication request.</span></span>



</div>

<div class="">


> [!NOTE]  
> <span data-ttu-id="cc1b1-118">O serviço Web de descoberta automática do Lync é definido nos <STRONG>protocolos do Microsoft Office</STRONG> na seção <STRONG>especificações abertas</STRONG> da biblioteca do <STRONG>Microsoft Developer Network</STRONG> (MSDN).</span><span class="sxs-lookup"><span data-stu-id="cc1b1-118">The Lync Autodiscover Web Service is defined in the <STRONG>Microsoft Office Protocols</STRONG> in the <STRONG>Open Specifications</STRONG> section of the <STRONG>Microsoft Developer Network</STRONG> (MSDN) library.</span></span> <span data-ttu-id="cc1b1-119">Para obter detalhes, consulte o documento de especificação completa, "protocolo de serviço Web de descoberta automática do Lync" em: <A href="https://go.microsoft.com/fwlink/?linkid=273839">https://go.microsoft.com/fwlink/?LinkId=273839</A> .</span><span class="sxs-lookup"><span data-stu-id="cc1b1-119">For details, see the full specification document, "Lync Autodiscover Web Service Protocol," at: <A href="https://go.microsoft.com/fwlink/?linkid=273839">https://go.microsoft.com/fwlink/?LinkId=273839</A>.</span></span> <span data-ttu-id="cc1b1-120">Para obter detalhes sobre a autenticação, consulte "OC Authentication Web Service Protocol" em <A href="https://go.microsoft.com/fwlink/?linkid=279015">https://go.microsoft.com/fwlink/?LinkId=279015</A> .</span><span class="sxs-lookup"><span data-stu-id="cc1b1-120">For details about authentication, see "OC Authentication Web Service Protocol" at <A href="https://go.microsoft.com/fwlink/?linkid=279015">https://go.microsoft.com/fwlink/?LinkId=279015</A>.</span></span>



</div>

<div>

## <a name="the-lync-server-web-service-autodiscover-response"></a><span data-ttu-id="cc1b1-121">A resposta de descoberta automática do serviço Web do Lync Server</span><span class="sxs-lookup"><span data-stu-id="cc1b1-121">The Lync Server Web Service Autodiscover Response</span></span>

<span data-ttu-id="cc1b1-122">A resposta retornada quando a solicitação de descoberta automática é enviada é a mesma para um cliente interno ou externo.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-122">The response returned when the Autodiscover request is sent is the same for an internal or an external client.</span></span> <span data-ttu-id="cc1b1-123">Alguns parâmetros que reconhecem a localização podem ser alterados.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-123">Some parameters that are location–aware may change.</span></span> <span data-ttu-id="cc1b1-124">Se uma solicitação de cliente for recebida, mas o pool real for diferente daquele que foi contatado, o pool inicial do usuário será definido para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-124">If a client request is received, but the actual pool is other than the one that has been contacted, the user’s home pool will be set for that user.</span></span> <span data-ttu-id="cc1b1-125">Um colega cuja conta de usuário está em um pool diferente, mas efetuar logon no mesmo escritório, teria uma resposta um pouco diferente.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-125">A colleague whose user account is on a different pool, but logging in from the same office, would get a slightly different response.</span></span> <span data-ttu-id="cc1b1-126">A resposta indica o servidor front-end ou o pool de front-ends correto para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-126">The response indicates the correct Front End Server or Front End pool for that user.</span></span>

<span data-ttu-id="cc1b1-127">Um exemplo de um documento de resposta de descoberta automática:</span><span class="sxs-lookup"><span data-stu-id="cc1b1-127">An example of an Autodiscover Response document:</span></span>

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">
       <User>
          <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>
          <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>
          <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>
          <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>
          <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>
          <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>
          <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>
          <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>
          <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>
          <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>
          <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>
          <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>
          <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>
       </User>
    </AutodiscoverResponse>

<div>

## <a name="autodiscover-response-document-details"></a><span data-ttu-id="cc1b1-128">Detalhes do documento de resposta de descoberta automática</span><span class="sxs-lookup"><span data-stu-id="cc1b1-128">Autodiscover Response Document Details</span></span>

<span data-ttu-id="cc1b1-129">O documento de resposta de descoberta automática pode estar em um dos dois formatos.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-129">The Autodiscover Response document can be in one of two formats.</span></span> <span data-ttu-id="cc1b1-130">O formato padrão é uma notação de objeto JavaScript (JSON).</span><span class="sxs-lookup"><span data-stu-id="cc1b1-130">The default format is a JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="cc1b1-131">O outro formato é o documento XML.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-131">The other format is extensible markup language (XML) document.</span></span> <span data-ttu-id="cc1b1-132">O XML é usado para este exemplo.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-132">The XML is used for this example.</span></span> <span data-ttu-id="cc1b1-133">A solicitação e a resposta são previsíveis porque o documento tem um esquema definido que determina o formato.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-133">The request and response are predictable because the document has a defined schema that determines the format.</span></span> <span data-ttu-id="cc1b1-134">A linha no documento que descreve o esquema usado é a primeira linha na solicitação ou resposta:</span><span class="sxs-lookup"><span data-stu-id="cc1b1-134">The line in the document that describes the schema used is the first line in the request or response:</span></span>

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

<span data-ttu-id="cc1b1-135">A definição de **AccessLocation = "external"** indica que a solicitação foi feita de um usuário externo.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-135">The definition of **AccessLocation=”External”** indicates that the request was made from an external user.</span></span>

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

&nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

<span data-ttu-id="cc1b1-136">SipServerInternalAccess e SipServerExternalAccess não são usados no momento.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-136">SipServerInternalAccess and SipServerExternalAccess are currently not used.</span></span> <span data-ttu-id="cc1b1-137">Essas entradas são reservadas para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-137">These entries are reserved for future use.</span></span>

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

&nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

<span data-ttu-id="cc1b1-138">SipClientInternalAccess e SipClientExternalAccess descrevem o nome de domínio totalmente qualificado e a porta que um cliente interno ou externo usará para acessar o servidor SIP definido.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-138">SipClientInternalAccess and SipClientExternalAccess describe the fully qualified domain name and port that an internal or external client will use to access the defined SIP Server.</span></span> <span data-ttu-id="cc1b1-139">O cliente do Lync desktop e o aplicativo Lync da Windows Store usam essas entradas, com base em sua localização (interna ou externa) para localizar o diretor ou servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-139">The Lync desktop client and the Lync Windows Store app use these entries, based on their location (internal or external) to find the Director or Front End Server.</span></span>

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

&nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

<span data-ttu-id="cc1b1-140">As `Autodiscover` referências contêm os pontos de entrada de serviço para o serviço de descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-140">The `Autodiscover` references contain the service entry points for the Autodiscover service.</span></span> <span data-ttu-id="cc1b1-141">O atributo token contém o nome do serviço e o href é uma URL que define o cliente onde o serviço pode ser encontrado.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-141">The token attribute contains the name of the service, and the href is a URL that defines for the client where the service can be found.</span></span> <span data-ttu-id="cc1b1-142">Os clientes em uma rede externa usam o `External/Autodiscover` .</span><span class="sxs-lookup"><span data-stu-id="cc1b1-142">Clients on an external network use the `External/Autodiscover`.</span></span> <span data-ttu-id="cc1b1-143">O serviço de descoberta automática é instalado como parte do processo de implantação.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-143">The Autodiscover service is installed as part of the deployment process.</span></span> <span data-ttu-id="cc1b1-144">`Internal/Autodiscover` Não é usado no momento e está reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-144">`Internal/Autodiscover` is not currently used, and is reserved for future use.</span></span>

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

&nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

<span data-ttu-id="cc1b1-145">As `AuthBroker` referências contêm os pontos de entrada de serviço para o serviço de agente de autenticação interno e externo, neste caso, SIP. svc.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-145">The `AuthBroker` references contain the service entry points for the internal and the external authentication broker service, in this case, sip.svc.</span></span> <span data-ttu-id="cc1b1-146">O atributo token contém o nome do serviço e o href é uma URL que define o cliente onde o serviço pode ser encontrado.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-146">The token attribute contains the name of the service, and the href is a URL that defines for the client where the service can be found.</span></span> <span data-ttu-id="cc1b1-147">Clientes na rede interna com o uso `Internal/AuthBroker` .</span><span class="sxs-lookup"><span data-stu-id="cc1b1-147">Clients on the internal network with use `Internal/AuthBroker`.</span></span> <span data-ttu-id="cc1b1-148">Os clientes em uma rede externa usam o `External/AuthBroker` .</span><span class="sxs-lookup"><span data-stu-id="cc1b1-148">Clients on an external network use the `External/AuthBroker`.</span></span> <span data-ttu-id="cc1b1-149">O serviço AuthBroker é instalado como parte do processo de implantação de seus serviços Web de implantação do Lync Server 2013 internos.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-149">The AuthBroker service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

&nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

<span data-ttu-id="cc1b1-150">O `WebScheduler` token faz referência às URLs para o acesso do cliente ao agendamento baseado na Web para conferências do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-150">The `WebScheduler` token references the URLs for client access to the web-based scheduling for Lync Server conferences.</span></span> <span data-ttu-id="cc1b1-151">Atualmente, apenas o `External/WebScheduler` é usado.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-151">Currently, only the `External/WebScheduler` is used.</span></span> <span data-ttu-id="cc1b1-152">O webscheduler é instalado como parte do processo de implantação de seus serviços Web de implantação do Lync Server 2013 internos.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-152">The WebScheduler is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

&nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

<span data-ttu-id="cc1b1-153">`Internal/Mcx` e `External/Mcx` são os locais dos serviços de mobilidade, introduzidos na atualização cumulativa do Lync Server 2010:2011 de novembro.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-153">`Internal/Mcx` and `External/Mcx` are the locations of the Mobility services, introduced in Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="cc1b1-154">Essas referências continuarão a ser usadas pelo Lync 2010 Mobile em todos os dispositivos com suporte.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-154">These references will continue to be used by Lync 2010 Mobile on all supported devices.</span></span> <span data-ttu-id="cc1b1-155">O serviço MCX é instalado como parte do processo de implantação de seus serviços Web de implantação do Lync Server 2013 internos.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-155">The Mcx service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

&nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

&nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

<span data-ttu-id="cc1b1-156">**Interno/Ucwa**, **external/Ucwa** e **Ucwa** fornecem um meio para os clientes acessarem a interface de programação de aplicativos Web de comunicação unificada (API Ucwa ou simplesmente Ucwa).</span><span class="sxs-lookup"><span data-stu-id="cc1b1-156">**Internal/Ucwa**, **External/Ucwa** and **Ucwa** provide a means for clients to access the Unified Communications Web Application Programming Interface (UCWA API, or simply UCWA).</span></span> <span data-ttu-id="cc1b1-157">`Internal/Ucwa` e os `External/Ucwa` diretórios virtuais são pontos de acesso reservados para aprimoramento de recursos futuros e não são usados.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-157">`Internal/Ucwa` and `External/Ucwa` virtual directories are access points reserved for future feature enhancement, and are not used.</span></span> <span data-ttu-id="cc1b1-158">O `Ucwa` diretório virtual é usado para o Microsoft Lync Mobile (introduzido com o Lync Server 2013) em todos os dispositivos com suporte.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-158">The `Ucwa` virtual directory is used for Microsoft Lync Mobile (introduced with Lync Server 2013) on all supported devices.</span></span> <span data-ttu-id="cc1b1-159">O serviço UCWA é instalado como parte do processo de implantação de seus serviços Web de implantação do Lync Server 2013 internos.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-159">The UCWA service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

<span data-ttu-id="cc1b1-160">`Internal/XFrame`, **External/Xframe** e **Xframe** fornecem acesso para aplicativos de servidor baseados em UCWA.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-160">`Internal/XFrame`, **External/XFrame** and **XFrame** provide access for UCWA-based server applications.</span></span> <span data-ttu-id="cc1b1-161">O XFrame é instalado como parte do processo de implantação de seus serviços Web de implantação do Lync Server 2013 internos.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-161">XFrame is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

<span data-ttu-id="cc1b1-162">O `Self` token se refere a informações específicas para o cliente (tipo de resposta do usuário) que está fazendo a solicitação.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-162">The `Self` token refers to information specific to the client (user response type) that is making the request.</span></span> <span data-ttu-id="cc1b1-163">O cliente que fez essa solicitação era externo e essa referência de descoberta automática é a parte do usuário do serviço de descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-163">The client that made this request was external, and this Autodiscover reference is to the user portion of the Autodiscover service.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cc1b1-164">Confira também</span><span class="sxs-lookup"><span data-stu-id="cc1b1-164">See Also</span></span>


[<span data-ttu-id="cc1b1-165">Requisitos do sistema para componentes de acesso de usuário externo para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc1b1-165">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[<span data-ttu-id="cc1b1-166">Planejamento para descoberta automática no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc1b1-166">Planning for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

