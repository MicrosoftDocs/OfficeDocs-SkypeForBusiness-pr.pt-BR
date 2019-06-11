---
title: 'Lync Server 2013: testando conferências de áudio de terceiros'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing third-party audio conferencing
ms:assetid: 0428eb2f-a5ce-47e5-9ea4-383965dfc1e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727299(v=OCS.15)
ms:contentKeyID: 63969576
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1c23f65015dd34f5efbaafa8472466394caa52c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844607"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-third-party-audio-conferencing-in-lync-server-2013"></a>Testar conferências de áudio de terceiros no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-11-01_


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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsAudioConferencingProvider. Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAudioConferencingProvider&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

Um provedor de conferência de áudio é uma empresa de terceiros que oferece serviços de conferência às organizações. Entre outras coisas, os provedores de conferência de áudio permitem que usuários que estiverem longe do local e não conectados à rede corporativa ou pela Internet participem do áudio de uma conferência ou reunião. Geralmente, os provedores de audioconferência fornecem serviços de high-end, como a tradução ao vivo, a transcrição e a assistência ao vivo por conferência ao vivo.

O cmdlet **Test-CsAudioConferencingProvider** é usado para verificar se um usuário consegue fazer uma conexão com seu provedor de serviços de audioconferência. Observe que esse cmdlet pode ser executado de uma das duas maneiras. Muitos administradores usarão os cmdlets CsHealthMonitoringConfiguration para configurar usuários de teste para cada um dos seus pools de registradores. Esses usuários de teste representam um par de contas de usuário que foram pré-configuradas para uso com transações sintéticas. (Geralmente são contas de teste e não contas que pertencem a usuários reais.) Se os usuários de teste estiverem configurados para um pool, os administradores poderão executar o cmdlet **Test-CsAudioConferencingProvider** nesse pool sem ter que especificar a identidade de (e fornecer as credenciais para) a conta de usuário envolvida no teste.

Como alternativa, os administradores podem executar o cmdlet **Test-CsAudioConferencingProvider** usando uma conta de usuário real. Se você decidir conduzir o teste usando uma conta de usuário real, será necessário fornecer o nome de logon e a senha da conta.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O exemplo 1 verifica se um usuário de teste definido para o pool atl-cs-001.litwareinc.com é capaz de se conectar ao seu provedor de serviços de audioconferência. Esse comando requer que pelo menos um usuário de teste seja definido para o pool. Se nenhum usuário de teste tiver sido definido para atl-cs-001.litwareinc.com, o comando irá falhar; Isso ocorre porque o cmdlet **Test-CsAudioConferencingProvider** não sabe qual o usuário empregar no teste. Se você não definiu usuários de teste para um pool, deve incluir o parâmetro UserSipAddress e as credenciais da conta de usuário que o comando deve empregar ao verificar a conexão com um provedor de audioconferência.

    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com 

Os comandos mostrados no exemplo 2 testam a capacidade de um usuário específico\\(litwareinc kenmyer) para se conectar ao seu provedor de serviços de audioconferência. Para fazer isso, o primeiro comando do exemplo usa o cmdlet Get-Credential para criar um objeto de credenciais da interface de linha de comando do Windows PowerShell que contém o nome e a senha do usuário Ken Myer. (Como o nome de logon\\litwareinc kenmyer foi incluído como um parâmetro, a caixa de diálogo solicitação de credenciais do Windows PowerShell exige que o administrador digite a senha para a conta Ken Myer.) O objeto de credenciais resultante é armazenado em uma variável chamada $credential.

Em seguida, o segundo comando verifica se este usuário pode se conectar ao seu provedor de serviços de audioconferência. Para executar essa tarefa, o cmdlet Test-CsAudioConferencingProvider é chamado, juntamente com três parâmetros: TargetFqdn (o FQDN do pool de registrador); Usercredential (o objeto do Windows PowerShell que contém as credenciais de usuário de Ken Myer); e UserSipAddress (o endereço SIP correspondente às credenciais de usuário fornecidas).

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinação do sucesso ou falha

Se o provedor de serviços de audioconferência estiver configurado corretamente, você receberá uma saída semelhante a isso, com a propriedade Result marcada como **Success:**

FQDN de destino: atl-sql-001.litwareinc.com

Resultado: êxito

Latência: 00:00:00

Mensagem de erro:

Correto

Se o usuário especificado não puder fazer logon ou logoff, o resultado será mostrado como uma **falha**, e informações adicionais serão gravadas nas propriedades de erro e diagnóstico:

FQDN de destino: atl-sql-001.litwareinc.com

Resultado: falha

Latência: 00:00:00

Mensagem de erro: 10060, falha na tentativa de conexão porque a parte conectada

Não respondeu corretamente após um período de tempo ou

a conexão estabelecida falhou porque o host conectado tem

Falha ao responder \[2001:4898: E8: f39e: 5c9a: ad83:81b3:9944\]: 5061

Exceção interna: falha na tentativa de conexão porque o

a parte conectada não respondeu corretamente após um período de

falha na hora ou estabelecida a conexão porque o host conectado

Não respondeu

\[2001:4898: E8: f39e: 5c9a: ad83:81b3:9944\]: 5061

Correto

Por exemplo, a saída anterior inclui a anotação "a parte conectada não respondeu corretamente" que geralmente indica um problema com o servidor de borda.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais **Test-CsAudioConferencingProvider** pode falhar:

  - Um valor de parâmetro incorreto foi fornecido. Conforme mostrado no exemplo anterior, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará. Execute o comando novamente sem os parâmetros opcionais e veja se isso é bem-sucedido.

  - Observe que o teste falhará se o usuário empregado pelo cmdlet **Test-CsAudioConferencingProvider** não tiver sido atribuído um provedor de audioconferência.

  - Esse comando falhará se o servidor de borda estiver configurado incorretamente ou ainda não foi implantado.

</div>

</div>

<span> </span>

</div>

</div>

</div>

