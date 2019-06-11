---
title: 'Lync Server 2013: Única borda consolidada com endereços IP privados e NAT'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Single consolidated edge with private IP addresses and NAT
ms:assetid: e1e5189e-f17d-45e9-b177-e0e6f97f8951
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399001(v=OCS.15)
ms:contentKeyID: 48185691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f37395f840e8811d343f11f6ee2a84bd4fcfbf82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844915"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="single-consolidated-edge-with-private-ip-addresses-and-nat-in-lync-server-2013"></a>Única borda consolidada com endereços IP privados e NAT no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-08_

Se sua organização requer suporte para menos de 15.000 conexões de cliente de serviço de borda de acesso, 1.000 conexões de cliente de serviço de Webconferência do Lync Server Web 500 e as sessões de borda de A/V simultâneas, a alta disponibilidade do servidor de borda não é importante, essa topologia oferece as vantagens de reduzir o custo de hardware e a implantação mais simples. Se você precisa de maior capacidade ou requer alta disponibilidade, é preciso implantar uma topologia de servidor de borda consolidada em escala. Para obter detalhes, consulte um dos seguintes procedimentos:

  - <span></span>  
    [Borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT no Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - <span></span>  
    [Borda consolidada em escala, balanceamento de carga de DNS com endereços IP públicos no Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - <span></span>  
    [Borda consolidada em escala com balanceadores de carga de hardware no Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

A figura não mostra diretores, uma função de servidor opcional implantada na rede interna entre os servidores de borda e seus pools ou servidores de front-end. Para obter detalhes sobre a topologia para diretores, consulte [os componentes necessários para o diretor no Lync Server 2013](lync-server-2013-components-required-for-the-director.md). A figura representa um único proxy reverso.

<div>


> [!NOTE]  
> A imagem mostrada é para orientação e exemplo de endereçamento IP, mas não pretende representar os fluxos de comunicação reais com o tráfego de entrada e saída correto. A figura representa uma exibição de alto nível do possível tráfego. Os detalhes do fluxo de tráfego que pertencem à entrada (em portas de escuta) e saída (para clientes ou servidores de destino) são representados no diagrama de Resumo de porta em cada cenário. Por exemplo, o TCP 443 é realmente de entrada (apenas para a borda ou proxy reverso) e só é um fluxo bidirecional de uma perspectiva de protocolo (TCP). Além disso, a figura mostra a natureza do tráfego à medida que ele muda quando o NAT (conversão de endereço de rede) ocorre (o endereço de destino é alterado em entrada, o endereço de origem é alterado na saída). Exemplo de firewall externo e interno e interfaces do servidor são mostradas somente para fins de referência. Por fim, o gateway padrão e as relações de rota são exibidos, quando aplicável. Observe também que o diagrama usa a zona DNS <EM>. com</EM> para representar a zona DNS externa para servidores de proxy reverso e Edge e a zona DNS do <EM>.net</EM> refere-se à zona DNS interna.



</div>

O novo para o Microsoft Lync Server 2013 é compatível com endereçamento IPv6. Como endereçamento IPv4, os endereços IPv6 devem ser atribuídos de forma que os endereços sejam parte do espaço de endereço IPv6 atribuído. Os endereços neste tópico são somente por exemplo. Você deve adquirir endereços IPv6 que funcionarão na sua implantação, fornecer o escopo correto e interoperar com o endereçamento interno e externo. O Windows Server fornece um recurso que é importante para a operação IPv6 de transição e comunicação IPv4 para IPv6 chamada de *pilha dupla*. A pilha dupla é uma pilha de rede separada e distinta para IPv4 e IPv6. A pilha dupla é o que permite atribuir endereçamento para IPv4 e IPv6 simultaneamente e permite que o servidor se comunique com outros hosts e clientes de acordo com suas necessidades.

Os tipos de endereços típicos que você usará para endereçamento IPv6 serão os endereços globais IPv6 (semelhantes aos endereços IPv4 públicos), os endereços locais exclusivos do IPv6 (semelhantes aos intervalos de endereços IPv4 particulares) e os endereços locais de link IPv6 (semelhante ao IP particular automático endereços no Windows Server para IPv4)

Há tecnologias de conversão de endereços de rede (NAT) para IPv6 que permitirão o NAT IPv6 para IPv4 (comumente chamado de NAT64) e para IPv6 NAT para IPv6 (geralmente chamado de NAT66). A existência de tecnologias NAT significa que os cinco cenários apresentados para servidores do Lync Server Edge ainda são válidos.

<div>


> [!WARNING]  
> O IPv6 é um tópico complexo e requer planejamento cuidadoso com sua equipe de rede e seu provedor de Internet para garantir que os endereços que você atribuir no nível do Windows Server e no nível do Lync Server 2013 funcionarão conforme o esperado. Consulte os links no final deste tópico para obter recursos adicionais sobre o endereço IPv6 e planejamento.



</div>

**Topologia de borda consolidada única**

![d9b889c1-587c-4732-9b68-841186ccff78] (images/Gg399001.d9b889c1-587c-4732-9b68-841186ccff78(OCS.15).jpg "d9b889c1-587c-4732-9b68-841186ccff78")

<div>


> [!IMPORTANT]  
> Se você estiver usando o controle de admissão de chamadas (CAC), ainda deverá atribuir endereços IPv4 à interface interna do servidor de borda. O CAC usa endereços IPv4 e deve tê-los disponíveis para operação.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Resumo de certificado - única borda consolidada com endereços IP privados usando NAT no Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [Resumo de porta - única borda consolidada com endereços IP privados usando NAT no Lync Server 2013](lync-server-2013-port-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [Resumo de DNS - única borda consolidada com endereços IP privados usando NAT no Lync Server 2013](lync-server-2013-dns-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

</div>

<div>

## <a name="see-also"></a>Confira também


[Arquitetura de endereçamento de IP versão 6](http://tools.ietf.org/html/rfc4291)  
[Formato de endereço de difusão ponto a ponto global IPv6](http://tools.ietf.org/html/rfc3587)  
[Endereços exclusivos de unicast IPv6 locais](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

