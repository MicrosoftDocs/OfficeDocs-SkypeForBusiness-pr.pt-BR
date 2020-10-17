---
title: 'Lync Server 2013: Configurando intervalos de portas para seus servidores de conferência, aplicativos e mediação'
description: 'Lync Server 2013: Configurando intervalos de portas para seus servidores de conferência, aplicativos e mediação.'
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
ms.openlocfilehash: eb3f51e42c86b667b6990f41640bf09e12e840c2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558757"
---
# <a name="configuring-port-ranges-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a>Configurando intervalos de portas no Lync Server 2013 para seus servidores de conferência, aplicativos e mediação

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2015-04-30_

A fim de implementar a Qualidade do serviço, você deve configurar intervalos de porta idênticos para áudio, vídeo e compartilhamento de aplicativo no seu servidor de Conferência, de Aplicativo e de Mediação; além disso, esses intervalos de porta não devem se sobrepor de nenhuma maneira. Para usar um exemplo simples, imagine que você utilize as portas de 10000 a 10999 para vídeo nos seus servidores de Conferência. Isso significa que você deve reservar as portas de 10000 a 10999 para vídeo nos seus servidores de Aplicativo e de Mediação. Caso não o faça, a Qualidade do serviço não funcionará como esperado.

De forma semelhante, imagine que você reserva as portas de 10000 a 10999 para vídeo e, em seguida, reserva as portas de 10500 a 11999 para áudio. Isso pode gerar problemas na Qualidade do serviço porque os intervalos de porta se sobrepõem. Com a QoS, cada modalidade deve possuir um conjunto de portas único: se usar as portas de 10000 a 10999 para vídeo, então você deverá usar um intervalo diferente (por exemplo, de 11000 a 11999 para áudio).

Por padrão, os intervalos de porta de áudio e vídeo não se sobrepõem no Microsoft Lync Server 2013; no entanto, os intervalos de portas atribuídos ao compartilhamento de aplicativos se sobrepõem com os intervalos de porta de áudio e vídeo. (O que, por sua vez, significa que nenhum desses intervalos é exclusivo.) Você pode verificar os intervalos de portas existentes para seus servidores de conferência, aplicativo e de mediação executando os seguintes três comandos de dentro do Shell de gerenciamento do Lync Server 2013:

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

<div>


> [!WARNING]  
> Como você pode observar nos comandos precedentes, é atribuído a cada tipo de porta – áudio, vídeo e compartilhamento de aplicativo – dois valores separados de propriedade: a porta inicial e a contagem de porta. A porta inicial indica a primeira porta usada por essa modalidade; por exemplo, se a porta inicial de áudio é igual a 50000, significa que a primeira porta usada para o tráfego de áudio é a porta 50000. Se a porta de contagem de áudio é 2 (valor inválido, mas é usado aqui pelo seu valor ilustrativo), significa que apenas duas portas estão alocadas para o áudio. Se a primeira porta é a porta 50000 e há um total de duas portas, significa que a segunda porta será a porta 50001 (os intervalos de porta devem ser contíguos). Dessa forma, o intervalo de porta para áudio seria da porta 50000 até a 50001, ambas incluídas.<BR>Observe que o servidor de Aplicativo e o servidor de Mediação suportam QoS somente para áudio; você não precisa modificar as portas de vídeo ou as de compartilhamento de aplicativo nos seus servidores de Aplicativo ou de Mediação.



</div>

Se você executar os três comandos anteriores, verá que os valores de porta padrão para o Lync Server 2013 estão configurados da seguinte maneira:


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
<th>Servidor de Conferência</th>
<th>Servidor de Aplicativo</th>
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


Conforme observado anteriormente, ao configurar as portas do Lync Server para QoS, você deve garantir que: 1) as configurações de porta de áudio são idênticas nos seus servidores de conferência, aplicativo e mediação; e, 2) os intervalos de porta não se sobrepõem. Se você observar com atenção a tabela anterior, verá que os intervalos de porta são idênticos nos três tipos de servidores. Por exemplo, a porta inicial de áudio está configurada para a porta 49152 em cada tipo de servidor e o número total de portas reservadas para áudio em cada servidor também é igual: 8348. No entanto, os intervalos de porta se sobrepõem: as portas de áudio iniciam na porta 49152, mas o mesmo acontece com as portas configuradas para o compartilhamento de aplicativo. Para usar a Qualidade do serviço de forma ótima, o compartilhamento de aplicativo deve ser reconfigurado para que use um único intervalo de porta. Por exemplo, você poderia configurar o compartilhamento de aplicativo para iniciar na porta 40803 e para usar as portas 8348. (Por que as portas 8348? Se você adicionar esses valores juntos--40803 + 8348--isso significa que o compartilhamento de aplicativos usará as portas 40803 através da porta 49150. Já que as portas de áudio não começam até a porta 49152, você não terá mais nenhum intervalo de porta em sobreposição.)

Após selecionar os novos intervalos de porta do compartilhamento de aplicativo, você será capaz de realizar suas modificações por meio do cmdlet Set-CsConferencingServer. Essa alteração não precisa ser feita no seus servidores de Aplicativo ou de Mediação, já que esses servidores não manipulam o tráfego do compartilhamento de aplicativos. Você precisa alterar somente os valores de porta nesses servidores caso decida reatribuir as portas usadas no tráfego de áudio.

Para modificar os valores de porta para compartilhamento de aplicativos em um único servidor de conferência, execute um comando semelhante a este no Shell de gerenciamento do Lync Server:

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

Se deseja realizar essas alterações em todos os seus servidores de Conferência, você pode executar esse comando:

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

Após alterar as configurações de porta, você deverá parar e, em seguida, reiniciar cada serviço afetado pelas alterações.

Não é obrigatório que seus servidores de Conferência, de Aplicativo e de Mediação compartilhem os mesmos intervalos de porta; o único requisito é que você configure intervalos de porta únicos em todos os servidores. No entanto, a administração será normalmente mais fácil se você usar os mesmo conjuntos de portas em todos os servidores.

</div>

<span> </span>

</div>

</div>

</div>

