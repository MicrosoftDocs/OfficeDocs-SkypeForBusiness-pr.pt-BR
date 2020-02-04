---
title: 'Lync Server 2013: Borda consolidada em escala com balanceadores de carga de hardware'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled consolidated edge with hardware load balancers
ms:assetid: 6783e225-9677-415a-8731-0bf2e2c4cf8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398478(v=OCS.15)
ms:contentKeyID: 48184353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fe027019953175c0ac6ede51a86ad3a300c2681
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Borda consolidada em escala com balanceadores de carga de hardware no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-21_

Na topologia do pool de bordas, dois ou mais servidores Edge são implantados como um pool de balanceamento de carga na rede de perímetro do Data Center. O balanceamento de carga de hardware é usado para tráfego nas interfaces do servidor de borda externa e interna.

Se a sua organização requer suporte para mais de 15.000 conexões de cliente de serviço de borda de acesso, as conexões de cliente de serviço de borda do serviço de borda de Webconferência do 1.000 500 ou as sessões de serviço de borda a/V simultâneas e alta disponibilidade do servidor de borda é importante, essa topologia oferece as vantagens de escalabilidade e suporte de failover.

A figura não mostra diretores, uma função de servidor opcional implantada na rede interna entre os servidores de borda e seus pools ou servidores de front-end. . Para obter detalhes sobre a topologia para diretores, consulte [os componentes necessários para o diretor no Lync Server 2013](lync-server-2013-components-required-for-the-director.md).

<div>


> [!NOTE]  
> A imagem mostrada é para orientação e exemplo de endereçamento IP, mas não pretende representar os fluxos de comunicação reais com o tráfego de entrada e saída correto. A figura representa uma exibição de alto nível do possível tráfego. Os detalhes do fluxo de tráfego que pertencem à entrada (em portas de escuta) e saída (para clientes ou servidores de destino) são representados no diagrama de Resumo de porta em cada cenário. Por exemplo, o TCP 443 é realmente de entrada (apenas para o servidor de borda ou proxy reverso) e só é um fluxo bidirecional de uma perspectiva de protocolo (TCP). Além disso, a figura mostra a natureza do tráfego à medida que ele muda quando o NAT (conversão de endereço de rede) ocorre (o endereço de destino é alterado em entrada, o endereço de origem é alterado na saída). Exemplo de firewall externo e interno e interfaces do servidor são mostradas somente para fins de referência. Por fim, o gateway padrão e as relações de rota são exibidos, quando aplicável. Observe também que o diagrama usa a zona DNS <EM>. com</EM> para representar a zona DNS externa para servidores de proxy reverso e Edge e a zona DNS do <EM>.net</EM> refere-se à zona DNS interna.



</div>

O novo para o Microsoft Lync Server 2013 é compatível com endereçamento IPv6. Como endereçamento IPv4, os endereços IPv6 devem ser atribuídos de forma que os endereços sejam parte do espaço de endereço IPv6 atribuído. Os endereços neste tópico são somente por exemplo. Você deve adquirir endereços IPv6 que funcionarão na sua implantação, fornecer o escopo correto e interoperar com o endereçamento interno e externo. O Windows Server fornece um recurso que é importante para a operação IPv6 de transição e comunicação IPv4 para IPv6 chamada de *pilha dupla*. A pilha dupla é uma pilha de rede separada e distinta para IPv4 e IPv6. A pilha dupla é o que permite atribuir endereçamento para IPv4 e IPv6 simultaneamente e permite que o servidor se comunique com outros hosts e clientes de acordo com suas necessidades.

Os tipos de endereços típicos que você usará para endereçamento IPv6 serão os endereços globais IPv6 (semelhantes aos endereços IPv4 públicos), os endereços locais exclusivos do IPv6 (semelhantes aos intervalos de endereços IPv4 particulares) e os endereços locais de link IPv6 (semelhante ao IP particular automático endereços no Windows Server para IPv4)

Há tecnologias de conversão de endereços de rede (NAT) para IPv6 que permitirão o NAT IPv6 para IPv4 (comumente chamado de NAT64) e para IPv6 NAT para IPv6 (geralmente chamado de NAT66). A existência de tecnologias NAT significa que os cinco cenários apresentados para servidores do Lync Server Edge ainda são válidos.

<div>


> [!WARNING]  
> O IPv6 é um tópico complexo e requer planejamento cuidadoso com sua equipe de rede e seu provedor de Internet para garantir que os endereços que você atribuir no nível do Windows Server e no nível do Lync Server 2013 funcionarão conforme o esperado. Consulte os links no final deste tópico para obter recursos adicionais sobre o endereço IPv6 e planejamento.



</div>

**Configuração do balanceador de carga de hardware**

Para obter detalhes, consulte a seção "requisitos do balanceador de carga de hardware para A/V Edge" em [componentes necessários para o acesso de usuários externos no Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).

**Topologia de borda consolidada redimensionada (hardware com balanceamento de carga)**

![3a57cd0d-8de4-4ecc-a783-4dff5b3456a2](images/Gg398478.3a57cd0d-8de4-4ecc-a783-4dff5b3456a2(OCS.15).jpg "3a57cd0d-8de4-4ecc-a783-4dff5b3456a2")

<div>


> [!IMPORTANT]  
> Se você estiver usando o controle de admissão de chamadas (CAC), ainda deverá atribuir endereços IPv4 à interface interna do servidor de borda. O CAC usa endereços IPv4 e deve tê-los disponíveis para operação.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Resumo de certificado - Borda consolidada em escala com balanceadores de carga de hardware no Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [Resumo de porta - borda consolidada em escala com balanceadores de carga de hardware no Lync Server 2013](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [Resumo de DNS - borda consolidada em escala com balanceadores de carga de hardware no Lync Server 2013](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

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

