---
title: 'Lync Server 2013: teste o número de telefone em uma rota de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test telephone number against a voice route
ms:assetid: 9a77ed6d-9394-4bef-9344-3d91b6959b97
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725211(v=OCS.15)
ms:contentKeyID: 63969631
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d4105b54c7d5b745efddeeb961960c402aaa349
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a>Teste o número de telefone em uma rota de voz no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-05-20_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Cronograma de verificação</p></td>
<td><p>Mensal</p></td>
</tr>
<tr class="even">
<td><p>Ferramenta de teste</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Permissões necessárias</p></td>
<td><p>Quando executado localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</p>
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsVoiceRoute. Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

As rotas de voz trabalham em conjunto com as políticas de voz para ajudar a rotear chamadas do Enterprise Voice para a rede PSTN. Cada rota de voz inclui uma expressão regular (um padrão de número) que identifica os números de telefone que serão roteados por meio de uma determinada rota de voz: a rota será capaz de manipular os números de telefone correspondentes a essa expressão regular. Por exemplo, uma rota de voz pode ter uma expressão regular que a permita manipular qualquer número de 10 dígitos. Isso significa que a rota seria capaz de manipular um número de telefone como este:

  - 2065551219

A rota não seria capaz de manipular um dos dois números a seguir, e nenhum deles tem 10 dígitos:

  - 5551219

  - 12065551219

O cmdlet Test-CsVoiceRoute verifica se uma determinada rota de voz pode direcionar um número de telefone especificado.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

Verificar se a capacidade de uma rota de voz para direcionar um número de telefone especificado é um processo de duas etapas. Primeiro, você precisa usar o cmdlet Get-CsVoiceRoute para retornar uma instância dessa rota de voz e, em seguida, usar o cmdlet Test-CsVoiceRoute para verificar a capacidade dessa rota para manipular o número de telefone de destino. Por exemplo, esse comando verifica se a rota de voz RedmondVoiceRoute pode direcionar o número de telefone 2065551219:

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

Observe que o número de telefone deve ser digitado, pois você espera que os usuários disquem esse número. Por exemplo, se você não espera que os usuários incluam o código do país e o código de área ao discar, use uma sintaxe semelhante a esta:

`-TargetNumber "5551219"`

Nesse caso, o número de destino deixará o código de país e o código de área.

Para usar um único comando para testar todas as rotas de voz em relação a um número de destino especificado, use a sintaxe como a seguinte:

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

Para obter mais informações, consulte a documentação da ajuda para o cmdlet Test-CsVoiceRoute.

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinação do sucesso ou falha

Se a rota de voz puder direcionar o número de telefone de destino, o cmdlet Test-CsVoiceRoute apenas retornará o valor true:

MatchesPattern

\--------------

Verdadeiro

Isso significa que a rota pode manipular números semelhantes ao número de destino. Se a rota de voz não puder manipular o número de destino, teste-CsVoiceRoute retornará o valor false:

MatchesPattern

\--------------

Falso

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Ao testar as rotas de voz, "falha" é um termo relativo. Nesse caso, não significa que a rota está de alguma forma "interrompida;" em vez disso, significa que a rota não pode manipular o número de destino. Isso pode ser porque a rota de voz foi configurada incorretamente. Também pode significar que a rota nunca se destina a manipular números usando esse padrão. Por exemplo, se você não quiser direcionar chamadas para outros países em uma determinada rota, essa rota pode ser configurada para rejeitar todos os números de telefone que incluem um código de país. Se Test-CsVoiceRoute retornar false quando você espera retornar true, verifique se digitou o número de destino corretamente. Se você fez isso, use um comando semelhante a este para exibir o NumberPattern configurado para a rota:

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Select-Object NumberPattern`

</div>

<div>

## <a name="see-also"></a>Confira também


[Test-CsVoiceRoute](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

