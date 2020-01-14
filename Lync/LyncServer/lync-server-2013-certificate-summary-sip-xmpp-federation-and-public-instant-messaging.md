---
title: Resumo do certificado-SIP, Federação do XMPP e mensagens instantâneas públicas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 933d6351-cfa6-4432-b3ed-1aff3ac92065
ms:mtpsurl: https://technet.microsoft.com/library/JJ618372(v=OCS.15)
ms:contentKeyID: 49105659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aede53e06493fab89a843ccc2de543aed7f05dae
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111545"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Resumo do certificado-SIP, Federação do XMPP e mensagens instantâneas públicas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-03-15_

Os certificados que você precisa para a Federação com o Microsoft Lync Server 2013, o Lync Server 2010 e o Office Communications Server normalmente serão atendidos pelos certificados que você configurar, solicitar e atribuir ao seu servidor de borda.

Os requisitos de certificado para habilitar e estabelecer comunicações com os parceiros do protocolo de presença Extensible Messaging e de presença (XMPP) exigem a adição de entradas para seus domínios do XMPP. O registro incluído no certificado como um nome alternativo de assunto (SAN) será o domínio que pode participar de comunicações XMPP. O domínio pode ser o domínio de nível raiz (por exemplo, contoso.com) se você quiser habilitar o XMPP para o seu domínio inteiro ou pode ser selecionado domínios filho (por exemplo, corp.contoso.com, finance.contoso.com) se você estiver habilitando XMPP para um subconjunto de usuários.

Para configurar certificados para conectividade de mensagens instantâneas públicas, observe que não há nada diferente de outros tipos de Federação SIP ou até mesmo dos certificados de servidor de borda padrão, exceto que o America Online (AOL) requer um certificado ou certificados (em o caso de um pool de bordas) também contenha o EKU do cliente. O EKU do cliente é uma adição ao certificado e faz parte do certificado público externo atribuído ao seu servidor de borda.

Para confirmar que você atendeu aos requisitos de certificado corretos para a implantação do servidor de borda, revise os tópicos listados na seção intitulada **Consulte também**.

<div>



<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente</th>
<th>Nome do assunto</th>
<th>Nomes alternativos de entidades (SAN)</th>
<th>Comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Borda externa/de acesso</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>contoso.com</p>



> [!NOTE]
> Para dar suporte ao namespace contoso.com XMPP


<p>sip.fabrikam.com</p>



> [!NOTE]
> Para dar suporte ao namespace SIP fabrikam.com


<p>fabrikam.com</p>



> [!NOTE]
> Para dar suporte ao namespace fabrikam.com XMPP

</td>
<td><p>O certificado deve ser de uma CA pública e deve ter o EKU do servidor e o cliente EKU se a conectividade de IM pública com AOL for implantada. O certificado é atribuído às interfaces do servidor de borda externo para:</p>
<ul>
<li><p>Serviço de Borda de Acesso</p></li>
<li><p>Serviço de Borda de Webconferência</p></li>
<li><p>Serviço de Borda A/V</p></li>
</ul>



> [!NOTE]
> Tecnicamente, um certificado não é atribuído à borda A/V. A comunicação e a autenticação seguras são gerenciadas por meio do serviço de autenticação de retransmissão de mídia (MRAS). O MRAS usa o certificado atribuído à interface interna do servidor de borda.


<p>Observe que as SANs são adicionadas automaticamente ao certificado com base em suas definições no construtor de topologias. Você adiciona entradas de SAN conforme necessário para domínios SIP adicionais e outras entradas de que você precisa para dar suporte. O nome do requerente é replicado na SAN e deve estar presente para a operação correta.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Confira também


[Exemplo de configuração de XMPP no Lync Server 2013 – federação XMPP com Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Planejar certificados do Servidor de Borda no Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  
[Resumo de certificado - única borda consolidada com endereços IP privados usando NAT no Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[Resumo de certificado - Única borda consolidada com endereços IP públicos no Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[Resumo de certificado - borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT no Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)  
[Resumo de certificado - Borda consolidade em escala, balanceamento de carga de DNS com endereços IP públicos no Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[Resumo de certificado - Borda consolidada em escala com balanceadores de carga de hardware no Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

