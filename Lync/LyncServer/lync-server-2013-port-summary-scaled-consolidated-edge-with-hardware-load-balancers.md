---
title: Resumo de porta - borda consolidada em escala com balanceadores de carga de hardware
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 91213b1e-f875-464b-83e8-fe3a351595a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398739(v=OCS.15)
ms:contentKeyID: 48184841
ms.date: 04/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60250db155922999ce677248a41c3f4158aba466
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Resumo de porta - borda consolidada em escala com balanceadores de carga de hardware no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2015-04-27_

A funcionalidade do servidor de borda do Lync Server 2013 descrita nesta arquitetura de cenário é muito semelhante à implementada no Lync Server 2010. A adição mais perceptível é a porta **5269 sobre** a entrada TCP para o protocolo de mensagens extensíveis e de presença (XMPP). O Lync Server 2013, opcionalmente, implanta um proxy XMPP no servidor de borda ou no pool de periféricos e o servidor de Gateway XMPP no servidor front-end ou no pool de front-end.

Além do IPv4, o servidor de borda agora oferece suporte ao IPv6. Para fins de clareza, somente o IPv4 é usado nos cenários.

**Borda consolidada dimensionada usando o balanceamento de carga de hardware**

![Portas e protocolos de rede do perímetro do servidor de borda] (images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Portas e protocolos de rede do perímetro do servidor de borda")

<div>

## <a name="port-and-protocol-details"></a>Detalhes de protocolo e porta

É recomendável que você abra apenas as portas necessárias para dar suporte à funcionalidade para a qual você está fornecendo acesso externo.

Para que o acesso remoto funcione para qualquer serviço de borda, é obrigatório que o tráfego SIP tenha permissão de fluxo bidirecional, conforme mostrado na figura de tráfego de borda de entrada/saída. Declarado de outra maneira, o recurso de mensagens SIP para e do serviço de borda de acesso está envolvido em mensagens instantâneas (IM), presença, Web conferência, áudio/vídeo (A/V) e Federação.

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a>Resumo de firewall para borda consolidada dimensionada, carga de hardware balanceada: interface externa – nó 1 e nó 2 (exemplo)

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
<td><p>Access/HTTP/TCP/80</p></td>
<td><p>Endereço IP público do serviço de borda do acesso ao servidor de borda</p></td>
<td><p>Qualquer um</p></td>
<td><p>Revogação e verificação de revogação/revogação de certificados e recuperação</p></td>
</tr>
<tr class="even">
<td><p>Access/DNS/TCP/53</p></td>
<td><p>Endereço IP público do serviço de borda do acesso ao servidor de borda</p></td>
<td><p>Qualquer um</p></td>
<td><p>Consulta DNS via TCP</p></td>
</tr>
<tr class="odd">
<td><p>Access/DNS/UDP/53</p></td>
<td><p>Endereço IP público do serviço de borda do acesso ao servidor de borda</p></td>
<td><p>Qualquer um</p></td>
<td><p>Consulta DNS via UDP</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50.000 A 59.999</p></td>
<td><p>Endereço IP do serviço de borda do servidor de borda A/V</p></td>
<td><p>Qualquer um</p></td>
<td><p>Obrigatório para federação com parceiros que executam o Office Communications Server 2007, o Office Communications Server 2007 R2, o Lync Server 2010 e o Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59.999</p></td>
<td><p>Endereço IP público do serviço de borda do servidor de borda A/V</p></td>
<td><p>Qualquer um</p></td>
<td><p>Obrigatório somente para federação com parceiros que executam o Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50.000 A 59.999</p></td>
<td><p>Qualquer um</p></td>
<td><p>Endereço IP público do serviço de borda do servidor de borda A/V</p></td>
<td><p>Obrigatório somente para federação com parceiros que executam o Office Communications Server 2007</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59.999</p></td>
<td><p>Qualquer um</p></td>
<td><p>Endereço IP público do serviço de borda do servidor de borda A/V</p></td>
<td><p>Obrigatório somente para federação com parceiros que executam o Office Communications Server 2007</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Endereço IP público do serviço de borda do servidor de borda A/V</p></td>
<td><p>Qualquer um</p></td>
<td><p>3478 a saída é usada para determinar a versão do servidor de borda com a qual o Lync Server está se comunicando e também para o tráfego de mídia do servidor edge edge-to-edge. Obrigatório para federação com o Lync Server 2010, o Windows Live Messenger e o Office Communications Server 2007 R2 e também se vários pools de bordas forem implantados em uma empresa.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Qualquer um</p></td>
<td><p>Endereço IP público do serviço de borda do servidor de borda A/V</p></td>
<td><p>STUN/desliga a negociação de candidatos via UDP/3478</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Qualquer um</p></td>
<td><p>Endereço IP público do serviço de borda do servidor de borda A/V</p></td>
<td><p>STUN/TRANSFORMe a negociação de candidatos via TCP/443</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Endereço IP público do serviço de borda do servidor de borda A/V</p></td>
<td><p>Qualquer um</p></td>
<td><p>STUN/TRANSFORMe a negociação de candidatos via TCP/443</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a>Resumo de firewall para borda consolidada dimensionada, balanceamento de carga de hardware: nó de interface interna 1 e nó 2

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
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>Any (pode ser definido como endereço do servidor front-end ou endereço IP virtual do pool de front-end executando o serviço de gateway do XMPP)</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Tráfego de XMPP de saída do serviço de gateway do XMPP em execução em servidor front-end ou pool de front-end</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Any (pode ser definido como o IP ou pool do servidor de front-end que mantém o repositório de gerenciamento central)</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Replicação de alterações do repositório de gerenciamento central para o servidor de borda</p></td>
</tr>
<tr class="odd">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>Any (pode ser definido como IP do diretor, IP do servidor front-end ou IP virtual do pool)</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Tráfego de Webconferência da implantação interna para a interface de servidor de borda interna</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>Any (pode ser definido como IP do diretor, IP do servidor front-end ou IP virtual do pool)</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Caminho preferencial para transferência de mídia A/V entre usuários internos e externos, aparelho de ramificação sobreviventes ou servidor de ramificação sobreviventes</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Any (pode ser definido como IP do diretor, IP do servidor front-end ou IP virtual do pool)</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Caminho de fallback para transferência de mídia A/V entre usuários internos e externos, aparelho de ramificação sobreviventes ou servidor de ramificação sobreviventes se não for possível estabelecer comunicação UDP, o TCP será usado para transferência de arquivos e compartilhamento de área de trabalho</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Qualquer um</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Controlador de serviço de log centralizado usando cmdlets do Shell de gerenciamento do Lync Server e do serviço de log centralizado, comandos de linha de comando do ClsController (ClsController. exe) ou comandos do agente (ClsAgent. exe) e a coleção de logs</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Qualquer um</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Controlador de serviço de log centralizado usando cmdlets do Shell de gerenciamento do Lync Server e do serviço de log centralizado, comandos de linha de comando do ClsController (ClsController. exe) ou comandos do agente (ClsAgent. exe) e a coleção de logs</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Qualquer um</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Controlador de serviço de log centralizado usando cmdlets do Shell de gerenciamento do Lync Server e do serviço de log centralizado, comandos de linha de comando do ClsController (ClsController. exe) ou comandos do agente (ClsAgent. exe) e a coleção de logs</p></td>
</tr>
</tbody>
</table>


Os balanceadores de carga de hardware têm requisitos específicos quando implantados para fornecer disponibilidade e balanceamento de carga do Lync Server. Os requisitos são definidos na figura e nas tabelas a seguir. Fornecedores de terceiros podem usar terminologia diferente para os requisitos definidos aqui. Será necessário mapear os requisitos do Lync Server para os recursos e as opções de configuração fornecidas pelo fornecedor do balanceador de carga de hardware.

Ao configurar balanceadores de carga de hardware, considere os seguintes requisitos:

  - A conversão de endereços de rede de origem (SNAT) pode ser configurada no balanceamento de carga de hardware (HLB) para serviço de borda de acesso e serviço de borda de conferência Web

  - O SNAT não pode ser configurado no serviço de borda A/V – o serviço de borda A/V deve responder com o endereço do servidor real, e não com o IP virtual (VIP) do HLB, para fazer uma simples passagem do UDP sobre NAT (STUN)/Traversal usando o NAT de retransmissão (ativar)/Federation TURN (FTURN) para funcionar corretamente
    
      - Se o cliente envia uma solicitação para o HLB, a resposta deve retornar do VIP HLB
    
      - Se o cliente envia uma solicitação para a borda, a resposta deve retornar do IP de borda

  - Os endereços IP públicos são usados em cada interface do servidor e nos VIPs do HLB, e as suas necessidades de endereço IP público são N + 1, onde há um endereço IP público para cada interface do servidor real e outra para cada VIP HLB. Onde você tem dois servidores de borda no pool, isso resulta em 9 endereços IP públicos, em que 3 são usados para VIPs HLB e um para cada interface do servidor de borda (um total de seis para os servidores)

  - Para o serviço de borda de acesso e o serviço de borda de Webconferência (e usar NAT no HLB) o cliente entra em contato com o VIP, o VIP altera o endereço IP de origem do cliente para seu próprio endereço IP. A interface do servidor endereça o endereço do remetente ao VIP, o VIP altera o endereço de origem do endereço IP da interface do servidor e envia o pacote para o cliente

  - Para o serviço de borda a/V, o VIP não deve alterar o endereço IP de origem e o endereço do servidor real é retornado ao cliente diretamente – você não pode configurar o NAT no HLB para tráfego de AV
    
      - Se o cliente envia uma solicitação para o VIP HLB, a resposta deve retornar do VIP HLB
    
      - Se o cliente envia uma solicitação ao IP de borda, a resposta deve retornar do IP de borda

  - Para o AV, o firewall externo manterá o endereço IP público do real Server para todos os pacotes

  - Depois de estabelecida, o cliente para a comunicação do serviço de borda a/V se destina ao real Server, não ao HLB

  - A borda interna para servidores internos e clientes devem ser roteadas, e as rotas persistentes são definidas para todas as redes internas que hospedam servidores ou clientes

  - O serviço de borda de acesso do HLB funcionará como o gateway padrão para cada interface do servidor de borda

<div>


> [!NOTE]
> Para obter mais informações sobre o planejamento e a funcionalidade do NAT, consulte <A href="lync-server-2013-hardware-load-balancer-requirements.md">requisitos do balanceador de carga de hardware para o Lync Server 2013</A>.



</div>

![Detalhes de portas e protocolos do servidor de borda] (images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Detalhes de portas e protocolos do servidor de borda")

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a>Configurações de porta externa necessárias para borda consolidada dimensionada, carga de hardware balanceada: IPs virtuais de interface externa

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
<td><p>XMPP/TCP/5269</p></td>
<td><p>Serviço de proxy XMPP (compartilha o endereço IP com o serviço de borda de acesso)</p></td>
<td><p>Qualquer um</p></td>
<td><p>O serviço de proxy XMPP envia o tráfego para os contatos do XMPP em federações XMPP definidas</p></td>
</tr>
<tr class="odd">
<td><p>/TCP/443 de acesso/SIP (TLS)</p></td>
<td><p>Qualquer um</p></td>
<td><p>Endereço VIP público do serviço de borda do Access</p></td>
<td><p>Tráfego SIP de cliente para servidor para acesso de usuário externo</p></td>
</tr>
<tr class="even">
<td><p>/TCP/5061 de acesso/SIP (MTLS)</p></td>
<td><p>Qualquer um</p></td>
<td><p>Endereço VIP público do serviço de borda do Access</p></td>
<td><p>Sinalização SIP, conectividade de mensagens de chat públicas e federadas usando o SIP</p></td>
</tr>
<tr class="odd">
<td><p>/TCP/5061 de acesso/SIP (MTLS)</p></td>
<td><p>Endereço VIP público do serviço de borda do Access</p></td>
<td><p>Parceiro federado</p></td>
<td><p>Sinalização SIP, conectividade de mensagens de chat públicas e federadas usando o SIP</p></td>
</tr>
<tr class="even">
<td><p>Web Conferencing/PSOM (TLS)/TCP/443</p></td>
<td><p>Qualquer um</p></td>
<td><p>Endereço VIP público do serviço de borda de Webconferência da Web Edge</p></td>
<td><p>Mídia de Webconferência</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Qualquer um</p></td>
<td><p>Endereço VIP público do serviço Edge Server A/V</p></td>
<td><p>STUN/desliga a negociação de candidatos via UDP/3478</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Qualquer um</p></td>
<td><p>Endereço VIP público do serviço Edge Server A/V</p></td>
<td><p>STUN/TRANSFORMe a negociação de candidatos via TCP/443</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a>Resumo de firewall para borda consolidada em escala, balanceamento de carga de hardware: interface interna IPs virtual

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
<td><p>Any (pode ser definido como director, endereço IP virtual do pool do diretor, servidor front-end ou endereço IP virtual do pool de front-end)</p></td>
<td><p>Interface VIP interna do servidor de borda</p></td>
<td><p>Tráfego SIP de saída (do diretor, endereço IP virtual do pool diretor, servidor front-end ou endereço IP virtual do pool de front-end) para VIP de borda interna</p></td>
</tr>
<tr class="even">
<td><p>/TCP/5061 de acesso/SIP (MTLS)</p></td>
<td><p>Interface VIP interna do servidor de borda</p></td>
<td><p>Any (pode ser definido como director, endereço IP virtual do pool do diretor, servidor front-end ou endereço IP virtual do pool de front-end)</p></td>
<td><p>Tráfego SIP de entrada (para o director, endereço IP virtual do pool diretor, servidor front-end ou endereço IP virtual do pool de front-end) da interface interna do servidor de borda</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>Any (pode ser definido como endereço IP do servidor front-end ou endereço IP do pool de front-end ou qualquer aparelho de ramificação sobreviventes ou servidor de ramificação sobreviventes que use este servidor de borda)</p></td>
<td><p>Interface VIP interna do servidor de borda</p></td>
<td><p>Autenticação de usuários de A/V (serviço de autenticação A/V) do servidor front-end ou do endereço IP do pool de front-end ou qualquer aparelho de ramificação sobreviventes ou servidor de ramificação sobreviventes que use este servidor de borda</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>Qualquer um</p></td>
<td><p>Interface VIP interna do servidor de borda</p></td>
<td><p>Caminho preferencial para transferência de mídia A/V entre usuários internos e externos</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Qualquer um</p></td>
<td><p>Interface VIP interna do servidor de borda</p></td>
<td><p>Caminho de fallback para transferência de mídia A/V entre usuários internos e externos se não for possível estabelecer a comunicação UDP, o TCP será usado para transferência de arquivos e compartilhamento de área de trabalho</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Interface VIP interna do servidor de borda</p></td>
<td><p>Qualquer um</p></td>
<td><p>Caminho de fallback para transferência de mídia A/V entre usuários internos e externos se não for possível estabelecer a comunicação UDP, o TCP será usado para transferência de arquivos e compartilhamento de área de trabalho</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

