---
title: 'Lync Server 2013: testando a capacidade de fazer mensagens instantâneas em grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to do group IM
ms:assetid: ca5545bc-51ac-490f-b96b-917bb742ad04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743839(v=OCS.15)
ms:contentKeyID: 63969652
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8552d5caadf26d70265f5538f10c6152eb67dcc8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-do-group-im-in-lync-server-2013"></a>Testar a capacidade de fazer mensagens instantâneas em grupo no Lync Server 2013

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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsGroupIM. Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet Test-CsGroupIM verifica se os usuários em sua organização podem conduzir sessões de mensagens instantâneas em grupo. Ao executar Test-CsGroupIM, o cmdlet tenta entrar em um par de usuários de teste para o Lync Server. Se for bem-sucedido, o Test-CsGroupIM criará uma nova conferência usando o primeiro usuário de teste e convidará o segundo usuário para ingressar na conferência. Após uma troca de mensagens, os dois usuários são desconectados do sistema. Observe que tudo isso acontece sem qualquer interação do usuário e sem afetar os usuários reais. Por exemplo, suponha que o sip:kenmyer@litwareinc.com da conta de teste corresponda a um usuário real que tenha uma conta real do Lync Server. Nesse caso, o teste será realizado sem qualquer interrupção no Ken Myer verdadeiro. Por exemplo, mesmo quando a conta de teste de Ken Myer se desconecta do sistema, Ken Myer a pessoa permanecerá conectada. Da mesma forma, o "Ken Myer" realmente não receberá um convite para participar da conferência. Este convite será enviado para e aceito pela conta de teste.

Para obter mais informações, consulte a documentação da ajuda para o cmdlet [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O cmdlet Test-CsGroupIM pode ser executado usando um par de contas de teste pré-configuradas (consulte Configurando contas de teste para executar testes do Lync Server) ou das contas de dois usuários que estão habilitados para o Lync Server. Para executar essa verificação usando contas de teste, basta especificar o FQDN do pool do servidor do Lync que está sendo testado. Por exemplo:

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com"

Para executar essa verificação usando contas de usuário reais, você deve criar dois objetos de credenciais do Shell de gerenciamento do Lync Server (objetos que contêm o nome e a senha da conta) para cada conta. Em seguida, você deve incluir esses objetos de credenciais e os endereços SIP das duas contas ao chamar Test-CsGroupIM:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsGroupIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

Para obter mais informações, consulte a documentação da ajuda para o cmdlet [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinação do sucesso ou falha

Se os dois usuários puderem concluir uma sessão de mensagens instantâneas em grupo, você receberá uma saída semelhante a isso com a propriedade Result marcada como **Success:**

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: êxito

Latência: 00:00:06.3812203

Erros

Correto

Se os dois usuários não puderem concluir a sessão de mensagens instantâneas, o resultado será mostrado como uma falha, e informações adicionais serão gravadas nas propriedades de erro e diagnóstico:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: falha

Latência: 00:00:00

Erro: 404, não encontrado

Diagnóstico: ErrorCode = 4005, Source = ATL-cs-001.litwareinc.com,

Motivo = o URI de destino não está habilitado para SIP ou não

Existem.

Microsoft. RTC. Signaling. DiagnosticHeader

A saída anterior informa que o teste falhou porque, pelo menos uma das contas de teste não era válida, porque a conta não existe ou porque o usuário não foi habilitado para o Lync Server. Você pode verificar se a conta existe e se a conta foi habilitada para nm-OCS-14-3ª executando um comando semelhante a este:

    "Ken Myer", "David Longmire" | Get-CsUser | Select-Object SipAddress, Enabled

Se Test-CsGroupIM falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Quando o parâmetro Verbose estiver incluído, Test-CsGroupIM retornará uma conta passo a passo de cada ação que tentou verificar quando verificou a capacidade dos usuários especificados para participar de sessões de mensagens instantâneas em grupo. Por exemplo, se o teste falhar e você for informado de que uma ou mais contas de usuário não são válidas, você pode executar novamente o teste usando o parâmetro Verbose e determinar qual conta de usuário não é válida:

Enviando solicitação de registro:

 FQDN de destino = atl-cs-001.litwareinc.com

 Endereço SIP do usuário = sip:kenmyer@litwareinc.com

 Porta do registro = 5061

O tipo de autenticação ' IWA ' é selecionado.

Uma exceção ' o logon foi negado. Verifique se as credenciais corretas estão sendo usadas e se a conta está ativa

Como você pode ver, neste exemplo, o usuário que tem o endereço SIP sip:kenmyer@litwareinc.com não pôde fazer logon.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais Test-CsGroupIM pode falhar:

  - Você especificou uma conta de usuário incorreta. Você pode verificar se existe uma conta de usuário executando um comando semelhante a este:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server. Para verificar se uma conta de usuário foi habilitada para o Lync Server, execute um comando semelhante ao seguinte:
    
    Get-CsUser "sip:kenmyer@litwareinc.com" | Selecionar-objeto habilitado
    
    Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está habilitado no momento para o Lync Server.

  - O serviço de mensagem instantânea pode não estar disponível. Com o Lync Server, você pode configurar o sistema para que o sistema de mensagens instantâneas não esteja disponível se o banco de dados de arquivamento não puder ser acessado. Você pode verificar se está executando um comando semelhante ao seguinte:
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    Se BlockOnArchiveFailure for definido como true, você deve determinar se o banco de dados de arquivamento está disponível. Você pode retornar os locais dos bancos de dados de arquivamento usando o seguinte comando:
    
        Get-CsService -ArchivingDatabase

  - O servidor de arquivamento pode não estar disponível. Você pode recuperar o FQDN dos seus servidores de arquivamento usando este comando:
    
        Get-CsService -ArchivingServer
    
    Em seguida, você pode executar ping no servidor apropriado para verificar se ele está disponível. Por exemplo:
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

