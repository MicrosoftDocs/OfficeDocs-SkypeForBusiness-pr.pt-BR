---
title: 'Lync Server 2013: testar acesso de usuário móvel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile user access
ms:assetid: 81d97420-428b-41b7-91ef-185d572d3456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767947(v=OCS.15)
ms:contentKeyID: 63969624
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6052785bdb8e748ac657d800a630ecc76415af9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42021332"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-mobile-user-access-in-lync-server-2013"></a>Testar o acesso de usuário móvel no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-06-07_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Agenda de verificação</p></td>
<td><p>Mensal</p></td>
</tr>
<tr class="even">
<td><p>Ferramenta de teste</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Permissões obrigatórias</p></td>
<td><p>Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</p>
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsMcxConference. Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O serviço de mobilidade permite que os usuários de dispositivos móveis façam coisas como:

1.  Informações de presença e mensagens instantâneas do Exchange.

2.  Armazenar e recuperar a caixa postal internamente em vez de com seu provedor sem fio.

3.  Aproveite os recursos do Lync Server, como ligar via trabalho e conferência discada. O cmdlet Test-CsMcxConference fornece uma maneira rápida e fácil de verificar se os usuários podem participar e participar de conferências do Lync Server usando um dispositivo móvel.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

Para executar essa verificação, você deve criar três objetos de credenciais do Windows PowerShell (objetos que contêm o nome da conta e a senha) para cada conta. Em seguida, você deve incluir esses objetos de credenciais e os endereços SIP das duas contas ao chamar Test-CsMcxConference, conforme mostrado no exemplo a seguir:

    $organizerCred = Get-Credential "litwareinc\kenmyer"
    $user1Cred = Get-Credential "litwareinc\packerman"
    $user2Cred = Get-Credential "litwareinc\adelaney"
    
    Test-CsMcxConference -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -OrganizerSipAddress "sip:kenmyer@litwareinc.com" -OrganizerCredential $organizerCred -UserSipAddress "sip:pilar@litwareinc.com" -UserCredential $user1Cred -User2SipAddress "sip:adelaney@litwareinc.com" -User2Credential $user2Cred

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

Se a verificação for bem-sucedida, Test-CsMcxConference informará o resultado do teste de êxito:

FQDN de destino: atl-cs-001.litwareinc.com

URI de destino:http://atl-cs-001.litwareinc.com:443/mcx

Resultado: êxito

Latência: 00:00:00

Mensagem de erro:

Diagnóstico

Se a verificação for malsucedida, Test-CsMcxConference relatará um resultado de teste de falha. Esse resultado de teste normalmente será acompanhado por uma mensagem de erro e um diagnóstico detalhados. Por exemplo:

FQDN de destino: atl-cs-001.litwareinc.com

URI de destino:https://atl-cs-001.litwareinc.com:443/mcx

Resultado: falha

Latência: 00:00:00

Mensagem de erro: nenhuma resposta recebida para o serviço de tíquete da Web.

Exceção interna: a solicitação HHTP não é autorizada com o cliente

esquema de negociação ' NTLM '. O cabeçalho de autenticação recebido

do servidor foi ' Negotiate '.

Exceção interna: o servidor remoto retornou um erro: (401)

Não autorizado.

Diagnóstico

Diagnóstico interno: X-MS-Server-Fqdb: atl-cs-001.litwareinc.com

Cache-Control: Private

Content-Type: text/html; charset = utf-8.

Servidor: Microsoft-IIS/8.5

WWW-Authenticate: Negotiate, NTLM

X-powered-by: ASP.NET

X-Content-Type-opções: nosniff

Date: Qua, 28 de maio de 2014 19:22:19 GMT

Content-Length: 6305

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Se Test-CsMcxConference falhar, verifique se o serviço de mobilidade está em execução e se pode ser acessado. Isso pode ser feito usando um navegador da Web para verificar se a URL do serviço de mobilidade do seu pool do Lync Server pode ser acessada. Por exemplo, este comando verifica a URL para o pool atl-cs-001.litwareinc.com:

`https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc`

Se o serviço de mobilidade puder ser acessado, verifique se os usuários de teste possuem contas válidas do Lync Server. Você pode recuperar informações da conta usando um comando semelhante ao seguinte:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Se a propriedade Enabled não for igual a true ou se o comando falhar, isso significa que o usuário não tem uma conta válida do Lync Server. Você também deve verificar se cada conta de usuário está habilitada para mobilidade. Para fazer isso, primeiro determine a política de mobilidade atribuída à conta:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

Depois de saber o nome da política, use o cmdlet Get-CsMobilityPolicy para verificar se a política em questão (por exemplo, Edmondmobilitypolicy) tem a propriedade EnableMobility definida como true:

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

Se você receber uma mensagem de erro "cabeçalho de autenticação" ao executar Test-CsMcxConference, isso geralmente significa que você não especificou uma conta de usuário válida, verifique o nome de usuário e a senha e tente testar novamente. Se você estiver convencido de que a conta de usuário é válida, use o cmdlet Get-CsWebServiceConfiguration e verifique o valor da Propriedade UseWindowsAuth. Isso indicará quais métodos de autenticação estão habilitados em sua organização.

Para obter mais dicas sobre como solucionar problemas do serviço de mobilidade, consulte o blog post [Troubleshooting external Lync Mobility Connectivity issues passo a passo](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).

</div>

</div>

<span> </span>

</div>

</div>

</div>

