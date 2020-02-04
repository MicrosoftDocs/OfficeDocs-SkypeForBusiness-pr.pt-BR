---
title: 'Lync Server 2013: Visão geral dos tipos de endereços IP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of IP address types for Lync Server
ms:assetid: ee9a695f-5cf5-441e-94fb-6adeca50e8d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205363(v=OCS.15)
ms:contentKeyID: 48185759
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d1172fc7da9600de036312adb05548b51dea6b0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755525"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-ip-address-types-for-lync-server-2013"></a>Visão geral dos tipos de endereços IP para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-01-29_

Você tem três opções ao configurar endereços IP no Lync Server 2013. Você pode configurar o Lync Server 2013 para dar suporte somente para IP versão 4 (IPv4), somente para IP versão 6 (IPv6) ou uma combinação de ambos (conhecida como *pilha dupla*). Vários problemas devem ser considerados para cada tipo de configuração:

  - **IPv4 somente**   IPv6 foi criado porque o mundo está ficando sem endereços IPv4. No fim das contas, o IPv6 será completamente suportado em todo o mundo, mas no momento, várias empresas e dispositivos aos quais sua empresa pode precisar se comunicar ainda não oferecem suporte ao IPv6, e poderão não oferecer por algum tempo. Uma configuração somente IPv4 ajudará a garantir que a implementação do Lync Server possa se comunicar com a maioria dos dispositivos existentes.

  - **** Por outro lado, uma implementação IPv6 completa, no momento, excluirá a comunicação com muitos dispositivos existentes.   

  - **Pilha dupla dupla empilhada**   é uma rede onde ambos os endereços IPv4 e IPv6 são habilitados. Essa configuração tem suporte no Lync Server 2013 porque, na maioria dos casos, a transição de Full-IPv4 para Full-IPv6 levará vários anos.

As seções a seguir descrevem a compatibilidade entre essas três configurações para vários recursos do Lync Server.

<div>


> [!NOTE]  
> Configuração de cliente ou servidor com somente IPv6 é suportada apenas para fins de validação ou utilização em laboratório. A configuração somente IPv6 não é suportada na implantação de produção.



</div>

<div>

## <a name="client-registration"></a>Registro de cliente


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Extremidade de rede de cliente</th>
<th>Rede de servidor</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>IPv4</p></td>
<td><p>Pilha dual</p></td>
</tr>
<tr class="odd">
<td><p>Pilha dual</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>Pilha dual</p></td>
<td><p>Pilha dual</p></td>
</tr>
<tr class="odd">
<td><p>Pilha dual</p></td>
<td><p>IPv6</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>Pilha dual</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="peer-to-peer-client"></a>Cliente ponto a ponto

As comunicações ponto a ponto incluem áudio, áudio/vídeo, compartilhamento de aplicativos e transferência de arquivos. Após o registro bem sucedido de ambos os clientes, as combinações a seguir são suportadas.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Extremidade de cliente 1</th>
<th>Extremidade de cliente 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>IPv4</p></td>
<td><p>Pilha dual</p></td>
</tr>
<tr class="odd">
<td><p>Pilha dual</p></td>
<td><p>Pilha dual</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>Pilha dual</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="conferencing"></a>Conferência

A conferência inclui áudio/vídeo, compartilhamento de aplicativos e colaboração de dados (quadro de comunicações e compartilhamento de arquivos).


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Extremidade de rede de cliente</th>
<th>Rede de servidor</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>IPv4</p></td>
<td><p>Pilha dual</p></td>
</tr>
<tr class="odd">
<td><p>Pilha dual</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>Pilha dual</p></td>
<td><p>Pilha dual</p></td>
</tr>
<tr class="odd">
<td><p>Pilha dual</p></td>
<td><p>IPv6</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>Pilha dual</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="mediation-serverpstn"></a>Servidor de Mediação/PSTN

O Lync Server 2013 não oferece suporte à bypass de mídia para chamadas PSTN (rede telefônica pública comutada) se o tráfego for por meio de uma interface IPv6. Se o desvio de mídia é necessário, recomendamos que o gateway PSTN seja configurado para IPv4.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Interface principal*</th>
<th>Interface PSTN (no Servidor de Mediação)</th>
<th>Configuração do gateway PSTN</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>Pilha dual</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>Pilha dual</p></td>
<td><p>Pilha dual</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="odd">
<td><p>Pilha dual</p></td>
<td><p>Pilha dual</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


\*A interface principal é a interface que se comunica com os componentes do Lync Server.

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a>Comunicações ponto a ponto de usuário remoto

As comunicações ponto a ponto com usuários remotos incluem mensagens instantâneas, áudio/vídeo, compartilhamento de aplicativos e transferência de arquivos.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Rede de usuários remotos</th>
<th>Servidor de borda (Borda externa)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>Pilha dual</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="odd">
<td><p>Pilha dual</p></td>
<td><p>Pilha dual</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>Pilha dual</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a>Configuração do pool de Front-Ends e do pool do Servidor de Borda

A tabela a seguir mostra a matriz de suporte entre o pool do servidor front-end e o pool do servidor de borda interna.

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a>Matriz do Pool de Front-Ends e do Pool de Borda (Borda interna)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><strong>Pool de borda: IPv4</strong></p></td>
<td><p><strong>Pool de borda: Pilha dual</strong></p></td>
<td><p><strong>Pool de borda: IPv6</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Pool de Front-Ends: IPv4</strong></p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Não</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool de Front-Ends: Pilha dual</strong></p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Não</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool de Front-Ends: IPv6</strong></p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p>Sim*</p></td>
</tr>
</tbody>
</table>


\*Use essa combinação apenas em um ambiente de laboratório.

A tabela a seguir descreve a matriz de combinações suportadas das interfaces de borda interna e externa.

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a>Matriz do Pool de borda (Borda interna) e do Pool de borda (Borda externa)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><strong>Pool de borda (Borda externa): IPv4</strong></p></td>
<td><p><strong>Pool de borda (Borda externa): Pilha dual</strong></p></td>
<td><p><strong>Pool de borda (Borda externa): IPv6</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Pool de borda (Borda interna): IPv4</strong></p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Não</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool de borda (Borda interna): Pilha dual</strong></p></td>
<td><p>Não</p></td>
<td><p>Sim</p></td>
<td><p>Não</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool de borda (Borda interna): IPv6</strong></p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p>Sim*</p></td>
</tr>
</tbody>
</table>


\*Use essa combinação apenas em um ambiente de laboratório.

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a>Suporte avançado do Enterprise Voice para IPv6

Implantações que incluem controle de admissão de chamadas (CAC), Enhanced 9-1-1 (E9-1-1) ou passagem livre de mídia devem ser configurados como implementações somente IPv4 ou de pilha dual.

<div>


> [!NOTE]  
> Em uma implantação de pilha dupla, mesmo que um cliente do Lync se conecte a um servidor do Lync usando o IPv6, o Lync fará um melhor esforço para mapear um endereço IPv4 apropriado para dar suporte a E9-1-1.



</div>

Não há suporte para o serviço de informações de localização com endereços IPv6.

O Unified Messaging (UM) do Exchange não suporta IPv6. Para o UM do Exchange, certifique-se de que a resolução do DNS não retorna um endereço IPv6. A utilização de IPv6 pode provocar falhas ao enviar chamadas para correios de voz.

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a>Outro suporte do recurso Lync Server 2013 para IPv6

Além dos recursos e componentes mencionados anteriormente, o Lync Server 2013 oferece suporte ao IPv6 para os seguintes recursos:

  - **Chat Persistente**
    
    Você configura o IPv6 para chats persistentes usando o construtor de topologias. Para obter detalhes sobre como configurar o chat persistente, consulte a documentação implantando o servidor de chat persistente.

  - **Relatórios de CDR (registro de detalhes de chamada) e QoE (Qualidade de experiência)**
    
    Os relatórios de monitoramento incluem o endereço IP conforme é armazenado no banco de dados do Servidor de Monitoramento, independente de ser do tipo IPv4 ou IPv6.

</div>

</div>

<span> </span>

</div>

</div>

</div>

