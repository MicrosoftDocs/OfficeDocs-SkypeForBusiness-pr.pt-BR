---
title: 'Lync Server 2013: testar a capacidade de executar IM no grupo'
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
ms.openlocfilehash: 7f33d34644f76c9773edbfd9ad5d3945c0c1974c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527818"
---
# <a name="testing-ability-to-do-group-im-in-lync-server-2013"></a>Testando a capacidade de realizar o grupo de IM no Lync Server 2013

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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsGroupIM. Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet Test-CsGroupIM verifica se os usuários da sua organização podem realizar sessões de mensagens instantâneas de grupo. Quando você executa o Test-CsGroupIM, o cmdlet tenta entrar em um par de usuários de teste para o Lync Server. Se houver êxito, Test-CsGroupIM criará uma nova conferência usando o primeiro usuário de teste e, em seguida, convidará o segundo usuário para ingressar na conferência. Depois de uma troca de mensagens, ambos os usuários são desconectados do sistema. Observe que tudo isso ocorre sem qualquer interação do usuário e sem afetar os usuários reais. Por exemplo, suponha que a conta de teste sip:kenmyer@litwareinc.com corresponde a um usuário real que tem uma conta real do Lync Server. Nesse caso, o teste será realizado sem nenhuma interrupção para o Ken Myer real. Por exemplo, mesmo quando a conta de teste Ken Myer fizer logoff do sistema, a pessoa Ken Myer permanecerá conectada. Da mesma forma, o verdadeiro Ken Myer não receberá um convite para ingressar na conferência. Esse convite será enviado para e aceito pela conta de teste.

Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O cmdlet Test-CsGroupIM pode ser executado usando um par de contas de teste pré-configuradas (Confira Configurando contas de teste para executar testes do Lync Server) ou as contas de dois usuários que estão habilitados para o Lync Server. Para executar essa verificação usando contas de teste, basta especificar o FQDN do pool do Lync Server que está sendo testado. Por exemplo:

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com"

Para executar essa verificação usando contas de usuário reais, você deve criar dois objetos de credenciais do Shell de gerenciamento do Lync Server (objetos que contêm o nome da conta e a senha) para cada conta. Em seguida, você deve incluir esses objetos de credenciais e os endereços SIP das duas contas ao chamar Test-CsGroupIM:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsGroupIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

Se os dois usuários podem concluir uma sessão de mensagens instantâneas de grupo, você receberá uma saída semelhante a essa, com a propriedade Result marcada como **Success:**

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: êxito

Latência: 00:00:06.3812203

Erros

Diagnóstico

Se os dois usuários não puderem concluir a sessão de mensagens instantâneas, o resultado será mostrado como falha e as informações adicionais serão registradas nas propriedades de erro e diagnóstico:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: falha

Latência: 00:00:00

Erro: 404, não encontrado

Diagnóstico: ErrorCode = 4005, Source = ATL-cs-001.litwareinc.com,

Razão = o URI de destino não está habilitado para SIP ou não

existente.

Microsoft. RTC. Signaling. DiagnosticHeader

A saída anterior diz que o teste falhou porque pelo menos uma das contas de teste não era válida porque a conta não existe ou porque o usuário não foi habilitado para o Lync Server. Você pode verificar se a conta existe e se a conta foi habilitada para o nm-OCS-14-3ª executando um comando semelhante a este:

    "Ken Myer", "David Longmire" | Get-CsUser | Select-Object SipAddress, Enabled

Se Test-CsGroupIM falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Quando o parâmetro Verbose é incluído, Test-CsGroupIM retornará uma conta passo a passo de cada ação que tentou quando verificou a capacidade dos usuários especificados de participar de uma sessão de mensagens instantâneas de grupo. Por exemplo, se o teste falhar e você for informado de que uma ou mais contas de usuário não são válidas, você pode executar novamente o teste usando o parâmetro Verbose e determinar qual conta de usuário não é válida:

Enviando solicitação de registro:

 FQDN de destino = atl-cs-001.litwareinc.com

 Endereço SIP do usuário = sip:kenmyer@litwareinc.com

 Porta de registro = 5061

O tipo de autenticação ' IWA ' é selecionado.

Uma exceção ' o logon foi negado. Verifique se as credenciais corretas estão sendo usadas e se a conta está ativa

Como você pode ver, neste exemplo, o usuário com o endereço SIP sip:kenmyer@litwareinc.com não pôde fazer logon.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns para que Test-CsGroupIM possa falhar:

  - Você especificou uma conta de usuário incorreta. Você pode verificar se uma conta de usuário existe executando um comando semelhante a este:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server. Para verificar se uma conta de usuário foi habilitada para o Lync Server, execute um comando semelhante ao seguinte:
    
    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object habilitado
    
    Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está atualmente habilitado para o Lync Server.

  - O serviço de mensagens instantâneas pode não estar disponível. Com o Lync Server, você pode configurar o sistema para que o sistema de mensagens instantâneas não fique disponível se o banco de dados de arquivamento não puder ser acessado. Você pode verificar se está executando um comando semelhante ao seguinte:
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    Se BlockOnArchiveFailure estiver definido como true, você deverá determinar se o banco de dados de arquivamento está disponível ou não. Você pode retornar os locais dos seus bancos de dados de arquivamento usando o seguinte comando:
    
        Get-CsService -ArchivingDatabase

  - O servidor de arquivamento pode não estar disponível. Você pode recuperar o FQDN dos seus servidores de arquivamento usando este comando:
    
        Get-CsService -ArchivingServer
    
    Você pode fazer o ping no servidor apropriado para verificar se ele está disponível. Por exemplo:
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

