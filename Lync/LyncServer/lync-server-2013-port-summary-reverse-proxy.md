---
title: 'Lync Server 2013: Resumo de porta-proxy reverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Reverse proxy
ms:assetid: 59b9ac3c-3e6f-4776-b366-174f0dd1f2eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204932(v=OCS.15)
ms:contentKeyID: 48184251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6259614da322e79f69db40441125b28c95e379c9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183904"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---reverse-proxy-in-lync-server-2013"></a>Resumo de porta-proxy reverso no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-15_

O proxy reverso tem requisitos mínimos de firewall e porta/protocolo.

  - Os requisitos de firewall externos são o HTTPS/TCP/443 e o HTTP/TCP/80 opcional. O HTTPS é usado para comunicações seguras SSL e TLS por meio do proxy reverso. HTTP é usado se você optar por permitir o acesso ao serviço de descoberta automática ao modificar certificados pode ser muito difícil ou não ser justificado.

  - Os clientes esperam entrar em contato com o servidor do Office Web Apps no HTTPS. O servidor do Office Web Apps espera a comunicação de clientes internos em HTTPS/TCP/443. A configuração recomendada é permitir HTTPS/TCP/443 do proxy reverso para o servidor do Office Web Apps.

  - A porta 8080 é usada para rotear o tráfego da interface interna do proxy reverso para o servidor front-end, VIP (IP virtual) do pool de front-end ou o diretor opcional ou VIP do pool de diretores. A porta TCP 8080 é necessária para dispositivos móveis que executam o Lync para localizar o serviço de descoberta automática em situações em que a modificação do certificado de regra de publicação do serviço Web externo é indesejável (por exemplo, se você tiver um grande número de domínios SIP). Se você optar por adquirir novos certificados com as entradas de SAN necessárias, a porta TCP 8080 não será necessária e será opcional.

  - A porta 4443 é usada para o tráfego da interface interna do proxy reverso para o servidor front-end, IP virtual do pool de front-end (VIP) ou o diretor opcional ou VIP do pool de diretor
    
    ![13142405-D5C9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-D5C9-45b7-a8b7-a8c89f09c97c")  
    
    <div>
    

    > [!WARNING]  
    > Não confunda o 4443 sobre TCP do proxy reverso para a implantação interna da porta 4443 sobre o tráfego TCP do servidor Standard Edition ou do pool de front-ends que gerencia a função de repositório de gerenciamento central.

    
    </div>

<div>

## <a name="port-and-protocol-details"></a>Detalhes de Porta e Protocolo

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
<td><p>Qualquer tamanho</p></td>
<td><p>Ouvinte de proxy reverso</p></td>
<td><p>Opcion Redirecionamento para HTTPS se o usuário inserir&lt;http://&gt;publishedSiteFQDN.</p>
<p>Também necessário se estiver usando o Office Web Apps para conferência e o serviço de descoberta automática para dispositivos móveis que executam o Lync em situações em que a organização não deseja modificar o certificado de regra de publicação do serviço Web externo.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/443</p></td>
<td><p>Qualquer tamanho</p></td>
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
<td><p>Servidor front-end, pool de front-ends, diretor, pool de diretores</p></td>
<td><p>Necessário se estiver usando o serviço de descoberta automática para dispositivos móveis que executam o Lync em situações em que a organização não deseja modificar o certificado de regra de publicação do serviço Web externo.</p>
<p>O tráfego enviado para a porta 80 na interface externa do proxy reverso é redirecionado para um pool na porta 8080 a partir da interface interna do proxy reverso, para que os serviços Web do pool possam distingui-lo do tráfego Web interno.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Interface interna do proxy reverso</p></td>
<td><p>Servidor front-end, pool de front-ends, diretor, pool de diretores</p></td>
<td><p>O tráfego enviado para a porta 443 na interface externa do proxy reverso é redirecionado para um pool na porta 4443 a partir da interface interna do proxy reverso, para que os serviços Web do pool possam distingui-lo do tráfego Web interno.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP/443</p></td>
<td><p>Interface interna do proxy reverso</p></td>
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

