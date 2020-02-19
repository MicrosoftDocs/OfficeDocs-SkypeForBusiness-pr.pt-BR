---
title: 'Lync Server 2013: testar configuração de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice configuration
ms:assetid: 574794a3-cb30-4762-bb62-3a68574f05e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725208(v=OCS.15)
ms:contentKeyID: 63969605
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f0d5c8aef7c3cca22a41f591a208413cc453898
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-voice-configuration-in-lync-server-2013"></a>Testar a configuração de voz no Lync Server 2013

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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsVoiceTestConfiguration. Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceTestConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O Lync Server inclui vários cmdlets do Windows PowerShell (como Test-CsVoiceRoute e Test-CsVoicePolicy, Test-CsTrunkConfiguration) que permitem verificar se as partes individuais de sua infraestrutura do Enterprise Voice – rotas de voz, voz as políticas, troncos SIP – estão funcionando conforme o esperado.

Embora seja importante com o Enterprise Voice que todas as partes individuais funcionem: é possível ter uma rota de voz válida, uma política de voz válida e um tronco SIP válido, mas ainda assim os usuários não podem fazer ou receber chamadas telefônicas. Por isso, o Lync Server também oferece a capacidade de criar configurações de teste de voz. As configurações de teste de voz representam cenários comuns do Enterprise Voice: você pode especificar coisas como uma rota de voz, uma política de voz e um plano de discagem e, em seguida, verificar se esses itens individuais podem trabalhar juntos para fornecer serviço de telefone. Além disso, você pode validar suas expectativas em um determinado cenário. Por exemplo, suponha que você espera que a combinação de plano de discagem A e a política de voz B resulte em chamadas sendo roteadas pela rota de voz C. Você pode inserir a rota de voz C como ExpectedRoute. Quando você executar o teste, se a rota de voz C não for empregada, o teste será marcado como tendo falhado.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

Antes de testar as coleções de configuração de voz usando o Windows PowerShell, você deve primeiro usar o cmdlet Get-CsVoiceTestConfiguration para recuperar uma instância dessas definições de configuração. Essa instância deve então ser canalizada para o Test-CsVoiceTestConfiguration. Por exemplo:

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

Para validar todas as definições de configuração de teste de voz ao mesmo tempo, use este comando:

`Get-CsVoiceTestConfiguration | Test-CsVoiceTestConfiguration`

Para obter mais informações, consulte a documentação de ajuda para o cmdlet Test-CsVoiceTestConfiguration.

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

O cmdlet Test-CsVoiceTestConfiguration relata se um teste falhou ou teve êxito e fornece informações adicionais sobre cada teste bem-sucedido, como a regra de conversão, a rota de voz e o uso de PSTN usados para concluir a tarefa:

Resultado: êxito

TranslatedNumber: + 15551234

MatchingRule: Descrição =; Padrão = ^ (\\d{4}) $; Tradução = + 1\\d; Name = teste; IsInternalExtension = false

FirstMatchingRoute: site: Redmond

MatchingUsage: local

Se o teste falhar, o resultado será relatado como falha:

Resultado: falha

TranslatedNumber:   

FirstMatchingRoute:

MatchingUsage:      

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Como o teste de configuração de teste de voz testa vários itens diferentes, incluindo políticas de voz, planos de discagem, rotas de voz e assim por diante, há vários fatores diferentes que podem resultar em um teste com falha. Se um teste falhar, sua primeira etapa deve ser revisar as definições de configuração por conta própria usando o cmdlet Get-CsVoiceTestConfiguration:

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration"`

Se as configurações parecem estar configuradas corretamente, execute o teste novamente, incluindo o parâmetro Verbose:

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

O parâmetro Verbose fornecerá uma conta passo a passo de cada ação tomada por Test-CsVoiceTestConfiguration, conforme mostrado neste exemplo:

VERBOse: carregando o plano de discagem: "global"

VERBOse: carregando política de voz: "RedmondDialPlan"

Esta conta passo a passo pode fornecer uma pista útil para onde o teste realmente falhou. Caso contrário, você poderá usar outros cmdlets do Windows PowerShell (como Test-CsVoicePolicy) e começar metodicamente a verificar os componentes individuais que estão incluídos nas definições de configuração do teste de voz.

Além disso, esteja ciente de que é possível que um teste seja capaz de rotear uma chamada e ainda seja marcado como uma falha; Isso pode ocorrer se você inserir valores para ExpectedRoute, ExpectedTranslatedNumber e ExpectedUsage, e qualquer uma dessas expectativas não for atendida. Por exemplo, suponha que você insira a rota de voz C como rota de voz esperada, mas o teste realmente conclui a chamada usando a rota de voz D. Nesse caso, o teste será marcado como Failed porque a rota de voz esperada não foi usada. Se um teste falhar, você poderá remover os valores de ExpectedRoute, ExpectedTranslatedNumber e ExpectedUsage e, em seguida, executar novamente o teste. Isso ajudará você a determinar se a falha ocorreu porque a chamada não pôde ser concluída ou porque você espera uma coisa e realmente recebeu outra.

</div>

<div>

## <a name="see-also"></a>Confira também


[Test-CsVoiceTestConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceTestConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

