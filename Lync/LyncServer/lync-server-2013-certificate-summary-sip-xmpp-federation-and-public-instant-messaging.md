---
title: Resumo de certificado-SIP, Federação XMPP e mensagens instantâneas públicas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 933d6351-cfa6-4432-b3ed-1aff3ac92065
ms:mtpsurl: https://technet.microsoft.com/library/JJ618372(v=OCS.15)
ms:contentKeyID: 49105659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 284a633a2c5ce820009c6672058837bbecb7ecd6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517868"
---
# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Resumo de certificado-SIP, Federação XMPP e mensagens instantâneas públicas no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-03-15_

Os certificados necessários para a Federação com o Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server serão normalmente atendidos pelos certificados que você configurou, solicitam e atribuem ao servidor de borda.

Os requisitos de certificado para habilitar e estabelecer comunicações com os parceiros XMPP (Extensible Messaging and Presence Protocol) exigem a adição de entradas para seus domínios do XMPP. O registro incluído no certificado como um nome alternativo da entidade (SAN) será o domínio que pode participar das comunicações XMPP. O domínio pode ser o domínio no nível raiz (por exemplo, contoso.com) se você deseja habilitar XMPP para o domínio inteiro ou pode ser determinados domínios filho (por exemplo, corp.contoso.com, finance.contoso.com) se estiver habilitando XMPP para um subconjunto de usuários.

Para configurar certificados para conectividade de mensagens instantâneas públicas, observe que não há nada diferente de outros tipos de Federação SIP ou até mesmo de certificados de servidor de borda padrão, exceto que America Online (AOL) exige que o certificado ou certificados (no caso de um pool de borda) também contenham o EKU do cliente. O EKU do cliente é uma adição ao certificado e faz parte do certificado público externo atribuído ao servidor de borda.

Para confirmar se você atende aos requisitos de certificado corretos para a implantação do servidor de borda, revise os tópicos listados na seção intitulada **Consulte também**.

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
<th>Nome da entidade</th>
<th>SAN (nomes alternativos da entidade)</th>
<th>Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Borda de Acesso/Externo</p></td>
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
<td><p>O certificado deve ser de uma autoridade de certificação pública e deve ter o EKU do servidor e o EKU do cliente se a conectividade de IM pública com AOL for implantada. O certificado é atribuído às interfaces do servidor de borda externo para:</p>
<ul>
<li><p>Serviço de Borda de Acesso</p></li>
<li><p>Web Conferencing Edge service</p></li>
<li><p>serviço de Borda A/V</p></li>
</ul>



> [!NOTE]
> Tecnicamente, um certificado não é atribuído à borda A/V. A comunicação e a autenticação seguras são gerenciadas por meio do serviço de autenticação de retransmissão de mídia (MRAS). MRAS usa o certificado atribuído à interface interna do servidor de borda.


<p>Observe que os SANs são adicionados automaticamente ao certificado com base nas suas definições no Construtor de Topologia. É possível adicionar entradas SAN conforme necessário para domínios SIP adicionais e outras enteadas que precisam de suporte. O nome do assunto é replicado no SAN e deve estar presente para a operação correta.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Confira também


[Exemplo de configuração de XMPP no Lync Server 2013 – Federação do XMPP com Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Planejar certificados de servidor de borda no Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  
[Resumo de certificado-borda consolidada única com endereços IP privados usando NAT no Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[Resumo de certificado-borda consolidada única com endereços IP públicos no Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[Resumo de certificado-borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT no Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)  
[Resumo de certificado-borda consolidada em escala, balanceamento de carga de DNS com endereços IP públicos no Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[Resumo de certificado-borda consolidada em escala com balanceadores de carga de hardware no Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

