---
title: 'Lync Server 2013: criptografia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Encryption for Lync Server 2013
ms:assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481135(v=OCS.15)
ms:contentKeyID: 59893874
ms.date: 09/14/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5cc25c66ce807e796cf7e510d89a5a623f98eb49
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="encryption-for-lync-server-2013"></a>Criptografia para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2017-09-14_

O Microsoft Lync Server 2013 usa TLS e MTLS para criptografar mensagens instantâneas. Todo o tráfego de servidor para servidor requer MTLS, independentemente de o tráfego ter sido confinado na rede interna ou cruzar o perímetro da rede interna. O TLS é opcional, mas é altamente recomendável entre o servidor de mediação e o gateway de mídia. Se o TLS estiver configurado nesse link, MTLS será necessário. Portanto, o gateway deve ser configurado com um certificado de uma autoridade de certificação que é confiável para o servidor de mediação.

<div>


> [!NOTE]  
> Um comunicado de segurança sobre SSL 3,0 foi publicado no 2014. A desabilitação do SSL 3,0 no Lync Server 2013 é uma opção com suporte. Para saber mais sobre o comunicado de segurança, <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>consulte.



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
<td>Para garantir que o protocolo criptográfico mais forte seja usado, o Lync Server 2013 oferecerá protocolos de criptografia TLS na seguinte ordem para clientes: <strong>TLS 1,2</strong> , <strong>TLS 1,1</strong>, <strong>TLS 1,0</strong>. O TLS é um aspecto crítico do Lync Server 2013 e, portanto, é necessário para manter um ambiente com suporte.</td>
</tr>
</tbody>
</table>


</div>

Os requisitos do tráfego de cliente para cliente depende de o tráfego atravessar ou não o firewall corporativo interno. O tráfego estritamente interno pode usar o TLS (as mensagens instantâneas são criptografadas) ou o TCP (as mensagens instantâneas não são criptografadas).

A tabela a seguir resume os requisitos de protocolo de cada tipo de tráfego.

### <a name="traffic-protection"></a>Proteção de tráfego

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de tráfego</th>
<th>Protegido por</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Servidor para servidor</p></td>
<td><p>MTLS</p></td>
</tr>
<tr class="even">
<td><p>Cliente para servidor</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="odd">
<td><p>Sistema de mensagens instantâneas e presença</p></td>
<td><p>TLS (se configurado para TLS)</p></td>
</tr>
<tr class="even">
<td><p>Compartilhamento de área de trabalho, áudio e vídeo da mídia</p></td>
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
<td><p>Download do conteúdo das reuniões, download do catálogo de endereços, expansão de grupos de distribuição</p></td>
<td><p>HTTPS</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="media-encryption"></a>Criptografia da mídia

O tráfego de mídia é criptografado usando SRTP, um perfil de protocolo RTP que fornece confidencialidade, autenticação e proteção contra ataque de repetição para o tráfego RTP. Além disso, o fluxo de mídia em ambas as direções entre o Servidor de Mediação e seu próximo salto interno também é criptografado usando o SRTP. O fluxo de mídia em ambas as direções entre o servidor de mediação e um gateway de mídia não é criptografado por padrão. O Servidor de Mediação pode oferecer suporte à criptografia para o gateway de mídia, mas o gateway deve oferecer suporte ao MTLS e ao armazenamento de um certificado.

<div>


> [!NOTE]  
> Áudio/vídeo (A/V) é compatível com a nova versão do Windows Live Messenger. Se você estiver implementando uma federação A/V com Windows Live Messenger, também deverá modificar o nível de criptografia do Lync Server. Por padrão, o nível de criptografia é Obrigatório. Você deve alterar essa configuração para suportado usando o Shell de gerenciamento do Lync Server. Para obter mais informações, consulte <A href="lync-server-2013-deploying-external-user-access.md">Deploying external User Access in Lync Server 2013</A> na documentação de implantação.



</div>

O tráfego de mídia de áudio e vídeo não é criptografado entre os clientes do Microsoft Lync 2013 e do Windows Live.

</div>

<div>

## <a name="fips"></a>FIPS

O Lync Server 2013 e o Microsoft Exchange Server 2013 operam com suporte para algoritmos normativos FIPS (Federal Information Processing Standard 140-2) se os sistemas operacionais Windows Server estiverem configurados para usar os algoritmos FIPS 140-2 para criptografia de sistema. Para implementar o suporte a FIPS, você deve configurar cada servidor executando o Lync Server 2013 para dar suporte a ele. Para obter detalhes sobre o uso de algoritmos compatíveis com FIPS e sobre como implementar o suporte a FIPS, consulte o artigo 811833 da base de dados de conhecimento da Microsoft, os efeitos da habilitação da configuração de segurança "criptografia de sistema: usar algoritmos compatíveis com FIPS para criptografia, hash [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)e assinatura" no Windows XP e em versões posteriores do Windows em. Para obter detalhes sobre o suporte a FIPS 140-2 e limitações no Exchange 2010, consulte Exchange 2010 SP1 e suporte para algoritmos compatíveis com FIPS em [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335).

</div>

</div>

<span> </span>

</div>

</div>

</div>

