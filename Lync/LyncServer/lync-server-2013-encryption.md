---
title: 'Lync Server 2013: criptografia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Encryption for Lync Server 2013
ms:assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481135(v=OCS.15)
ms:contentKeyID: 59893874
ms.date: 09/14/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01c989213b050bdb536e95a8a42e8f7b35292eaf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="encryption-for-lync-server-2013"></a>Criptografia para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2017-09-14_

O Microsoft Lync Server 2013 usa TLS e MTLS para criptografar mensagens instantâneas. Todo o tráfego de servidor para servidor necessita do MTLS, independentemente se o tráfego está restrito à rede interna ou se ultrapassa seu perímetro. O TLS é opcional, mas altamente recomendável entre o servidor de mediação e o gateway de mídia. Se o TLS for configurado neste link, o MTLS será necessário. Portanto, o gateway deve ser configurado com um certificado de uma autoridade de certificação que seja confiável para o servidor de mediação.

<div>


> [!NOTE]  
> Um comunicado de segurança sobre SSL 3.0 foi publicado em 2014. A desabilitação do SSL 3,0 no Lync Server 2013 é uma opção com suporte. Para saber mais sobre o comunicado de segurança, <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>consulte.



</div>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="segurança" alt="security" />Observação de segurança:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Para garantir que o protocolo criptográfico mais forte seja usado, o Lync Server 2013 oferecerá protocolos de criptografia TLS na seguinte ordem para clientes: <strong>TLS 1,2</strong> , <strong>TLS 1,1</strong>, <strong>TLS 1,0</strong>. O TLS é um aspecto crítico do Lync Server 2013 e, portanto, é necessário para manter um ambiente compatível.</td>
</tr>
</tbody>
</table>


</div>

Os requisitos para tráfego de cliente para cliente dependem do fato de o tráfego cruzar o firewall corporativo interno. O tráfego interno estrito pode usar o TLS, caso em que a mensagem instantânea está criptografada, ou TCP, e, nesse caso, não é.

A seguinte tabela resume os requisitos de protocolo para cada tipo de tráfego.

### <a name="traffic-protection"></a>Proteção de Tráfego

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de Tráfego</th>
<th>Protegido por</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Servidor para Servidor</p></td>
<td><p>MTLS</p></td>
</tr>
<tr class="even">
<td><p>Cliente para Servidor</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="odd">
<td><p>Mensagens instantâneas e presença</p></td>
<td><p>TLS (se configurado para TLS)</p></td>
</tr>
<tr class="even">
<td><p>Compartilhamento de mídia de áudio, vídeo e de área de trabalho</p></td>
<td><p>SRTP</p></td>
</tr>
<tr class="odd">
<td><p>Compartilhamento de área de trabalho (sinalização)</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="even">
<td><p>Webconferência</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="odd">
<td><p>Download de conteúdo de reunião, download do catálogo de endereços, expansão de grupo de distribuição</p></td>
<td><p>HTTPS</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="media-encryption"></a>Criptografia de mídia

O tráfego de mídia é criptografado usando SRTP (Secure RTP), um perfil do protocolo RTP que fornece confidencialidade, autenticação e proteção contra ataques de repetição para o tráfego RTP. Além disso, a mídia que flui em ambas as direções entre o Servidor de Mediação e seu próximo salto interno também é criptografada usando SRTP. A mídia flui em ambas as direções entre o servidor de mediação e um gateway de mídia não é criptografada por padrão. O Servidor de Mediação pode dar suporte à criptografia para o gateway de mídia, mas o gateway deve dar suporte a MTLS e ao armazenamento de um certificado.

<div>


> [!NOTE]  
> Áudio/vídeo (A/V) é compatível com a nova versão do Windows Live Messenger. Se você estiver implementando a Federação de A/V com o Windows Live Messenger, também deverá modificar o nível de criptografia do Lync Server. Por padrão, o nível de criptografia é Exigido. Você deve alterar essa configuração para com suporte usando o Shell de gerenciamento do Lync Server. Para obter mais informações, consulte Implantando o <A href="lync-server-2013-deploying-external-user-access.md">acesso de usuários externos no Lync Server 2013</A> na documentação de implantação.



</div>

O tráfego de mídia de áudio e vídeo não é criptografado entre clientes do Microsoft Lync 2013 e do Windows Live.

</div>

<div>

## <a name="fips"></a>FIPS

O Lync Server 2013 e o Microsoft Exchange Server 2013 operam com suporte para algoritmos de 140-2 padrão FIPS (Federal Information Processing Standard) se os sistemas operacionais Windows Server estiverem configurados para usar os algoritmos FIPS 140-2 para criptografia do sistema. Para implementar o suporte a FIPS, você deve configurar cada servidor que está executando o Lync Server 2013 para dar suporte a ele. Para obter detalhes sobre o uso de algoritmos compatíveis com FIPS e sobre como implementar o suporte a FIPS, consulte o artigo 811833 da base de dados de conhecimento Microsoft, os efeitos de habilitar a segurança "criptografia do sistema: usar algoritmos compatíveis com FIPS para criptografia, hash e assinatura" configuração no Windows XP e em versões posteriores do Windows [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)em. Para obter detalhes sobre o suporte e as limitações do FIPS 140-2 no Exchange 2010, consulte Exchange 2010 SP1 e suporte para [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335)algoritmos compatíveis com FIPS em.

</div>

</div>

<span> </span>

</div>

</div>

</div>

