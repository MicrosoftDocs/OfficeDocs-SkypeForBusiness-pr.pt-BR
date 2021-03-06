﻿---
title: "Lync Server 2013: Res. de porta - borda cons. em esc. c/ balanc. de carga de hardware"
TOCTitle: Resumo de porta - borda consolidada em escala com balanceadores de carga de hardware
ms:assetid: 91213b1e-f875-464b-83e8-fe3a351595a4
ms:mtpsurl: https://technet.microsoft.com/pt-br/library/Gg398739(v=OCS.15)
ms:contentKeyID: 49307449
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Resumo de porta - borda consolidada em escala com balanceadores de carga de hardware no Lync Server 2013

 

_**Tópico modificado em:** 2015-04-27_

A funcionalidade do Servidor de Borda do Lync Server 2013 descrita nesta arquitetura de cenário é muito parecida com a que foi implantada no Lync Server 2010. O acréscimo mais notável é a entrada **5269 sobre TCP** de porta para XMPP (extensible messaging and presence protocol). O Lync Server 2013 implanta opcionalmente um proxy XMPP no Servidor de Borda ou Pool de borda e o servidor de gateway XMPP no Servidor Front-End ou Pool de Front-Ends.

Além do IPv4, o Servidor de Borda agora tem suporte para IPv6. Para não confundir, apenas o IPv4 é usado nos cenários.

**Borda consolidada em escala com balanceamento de carga de hardware**

![Portas e protocolos de Rede de Perímetro do Servidor de Borda](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Portas e protocolos de Rede de Perímetro do Servidor de Borda")

## Detalhes de protocolo e porta

Recomenda-se abrir apenas as portas necessárias para dar suporte à funcionalidade para a qual você está fornecendo acesso externo.

Para que o acesso remoto funcione para qualquer serviço de borda, é imprescindível que o tráfego SIP seja permitido bidirecionalmente, conforme mostra a figura do tráfego de borda de entrada/saída. Dito de outra forma, o sistema de mensagens SIP de e para o Serviço de Borda de Acesso envolve sistemas de mensagens instantâneas (IM), presença, webconferências, áudio/vídeo (A/V) e federação.

### Resumo do firewall para borda consolidada em escala com balanceamento de carga do hardware: interface externa - nó 1 e nó 2 (exemplo)

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
<th>Endereço IP de Origem</th>
<th>Endereço IP de Destino</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Acesso/HTTP/TCP/80</p></td>
<td><p>Endereço IP público do Servidor de Borda Serviço de Borda de Acesso</p></td>
<td><p>Qualquer um</p></td>
<td><p>Revocação de certificado/verificação e recuperação CRL</p></td>
</tr>
<tr class="even">
<td><p>Acesso/DNS/TCP/53</p></td>
<td><p>Endereço IP público do Servidor de Borda Serviço de Borda de Acesso</p></td>
<td><p>Qualquer um</p></td>
<td><p>Consulta DNS sobre TCP</p></td>
</tr>
<tr class="odd">
<td><p>Acesso/DNS/UDP/53</p></td>
<td><p>Endereço IP público do Servidor de Borda Serviço de Borda de Acesso</p></td>
<td><p>Qualquer um</p></td>
<td><p>Consulta DNS sobre UDP</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50.000-59.999</p></td>
<td><p>Endereço IP do Servidor de Borda  Serviço de Borda A/V</p></td>
<td><p>Qualquer um</p></td>
<td><p>Necessário para federar com parceiros que executem o Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 e Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50.000-59.999</p></td>
<td><p>Endereço IP público do Servidor de Borda  Serviço de Borda A/V</p></td>
<td><p>Qualquer um</p></td>
<td><p>Necessário somente para federação com parceiros que estejam executando o Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50.000-59.999</p></td>
<td><p>Qualquer um</p></td>
<td><p>Endereço IP público do Servidor de Borda  Serviço de Borda A/V</p></td>
<td><p>Necessário somente para federação com parceiros que estejam executando o Office Communications Server 2007</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50.000-59.999</p></td>
<td><p>Qualquer um</p></td>
<td><p>Endereço IP público do Servidor de Borda  Serviço de Borda A/V</p></td>
<td><p>Necessário somente para federação com parceiros que estejam executando o Office Communications Server 2007</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN,MSTURN/UDP/3478</p></td>
<td><p>Endereço IP público do Servidor de Borda  Serviço de Borda A/V</p></td>
<td><p>Qualquer um</p></td>
<td><p>A saída 3478 é usada para determinar a versão do Servidor de Borda com que o Lync Server está se comunicando e também para tráfego de mídia de Servidor de Borda a Servidor de Borda. Necessária para federação com Lync Server 2010, Windows Live Messenger e Office Communications Server 2007 R2, necessária também se diversos Pools de borda forem implantados em uma empresa.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN,MSTURN/UDP/3478</p></td>
<td><p>Qualquer um</p></td>
<td><p>Endereço IP público do Servidor de Borda  Serviço de Borda A/V</p></td>
<td><p>Negociação de candidatos STUN/TURN através de UDP/3478</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN,MSTURN/TCP/443</p></td>
<td><p>Qualquer um</p></td>
<td><p>Endereço IP público do Servidor de Borda  Serviço de Borda A/V</p></td>
<td><p>Negociação de candidatos STUN/TURN através de TCP/443</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN,MSTURN/TCP/443</p></td>
<td><p>Endereço IP público do Servidor de Borda  Serviço de Borda A/V</p></td>
<td><p>Qualquer um</p></td>
<td><p>Negociação de candidatos STUN/TURN através de TCP/443</p></td>
</tr>
</tbody>
</table>


### Resumo do firewall para borda consolidada em escala com balanceamento de carga do hardware: interface interna - nó 1 e nó 2

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
<th>Endereço IP de Origem</th>
<th>Endereço IP de Destino</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>Qualquer (pode ser definido como endereço do Servidor Front-End ou como IP virtual do Pool de Front-Ends executando o serviço de gateway XMPP)</p></td>
<td><p>Interface interna do Servidor de Borda</p></td>
<td><p>Tráfego XMPP de saída do serviço de gateway XMPP sendo executado no Servidor Front-End ou Pool de Front-Ends</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Qualquer um (pode ser definido como o IP ou pool do servidor do Servidor Front-End que contém o Repositório de Gerenciamento Central)</p></td>
<td><p>Interface interna do Servidor de Borda</p></td>
<td><p>Replicação de alterações do Repositório de Gerenciamento Central para o Servidor de Borda</p></td>
</tr>
<tr class="odd">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>Qualquer um (pode ser definido como IP do Diretor, IP do Servidor Front-End ou IP virtual de pool)</p></td>
<td><p>Interface interna do Servidor de Borda</p></td>
<td><p>Tráfego de Webconferência da implantação interna para interface de Servidor de Borda</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>Qualquer um (pode ser definido como IP do Diretor, IP do Servidor Front-End ou IP virtual de pool)</p></td>
<td><p>Interface interna do Servidor de Borda</p></td>
<td><p>Caminho preferencial para transferência de mídia A/V entre usuários internos e externos, Aparelho de Filial Persistente ou Servidor de Filial Persistente</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Qualquer um (pode ser definido como IP do Diretor, IP do Servidor Front-End ou IP virtual de pool)</p></td>
<td><p>Interface interna do Servidor de Borda</p></td>
<td><p>Caminho de fallback para transferência de mídia A/V entre usuários internos e externos, Aparelho de Filial Persistente ou Servidor de Filial Persistente; se a comunicação UDP não pode ser estabelecida, TCP é usado para transferência de arquivos e compartilhamento de área de trabalho</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Qualquer um</p></td>
<td><p>Interface interna do Servidor de Borda</p></td>
<td><p>Controlador Serviço de Log Centralizado usando cmdlets Shell de Gerenciamento do Lync Server e Serviço de Log Centralizado, linha de comando ClsController (ClsController.exe) ou comandos e conjunto de log do agente (ClsAgent.exe)</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Qualquer um</p></td>
<td><p>Interface interna do Servidor de Borda</p></td>
<td><p>Controlador Serviço de Log Centralizado usando cmdlets Shell de Gerenciamento do Lync Server e Serviço de Log Centralizado, linha de comando ClsController (ClsController.exe) ou comandos e conjunto de log do agente (ClsAgent.exe)</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Qualquer um</p></td>
<td><p>Interface interna do Servidor de Borda</p></td>
<td><p>Controlador Serviço de Log Centralizado usando cmdlets Shell de Gerenciamento do Lync Server e Serviço de Log Centralizado, linha de comando ClsController (ClsController.exe) ou comandos e conjunto de log do agente (ClsAgent.exe)</p></td>
</tr>
</tbody>
</table>


Os balanceadores de carga de hardware têm requisitos específicos quando implantados para fornecer disponibilidade e balanceamento de carga para Lync Server. Os requisitos são definidos na figura e tabelas a seguir. Fornecedores terceirizados podem usar uma terminologia diferente dos requisitos definidos aqui. Será necessário mapear os requisitos do Lync Server para os recursos e opções de configuração fornecidas por seu fornecedor de balanceadores de carga de hardware.

Ao configurar os balanceadores de carga de hardware, considere os requisitos a seguir:

  - A Conversão de endereço de rede de origem (SNAT) pode ser configurada no balanceadores de carga de hardware (HLB) para Serviço de Borda de Acesso e Serviço de Borda de Webconferência

  - A SNAT não pode ser configurada no Serviço de Borda A/V- o Serviço de Borda A/V deve responder com o endereço do servidor real, não o IP virtual do HLB (VIP) para percurso simples de UDP sobre NAT (STUN)/percurso usando relé NAT (TURN)/federação TURN (FTURN) para funcionar corretamente

  - Os endereços públicos de IP são usados em cada interface de servidor e nos VIPs do HLB, e seus requisitos de endereço IP público são N+1, onde há um endereço IP público para cada interface de servidor real e um para cada VIP do HLB. Quando você tiver 2 servidores de borda no pool, o resultado será 9 endereços IP públicos, onde 3 são usados para os VIPs do HLB, um para cada interface de servidor de borda (um total de seis para os servidores)

  - No Serviço de Borda de Acesso e Serviço de Borda de Webconferência, (e usando NAT no HLB) o cliente entra em contato com o VIP, o VIP altera o endereço IP de origem do cliente para seu próprio endereço IP. A interface de servidor endereça o endereço de retorno para o VIP, o VIP altera o endereço de origem do endereço IP da interface do servidor e envia o pacote ao cliente

  - No Serviço de Borda A/V, o VIP NÃO deve alterar o endereço IP de origem, e o endereço de servidor real é retornado para o cliente diretamente - você não pode configurar NAT no HLB para tráfego AV

  - Para AV, o firewall externo reterá o endereço IP público do servidor real para todos os pacotes

  - Uma vez estabelecido, cliente para comunicação do Serviço de Borda A/V será para o servidor real, não o HLB

  - Borda interna para servidores e clientes internos devem ser roteados, e rotas persistentes são definidas para todas as redes internas que hospedam servidores ou clientes

  - O VIP do Serviço de Borda de Acesso do HLB agirá como gateway padrão de cada interface de servidor de borda

![Detalhes das portas do Servidor de Borda e dos protocolos](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Detalhes das portas do Servidor de Borda e dos protocolos")

### Configurações de porta interna do firewall necessárias para a Topologia de Borda Consolidada em Escala: IPs virtuais da interface externa

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
<th>Endereço IP de Origem</th>
<th>Endereço IP de Destino</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Qualquer um</p></td>
<td><p>Serviço de proxy XMPP (compartilha IP com Serviço de Borda de Acesso)</p></td>
<td><p>O serviço de proxy XMPP aceita tráfego de contatos XMPP em federações XMPP definidas</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Serviço de proxy XMPP (compartilha IP com Serviço de Borda de Acesso)</p></td>
<td><p>Qualquer um</p></td>
<td><p>O serviço de proxy XMPP envia tráfego a contatos XMPP em federações XMPP definidas</p></td>
</tr>
<tr class="odd">
<td><p>Acesso/SIP(TLS)/TCP/443</p></td>
<td><p>Qualquer um</p></td>
<td><p>Endereço VIP público do Serviço de Borda de Acesso</p></td>
<td><p>Tráfego SIP do cliente para o servidor para acesso de usuário externo</p></td>
</tr>
<tr class="even">
<td><p>Acesso/SIP(MTLS)/TCP/5061</p></td>
<td><p>Qualquer um</p></td>
<td><p>Endereço VIP público do Serviço de Borda de Acesso</p></td>
<td><p>Sinalização SIP, conectividade federada e de IM público usando SIP</p></td>
</tr>
<tr class="odd">
<td><p>Acesso/SIP(MTLS)/TCP/5061</p></td>
<td><p>Endereço VIP público do Serviço de Borda de Acesso</p></td>
<td><p>Parceiro federado</p></td>
<td><p>Sinalização SIP, conectividade federada e de IM público usando SIP</p></td>
</tr>
<tr class="even">
<td><p>Webconferência/PSOM (TLS)/TCP/443</p></td>
<td><p>Qualquer um</p></td>
<td><p>Endereço VIP público do Servidor de Borda  Serviço de Borda de Webconferência</p></td>
<td><p>Mídia da webconferência</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN,MSTURN/UDP/3478</p></td>
<td><p>Qualquer um</p></td>
<td><p>Endereço VIP público do Servidor de Borda Serviço de Borda A/V</p></td>
<td><p>Negociação de candidatos STUN/TURN através de UDP/3478</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN,MSTURN/TCP/443</p></td>
<td><p>Qualquer um</p></td>
<td><p>Endereço VIP público do Servidor de Borda Serviço de Borda A/V</p></td>
<td><p>Negociação de candidatos STUN/TURN através de TCP/443</p></td>
</tr>
</tbody>
</table>


### Configurações de porta interna do firewall necessárias para a Topologia de Borda Consolidada em Escala, Carga de Hardware Balanceada: IPs virtuais da interface interna

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
<th>Endereço IP de Origem</th>
<th>Endereço IP de Destino</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Acesso/SIP(MTLS)/TCP/5061</p></td>
<td><p>Qualquer um (pode ser definido como Diretor, IP virtual do Pool de diretores, Servidor Front-End ou IP virtual do Pool de Front-Ends)</p></td>
<td><p>Interface VIP interna do Servidor de Borda</p></td>
<td><p>Tráfego SIP de saída (do Diretor, IP virtual do Pool de diretores, Servidor Front-End ou IP virtual do Pool de Front-Ends) para IP virtual de borda interna</p></td>
</tr>
<tr class="even">
<td><p>Acesso/SIP(MTLS)/TCP/5061</p></td>
<td><p>Interface VIP interna do Servidor de Borda</p></td>
<td><p>Qualquer um (pode ser definido como Diretor, IP virtual do Pool de diretores, Servidor Front-End ou IP virtual do Pool de Front-Ends)</p></td>
<td><p>Tráfego SIP de entrada (para Diretor, IP virtual do Pool de diretores, Servidor Front-End ou IP virtual do Pool de Front-Ends) da interface interna do Servidor de Borda</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>Qualquer um (pode ser definido como IP do Servidor Front-End ou do Pool de Front-Ends, ou então como qualquer Aparelho de Filial Persistente ou Servidor de Filial Persistente utilizando esse Servidor de Borda)</p></td>
<td><p>Interface VIP interna do Servidor de Borda</p></td>
<td><p>Autenticação de usuários A/V (serviço de autenticação A/V) de Servidor Front-End ou endereço IP do Pool de Front-Ends ou qualquer Aparelho de Filial Persistente ou Servidor de Filial Persistente utilizando esse Servidor de Borda</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>Qualquer um</p></td>
<td><p>Interface VIP interna do Servidor de Borda</p></td>
<td><p>Caminho preferencial para transferência de mídia A/V entre usuários internos e externos (UDP)</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Qualquer um</p></td>
<td><p>Interface VIP interna do Servidor de Borda</p></td>
<td><p>Caminho de fallback para transferência de mídia A/V entre usuários internos e externos; se a comunicação UDP não pode ser estabelecida, TCP é usado para transferência de arquivos e compartilhamento de área de trabalho</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Interface VIP interna do Servidor de Borda</p></td>
<td><p>Qualquer um</p></td>
<td><p>Caminho de fallback para transferência de mídia A/V entre usuários internos e externos; se a comunicação UDP não pode ser estabelecida, TCP é usado para transferência de arquivos e compartilhamento de área de trabalho</p></td>
</tr>
</tbody>
</table>

