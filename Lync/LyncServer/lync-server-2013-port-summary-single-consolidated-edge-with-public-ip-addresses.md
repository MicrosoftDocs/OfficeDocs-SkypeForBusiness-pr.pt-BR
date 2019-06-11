---
title: Sumário de porta - única borda consolidada com endereços IP públicos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Single consolidated edge with public IP addresses
ms:assetid: 28407acc-8b92-4f78-875c-fd6b4323b602
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204756(v=OCS.15)
ms:contentKeyID: 48183685
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c1a61341908bef3a3098e70b06816bbf5ea328b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824236"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a>Sumário de porta - única borda consolidada com endereços IP públicos no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

A funcionalidade do servidor de borda do Lync Server 2013 descrita nesta arquitetura de cenário é muito semelhante à implementada no Lync Server 2010. A adição mais perceptível é a porta **5269 sobre** a entrada TCP para o protocolo de mensagens extensíveis e de presença (XMPP). O Lync Server 2013, opcionalmente, implanta um proxy XMPP no servidor de borda ou no pool de periféricos e o servidor de Gateway XMPP no servidor front-end ou no pool de front-end. As informações de planejamento para o proxy reverso e a Federação são encontradas em [cenários para inverter proxy no Lync server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) e [planejamento para SIP, Federação do XMPP e mensagens instantâneas públicas nas seções do Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) , respectivamente.

Além do IPv4, o servidor de borda agora oferece suporte ao IPv6. Para fins de clareza, somente o IPv4 é usado nos cenários.

**Rede de perímetro da empresa para uma única aresta consolidada com endereçamento de IP público**

![f8c144c5-e5fb-498a-823e-eb39f26b6847] (images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")

<div>

## <a name="port-and-protocol-details"></a>Detalhes de protocolo e porta

Recomendamos que você abra apenas as portas necessárias para dar suporte à funcionalidade para a qual você está fornecendo acesso externo.

Para que o acesso remoto funcione para qualquer serviço de borda, é obrigatório que o tráfego SIP tenha permissão de fluxo bidirecionalmente, como mostrado na figura de tráfego de borda de entrada/saída. Declarado de outra maneira, o recurso de mensagens SIP para e do serviço de borda de acesso está envolvido em mensagens instantâneas (IM), presença, Web conferência, áudio/vídeo (A/V) e Federação.

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a>Resumo de firewall para uma única aresta consolidada com endereços IP públicos: interface externa

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Função/protocolo/TCP ou UDP/porta</th>
<th>Endereço IP de Origem</th>
<th>Endereço IP de Destino</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Qualquer um</p></td>
<td><p>Serviço de proxy XMPP (compartilha o endereço IP com o serviço de borda de acesso)</p></td>
<td><p>O serviço de proxy XMPP aceita o tráfego de contatos do XMPP em agrupamentos XMPP definidos</p></td>
</tr>
<tr class="even">
<td><p>Access/HTTP/TCP/80</p></td>
<td><p>Endereço IP público do serviço de borda do acesso ao servidor de borda</p></td>
<td><p>Qualquer um</p></td>
<td><p>Revogação e verificação de revogação/revogação de certificados e recuperação</p></td>
</tr>
<tr class="odd">
<td><p>Access/DNS/TCP/53</p></td>
<td><p>Endereço IP público do serviço de borda do acesso ao servidor de borda</p></td>
<td><p>Qualquer um</p></td>
<td><p>Consulta DNS via TCP</p></td>
</tr>
<tr class="even">
<td><p>Access/DNS/UDP/53</p></td>
<td><p>Endereço IP público do serviço de borda do acesso ao servidor de borda</p></td>
<td><p>Qualquer um</p></td>
<td><p>Consulta DNS via UDP</p></td>
</tr>
<tr class="odd">
<td><p>/TCP/443 de acesso/SIP (TLS)</p></td>
<td><p>Qualquer um</p></td>
<td><p>Endereço IP público do serviço de borda do acesso ao servidor de borda</p></td>
<td><p>Tráfego SIP de cliente para servidor para acesso de usuário externo</p></td>
</tr>
<tr class="even">
<td><p>/TCP/5061 de acesso/SIP (MTLS)</p></td>
<td><p>Qualquer um</p></td>
<td><p>Endereço IP público do serviço de borda do acesso ao servidor de borda</p></td>
<td><p>Para conectividade de mensagens de chat públicas e federadas usando SIP</p></td>
</tr>
<tr class="odd">
<td><p>/TCP/5061 de acesso/SIP (MTLS)</p></td>
<td><p>Endereço IP público do serviço de borda do acesso ao servidor de borda</p></td>
<td><p>Qualquer um</p></td>
<td><p>Para conectividade de mensagens de chat públicas e federadas usando SIP</p></td>
</tr>
<tr class="even">
<td><p>Web Conferencing/PSOM (TLS)/TCP/443</p></td>
<td><p>Qualquer um</p></td>
<td><p>Endereço IP público do serviço de borda de Webconferência do Edge Server Web</p></td>
<td><p>Mídia de Webconferência</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/TCP/50.000 A 59.999</p></td>
<td><p>Endereço IP público do serviço de borda do acesso ao servidor de borda</p></td>
<td><p>Qualquer um</p></td>
<td><p>Obrigatório para federação com parceiros que executam o Office Communications Server 2007, o Office Communications Server 2007 R2, o Lync Server 2010 e o Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/UDP/50000-59.999</p></td>
<td><p>Endereço IP público do serviço de borda do servidor de borda A/V</p></td>
<td><p>Qualquer um</p></td>
<td><p>Obrigatório somente para federação com parceiros que executam o Office Communications Server 2007</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/TCP/50.000 A 59.999</p></td>
<td><p>Qualquer um</p></td>
<td><p>Endereço IP público do serviço de borda do servidor de borda A/V</p></td>
<td><p>Obrigatório somente para federação com parceiros que executam o Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/UDP/50000-59.999</p></td>
<td><p>Qualquer um</p></td>
<td><p>Endereço IP público do serviço de borda do servidor de borda A/V</p></td>
<td><p>Obrigatório somente para federação com parceiros que executam o Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Endereço IP público do serviço de borda do servidor de borda A/V</p></td>
<td><p>Qualquer um</p></td>
<td><p>3478 a saída é usada para determinar a versão do servidor de borda com a qual o Lync Server está se comunicando e também para o tráfego de mídia do servidor edge edge-to-edge. Obrigatório para federação com o Lync Server 2010, o Windows Live Messenger e o Office Communications Server 2007 R2 e também se vários pools de bordas forem implantados em uma empresa.</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Qualquer um</p></td>
<td><p>Endereço IP público do serviço de borda do servidor de borda A/V</p></td>
<td><p>STUN/desliga a negociação de candidatos via UDP/3478</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Qualquer um</p></td>
<td><p>Endereço IP público do serviço de borda do servidor de borda A/V</p></td>
<td><p>STUN/TRANSFORMe a negociação de candidatos via TCP/443</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Endereço IP público do serviço de borda do servidor de borda A/V</p></td>
<td><p>Qualquer um</p></td>
<td><p>STUN/TRANSFORMe a negociação de candidatos via TCP/443</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a>Resumo de firewall para uma única aresta consolidada com endereços IP públicos: interface interna

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
<th>Endereço IP de Origem</th>
<th>Endereço IP de Destino</th>
<th>Comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>Any (pode ser definido como padrão de servidor Standard Edition, endereço IP do servidor Standard Edition ou endereço IP do pool executando o serviço de gateway do XMPP)</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Tráfego de XMPP de saída do serviço de gateway do XMPP em execução em servidor front-end ou pool de front-end</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>Any (pode ser definido como director, endereço IP do pool do diretor, servidor front-end ou endereço IP do pool de front-end)</p></td>
<td><p>IP do servidor de borda ou pool que mantém a interface interna</p></td>
<td><p>Tráfego SIP de saída (do director, endereço IP do pool do diretor, servidor front-end ou endereço IP do pool de front-end) para a interface interna do servidor de borda</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Any (pode ser definido como director, endereço IP do pool do diretor, servidor front-end ou endereço do pool de front-end)</p></td>
<td><p>Tráfego SIP de entrada (para o director, endereço IP do pool do diretor, servidor front-end ou endereço IP do pool de front-end) da interface interna do servidor de borda</p></td>
</tr>
<tr class="even">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>Any (pode ser definido como o endereço IP do servidor front-end ou cada endereço IP do servidor front-end em um pool Front-end)</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Tráfego de Webconferência do servidor front-end ou de cada servidor front-end se estiver em um pool, para a interface interna do servidor de borda</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>Any (pode ser definido como endereço IP do servidor front-end ou endereço IP do pool de front-end ou qualquer aparelho de ramificação sobreviventes ou servidor de ramificação sobreviventes que use este servidor de borda)</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Autenticação de usuários de A/V (serviço de autenticação A/V) do servidor front-end ou do endereço IP do pool de front-end ou qualquer aparelho de ramificação sobreviventes ou servidor de ramificação sobreviventes que use este servidor de borda</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>Qualquer um</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Caminho preferencial para transferência de mídia A/V entre usuários internos e externos, aparelho de ramificação sobreviventes ou servidor de ramificação sobreviventes</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Qualquer um</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Caminho de fallback para transferência de mídia A/V entre usuários internos e externos, aparelho de ramificação sobreviventes ou servidor de ramificação sobreviventes se não for possível estabelecer comunicação UDP, o TCP será usado para transferência de arquivos e compartilhamento de área de trabalho</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Any (pode ser definido como o endereço IP do servidor front-end ou o pool que mantém o repositório de gerenciamento central)</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Replicação de alterações do repositório de gerenciamento central para o servidor de borda</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Qualquer um</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Controlador de serviço de log centralizado usando cmdlets do Shell de gerenciamento do Lync Server e do serviço de log centralizado, comandos de linha de comando do ClsController (ClsController. exe) ou comandos do agente (ClsAgent. exe) e a coleção de logs</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Qualquer um</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Controlador de serviço de log centralizado usando cmdlets do Shell de gerenciamento do Lync Server e do serviço de log centralizado, comandos de linha de comando do ClsController (ClsController. exe) ou comandos do agente (ClsAgent. exe) e a coleção de logs</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Qualquer um</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Controlador de serviço de log centralizado usando cmdlets do Shell de gerenciamento do Lync Server e do serviço de log centralizado, comandos de linha de comando do ClsController (ClsController. exe) ou comandos do agente (ClsAgent. exe) e a coleção de logs</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a>Resumo do firewall para Federação


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Função/protocolo/TCP ou UDP/porta</th>
<th>Endereço IP de Origem</th>
<th>Endereço IP de Destino</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>/TCP/5061 de acesso/SIP (MTLS)</p></td>
<td><p>Endereço IP público do serviço de borda do Access</p></td>
<td><p>Qualquer um</p></td>
<td><p>Para conectividade de mensagens de chat públicas e federadas usando SIP</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a>Resumo do Firewall – Conectividade de mensagens instantâneas públicas


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Função/protocolo/TCP ou UDP/porta</th>
<th>Endereço IP de Origem</th>
<th>Endereço IP de Destino</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>/TCP/5061 de acesso/SIP (MTLS)</p></td>
<td><p>Parceiros de conectividade de mensagens de chat públicas</p></td>
<td><p>Serviço de borda de acesso do servidor de borda</p></td>
<td><p>Para conectividade de mensagens de chat públicas e federadas usando SIP</p></td>
</tr>
<tr class="even">
<td><p>/TCP/5061 de acesso/SIP (MTLS)</p></td>
<td><p>Serviço de borda de acesso do servidor de borda</p></td>
<td><p>Parceiros de conectividade de mensagens de chat públicas</p></td>
<td><p>Para conectividade de mensagens de chat públicas e federadas usando SIP</p></td>
</tr>
<tr class="odd">
<td><p>/TCP/443 de acesso/SIP (TLS)</p></td>
<td><p>Clientes</p></td>
<td><p>Serviço de borda de acesso do servidor de borda</p></td>
<td><p>Tráfego SIP de cliente para servidor para acesso de usuário externo</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50.000 A 59.999</p></td>
<td><p>Serviço Edge Server A/V Edge</p></td>
<td><p>Clientes do Live Messenger</p></td>
<td><p>Usado para sessões de A/V com o Windows Live Messenger se a conectividade de mensagem de chat pública estiver configurada.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Serviço Edge Server A/V Edge</p></td>
<td><p>Clientes do Live Messenger</p></td>
<td><p>Necessário para conectividade de IM pública com o Windows Live Messenger</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Clientes do Live Messenger</p></td>
<td><p>Serviço Edge Server A/V Edge</p></td>
<td><p>Necessário para conectividade de IM pública com o Windows Live Messenger</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a>Resumo de firewall para mensagens extensíveis e protocolo de presença


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
<th>Fonte (endereço IP)</th>
<th>Destino (endereço IP)</th>
<th>Comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Qualquer um</p></td>
<td><p>Endereço IP da interface do serviço de borda do acesso do servidor de borda</p></td>
<td><p>Porta de comunicação de servidor para servidor padrão para XMPP. Permite a comunicação com o servidor de borda XMPP o proxy de parceiros de XMPP federado</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Endereço IP da interface do serviço de borda do acesso do servidor de borda</p></td>
<td><p>Qualquer um</p></td>
<td><p>Porta de comunicação de servidor para servidor padrão para XMPP. Permite a comunicação do proxy do servidor de borda XMPP com parceiros do XMPP federado</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>Qualquer um</p></td>
<td><p>Cada IP de interface do servidor de borda interna</p></td>
<td><p>Tráfego de XMPP interno do Gateway XMPP no servidor front-end ou do pool de front-end para o endereço IP interno do servidor de borda ou o endereço IP interno de cada membro do pool de bordas</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

