---
title: 'Lync Server 2013: testando chamada ponto a ponto PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing PSTN peer to peer call
ms:assetid: 7e128eef-9ada-49b4-940f-97d7d13f1e4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690131(v=OCS.15)
ms:contentKeyID: 63969622
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51b74697c7d6d5a037537bb036494d89264c4e75
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844628"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-peer-to-peer-call-in-lync-server-2013"></a>Testando chamada ponto a ponto PSTN no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-06-05_


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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsPstnPeerToPeerCall. Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnPeerToPeerCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet Test-CsPstnPeerToPeerCall verifica a capacidade de um par de usuários realizar uma chamada ponto a ponto pelo gateway PSTN (rede telefônica pública comutada). Quando você chama Test-CsPstnPeerToPeerCall, o cmdlet tenta primeiro fazer logon dois usuários de teste no Lync Server. Pressupondo que os logons sejam bem-sucedidos, o cmdlet terá o usuário 1 tentando chamar o usuário 2 pelo gateway PSTN. Test-CsPstnPeerToPeerCall fará essa chamada usando o plano de discagem, a política de voz e outras configurações de política e configuração atribuídas ao usuário de teste. Se o teste for planejado, o cmdlet verificará se o usuário 2 pôde atender a chamada e, em seguida, fazer logoff de ambas as contas de teste do sistema.

Test-CsPstnPeerToPeerCall faz uma chamada telefônica real, uma que verifica se uma conexão pode ser feita e também transmite códigos DTMF pela rede para determinar se a mídia pode ser enviada pela conexão. A chamada é atendida pelo próprio cmdlet e não é necessário encerrar manualmente a chamada. (Ou seja, ninguém precisa atender e desligar o telefone que foi chamado.)

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O cmdlet Test-CsPstnPeerToPeerCall pode ser executado usando um par de contas de teste pré-configuradas (consulte Configurando contas de teste para executar testes do Lync Server) ou das contas de dois usuários que estão habilitados para o Lync Server. Para executar essa verificação usando contas de teste, basta especificar o FQDN do pool do servidor do Lync que está sendo testado. Por exemplo:

`Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com"`

Para executar essa verificação usando contas de usuário reais, você deve criar dois objetos de credenciais do Windows PowerShell (objetos que contêm o nome da conta e a senha) para cada conta. Em seguida, você deve incluir esses objetos de credenciais e os endereços SIP das duas contas ao chamar Test-CsPstnPeerToPeerCall:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

Para obter mais informações, consulte a documentação da ajuda para o cmdlet [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinação do sucesso ou falha

Se os usuários especificados puderem concluir uma chamada ponto a ponto, você receberá uma saída semelhante a isso, com a propriedade Result marcada como **Success:**

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: êxito

Latência: 00:00:06.8630376

Erros

Correto

Se os usuários especificados não puderem concluir uma chamada ponto a ponto, o resultado será mostrado como uma falha, e informações adicionais serão gravadas nas propriedades de erro e diagnóstico:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: falha

Latência: 00:00:0182361

Erro: 403, proibido

Diagnóstico: ErrorCode = 12001, Source = ATL-cs-001.litwareinc.com,

Razão = a política de usuário não contém uso de rota de telefone

A saída anterior informa que o teste falhou porque a política de voz atribuída a pelo menos um dos usuários especificados não inclui um uso de telefone. (Os usos de telefone unem as políticas de voz a rotas de voz. Sem uma política de voz e uma rota de voz correspondente, você não pode fazer chamadas pela PSTN.)

Se Test-CsPstnPeerToPeerCall falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:

    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Quando o parâmetro Verbose estiver incluído, Test-CsPstnPeerToPeerCall retornará uma conta passo a passo de cada ação que tentou verificar quando verificou a capacidade do usuário especificado para fazer logon no Lync Server. Por exemplo, essa saída indica que problemas de rede estão impedindo uma conexão com o PSTN:

Como estabelecer uma chamada com vídeo de áudio para ' SIP: +12065551219@litwareinc.com; user = Phone '.

Uma resposta de exceção ' A 404 (não encontrada) foi recebida da rede e a operação falhou.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais Test-CsPstnPeerToPeerCall pode falhar:

  - Você especificou uma conta de usuário que não é válida. Você pode verificar se existe uma conta de usuário executando um comando semelhante a este:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server. Para verificar se uma conta de usuário está habilitada para o Lync Server, execute um comando semelhante ao seguinte:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está habilitado no momento para o Lync Server.

  - A política de voz atribuída ao usuário especificado não tem um uso PSTN válido. Você pode determinar a política de voz atribuída a um usuário usando um comando semelhante a este:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    Em seguida, você pode determinar os usos PSTN (se houver) atribuídos a essa política usando um comando semelhante ao seguinte, que recupera informações sobre a política de voz por usuário RedmondVoicePolicy:
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

