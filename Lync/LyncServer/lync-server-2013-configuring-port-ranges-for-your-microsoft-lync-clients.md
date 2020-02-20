---
title: 'Lync Server 2013: Configurando intervalos de portas para seus clientes Microsoft Lync'
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
ms.openlocfilehash: f16fa3b16a992ce15f16e7413a59525e55ddba75
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147284"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-microsoft-lync-clients-in-lync-server-2013"></a>Configurando intervalos de portas para seus clientes Microsoft Lync no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-04-22_

Por padrão, os aplicativos cliente do Lync podem usar qualquer porta entre as portas 1024 e 65535 quando envolvido em uma sessão de comunicação; Isso ocorre porque intervalos de portas específicos não são automaticamente habilitados para clientes. Para poder usar a Qualidade do Serviço, no entanto, você precisará reatribuir os vários tipos de tráfego (áudio, vídeo, mídia, compartilhamento de aplicativos e transferência de arquivos) para uma série de intervalos de porta únicos. Isto pode ser realizado usando o cmdlet Set-CsConferencingConfiguration.

<div>


> [!NOTE]  
> Os usuários finais não podem fazer essas alterações por conta própria. As alterações de porta só podem ser feitas por administradores usando o cmdlet Set-CsConferencingConfiguration.



</div>

Você pode determinar quais intervalos de portas são usados atualmente para sessões de comunicação executando o seguinte comando no Shell de gerenciamento do Microsoft Lync Server 2013:

    Get-CsConferencingConfiguration

Supondo que você não tenha feito nenhuma alteração nas configurações de conferência desde que você instalou o Lync Server 2013, você deve obter as informações que incluem estes valores de propriedade:

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

Se você verificar o resultado anterior, você verá duas coisas de importância. Primeiro, a propriedade ClientMediaPortRangeEnabled é definida para False:

    ClientMediaPortRangeEnabled : False

Isso é importante porque, quando essa propriedade é definida como false, os clientes do Lync usarão qualquer porta disponível entre as portas 1024 e 65535 quando envolvidas em uma sessão de comunicação; Isso é verdadeiro independentemente de qualquer outra configuração de porta (por exemplo, ClientMediaPort ou ClientVideoPort). Se você deseja restringir o uso para um conjunto de portas especificado (e isto é algo que você deseja fazer se planeja implementar a Qualidade do Serviço), você deve primeiro habilitar os intervalos de porta de mídia do cliente. Isso pode ser feito usando o seguinte comando do Windows PowerShell:

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

O comando anterior habilita os intervalos de porta de mídia do cliente para o conjunto global de definições de configuração de conferência; no entanto, estas configurações também podem ser aplicadas para o escopo local e/ou de serviço (apenas para o serviço do Servidor de Conferência). Para habilitar os intervalos de porta de mídia do cliente para um site ou servidor específico, defina a Identidade deste site ou servidor ao chamar Set-CsConferencingConfiguration:

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

Em alternativa, é possível usar este comando para habilitar simultaneamente intervalos de portas para todas as suas definições de configuração de conferência:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

A segunda coisa importante que você observará é o resultado de amostra mostrando que, por padrão, o conjunto de intervalos da porta de mídia para cada tipo de tráfego de rede são idênticos:

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

Para poder implementar o QoS, cada um destes intervalos de porta precisarão ser exclusivos. Por exemplo, você pode configurar os intervalos de porta desta forma:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de Tráfego do Cliente</th>
<th>Início da Porta</th>
<th>Intervalo da Porta</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Áudio</p></td>
<td><p>50020</p></td>
<td><p>508</p></td>
</tr>
<tr class="even">
<td><p>Vídeo</p></td>
<td><p>58000</p></td>
<td><p>508</p></td>
</tr>
<tr class="odd">
<td><p>Compartilhamento de aplicativo</p></td>
<td><p>42000</p></td>
<td><p>508</p></td>
</tr>
<tr class="even">
<td><p>Transferência de arquivos</p></td>
<td><p>42020</p></td>
<td><p>508</p></td>
</tr>
</tbody>
</table>


Na tabela anterior, os intervalos da porta do cliente representam um subconjunto dos intervalos de porta configurados para seus servidores. Por exemplo, nos servidores, o compartilhamento de aplicativos foi configurado para usar as portas 40803 a 49151; nos computadores clientes, o compartilhamento de aplicativos é configurado para usar as portas 42000 a 42019. Isto também é realizado principalmente para tornar a administração do QoS mais fácil: as portas do cliente não precisam representar um conjunto de portas usadas no servidor. (Por exemplo, em computadores clientes que você pode configurar o compartilhamento de aplicativos a usar, digamos, as portas 10000 a 10019.) No entanto, é recomendado que você torne seus intervalos da porta do cliente um subconjunto dos seus intervalos de porta do servidor.

Além disso, você pode observar que 8348 portas foram definidas para compartilhamento de aplicativos nos servidores, mas apenas 20 portas foram separadas para compartilhamento de aplicativos nos clientes. Isto também é recomendado, mas não é uma regra rígida. Em geral, você pode considerar cada porta disponível para representar uma única sessão de comunicação: se você possui 100 portas disponíveis em um intervalo de porta, significa que o computador em questão pode participar, no máximo, de 100 sessões de comunicação em um determinado momento. Como os servidores provavelmente terão parte em muito mais conversas do que os clientes, faz sentido abrir mais portas em servidores do que em clientes.Configurar outras 20 portas para compartilhamento de aplicativo em um cliente significa que um usuário pode participar de 20 sessões de compartilhamento de aplicativos no dispositivo especificado e tudo ao mesmo tempo. Isso deve ser suficiente para a grande maioria dos seus usuários.

Para atribuir os intervalos de portas precedentes à sua coleção global de definições de configuração de conferência, você pode usar o seguinte comando do Shell de gerenciamento do Lync Server:

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Em alternativa, use este comando para atribuir estes mesmos intervalos de porta para todas suas definições de configuração de conferência:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Os usuários individuais devem fazer logoff do Lync e, em seguida, fazer logon novamente para que essas alterações entrem em vigor.

<div>


> [!NOTE]  
> Também é possível habilitar intervalos de porta da mídia do cliente e atribuir estes intervalos de porta usando um único comando. Por exemplo:<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>



</div>

</div>

<span> </span>

</div>

</div>

</div>

