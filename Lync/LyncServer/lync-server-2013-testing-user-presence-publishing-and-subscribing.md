---
title: 'Lync Server 2013: testar a publicação de presença do usuário e inscrever-se'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user presence publishing and subscribing
ms:assetid: 27694c71-8e63-4aa4-b49f-fa06ccb81949
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743832(v=OCS.15)
ms:contentKeyID: 63969587
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b76cd47ccfe35cecf7b7e9182aeadccc37436bc5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-user-presence-publishing-and-subscribing-in-lync-server-2013"></a>Testar a publicação de presença do usuário e inscrever-se no Lync Server 2013

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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsPresence. Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPresence&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

Test-CsPresence é usado para determinar se um par de usuários de teste pode fazer logon no Lync Server e, em seguida, trocar informações de presença. Para fazer isso, o cmdlet primeiro faz logon dos dois usuários no sistema. Se o logon de ambos tiver êxito, o primeiro usuário de testes solicita o recebimento de informações de presença do segundo usuário. O segundo usuário publica essas informações, e Test-CsPresence verifica se as informações foram transmitidas com êxito para o primeiro usuário. Após a troca de informações de presença, os dois usuários de teste são então desconectados do Lync Server.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O cmdlet Test-CsPresence pode ser executado usando um par de contas de teste pré-configuradas (consulte Configurando contas de teste para executar testes do Lync Server) ou as contas de dois usuários que estão habilitados para o Lync Server. Para executar essa verificação usando contas de teste, basta especificar o FQDN do pool do Lync Server que está sendo testado. Por exemplo:

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com"

Para executar essa verificação usando contas de usuário reais, você deve criar dois objetos de credenciais do Windows PowerShell (objetos que contêm o nome da conta e a senha) para cada conta. Em seguida, você deve incluir esses objetos de credenciais e os endereços SIP das duas contas ao chamar Test-CsPresence:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -PublisherSipAddress "sip:kenmyer@litwareinc.com" -PublisherCredential $credential1 -SubscriberSipAddress "sip:davidlongmire@litwareinc.com" -SubscriberCredential $credential2

Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

Se os usuários especificados puderem trocar informações de presença, você receberá uma saída semelhante a esta, com a propriedade Result marcada como **êxito:**

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: êxito

Latência: 00:00:06.3280315

Erros

Diagnóstico

Se os dois usuários não puderem trocar informações de presença, o resultado será mostrado como falha, e informações adicionais serão registradas nas propriedades de erro e diagnóstico:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: falha

Latência: 00:00:00

Erro: 404, não encontrado

Diagnóstico: ErrorCode = 4005, Source = ATL-cs-001.litwareinc.com,

Razão = o URI de destino não está habilitado para SIP ou não

existente.

Microsoft. RTC. Signaling. DiagnosticHeader

Por exemplo, a saída anterior diz que o teste falhou porque pelo menos uma das duas contas de usuário não é válida: a conta não existe ou não foi habilitada para o Lync Server. Você pode verificar se as contas existem e determinar se elas estão habilitadas para o Lync Server, executando um comando semelhante a este:

    "sip:kenmyer@litwareinc.com", "sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, Enabled

Se Test-CsPresence falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Quando o parâmetro Verbose é incluído, o Test-CsPresence retornará uma conta passo a passo de cada ação que tentou quando verificou a capacidade do usuário especificado fazer logon no Lync Server. Por exemplo:

Acerto de solicitação de registro contra desconhecido

Atividade ' Register ' concluída em ' 0, 345791 ' segundos.

Atividade ' SelfSubscribeActivity ' iniciada.

Atividade ' SelfSubscribeActivity ' concluída em ' 0, 41174 ' segundos.

Atividade ' SubscribePresence ' iniciada.

Atividade ' SubscribePresence ' concluída em ' 0, 38764 ' segundos.

Atividade ' PublishPresence ' iniciada.

Uma exceção uma notificação de presença não é recebida em 25 segundos. ocorreu uma execução do fluxo de trabalho ruing Microsoft. RTC. SyntheticTransactions. workflows. STPresenceWorkflow.

O fato de que a notificação de presença não foi recebida em 25 segundos pode indicar que os problemas de rede estão impedindo que as informações sejam trocadas.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais Test-CsPresence pode falhar:

  - Você especificou uma conta de usuário incorreta. Você pode verificar se uma conta de usuário existe executando um comando semelhante a este:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server. Para verificar se uma conta de usuário está habilitada para o Lync Server, execute um comando semelhante ao seguinte:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está habilitado para o Lync Server no momento.

</div>

</div>

<span> </span>

</div>

</div>

</div>

