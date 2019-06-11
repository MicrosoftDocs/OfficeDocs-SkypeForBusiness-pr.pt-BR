---
title: 'Lync Server 2013: verificar regras de normalização de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Check voice normalization rules
ms:assetid: bf71a218-71cd-4b64-b8e8-b3a98b6e87a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725212(v=OCS.15)
ms:contentKeyID: 63969649
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 487415fccc1e779daa476a4e76aa99a891f6b7fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-voice-normalization-rules-in-lync-server-2013"></a>Verificar regras de normalização de voz no Lync Server 2013

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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsVoiceNormalizationRule. Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceNormalizationRule&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

As regras de normalização de voz são usadas para converter um número de telefone discado por um usuário (por exemplo, 2065551219) para o formato E. 164 usado pelo Lync Server (+ 12065551219). Por exemplo, se os usuários estiverem no hábito de discar um número de telefone sem incluir o código de país ou o código de área (por exemplo, 5551219), você deve ter uma regra de normalização de voz que pode converter esse número no formato E. 164: + 12065551219. Sem essa regra, o usuário não poderá ligar para 555-1219.

O cmdlet Test-CsVoiceNormalizationRule verifica se uma regra de normalização de voz especificada pode converter com êxito um número de telefone especificado. Por exemplo, esse comando verifica se a regra de normalização global NoAreaCode pode normalizar e converter a cadeia de caracteres de discagem 5551219.

`Get-CsVoiceNormalizationRule -Identity "global/NoAreaCode" | Test-CsVoiceNormalizationRule -DialedNumber "5551219"`

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

Para executar o cmdlet Test-CsVoiceNormalizationRule, você deve primeiro usar o cmdlet Get-CsVoiceNormalizationRule para recuperar uma instância da regra que está sendo testada e, em seguida, canalizar essa instância para Test-CsVoiceNormalizationRule. A sintaxe semelhante a esta não funcionará:

Test-CsVoiceNormalizationRule-DialedNumber "12065551219" – NormalizationRule "global/prefix All"

Em vez disso, use sintaxe como a seguir, que combina os cmdlets Get-CsVoiceNormalizationRule e Test-CsVoiceNormalizationRule:

Get-CsVoiceNormalizationRule-identidade "global/prefix All" | Test-CsVoiceNormalizationRule-DialedNumber "12065551219"

<div>


> [!NOTE]  
> . Ou, você também pode usar essa abordagem para recuperar uma instância de uma regra e, em seguida, testar essa regra em relação a um número de telefone especificado:



</div>

`$x = Get-CsVoiceNormalizationRule -Identity "global/Prefix All"`

`Test-CsVoiceNormalizationRule -DialedNumber "12065551219" -NormalizationRule $x`

Digite o valor do parâmetro DialedNumber exatamente como você espera que o número seja discado. Por exemplo, se a regra de normalização de voz especificada deve adicionar automaticamente o código de país (o 1 inicial no valor 12065551219), você deve deixar de fora o código de país:

`-DialedNumber "2065551219"`

Se a regra estiver configurada corretamente, ela adicionará automaticamente o código do país ao traduzir o número para o formato E. 164 que é usado pelo Lync Server.

Para obter mais informações, consulte a documentação da ajuda para o cmdlet Test-CsVoiceNormalizationRule.

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinação do sucesso ou falha

Se a regra de normalização de voz especificada puder traduzir o número fornecido, o número traduzido será exibido na tela:

TranslatedNumber

\----------------

\+12065551219

Se o teste falhar, um número traduzido em branco será retornado:

TranslatedNumber

\----------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Se o teste-CsVoiceNormalizationRule retornar um número traduzido que significa que a regra de normalização de voz especificada não pôde traduzir o número de telefone fornecido para o formato E. 164 que é usado pelo Lync Server. Para verificar isso, primeiro certifique-se de que digitou o número de telefone corretamente. Por exemplo, você espera que sua regra de normalização de voz tenha problemas para traduzir um número semelhante a este:

`-DialedNumber "1"`

Pressupondo que o número foi digitado corretamente, a próxima etapa deve ser verificar se a regra de normalização especificada foi projetada para manipular esse número de telefone. Por exemplo, uma regra de normalização pode ser projetada para manipular o formato 12065551219, mas uma segunda regra pode ser projetada para manipular o número 2065551219. (Esse é o mesmo número de telefone, menos o código de país 1 no início.) Para retornar informações detalhadas sobre uma regra de normalização de voz, execute um comando semelhante a este:

`Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Format-List`

Para retornar informações detalhadas sobre todas as regras de normalização de voz, execute este comando em vez disso:

`Get-CsVoiceNormalizationRule | Format-List`

</div>

<div>

## <a name="see-also"></a>Confira também


[Test-CsVoiceNormalizationRule](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceNormalizationRule)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

