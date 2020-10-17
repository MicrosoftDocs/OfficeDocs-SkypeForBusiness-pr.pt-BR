---
title: 'Lync Server 2013: como validar conferências de áudio/vídeo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating audio/video conferences
ms:assetid: 6c8c422a-d501-42cb-820b-b002f9b2250b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720915(v=OCS.15)
ms:contentKeyID: 63969615
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f0bfeef1abcf7b5859c365b7c64b4fcc84f49ae
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503698"
---
# <a name="validating-audiovideo-conferences-in-lync-server-2013"></a>Validar conferências de áudio/vídeo no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>Agenda de verificação</p></td>
<td><p>Diariamente</p></td>
</tr>
<tr class="odd">
<td><p>Ferramenta de teste</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="even">
<td><p>Permissões obrigatórias</p></td>
<td><p>Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</p>
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsAVConference. Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAVConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet Test-CsAVConference verifica se dois usuários de teste podem participar de uma conferência de áudio/vídeo (A/V). Quando o cmdlet for executado, os dois usuários serão registrados no sistema. Após enfrentar o logon bem-sucedido, o primeiro usuário cria uma conferência de A/V e, em seguida, aguarda o segundo usuário ingressar nessa conferência. Depois de uma breve troca de dados, a conferência é excluída e os dois usuários de teste fazem logoff.

Observe que Test-CsAVConference não realiza uma conferência A/V real entre os dois usuários de teste. Em vez disso, o cmdlet verifica se os dois usuários podem fazer todas as conexões necessárias para a realização de uma conferência.

Outros exemplos para este comando podem ser encontrados em [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference).

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O cmdlet Test-CsAVConference pode ser executado usando um par de contas de teste pré-configuradas (Confira Configurando contas de teste para executar testes do Lync Server) ou as contas de dois usuários que estão habilitados para o Lync Server. Para executar essa verificação usando contas de teste, basta especificar o FQDN do pool do Lync Server que está sendo testado. Por exemplo:

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com"

Para executar essa verificação usando contas de usuário reais, você deve criar dois objetos de credenciais do Windows PowerShell (objetos que contêm o nome da conta e a senha) para cada conta. Em seguida, você deve incluir esses objetos de credenciais e os endereços SIP das duas contas ao chamar Test-CsAVConference:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

Se os usuários especificados puderem concluir com êxito uma conferência A/V, você receberá uma saída semelhante a esta, com a propriedade Result marcada como **Success:**

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: êxito

Latência: 00:00:02.6841765

Erros

Diagnóstico

Se os usuários não puderem concluir a conferência, o resultado será mostrado como falha, e informações adicionais serão registradas nas propriedades de erro e diagnóstico:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: falha

Latência: 00:00:00

Erro: 404, não encontrado

Diagnóstico: ErrorCode = 4005, Source = ATL-cs-001.litwareinc.com,

Razão = o URI de destino não está habilitado para SIP ou não

existente.

Microsoft. RTC. Signaling. DiagnosticHeader

Por exemplo, a saída anterior diz que o teste falhou porque pelo menos uma das duas contas de usuário não era válida porque a conta não existe ou porque a conta não foi habilitada para o Lync Server. Você pode verificar a existência das duas contas de teste e se elas foram habilitadas para o Lync Server, executando um comando semelhante ao seguinte:

    "sip:kenmyer@litwareinc.com","sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, enabled

Se Test-CsAVConference falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Quando o parâmetro Verbose é incluído Test-CsAVConference retornará uma conta passo a passo de cada ação que tentou quando verificou a capacidade dos usuários especificados de participar de uma conferência AV. Por exemplo, suponha que o teste falhe e que você receba o seguinte diagnóstico:

ErrorCode = 1008, Source = accessproxy. litwareinc. com, Reason = não é possível resolver o registro SRV de DNS

Se você executar novamente o teste usando o parâmetro Verbose, as informações passo a passo retornadas incluirão uma saída semelhante a esta:

VERBOse: atividade de ' registro ' iniciada.

Enviando solicitação de registro:

FQDN de destino = atl-cs-001.litwareinc.com

Endereço SIP do usuário = sip:davidlongmire@litwareinc.com

Porta do registrador = 5061.

O tipo de autenticação ' confiável ' é selecionado.

Atividade de ' Register ' iniciada.

Enviando solicitação de registro:

FQDN de destino = atl-cs-001.litwareinc.com

Endereço SIP do usuário = sip:kenmyer@litwareinc.com

Porta do registrador = 5061.

O tipo de autenticação ' confiável ' é selecionado.

Uma exceção ' o ponto de extremidade não pôde ser registrado. Consulte ErrorCode por motivo específico. " ocorreu durante o fluxo de trabalho

A última linha desse resultado indica que o usuário sip:kenmyer@litwareinc.com não pôde se registrar no Lync Server. Isso significa que você deve verificar se o endereço SIP sip:kenmyer@litwareinc.com é válido e se o usuário associado está habilitado para o Lync Server.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns para que Test-CsAVConference possa falhar:

  - Você especificou uma conta de usuário que não é válida. Você pode verificar se uma conta de usuário existe executando um comando semelhante a este:
    
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

