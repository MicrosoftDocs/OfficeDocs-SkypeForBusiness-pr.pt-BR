---
title: 'Lync Server 2013: Configurando intervalos de porta para seus clientes Microsoft Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Microsoft Lync clients
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f6405ff6738315476efb7ee65f6d5e020a7cf28a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730671"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-microsoft-lync-clients-in-lync-server-2013"></a>Configurando intervalos de porta para seus clientes do Microsoft Lync no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-04-22_

Por padrão, os aplicativos cliente do Lync podem usar qualquer porta entre as portas 1024 e 65535 quando envolvidos em uma sessão de comunicação; Isso ocorre porque intervalos de porta específicos não são habilitados automaticamente para clientes. No entanto, para usar a qualidade do serviço, você precisará reatribuir os vários tipos de tráfego (áudio, vídeo, mídia, compartilhamento de aplicativos e transferência de arquivos) a uma série de intervalos de porta exclusivos. Isso pode ser feito usando o cmdlet Set-CsConferencingConfiguration.

<div>


> [!NOTE]  
> Os usuários finais não podem fazer essas alterações. As alterações de porta só podem ser feitas por administradores usando o cmdlet Set-CsConferencingConfiguration.



</div>

Você pode determinar quais intervalos de portas são atualmente usados para sessões de comunicação executando o seguinte comando no Shell de gerenciamento do Microsoft Lync Server 2013:

    Get-CsConferencingConfiguration

Pressupondo que você não tenha feito nenhuma alteração nas configurações de conferência desde que instalou o Lync Server 2013, você deve obter as informações que incluem esses valores de propriedade:

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

Se você olhar atentamente a saída anterior, verá duas coisas de importância. Primeiro, a propriedade ClientMediaPortRangeEnabled é definida como false:

    ClientMediaPortRangeEnabled : False

Isso é importante porque, quando essa propriedade é definida como falsa, os clientes do Lync usam qualquer porta disponível entre as portas 1024 e 65535 quando envolvidas em uma sessão de comunicação; Isso é verdadeiro independentemente de qualquer outra configuração de porta (por exemplo, ClientMediaPort ou ClientVideoPort). Se você quiser restringir o uso para um conjunto de portas especificado (e isso é algo que você deseja fazer se planejar a implementação da qualidade do serviço), primeiro você deve habilitar os intervalos de porta de mídia do cliente. Isso pode ser feito usando o seguinte comando do Windows PowerShell:

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

O comando anterior habilita os intervalos de porta de mídia do cliente para o conjunto global de definições de configuração de conferência; no entanto, essas configurações também podem ser aplicadas ao escopo do site e/ou ao escopo do serviço (somente para o serviço de servidor de conferência). Para habilitar os intervalos de porta de mídia do cliente para um site ou servidor específico, especifique a identidade desse site ou servidor ao chamar Set-CsConferencingConfiguration:

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

Ou, se preferir, você pode usar esse comando para habilitar simultaneamente intervalos de porta para todas as suas definições de configuração de conferência:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

O segundo motivo da importância que você observará é que a saída do exemplo mostra que, por padrão, os intervalos de porta de mídia definidos para cada tipo de tráfego de rede são idênticos:

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

Para implementar a QoS, cada um desses intervalos de portas precisará ser exclusivo. Por exemplo, você pode configurar os intervalos de porta como este:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de tráfego do cliente</th>
<th>Início da porta</th>
<th>Intervalo de porta</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Áudio</p></td>
<td><p>50020</p></td>
<td><p>cedido</p></td>
</tr>
<tr class="even">
<td><p>Vídeo</p></td>
<td><p>58000</p></td>
<td><p>cedido</p></td>
</tr>
<tr class="odd">
<td><p>Compartilhamento de aplicativos</p></td>
<td><p>42000</p></td>
<td><p>cedido</p></td>
</tr>
<tr class="even">
<td><p>Transferência de arquivos</p></td>
<td><p>42020</p></td>
<td><p>cedido</p></td>
</tr>
</tbody>
</table>


Na tabela anterior, intervalos de porta do cliente representam um subconjunto de intervalos de porta configurados para seus servidores. Por exemplo, nos servidores, o compartilhamento de aplicativos foi configurado para usar as portas 40803 a 49151; nos computadores cliente, o compartilhamento de aplicativos é configurado para usar as portas 42000 a 42019. Isso também é feito principalmente para facilitar a administração da QoS: as portas do cliente não precisam representar um subconjunto de portas usadas no servidor. (Por exemplo, nos computadores cliente, você pode configurar o compartilhamento de aplicativos para usar, digamos, portas 10000 a 10019.) No entanto, é recomendável que os intervalos de porta do cliente sejam um subconjunto de intervalos de porta do servidor.

Além disso, você pode ter notado que 8348 portas foram reservadas para o compartilhamento de aplicativos nos servidores, mas apenas 20 portas foram reservadas para o compartilhamento de aplicativos nos clientes. Isso também é recomendado, mas não é uma regra difícil e rápida. Em geral, você pode considerar cada porta disponível para representar uma única sessão de comunicação: se você tiver portas 100 disponíveis em um intervalo de porta que significa que o computador em questão pode participar, no máximo, 100 sessões de comunicação a qualquer momento. Como os servidores provavelmente participarão de muitas mais conversas do que clientes, faz sentido abrir muito mais portas em servidores do que em clientes. A configuração de mais de 20 portas para compartilhamento de aplicativos em um cliente significa que um usuário pode participar de 20 sessões de compartilhamento de aplicativos no dispositivo especificado e todos ao mesmo tempo. Isso deve provar suficiente para a grande maioria dos seus usuários.

Para atribuir os intervalos de porta precedentes ao conjunto global de configurações de conferência, você pode usar o seguinte comando do Shell de gerenciamento do Lync Server:

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Ou use este comando para atribuir esses mesmos intervalos de portas para todas as suas configurações de conferência:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Os usuários individuais devem fazer logoff do Lync e, em seguida, fazer logon novamente para que as alterações realmente entrem em vigor.

<div>


> [!NOTE]  
> Você também pode habilitar os intervalos de porta de mídia do cliente e, em seguida, atribuir esses intervalos de porta usando um único comando. Por exemplo:<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>



</div>

</div>

<span> </span>

</div>

</div>

</div>

