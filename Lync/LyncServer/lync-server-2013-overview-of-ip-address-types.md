---
title: 'Lync Server 2013: visão geral dos tipos de endereço IP'
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
ms.openlocfilehash: 417b304825da6a611ccfdaf3521b2d9571cd4756
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216277"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-ip-address-types-for-lync-server-2013"></a>Visão geral dos tipos de endereço IP para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-01-29_

Você tem três opções ao configurar endereços IP no Lync Server 2013. Você pode configurar o Lync Server 2013 para oferecer suporte somente a IP versão 4 (IPv4), somente o IP versão 6 (IPv6) ou uma combinação dos dois (conhecido como *pilha Dual*). Há vários problemas que devem ser considerados em cada tipo de configuração:

  - ****   O IPv6 somente IPv4 foi criado porque o mundo está ficando sem endereços IPv4. Por fim, o IPv6 será totalmente suportado em todo o mundo, mas, neste momento, muitas empresas e dispositivos que sua empresa talvez precisem se comunicar com o não dão suporte a IPv6, e talvez não haja algum tempo. Uma configuração somente IPv4 ajudará a garantir que sua implementação do Lync Server possa se comunicar com a maioria dos dispositivos existentes.

  - **Somente IPv6 por**   outro lado, uma implementação IPv6 completa, neste momento, excluirá a comunicação com vários dispositivos existentes.

  - ****   Pilha dual de pilha dupla é uma rede onde endereços IPv4 e IPv6 estão habilitados. Essa configuração é suportada no Lync Server 2013 porque, na maioria dos casos, a transição de IPv4 para pleno IPv6 levará vários anos.

As seções a seguir descrevem a compatibilidade entre essas três configurações para vários recursos do Lync Server.

<div>


> [!NOTE]  
> A configuração de cliente ou servidor com IPv6 só é suportada para fins de laboratório ou validação. A configuração IPv6 somente não é suportada na implantação de produção.



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
<th>Rede de ponto de extremidade do cliente</th>
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

As comunicações ponto a ponto incluem áudio, áudio/vídeo, compartilhamento de aplicativos e transferência de arquivos. Após os dois clientes terem sido registrados com êxito, as combinações a seguir são suportadas.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Ponto de extremidade de cliente 1</th>
<th>Ponto de extremidade 2 do cliente</th>
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

## <a name="conferencing"></a>Conferências

A conferência inclui áudio/vídeo, compartilhamento de aplicativos e colaboração de dados (quadro de comunicações e compartilhamento de arquivos).


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Rede de ponto de extremidade do cliente</th>
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

## <a name="mediation-serverpstn"></a>Servidor de mediação/PSTN

O Lync Server 2013 não é compatível com bypass de mídia para chamadas PSTN (rede telefônica pública comutada) se o tráfego estiver por meio de uma interface IPv6. Se o bypass de mídia for necessário, recomendamos que o gateway PSTN esteja configurado como IPv4.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Interface principal *</th>
<th>Interface PSTN (no servidor de mediação)</th>
<th>Configuração de gateway PSTN</th>
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

Comunicações ponto a ponto com usuários remotos incluem mensagens instantâneas, áudio/vídeo, compartilhamento de aplicativos e transferência de arquivos.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Rede de usuário remoto</th>
<th>Servidor de borda (borda externa)</th>
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

## <a name="front-end-pool-and-edge-pool-configuration"></a>Configuração do pool de front-ends e do pool de borda

A tabela a seguir mostra a matriz de suporte entre o pool do servidor front-end e o pool do servidor de borda interno.

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a>Matriz do pool de front-ends e do pool de borda (borda interna)

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
<td><p><strong>Pool de borda: pilha dupla</strong></p></td>
<td><p><strong>Pool de borda: IPv6</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Pool de front-ends: IPv4</strong></p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Não</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool de front-ends: pilha dual</strong></p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Não</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool de front-ends: IPv6</strong></p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p>Sim</p></td>
</tr>
</tbody>
</table>


\*Use essa combinação somente em um ambiente de laboratório.

A tabela a seguir é uma matriz das combinações suportadas de interfaces de borda internas e externas.

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a>Matriz do pool de borda (borda interna) e do pool de borda (borda externa)

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
<td><p><strong>Pool de borda (borda externa): IPv4</strong></p></td>
<td><p><strong>Pool de borda (borda externa): pilha dupla</strong></p></td>
<td><p><strong>Pool de borda (borda externa): IPv6</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Pool de borda (borda interna): IPv4</strong></p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Não</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool de borda (borda interna): pilha dupla</strong></p></td>
<td><p>Não</p></td>
<td><p>Sim</p></td>
<td><p>Não</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool de borda (borda interna): IPv6</strong></p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p>Sim</p></td>
</tr>
</tbody>
</table>


\*Use essa combinação somente em um ambiente de laboratório.

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a>Suporte avançado do Enterprise Voice para IPv6

Implantações que incluem controle de admissão de chamadas (CAC), Enhanced 9-1-1 (E9-1-1) ou bypass de mídia devem ser configurados como IPv4 somente ou como uma implementação de pilha dupla.

<div>


> [!NOTE]  
> Em uma implantação de pilha dupla, mesmo que um cliente do Lync se conecte a um Lync Server usando IPv6, o Lync fará um melhor esforço para mapear um endereço IPv4 apropriado para suportar o E9-1-1.



</div>

O serviço de informações de local com endereços IPv6 não é suportado.

A Unificação de mensagens (UM) do Exchange não oferece suporte a IPv6. Para UM do Exchange, certifique-se de que a resolução de DNS não retorna um endereço IPv6. O uso do IPv6 pode causar falha quando as chamadas são enviadas para caixa postal.

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a>Outro suporte de recurso do Lync Server 2013 para IPv6

Além dos recursos e componentes mencionados anteriormente, o Lync Server 2013 suporta IPv6 para os seguintes recursos:

  - **Chat persistente**
    
    Você configura o IPv6 para chat persistente usando o construtor de topologias. Para obter detalhes sobre como configurar o chat persistente, consulte a documentação implantando o servidor de chat persistente.

  - **Relatórios de QoE (qualidade da experiência) e de registro de detalhes das chamadas (CDR)**
    
    Os relatórios de monitoramento incluem o endereço IP conforme ele é armazenado no banco de dados do Monitoring Server, seja do tipo IPv4 ou IPv6.

</div>

</div>

<span> </span>

</div>

</div>

</div>

