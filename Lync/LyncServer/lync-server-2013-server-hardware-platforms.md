---
title: 'Lync Server 2013: Plataformas de hardware de servidor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server hardware platforms
ms:assetid: c964c1c0-0153-472b-88ad-a38866e0df0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398835(v=OCS.15)
ms:contentKeyID: 48185395
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2682d0d8636c024dee4151842a143e65b11d48c5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822122"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-hardware-platforms-for-lync-server-2013"></a>Plataformas de hardware de servidor para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2016-07-28_

As funções de servidor do Lync Server 2013 e os computadores executando as ferramentas administrativas do Lync Server exigem hardware de 64 bits.

O hardware específico usado para a implantação do Lync Server 2013 pode variar, dependendo dos requisitos de tamanho e uso. Esta seção descreve o hardware recomendado. Embora estas sejam recomendações, não obrigações, o uso de hardware que não atende a estas recomendações pode resultar em problemas significativos de desempenho e outros problemas.

<div>

## <a name="recommended-hardware-platform"></a>Plataforma de Hardware Recomendada

Para obter o melhor desempenho, recomendamos que você execute o Lync Server em servidores com hardware que atenda aos requisitos na tabela a seguir. Se usar um hardware menos poderoso, você poderá enfrentar problemas de funcionalidade ou mau desempenho. Observe que esses requisitos de hardware são maiores do que os das versões anteriores do Lync Server, principalmente porque no Lync Server 2013, todos os servidores de front-end executam o SQL Server.

<div>


> [!NOTE]  
> O agrupamento da NIC tem suporte e deve ser transparente para o Lync Server. Para obter detalhes, consulte <A href="http://go.microsoft.com/fwlink/p/?linkid=389910">servidor de comunicações ou Lync Server e agrupamento de adaptadores de rede</A>.



</div>

### <a name="recommended-hardware-for-front-end-servers-back-end-servers-standard-edition-servers-persistent-chat-servers-and-persistent-chat-store-and-persistent-chat-compliance-store-back-end-server-roles-for-persistent-chat-server"></a>Hardware recomendado para Servidores de Front-End, Servidores de Back-End, Servidores de Edição Padrão, Servidores de Chat Persistente e Armazenamento de Chat Persistente e Armazenamento de Conformidade de Chat Persistente (Funções de Servidores de Back-End para Servidores de Chat Persistente)

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
<td><p>Processador duplo de 64 bits, núcleo hexagonal, 2.26 gigahertz (GHz) ou superior.</p>
<p>Não há suporte para processadores Intel Itanium para funções de servidor do Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>Memória</p></td>
<td><p>32 gigabytes (GB).</p></td>
</tr>
<tr class="odd">
<td><p>Disco</p></td>
<td><ul>
<li><p>Oito ou mais unidades de disco rígido de 10.000 RPM com pelo menos 72 GB de espaço em disco livre.</p>
<p>Dois dos discos devem usar RAID 1 e seis devem usar RAID 10.</p>
<p>-OR</p></li>
<li><p>Drivers de estado sólido (SSDs) que oferecem desempenho semelhante a 8 drivers de disco mecânico de 10.000-RPM.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Rede</p></td>
<td><ul>
<li><p>1 adaptador de rede de porta dupla, 1 Gbps ou superior (2 recomendados, que exige agrupamento com um único endereço MAC e um único endereço IP).</p>
<div>

> [!NOTE]  
> Não há suporte para configurações de duas ou várias bases para servidores front-end, servidores back-end, servidores de edição padrão e servidores de chat persistente.<BR>ILO/DRAC/etc. as conexões não expostas ao sistema operacional e usadas para monitorar e gerenciar o hardware do servidor não constituem um servidor de hospedagem múltipla e, assim, é compatível.


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
<p>-OR</p></li>
<li><p>processador de 4 vias de 64 bits, Dual-Core, 2,0 GHz ou superior.</p></li>
</ul>
<p>Não há suporte para processadores Intel Itanium para funções de servidor do Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>Memória</p></td>
<td><p>16 gigabytes (GB).</p></td>
</tr>
<tr class="odd">
<td><p>Disco</p></td>
<td><ul>
<li><p>4 ou mais 10.000 unidades de disco rígido RPM com pelo menos 72 GB de espaço livre em disco.</p>
<p>Os discos devem estar em uma configuração 2x RAID 1.</p>
<p>-OR</p></li>
<li><p>Unidades de estado sólido (SSDs) que ofereçam desempenho semelhante a quatro unidades de disco mecânico de 10.000 RPM.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Rede</p></td>
<td><ul>
<li><p>1 adaptador de rede de porta dupla, 1 Gbps ou superior (2 recomendados, que exige agrupamento com um único endereço MAC e um único endereço IP). duas interfaces de rede são necessárias em servidores de borda e têm suporte em servidores de mediação autônomos.</p></li>
</ul>
<div>

> [!NOTE]  
> Não há suporte para configurações de duas ou várias bases para os directors.<BR>ILO/DRAC/etc. as conexões não expostas ao sistema operacional e usadas para monitorar e gerenciar o hardware do servidor não constituem um servidor de hospedagem múltipla e, assim, é compatível.


</div>
<p>Os servidores de borda exigem duas interfaces de rede que sejam adaptadores de rede de duas portas, 1 Gbps ou superior (ou dois adaptadores de rede emparelhados, para um total de quatro, cada par sendo agrupado com um único endereço MAC e um único endereço IP, para um total de dois pares).</p>
<p>A instalação de placas de interface de rede adicionais (NICs) para permitir a configuração de um endereço IP PSTN específico tem suporte em servidores de mediação autônomos.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

