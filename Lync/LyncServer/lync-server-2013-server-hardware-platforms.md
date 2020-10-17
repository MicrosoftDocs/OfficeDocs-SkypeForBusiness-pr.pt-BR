---
title: Plataformas de hardware de servidor do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server hardware platforms
ms:assetid: c964c1c0-0153-472b-88ad-a38866e0df0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398835(v=OCS.15)
ms:contentKeyID: 48185395
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb5c5cbe1ef98a4028f8b05d96e4acc90cae7963
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510268"
---
# <a name="server-hardware-platforms-for-lync-server-2013"></a>Plataformas de hardware de servidor para o Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2016-07-28_

As funções de servidor do Lync Server 2013 e os computadores que executam as ferramentas administrativas do Lync Server exigem hardware de 64 bits.

O hardware específico usado para a implantação do Lync Server 2013 pode variar, dependendo dos requisitos de tamanho e uso. Esta seção descreve o hardware recomendado. Embora estas sejam recomendações, não obrigações, usar o hardware não atende estas recomendações pode resultar em problemas significativos de desempenho e outros problemas.

<div>

## <a name="recommended-hardware-platform"></a>Plataforma de Hardware Recomendada

Para obter um melhor desempenho, recomendamos que você execute o Lync Server em servidores com hardware que atenda aos requisitos na tabela a seguir. Se você usar hardware menos poderoso, você pode enfrentar problemas de funcionalidade ou mau desempenho. Observe que esses requisitos de hardware são maiores do que os das versões anteriores do Lync Server, principalmente por causa do Lync Server 2013, todos os servidores front-end executam o SQL Server.

<div>


> [!NOTE]  
> A equipe de NIC é suportada e deve ser transparente para o Lync Server. Para obter detalhes, consulte <A href="https://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server or Lync Server and Network Adapter teaming</A>.



</div>

### <a name="recommended-hardware-for-front-end-servers-back-end-servers-standard-edition-servers-persistent-chat-servers-and-persistent-chat-store-and-persistent-chat-compliance-store-back-end-server-roles-for-persistent-chat-server"></a>Hardware recomendado para servidores front-end, servidores back-end, servidores Standard Edition, servidores de chat persistente e repositório de chat persistente e repositório de conformidade de chat persistente (funções de servidor back-end para servidor de chat persistente)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente de hardware</th>
<th>Recomendado</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><p>processador dual de 64 bits, Hex-Core, 2,26 gigahertz (GHz) ou superior.</p>
<p>Processadores Intel Itanium não são suportados para funções de servidor do Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>Memória</p></td>
<td><p>32 gigabytes (GB).</p></td>
</tr>
<tr class="odd">
<td><p>Disco</p></td>
<td><ul>
<li><p>8 ou mais drives de disco rígido de 10.000 RPM com pelo menos 72 GB espaço de disco livre.</p>
<p>Dois dos discos devem usar RAID 1 e seis devem usar RAID 10.</p>
<p>- Ou</p></li>
<li><p>Drivers de estado sólido (SSDs) que oferecem desempenho semelhante à 8 drivers de disco mecânico de 10.000-RPM.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Rede</p></td>
<td><ul>
<li><p>1 adaptador de rede de porta dupla, 1 Gbps ou superior (2 recomendado, que requer o agrupamento com um único endereço MAC e um único endereço IP).</p>
<div>

> [!NOTE]  
> As configurações de duas ou várias bases não têm suporte para servidores front-end, servidores de back-end, servidores Standard Edition e servidores de chat persistente.<BR>ILO/DRAC/etc. as conexões não expostas ao sistema operacional e usadas para monitorar e gerenciar o hardware do servidor não constituem um servidor de hospedagem múltipla e, portanto, são compatíveis.


</div></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="recommended-hardware-for-edge-servers-standalone-mediation-servers-and-directors"></a>Hardware recomendado para Servidores de Borda, Servidores de Mediação Autônomo e Diretores

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente de hardware</th>
<th>Recomendado</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><ul>
<li><p>processador dual de 64 bits, Quad-Core, 2,0 gigahertz (GHz) ou superior.</p>
<p>- Ou</p></li>
<li><p>processador de 4 vias com 64 bits, Dual-Core, 2,0 GHz ou superior.</p></li>
</ul>
<p>Processadores Intel Itanium não são suportados para funções de servidor do Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>Memória</p></td>
<td><p>16 gigabytes (GB).</p></td>
</tr>
<tr class="odd">
<td><p>Disco</p></td>
<td><ul>
<li><p>4 ou mais unidades de disco rígido de 10.000 RPM com pelo menos 72 GB de espaço livre em disco.</p>
<p>Os discos devem estar em uma configuração RAID 1 2x.</p>
<p>- Ou</p></li>
<li><p>Drivers de estado sólido (SSDs) que oferecem desempenho semelhante a 4 drivers de disco mecânico de 10.000-RPM.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Rede</p></td>
<td><ul>
<li><p>1 adaptador de rede de porta dupla, 1 Gbps ou superior (2 recomendado, que requer o agrupamento com um único endereço MAC e um único endereço IP). 2 as interfaces de rede são necessárias em servidores de borda e são compatíveis com servidores de mediação autônomos.</p></li>
</ul>
<div>

> [!NOTE]  
> As configurações de duas ou várias bases não têm suporte para diretores.<BR>ILO/DRAC/etc. as conexões não expostas ao sistema operacional e usadas para monitorar e gerenciar o hardware do servidor não constituem um servidor de hospedagem múltipla e, portanto, são compatíveis.


</div>
<p>Os servidores de borda exigirão duas interfaces de rede que sejam adaptadores de rede de duas portas, 1 Gbps ou superior (ou dois adaptadores de rede emparelhados, para um total de quatro, cada par que está sendo agrupado com um único endereço MAC e um único endereço IP, para um total de dois pares).</p>
<p>A instalação de NICs (placas de interface de rede) adicionais para permitir a configuração de um endereço IP PSTN específico é suportada em servidores de mediação autônomos.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

