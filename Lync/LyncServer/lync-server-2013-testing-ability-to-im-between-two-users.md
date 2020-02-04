---
title: 'Lync Server 2013: testando a capacidade de enviar mensagens instantâneas entre dois usuários'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to IM between two users
ms:assetid: a0f3f5c6-f115-4c3f-90ac-5fdc932b417e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743838(v=OCS.15)
ms:contentKeyID: 63969635
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 201aceceadeba3c6c97530925273097fe039bc08
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745891"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-im-between-two-users-in-lync-server-2013"></a>Testar a capacidade de enviar mensagens instantâneas entre dois usuários no Lync Server 2013

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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsIM. Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet Test-CsIM verifica se um par de usuários de teste podem trocar mensagens instantâneas. Quando chamado, o cmdlet Test-CsIM começa a tentar fazer logon em um par de usuários de teste para o Lync Server. Pressupondo que os dois logons sejam bem-sucedidos, o cmdlet iniciará uma sessão de mensagem instantânea entre os dois usuários de teste. (O usuário 1 convida o usuário 2 a uma sessão de mensagem instantânea, e o usuário 2 aceita o convite.) Depois de verificar se as mensagens podem ser trocadas entre os dois usuários, teste-CsIM e, em seguida, termina a sessão de mensagem instantânea e registra os dois usuários fora do sistema.

Para obter mais informações, consulte a documentação da ajuda para o cmdlet [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) .

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O cmdlet Test-CsIM pode ser executado usando um par de contas de teste pré-configuradas (consulte Configurando contas de teste para executar testes do Lync Server) ou das contas de dois usuários que estão habilitados para o Lync Server. Para executar essa verificação usando contas de teste, basta especificar o FQDN do pool do servidor do Lync que está sendo testado. Por exemplo:

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com"

Para executar essa verificação usando contas de usuário reais, você deve criar dois objetos de credenciais do Windows PowerShell (objetos que contêm o nome da conta e a senha) para cada conta. Em seguida, você deve incluir esses objetos de credenciais e os endereços SIP das duas contas ao chamar Test-CsIM:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

Para obter mais informações, consulte a documentação da ajuda para o cmdlet [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinação do sucesso ou falha

Se os dois usuários puderem concluir uma sessão de mensagens instantâneas, você receberá uma saída semelhante a isso, com a propriedade Result marcada como **Success:**

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: êxito

Latência: 00:00:06.6630911

Erros

Correto

Se os usuários do teste não puderem concluir a sessão, o resultado será mostrado como uma falha, e informações adicionais serão gravadas nas propriedades de erro e diagnóstico:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: falha

Latência: 00:00:00

Erro: 504, tempo limite do servidor

Diagnóstico: ErrorCode = 2, origem = ATL-cs-001. litwareinc. com, motivo = Veja

código de resposta e frase de motivo.

Microsoft. RTC. Signaling. DiagnosticHeader

Por exemplo, a saída anterior informa que o teste falhou porque o usuário especificado não foi encontrado. Você pode determinar se um endereço SIP é válido (e se o usuário que atribuiu o endereço SIP foi habilitado para o Lync Server) executando este comando:

    Get-CsUser "Ken Myer" | Select-Object SipAddress, Enabled

Se Test-CsIM falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Quando o parâmetro Verbose estiver incluído, Test-CsIM retornará uma conta passo a passo de cada ação que tentou verificar quando verificou a capacidade dos dois usuários de teste participarem de uma sessão de mensagem instantânea. Por exemplo, veja a seguir uma saída de exemplo que ocorre quando um conjunto incorreto de credenciais de usuário (nesse caso, uma senha incorreta) é fornecido para Test-CsIM:

Enviando solicitação de registro:

FQDN de destino = atl-cs-011.litwareinc.com

Endereço SIP do usuário = sip:kenmyer@litwareinc.com

Porta do registrador = 5061

O tipo de autenticação ' IWA ' é selecionado.

Acesso à inscrição em SIP/ATL-cs-001. litwareinc. com

Atividade ' Register ' concluída em ' 0, 601795 ' segundos.

Uma exceção ' o logon foi negado. Verifique se as credenciais corretas estão sendo usadas e se a conta está ativa. ocorridas durante o fluxo de trabalho.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais Test-CsIM pode falhar:

  - Você especificou uma conta de usuário que não é válida. Você pode verificar se existe uma conta de usuário executando um comando semelhante a este:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server. Para verificar se uma conta de usuário está habilitada para o Lync Server, execute um comando semelhante ao seguinte:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
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

