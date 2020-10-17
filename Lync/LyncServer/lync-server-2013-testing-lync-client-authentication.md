---
title: 'Lync Server 2013: testar a autenticação de cliente do Lync'
description: 'Lync Server 2013: testando a autenticação de cliente do Lync.'
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
ms.openlocfilehash: 03694b7fd56d7847d8d493304b97af335d2a5b4d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560577"
---
# <a name="testing-lync-client-authentication-in-lync-server-2013"></a>Testando a autenticação de cliente do Lync no Lync Server 2013

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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsClientAuth. Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsClientAuth&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet Test-CsClientAuth permite que você determine se um usuário pode fazer logon no Lync Server usando um certificado de cliente, é possível executar o cmdlet Test-CsClientAuth. Depois de chamar Test-CsClientAuth, o cmdlet contata o serviço de provisionamento de certificados e baixa uma cópia dos certificados de clientes para o usuário especificado. Se um certificado de cliente puder ser encontrado e baixado, Test-CsClientAuth tentará fazer logon usando esse certificado. Se o logon for bem sucedido, Test-CsClientAuth irá fazer logoff e relatar se o teste teve êxito. Se nenhum certificado for encontrado ou baixado, ou se o cmdlet não conseguir fazer logon usando o certificado, Test-CsClientAuth irá relatar que o teste fracassou.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O cmdlet Test-CsClientAuth é executado usando a conta de qualquer usuário habilitado para o Lync Server. Para executar essa verificação usando uma conta de usuário real, você deve primeiro criar um objeto de credenciais do Windows PowerShell que contenha o nome da conta e a senha. Em seguida, você deve incluir o objeto Credentials e o endereço SIP atribuído à conta quando o sistema chama Test-CsClientAuth:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsClientAuth](https://technet.microsoft.com/library/gg398712\(v=ocs.14\).aspx) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

Se o usuário especificado puder fazer logon no Lync Server usando um certificado de cliente, você receberá uma saída semelhante a esta, com a propriedade Result marcada como **êxito:**

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: êxito

Latência: 00:00:06.8630376

Erros

Diagnóstico

Se o usuário especificado não puder fazer logon, o resultado será mostrado como falha e informações adicionais serão registradas nas propriedades de erro e diagnóstico:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: falha

Latência: 00:00:03.3645259

Erro: não foi possível baixar um certificado de CS para o usuário fornecido. Verifique se

o URI fornecido e as credenciais estão corretos.

Diagnóstico

Por exemplo, a saída anterior diz que o teste falhou porque um certificado de cliente válido não pôde ser localizado para o usuário especificado. Você pode retornar uma lista de certificados de cliente emitidos para um usuário executando um comando da seguinte maneira:

    Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

Se Test-CsClientAuth falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -Verbose

Quando o parâmetro Verbose é incluído, Test-CsClientAuth retornará uma conta passo a passo de cada ação que tentou quando verificou a capacidade do usuário especificado fazer logon no Lync Server. Por exemplo:

Tentando baixar um certificado CS para o usuário: ponto de extremidade kenmyer@litwareinc.com: STEpid

URL do serviço Web: https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc

Não foi possível baixar um certificado de CS do serviço Web.

Fira

\- A URL do serviço Web é válida e os serviços Web são funcionais

\-Se estiver usando \\ \\ o PIN PhoneNo para autenticação, certifique-se de que eles correspondam ao URI do usuário

\- Se estiver usando a \\ autenticação Kerberos NTLM, certifique-se de ter fornecido credenciais válidas

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns para que Test-CsClientAuth possa falhar:

  - Você especificou uma conta de usuário que não era válida. Você pode verificar se uma conta de usuário existe executando um comando semelhante a este:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server. Para verificar se uma conta de usuário está habilitada para o Lync Server, execute um comando semelhante ao seguinte:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está atualmente habilitado para o Lync Server.

  - O usuário de teste pode não ter um certificado de cliente válido. Você pode retornar informações sobre os certificados de cliente atribuídos a um usuário usando um comando semelhante a este:
    
        Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

