---
title: 'Lync Server 2013: Como implementar tronco SIP?'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: How do I implement SIP trunking?
ms:assetid: 273a22b1-8a4c-4187-acf8-c57d5c6598ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425743(v=OCS.15)
ms:contentKeyID: 48183666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c14375f9e0b7f3a7615c11ddaca2bc6c46ec72f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829067"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-do-i-implement-sip-trunking-in-lync-server-2013"></a>Como implementar tronco SIP no Lync Server 2013?

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-03-18_

Para implementar o entroncamento SIP, você deve direcionar a conexão por meio de um servidor de mediação, que atua como um proxy para sessões de comunicação entre clientes do Lync Server 2013 e o provedor de serviço e transformações de mídia, quando necessário.

Cada servidor de mediação tem uma interface de rede interna e uma interface de rede externa. A interface interna se conecta aos servidores front-end. A interface externa geralmente é chamada de interface do gateway porque tem sido usada tradicionalmente para conectar o servidor de mediação a um gateway PSTN (rede telefônica pública comutada) ou a um IP-PBX. Para implementar um tronco SIP, conecte a interface externa do servidor de mediação ao componente Edge externo da ITSP.

<div>


> [!NOTE]  
> O componente de borda externa do ITSP pode ser um SBC (Controlador de Borda da Sessão), um roteador ou um gateway.



</div>

Para obter detalhes sobre os servidores de mediação, consulte [componente servidor de mediação no Lync server 2013](lync-server-2013-mediation-server-component.md).

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a>Tronco SIP centralizado versus distribuído

*Centralizado* O entroncamento SIP roteia todo o tráfego do protocolo VoIP, incluindo o tráfego do site da filial, por meio de seu site central. O modelo de implantação centralizado é simples, econômico e geralmente é a abordagem recomendada para a implementação de troncos SIP com o Lync Server 2013.

*Distribuído* O entroncamento SIP é um modelo de implantação no qual você implementa um tronco SIP local em um ou mais sites de filiais. O tráfego de VoIP é então encaminhado do site de filial diretamente para um provedor de serviços sem passar pelo site central.

O tronco SIP distribuído é necessário somente nos seguintes casos:

  - O site da filial requer conectividade de telefone para o telefone cofuncional (por exemplo, se a WAN ficar inoperante). Esse requisito deve ser analisado para cada site de filiais; algumas das suas filiais podem exigir redundância e failover, enquanto outras não podem.

  - A resiliência é necessária entre dois sites centrais. Você precisa ter certeza de que um tronco SIP termina em cada site central. Por exemplo, se você tiver sites centrais de Dublin e Tukwila e ambos usarem apenas um tronco SIP do site, se o tronco ficar inativo, os usuários do outro site não poderão fazer chamadas PSTN.

  - O site de ramificação e o site central estão em países/regiões diferentes. Por motivos legais e de compatibilidade, você precisa de pelo menos um tronco SIP por país/região. Por exemplo, na União Europeia, as comunicações não podem deixar um país/região sem terminarem localmente em um ponto centralizado.

Dependendo da localização geográfica dos sites e da quantidade de tráfego que você prevê na sua empresa, talvez você não queira direcionar todos os usuários por meio do tronco SIP central ou pode optar por direcionar alguns usuários por meio de um tronco SIP em seu site de filiais. Para analisar suas necessidades, responda às seguintes perguntas:

  - Qual é o tamanho de cada site (ou seja, quantos usuários estão habilitados para o Enterprise Voice)?

  - Quais números DID (discagem direta interna) em cada local recebem a maioria das chamadas?

A decisão de implantar um tronco SIP centralizado ou distribuído exige uma análise de custo-benefício. Em alguns casos, pode ser vantajoso optar pelo modelo de implantação distribuído mesmo se ele não for necessário. Em uma implantação completamente centralizada, todo o tráfego do site da filial é roteado através de links WAN. Em vez de pagar pela largura de banda necessária ao link de WAN, convém usar o tronco SIP distribuído. Por exemplo, você pode querer implantar um servidor Standard Edition em um site de filial com Federação para o site central ou pode querer implantar um aparelho de ramificação sobreviventes ou um servidor de ramificação sobreviventes com um pequeno gateway.

<div>


> [!NOTE]  
> Para obter detalhes sobre o entroncamento SIP distribuído, consulte <A href="lync-server-2013-branch-site-sip-trunking.md">entroncamento do site de ramificação SIP no Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a>Tipos de conexão de tronco SIP suportadas

O Lync Server oferece suporte aos seguintes tipos de conexão para entroncamento SIP:

  - O MPLS é uma rede privada que direciona e transporta dados de um nó de rede para o próximo. A largura de banda em uma rede MPLS é compartilhada com outros assinantes e cada pacote de dados recebe um rótulo para diferenciar os dados de um assinante dos dados de outro assinante. Esse tipo de conexão não exige VPN (rede virtual privada). Uma possível desvantagem é que o tráfego IP excessivo pode interferir na operação de VoIP, a menos que o tráfego VoIP tenha prioridade.

  - Uma conexão privada sem outro tráfego, por exemplo, uma conexão de fibra ótica concedida ou uma linha T1, é normalmente o tipo de conexão mais confiável e seguro. Esse tipo de conexão oferece a maior capacidade de realização de chamadas, mas é geralmente o mais caro. Não é necessário VPN. As conexões privadas são adequadas para organizações com alto volume de chamadas ou com requisitos de segurança e disponibilidade rígidos.

  - A Internet é o tipo de conexão menos caro, mas também o menos confiável. Conexão à Internet é o único tipo de conexão de entroncamento do Lync Server SIP que requer VPN.

<div>

## <a name="selecting-a-connection-type"></a>Selecionando um tipo de conexão

O tipo de conexão de tronco SIP mais apropriado para sua empresa depende de suas necessidades e de seu orçamento.

  - Para uma empresa de médio ou grande porte, uma rede MPLS normalmente fornece o maior valor. Ela pode fornecer a largura de banda necessária por uma taxa mais barata do que uma rede privada especializada.

  - Empresas de grande porte podem exigir uma conexão de fibra ótica, T1, T3 ou superior privada (E1, E3 ou superior na União Europeia).

  - Para uma pequena empresa ou site de filial com baixo volume de chamadas, o entroncamento SIP pela Internet pode ser a melhor opção. Esse tipo de conexão não é recomendado para locais de médio ou grande porte.

</div>

</div>

<div>

## <a name="bandwidth-requirements"></a>Requisitos de largura de banda

A quantidade de largura de banda exigida pela sua implementação depende da capacidade da chamada (o número de chamadas simultâneas que você precisa suportar). A disponibilidade de largura de banda precisa ser levada em consideração para que você possa aproveitar ao máximo a capacidade de pico pela qual pagou. Use a fórmula a seguir para calcular o requisito de largura de banda de pico do tronco SIP:

Largura de banda de pico do tronco SIP = máximo de chamadas simultâneas x (64 kbps + tamanho do cabeçalho)

<div>


> [!NOTE]  
> O tamanho do cabeçalho é de 20 bytes no máximo.



</div>

</div>

<div>

## <a name="codec-support"></a>Suporte ao codec

O Lync Server 2013 só oferece suporte aos seguintes codecs:

  - G.711 a-law (usado principalmente fora da América do Norte)

  - G.711 µ-law (usado na América do Norte)

</div>

<div>

## <a name="internet-telephony-service-provider"></a>Provedor de Serviço de Telefonia pela Internet

O modo de implementação do lado do provedor de serviços de uma conexão de tronco SIP varia de um ITSP para outro. Para obter informações de implantação, contate seu provedor de serviços. Para obter uma lista de provedores de serviços de entroncamento SIP certificados, consulte [website Microsoft Unified Communication Open Interoperability Program](http://go.microsoft.com/fwlink/?linkid=287029).

Para obter detalhes sobre os provedores de tronco SIP certificado pela Microsoft, entre em contato com seu representante da Microsoft.

<div>


> [!IMPORTANT]  
> Você deve usar um provedor de serviço certificado pela Microsoft para garantir que seu ITSP suporte todas as funcionalidades que atravessam o tronco SIP (por exemplo, configurar e gerenciar sessões e suportar todos os serviços de VoIP estendido). O suporte técnico da Microsoft não estender as configurações que usam provedores não certificados. Se você atualmente usa um provedor de serviço Internet não certificado para tronco SIP, é possível optar por continuar usando este provedor como seu ISP e usar um provedor certificado pela Microsoft para tronco SIP.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

