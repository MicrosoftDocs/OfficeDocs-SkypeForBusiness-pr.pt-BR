---
title: 'Lync Server 2013: testar chamadas de áudio/vídeo ponto a ponto'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing peer to peer audio/video call
ms:assetid: 95eb3693-b866-4652-bc45-9b75fdb40b49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743835(v=OCS.15)
ms:contentKeyID: 63969627
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea5283f588315d06387ed2d441f138538cd13ca3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193964"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-peer-to-peer-audiovideo-call-in-lync-server-2013"></a>Teste de chamada de áudio/vídeo ponto a ponto no Lync Server 2013

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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsP2PAV. Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsP2PAV&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

Test-CsP2PAV é usado para determinar se um par de usuários de teste pode participar de uma conversa de A/V ponto a ponto. Para testar esse cenário, o cmdlet é iniciado registrando os dois usuários no Lync Server. Presumindo-se que os dois logons sejam bem-sucedidos, o primeiro usuário convidará o segundo para participar da chamada de áudio/vídeo. O segundo usuário aceitará a chamada, a conexão entre os dois usuários será testada e, em seguida, a chamada será encerrada e os usuários de teste farão o logoff do sistema.

Test-CsP2PAV não realiza uma chamada A/V. As informações de multimídia não são trocadas entre os usuários de teste. Em vez disso, o cmdlet verifica apenas se as conexões apropriadas podem ser feitas e se os dois usuários podem conduzir essa chamada.

Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) .

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O cmdlet Test-CsP2PAV pode ser executado usando um par de contas de teste pré-configuradas (consulte Configurando contas de teste para executar testes do Lync Server) ou as contas de dois usuários que estão habilitados para o Lync Server. Para executar essa verificação usando contas de teste, basta especificar o FQDN do pool do Lync Server que está sendo testado. Por exemplo:

    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com"

Para executar essa verificação usando contas de usuário reais, você deve criar dois objetos de credenciais do Lync Server (objetos que contêm o nome da conta e a senha) para cada conta. Em seguida, você deve incluir esses objetos de credenciais e os endereços SIP das duas contas ao chamar Test-CsP2PAV:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

Se os dois usuários de teste puderem concluir uma chamada de A/V ponto a ponto, você receberá uma saída semelhante à propriedade Result marcada como **Success:**

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: êxito

Latência: 00:00:06.8630376

Erros

Diagnóstico

Se os usuários de teste não puderem concluir a chamada, o resultado será mostrado como falha, e informações adicionais serão registradas nas propriedades de erro e diagnóstico:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: falha

Latência: 00:00:00

Erro: 480, temporariamente indisponível

Diagnóstico: ErrorCode = 15030, Source = ATL-cs-001. litwareinc. com, Reason = Failed

para rotear para o Exchange Server

Microsoft. RTC. Signaling. DiagnosticHeader

Por exemplo, a saída anterior diz que o teste falhou porque o Microsoft Exchange Server não pôde ser contatado. Essa mensagem de erro normalmente indica um problema na configuração da Unificação de mensagens do Exchange.

Se Test-CsP2PAV falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:

Test-CsP2PAV-TargetFqdn "atl-cs-001.litwareinc.com"-Verbose

Quando o parâmetro Verbose for incluído, o Test-CsP2PAV retornará uma conta passo a passo de cada ação que tentou que verificou a capacidade do usuário especificado fazer logon no Lync Server. Por exemplo, suponha que o teste falhou com o seguinte diagnóstico:

ErrorCode = 6003, Source = ATL-cs-001. litwareinc. com, razão = não há suporte para a solicitação de diálogo

Se você executar Test-CsP2PAV novamente e incluir o parâmetro Verbose, receberá uma saída semelhante a esta:

VERBOse: atividade de ' registro ' iniciada.

Enviando solicitação de registro:

FQDN de destino = atl-cs-011.litwareinc.com

Endereço SIP do usuário = sip:kenmyer@litwareinc.com

Porta do registrador = 5062.

O tipo de autenticação ' IWA ' é selecionado.

Uma exceção ' o ponto de extremidade não pôde ser registrado. Consulte ErrorCode por motivo específico. " ocorrido durante a execução do fluxo de trabalho Microsoft. RTC. SyntheticTransactions. workflows. STP2PAVWorkflow.

Embora ele possa não ser imediatamente óbvio, se você examinar a saída cuidadosamente, verá que uma porta de registrador incorreta (porta 5062) foi especificada. Por sua vez, isso causaria falha no teste.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais Test-CsP2PAV pode falhar:

  - Você especificou uma conta de usuário que não é válida. Você pode verificar se uma conta de usuário existe executando um comando semelhante a este:
    
    Get-CsUser "sip:kenmyer@litwareinc.com"

  - A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server. Para verificar se uma conta de usuário está habilitada para o Lync Server, execute um comando semelhante ao seguinte:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está atualmente habilitado para o Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

