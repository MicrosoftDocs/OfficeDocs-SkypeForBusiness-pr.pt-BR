---
title: 'Lync Server 2013: planejando roteamento de voz de saída'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning outbound voice routing
ms:assetid: 37c55fa4-175a-4190-b9e4-c2e5ac7b9261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425853(v=OCS.15)
ms:contentKeyID: 48183835
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 852e11c596a541f04fe1dd5771dee193db48e600
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513428"
---
# <a name="planning-outbound-voice-routing-in-lync-server-2013"></a>Planejamento de roteamento de voz de saída no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-21_

O roteamento de chamadas de saída é aplicado a chamadas destinadas a um gateway PSTN (Rede Telefônica Pública Comutada), tronco ou PBX (central privada de comutação telefônica). Quando um usuário faz uma chamada, o servidor normaliza o número de telefone para o formato E.164, se necessário, e tenta correspondê-lo a um URI do SIP. Se o servidor não conseguir fazer a correspondência, ele aplicará a lógica de roteamento de chamadas de saída baseada na cadeia de caracteres de discagem especificada. Especifique essa lógica definindo as configurações do servidor descritas na tabela a seguir.

### <a name="lync-server-outbound-call-routing-settings"></a>Configurações de roteamento de chamadas de saída do Lync Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Objeto</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Plano de discagem</p></td>
<td><p>Um plano de discagem é um conjunto nomeado de regras de normalização que converte números de telefone de um local nomeado, usuário individual ou objeto de contato em um formato padrão único (E.164) para fins de roteamento de chamadas e autorização.</p></td>
</tr>
<tr class="even">
<td><p>Regra de normalização</p></td>
<td><p>As regras de normalização definem como os números de telefone expressos em vários formatos são roteados para cada local, usuário ou objeto de contato especificado. A mesma cadeia de caracteres de discagem pode ser interpretada e convertida de maneira diferente, conforme o local do qual é discada e da pessoa ou objeto de contato que está fazendo a chamada. Um conjunto de regras de normalização associadas a um local específico constitui um plano de discagem.</p></td>
</tr>
<tr class="odd">
<td><p>Política de voz</p></td>
<td><p>Uma política de voz associa um ou mais registros de uso de PSTN a um usuário ou grupo de usuários. Também fornece uma lista de recursos de chamada que você pode ativar ou desativar.</p></td>
</tr>
<tr class="even">
<td><p>Registro de uso de PSTN</p></td>
<td><p>Um registro de uso de PSTN especifica uma classe de chamada (por exemplo, interna, local ou interurbana) que pode ser feita por vários usuários ou grupos de usuários em uma organização.</p></td>
</tr>
<tr class="odd">
<td><p>Rota de chamada</p></td>
<td><p>Uma rota de chamada associa os números de telefone de destino com troncos específicos e registros de uso de PSTN. Um gateway PSTN é considerado um tronco.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>Nesta seção

Esta seção fornece diretrizes para definir as seguintes configurações do servidor de roteamento de chamadas de saída

  - <span></span>  
    [Planos de discagem e regras de normalização no Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md)

  - <span></span>  
    [Políticas de voz no Lync Server 2013](lync-server-2013-voice-policies.md)

  - <span></span>  
    [Registros de uso de PSTN no Lync Server 2013](lync-server-2013-pstn-usage-records.md)

  - <span></span>  
    [Rotas de voz no Lync Server 2013](lync-server-2013-voice-routes.md)

</div>

<div>

## <a name="see-also"></a>Confira também


[Tronco SIP no Lync Server 2013](lync-server-2013-sip-trunking.md)  
[Conexões SIP diretas no Lync Server 2013](lync-server-2013-direct-sip-connections.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

