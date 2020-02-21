---
title: 'Lync Server 2013: testar chamadas telefônicas PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call
ms:assetid: dc7d319d-a627-45b6-a978-6111901251e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690133(v=OCS.15)
ms:contentKeyID: 63969656
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7c9c0b0441ea31e2419101aba188c33b0bbfd70
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193914"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-in-lync-server-2013"></a>Testando chamada telefônica PSTN no Lync Server 2013

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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsRegistration. Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnOutboundCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet Test-CsPstnOutboundCall testa a capacidade de um usuário fazer uma chamada para um número de telefone localizado no PSTN. Quando você executa o Test-CsPstnOutboundCall, o cmdlet tenta primeiro registrar o usuário de teste no Lync Server. Se o logon for bem-sucedido, o cmdlet tentará fazer uma chamada telefônica no gateway PSTN. Este telefonema será feito usando o plano de discagem, a política de voz e outras políticas e configurações atribuídas à conta de teste. Quando a chamada é atendida, o cmdlet envia códigos DTMF (multifrequência de tom dual) pela rede para verificar a conectividade de mídia.

Ao conduzir seu teste, Test-CsPstnOutboundCall fará uma chamada telefônica real: o telefone de destino irá tocar e deve ser atendido para que o teste tenha êxito. Essa chamada também deve ser finalizada manualmente pelo administrador.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O cmdlet Test-CsPstnOutboundCall pode ser executado usando uma conta de teste pré-configurada (consulte Configurando contas de teste para executar testes do Lync Server) ou a conta de qualquer usuário habilitado para o Lync Server. Para executar essa verificação usando uma conta de teste, basta especificar o FQDN do pool do Lync Server que está sendo testado e o número de telefone PSTN que está sendo chamado. Por exemplo:

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219"

Para executar essa verificação usando uma conta de usuário real, você deve primeiro criar um objeto de credenciais do Windows PowerShell que contenha o nome da conta e a senha. Em seguida, você deve incluir o objeto Credentials e o endereço SIP atribuído à conta quando chamar Test-CsPstnOutboundCall:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

Se o usuário especificado puder fazer a chamada, e se a chamada for atendida, você receberá uma saída semelhante a esta, com a propriedade Result marcada como **êxito:**

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: êxito

Latência: 00:00:06.8630376

Erros

Diagnóstico

Se o usuário especificado não puder fazer a chamada ou se a chamada não for atendida, o resultado será mostrado como falha, e informações adicionais serão registradas nas propriedades de erro e diagnóstico:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: falha

Latência: 00:00:0987365

Erro: 403, proibido

Diagnóstico: ErrorCode = 12001, Source = ATL-cs-001. litwareinc. com, Reason = User

A política não contém uso de rota de telefone

A saída anterior diz que o teste falhou porque a política de voz atribuída ao usuário especificado não inclui um uso de telefone. (Os usos de telefone unem as políticas de voz para rotas de voz. Sem uma política de voz e uma rota de voz correspondente, você não pode fazer chamadas pela PSTN.

Se Test-CsPstnOutboundCall falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -Verbose

Quando o parâmetro Verbose é incluído, o Test-CsPstnOutboundCall retornará uma conta passo a passo de cada ação que tentou quando verificou a capacidade do usuário especificado fazer logon no Lync Server. Por exemplo, essa saída indica que problemas de rede estão impedindo uma conexão com o PSTN:

Estabelecendo chamada de vídeo de áudio para ' SIP: + 12065551219@litwareinc. com; user = Phone '.

Uma resposta de uma exceção ' A 404 (não encontrada) foi recebida da rede e a operação falhou.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais Test-CsPstnOutboundCall pode falhar:

  - Você especificou uma conta de usuário inválida. Você pode verificar se uma conta de usuário existe executando um comando semelhante a este:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server. Para verificar se uma conta de usuário está habilitada para o Lync Server, execute um comando semelhante ao seguinte:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está habilitado para o Lync Server no momento.

  - A política de voz atribuída ao usuário especificado não tem um uso PSTN válido. Você pode determinar a política de voz atribuída a um usuário usando um comando semelhante a este:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    E, em seguida, você pode determinar os usos de PSTN (se houver) atribuídos a essa política usando um comando semelhante ao seguinte, que recupera informações sobre a política de voz por usuário RedmondVoicePolicy:
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

