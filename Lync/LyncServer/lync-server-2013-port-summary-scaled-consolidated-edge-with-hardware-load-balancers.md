---
title: Resumo de porta-borda consolidada em escala com balanceadores de carga de hardware
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 91213b1e-f875-464b-83e8-fe3a351595a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398739(v=OCS.15)
ms:contentKeyID: 48184841
ms.date: 04/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc4a56edb79d2eff52bf0d234aedcee1b3cdced4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534108"
---
# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Resumo de porta-borda consolidada em escala com balanceadores de carga de hardware no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2015-04-27_

O Lync Server 2013, a funcionalidade do servidor de borda descrito nesta arquitetura de cenário é muito semelhante ao que foi implementado no Lync Server 2010. O acréscimo mais notável é a entrada **5269 over TCP** de porta para XMPP (extensible messaging and presence protocol). O Lync Server 2013 implanta opcionalmente um proxy do XMPP no servidor de borda ou no pool de borda e no servidor de gateway do XMPP no servidor front-end ou no pool de front-ends.

Além do IPv4, o servidor de borda agora oferece suporte a IPv6. Para não confundir, apenas o IPv4 é usado nos cenários.

**Borda consolidada dimensionada usando o balanceamento de carga de hardware**

![Portas e protocolos de rede de perímetro do servidor de borda](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Portas e protocolos de rede de perímetro do servidor de borda")

<div>

## <a name="port-and-protocol-details"></a>Detalhes de Porta e Protocolo

Recomendamos abrir somente as portas necessárias para dar suporte à funcionalidade para a qual você está fornecendo acesso externo.

Para que o acesso remoto funcione para qualquer serviço de borda, é imprescindível que o tráfego SIP seja permitido bi-direcionalmente, conforme mostra a figura do tráfego de borda de entrada/saída. Dito de outra forma, as mensagens SIP de e para o serviço de Borda de Acesso está envolvido em sistemas de mensagens instantâneas (IM), presença, webconferências, áudio/vídeo (A/V) e federação.

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a>Resumo do firewall para borda consolidada em escala, balanceamento de carga de hardware: interface externa – nó 1 e nó 2 (exemplo)

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
<td><p>Access/HTTP/TCP/80</p></td>
<td><p>Endereço IP público do serviço de borda de acesso do servidor de borda</p></td>
<td><p>Qualquer</p></td>
<td><p>Revogação de certificado/verificação e recuperação CRL</p></td>
</tr>
<tr class="even">
<td><p>Access/DNS/TCP/53</p></td>
<td><p>Endereço IP público do serviço de borda de acesso do servidor de borda</p></td>
<td><p>Qualquer</p></td>
<td><p>Consulta DNS sobre TCP</p></td>
</tr>
<tr class="odd">
<td><p>Access/DNS/UDP/53</p></td>
<td><p>Endereço IP público do serviço de borda de acesso do servidor de borda</p></td>
<td><p>Qualquer</p></td>
<td><p>Consulta DNS sobre UDP</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59.999</p></td>
<td><p>Endereço IP do serviço de borda de A/V do servidor de borda</p></td>
<td><p>Qualquer</p></td>
<td><p>Necessário para federação com parceiros que executam o Office Communications Server 2007, o Office Communications Server 2007 R2, o Lync Server 2010 e o Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59.999</p></td>
<td><p>Endereço IP público do serviço de borda A/V do servidor de borda</p></td>
<td><p>Qualquer</p></td>
<td><p>Necessário somente para federação com parceiros que executam o Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59.999</p></td>
<td><p>Qualquer</p></td>
<td><p>Endereço IP público do serviço de borda A/V do servidor de borda</p></td>
<td><p>Necessário somente para federação com parceiros que executam o Office Communications Server 2007</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59.999</p></td>
<td><p>Qualquer</p></td>
<td><p>Endereço IP público do serviço de borda A/V do servidor de borda</p></td>
<td><p>Necessário somente para federação com parceiros que executam o Office Communications Server 2007</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Endereço IP público do serviço de borda A/V do servidor de borda</p></td>
<td><p>Qualquer</p></td>
<td><p>3478 a saída é usada para determinar a versão do servidor de borda com a qual o Lync Server está se comunicando e também para o tráfego de mídia do servidor de borda servidor a borda. Necessário para federação com o Lync Server 2010, o Windows Live Messenger e o Office Communications Server 2007 R2, e também se vários pools de borda estiverem implantados em uma empresa.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Qualquer</p></td>
<td><p>Endereço IP público do serviço de borda A/V do servidor de borda</p></td>
<td><p>Negociação de candidatos STUN/TURN através de UDP/3478</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Qualquer</p></td>
<td><p>Endereço IP público do serviço de borda A/V do servidor de borda</p></td>
<td><p>Negociação de candidatos STUN/TURN através de TCP/443</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Endereço IP público do serviço de borda A/V do servidor de borda</p></td>
<td><p>Qualquer</p></td>
<td><p>Negociação de candidatos STUN/TURN através de TCP/443</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a>Resumo do firewall para borda consolidada em escala, balanceamento de carga de hardware: nó de interface interna 1 e nó 2

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
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>Qualquer um (pode ser definido como endereço de servidor front-end ou endereço IP virtual do pool de front-ends executando o serviço de gateway do XMPP)</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Tráfego XMPP de saída do serviço de Gateway XMPP executado no servidor front-end ou no pool de front-ends</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Qualquer um (pode ser definido como o IP ou pool do servidor de front-end que mantém o repositório de gerenciamento central)</p></td>
<td><p>Interface Interna dos Servidores de Borda</p></td>
<td><p>Replicação de alterações do armazenamento do Gerenciamento Central para o servidor de borda</p></td>
</tr>
<tr class="odd">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>Qualquer um (pode ser definido como IP de diretor, IP do servidor front-end ou IP virtual do pool)</p></td>
<td><p>Interface Interna dos Servidores de Borda</p></td>
<td><p>Tráfego de Webconferência da implantação interna para interface de servidor de borda interno</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>Qualquer um (pode ser definido como IP de diretor, IP do servidor front-end ou IP virtual do pool)</p></td>
<td><p>Interface Interna dos Servidores de Borda</p></td>
<td><p>Caminho preferencial para transferência de mídia A/V entre usuários internos e externos, aparelho de filial persistente ou servidor de filial persistente</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Qualquer um (pode ser definido como IP de diretor, IP do servidor front-end ou IP virtual do pool)</p></td>
<td><p>Interface Interna dos Servidores de Borda</p></td>
<td><p>Caminho de fallback para transferência de mídia A/V entre usuários internos e externos, aparelho de filial persistente ou servidor de filial persistente se a comunicação UDP não puder ser estabelecida, o TCP é usado para transferência de arquivos e compartilhamento de área de trabalho</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Qualquer</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Controle de log centralizado usando o Shell de gerenciamento do Lync Server e os cmdlets do serviço de registro em log centralizado, comandos de linha de comando do ClsController (ClsController.exe) ou de agente (ClsAgent.exe) e coleção de logs</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Qualquer</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Controle de log centralizado usando o Shell de gerenciamento do Lync Server e os cmdlets do serviço de registro em log centralizado, comandos de linha de comando do ClsController (ClsController.exe) ou de agente (ClsAgent.exe) e coleção de logs</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Qualquer</p></td>
<td><p>Interface interna do servidor de borda</p></td>
<td><p>Controle de log centralizado usando o Shell de gerenciamento do Lync Server e os cmdlets do serviço de registro em log centralizado, comandos de linha de comando do ClsController (ClsController.exe) ou de agente (ClsAgent.exe) e coleção de logs</p></td>
</tr>
</tbody>
</table>


Os balanceadores de carga de hardware têm requisitos específicos quando implantados para fornecer disponibilidade e balanceamento de carga para o Lync Server. Os requisitos são definidos na figura e tabelas a seguir. Fornecedores terceirizados podem usar terminologia diferente para os requisitos definidos aqui. Será necessário mapear os requisitos do Lync Server para os recursos e opções de configuração fornecidos pelo fornecedor do balanceador de carga de hardware.

Ao configurar balanceadores de carga de hardware, considere os seguintes requisitos:

  - A conversão de endereço de rede de origem (SNAT) pode ser configurada no balanceador de carga de hardware (HLB) para serviço de borda de acesso e serviço de borda de Webconferência

  - O SNAT não pode ser configurado no serviço de borda A/V – o serviço de borda A/V deve responder com o endereço do servidor real, e não o VIP (IP virtual) do HLB, para a passagem simples de UDP sobre NAT (STUN)/Traversal usando o NAT de retransmissão (ativar)/Federation TURN (FTURN) para funcionar corretamente
    
      - Se o cliente envia uma solicitação para o HLB, a resposta deve retornar do VIP HLB
    
      - Se o cliente envia uma solicitação para a borda, a resposta deve retornar do IP de borda

  - Os endereços IP públicos são usados em cada interface de servidor e nos VIPs do HLB, e seus requisitos de endereço IP público são N + 1, onde há um endereço IP público para cada interface de servidor real e um para cada VIP do HLB. Onde você tem dois servidores de borda no pool, isso resulta em 9 endereços IP públicos, onde 3 são usados para os VIPs HLB e um para cada interface de servidor de borda (um total de seis para os servidores)

  - Para o serviço de borda de acesso e serviço de borda de webconferência, (e usando NAT no HLB) o cliente contata o VIP, o VIP altera o endereço IP de origem do cliente para seu próprio endereço IP. A interface do servidor resolve o endereço de retorno para o VIP, o VIP altera o endereço de origem do endereço IP da interface do servidor e envia o pacote para o cliente

  - Para o serviço de borda A/V, o VIP não deve alterar o endereço IP de origem e o endereço do servidor real é retornado ao cliente diretamente – você não pode configurar o NAT no HLB para tráfego AV
    
      - Se o cliente envia uma solicitação para o VIP HLB, a resposta deve retornar do VIP HLB
    
      - Se o cliente envia uma solicitação para o IP de borda, a resposta deve retornar do IP de borda

  - Para o AV, o firewall externo manterá o endereço IP público do real Server para todos os pacotes

  - Depois de estabelecida, o cliente para a comunicação do serviço de borda a/V é para o servidor real, não para o HLB

  - A borda interna para servidores internos e clientes devem ser roteadas, e as rotas persistentes são definidas para todas as redes internas que hospedam servidores ou clientes

  - O VIP do serviço de borda de acesso do HLB atuará como o gateway padrão para cada interface de servidor de borda

<div>


> [!NOTE]
> Para obter mais informações sobre planejamento e funcionalidade de NAT, consulte <A href="lync-server-2013-hardware-load-balancer-requirements.md">requisitos do balanceador de carga de hardware para o Lync Server 2013</A>.



</div>

![Detalhes de portas e protocolos do servidor de borda](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Detalhes de portas e protocolos do servidor de borda")

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a>Configurações de porta externa necessárias para borda consolidada em escala, balanceamento de carga de hardware: IPs virtuais de interface externa

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
<td><p>Qualquer</p></td>
<td><p>Serviço de proxy XMPP (compartilha o endereço IP com o serviço de borda de acesso)</p></td>
<td><p>O serviço de proxy XMPP aceita tráfego de contatos XMPP em federações XMPP definidas</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Serviço de proxy XMPP (compartilha o endereço IP com o serviço de borda de acesso)</p></td>
<td><p>Qualquer</p></td>
<td><p>O serviço de proxy XMPP envia o tráfego para os contatos do XMPP em federações XMPP definidas</p></td>
</tr>
<tr class="odd">
<td><p>/TCP/443 de acesso/SIP (TLS)</p></td>
<td><p>Qualquer</p></td>
<td><p>Endereço VIP público do serviço de borda de acesso</p></td>
<td><p>Tráfego SIP de cliente a servidor para acesso de usuário externo</p></td>
</tr>
<tr class="even">
<td><p>/TCP/5061 de acesso/SIP (MTLS)</p></td>
<td><p>Qualquer</p></td>
<td><p>Endereço VIP público do serviço de borda de acesso</p></td>
<td><p>Sinalização SIP, conectividade de IM pública e federada usando SIP</p></td>
</tr>
<tr class="odd">
<td><p>/TCP/5061 de acesso/SIP (MTLS)</p></td>
<td><p>Endereço VIP público do serviço de borda de acesso</p></td>
<td><p>Parceiro federado</p></td>
<td><p>Sinalização SIP, conectividade de IM pública e federada usando SIP</p></td>
</tr>
<tr class="even">
<td><p>Webconferência/PSOM (TLS)/TCP/443</p></td>
<td><p>Qualquer</p></td>
<td><p>Endereço VIP público do serviço de borda de Webconferência do servidor de borda</p></td>
<td><p>Mídia de webconferência</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Qualquer</p></td>
<td><p>Endereço VIP público do serviço de borda A/V do servidor de borda</p></td>
<td><p>Negociação de candidatos STUN/TURN através de UDP/3478</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Qualquer</p></td>
<td><p>Endereço VIP público do serviço de borda A/V do servidor de borda</p></td>
<td><p>Negociação de candidatos STUN/TURN através de TCP/443</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a>Resumo do firewall para borda consolidada em escala, balanceamento de carga de hardware: IPs virtuais de interface interna

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
<td><p>Qualquer um (pode ser definido como diretor, endereço IP virtual do pool de diretores, servidor front-end ou endereço IP virtual do pool de front-end)</p></td>
<td><p>Interface VIP interna do servidor de borda</p></td>
<td><p>Tráfego SIP de saída (do diretor, endereço IP virtual do pool de diretores, servidor front-end ou endereço IP virtual do pool de front-ends) para VIP de borda interna</p></td>
</tr>
<tr class="even">
<td><p>/TCP/5061 de acesso/SIP (MTLS)</p></td>
<td><p>Interface VIP interna do servidor de borda</p></td>
<td><p>Qualquer um (pode ser definido como diretor, endereço IP virtual do pool de diretores, servidor front-end ou endereço IP virtual do pool de front-end)</p></td>
<td><p>Tráfego SIP de entrada (para diretor, endereço IP virtual do pool de diretores, servidor front-end ou endereço IP virtual do pool de front-ends) da interface interna do servidor de borda</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>Qualquer um (pode ser definido como endereço IP do servidor front-end ou endereço IP do pool de front-ends ou qualquer aparelho de filial persistente ou servidor de filial persistente usando este servidor de borda)</p></td>
<td><p>Interface VIP interna do servidor de borda</p></td>
<td><p>Autenticação de usuários A/V (serviço de autenticação A/V) do servidor front-end ou endereço IP do pool de front-end ou de qualquer aparelho de filial persistente ou servidor de filial persistente usando este servidor de borda</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>Qualquer</p></td>
<td><p>Interface VIP interna do servidor de borda</p></td>
<td><p>Caminho preferencial para transferência de mídia A/V entre usuários internos e externos (UDP)</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Qualquer</p></td>
<td><p>Interface VIP interna do servidor de borda</p></td>
<td><p>Caminho de fallback para transferência de mídia A/V entre usuários internos e externos, se a comunicação UDP não pode ser estabelecida, TCP é usado para transferência de arquivos e compartilhamento de área de trabalho</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Interface VIP interna do servidor de borda</p></td>
<td><p>Qualquer</p></td>
<td><p>Caminho de fallback para transferência de mídia A/V entre usuários internos e externos, se a comunicação UDP não pode ser estabelecida, TCP é usado para transferência de arquivos e compartilhamento de área de trabalho</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

