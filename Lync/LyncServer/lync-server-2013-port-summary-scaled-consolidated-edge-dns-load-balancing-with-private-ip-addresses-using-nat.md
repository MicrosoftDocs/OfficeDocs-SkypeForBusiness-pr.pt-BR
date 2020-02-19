---
title: 'Lync Server 2013: Resumo de porta-borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: a296c2af-54d4-4b4f-9795-9191baf688cb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412756(v=OCS.15)
ms:contentKeyID: 48184955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a90da0679fb48396cf3441464646a27bd2e0caa
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139202"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a>Resumo de porta-borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-12-04_

O Lync Server 2013, a funcionalidade do servidor de borda descrito nesta arquitetura de cenário é muito semelhante ao que foi implementado no Lync Server 2010. O acréscimo mais notável é a entrada **5269 over TCP** de porta para XMPP (extensible messaging and presence protocol). O Lync Server 2013 implanta opcionalmente um proxy do XMPP no servidor de borda ou no pool de borda e no servidor de gateway do XMPP no servidor front-end ou no pool de front-ends.

Além do IPv4, o servidor de borda agora oferece suporte a IPv6. Para não confundir, apenas o IPv4 é usado nos cenários.

**Rede de perímetro corporativa para borda consolidada em escala com endereços IP privados usando NAT**

![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")

<div>

## <a name="port-and-protocol-details"></a>Detalhes de Porta e Protocolo

Recomendamos abrir somente as portas necessárias para dar suporte à funcionalidade para a qual você está fornecendo acesso externo.

Para que o acesso remoto funcione para qualquer serviço de borda, é imprescindível que o tráfego SIP seja permitido bi-direcionalmente, conforme mostra a figura do tráfego de borda de entrada/saída. Dito de outra forma, as mensagens SIP de e para o serviço de Borda de Acesso está envolvido em sistemas de mensagens instantâneas (IM), presença, webconferências, áudio/vídeo (A/V) e federação.

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a>Resumo do firewall para borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT: interface externa – nó 1 e nó 2 (exemplo)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Função/Protocolo/TCP ou UDP/Porta</th>
<th>Endereço IP de origem</th>
<th>Endereço IP de destino</th>
<th>Observações</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Serviço de proxy XMPP (compartilha o endereço IP com o serviço de borda de acesso)</p></td>
<td><p>O serviço de proxy XMPP aceita tráfego de contatos XMPP em federações XMPP definidas</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Serviço de proxy XMPP (compartilha o endereço IP com o serviço de borda de acesso)</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>O serviço de proxy XMPP envia o tráfego para os contatos do XMPP em federações XMPP definidas</p></td>
</tr>
<tr class="odd">
<td><p>Access/HTTP/TCP/80</p></td>
<td><p>Serviço de borda de acesso do servidor de borda</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Revogação de certificado/verificação e recuperação CRL</p></td>
</tr>
<tr class="even">
<td><p>Access/DNS/TCP/53</p></td>
<td><p>Serviço de borda de acesso do servidor de borda</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Consulta DNS sobre TCP</p></td>
</tr>
<tr class="odd">
<td><p>Access/DNS/UDP/53</p></td>
<td><p>Serviço de borda de acesso do servidor de borda</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Consulta DNS sobre UDP</p></td>
</tr>
<tr class="even">
<td><p>/TCP/443 de acesso/SIP (TLS)</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Serviço de borda de acesso do servidor de borda</p></td>
<td><p>Tráfego SIP de cliente a servidor para acesso de usuário externo</p></td>
</tr>
<tr class="odd">
<td><p>/TCP/5061 de acesso/SIP (MTLS)</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Serviço de borda de acesso do servidor de borda</p></td>
<td><p>Para conectividade a redes públicas e federadas de IM usando SIP</p></td>
</tr>
<tr class="even">
<td><p>/TCP/5061 de acesso/SIP (MTLS)</p></td>
<td><p>Serviço de borda de acesso do servidor de borda</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Para conectividade a redes públicas e federadas de IM usando SIP</p></td>
</tr>
<tr class="odd">
<td><p>Webconferência/PSOM (TLS)/TCP/443</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Serviço de borda de Webconferência da servidor de borda</p></td>
<td><p>Mídia de webconferência</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59.999</p></td>
<td><p>Serviço de borda A/V do servidor de borda</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Necessário para federação com parceiros que executam o Office Communications Server 2007, o Office Communications Server 2007 R2, o Lync Server 2010 e o Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59.999</p></td>
<td><p>Serviço de borda A/V do servidor de borda</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Necessário somente para federação com parceiros que executam o Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59.999</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Serviço de borda A/V do servidor de borda</p></td>
<td><p>Necessário somente para federação com parceiros que executam o Office Communications Server 2007</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59.999</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Serviço de borda A/V do servidor de borda</p></td>
<td><p>Necessário somente para federação com parceiros que executam o Office Communications Server 2007</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Serviço de borda A/V do servidor de borda</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>3478 a saída é usada para determinar a versão do servidor de borda com a qual o Lync Server está se comunicando e também para o tráfego de mídia do servidor de borda servidor a borda. Necessário para federação com o Lync Server 2010, o Windows Live Messenger e o Office Communications Server 2007 R2, e também se vários pools de borda estiverem implantados em uma empresa.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Serviço de borda A/V do servidor de borda</p></td>
<td><p>Negociação de candidatos STUN/TURN através de UDP/3478</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Serviço de borda A/V do servidor de borda</p></td>
<td><p>Negociação de candidatos STUN/TURN através de TCP/443</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Serviço de borda A/V do servidor de borda</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Negociação de candidatos STUN/TURN através de TCP/443</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a>Resumo do firewall para borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT: interface interna – nó 1 e nó 2 (exemplo)

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
<th>Comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>Qualquer um (pode ser definido como endereço de servidor front-end ou endereço IP do pool de front-ends executando o serviço de gateway do XMPP)</p></td>
<td><p>Endereço IP da interface interna do servidor de borda</p></td>
<td><p>Tráfego XMPP de saída do serviço de Gateway XMPP executado no servidor front-end ou no pool de front-ends</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>Qualquer um (pode ser definido como diretor, endereço IP do pool de diretores, servidor front-end ou endereço IP do pool de front-ends)</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Tráfego SIP de saída (do diretor, endereço IP do pool de diretores, servidor front-end ou endereço IP do pool de front-ends) para a interface interna do servidor de borda</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Qualquer um (pode ser definido como diretor, endereço IP do pool de diretores, servidor front-end ou endereço IP do pool de front-ends)</p></td>
<td><p>Tráfego SIP de entrada (para diretor, endereço IP do pool de diretores, servidor front-end ou endereço IP do pool de front-ends) da interface interna do servidor de borda</p></td>
</tr>
<tr class="even">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>Qualquer um (pode ser definido como endereço IP do servidor front-end ou cada endereço IP do servidor front-end em um pool de front-ends)</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Tráfego de Webconferência do servidor front-end ou de cada servidor de front-end, se estiver em um pool, para a interface interna do servidor de borda</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>Qualquer um (pode ser definido como endereço IP do servidor front-end ou endereço IP do pool de front-ends ou qualquer aparelho de filial persistente ou servidor de filial persistente usando este servidor de borda)</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Autenticação de usuários A/V (serviço de autenticação A/V) do servidor front-end ou endereço IP do pool de front-end ou de qualquer aparelho de filial persistente ou servidor de filial persistente usando este servidor de borda</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Caminho preferencial para transferência de mídia A/V entre usuários internos e externos, aparelho de filial persistente ou servidor de filial persistente</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Caminho de fallback para transferência de mídia A/V entre usuários internos e externos, aparelho de filial persistente ou servidor de filial persistente se a comunicação UDP não puder ser estabelecida, o TCP é usado para transferência de arquivos e compartilhamento de área de trabalho</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Qualquer um (pode ser definido como o endereço IP do servidor front-end ou o pool que contém o repositório de gerenciamento central)</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Replicação de alterações do armazenamento do Gerenciamento Central para o servidor de borda</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Controle de log centralizado usando o Shell de gerenciamento do Lync Server e os cmdlets do serviço de registro em log centralizado, comandos de linha de comando do ClsController (ClsController. exe) ou de agente (ClsAgent. exe) e coleção de logs</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Controle de log centralizado usando o Shell de gerenciamento do Lync Server e os cmdlets do serviço de registro em log centralizado, comandos de linha de comando do ClsController (ClsController. exe) ou de agente (ClsAgent. exe) e coleção de logs</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Controle de log centralizado usando o Shell de gerenciamento do Lync Server e os cmdlets do serviço de registro em log centralizado, comandos de linha de comando do ClsController (ClsController. exe) ou de agente (ClsAgent. exe) e coleção de logs</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a>Resumo de firewall para federação


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Função/Protocolo/TCP ou UDP/Porta</th>
<th>Endereço IP de origem</th>
<th>Endereço IP de destino</th>
<th>Observações</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>/TCP/5061 de acesso/SIP (MTLS)</p></td>
<td><p>Endereço IP público do serviço da Borda de Acesso</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Para conectividade a redes públicas e federadas de IM usando SIP</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a>Resumo do firewall – Conectividade pública de mensagens instantâneas


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Função/Protocolo/TCP ou UDP/Porta</th>
<th>Endereço IP de origem</th>
<th>Endereço IP de destino</th>
<th>Observações</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>/TCP/5061 de acesso/SIP (MTLS)</p></td>
<td><p>Parceiros de conectividade pública de IM</p></td>
<td><p>Serviço de borda de acesso do servidor de borda</p></td>
<td><p>Para conectividade pública e federada de mensagens instantâneas usando SIP</p></td>
</tr>
<tr class="even">
<td><p>/TCP/5061 de acesso/SIP (MTLS)</p></td>
<td><p>Serviço de borda de acesso do servidor de borda</p></td>
<td><p>Parceiros de conectividade pública de IM</p></td>
<td><p>Para conectividade de IM público e federado usando SIP</p></td>
</tr>
<tr class="odd">
<td><p>/TCP/443 de acesso/SIP (TLS)</p></td>
<td><p>Clientes</p></td>
<td><p>Serviço de borda de acesso do servidor de borda</p></td>
<td><p>Tráfego SIP de cliente a servidor para acesso de usuário externo</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59.999</p></td>
<td><p>Serviço de borda A/V do servidor de borda</p></td>
<td><p>Clientes Live Messenger</p></td>
<td><p>Usado para sessões A/V com o Windows Live Messenger se a conectividade pública de IM estiver configurada.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Serviço de borda A/V do servidor de borda</p></td>
<td><p>Clientes Live Messenger</p></td>
<td><p>Necessário para conectividade de IM público com Windows Live Messenger</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Clientes Live Messenger</p></td>
<td><p>Serviço de borda A/V do servidor de borda</p></td>
<td><p>Obrigatório para conectividade pública de IM com o Windows Live Messenger</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a>Resumo de Firewall para protocolo XMPP (Extensible Messaging and Presence Protocol)


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
<th>Origem (endereço IP)</th>
<th>Destino (endereço IP)</th>
<th>Comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Endereço IP da interface de serviço de borda de acesso do servidor de borda</p></td>
<td><p>Porta padrão de comunicação entre servidores para XMPP. Permite a comunicação com o servidor de borda XMPP proxy de parceiros federados do XMPP</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Endereço IP da interface de serviço de borda de acesso do servidor de borda</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Porta padrão de comunicação entre servidores para XMPP. Permite a comunicação do proxy do servidor de borda XMPP com parceiros federados XMPP</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>Qualquer tamanho</p></td>
<td><p>Cada IP de interface de servidor de borda interna</p></td>
<td><p>Tráfego XMPP interno do Gateway XMPP no servidor front-end ou do pool de front-ends para o endereço IP interno do servidor de borda ou o endereço IP interno de cada membro do pool de borda</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

