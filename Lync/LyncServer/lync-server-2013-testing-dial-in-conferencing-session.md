---
title: 'Lync Server 2013: testando sessão de conferência discada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing dial-in conferencing session
ms:assetid: 6c505be5-5af7-450c-b3ca-10d9122bee5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743834(v=OCS.15)
ms:contentKeyID: 63969613
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1afb4ee2e1a500b08c3481f71994f585298bc8c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745831"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-dial-in-conferencing-session-in-lync-server-2013"></a>Testando sessão de conferência discada no Lync Server 2013

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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsDialInConferencing. Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialInConferencing&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet Test-CsDialInConferencing verifica se um usuário pode participar de uma conferência discada. Test-CsDialInConferencing funciona tentando registrar um usuário de teste no sistema. Se o logon for bem-sucedido, o cmdlet usará as credenciais e permissões do usuário para experimentar todos os números de acesso de conferência discada disponíveis. O êxito ou a falha de cada tentativa de discagem será observado, e o usuário de teste será desconectado do Lync Server. Test-CsDialInConferencing verifica apenas se as conexões apropriadas podem ser feitas. Na verdade, o cmdlet não faz chamadas telefônicas nem cria conferências discadas que outros usuários podem participar.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O cmdlet Test-CsDialInConferencing pode ser executado usando uma conta de teste pré-configurada (consulte Configurando contas de teste para executar testes do Lync Server) ou a conta de qualquer usuário habilitado para o Lync Server. Para executar essa verificação usando uma conta de teste, basta especificar o FQDN do pool do servidor do Lync que está sendo testado. Por exemplo:

    Test-CsDialInConferencing -TargetFqdn "atl-cs-001.litwareinc.com" 

Para executar essa verificação usando uma conta de usuário real, você deve criar um objeto de credenciais do Windows PowerShell que contenha o nome da conta e a senha. Em seguida, você deve incluir esse objeto de credenciais e o endereço SIP da conta, o teste de chamada-CsDialInConferencing:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsDialInConferencing -TargetFqdn atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Para obter mais informações, consulte a documentação da ajuda para o cmdlet [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinação do sucesso ou falha

Se o usuário especificado puder fazer logon no Lync Server e fazer uma conexão usando um dos números de acesso de conferência discada disponíveis, você receberá uma saída semelhante a isso, com a propriedade Result marcada como **Success:**

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: êxito

Latência: 00:00:06.8630376

Erros

Correto

Se o usuário especificado não puder fazer essa conexão, o resultado será mostrado como uma falha, e informações adicionais serão gravadas nas propriedades de erro e diagnóstico:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: falha

Latência: 00:00:00

Erro: o logon foi negado. Verifique se as credenciais adequadas estão

sendo usado e a conta está ativa.

Exceção interna: NegotiateSecurityAssociation falhou, erro:-

2146893044

Correto

A saída anterior indica que o usuário de teste teve o acesso negado ao próprio Lync Server. Isso normalmente significa que as credenciais do usuário transmitidas para Test-CsDialInConferencing não eram válidas. Por sua vez, você deve recriar o objeto de credenciais do Windows PowerShell. Embora você possa recuperar a senha da conta de usuário, pode verificar o endereço SIP usando um comando semelhante a este:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais Test-CsDialInConferencing pode falhar:

  - Você especificou uma conta de usuário que não é válida. Você pode verificar se existe uma conta de usuário executando um comando semelhante a este:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server. Para verificar se uma conta de usuário está habilitada para o Lync Server, execute um comando semelhante ao seguinte:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está habilitado no momento para o Lync Server.

  - Você pode ter um número incorreto de acesso à conferência discada. Você pode retornar a lista atualmente configurada de números de acesso de conferência discada usando este comando:
    
        Get-CsDialConferencingAccessNumber

</div>

</div>

<span> </span>

</div>

</div>

</div>

