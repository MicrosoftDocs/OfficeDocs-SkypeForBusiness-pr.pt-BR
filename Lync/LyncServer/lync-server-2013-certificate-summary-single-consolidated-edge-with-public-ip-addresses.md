---
title: Resumo de certificado - Única borda consolidada com endereços IP públicos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Single consolidated edge with public IP addresses
ms:assetid: 25b8ae7a-e5a0-43c0-92ae-7e144d5e4a36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204747(v=OCS.15)
ms:contentKeyID: 48183653
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1880856214632357a1a4190a22cd56b29dee020a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722602"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a>Resumo de certificado - Única borda consolidada com endereços IP públicos no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-08_

O Microsoft Lync Server 2013 usa certificados para autenticar mutuamente outros servidores e criptografar dados do servidor para o servidor e o servidor para o cliente. Os certificados exigem correspondência de nome dos registros de sistema de nomes de domínio (DNS) associados aos servidores e o nome da entidade (SN) e o nome alternativo do assunto (SAN) no certificado. Para mapear com êxito os servidores, registros DNS e entradas de certificado, você deve planejar cuidadosamente os nomes de domínio totalmente qualificados do servidor conforme registrado no DNS e as entradas de SN e SAN no certificado.

O certificado atribuído às interfaces externas do servidor de borda é solicitado a partir de uma autoridade de certificação pública (CA). As CAs públicas que demonstraram sucesso no fornecimento de certificados para a finalidade de comunicações unificadas são listadas no [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=929395](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=929395) seguinte artigo: ao solicitar o certificado, você pode usar a solicitação de certificado gerada pelo assistente de implantação do Lync Server ou criar a solicitação manualmente ou por um processo fornecido pela CA pública. Ao atribuir o certificado, o certificado é atribuído à interface do serviço de borda de acesso, à interface do serviço de borda de Webconferência e ao serviço de autenticação de áudio/vídeo. O serviço de autenticação de áudio/vídeo não deve ser confundido com o serviço de borda A/V que não usa um certificado para criptografar os fluxos de áudio e vídeo. A interface do servidor de borda interna pode usar um certificado de uma autoridade de certificação interna (para a sua organização) ou de um certificado de uma autoridade de certificação pública. O certificado de interface interna usa apenas o SN e não precisa ou usa entradas de SAN.

<div>


> [!NOTE]
> A tabela a seguir mostra uma segunda entrada SIP (sip.fabrikam.com) na lista nome alternativo do assunto como referência. Para cada domínio SIP em sua organização, você precisa adicionar um FQDN correspondente listado na lista nome alternativo do requerente do certificado.



</div>

<div>

## <a name="certificates-required-for-single-consolidated-edge-with-public-ip-addresses"></a>Certificados necessários para uma única aresta consolidada com endereços IP públicos


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
<th>Nome da entidade (SN)</th>
<th>Nomes alternativos de assunto (SAN)/Order</th>
<th>Comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Borda consolidada única (borda externa)</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>O certificado deve ser de uma CA pública e deve ter o EKU do servidor e o cliente EKU se a conectividade de IM pública com AOL for implantada. O certificado é atribuído às interfaces de borda externa para:</p>
<ul>
<li><p>Borda de Acesso</p></li>
<li><p>Borda de conferência</p></li>
<li><p>Borda A/V</p></li>
</ul>
<p>Observe que as SANs são adicionadas automaticamente ao certificado com base em suas definições no construtor de topologias. Você adiciona entradas de SAN conforme necessário para domínios SIP adicionais e outras entradas de que você precisa para dar suporte. O nome do requerente é replicado na SAN e deve estar presente para a operação correta.</p></td>
</tr>
<tr class="even">
<td><p>Borda consolidada única (borda interna)</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>Sem necessidade de SAN</p></td>
<td><p>O certificado pode ser emitido por uma autoridade de certificação pública ou privada e deve conter o EKU do servidor. O certificado é atribuído à interface de borda interna.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a>Resumo do certificado – conectividade de mensagens instantâneas públicas


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
<th>Nomes alternativos de assunto (SAN)/Order</th>
<th>Comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Borda externa/de acesso</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>O certificado deve ser de uma CA pública e deve ter o EKU do servidor e o cliente EKU se a conectividade de IM pública com AOL for implantada. O certificado é atribuído às interfaces de borda externa para:</p>
<ul>
<li><p>Borda de Acesso</p></li>
<li><p>Borda de conferência</p></li>
<li><p>Borda A/V</p></li>
</ul>
<p>Observe que as SANs são adicionadas automaticamente ao certificado com base em suas definições no construtor de topologias. Você adiciona entradas de SAN conforme necessário para domínios SIP adicionais e outras entradas de que você precisa para dar suporte. O nome do requerente é replicado na SAN e deve estar presente para a operação correta.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a>Resumo do certificado de mensagens extensíveis e protocolo de presença


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
<th>Nomes alternativos de assunto (SAN)/Order</th>
<th>Comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Atribuir ao serviço Edge para acessar o servidor de borda ou o pool de bordas</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p>
<p>xmpp.contoso.com</p>
<p><strong>*.contoso.com</strong></p></td>
<td><p>As três primeiras entradas de SAN são as entradas de SAN normais para um servidor de perímetro completo. O contoso.com é a entrada necessária para federação com o parceiro XMPP no nível do domínio raiz. Essa entrada permitirá XMPP para todos os domínios com o sufixo *. contoso.com.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

