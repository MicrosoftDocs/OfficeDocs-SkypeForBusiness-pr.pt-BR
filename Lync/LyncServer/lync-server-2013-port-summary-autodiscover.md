---
title: 'Lync Server 2013: Resumo da porta-descoberta automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Autodiscover
ms:assetid: 8bd16363-5e18-4e4b-be99-b3e6457b4c99
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945642(v=OCS.15)
ms:contentKeyID: 51541497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 945e3ed9d532f27676e250c29ab415646bd967ec
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747621"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---autodiscover-in-lync-server-2013"></a>Resumo da porta-descoberta automática no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-03-05_

O serviço de descoberta automática do Lync Server 2013 é executado nos servidores do diretor e do pool de front-end e, `lyncdiscover.<domain>` quando `lyncdiscoverinternal.<domain>` publicados no DNS, usando os registros de host e de host, podem ser usados por clientes para localizar os recursos do Lync Server. Para que os dispositivos móveis que executam o Lync Mobile usem a descoberta automática, você precisa primeiro modificar listas de nomes alternativos de entidades de certificado em qualquer director e servidor front-end executando o serviço descoberta automática. Além disso, pode ser necessário modificar as listas de nomes alternativos de entidades nos certificados usados para regras de publicação de serviço Web externo em proxies reverso.

A decisão sobre se deve usar listas de nomes alternativos de entidades em proxies invertidos se baseia se você publica o serviço de descoberta automática na porta 80 ou na porta 443:

  - **Publicado na porta 80**   para dispositivos móveis, nenhuma alteração de certificado será necessária se a consulta inicial para o serviço descoberta automática ocorrer na porta 80. Isso ocorre porque os dispositivos móveis que executam o Lync acessam o proxy reverso na porta 80 externamente e, em seguida, redirecionados para um diretor ou servidor front-end na porta 8080 internamente.

  - **Publicado na porta 443**   a lista de nomes alternativos de entidades nos certificados usados pela regra de publicação de serviços Web externos `lyncdiscover.<sipdomain>` deve conter uma entrada para cada domínio SIP dentro de sua organização.
    
    <div>
    

    > [!IMPORTANT]  
    > Para novas instalações ou atualizações do Lync Server 2010 em que você implantou a mobilidade, você usou a porta 80 para descoberta automática do serviço de mobilidade ou emitiu novamente certificados com o nome da entidade apropriada e nomes alternativos da entidade no local. Revise os certificados no seu diretor e servidor front-end para confirmar qual caminho você escolheu.

    
    </div>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a>Detalhes do firewall para servidor de proxy reverso: interface externa

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocolo/TCP ou UDP/porta</th>
<th>Endereço IP de origem</th>
<th>Endereço IP de destino</th>
<th>Observações</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/80</p></td>
<td><p>Qualquer um</p></td>
<td><p>Escuta de proxy reverso</p></td>
<td><p>Adicionais Redirecionamento para HTTPS se o usuário entrar&lt;http://&gt;publishedSiteFQDN. Também necessário se estiver usando o Office Web Apps para conferência e o serviço de descoberta automática para dispositivos móveis que executam o Lync em situações em que a organização não deseja modificar o certificado de regra de publicação de serviço Web externo.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/443</p></td>
<td><p>Qualquer um</p></td>
<td><p>Escuta de proxy reverso</p></td>
<td><p>Downloads do catálogo de endereços, serviço de consulta à Web do catálogo de endereços, descoberta automática, atualizações do cliente, conteúdo da reunião, atualizações de dispositivo, expansão de grupo, Office Web Apps para conferência, conferência discada e reuniões.</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a>Detalhes do firewall para servidor proxy reverso: interface interna

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocolo/TCP ou UDP/porta</th>
<th>Endereço IP de origem</th>
<th>Endereço IP de destino</th>
<th>Observações</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/8080</p></td>
<td><p>Interface de proxy inversa interna</p></td>
<td><p>Servidor front-end, pool de front-end, diretor, pool do director, Office Web Apps para conferência</p></td>
<td><p>Obrigatório se estiver usando o serviço de descoberta automática para dispositivos móveis executando o Lync em situações em que a organização não deseja modificar o certificado de regra de publicação de serviço Web externo. O tráfego enviado para a porta 80 na interface externa de proxy reverso é redirecionado para um pool na porta 8080 da interface interna de proxy reverso para que os serviços Web de pool possam distingui-lo do tráfego interno da Web.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Interface de proxy inversa interna</p></td>
<td><p>Servidor front-end, pool de front-end, diretor, pool do director, Office Web Apps para conferência</p></td>
<td><p>O tráfego enviado para a porta 443 na interface externa de proxy reverso é redirecionado para um pool na porta 4443 da interface interna de proxy reverso para que os serviços Web de pool possam distingui-lo do tráfego interno da Web.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

