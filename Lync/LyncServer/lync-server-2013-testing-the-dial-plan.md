---
title: 'Lync Server 2013: testar o plano de discagem'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the dial plan
ms:assetid: 70eec03c-aca3-4106-86a7-77ae96b53779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690130(v=OCS.15)
ms:contentKeyID: 63969616
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14c8e53b0b18ae7813cf0f2d63aaa54ffbd4998b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141277"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-the-dial-plan-in-lync-server-2013"></a>Testando o plano de discagem no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-06-05_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Agenda de verificação</p></td>
<td><p>Diariamente</p></td>
</tr>
<tr class="even">
<td><p>Ferramenta de teste</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Permissões obrigatórias</p></td>
<td><p>Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</p>
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsDialPlan. Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialPlan&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet Test-CsDialPlan permite que você veja os resultados da aplicação de um plano de discagem a um determinado número de telefone. Os planos de discagem fornecem informações, como as regras de normalização que são aplicadas, necessárias para permitir que os usuários do Enterprise Voice façam chamadas telefônicas. Considerando um número discado e um plano de discagem, este cmdlet verificará qual regra de normalização dentro do plano de discagem será aplicada e qual será o número traduzido.

Você pode usar esse cmdlet para solucionar problemas com traduções de número ou para verificar como aplicar regras em determinados números.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O cmdlet Test-CsDialPlan exige que você faça duas coisas. Primeiro, você deve obter uma instância do plano de discagem que está sendo testado; Isso pode ser feito usando o cmdlet Get-CsDialPlan. Em segundo lugar, você deve especificar o número de telefone que deve ser normalizado. O formato usado para o número de telefone deve corresponder ao número como discado/inserido por um usuário. Por exemplo, este comando recupera uma instância do plano de discagem, RedmondDialPlan, e verifica se o número de telefone 12065551219 pode ser normalizado:

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "12065551219" | Format-List

Se você tiver uma regra de normalização que adicione automaticamente o código do país (neste exemplo, 1) e o código de área (206), talvez você queira verificar o número de telefone 5551219, da seguinte maneira:

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "5551219" | Format-List

Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

Test-CsDialPlan difere de muitos dos cmdlets de teste do Lync Server porque apenas indica indiretamente se um teste foi bem-sucedido ou falhou. Ao usar o Test-CsDialPlan, você não recebe uma saída semelhante a esta com o resultado identificado com clareza:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: êxito

Latência: 00:00:06.8630376

Erros

Diagnóstico

Em vez disso, se Test-CsDialPlan tiver êxito, você receberá informações sobre a regra de normalização que foi capaz de traduzir e usar o número de telefone especificado com êxito:

TranslatedNumber: + 12065551219

MatchingRule: Descrição =; Padrão = ^ (\\d (11)) $; Conversão = + $1;

Name = prefix All; IsInternalExtension = false

Se Test-CsDialPlan falhar (ou seja, se o plano de discagem não tiver uma regra de normalização que possa traduzir o número de telefone especificado), você receberá a saída "Empty" da seguinte maneira:

TranslatedNumber :

MatchingRule :

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais Test-CsDialPlan pode falhar:

  - Você pode ter usado um formato incorreto ao especificar o número de telefone. Os planos de discagem incluem regras de normalização que permitem ao Lync Server converter os números de telefone discados ou inseridos por um usuário. Portanto, o plano de discagem deve ter regras de normalização que correspondam aos números que os usuários podem discar. Por exemplo, se os usuários podem discar o código do país, o código de área e o número de telefone em si, isso significa que seu plano de discagem deve ter uma regra de normalização para lidar com números de telefone, como:
    
    12065551219
    
    No entanto, se você inserir um número de telefone incorreto (por exemplo, deixando o último dígito), Test-CsDialPlan falhará. Isso não ocorre porque o plano de discagem está defeituoso, mas porque você inseriu um número de telefone do que não pode ser interpretado.

</div>

</div>

<span> </span>

</div>

</div>

</div>

