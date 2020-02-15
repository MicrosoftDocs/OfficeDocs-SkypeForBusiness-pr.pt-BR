---
title: 'Lync Server 2013: testar número de telefone em uma política de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test telephone number against a voice policy
ms:assetid: 30c51700-17c6-4c57-891a-8d5ec30b50ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725207(v=OCS.15)
ms:contentKeyID: 63969596
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a234419dc6f06ae9bdc8d7c198873bdc3c706701
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41985086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-policy-in-lync-server-2013"></a>Testar número de telefone em uma política de voz no Lync Server 2013

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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsVoicePolicy. Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoicePolicy&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

A capacidade de usuários do Enterprise Voice de fazer chamadas telefônicas de saída por meio das dobradiças da PSTN (rede telefônica pública comutada), em grande parte, em três coisas:

  - A política de voz atribuída ao usuário.

  - As rotas de voz usadas para rotear chamadas do Lync Server para a rede PSTN.

  - O uso do PSTN, uma propriedade do Lync Server que conecta uma política de voz a uma rota de voz.

O uso do PSTN é especialmente importante: é a propriedade que conecta uma política de voz a uma rota de voz. (Uma política de voz e uma rota de voz são consideradas conectadas se tiverem pelo menos um uso de PSTN em comum). As políticas de voz podem ser configuradas sem a especificação de um uso de PSTN. Nesse caso, os usuários que receberam essa política não poderão fazer chamadas de saída na rede PSTN. Da mesma forma, as rotas de voz que não têm pelo menos um uso PSTN especificado não poderão rotear as chamadas para a rede PSTN.

O cmdlet Test-CsVoicePolicy verifica se uma determinada política de voz tem um uso de PSTN e se o uso é compartilhado por pelo menos uma rota de voz. Se a verificação executada por Test-CsVoicePolicy tiver êxito, o cmdlet relatará o nome da primeira rota de voz válida que encontrará e também o nome do uso de PSTN que conecta a política à rota.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

Para executar o cmdlet Test-CsVoicePolicy, primeiro você deve usar o cmdlet Get-CsVoicePolicy recuperar uma instância da política de voz a ser testada; essa instância deve então ser canalizada para Test-CsVoicePolicy. Por exemplo:

`Get-CsVoicePolicy -Identity "Global" | Test-CsVoicePolicy -TargetNumber "+12065551219"`

Observe que esse comando, que não usa Get-CsVoicePolicy para recuperar uma instância de política de voz, falhará:

`Test-CsVoicePolicy -TargetNumber "+12065551219" -VoicePolicy "Global"`

Se quiser verificar todas as políticas de voz em relação a um número de telefone específico, use um comando semelhante ao seguinte:

`Get-CsVoicePolicy | Test-CsVoicePolicy -TargetNumber "+12065551219"`

Observe que o TargetNumber deve ser especificado usando o formato E. 164. Test-CsVoicePolicy não tentará normalizar ou traduzir números de telefone no formato E. 164.

Para obter mais informações, consulte a documentação de ajuda para o cmdlet Test-CsVoicePolicy.

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

Se a política de voz puder encontrar uma rota de voz correspondente e um uso de PSTN correspondente, tanto a rota quanto o uso serão exibidos na tela:

FirstMatchingRoute MatchingUsage

\------------------ -------------

RedmondVoiceRoute RedmondPstnUsage

Se uma rota de voz apropriada ou um uso de PSTN apropriado não puder ser encontrado, os valores de propriedade em branco serão exibidos na tela:

FirstMatchingRoute MatchingUsage

\------------------ -------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Se Test-CsVoicePolicy não retornar uma correspondência que possa significar que a política de voz não compartilha um uso de PSTN com uma rota de voz. Para verificar isso, use um cmdlet semelhante ao seguinte para verificar se os usos de PSTN foram atribuídos à política de voz:

`Get-CsVoicePolicy -Identity "Global" | Select-Object PstnUsages | Format-List`

Em seguida, execute este comando para determinar os usos de PSTN atribuídos a cada uma das suas rotas de voz:

`Get-CsVoiceRoute | Select-Object Identity, PstnUsages`

Se você vir qualquer correspondência (ou seja, se vir uma ou mais rotas de voz que compartilham pelo menos um uso de PSTN com sua política de voz), deverá executar o cmdlet Test-CsVoiceRoute para verificar se a rota de voz pode discar o número de telefone fornecido.

</div>

<div>

## <a name="see-also"></a>Confira também


[Test-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsVoicePolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

