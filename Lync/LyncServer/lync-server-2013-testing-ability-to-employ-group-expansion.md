---
title: 'Lync Server 2013: testando a capacidade de empregar a expansão do grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing ability to employ group expansion
ms:assetid: 9b0fc954-6f9c-411a-ab32-94ebabc42de2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743836(v=OCS.15)
ms:contentKeyID: 63969634
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f99be38a906c508346f580b36d055ccba86a168e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844653"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a>Testar a capacidade de empregar a expansão de grupo no Lync Server 2013

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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsGroupExpansion. Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet Test-CsGroupExpansion permite determinar se a expansão de grupo está funcionando em sua organização. Quando a expansão de grupo está habilitada, os usuários configuram grupos de distribuição como um contato. Isso significa que esses usuários podem enviar a mesma mensagem instantânea para todos os membros do grupo, endereçando a mensagem para o grupo em vez de a membros individuais desse grupo. A expansão de grupo permite exibir rápida e facilmente todos os membros do grupo e seu status atual.

Com o cmdlet Test-CsGroupExpansion, você especifica um grupo de distribuição do Active Directory usando o endereço de email do grupo. Test-CsGroupExpansion usa a expansão do grupo para recuperar a associação do grupo e comparar a lista recuperada com a associação do endereço de email do grupo que você forneceu. Se houver correspondência entre as duas listas, a expansão do grupo funcionará corretamente. Observe que você pode testar a expansão do grupo de duas maneiras: testando o próprio serviço ou testando o serviço Web associado.

Para obter mais informações, consulte a documentação da ajuda para o cmdlet [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O cmdlet Test-CsGroupExpansion pode ser executado usando uma conta de teste pré-configurada (consulte Configurando contas de teste para executar testes do Lync Server) ou a conta de qualquer usuário que tenha sido habilitado para o Lync Server. Para executar essa verificação usando uma conta de teste, basta especificar o FQDN do pool do servidor do Lync que está sendo testado e o endereço de email de um grupo de distribuição válido. Por exemplo:

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

Para executar essa verificação usando uma conta de usuário real, primeiro você deve criar um objeto de credenciais do Lync Server que contenha o nome da conta e a senha. Em seguida, você deve incluir esse objeto de credenciais e o endereço SIP atribuído à conta quando o sistema chamar Test-CsGroupExpansion:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Para obter mais informações, consulte a documentação da ajuda para o cmdlet [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinação do sucesso ou falha

Se o usuário especificado puder usar a expansão de grupo, você receberá uma saída semelhante a isso com a propriedade Result marcada como **Success:**

TargetUri :https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: êxito

Latência: 00:00:01.1234976

Erros

Correto

Se o usuário especificado não puder usar a expansão de grupo, o resultado será mostrado como falha e as informações adicionais serão gravadas nas propriedades de erro e diagnóstico:

TargetUri :https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: falha

Latência: 00:00:00

Erros

Correto

Test-CsGroupExpansion: não foi possível registrar o ponto de extremidade. Consulte ErrorCode por motivo específico.

A saída anterior informa que o teste falhou porque o usuário especificado não pôde se registrar no Lync Server. Isso normalmente ocorrerá se a conta de teste não existir ou não tiver sido habilitada para o Lync Server. Você pode verificar se a conta existe e determinar se a conta foi habilitada para nm-OCS-14-3ª executando um comando semelhante ao seguinte:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

Se Test-CsGroupExpansion falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

Quando o parâmetro Verbose for incluído, Test-CsGroupExpansion retornará uma conta passo a passo de cada ação que tentou verificar quando verificou a capacidade do usuário especificado para fazer logon no Lync Server. Por exemplo, essa saída indica que o grupo de distribuição especificado não foi encontrado:

Tentando obter a permissão na Web.

URL do serviço Web:https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc

Usando autenticação NTLM/Kerb.

GetWebTicketActivity concluído.

Atividade "VerifyDistributionList" iniciada.

O status da resposta do serviço Web DLX é: não encontrado.

Atividade ' VerifyDistributionList ' concluída em ' 0,2597923 ' segundos.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais Test-CsGroupExpansion pode falhar:

  - Você especificou uma conta de usuário inválida. Você pode verificar se existe uma conta de usuário executando um comando semelhante a este:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server. Para verificar se uma conta de usuário foi habilitada para o Lync Server, execute um comando semelhante ao seguinte:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está habilitado no momento para o Lync Server.

  - A expansão de grupo pode estar desabilitada. É possível desativar a expansão do grupo. Se a expansão do grupo tiver sido desabilitada, o cmdlet Test-CsGroupExpansion falhará. Para determinar se a expansão de grupo está habilitada, use um comando semelhante a este:
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>

