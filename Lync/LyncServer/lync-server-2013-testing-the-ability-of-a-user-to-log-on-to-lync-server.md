---
title: 'Lync Server 2013: testando a capacidade de um usuário para fazer logon no Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing the ability of a user to log on to Lync Server
ms:assetid: d9cd0f9b-6ef2-4050-a4ca-263c5afa93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743841(v=OCS.15)
ms:contentKeyID: 63969655
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adf6cae2899d08765faf5d605ea20ae111f395ce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844617"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a>Testar a capacidade de um usuário para fazer logon no Lync Server 2013

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
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet Test-CsRegistration permite que você verifique se os usuários em sua organização podem fazer logon no Lync Server. Ao executar Test-CsRegistration, o cmdlet tenta se conectar a um usuário de teste ao Lync Server e, se tiver êxito, desconectará o usuário de teste do sistema. Tudo isso acontece sem qualquer interação do usuário e sem afetar os usuários reais. Por exemplo, suponha que o sip:kenmyer@litwareinc.com da conta de teste corresponda a um usuário real que tenha uma conta real do Lync Server. Nesse caso, o teste será realizado sem qualquer interrupção no Ken Myer verdadeiro. Quando a conta de teste de Ken Myer é desconectada do sistema, Ken Myer a pessoa permanecerá conectada.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O cmdlet Test-CsRegistration pode ser executado usando uma conta de teste pré-configurada (consulte Configurando contas de teste para executar testes do Lync Server) ou a conta de qualquer usuário habilitado para o Lync Server. Para executar essa verificação usando uma conta de teste, basta especificar o FQDN do pool de registradores do Lync Server que está sendo testado. Por exemplo:

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

Para executar essa verificação usando uma conta de usuário real, primeiro você deve criar um objeto de credenciais do Windows PowerShell que contenha o nome da conta e a senha. Em seguida, você deve incluir esse objeto de credenciais e o endereço SIP atribuído à conta ao chamar Test-CsRegistration:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Para obter mais informações, consulte a documentação da ajuda para o cmdlet [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinação do sucesso ou falha

Se o usuário especificado puder fazer logon (e, em seguida, fazer logoff do) Lync Server, você receberá uma saída semelhante a isso com a propriedade Result marcada como **Success:**

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: êxito

Latência: 00:00:06.8630376

Erros

Correto

Se o usuário especificado não puder entrar ou fazer logoff, o resultado será mostrado como uma falha, e informações adicionais serão gravadas nas propriedades de erro e diagnóstico:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: falha

Latência: 00:00:00

Erro: 404, não encontrado

Diagnóstico: ErrorCode = 1003, Source = ATL-cs-001. litwareinc. com, Reason = o usuário faz

Não existe

Microsoft. RTC. Signaling. DiagnosticHeader

Por exemplo, a saída anterior informa que o teste falhou porque o usuário especificado não foi encontrado. Você pode determinar se um endereço SIP é válido (e se o usuário que atribuiu esse endereço SIP está habilitado para o Lync Server) executando este comando:

    Get-CsUser "sip:kenmyer@litwareinc.com"

Se Test-CsRegistration falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Quando o parâmetro Verbose estiver incluído, Test-CsRegistration retornará uma conta passo a passo de cada ação que tentou verificar quando verificou a capacidade do usuário especificado para fazer logon no Lync Server. Por exemplo:

VERBOse: atividade de ' registro ' iniciada.

Enviando solicitação de registro:

FQDN de destino = atl-cs-011.litwareinc.com

Endereço SIP do usuário = sip:kenmyer@litwareinc.com

Porta do registrador = 5061.

O tipo de autenticação "confiável" está selecionado.

Uma exceção ' o ponto de extremidade não pode se registrar. Veja o código de erro por motivo específico ' durante a execução do fluxo de trabalho Microsoft. RTC. SyntheticTransactions. Workflow. STRegistrerWorkflow.

Pilha de chamadas de exceção: em Microsoft. RTC. Signaling. SipAsyncResult'1. ThrowIfFailed ()

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais Test-CsRegistration pode falhar:

  - Você especificou uma conta de usuário incorreta. Você pode verificar se existe uma conta de usuário executando um comando semelhante a este:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server. Para verificar se uma conta de usuário está habilitada para o Lync Server, execute um comando semelhante ao seguinte:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está habilitado no momento para o Lync Server.

  - Você especificou um pool de registradores incorreto. Você pode retornar os FQDNs dos seus pools de registradores usando este comando:
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - No momento, o pool de registradores não está disponível. Tente executar o ping no pool para ver se ele responde:
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

