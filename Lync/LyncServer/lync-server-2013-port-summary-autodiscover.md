---
title: 'Lync Server 2013: Resumo de porta-descoberta automática'
description: 'Lync Server 2013: Resumo de porta-descoberta automática.'
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
ms.openlocfilehash: 20a5ef54d4ad8419fd6e73909f97764bf1290c22
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543137"
---
# <a name="port-summary---autodiscover-in-lync-server-2013"></a>Resumo de porta-descoberta automática no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-03-05_

O serviço de descoberta automática do Lync Server 2013 é executado nos servidores do diretor e do pool de front-ends, e quando publicado no DNS usando os `lyncdiscover.<domain>` `lyncdiscoverinternal.<domain>` registros de host, pode ser usado por clientes para localizar recursos do Lync Server. Para que os dispositivos móveis que executam o Lync Mobile usem a descoberta automática, você precisará primeiro modificar listas de nomes alternativos de entidades de certificado em qualquer diretor e servidor front-end executando o serviço de descoberta automática. Além disso, pode ser necessário modificar as listas de nomes alternativos de entidade nos certificados usados pelas regras de publicação de serviços de Web externa em proxies reversos.

A decisão sobre a utilização de listas de nomes alternativos de entidades em proxies reversos baseia-se no fato de você publicar o serviço de descoberta automática na porta 80 ou na porta 443:

  - **Publicado na porta 80**     Para dispositivos móveis, nenhuma alteração de certificado será necessária se a consulta inicial para o serviço de descoberta automática ocorrer pela porta 80. Isso ocorre porque os dispositivos móveis que executam o Lync acessarão o proxy reverso na porta 80 externamente e, em seguida, serão redirecionados para um diretor ou servidor front-end na porta 8080 internamente.

  - **Publicado na porta 443**     A lista de nomes alternativos da entidade em certificados usados pela regra de publicação dos serviços Web externos deve conter uma `lyncdiscover.<sipdomain>` entrada para cada domínio SIP em sua organização.
    
    <div>
    

    > [!IMPORTANT]  
    > Para novas instalações ou atualizações do Lync Server 2010 onde você implantou a mobilidade, você usou a porta 80 para descoberta automática do serviço de mobilidade ou emitiu novamente os certificados com o nome da entidade e os nomes alternativos da entidade apropriados. Revise os certificados no diretor e servidor front-end para confirmar qual caminho você escolheu.

    
    </div>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a>Detalhes de firewall do servidor proxy reverso: interface externa

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocolo/TCP ou UDP/Porta</th>
<th>Endereço IP de origem</th>
<th>Endereço IP de destino</th>
<th>Observações</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/80</p></td>
<td><p>Qualquer</p></td>
<td><p>Ouvinte de proxy reverso</p></td>
<td><p>Opcion Redirecionamento para HTTPS se o usuário inserir http:// &lt; publishedSiteFQDN &gt; . Também necessário se estiver usando o Office Web Apps para conferência e o serviço de descoberta automática para dispositivos móveis que executam o Lync em situações em que a organização não deseja modificar o certificado de regra de publicação do serviço Web externo.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/443</p></td>
<td><p>Qualquer</p></td>
<td><p>Ouvinte de proxy reverso</p></td>
<td><p>Downloads do catálogo de endereços, serviço de consulta à Web do catálogo de endereços, descoberta automática, atualizações do cliente, conteúdo da reunião, atualizações de dispositivo, expansão de grupo, Office Web Apps para conferência, conferência discada e reuniões.</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a>Detalhes de firewall do servidor proxy reverso: interface interna

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocolo/TCP ou UDP/Porta</th>
<th>Endereço IP de origem</th>
<th>Endereço IP de destino</th>
<th>Observações</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/8080</p></td>
<td><p>Interface interna do proxy reverso</p></td>
<td><p>Servidor front-end, pool de front-ends, diretor, pool de diretores, Office Web Apps para conferência</p></td>
<td><p>Necessário se estiver usando o serviço de descoberta automática para dispositivos móveis que executam o Lync em situações em que a organização não deseja modificar o certificado de regra de publicação do serviço Web externo. O tráfego enviado para a porta 80 na interface externa do proxy reverso é redirecionado para um pool na porta 8080 a partir da interface interna do proxy reverso, para que os serviços Web do pool possam distingui-lo do tráfego Web interno.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Interface interna do proxy reverso</p></td>
<td><p>Servidor front-end, pool de front-ends, diretor, pool de diretores, Office Web Apps para conferência</p></td>
<td><p>O tráfego enviado para a porta 443 na interface externa do proxy reverso é redirecionado para um pool na porta 4443 a partir da interface interna do proxy reverso, para que os serviços Web do pool possam distingui-lo do tráfego Web interno.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

