---
title: 'Lync Server 2013: Resumo de porta - Proxy reverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Reverse proxy
ms:assetid: 59b9ac3c-3e6f-4776-b366-174f0dd1f2eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204932(v=OCS.15)
ms:contentKeyID: 48184251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a86b993a35210934f5ebef61464c11a153bf297
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---reverse-proxy-in-lync-server-2013"></a>Resumo de porta - Proxy reverso no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-15_

O proxy reverso tem requisitos mínimos para firewall e porta/protocolo.

  - Os requisitos de firewall externo são HTTPS/TCP/443 e HTTP/TCP/80 opcionais. HTTPS é usado para comunicações seguras SSL e TLS por meio do proxy reverso. O HTTP é usado se você optar por permitir o acesso ao serviço de descoberta automática quando a modificação de certificados pode ser muito difícil ou não ser justificada pelo custo.

  - Os clientes esperam entrar em contato com o servidor do Office Web Apps no HTTPS. O servidor Office Web Apps espera a comunicação de clientes internos em HTTPS/TCP/443. A configuração recomendada é permitir HTTPS/TCP/443 do proxy reverso para o servidor do Office Web Apps.

  - A porta 8080 é usada para direcionar o tráfego da interface interna de proxy inverso para o servidor front-end, o VIP (IP virtual do pool de front-end) ou o diretor opcional ou VIP do pool do diretor. A porta TCP 8080 é necessária para dispositivos móveis que executam o Lync para localizar o serviço de descoberta automática em situações em que a modificação do certificado de regra de publicação do serviço Web externo é indesejável (por exemplo, se você tiver um grande número de domínios SIP). Se você optar por adquirir novos certificados com as entradas de SAN necessárias, a porta TCP 8080 não será necessária e será opcional.

  - A porta 4443 é usada para o tráfego da interface interna de proxy reverso para o servidor front-end, o VIP (IP virtual do pool de front-end) ou o diretor opcional ou VIP do pool do diretor
    
    ![13142405-D5C9-45b7-a8b7-a8c89f09c97c] (images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-D5C9-45b7-a8b7-a8c89f09c97c")  
    
    <div>
    

    > [!WARNING]  
    > Não confunda o 4443 sobre TCP do proxy reverso para a implantação interna da porta 4443 sobre o tráfego TCP do servidor Standard Edition ou do pool de front-ends que gerencia a função de repositório central de gerenciamento.

    
    </div>

<div>

## <a name="port-and-protocol-details"></a>Detalhes de protocolo e porta

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
<td><p>Adicionais Redirecionamento para HTTPS se o usuário entrar&lt;http://&gt;publishedSiteFQDN.</p>
<p>Também necessário se estiver usando o Office Web Apps para conferência e o serviço de descoberta automática para dispositivos móveis que executam o Lync em situações em que a organização não deseja modificar o certificado de regra de publicação de serviço Web externo.</p></td>
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
<td><p>Servidor front-end, pool de front-end, diretor, pool de diretor</p></td>
<td><p>Obrigatório se estiver usando o serviço de descoberta automática para dispositivos móveis executando o Lync em situações em que a organização não deseja modificar o certificado de regra de publicação de serviço Web externo.</p>
<p>O tráfego enviado para a porta 80 na interface externa de proxy reverso é redirecionado para um pool na porta 8080 da interface interna de proxy reverso para que os serviços Web de pool possam distingui-lo do tráfego interno da Web.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Interface de proxy inversa interna</p></td>
<td><p>Servidor front-end, pool de front-end, diretor, pool de diretor</p></td>
<td><p>O tráfego enviado para a porta 443 na interface externa de proxy reverso é redirecionado para um pool na porta 4443 da interface interna de proxy reverso para que os serviços Web de pool possam distingui-lo do tráfego interno da Web.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP/443</p></td>
<td><p>Interface de proxy inversa interna</p></td>
<td><p>Office Web Apps para conferência</p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

