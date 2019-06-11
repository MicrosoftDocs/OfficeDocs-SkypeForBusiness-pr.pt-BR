---
title: 'Lync Server 2013: testando chamada telefônica PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing PSTN phone call
ms:assetid: dc7d319d-a627-45b6-a978-6111901251e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690133(v=OCS.15)
ms:contentKeyID: 63969656
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 641b2f77079fee100d8f3ac85a1a7580d7cf7d84
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844620"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-in-lync-server-2013"></a>Testando chamadas telefônicas PSTN no Lync Server 2013

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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsRegistration. Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnOutboundCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet Test-CsPstnOutboundCall testa a capacidade de um usuário fazer uma chamada para um número de telefone localizado na PSTN. Quando você executa Test-CsPstnOutboundCall, o cmdlet tenta registrar o usuário de teste no Lync Server. Se o logon for bem-sucedido, o cmdlet tentará fazer uma chamada telefônica pelo gateway PSTN. Esta chamada telefônica será feita usando o plano de discagem, a política de voz e outras políticas e configurações atribuídas à conta de teste. Quando a chamada é atendida, o cmdlet envia códigos DTMF (Multifrequency) de dupla Tom pela rede para verificar a conectividade de mídia.

Ao conduzir seu teste, Test-CsPstnOutboundCall fará uma chamada telefônica real: o telefone de destino vai tocar e deve ser respondido para que o teste seja bem-sucedido. Essa chamada também deve ser encerrada manualmente pelo administrador.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O cmdlet Test-CsPstnOutboundCall pode ser executado usando uma conta de teste pré-configurada (consulte Configurando contas de teste para executar testes do Lync Server) ou a conta de qualquer usuário habilitado para o Lync Server. Para executar essa verificação usando uma conta de teste, basta especificar o FQDN do pool do servidor do Lync sendo testado e o número de telefone PSTN sendo chamado. Por exemplo:

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219"

Para executar essa verificação usando uma conta de usuário real, primeiro você deve criar um objeto de credenciais do Windows PowerShell que contenha o nome da conta e a senha. Em seguida, você deve incluir esse objeto de credenciais e o endereço SIP atribuído à conta ao chamar Test-CsPstnOutboundCall:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Para obter mais informações, consulte a documentação da ajuda para o cmdlet [Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinação do sucesso ou falha

Se o usuário especificado puder fazer a chamada e se a chamada for respondida, você receberá uma saída semelhante a essa, com a propriedade Result marcada como **Success:**

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: êxito

Latência: 00:00:06.8630376

Erros

Correto

Se o usuário especificado não puder fazer a chamada ou se a chamada não for respondida, o resultado será mostrado como uma falha, e informações adicionais serão gravadas nas propriedades erro e diagnóstico:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: falha

Latência: 00:00:0987365

Erro: 403, proibido

Diagnóstico: ErrorCode = 12001, Source = ATL-cs-001. litwareinc. com, Reason = User

A política não contém uso de rota de telefone

A saída anterior informa que o teste falhou porque a política de voz atribuída ao usuário especificado não inclui um uso de telefone. (Os usos de telefone unem as políticas de voz a rotas de voz. Sem uma política de voz e uma rota de voz correspondente, você não pode fazer chamadas pela PSTN.)

Se Test-CsPstnOutboundCall falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -Verbose

Quando o parâmetro Verbose estiver incluído, Test-CsPstnOutboundCall retornará uma conta passo a passo de cada ação que tentou verificar quando verificou a capacidade do usuário especificado para fazer logon no Lync Server. Por exemplo, essa saída indica que problemas de rede estão impedindo uma conexão com o PSTN:

Como estabelecer uma chamada com vídeo de áudio para ' SIP: +12065551219@litwareinc.com; user = Phone '.

Uma resposta de exceção ' A 404 (não encontrada) foi recebida da rede e a operação falhou.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais Test-CsPstnOutboundCall pode falhar:

  - Você especificou uma conta de usuário inválida. Você pode verificar se existe uma conta de usuário executando um comando semelhante a este:
    
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

