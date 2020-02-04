---
title: 'Lync Server 2013: Suporte a tronco SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunking support
ms:assetid: e3042831-e8d8-4ea2-baa2-1a697401ffa0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399005(v=OCS.15)
ms:contentKeyID: 48185714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58108df8795aaae8d431b320125d34d14ee3a275
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunking-support-in-lync-server-2013"></a>Suporte a tronco SIP no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-03_

Se você pretende usar o Enterprise Voice com entroncamento SIP, deve implantar um servidor de mediação e verificar se outros componentes e infraestrutura atendem aos requisitos de suporte apropriados para seu modelo de implantação. Para obter detalhes sobre como determinar se o entroncamento SIP deve ser implementado, consulte [visão geral de entroncamento SIP no Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) na documentação de planejamento.

Você pode usar o programa de interoperabilidade aberto da Microsoft Unified Communication para a infraestrutura de telefonia empresarial para localizar gateways da rede de telefonia pública comutada (PSTN), PBXs IP e serviços de entroncamento SIP, incluindo a telefonia IP qualificada provedores de serviços. Para obter detalhes, consulte o site do programa de interoperabilidade Open [http://go.microsoft.com/fwlink/p/?LinkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309)Microsoft Unified Communication em.

<div>

## <a name="mediation-server-support"></a>Suporte do servidor de mediação

Para implementar o entroncamento SIP, você deve direcionar a conexão por meio de um servidor de mediação, que atua como um proxy para sessões de comunicação entre clientes do Lync Server 2013 e o provedor de serviços. O servidor de mediação decodifica o tráfego de mídia de clientes e servidores e o codifica novamente antes de enviá-lo ao provedor de serviços. A recodificação é necessária porque troncos SIP não são compatíveis com alguns codecs usados, como o RTA (áudio em tempo real) ou a negociação do protocolo ICE (estabelecimento de conectividade interativa) para o Firewall Traversal.

Cada servidor de mediação pode ter dois adaptadores de rede, que fornecem uma interface de rede interna e externa. A interface externa geralmente é chamada de interface do gateway porque, tradicionalmente, foi usada para conexão com um gateway PSTN ou um IP-PBX. Para implementar um tronco SIP, conecte a interface externa a um controlador de borda de sessão (SBC) em um provedor de serviços.

</div>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a>Tronco SIP centralizado versus distribuído

*Centralizado* O entroncamento SIP roteia todo o tráfego do protocolo VoIP, incluindo o tráfego do site da filial, por meio do Data Center. O modelo de implantação centralizado é simples, econômico e geralmente é a abordagem preferida para a implementação de troncos SIP com o Lync Server 2013.

Dependendo dos padrões de uso na sua empresa, talvez você não queira encaminhar todos os usuários por meio do tronco SIP centralizado. Para analisar suas necessidades, responda às seguintes perguntas:

  - Qual é o tamanho de cada site? Quantos usuários?

  - Quais números do Direct Inward Dialing (DID) em cada site obtêm mais chamadas telefônicas?

*Distribuído* O entroncamento SIP é um modelo de implantação no qual você implementa um tronco SIP local em um ou mais sites de filiais. O tráfego de VoIP é então encaminhado do site de filial diretamente para o provedor de serviços, sem passar pelo Data Center.

O tronco SIP distribuído é necessário somente nos seguintes casos:

  - O site da filial requer conectividade de telefone para o telefone cofuncional (por exemplo, se a WAN ficar inoperante). Se a ramificação precisar de redundância e failover, o provedor de serviço será cobrado mais e a configuração será mais demorada. Isso deve ser analisado para cada site de filial. Algumas das suas filiais podem exigir redundância e failover, enquanto outras não podem.

  - O site de filial e o Data Center estão em países/regiões diferentes. Por motivos legais e de compatibilidade, você precisa de pelo menos um tronco SIP por país/região.

Decidir se deve implantar o entroncamento SIP centralizado ou distribuído exige uma análise de custo-benefício. Em alguns casos, pode ser vantajoso optar pelo modo de implantação distribuída, mesmo se não for necessário. Em uma implantação completamente centralizada, todo o tráfego do site da filial é roteado através de links WAN. Em vez de pagar pela largura de banda necessária ao link de WAN, convém usar o tronco SIP distribuído.

<div>


> [!NOTE]  
> Para obter detalhes sobre o porquê e como você pode usar o entroncamento do SIP distribuído, consulte <A href="lync-server-2013-branch-site-sip-trunking.md">entroncamento do site de ramificação SIP no Lync Server 2013</A> na documentação de planejamento.



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a>Tipos de conexão de tronco SIP suportadas

O Lync Server 2013 oferece suporte aos seguintes tipos de conexão para entroncamento SIP:

  - O MPLS é uma rede privada que direciona e transporta dados de um nó de rede para o próximo. A largura de banda em uma rede MPLS é compartilhada com outros assinantes e cada pacote de dados recebe um rótulo para diferenciar os dados de um assinante dos dados de outro assinante. Esse tipo de conexão não requer VPN. Uma possível desvantagem é que o tráfego IP excessivo pode interferir na operação de VoIP, a menos que o tráfego VoIP tenha prioridade.

  - Uma conexão privada sem outro tráfego geralmente é o tipo de conexão mais confiável e mais confiável (por exemplo, uma conexão de fibra óptica alugada ou linha T1). Esse tipo de conexão fornece a maior capacidade de transporte de chamadas, mas geralmente é o mais caro. Não é necessário VPN. As conexões privadas são adequadas para organizações com alto volume de chamadas ou com requisitos de segurança e disponibilidade rígidos.

  - A Internet pública é o tipo de conexão menos barato, mas também a menos confiável, e a de menor capacidade de transporte de chamadas. Seu provedor de serviços de telefonia à Internet (ITSP) pode ajudar a proteger esse tipo de conexão de tronco SIP se ele der suporte ao protocolo TLS e SSTP (Secure real-time Transport Protocol) para criptografar a sinalização e o tráfego de mídia. Se não for possível configurar uma conexão de tronco SIP pela Internet para usar TLS e SRTP, recomendamos enfaticamente que você use um encapsulamento VPN para fornecer uma conexão mais segura. Entre em contato com o ITSP para determinar se ele fornece suporte para TLS com o SRTP.

<div>

## <a name="selecting-a-connection-type"></a>Selecionando um tipo de conexão

O tipo de conexão de tronco SIP mais apropriado para sua empresa depende de suas necessidades e de seu orçamento.

  - Para uma empresa de médio porte ou maior porte, uma rede MPLS geralmente oferece o maior valor. Ela pode fornecer a largura de banda necessária por uma taxa mais barata do que uma rede privada especializada.

  - Grandes empresas podem exigir uma conexão de fibra óptica ou uma conexão T1 privada.

  - Para uma pequena empresa ou site de filial com baixo volume de chamadas, o entroncamento SIP pela Internet pode ser a melhor opção. No entanto, esse tipo de conexão não é recomendado para sites de médio porte ou sites maiores.

</div>

</div>

<div>

## <a name="codec-support"></a>Suporte ao codec

O proxy do provedor de serviço deve dar suporte aos seguintes codecs:

  - G.711 a-law (usado principalmente fora da América do Norte)

  - G.711 µ-law (usado na América do Norte)

</div>

</div>

<span> </span>

</div>

</div>

</div>

