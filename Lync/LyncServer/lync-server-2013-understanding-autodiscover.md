---
title: 'Lync Server 2013: Noções básicas sobre descoberta automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Understanding Autodiscover
ms:assetid: d70a15b7-750b-4e0f-9a7f-0254d6d486c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945654(v=OCS.15)
ms:contentKeyID: 51541522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae8a4965674952cfa5822c24e887ed4d5a02b798
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844568"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-autodiscover-in-lync-server-2013"></a>Compreendendo a descoberta automática no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-06-03_

O serviço de descoberta automática do Lync Server 2013 é um recurso que foi originalmente introduzido no Microsoft Lync Server 2010 como parte da atualização cumulativa do Lync Server 2010: novembro de 2011. Além de correções, esta atualização cumulativa fornece suporte para clientes do Lync Mobile e do Lync 2013.

No Lync Server 2013, o serviço de descoberta automática é uma parte integral da operação de clientes móveis externos e externos, e a descoberta automática também é prorrogada para novos clientes, como o aplicativo Lync da Windows Store recentemente introduzido para Windows 8. A descoberta automática também é usada pelos clientes de desktop do Lync 2013. A descoberta automática é reconhecida no Lync Server pelos registros DNS (sistema de nome de domínio) obrigatórios **lyncdiscover.\< domínio\> ** e **lyncdiscoverinternal.\< domínio\>**. Além disso, as versões mais recentes do cliente de área de trabalho Lync 2010 e Lync 2013 preferem a descoberta automática nos registros SRV do sistema de nomes de domínio (DNS), usando os registros SRV DNS somente se lyncdiscover. \<domínio\> ou lyncdiscoverinternal. \<o\> domínio não responde ou não é resolvido. O aplicativo Lync da Windows Store para Windows 8 e Lync Mobile usa o autodiscover exclusivamente e não se refere aos Registros SRV DNS tradicionais.

No Lync Server 2013, a descoberta automática é expandida para se comunicar com o cliente quais elementos, recursos e métodos de comunicação estão disponíveis para o cliente. As informações são comunicadas por meio de uma solicitação que é enviada do cliente e os serviços Web do Lync Server respondem com uma resposta claramente definida que nomeia o que está disponível para o cliente e como entrar em contato com esses recursos no formato da descoberta automática Documento de resposta.

A melhor maneira de entender o documento de resposta de descoberta automática, incluindo como os serviços Web comunicam os recursos aos clientes por meio deste documento, é Dissect e definir cada linha em uma resposta típica do documento de resposta de descoberta automática do Lync Web Service.

<div class="">


> [!NOTE]  
> Nos detalhes a seguir, o usuário já foi autenticado no servidor primário respondendo a uma solicitação de autenticação.



</div>

<div class="">


> [!NOTE]  
> O serviço Web de descoberta automática do Lync é definido nos <STRONG>protocolos do Microsoft Office</STRONG> na seção <STRONG>especificações abertas</STRONG> da biblioteca do <STRONG>Microsoft Developer Network</STRONG> (MSDN). Para obter detalhes, consulte o documento de especificação completa, "protocolo de serviço Web de descoberta automática do <A href="http://go.microsoft.com/fwlink/?linkid=273839">http://go.microsoft.com/fwlink/?LinkId=273839</A>Lync" em:. Para obter detalhes sobre autenticação, consulte "protocolo de serviço Web de autenticação <A href="http://go.microsoft.com/fwlink/?linkid=279015">http://go.microsoft.com/fwlink/?LinkId=279015</A>OC" em.



</div>

<div>

## <a name="the-lync-server-web-service-autodiscover-response"></a>A resposta de descoberta automática do serviço Web do Lync Server

A resposta retornada quando a solicitação de descoberta automática é enviada é a mesma para um cliente interno ou externo. Alguns parâmetros que reconhecem a localização podem mudar. Se uma solicitação de cliente for recebida, mas o pool real for diferente daquele que foi contatado, o pool inicial do usuário será definido para esse usuário. Um colega cuja conta de usuário está em um pool diferente, mas conectar-se ao mesmo escritório, seria uma resposta um pouco diferente. A resposta indica o servidor front-end correto ou o pool de front-end para esse usuário.

Um exemplo de um documento de resposta de descoberta automática:

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

## <a name="autodiscover-response-document-details"></a>Detalhes do documento de resposta de descoberta automática

O documento resposta de descoberta automática pode estar em um dos dois formatos. O formato padrão é uma JSON (JavaScript Object Notation). O outro formato é o documento Extensible Markup Language (XML). O XML é usado para este exemplo. A solicitação e a resposta são previsíveis porque o documento tem um esquema definido que determina o formato. A linha no documento que descreve o esquema usado é a primeira linha na solicitação ou resposta:

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

A definição de **AccessLocation = "externo"** indica que a solicitação foi feita de um usuário externo.

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

&nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

SipServerInternalAccess e SipServerExternalAccess não são usados no momento. Essas entradas são reservadas para uso futuro.

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

&nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

SipClientInternalAccess e SipClientExternalAccess descrevem o nome de domínio totalmente qualificado e a porta que um cliente interno ou externo usará para acessar o servidor SIP definido. O cliente de área de trabalho do Lync e o aplicativo Lync da Windows Store usam essas entradas com base em sua localização (interna ou externa) para localizar o diretor ou servidor front-end.

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

&nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

As `Autodiscover` referências contêm os pontos de entrada de serviço para o serviço de descoberta automática. O atributo token contém o nome do serviço e o href é uma URL que define para o cliente onde o serviço pode ser encontrado. Os clientes em uma rede externa usam `External/Autodiscover`o. O serviço descoberta automática é instalado como parte do processo de implantação. `Internal/Autodiscover`Não está sendo usado no momento e está reservado para uso futuro.

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

&nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

As `AuthBroker` referências contêm os pontos de entrada de serviço para o serviço de agente de autenticação interno e externo, nesse caso, SIP. svc. O atributo token contém o nome do serviço e o href é uma URL que define para o cliente onde o serviço pode ser encontrado. Clientes na rede interna com uso `Internal/AuthBroker`. Os clientes em uma rede externa usam `External/AuthBroker`o. O serviço AuthBroker é instalado como parte do processo de implantação de seus serviços Web internos de implantação do Lync Server 2013.

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

&nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

O `WebScheduler` token referencia as URLs para o cliente acessar o agendamento baseado na Web para conferências do Lync Server. Atualmente, apenas o `External/WebScheduler` é usado. O webscheduler é instalado como parte do processo de implantação de seus serviços Web internos de implantação do Lync Server 2013.

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

&nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

`Internal/Mcx`e `External/Mcx` são as localizações dos serviços de mobilidade, introduzidas na atualização cumulativa do Lync Server 2010:2011 de novembro. Essas referências continuarão sendo usadas pelo Lync 2010 Mobile em todos os dispositivos compatíveis. O serviço MCX é instalado como parte do processo de implantação de seus serviços Web internos de implantação do Lync Server 2013.

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

&nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

&nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

**Internal/Ucwa**, **external/Ucwa** e **Ucwa** fornecem um meio para os clientes acessarem a interface de programação de aplicativo Web de comunicação unificada (API Ucwa ou simplesmente Ucwa). `Internal/Ucwa`e `External/Ucwa` diretórios virtuais são pontos de acesso reservados para futuros aprimoramentos de recursos e não são usados. O `Ucwa` diretório virtual é usado para o Microsoft Lync Mobile (introduzido com o Lync Server 2013) em todos os dispositivos com suporte. O serviço UCWA é instalado como parte do processo de implantação de seus serviços Web internos de implantação do Lync Server 2013.

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

`Internal/XFrame`, **External/Xframe** e **Xframe** fornecem acesso para aplicativos de servidor baseados em UCWA. O XFrame é instalado como parte do processo de implantação de seus serviços Web internos de implantação do Lync Server 2013.

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

O `Self` token se refere a informações específicas do cliente (tipo de resposta do usuário) que está realizando a solicitação. O cliente que fez essa solicitação era externo e esta referência de descoberta automática é para a parte do usuário do serviço de descoberta automática.

</div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Requisitos do sistema para componentes de acesso de usuário externo para Lync Server 2013](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[Planejando a descoberta automática no Lync Server 2013](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

