---
title: 'Lync Server 2013: testar regras de voz, rotas e políticas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice rules, routes, and policies
ms:assetid: ebb9c3fa-6950-4311-87ca-e1ecd9280a43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725213(v=OCS.15)
ms:contentKeyID: 63969661
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bbf04728db30bada37e43f14b33420ede1ce9258
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-voice-rules-routes-and-policies-in-lync-server-2013"></a>Testar regras de voz, rotas e políticas no Lync Server 2013

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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsVoiceUser. Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceUser&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

Quando um usuário faz uma chamada telefônica, a rota que a chamada leva para chegar ao seu destino depende das políticas e dos planos de discagem atribuídos a esse usuário. Dado o endereço SIP de um usuário e um número de telefone, o cmdlet Test-CsVoiceUser verifica se o usuário em questão pode concluir uma chamada para esse número. Se o teste for bem-sucedido, Test-CsVoiceUser retornará o seguinte:

  - O número convertido no formato E. 164 (com base no plano de discagem do usuário)

  - A regra de normalização que forneceu essa tradução

  - A rota de voz usada (com base na prioridade da rota);

  - O uso de telefone que vinculou a política de voz do usuário à rota de voz.

Test-CsVoiceUser permite determinar se um número de telefone específico irá encaminhar e traduzir conforme o esperado e pode ajudar a solucionar problemas relacionados a chamadas que são experientes por usuários individuais.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

Ao executar o cmdlet Test-CsVoiceUser, você deve fornecer duas partes de informação: o número sendo discado (DialedNumber) e a identidade da conta de usuário que está sendo testada. Por exemplo, este comando testa a capacidade do usuário que tem o endereço SIP sip:kenmyer@litwareinc.com para fazer uma chamada para o número de telefone + 1206555-1219:

`Test-CsVoiceUser -DialedNumber "12065551219" -SipUri "sip:kenmyer@litwareinc.com"`

O número de telefone deve ser formatado da forma que você espera que ele seja discado. Por exemplo, se os usuários normalmente não discam o 1 antes de colocar uma chamada de longa distância, você deve usar este formato:

`-DialedNumber "2065551219"`

Obviamente, nesse caso, o teste falhará se você não tiver uma regra de normalização que possa converter corretamente o número 2065551219 no formato de telefone E. 164 que é usado pelo Lync Server. Para obter mais informações, consulte o tópico de ajuda New-CsVoiceNormalizationRule cmdlet.

Se quiser executar esse mesmo teste em relação a cada uma das suas contas de usuário, você poderá usar um comando semelhante ao seguinte:

`Get-CsUser | ForEach-Object {$_.DisplayName; Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri $_.SipAddress} | Format-List`

Para obter mais informações, consulte a documentação de ajuda para o cmdlet Test-CsVoiceUser.

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

Se o teste for concluído com êxito (ou seja, se o usuário puder fazer uma chamada telefônica para o número especificado), a saída mostrará informações como o número de telefone convertido e a regra de normalização e a rota de voz correspondente:

TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage

\----------------    ------------    ------------------    -------------

\+12065551219 Descripti...    Local LocalRoute

Devido às limitações da tela do Windows PowerShell, pelo menos algumas informações retornadas (mais notavelmente a descrição completa da regra de normalização correspondente) podem não aparecer na tela. Se você estiver interessado apenas no sucesso ou na falha do teste, isso pode não ser importante. Se preferir ver os detalhes completos dos dados retornados, canalize a saída para o cmdlet Format-List ao executar o teste:

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose | Format-List`

Isso exibirá a saída em um formato mais amigável para leitores:

TranslatedNumber: + 12065551219

MatchingRule: Descrição =; Padrão = ^ (\\d{11}) $; Conversão = + $1;

Name = prefix All; IsInternalExtension = false

FirsMatchingRoute: LocalRoute

MatchingUsage: local

Se o teste falhar, Test-CsVoiceUser retornará um conjunto vazio de valores de propriedade:

TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage

\---------------- ------------ ------------------ -------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Há várias razões pelas quais o cmdlet Test-CsVoiceUser pode falhar: Talvez não haja uma regra de normalização que possa traduzir o número de telefone fornecido. Pode haver problemas com a rota de voz. Pode haver um problema de configuração com o plano de discagem atribuído ao usuário em questão. Por isso, talvez você queira incluir o parâmetro Verbose quando estiver executando o cmdlet Test-CsVoiceUser:

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose`

Quando o cmdlet verboso for incluído, o Test-CsVoiceUser emitirá uma conta detalhada de todas as etapas adotadas ao conduzir suas verificações. Por exemplo, você pode ver etapas semelhantes a estas: 

VERBOse: Localizando usuário com identidade "sip:kenmyer@litwareinc.com"

VERBOse: carregando o plano de discagem: "RedmondDialPlan"

Essas informações adicionais podem fornecer dicas sobre as etapas que você pode tomar para identificar a causa da falha. Por exemplo, a saída detalhada mostrada aqui diz que o usuário sendo testado recebeu o plano de discagem RedmondDialPlan. Se o teste falhar, uma próxima etapa lógica será verificar se o RedmondDialPlan pode traduzir o número de telefone fornecido.

</div>

<div>

## <a name="see-also"></a>Confira também


[Test-CsVoiceUser](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

