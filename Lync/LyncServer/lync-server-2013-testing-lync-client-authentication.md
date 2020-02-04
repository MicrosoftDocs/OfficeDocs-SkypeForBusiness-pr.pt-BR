---
title: 'Lync Server 2013: testando a autenticação do cliente do Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Client authentication
ms:assetid: e22114cb-4456-4e5f-93ab-51592c4a8209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689120(v=OCS.15)
ms:contentKeyID: 63969659
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e24f579a4fcaca2651c0225b515241db00ff990
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745701"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-client-authentication-in-lync-server-2013"></a>Testando a autenticação do cliente do Lync no Lync Server 2013

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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsClientAuth. Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsClientAuth&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet Test-CsClientAuth permite que você determine se um usuário pode fazer logon no Lync Server usando um certificado de cliente, você pode executar o cmdlet Test-CsClientAuth. Depois de chamar Test-CsClientAuth, o cmdlet entrará em contato com o serviço de provisionamento de certificado e baixará uma cópia de qualquer certificado de cliente para o usuário especificado. Se um certificado de cliente pode ser encontrado e baixado, o Test-CsClientAuth tentará fazer logon usando esse certificado. Se o logon for bem-sucedido, Test-CsClientAuth fará logoff e relatará que o teste foi bem-sucedido. Se não for possível localizar ou baixar um certificado, ou se o cmdlet não conseguir fazer logon usando esse certificado, o teste-CsClientAuth reportará que o teste falhou.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O cmdlet Test-CsClientAuth é executado usando a conta de qualquer usuário habilitado para o Lync Server. Para executar essa verificação usando uma conta de usuário real, primeiro você deve criar um objeto de credenciais do Windows PowerShell que contenha o nome da conta e a senha. Em seguida, você deve incluir esse objeto de credenciais e o endereço SIP atribuído à conta quando o sistema chamar Test-CsClientAuth:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Para obter mais informações, consulte a documentação da ajuda para o cmdlet [Test-CsClientAuth](http://technet.microsoft.com/en-us/library/gg398712\(v=ocs.14\).aspx) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinação do sucesso ou falha

Se o usuário especificado puder fazer logon no Lync Server usando um certificado de cliente, você receberá uma saída semelhante a isso, com a propriedade Result marcada como **Success:**

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: êxito

Latência: 00:00:06.8630376

Erros

Correto

Se o usuário especificado não puder fazer logon, o resultado será mostrado como uma falha e informações adicionais serão gravadas nas propriedades de erro e diagnóstico:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: falha

Latência: 00:00:03.3645259

Erro: não foi possível baixar um certificado de CS para o usuário fornecido. Verifique se

as credenciais e o URI fornecidos estão corretos.

Correto

Por exemplo, a saída anterior informa que o teste falhou porque um certificado de cliente válido não pôde ser localizado para o usuário especificado. Você pode retornar uma lista dos certificados de cliente emitidos para um usuário executando um comando da seguinte maneira:

    Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

Se Test-CsClientAuth falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -Verbose

Quando o parâmetro Verbose estiver incluído, Test-CsClientAuth retornará uma conta passo a passo de cada ação que tentou verificar quando verificou a capacidade do usuário especificado para fazer logon no Lync Server. Por exemplo:

Tentando baixar um certificado de CS para o usuário: kenmyer@litwareinc.com Endpoint: STEpid

URL do serviço Web:https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc

Não foi possível baixar um certificado de CS do serviço Web.

SELECIONAR

\-A URL do serviço Web é válida e os serviços Web são funcionais

\-Se estiver usando\\\\o pino PhoneNo para autenticar, certifique-se de que correspondam ao URI do usuário

\-Se estiver usando\\a autenticação Kerberos NTLM, certifique-se de que você forneceu credenciais válidas

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais Test-CsClientAuth pode falhar:

  - Você especificou uma conta de usuário que não era válida. Você pode verificar se existe uma conta de usuário executando um comando semelhante a este:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server. Para verificar se uma conta de usuário está habilitada para o Lync Server, execute um comando semelhante ao seguinte:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está habilitado no momento para o Lync Server.

  - O usuário de teste pode não ter um certificado de cliente válido. Você pode retornar informações sobre os certificados de cliente atribuídos a um usuário usando um comando semelhante a este:
    
        Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

