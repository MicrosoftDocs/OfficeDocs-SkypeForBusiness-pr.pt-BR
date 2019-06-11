---
title: 'Lync Server 2013: Registros de uso de PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN usage records
ms:assetid: b5f624aa-abe8-455b-a8e3-c228be230463
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412878(v=OCS.15)
ms:contentKeyID: 48185188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e32000f1664591a3e054d058ced4f996a98f27cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-usage-records-in-lync-server-2013"></a>Registros de uso de PSTN no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-23_

O planejamento dos registros de uso de PSTN consiste principalmente em listar todas as permissões de chamadas em uso na organização, desde o CEO até os funcionários temporários, os consultores e a equipe contingente. Esse processo também oferece uma oportunidade de reexaminar as permissões de chamadas existentes e revisá-las. Você pode criar registros de uso de PSTN somente para as permissões de chamada que se aplicam aos usuários de Enterprise Voice previstos, mas uma solução de maior alcance pode ser criar registros de uso de PSTN para todas as permissões de chamada, independentemente de talvez alguns não aplicar-se ao grupo de usuários a ser habilitado para o Enterprise Voice. Se as permissões de chamada forem alteradas ou novos usuários com permissões de chamada diferentes forem adicionados, você já terá criado os registros de uso de PSTN necessários.

A tabela a seguir mostra um quadro típico de uso de PSTN.

### <a name="pstn-usage-records"></a>Registros de uso de PSTN

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Atributo do telefone</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Local</p></td>
<td><p>Chamadas locais</p></td>
</tr>
<tr class="even">
<td><p>Long-Distance</p></td>
<td><p>Chamadas interurbanas</p></td>
</tr>
<tr class="odd">
<td><p>International</p></td>
<td><p>Chamadas internacionais</p></td>
</tr>
<tr class="even">
<td><p>Delhi</p></td>
<td><p>Funcionários de Délhi em tempo integral</p></td>
</tr>
<tr class="odd">
<td><p>Redmond</p></td>
<td><p>Funcionários de Redmond em tempo integral</p></td>
</tr>
<tr class="even">
<td><p>RedmondTemps</p></td>
<td><p>Funcionários temporários de Redmond</p></td>
</tr>
<tr class="odd">
<td><p>Zurich</p></td>
<td><p>Funcionários de Zurique em tempo integral</p></td>
</tr>
</tbody>
</table>


Sozinhos, os registros de uso do PSTN não fazem nada. Para que funcionem, é necessário associá-los ao seguinte:

  - Políticas de voz, que são atribuídas a usuários.

  - Rotas, que são atribuídas a números de telefone.

Para obter detalhes sobre políticas e rotas de voz, consulte [políticas de voz no Lync Server 2013](lync-server-2013-voice-policies.md) e [rotas de voz no Lync Server 2013](lync-server-2013-voice-routes.md). Para obter detalhes sobre como criar e configurá-los, consulte Configurando [rotas de voz para chamadas de saída no Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).

</div>

<span> </span>

</div>

</div>

</div>

