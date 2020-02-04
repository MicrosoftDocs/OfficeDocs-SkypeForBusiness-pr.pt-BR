---
title: 'Lync Server 2013: testar a capacidade dos usuários móveis de trocar mensagens instantâneas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile users' ability to exchange instant messages
ms:assetid: a78a048f-d413-4bee-8626-d62b8b74f811
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767950(v=OCS.15)
ms:contentKeyID: 63969638
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db5af113c6ea87a700ca824bcef09b525338f4e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a>Testar a capacidade dos usuários móveis de trocar mensagens instantâneas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-06-07_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Cronograma de verificação</p></td>
<td><p>Mensal</p></td>
</tr>
<tr class="even">
<td><p>Ferramenta de teste</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Permissões necessárias</p></td>
<td><p>Quando executado localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</p>
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsMcxP2PIM. Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O serviço de mobilidade permite que os usuários de dispositivos móveis executem itens como:

1.  Trocar mensagens instantâneas e informações de presença.

2.  Armazene e recupere a caixa postal internamente em vez de usar o seu provedor sem fio.

3.  Aproveite os recursos do Lync Server, como chamada via trabalho e conferência discada.

O cmdlet Test-CsMxcP2PIM fornece uma maneira rápida e fácil de verificar se os usuários podem usar o serviço de mobilidade para trocar mensagens de chat.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

Para executar esse teste, você deve criar dois objetos de credenciais do Windows PowerShell (objetos que contêm o nome e a senha da conta) para cada conta. Em seguida, você deve incluir esses objetos de credenciais e os endereços SIP das duas contas ao chamar Test-CsMcxP2PIM:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinação do sucesso ou falha

Se os dois usuários de teste puderem trocar mensagens de chat usando o serviço de mobilidade, o teste-CsMcxP2PIM retornará o êxito do resultado do teste:

FQDN de destino: atl-cs-001.litwareinc.com

URI de destino:http://atl-cs-001.litwareinc.com:443/mcx

Resultado: êxito

Latência: 00:00:00

Mensagem de erro:

Correto

Se o teste falhar, o resultado será definido como Failure e uma mensagem de erro detalhada e o diagnóstico serão exibidos:

FQDN de destino: atl-cs-001.litwareinc.com

URI de destino:https://atl-cs-001.litwareinc.com:443/mcx

Resultado: falha

Latência: 00:00:00

Mensagem de erro: nenhuma resposta recebida para o serviço de tíquete na Web.

Exceção interna: a solicitação HHTP está não autorizada com

esquema de negociação do cliente ' NTLM '. A autenticação

o cabeçalho recebido do servidor era ' Negotiate, NTLM '.

Exceção interna: o servidor remoto retornou um erro:

(401) não autorizado.

Correto

Diagnóstico interno: X-MS-Server-Fqdb: ATL-cs-

001.litwareinc.com

Cache-Control: Private

Tipo de conteúdo: texto/HTML; charset = utf-8.

Servidor: Microsoft-IIS/8.5

WWW-Authenticate: Negotiate, NTLM

X-ativado por: ASP.NET

X-tipo de conteúdo-opções: nofarejador

Data: quarta-feira, 28 de maio de 2014 19:16:05 GMT

Content-Length: 6305

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Se Test-CsMcxP2PIM falhar, seu primeiro passo deve ser verificar se o serviço de mobilidade está ativo e em execução. Isso pode ser feito usando um navegador da Web para verificar se a URL do serviço de mobilidade do seu pool do Lync Server pode ser acessada. Por exemplo, esse comando verifica a URL para o conjunto de atl-cs-001.litwareinc.com:

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

Se o serviço de mobilidade parecer estar em execução, verifique se os dois usuários de teste têm contas válidas do Lync Server. Você pode recuperar informações da conta usando um comando semelhante a este:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Se a propriedade Enabled não for igual a true ou se o comando falhar, isso significará que o usuário não tem uma conta válida do Lync Server.

Você também deve verificar se o usuário está habilitado para mobilidade. Para isso, primeiro determine a política de mobilidade atribuída à conta:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

Depois de saber o nome da política, use o cmdlet Get-CsMobilityPolicy para verificar se a política em questão (por exemplo, RedmondMobilityPolicy) tem a propriedade EnableMobility definida como true:

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

Se você receber uma mensagem de erro com cabeçalhos de autenticação, isso geralmente significa que você não especificou uma conta de usuário válida. Verifique o nome de usuário e a senha e tente testar novamente. Se você estiver convencido de que a conta de usuário é válida, use o cmdlet Get-CsWebServiceConfiguration e verifique o valor da Propriedade UseWindowsAuth. Isso indicará quais métodos de autenticação estão habilitados em sua organização. Para obter mais dicas sobre como solucionar problemas com o serviço de mobilidade, confira a [solução de problemas de solução de problemas de conectividade externa do Lync Mobility passo a passo](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).

</div>

</div>

<span> </span>

</div>

</div>

</div>

