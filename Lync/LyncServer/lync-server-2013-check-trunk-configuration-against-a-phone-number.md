---
title: 'Lync Server 2013: verificar configuração de tronco em relação a um número de telefone'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check trunk configuration against a phone number
ms:assetid: 0800d7a3-fc35-482b-a9a4-203d890bfa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725206(v=OCS.15)
ms:contentKeyID: 63969574
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b67831b6dbcd7dae12f9b19dd71f2512a8807189
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-trunk-configuration-against-a-phone-number-in-lync-server-2013"></a>Verificar a configuração de tronco em relação a um número de telefone no Lync Server 2013

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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsTrunkConfiguration. Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

Os troncos SIP conectam a rede de voz interna do Lync Server a qualquer um dos seguintes:

  - A rede telefônica pública comutada (PSTN).

  - Uma central de comutação de IP (PBX).

  - Um controlador de borda de sessão (SBC).

O cmdlet Test-CsTrunkConfiguration verifica se um número de telefone (como discado por um usuário) pode ser convertido na rede E. 164 e roteado através de um tronco SIP especificado.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

Para executar o cmdlet Test-CsTrunkConfiguration, primeiro você deve usar o cmdlet Get-CsTrunkConfiguration para recuperar uma instância de suas definições de configuração do tronco SIP; essa instância é então canalizada para Test-CsTrunkConfiguration:

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

Executar Test-CsTrunkConfiguration sem executar primeiro Get-CsTrunkConfiguration não funcionará. Por exemplo, esse comando falhará sem retornar nenhum dado:

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

Se você tiver vários conjuntos de definições de configuração do tronco SIP, poderá usar um comando semelhante ao seguinte, ao mesmo tempo, testar cada coleção com o mesmo número de telefone:

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

Para obter mais informações, consulte a documentação de ajuda para o cmdlet Test-CsTrunkConfiguration.

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

Se Test-CsTrunkConfiguration puder fazer uma chamada para o número discado, o número de telefone convertido (no formato E. 164) e a regra usada para traduzir esse número de telefone serão exibidos na tela:

TranslatedNumber MatchingRule

\---------------- ------------

\+12065551219 global/Redmond

Se o teste falhar, Test-CsTrunkConfiguration retornará valores de propriedade vazios:

TranslatedNumber MatchingRule

\---------------- ------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Se Test-CsTrunkConfiguration não retornar uma correspondência que normalmente significa que as configurações de tronco que estão sendo testadas não têm uma regra de conversão de número de chamada de saída capaz de converter o número discado para o formato E. 164. Para recuperar as regras de conversão atribuídas a um conjunto de definições de configuração de tronco, você pode usar uma sintaxe semelhante a esta:

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

Que retorna informações semelhantes a estas para cada regra de conversão:

Descrição: números de telefone sem um código do país ou código de área.

Padrão: ^\\+ (\\d\*) $

`Translation : $1`

Nome: NoAreaCode

Nesse ponto, verifique o valor da propriedade Pattern (que é uma cadeia de caracteres de [expressão regular](http://go.microsoft.com/fwlink/?linkid=400464) ) para ver se alguma das regras de conversão está configurada para lidar com o número discado. Caso contrário, você terá que alterar uma das regras existentes (Set-CsOutboundTranslationRule) ou usar o cmdlet New-CsOutboundTranslationRule para adicionar uma nova regra à coleção.

</div>

<div>

## <a name="see-also"></a>Confira também


[Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

