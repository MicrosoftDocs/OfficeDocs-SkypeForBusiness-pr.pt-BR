---
title: 'Lync Server 2013: Configurando intervalos de porta para seus servidores de borda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Edge Servers
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
ms.date: 07/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6eddf59f6fe4b2575e0e7d70adddb2e94c90e05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-edge-servers-in-lync-server-2013"></a>Configurando intervalos de porta para seus servidores de borda no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2015-07-24_

Com os servidores de borda, você não precisa configurar intervalos de porta separados para compartilhamento de áudio, vídeo e aplicativos; da mesma forma, os intervalos de porta usados para servidores de borda não precisam corresponder aos intervalos de porta usados com os servidores de conferência, aplicativo e mediação. Antes de continuarmos com o nosso exemplo, é importante enfatizar que, enquanto essa opção existe, recomendamos que você não altere os intervalos de porta, pois isso pode afetar negativamente alguns cenários se você sair do intervalo de porta 50000.

Por exemplo, suponha que você tenha configurado seus servidores de conferência, aplicativo e mediação para usar estes intervalos de porta:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de pacote</th>
<th>Porta inicial</th>
<th>Número de portas reservadas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Compartilhamento de aplicativos</p></td>
<td><p>40803</p></td>
<td><p>8348</p></td>
</tr>
<tr class="even">
<td><p>Áudio</p></td>
<td><p>49152</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>Vídeo</p></td>
<td><p>57500</p></td>
<td><p>8034</p></td>
</tr>
<tr class="even">
<td><p><strong>Totais</strong></p></td>
<td><p>--</p></td>
<td><p>24730</p></td>
</tr>
</tbody>
</table>


Como você pode ver, os intervalos de portabilidade de áudio, vídeo e compartilhamento de aplicativos começam na porta 40803 e englobam um total de 24732 portas. Se preferir, você pode configurar um servidor de borda específico para usar esses valores de porta gerais executando um comando semelhante a este de dentro do Shell de gerenciamento do Lync Server:

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

Ou use o seguinte comando para configurar simultaneamente todos os servidores de borda em sua organização:

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

Você pode verificar as configurações de porta atuais para seus servidores de borda usando o comando do Shell de gerenciamento do Lync Server:

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

Novamente, enquanto fornecemos essas opções, recomendamos que você deixe as coisas como elas são para a configuração de portabilidade.

</div>

<span> </span>

</div>

</div>

</div>

