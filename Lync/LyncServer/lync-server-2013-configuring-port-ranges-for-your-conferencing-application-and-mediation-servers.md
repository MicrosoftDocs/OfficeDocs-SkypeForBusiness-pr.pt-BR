---
title: 'Lync Server 2013: Configurando intervalos de porta para seus servidores de conferência, aplicativo e mediação'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Conferencing, Application, and Mediation servers
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
ms.date: 05/01/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54aab5efbca06d918cc2dbeccc0e36aee9d4abf8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a>Configurando intervalos de porta no Lync Server 2013 para servidores de conferência, aplicativo e mediação

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2015-04-30_

Para implementar a qualidade do serviço, você deve configurar intervalos de porta idênticos para compartilhamento de áudio, vídeo e aplicativos em seus servidores de conferência, aplicativo e mediação; Além disso, esses intervalos de portas não devem ser sobrepostos de maneira alguma. Para usar um exemplo simples, suponha que você use as portas 10000 a 10999 para vídeo em seus servidores de conferência. Isso significa que você também deve reservar as portas de 10000 a 10999 para o vídeo em seus servidores de aplicativo e mediação. Se você não fizer isso, a QoS não funcionará conforme o esperado.

Da mesma forma, suponha que você reserve portas de 10000 a 10999 para vídeo, mas Reserve portas de 10500 a 11999 para áudio. Isso pode criar problemas para a qualidade do serviço, pois os intervalos de porta se sobrepõem. Com a QoS, cada modalidade deve ter um conjunto exclusivo de portas: se você usar as portas 10000 a 10999 para vídeo, será necessário usar um intervalo diferente (por exemplo, 11000 a 11999 para áudio).

Por padrão, os intervalos de porta de áudio e vídeo não se sobrepõem no Microsoft Lync Server 2013; no entanto, os intervalos de porta atribuídos ao compartilhamento de aplicativos se sobrepõem com os intervalos de porta de áudio e vídeo. (Que, por sua vez, significa que nenhum desses intervalos é exclusivo.) Você pode verificar os intervalos de porta existentes para seus servidores de conferência, aplicativo e mediação executando os três comandos a seguir no Shell de gerenciamento do Lync Server 2013:

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

<div>


> [!WARNING]  
> Como você pode ver nos comandos anteriores, cada tipo de porta – áudio, vídeo e compartilhamento de aplicativos – recebe dois valores de propriedade separados: o início da porta e a contagem de portabilidade. A porta Start indica a primeira porta usada para essa modalidade; por exemplo, se o início da porta de áudio for igual a 50000, isso significa que a primeira porta usada para tráfego de áudio é a porta 50000. Se o número da porta de áudio for 2 (que não é um valor válido, mas é usado aqui para fins de ilustração), isso significa que apenas duas portas são alocadas para áudio. Se a primeira porta for a porta 50000 e houver um total de duas portas, isso significa que a segunda porta deve ser a porta 50001 (intervalos de porta devem ser contíguos). Como resultado, o intervalo de porta para áudio seria a porta 50000 a 50001, inclusive.<BR>Observe que o servidor de aplicativos e o servidor de mediação também dão suporte a QoS para áudio; Você não precisa alterar as portas de vídeo ou de compartilhamento de aplicativos em seus servidores de aplicativos ou servidores de mediação.



</div>

Se você executar os três comandos anteriores, verá que os valores de porta padrão para o Lync Server 2013 são configurados da seguinte maneira:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Propriedade</th>
<th>Servidor de conferência</th>
<th>Servidor de aplicativos</th>
<th>Servidor de Mediação</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AudioPortStart</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
</tr>
<tr class="even">
<td><p>AudioPortCount</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>VideoPortStart</p></td>
<td><p>57501</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>VideoPortCount</p></td>
<td><p>8034</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p>ApplicationSharingPortStart</p></td>
<td><p>49152</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>ApplicationSharingPortCount</p></td>
<td><p>16383</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>


Conforme observado anteriormente, ao configurar as portas do Lync Server para QoS, certifique-se de que: 1) as configurações da porta de áudio sejam idênticas nos seus servidores de conferência, aplicativo e mediação; e, 2) os intervalos de porta não se sobrepõem. Se você olhar atentamente para a tabela anterior, verá que os intervalos de porta são idênticos nos três tipos de servidor. Por exemplo, a porta de áudio inicial é definida como a porta 49152 em cada tipo de servidor e o número total de portas reservadas para áudio em cada servidor também é idêntica: 8348. No entanto, os intervalos de porta sobrepõem: as portas de áudio começam na porta 49152, mas as portas se reservam para o compartilhamento de aplicativos. Para fazer uso ideal da qualidade do serviço, o compartilhamento de aplicativos deve ser reconfigurado para usar um intervalo de porta exclusivo. Por exemplo, você pode configurar o compartilhamento de aplicativos para iniciar na porta 40803 e para usar as portas do 8348. (Por que 8348 portas? Se você adicionar esses valores juntos--40803 + 8348-------------------------49150 40803-- Como as portas de áudio não começam até a porta 49152, você não terá mais nenhum intervalo de portas sobrepostos.)

Depois de selecionar o novo intervalo de porta para compartilhamento de aplicativos, você pode fazer a alteração usando o cmdlet Set-CsConferencingServer. Essa alteração não precisa ser feita em seus servidores de aplicativos ou em seus servidores de mediação, pois esses servidores não manipulam o tráfego de compartilhamento de aplicativos. Você só precisa alterar valores de porta nestes servidores se decidir reatribuir as portas usadas para tráfego de áudio.

Para modificar os valores de porta para compartilhamento de aplicativos em um único servidor de conferência, execute um comando semelhante a isso dentro do Shell de gerenciamento do Lync Server:

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

Se você quiser fazer essas alterações em todos os seus servidores de conferência, poderá executar esse comando em vez disso:

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

Depois de alterar as configurações de porta, você deve parar e reiniciar cada serviço afetado pelas alterações.

Não é obrigatório que seus servidores de conferência, servidores de aplicativos e servidores de mediação compartilhem exatamente o mesmo intervalo de porta; o único requisito verdadeiro é que você se reservasse intervalos de porta exclusivos em todos os seus servidores. No entanto, a administração normalmente será mais fácil se você usar o mesmo conjunto de portas em todos os seus servidores.

</div>

<span> </span>

</div>

</div>

</div>

