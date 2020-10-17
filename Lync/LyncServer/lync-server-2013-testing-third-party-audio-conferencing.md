---
title: 'Lync Server 2013: testar audioconferência de áudio de terceiros'
description: 'Lync Server 2013: testar conferências de áudio de terceiros.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing third-party audio conferencing
ms:assetid: 0428eb2f-a5ce-47e5-9ea4-383965dfc1e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727299(v=OCS.15)
ms:contentKeyID: 63969576
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f009d95834768d8a4e6619a79ff1f3be0a2b92bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556097"
---
# <a name="testing-third-party-audio-conferencing-in-lync-server-2013"></a>Testando a conferência de áudio de terceiros no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-11-01_


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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsAudioConferencingProvider. Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAudioConferencingProvider&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

Um provedor de conferência de áudio é uma empresa terceirizada que oferece serviços de conferências para a organização. Entre outras coisas, os provedores de conferência de áudio permitem os usuários fora do local e não conectados à rede empresarial ou Internet participarem da parte de áudio de uma conferência ou reunião. Os provedores de conferência de áudio frequentemente oferecem serviços de alta tecnologia como conversão ao vivo, transcrição e assistência ao operador por conferência.

O cmdlet **Test-CsAudioConferencingProvider** é usado para verificar se um usuário é capaz de fazer uma conexão com seu provedor de conferência de áudio. Observe que este cmdlet pode ser executado em uma das duas formas. Vários administradores usarão os cmdlets CsHealthMonitoringConfiguration para configurar usuários de teste para cada um de seus pools do Registrador. Estes usuários de teste representam um par de contas de usuário pré-configurados para uso com transações sintéticas. (Normalmente, são contas de teste e não contas que pertencem a usuários reais.) Se os usuários de teste estiverem configurados para um pool, os administradores poderão executar o cmdlet **Test-CsAudioConferencingProvider** nesse pool, sem ter que especificar a identidade (e fornecer as credenciais) da conta de usuário envolvida no teste.

Como alternativa, os administradores podem executar o cmdlet **Test-CsAudioConferencingProvider** usando uma conta de usuário real. Se você optar por conduzir um teste usando uma conta de usuário real, será necessário fornecer o nome de logon e a senha dessa conta.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O Exemplo 1 verifica se um usuário de teste definido para o pool atl-cs-001.litwareinc.com pode se conectar ao provedor de conferência de áudio. Este comando exige que pelo menos um usuário de teste seja definido para o pool. Se nenhum usuário de teste tiver sido definido para o atl-cs-001.litwareinc.com, o comando irá falhar; Isso ocorre porque o cmdlet **Test-CsAudioConferencingProvider** não sabe qual usuário empregar no teste. Se você não definiu os usuários de teste para um pool, deve incluir o parâmetro UserSipAddress e as credenciais da conta de usuário que o comando deve implantar ao verificar a conexão com um provedor de conferência de áudio.

    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com 

Os comandos mostrados no exemplo 2 testam a capacidade de um usuário específico (litwareinc \\ kenmyer) para se conectar ao seu provedor de conferência de áudio. Para fazer isso, o primeiro comando no exemplo usa o cmdlet Get-Credential para criar um objeto de credenciais da interface de linha de comando do Windows PowerShell contendo o nome e a senha do usuário Ken Myer. (Como o nome de logon litwareinc \\ kenmyer foi incluído como um parâmetro, a caixa de diálogo de solicitação de credencial do Windows PowerShell só exige que o administrador insira a senha da conta Ken Myer.) O objeto de credenciais resultante é armazenado em uma variável chamada $credential.

O segundo comando verifica se este usuário pode se conectar ao provedor de conferência de áudio. Para realizar essa tarefa, o cmdlet Test-CsAudioConferencingProvider é chamado, juntamente com três parâmetros: TargetFqdn (o FQDN do pool de registradores); Usercredential (o objeto Windows PowerShell que contém as credenciais de usuário de Ken Myer); e UserSipAddress (o endereço SIP correspondente às credenciais de usuário fornecidas).

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

Se o provedor de serviços de audioconferência estiver configurado corretamente, você receberá uma saída semelhante a esta, com a propriedade Result marcada como **êxito:**

FQDN de destino: atl-sql-001.litwareinc.com

Resultado: êxito

Latência: 00:00:00

Mensagem de erro:

Diagnóstico

Se o usuário especificado não puder fazer logon ou logoff, o resultado será mostrado como uma **falha**, e informações adicionais serão registradas nas propriedades de erro e diagnóstico:

FQDN de destino: atl-sql-001.litwareinc.com

Resultado: falha

Latência: 00:00:00

Mensagem de erro: 10060, uma tentativa de conexão falhou porque a parte conectada

Não respondeu corretamente após um período de tempo ou

a conexão estabelecida falhou porque o host conectado tem

Falha ao responder \[ 2001:4898: E8: f39e: 5c9a: ad83:81b3:9944: \] 5061

Exceção interna: falha na tentativa de conexão porque o

a parte conectada não respondeu corretamente após um período de

a hora ou a conexão estabelecida falhou porque o host conectado

falhou ao responder

\[2001:4898: E8: f39e: 5c9a: ad83:81b3: \] 5061

Diagnóstico

Por exemplo, a saída anterior inclui a anotação "a parte conectada não respondeu corretamente" que geralmente indica um problema com o servidor de borda.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais **Test-CsAudioConferencingProvider** pode falhar:

  - Um valor de parâmetro incorreto foi fornecido. Conforme mostrado no exemplo anterior, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará. Execute novamente o comando sem os parâmetros opcionais e veja se isso é bem-sucedido.

  - Observe que o teste falhará se o usuário empregado pelo cmdlet **Test-CsAudioConferencingProvider** não tiver sido atribuído um provedor de conferência de áudio.

  - Esse comando falhará se o servidor de borda estiver configurado incorretamente ou ainda não tiver sido implantado.

</div>

</div>

<span> </span>

</div>

</div>

</div>

