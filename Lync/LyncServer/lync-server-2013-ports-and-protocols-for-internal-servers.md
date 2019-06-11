---
title: 'Lync Server 2013: portas e protocolos para servidores internos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Ports and protocols for internal servers
ms:assetid: c94063f1-e802-4a61-be90-022fc185335e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398833(v=OCS.15)
ms:contentKeyID: 48185402
ms.date: 04/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 026843216e433ebea120384209ed90f38be3437b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a>Portas e protocolos para servidores internos no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2016-04-06_

Esta seção resume as portas e os protocolos usados por servidores, balanceadores de carga e clientes em uma implantação do Lync Server.

<div>


> [!IMPORTANT]  
> Os clientes do Lync e do Communicator, quando envolvidos em uma comunicação de um para um, geralmente são chamados de ponto a ponto. Tecnicamente, os dois clientes estão se comunicando em uma conversa de uma ou uma, com a IMMCU (unidade de controle Multipoint) do chat no meio. O IMMCU é um componente do servidor front-end. Colocar o IMMCU no fluxo de trabalho de comunicação necessário permite a gravação de detalhes da chamada e outros recursos que o servidor de front-end permite. A comunicação é de uma porta de origem dinâmica no cliente para a porta de servidor front-end TLS/TCP/5061 (pressupondo o uso da segurança da camada de transporte recomendada). Por design, a comunicação ponto a ponto (bem como mensagens instantâneas de vários participantes) só é possível quando o Lync Server e o IMMCU estão ativos e disponíveis.



</div>

<div>

## <a name="port-and-protocol-details"></a>Detalhes de protocolo e porta

<div>


> [!NOTE]  
> O Firewall do Windows deve estar em execução antes de iniciar os serviços do Lync Server em um servidor, pois isso ocorre quando o Lync Server abre as portas obrigatórias no firewall.



</div>

Para obter detalhes sobre a configuração de firewall para componentes de borda, consulte [determinar requisitos de firewall e porta externo A/V para o Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).

A tabela a seguir lista as portas que precisam ser abertas em cada função de servidor interno.

### <a name="required-server-ports-by-server-role"></a>Portas do servidor necessárias (por Função de servidor)

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Função de servidor</th>
<th>Nome do serviço</th>
<th>Porta</th>
<th>Protocolo</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Todos os servidores</p></td>
<td><p>Navegador do SQL</p></td>
<td><p>1434</p></td>
<td><p>UDP</p></td>
<td><p>Navegador do SQL para a cópia replicada local do banco de dados do repositório de gerenciamento central.</p></td>
</tr>
<tr class="even">
<td><p>Servidores Front-End</p></td>
<td><p>Serviço de front-end do Lync Server</p></td>
<td><p>5060</p></td>
<td><p>TCP</p></td>
<td><p>Usada como opção pelos servidores Standard Edition e Servidores Front-End para rotas estáticas para serviços confiáveis, como servidores de controle de chamada remota.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores Front-End</p></td>
<td><p>Serviço de front-end do Lync Server</p></td>
<td><p>5061</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Usada pelos servidores Standard Edition e pools de front-ends em todas as comunicações SIP internas entre servidores (MTLS), em comunicações SIP entre o servidor e o cliente (TLS) e em comunicações SIP entre os servidores front-end e os servidores de mediação (MTLS). Também usado para comunicações com o Monitoring Server.</p></td>
</tr>
<tr class="even">
<td><p>Servidores Front-End</p></td>
<td><p>Serviço de front-end do Lync Server</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p>
<p>TCP</p></td>
<td><p>Usado para comunicação HTTPS entre o foco (o componente do Lync Server que gerencia o estado da conferência) e os servidores individuais.</p>
<p>Essa porta também é usada para comunicação TCP entre aparelhos de ramificação sobreviventes e servidores front-end.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores Front-End</p></td>
<td><p>Serviço de front-end do Lync Server</p></td>
<td><p>135</p></td>
<td><p>DCOM e RPC (controle de procedimento remoto)</p></td>
<td><p>Usada para operações com base em DCOM, como Movendo Usuários, Sincronização do Replicador do Usuário e Sincronização do Catálogo de Endereços.</p></td>
</tr>
<tr class="even">
<td><p>Servidores Front-End</p></td>
<td><p>Serviço de conferência IM do Lync Server</p></td>
<td><p>5062</p></td>
<td><p>TCP</p></td>
<td><p>Usado para solicitações SIP de entrada para conferência de IM (mensagem instantânea).</p></td>
</tr>
<tr class="odd">
<td><p>Servidores Front-End</p></td>
<td><p>Serviço de conferência Web do Lync Server</p></td>
<td><p>8057</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Usada para escutar conexões PSOM (Modelo de Objeto Compartilhado Persistente) do cliente.</p></td>
</tr>
<tr class="even">
<td><p>Servidores Front-End</p></td>
<td><p>Serviço de compatibilidade do Lync Server Web referencing</p></td>
<td><p>8058</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Usado para escutar conexões do modelo de objeto compartilhado persistente (PSOM) do cliente de reunião ao vivo e versões anteriores do Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores Front-End</p></td>
<td><p>Serviço de conferência de áudio/vídeo do Lync Server</p></td>
<td><p>5063</p></td>
<td><p>TCP</p></td>
<td><p>Usada para solicitações SIP de entrada para conferência de áudio/vídeo (A/V).</p></td>
</tr>
<tr class="even">
<td><p>Servidores Front-End</p></td>
<td><p>Serviço de conferência de áudio/vídeo do Lync Server</p></td>
<td><p>57501-65535</p></td>
<td><p>TCP/UDP</p></td>
<td><p>Intervalo de porta de mídia usado para videoconferência.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores Front-End</p></td>
<td><p>Serviço de compatibilidade da Web do Lync Server</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
<td><p>Usada para comunicação dos Servidores Front-End com os FQDNs do farm da web (as URLs usadas pelos componentes da web IIS) quando HTTPS não é usado.</p></td>
</tr>
<tr class="even">
<td><p>Servidores Front-End</p></td>
<td><p>Serviço de compatibilidade da Web do Lync Server</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td><p>Usado para comunicação dos servidores front-End no farm da web FQDNs (as URLs usadas pelos componentes da web do IIS).</p></td>
</tr>
<tr class="odd">
<td><p>Servidores Front-End</p></td>
<td><p>Serviço de compatibilidade da Web do Lync Server</p></td>
<td><p>8080</p></td>
<td><p>TCP e HTTP</p></td>
<td><p>Usado pelos componentes da Web para acesso externo.</p></td>
</tr>
<tr class="even">
<td><p>Servidores Front-End</p></td>
<td><p>Servidor de componentes da Web</p></td>
<td><p>4443</p></td>
<td><p>HTTPS</p></td>
<td><p>Comunicações entre pools de front-end HTTPS (de Proxy Reverso) e HTTPS para conexão de Descoberta automática.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores Front-End</p></td>
<td><p>Servidor de componentes da Web</p></td>
<td><p>8060</p></td>
<td><p>TCP (MTLS)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Servidores Front-End</p></td>
<td><p>Servidor de componentes da Web</p></td>
<td><p>8061</p></td>
<td><p>TCP (MTLS)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Servidores Front-End</p></td>
<td><p>Componente dos serviços de mobilidade</p></td>
<td><p>5086</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Porta SIP usada pelos processos internos dos Serviços de Mobilidade</p></td>
</tr>
<tr class="even">
<td><p>Servidores Front-End</p></td>
<td><p>Componente dos serviços de mobilidade</p></td>
<td><p>5087</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Porta SIP usada pelos processos internos dos Serviços de Mobilidade</p></td>
</tr>
<tr class="odd">
<td><p>Servidores Front-End</p></td>
<td><p>Componente dos serviços de mobilidade</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Servidores Front-End</p></td>
<td><p>Serviço de atendedor do Lync Server Conferencing (conferência discada)</p></td>
<td><p>5064</p></td>
<td><p>TCP</p></td>
<td><p>Usada para solicitações SIP de entrada para conferência discada.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores Front-End</p></td>
<td><p>Serviço de atendedor do Lync Server Conferencing (conferência discada)</p></td>
<td><p>5072</p></td>
<td><p>TCP</p></td>
<td><p>Usado para solicitações SIP de entrada do atendente (discagem por conferência).</p></td>
</tr>
<tr class="even">
<td><p>Servidores Front-End que também executam um Servidor de Mediação Colocado</p></td>
<td><p>Serviço de mediação do Lync Server</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
<td><p>Usada pelo Servidor de Mediação para solicitações de entrada do Servidor Front-End para o Servidor de Mediação.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores Front-End que também executam um Servidor de Mediação Colocado</p></td>
<td><p>Serviço de mediação do Lync Server</p></td>
<td><p>5067</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Usada para solicitações SIP de entrada do gateway PSTN para o Servidor de Mediação.</p></td>
</tr>
<tr class="even">
<td><p>Servidores Front-End que também executam um Servidor de Mediação Colocado</p></td>
<td><p>Serviço de mediação do Lync Server</p></td>
<td><p>5068</p></td>
<td><p>TCP</p></td>
<td><p>Usada para solicitações SIP de entrada do gateway PSTN para o Servidor de Mediação.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores Front-End que também executam um Servidor de Mediação Colocado</p></td>
<td><p>Serviço de mediação do Lync Server</p></td>
<td><p>5081</p></td>
<td><p>TCP</p></td>
<td><p>Usada para solicitações SIP de saída do Servidor de Mediação para o gateway PSTN.</p></td>
</tr>
<tr class="even">
<td><p>Servidores Front-End que também executam um Servidor de Mediação Colocado</p></td>
<td><p>Serviço de mediação do Lync Server</p></td>
<td><p>5082</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Usada para solicitações SIP de saída do Servidor de Mediação para o gateway PSTN.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores Front-End</p></td>
<td><p>Serviço de compartilhamento de aplicativos do Lync Server</p></td>
<td><p>5065</p></td>
<td><p>TCP</p></td>
<td><p>Usada para solicitações de escuta do SIP de entrada para compartilhamento de aplicativos.</p></td>
</tr>
<tr class="even">
<td><p>Servidores Front-End</p></td>
<td><p>Serviço de compartilhamento de aplicativos do Lync Server</p></td>
<td><p>49152-65535</p></td>
<td><p>TCP</p></td>
<td><p>Intervalo de porta de mídia usado para compartilhamento de aplicativo.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores Front-End</p></td>
<td><p>Serviço de anúncio de conferência do Lync Server</p></td>
<td><p>5073</p></td>
<td><p>TCP</p></td>
<td><p>Usado para solicitações SIP recebidas para o serviço de anúncio de conferência do Lync Server (ou seja, para conferência discada).</p></td>
</tr>
<tr class="even">
<td><p>Servidores Front-End</p></td>
<td><p>Serviço de Estacionamento de Chamada do Lync Server</p></td>
<td><p>5075</p></td>
<td><p>TCP</p></td>
<td><p>Usada para solicitações SIP de entrada para o aplicativo Estacionamento de Chamadas.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores Front-End</p></td>
<td><p>Serviço de teste de áudio do Lync Server</p></td>
<td><p>5076</p></td>
<td><p>TCP</p></td>
<td><p>Usada para solicitações SIP de entrada para o serviço Teste de Áudio.</p></td>
</tr>
<tr class="even">
<td><p>Servidores Front-End</p></td>
<td><p>Não aplicável</p></td>
<td><p>5066</p></td>
<td><p>TCP</p></td>
<td><p>Usada para o gateway de E9-1-1 (9-1-1 Avançado) de saída.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores Front-End</p></td>
<td><p>Serviço Grupo de Resposta do Lync Server</p></td>
<td><p>5071</p></td>
<td><p>TCP</p></td>
<td><p>Usada para solicitações SIP de entrada para o aplicativo Grupo de Respostas.</p></td>
</tr>
<tr class="even">
<td><p>Servidores Front-End</p></td>
<td><p>Serviço Grupo de Resposta do Lync Server</p></td>
<td><p>8404</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Usada para solicitações SIP de entrada para o aplicativo Grupo de Respostas.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores Front-End</p></td>
<td><p>Serviço de política de largura de banda do Lync Server</p></td>
<td><p>5080</p></td>
<td><p>TCP</p></td>
<td><p>Usada para controle de admissão de chamada pelo serviço Política de Largura de banda para tráfego TURN de Borda A/V.</p></td>
</tr>
<tr class="even">
<td><p>Servidores Front-End</p></td>
<td><p>Serviço de política de largura de banda do Lync Server</p></td>
<td><p>448</p></td>
<td><p>TCP</p></td>
<td><p>Usado para controle de admissão de chamadas pelo serviço de política de largura de banda do Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores front-end nos quais o repositório de gerenciamento central reside</p></td>
<td><p>Serviço de agente do Lync Server Master Replicator</p></td>
<td><p>445</p></td>
<td><p>TCP</p></td>
<td><p>Usado para enviar por push dados de configuração do repositório de gerenciamento central para servidores que executam o Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>Todos os servidores</p></td>
<td><p>Navegador do SQL</p></td>
<td><p>1434</p></td>
<td><p>UDP</p></td>
<td><p>Navegador do SQL para cópia replicada local de dados do repositório de gerenciamento central na instância do SQL Server local</p></td>
</tr>
<tr class="odd">
<td><p>Todos os servidores internos</p></td>
<td><p>Vários</p></td>
<td><p>49152-57500</p></td>
<td><p>TCP/UDP</p></td>
<td><p>Intervalo de porta de mídia usada para audioconferência em todos os servidores internos. Usado por todos os servidores que encerram áudio: servidores front-end (para o serviço de atendedor do Lync Server Conferencing, serviço de anúncio de conferência do Lync Server e serviço de videoconferência/vídeo do Lync Server) e servidor de mediação.</p></td>
</tr>
<tr class="even">
<td><p>Servidor Office Web Apps</p></td>
<td></td>
<td><p>443</p></td>
<td></td>
<td><p>Usado pelo Lync Server 2013 para se conectar ao servidor do Office Web Apps.</p></td>
</tr>
<tr class="odd">
<td><p>Diretores</p></td>
<td><p>Serviço de front-end do Lync Server</p></td>
<td><p>5060</p></td>
<td><p>TCP</p></td>
<td><p>Usada como opção para rotas estáticas até os serviços confiáveis, como servidores de controle de chamada remota.</p></td>
</tr>
<tr class="even">
<td><p>Diretores</p></td>
<td><p>Serviço de front-end do Lync Server</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p>
<p>TCP</p></td>
<td><p>Comunicação entre servidores entre Front-End e Diretor. Além disso, a publicação de certificado do cliente (para servidores front-end) ou a validar se o certificado do cliente já foi publicado.</p></td>
</tr>
<tr class="odd">
<td><p>Diretores</p></td>
<td><p>Serviço de compatibilidade da Web do Lync Server</p></td>
<td><p>80</p></td>
<td><p>TCP</p></td>
<td><p>Usada para comunicação inicial dos Diretores com os FQDNs de farm da web (as URLs usadas pelos componentes da web IIS). Em uma operação normal, trocará para tráfego HTTPS, usando a porta 443 e o tipo de protocolo TCP.</p></td>
</tr>
<tr class="even">
<td><p>Diretores</p></td>
<td><p>Serviço de compatibilidade da Web do Lync Server</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td><p>Usada para comunicação dos Diretores com os FQDNs de farm da web (as URLs usadas pelos componentes da web IIS).</p></td>
</tr>
<tr class="odd">
<td><p>Diretores</p></td>
<td><p>Serviço de front-end do Lync Server</p></td>
<td><p>5061</p></td>
<td><p>TCP</p></td>
<td><p>Usada para comunicações internas entre os servidores e para conexões do cliente.</p></td>
</tr>
<tr class="even">
<td><p>Servidores de Mediação</p></td>
<td><p>Serviço de mediação do Lync Server</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
<td><p>Usada pelo Servidor de mediação para solicitações de entrada do Servidor Front-End.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores de Mediação</p></td>
<td><p>Serviço de mediação do Lync Server</p></td>
<td><p>5067</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Usada para solicitações SIP de entrada do gateway PSTN.</p></td>
</tr>
<tr class="even">
<td><p>Servidores de mediação</p></td>
<td><p>Serviço de mediação do Lync Server</p></td>
<td><p>5068</p></td>
<td><p>TCP</p></td>
<td><p>Usada para solicitações SIP de entrada do gateway PSTN.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores de mediação</p></td>
<td><p>Serviço de mediação do Lync Server</p></td>
<td><p>5070</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Usada para solicitações SIP dos Servidores Front-End.</p></td>
</tr>
<tr class="even">
<td><p>Servidor de front-end de bate-papo persistente</p></td>
<td><p>SIP de bate-papo persistente</p></td>
<td><p>5041</p></td>
<td><p>TCP (MTLS)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Servidor de front-end de bate-papo persistente</p></td>
<td><p>Bate-papo persistente do Windows Communication Foundation (WCF)</p></td>
<td><p>881</p></td>
<td><p>TCP (TLS) e TCP (MTLS)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Servidor de front-end de bate-papo persistente</p></td>
<td><p>Serviço de transferência de arquivos de bate-papo persistente</p></td>
<td><p>443</p></td>
<td><p>TCP (TLS)</p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Alguns cenários de controle de chamada remota exigem uma conexão TCP entre o Servidor Front-End ou o Diretor e o PBX. Embora o Lync Server não use mais a porta TCP 5060, durante a implantação do controle de chamada remota, você cria uma configuração de servidor confiável, que associa o FQDN do servidor de linha de RCC à porta TCP que o servidor front-end ou o diretor usará para se conectar ao sistema PBX. Para obter detalhes, consulte o cmdlet <STRONG>CsTrustedApplicationComputer</STRONG> na documentação do Shell de gerenciamento do Lync Server.



</div>

Para os seus pools que usam somente o balanceamento de carga de hardware (não o balanceamento de carga DNS), a tabela a seguir mostra as portas que precisam abrir os balanceadores de carga de hardware.

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a>Portas do balanceador de carga de hardware se estiver usando somente o balanceador de carga de hardware

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Balanceador de carga</th>
<th>Porta</th>
<th>Protocolo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Balanceador de carga do Servidor Front-End</p></td>
<td><p>5061</p></td>
<td><p>TCP (TLS)</p></td>
</tr>
<tr class="even">
<td><p>Balanceador de carga do Servidor Front-End</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>Balanceador de carga do Servidor Front-End</p></td>
<td><p>135</p></td>
<td><p>DCOM e RPC (controle de procedimento remoto)</p></td>
</tr>
<tr class="even">
<td><p>Balanceador de carga do Servidor Front-End</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Balanceador de carga do Servidor Front-End</p></td>
<td><p>8080</p></td>
<td><p>TCP - Recuperação por parte do cliente e do dispositivo do certificado raiz do Servidor Front-End – clientes e dispositivos autenticados por NTLM</p></td>
</tr>
<tr class="even">
<td><p>Balanceador de carga do Servidor Front-End</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>Balanceador de carga do Servidor Front-End</p></td>
<td><p>4443</p></td>
<td><p>HTTPS (do proxy reverso)</p></td>
</tr>
<tr class="even">
<td><p>Balanceador de carga do Servidor Front-End</p></td>
<td><p>5072</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Balanceador de carga do Servidor Front-End</p></td>
<td><p>5073</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Balanceador de carga do Servidor Front-End</p></td>
<td><p>5075</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Balanceador de carga do Servidor Front-End</p></td>
<td><p>5076</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Balanceador de carga do Servidor Front-End</p></td>
<td><p>5071</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Balanceador de carga do Servidor Front-End</p></td>
<td><p>5080</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Balanceador de carga do Servidor Front-End</p></td>
<td><p>448</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Balanceador de carga do Servidor de mediação</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Balanceador de carga do Servidor Front-End (se o pool também executa o Servidor de mediação)</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Balanceador de carga do Diretor</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td><p>Balanceador de carga do Diretor</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>Balanceador de carga do Diretor</p></td>
<td><p>5061</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Balanceador de carga do Diretor</p></td>
<td><p>4443</p></td>
<td><p>HTTPS (do proxy reverso)</p></td>
</tr>
</tbody>
</table>


Seus pools do Front-End e do Diretor que usam o balanceamento de carga DNS também precisam ter um balanceador de carga de hardware implantado. A tabela a seguir mostra as portas que precisam ser abertas nesses balanceadores de carga de hardware.

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a>Portas do balanceador de carga de hardware se estiver usando o balanceamento de carga DNS

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Balanceador de carga</th>
<th>Porta</th>
<th>Protocolo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Balanceador de carga do Servidor Front-End</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
</tr>
<tr class="even">
<td><p>Balanceador de carga do Servidor Front-End</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>Balanceador de carga do Servidor Front-End</p></td>
<td><p>8080</p></td>
<td><p>TCP - Recuperação por parte do cliente e do dispositivo do certificado raiz do Servidor Front-End – clientes e dispositivos autenticados por NTLM</p></td>
</tr>
<tr class="even">
<td><p>Balanceador de carga do Servidor Front-End</p></td>
<td><p>4443</p></td>
<td><p>HTTPS (do proxy reverso)</p></td>
</tr>
<tr class="odd">
<td><p>Balanceador de carga do Diretor</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Balanceador de carga do Diretor</p></td>
<td><p>4443</p></td>
<td><p>HTTPS (do proxy reverso)</p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a>Portas do cliente necessárias

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
<th>Porta</th>
<th>Protocolo</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Clientes</p></td>
<td><p>67/68</p></td>
<td><p>DHCP</p></td>
<td><p>Usado pelo Lync Server para localizar o FQDN do registrador (isto é, se as configurações de SRV DNS falharem e as configurações manuais não estiverem definidas).</p></td>
</tr>
<tr class="even">
<td><p>Clientes</p></td>
<td><p>443</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Usada para tráfego SIP do cliente para o servidor para acesso de usuário externo.</p></td>
</tr>
<tr class="odd">
<td><p>Clientes</p></td>
<td><p>443</p></td>
<td><p>TCP (PSOM/TLS)</p></td>
<td><p>Usada para acesso de usuário externo às sessões de webconferência.</p></td>
</tr>
<tr class="even">
<td><p>Clientes</p></td>
<td><p>443</p></td>
<td><p>TCP (STUN/MSTURN)</p></td>
<td><p>Usada para acesso de usuário externa às sessões de A/V e mídia (TCP)</p></td>
</tr>
<tr class="odd">
<td><p>Clientes</p></td>
<td><p>3478</p></td>
<td><p>UDP (STUN/MSTURN)</p></td>
<td><p>Usada para acesso de usuário externo às sessões de A/V e mídia (UDP)</p></td>
</tr>
<tr class="even">
<td><p>Clientes</p></td>
<td><p>5061</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Usada para tráfego SIP do cliente para o servidor para acesso de usuário externo.</p></td>
</tr>
<tr class="odd">
<td><p>Clientes</p></td>
<td><p>6891-6901</p></td>
<td><p>TCP</p></td>
<td><p>Usado para transferência de arquivos entre clientes do Lync e clientes anteriores (clientes do Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007 e Live Communications Server 2005).</p></td>
</tr>
<tr class="even">
<td><p>Clientes</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP/UDP</p></td>
<td><p>Intervalo de porta de áudio (mínimo de 20 portas necessárias)</p></td>
</tr>
<tr class="odd">
<td><p>Clientes</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP/UDP</p></td>
<td><p>Intervalo de porta de vídeo (mínimo de 20 portas necessárias).</p></td>
</tr>
<tr class="even">
<td><p>Clientes</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP</p></td>
<td><p>Transferência de arquivos ponto a ponto (para transferência de arquivo de conferência, clientes que usam PSOM).</p></td>
</tr>
<tr class="odd">
<td><p>Clientes</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP</p></td>
<td><p>Compartilhamento de aplicativos.</p></td>
</tr>
<tr class="even">
<td><p>Telefone de área comum Aastra 6721ip</p>
<p>Telefone de mesa Aastra 6725ip</p>
<p>Telefone IP HP 4110 (telefone de área comum)</p>
<p>Telefone IP HP 4120 (telefone de mesa)</p>
<p>Telefone de área comum IP Polycom CX500</p>
<p>Telefone de mesa IP Polycom CX600</p>
<p>Telefone de mesa IP Polycom CX700</p>
<p>Telefone de conferência IP Polycom CX3000</p></td>
<td><p>67/68</p></td>
<td><p>DHCP</p></td>
<td><p>Usado pelos dispositivos listados para localizar o certificado do Lync Server, o provisionamento e o FQDN do registrador.</p></td>
</tr>
</tbody>
</table>


**\*** Para configurar portas específicas para esses tipos de mídia, use o cmdlet CsConferencingConfiguration (parâmetros ClientMediaPortRangeEnabled, ClientMediaPort e ClientMediaPortRange).

<div>


> [!NOTE]  
> Os programas definidos para clientes do Lync criam automaticamente as exceções necessárias de firewall do sistema operacional no computador cliente.



</div>

<div>


> [!NOTE]  
> As portas usadas para acesso de usuário externo são necessárias para qualquer cenário no qual o cliente precisa atravessar o firewall da organização (por exemplo, quaisquer comunicações externas ou reuniões hospedadas por outras organizações).



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

