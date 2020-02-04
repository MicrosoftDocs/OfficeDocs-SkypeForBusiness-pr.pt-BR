---
title: 'Lync Server 2013: testando o encaminhamento de chamadas telefônicas PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call routing
ms:assetid: 301dd44d-03e9-41cd-9722-54e00365aa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727302(v=OCS.15)
ms:contentKeyID: 63969598
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2dabe54fb2ba4df864d172015efb62ef161c77cb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a>Testando o roteamento de chamadas telefônicas PSTN no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-11-01_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Cronograma de verificação</p></td>
<td><p>Diário</p></td>
</tr>
<tr class="even">
<td><p>Ferramenta de teste</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Permissões necessárias</p></td>
<td><p>Quando executado localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</p>
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsInterTrunkRouting</strong> . Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet **Test-CsInterTrunkRouting** verifica se as chamadas podem ser roteadas de um SIP para outro. Para fazer isso, o cmdlet recebe um número de telefone e uma configuração de tronco. **Test-CsInterTrunkRouting** reportará os roteiros correspondentes e os usos de PSTN correspondentes para o número especificado. Observe que as chamadas podem ser roteadas entre troncos apenas se os troncos possuem um padrão de número que corresponde ao número de telefone especificado e apenas se os troncos compartilham pelo menos um uso PSTN.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

Os comandos exibidos abaixo retornam as rotas correspondentes e os usos de telefone correspondentes que permitem que os usuários chamem o número de telefone 1-206-555-1219 usando as configurações de tronco de configuração para o site de Redmond.

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinação do sucesso ou falha

Se as chamadas puderem ser roteadas de um SIP para outro, você receberá uma saída semelhante a esta:

FirstMatchingRoute MatchingUsage MatchingRoutes

\------------------ ------------- --------------

RedmondRoute LocalUsage {RedmondRoute}

Se o teste não for bem-sucedido, você receberá uma saída semelhante a esta:

Test-CsInterTrunkRouting: não é possível processar a transformação do argumento no parâmetro

'TrunkConfiguration'. TrunkConfigurationsetting (parâmetro) inválido. Especificar um

configuração válida (parâmetro) e tente novamente.

Na linha: 1 caractere: 79

\+Test-CsInterTrunkRouting-TargetNumber "Tel: + 12065551219"

\-TrunkConfiguration $t...

\+

~~

\+CategoryInfo: InvalidData: (:) \[Test-CsInterTrunkRouting\], par

ameterBindingArgumentTransformationException

\+FullyQualifiedErrorId: ParameterArgumentTransformationError, Microsoft. R

TC. Management. Voice. cmdlets. TestOcsInterTrunkRoutingCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais **Test-CsInterTrunkRouting** pode falhar:

  - Você especificou parâmetros inválidos. O tronco pode não estar corretamente configurado e o número de destino especificado pode estar incorreto ou inválido.

</div>

<div>

## <a name="see-also"></a>Confira também


[Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

