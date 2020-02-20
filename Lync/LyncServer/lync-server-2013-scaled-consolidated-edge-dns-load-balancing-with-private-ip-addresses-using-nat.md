---
title: 'Lync Server 2013: borda consolidada dimensionada, balanceamento de carga de DNS com endereços IP privados usando NAT'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: c7ca4ca8-c639-4d93-86d7-8891170cacbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398823(v=OCS.15)
ms:contentKeyID: 48185369
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69d8720a9ac4d6c6df020f8599ad21d1e36de203
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a>Borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-08_

Na topologia do pool do Servidor de Borda, dois ou mais Servidores de Borda são implantados como um pool com carga balanceada na rede de perímetro do centro de dados. O balanceamento de carga DNS é usado para tráfego de interfaces de Borda externa e interna.

Se sua organização precisar de suporte para mais de 15.000 conexões de cliente do serviço de borda de acesso, 1.000 conexões de cliente do serviço de Webconferência do Lync Server, 500 ou as sessões de borda A/V simultâneas, e/ou alta disponibilidade do servidor de borda for importante, essa topologia oferecerá as vantagens de escalabilidade e suporte a failover.

A figura não mostra diretores, uma função de servidor opcional implantada na rede interna entre os servidores de borda e seus pools de front-ends ou servidor. Para obter detalhes sobre a topologia para diretores, consulte [os componentes necessários para o diretor no Lync Server 2013](lync-server-2013-components-required-for-the-director.md). A figura representa um único proxy inverso.

<div>


> [!NOTE]  
> A figura mostrada é para orientações e endereço IP de exemplo, mas não pretende representar fluxos de comunicações reais com o tráfego de entrada e saída correto. A figura representa uma exibição de alto nível do possível tráfego. Detalhes para o fluxo de tráfego como eles pertencem para entrada (para portas de ouvinte) e saída (para servidores de destino ou clientes) é representado no diagrama Resumo da Porta em cada cenário. Por exemplo, TCP 443 é a entrada (para a Borda ou proxy reverso) apenas e é apenas um fluxo de duas vias de uma perspectiva do protocolo (TCP). Além disso, a figura mostra a natureza do tráfego conforme muda quando o NAT (conversão de endereço de rede) ocorre (endereço de destino é alterado na entrada, o endereço de origem é alterado na saída). Exemplos de firewall externo e interno e interfaces do servidor são mostrados apenas para fins de referência. Por fim, o exemplo de gateway padrão e relações de roteamento são mostrados, onde aplicável. Observe também que o diagrama usa a zona DNS <EM>. com</EM> para representar a zona DNS externa para servidores de borda e proxy reverso e a zona DNS do <EM>.net</EM> refere-se à zona DNS interna.



</div>

Novo no Microsoft Lync Server 2013 é o suporte para o endereçamento IPv6. Parecido como o endereço IPv4, os endereços IPv6 devem ser atribuídos de tal forma que o endereço faz parte do seu espaço de endereço IPv6 atribuído. Os endereços neste tópico são apenas para exemplo. Você deve adquirir endereços IPv6 que funcionarão em sua implantação, oferecer o escopo correto e irá interoperar com o endereço interno e externo. O Windows Server fornece um recurso importante para a operação de IPv6 de transição e a comunicação IPv4 para IPv6 chamada de *pilha Dual*. A pilha dupla é uma pilha de rede distinta e separada para IPv4 e IPv6. A pilha dupla é que permite atribuir endereços para IPv4 e IPv6 simultaneamente e permite o servidor comunicar com outros hosts e clientes com base em seus requisitos.

Os tipos de endereços típicos que você usará para o endereçamento IPv6 serão os endereços globais IPv6 (semelhante aos endereços IPv4 públicos), endereços locais exclusivos IPv6 (semelhante aos intervalos de endereços IPv4 privados) e endereços de link local IPv6 (semelhante ao IP privado automático endereços no Windows Server para IPv4)

Tecnologias de conversação do endereço de rede (NAT) para IPv6 existem que permitirá o NAT IPv6 para IPv4 (geralmente chamado como NAT64) e de NAT IPv6 para IPv6 (geralmente chamado como NAT66). A existência de tecnologias NAT significa que os cinco cenários apresentados para servidores de borda do Lync Server ainda são válidos.

<div>


> [!WARNING]  
> O IPv6 é um tópico complexo e requer um planejamento cuidadoso com sua equipe de rede e seu provedor de Internet para garantir que os endereços que você atribui no nível do Windows Server e no nível do Lync Server 2013 funcionem conforme o esperado. Consulte os links no final deste tópico para obter recursos adicionais sobre o endereço IPv6 e planejamento.



</div>

![899546d4-2eef-44d2-8317-51c5f699cd2a](images/Gg398823.899546d4-2eef-44d2-8317-51c5f699cd2a(OCS.15).jpg "899546d4-2eef-44d2-8317-51c5f699cd2a")

<div>


> [!IMPORTANT]  
> Se você estiver usando o CAC (controle de admissão de chamadas), ainda deverá atribuir endereços IPv4 à interface interna do servidor de borda. O CAC usa endereços IPv4 e deve ter disponível para operar.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Resumo de certificado-borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT no Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)

  - [Resumo de porta-borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT no Lync Server 2013](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [Resumo de DNS-borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT no Lync Server 2013](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

</div>

<div>

## <a name="see-also"></a>Confira também


[Arquitetura de endereçamento de IP versão 6](https://tools.ietf.org/html/rfc4291)  
[Formato de endereço de unicast global IPv6](https://tools.ietf.org/html/rfc3587)  
[Endereços exclusivos de unicast IPv6 locais](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

