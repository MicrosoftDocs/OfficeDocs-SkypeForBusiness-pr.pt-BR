---
title: Suporte de tronco SIP do Lync Server 2013
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
ms.openlocfilehash: 2fd2bd6d66b8b4f040e654f2412f86027071f9ac
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunking-support-in-lync-server-2013"></a>Suporte de tronco SIP no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-03_

Se você planeja usar o Enterprise Voice com tronco SIP, você deve implantar um servidor de mediação e certificar-se de que outros componentes e infraestrutura atendem aos requisitos de suporte apropriados ao seu modelo de implantação. Para obter detalhes sobre como determinar se deve implementar o tronco SIP, consulte [Overview of SIP trunking in Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) na documentação de planejamento.

Você pode usar o programa de interoperabilidade aberta do Microsoft Unified Communications para infraestrutura de telefonia corporativa para localizar gateways PSTN (rede telefônica pública comutada), IP-PBXs e serviços de tronco SIP, incluindo telefonia IP qualificada provedores de serviços. Para obter detalhes, consulte o site do programa de interoperabilidade aberta [http://go.microsoft.com/fwlink/p/?LinkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309)do Microsoft Unified Communications em.

<div>

## <a name="mediation-server-support"></a>Suporte ao servidor de mediação

Para implementar o tronco SIP, você deve encaminhar a conexão por meio de um servidor de mediação, que atua como um proxy para sessões de comunicação entre os clientes do Lync Server 2013 e o provedor de serviços. O servidor de mediação decodifica o tráfego de mídia de clientes e servidores e o codifica novamente antes de enviá-lo ao provedor de serviços. A recodificação é necessária porque os troncos SIP não dão suporte a alguns codecs usados, como o RTA (áudio em tempo real) ou a negociação de protocolo ICE (estabelecimento de conectividade interativa) para passagem de firewall.

Cada servidor de mediação pode ter dois adaptadores de rede, que fornecem uma interface de rede interna e externa. A interface externa é normalmente chamada de interface de gateway porque, tradicionalmente, ela foi usada para se conectar a um gateway PSTN ou a um IP-PBX. Para implementar um tronco SIP, conecte a interface externa a um controlador de borda de sessão (SBC) em um provedor de serviços.

</div>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a>Tronco SIP centralizado versus distribuído

*Centralizado* O tronco SIP roteia todo o tráfego do protocolo VoIP, incluindo o tráfego do site da filial, por meio do Data Center. O modelo de implantação centralizado é simples, econômico e geralmente é a abordagem preferida para a implementação de troncos SIP com o Lync Server 2013.

Dependendo dos padrões de uso em sua empresa, talvez você não queira rotear todos os usuários por meio do tronco SIP centralizado. Para analisar suas necessidades, responda às seguintes perguntas:

  - Qual é o tamanho de cada site? Quantos usuários?

  - Quais números DID (discagem direta interna) em cada site recebem mais chamadas telefônicas?

*Distribuído* O tronco SIP é um modelo de implantação no qual você implementa um tronco SIP local em um ou mais sites de filial. O tráfego VoIP é então roteado do site de filial diretamente para o provedor de serviços, sem passar pelo Data Center.

O tronco SIP distribuído é exigido somente nos seguintes casos:

  - O site de filial requer conectividade de telefone persistente (por exemplo, se a WAN for desativada). Se a ramificação precisar de redundância e failover, o provedor de serviços cobrará mais e a configuração levará mais tempo. Isso deve ser analisado para cada site de filial. Algumas das suas filiais podem exigir redundância e failover, enquanto outras não.

  - O site de filial e o Data Center estão em países/regiões diferentes. Por motivos legais e de compatibilidade, você precisa de pelo menos um tronco SIP por país/região.

Decidir se deve implantar o tronco SIP centralizado ou distribuído requer uma análise de custo-benefício. Em alguns casos, talvez seja vantajoso optar pelo modo de implantação distribuída, mesmo se não for necessário. Em uma implantação completamente centralizada, todo o tráfego do site da filial é roteado através de links WAN. Em vez de pagar pela largura de banda exigida pelo link de WAN, convém usar o tronco SIP distribuído.

<div>


> [!NOTE]  
> Para obter detalhes sobre por que e como você pode usar o tronco SIP distribuído, consulte <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP trunking in Lync Server 2013</A> na documentação de planejamento.



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a>Tipos de conexão de tronco SIP suportadas

O Lync Server 2013 oferece suporte aos seguintes tipos de conexão para tronco SIP:

  - MPLS (Multiprotocol Label Switching) é uma rede privada que direciona e transporta dados de um nó de rede para o próximo. A largura de banda em uma rede MPLS é compartilhada com outros assinantes e cada pacote de dados recebe um rótulo para diferenciar os dados de um assinante dos dados de outro assinante. Esse tipo de conexão não requer VPN. Uma possível desvantagem é que o tráfego IP excessivo pode interferir com a operação VoIP, a menos que o tráfego VoIP tenha prioridade.

  - Uma conexão privada sem outro tráfego é normalmente o tipo de conexão mais confiável e segura (por exemplo, uma conexão de fibra óptica dedicada ou uma linha T1). Esse tipo de conexão fornece a maior capacidade de transporte de chamadas, mas geralmente é o mais caro. VPN não é necessário. Conexões privadas são adequadas para organizações com alto volume de chamadas ou com requisitos de segurança e disponibilidade rígidos.

  - A Internet pública é o tipo de conexão menos caro, mas também a menos confiável, e aquela com a menor capacidade de transporte de chamadas. Seu provedor de serviços de telefonia da Internet (ITSP) pode ajudar a proteger esse tipo de conexão de tronco SIP se ele oferecer suporte à segurança da camada de transporte (TLS) e ao protocolo SRTP para criptografar a sinalização e o tráfego de mídia. Se você não puder configurar uma conexão de tronco SIP através da Internet para usar TLS e SRTP, recomendamos enfaticamente que você use um túnel VPN para fornecer uma conexão mais segura. Entre em contato com seu ITSP para determinar se ele fornece suporte para TLS com SRTP.

<div>

## <a name="selecting-a-connection-type"></a>Selecionando um tipo de conexão

O tipo de conexão de tronco SIP mais apropriado para sua empresa depende de suas necessidades e de seu orçamento.

  - Para uma empresa de médio ou grande porte, uma rede MPLS geralmente fornece o maior valor. Ela pode fornecer a largura de banda necessária por uma taxa mais barata do que uma rede privada especializada.

  - Grandes empresas podem exigir uma conexão privada óptica de fibra ou T1.

  - Para uma pequena empresa ou um site de filial com baixo volume de chamadas, o tronco SIP através da Internet pode ser a melhor opção. No entanto, esse tipo de conexão não é recomendado para sites de tamanho médio ou maior.

</div>

</div>

<div>

## <a name="codec-support"></a>Suporte ao codec

O proxy do provedor de serviços deve suportar os seguintes codecs:

  - G.711 a-law (usado principalmente fora da América do Norte)

  - G.711 µ-law (usado na América do Norte)

</div>

</div>

<span> </span>

</div>

</div>

</div>

