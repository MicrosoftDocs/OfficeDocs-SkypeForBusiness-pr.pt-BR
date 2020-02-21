---
title: Resumo de certificado-borda consolidada única com endereços IP públicos
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
ms.openlocfilehash: 11f1658ed907018e71590ad2ff60120fb6336ccd
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a>Resumo de certificado-borda consolidada única com endereços IP públicos no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-08_

O Microsoft Lync Server 2013 usa certificados para autenticar mutuamente outros servidores e para criptografar dados de servidor para servidor e servidor para cliente. Os certificados exigem correspondência de nomes de registros DNS (sistema de nomes de domínio) associados a servidores e SN (nome da entidade) e SAN (nome alternativo da entidade) no certificado. Para mapear servidores, registros DNS e entradas de certificados com sucesso, você deve planejar com cuidado os nomes de domínio totalmente qualificados registrados no DNS e as entradas de SN e SAN no certificado.

O certificado atribuído às interfaces externas do servidor de borda é solicitado de uma autoridade de certificação (CA) pública. As CAs públicas que demonstraram o sucesso no fornecimento de certificados para os fins de comunicações unificadas estão listadas [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=929395](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=929395) no seguinte artigo: ao solicitar o certificado, você pode usar a solicitação de certificado gerada pelo assistente de implantação do Lync Server ou criar a solicitação manualmente ou por um processo fornecido pela autoridade de certificação pública. Ao atribuir o certificado, o certificado é atribuído à interface de serviço de borda de acesso, a interface de serviço de borda de Webconferência e o serviço de autenticação de áudio/vídeo. O serviço de autenticação de áudio/vídeo não deve ser confundido com o serviço de borda A/V que não usa um certificado para criptografar os fluxos de áudio e vídeo. A interface de servidor de borda interna pode usar um certificado de uma autoridade de certificação interna (para sua organização) ou um certificado de uma autoridade de certificação pública. O certificado da interface interna usa somente o SN e não necessita ou usa entradas de SAN.

<div>


> [!NOTE]
> A tabela a seguir mostra uma segunda entrada SIP (sip.fabrikam.com) na lista de nome alternativo do assunto para referência. Para cada domínio SIP em sua organização, você precisa adicionar um FQDN correspondente listado na lista de nome alternativo do assunto do certificado.



</div>

<div>

## <a name="certificates-required-for-single-consolidated-edge-with-public-ip-addresses"></a>Certificados necessários para Borda consolidada única com endereços IP públicos


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
<th>Ordem/nome alternativo de entidade (SAN)</th>
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
<td><p>O certificado deverá ser de uma CA pública e ter EKU de cliente e servidor se a conectividade IM pública com AOL for implantada. O certificado é atribuído a interfaces de Borda externas para:</p>
<ul>
<li><p>Borda de acesso</p></li>
<li><p>Borda de conferência</p></li>
<li><p>Borda A/V</p></li>
</ul>
<p>Observe que os SANs são adicionados automaticamente ao certificado com base nas definições do Construtor de Topologia. Você adiciona entradas SAN conforme necessário para domínios SIP adicionais e outras entradas que você precisa suportar. O nome do assunto é replicado no SAN e deve estar presente para a operação correta.</p></td>
</tr>
<tr class="even">
<td><p>Borda consolidada única (borda interna)</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>Nenhum SAN obrigatório</p></td>
<td><p>O certificado pode ser emitido por uma CA pública ou privada e deve conter o EKU do servidor. O certificado é atribuído à interface de Borda interna.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a>Resumo do certificado – Conectividade com mensagens instantâneas públicas


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
<th>Nomes alternativos de entidade (SAN)/Ordem</th>
<th>Comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Borda de Acesso/Externo</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>O certificado deverá ser de uma CA pública e ter EKU de cliente e servidor se a conectividade IM pública com AOL for implantada. O certificado é atribuído a interfaces de Borda externas para:</p>
<ul>
<li><p>Borda de acesso</p></li>
<li><p>Borda de conferência</p></li>
<li><p>Borda A/V</p></li>
</ul>
<p>Observe que os SANs são adicionados automaticamente ao certificado com base nas definições no Construtor de Topologias. Adicione entradas de SAN conforme necessário para domínios SIP adicionais e outras entradas às quais precise oferecer suporte. O nome da entidade é replicado no SAN e deve estar presente para que a operação seja correta.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a>Resumo de certificado para protocolo XMPP


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
<th>Nomes alternativos de entidade (SAN)/Ordem</th>
<th>Comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Atribuir ao serviço de borda de acesso do servidor de borda ou do pool de borda</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p>
<p>xmpp.contoso.com</p>
<p><strong>*. contoso.com</strong></p></td>
<td><p>As três primeiras entradas de SAN são as entradas de SAN normais para um servidor de borda completo. A contoso.com é a entrada exigida para federação com o parceiro XMPP no nível de domínio raiz. Essa entrada autorizará XMPP para todos os domínios com sufixo *.contoso.com.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

