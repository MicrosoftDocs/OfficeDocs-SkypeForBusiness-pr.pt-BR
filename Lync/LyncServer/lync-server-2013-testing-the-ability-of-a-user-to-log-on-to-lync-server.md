---
title: 'Lync Server 2013: testar a capacidade de um usuário fazer logon no Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the ability of a user to log on to Lync Server
ms:assetid: d9cd0f9b-6ef2-4050-a4ca-263c5afa93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743841(v=OCS.15)
ms:contentKeyID: 63969655
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 541870c2dc9bf5fde0ce2a339b07b894feb83082
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193844"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a>Testando a capacidade de um usuário fazer logon no Lync Server 2013

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
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet Test-CsRegistration permite verificar se os usuários da sua organização podem fazer logon no Lync Server. Quando você executa o Test-CsRegistration, o cmdlet tenta entrar em um usuário de teste no Lync Server e, em seguida, se tiver êxito, desconectará o usuário de teste do sistema. Tudo isso acontece sem nenhuma interação por parte do usuário e sem afetar nenhum usuário real. Por exemplo, suponha que a conta de teste sip:kenmyer@litwareinc.com corresponde a um usuário real que tem uma conta real do Lync Server. Nesse caso, o teste será conduzido sem prejuízo algum ao verdadeiro Ken Myer. Quando a conta de teste de Ken Myer fizer logoff do sistema, a pessoa Ken Myer continuará conectada.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O cmdlet Test-CsRegistration pode ser executado usando uma conta de teste pré-configurada (consulte Configurando contas de teste para executar testes do Lync Server) ou a conta de qualquer usuário habilitado para o Lync Server. Para executar esta verificação usando uma conta de teste, basta especificar o FQDN do pool de registradores do Lync Server que está sendo testado. Por exemplo:

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

Para executar essa verificação usando uma conta de usuário real, você deve primeiro criar um objeto de credenciais do Windows PowerShell que contenha o nome da conta e a senha. Em seguida, você deve incluir o objeto Credentials e o endereço SIP atribuído à conta quando chamar Test-CsRegistration:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

Se o usuário especificado puder fazer logon (e, em seguida, fazer logoff do) Lync Server, você receberá uma saída semelhante a essa com a propriedade Result marcada como **êxito:**

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: êxito

Latência: 00:00:06.8630376

Erros

Diagnóstico

Se o usuário especificado não puder fazer logon ou logout, o resultado será mostrado como uma falha, e informações adicionais serão registradas nas propriedades de erro e diagnóstico:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: falha

Latência: 00:00:00

Erro: 404, não encontrado

Diagnóstico: ErrorCode = 1003, Source = ATL-cs-001. litwareinc. com, Reason = o usuário faz

Não existe

Microsoft. RTC. Signaling. DiagnosticHeader

Por exemplo, a saída anterior diz que o teste falhou porque o usuário especificado não pôde ser encontrado. Você pode determinar se um endereço SIP é ou não válido (e se o usuário atribuído cujo endereço SIP está habilitado para o Lync Server) executando este comando:

    Get-CsUser "sip:kenmyer@litwareinc.com"

Se Test-CsRegistration falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Quando o parâmetro Verbose é incluído, o Test-CsRegistration retornará uma conta passo a passo de cada ação que tentou quando verificou a capacidade do usuário especificado fazer logon no Lync Server. Por exemplo:

VERBOse: atividade de ' registro ' iniciada.

Enviando solicitação de registro:

FQDN de destino = atl-cs-011.litwareinc.com

Endereço SIP do usuário = sip:kenmyer@litwareinc.com

Porta do registrador = 5061.

O tipo de autenticação ' confiável ' é selecionado.

Uma exceção ' o ponto de extremidade não pode ser registrada. Veja o código de erro por motivo específico, durante a execução do fluxo de trabalho Microsoft. RTC. SyntheticTransactions. Workflow. STRegistrerWorkflow.

Pilha de chamadas de exceção: em Microsoft. RTC. Signaling. SipAsyncResult'1. ThrowIfFailed ()

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais Test-CsRegistration pode falhar:

  - Você especificou uma conta de usuário incorreta. Você pode verificar se uma conta de usuário existe executando um comando semelhante a este:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server. Para verificar se uma conta de usuário está habilitada para o Lync Server, execute um comando semelhante ao seguinte:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está atualmente habilitado para o Lync Server.

  - Você especificou um pool de registradores incorreto. Você pode retornar os FQDNs dos pools de registradores usando este comando:
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - O pool de registradores não está disponível no momento. Tente executar o ping no pool para ver se ele responderá:
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

