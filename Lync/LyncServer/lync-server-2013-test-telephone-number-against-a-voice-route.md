---
title: 'Lync Server 2013: testar número de telefone em uma rota de voz'
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
ms.openlocfilehash: 3fccdcb5dfc0fe52c2c0dcf80f7f6a374e35a39e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41985066"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a>Testar número de telefone em uma rota de voz no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-05-20_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Agenda de verificação</p></td>
<td><p>Mensal</p></td>
</tr>
<tr class="even">
<td><p>Ferramenta de teste</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Permissões obrigatórias</p></td>
<td><p>Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</p>
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsVoiceRoute. Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

As rotas de voz trabalham juntas com políticas de voz para ajudar a rotear chamadas do Enterprise Voice para a rede PSTN. Cada rota de voz inclui uma expressão regular (um padrão de número) que identifica os números de telefone que serão roteados por meio de uma determinada rota de voz: a rota será capaz de lidar com os números de telefone que correspondam a essa expressão regular. Por exemplo, uma rota de voz pode ter uma expressão regular que permite manipular qualquer número de 10 dígitos. Isso significa que a rota seria capaz de lidar com um número de telefone como este:

  - 2065551219

A rota não seria capaz de lidar com um dos dois números a seguir, que não tem 10 dígitos:

  - 5551219

  - 12065551219

O cmdlet Test-CsVoiceRoute verifica se uma determinada rota de voz pode rotear um número de telefone especificado.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

Verificar a capacidade de uma rota de voz de rotear um número de telefone especificado é um processo de duas etapas. Primeiro é necessário usar o cmdlet Get-CsVoiceRoute para retornar uma instância dessa rota de voz e, em seguida, você precisa usar o cmdlet Test-CsVoiceRoute para verificar a capacidade da rota de lidar com o número de telefone de destino. Por exemplo, este comando verifica se a rota de voz do RedmondVoiceRoute pode rotear o número de telefone 2065551219:

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

Observe que o número de telefone deve ser digitado, já que você espera que os usuários disquem esse número. Por exemplo, se você não espera que os usuários incluam o código do país e o código de área ao discar, use uma sintaxe semelhante a esta:

`-TargetNumber "5551219"`

Nesse caso, o número de destino deixa o código do país e o código de área.

Para usar um único comando para testar todas as rotas de voz em relação a um número de destino especificado, use uma sintaxe como a seguinte:

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

Para obter mais informações, consulte a documentação de ajuda para o cmdlet Test-CsVoiceRoute.

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

Se a rota de voz puder encaminhar o número de telefone de destino, o cmdlet Test-CsVoiceRoute apenas retornará o valor true:

MatchesPattern

\--------------

True

Isso significa que a rota pode lidar com números semelhantes ao número de destino. Se a rota de voz não puder lidar com o número de destino, Test-CsVoiceRoute retornará o valor false:

MatchesPattern

\--------------

Falso

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Ao testar rotas de voz, "falha" é um termo relativo. Nesse caso, não significa que a rota está de alguma forma "interrompida"; em vez disso, apenas significa que a rota não pode lidar com o número de destino. Isso pode ocorrer porque a rota de voz foi configurada incorretamente. Também pode significar que a rota nunca se destinava a lidar com números usando esse padrão. Por exemplo, se você não deseja encaminhar chamadas para outros países em uma determinada rota, essa rota pode ser configurada para rejeitar todos os números de telefone que incluem um código de país. Se Test-CsVoiceRoute retornar false quando você esperava retornar true, verifique se digitou o número de destino corretamente. Se você tiver feito isso, use um comando semelhante a este para exibir o NumberPattern configurado para a rota:

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

