---
title: 'Lync Server 2013: testar notificações por push em telefones inteligentes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test push notifications to smart phones
ms:assetid: 8f5ca7d1-1ccb-4cb0-b417-730559e79b6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767948(v=OCS.15)
ms:contentKeyID: 63969626
ms.date: 03/15/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a0d58c79fcd66229ffda43fa60ab99cedc308ab
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844699"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-push-notifications-to-smart-phones-in-lync-server-2013"></a>Testar notificações por push em Smart Phones no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2017-03-15_


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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsMcxPushNotification. Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxPushNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O serviço de notificação por push (serviço de notificação por push da Apple e o Microsoft Push Notification Service) pode enviar notificações sobre eventos como novas mensagens instantâneas ou nova caixa postal para dispositivos móveis, como iPhones e telefones Windows, mesmo que o cliente do Lync nesses dispositivos, no momento, está suspenso ou em execução em segundo plano. O serviço de notificação por push é um serviço baseado em nuvem que é executado em servidores da Microsoft. Para aproveitar as notificações por push, você deve ser capaz de se conectar e ser autenticado por meio de uma notificação por push. O cmdlet Test-CsMcxPushNotification permite que os administradores verifiquem se as solicitações de notificação por push podem ser roteadas pelo servidor de borda para a Clearinghouse de notificação por push.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

Para testar o serviço de notificação por push, chame o cmdlet Test-CsMcxPushNotification. Certifique-se de especificar o nome de domínio totalmente qualificado do seu servidor de borda:

    Test-CsMcxPushNotification -AccessEdgeFqdn "atl-edge-001.litwareinc.com"

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinação do sucesso ou falha

Se Test-CsMcxPushNotification tiver êxito, o cmdlet retornará o resultado do teste Success:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: êxito

Latência: 00:00:00

Erros

Correto

Se Test-CsMcxPushNotification não conseguir se conectar à Clearinghouse de notificação por push, o cmdlet normalmente não retornará um resultado de teste de falha. Em vez disso, o comando geralmente será reprovado completamente. Por exemplo:

Test-CsMcxPushNotification: uma resposta do 504 (tempo limite do servidor) foi recebida da rede e a operação falhou. Consulte os detalhes da exceção para obter mais informações.

Na linha: 1 caractere: 27

\+Test-CsMcxPushNotification \< \< \< \< -AccessEdgeFqdn lyncedge.mydomain.com

\+CategoryInfo: OperationStopped: (:) \[Test-CsMcxPushNotification\], FailureResponseException

\+FullyQualifiedErrorId: WorkflowNotCompleted, Microsoft. RTC. Management. SyntheticTransactions. TestMcxPushNotificationCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Se o serviço de notificação por push falhar, geralmente indica problemas de comunicação com o servidor de borda ou problemas de comunicação com a casa de compensação da notificação por push. Se você tiver problemas ao executar Test-CsMcxPushNotification, a primeira coisa que você deve fazer é verificar se o servidor de borda está funcionando corretamente. Uma maneira de fazer isso é usar o cmdlet Test-CsAVEdgeConnectivity:

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsAVEdgeConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Essa verificação verifica se um usuário especificado pode se conectar ao servidor de borda.

Se o servidor de borda parecer estar funcionando corretamente, isso geralmente significa que você não consegue se conectar à Clearinghouse de notificação por push. Geralmente, isso significa que você não configurou o URI da compensação corretamente ou que você não tem um registro SRV DNS que aponta para esta URL. Você pode verificar se o URI está definido com o valor correto (sip:push@push.lync.com) executando este comando:

    Get-CsMcxConfiguration

Se a propriedade PushNotificationProxyUri estiver definida como algo diferente de sip:push@push.lync.com, você poderá corrigir esse problema usando o cmdlet Set-McxConfiguration. Por exemplo, este comando define corretamente o URI em toda a sua organização:

    Get-CsMcxConfiguration | Set-CsMcxConfiguration -PushNotificationProxyUri "sip:push@push.lync.com"

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [set-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) .

Se o URI estiver configurado corretamente, seu próximo passo deve ser verificar se você tem um registro SRV DNS que é resolvido para o seu domínio SIP e para o seu servidor de borda. Para obter mais informações sobre como configurar esses registros, consulte o tópico da ajuda requisitos de DNS para mobilidade. Observe que a seguinte mensagem de erro geralmente indica um problema com os registros de DNS:

Uma resposta do 504 (tempo limite do servidor) foi recebida da rede e a operação falhou. Consulte os detalhes da exceção para obter mais informações.

Também é possível que Test-CsMcxConfiguration falhe com esta mensagem de erro:

Test-CsMcxPushNotification: solicitação de notificação por push recusada.

Na linha: 1 caractere: 27

\+Test-CsMcxPushNotification\<\<\<\<

\+CategoryInfo: OperationStopped: (:) \[Test-CsMcxPushNotification\], SyntheticTransactionException

\+FullyQualifiedErrorId: WorkflowNotCompleted, Microsoft. RTC. Management. SyntheticTransactions. TestMcxPushNotificationCmdlet

A mensagem "solicitação de notificação por push recusada" geralmente ocorre se você habilitou a filtragem de URL e está bloqueando os prefixos http: e https:. Você pode determinar quais prefixos estão sendo bloqueados usando um comando semelhante ao seguinte:

``` 
 (Get-CsImFilterConfiguration -Identity Global).Prefixes
```

Se http: ou https: aparecer nos resultados, você deve removê-los da lista de prefixos bloqueados para que as notificações por push funcionem. Isso pode ser feito usando comandos semelhantes aos seguintes:

    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="http:"}
    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="https:"}

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [set-CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration).

</div>

</div>

<span> </span>

</div>

</div>

</div>

