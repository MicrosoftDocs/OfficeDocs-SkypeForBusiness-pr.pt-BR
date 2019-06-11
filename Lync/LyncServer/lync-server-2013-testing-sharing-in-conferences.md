---
title: 'Lync Server 2013: testando o compartilhamento em conferências'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing sharing in conferences
ms:assetid: e6021d70-6ed9-414d-954c-06eef397dc1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727314(v=OCS.15)
ms:contentKeyID: 63969660
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce4cd1a45d1eddf8875d85ff28886b0c04c29cfe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844615"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-sharing-in-conferences-in-lync-server-2013"></a>Testando o compartilhamento em conferências no Lync Server 2013

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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsDataConference</strong> . Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDataConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

No Lync Server 2013, uma conferência de dados é qualquer conferência na qual atividades colaborativas, como quadros de comunicações ou anotações, são usadas. O cmdlet **Test-CsDataConference** permite que você verifique se um par de usuários consegue participar de uma conferência de dados.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O comando mostrado no exemplo 1 verifica se uma conferência de dados pode ser conduzida na atl-cs-001.litwareinc.com do pool. Esse comando pressupõe que você configurou um par de usuários de teste para o pool especificado. Se não houver esses usuários de teste, o comando falhará.

    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" 

Os comandos mostrados no exemplo 2 testam a capacidade de um par de usuários\\(litwareinc pilar\\e litwareinc kenmyer) para fazer logon no Lync Server 2013 e conduzir uma conferência de dados. Para fazer isso, o primeiro comando do exemplo usa o cmdlet **Get-Credential** para criar um objeto de credencial da interface de linha de comando do Windows PowerShell contendo o nome e a senha do pilar do usuário Alverca. (Como o nome de logon,\\litwareinc pilar, foi incluído como um parâmetro, a caixa de diálogo solicitação de credenciais do Windows PowerShell exige apenas que o administrador insira a senha da conta pilar Alverca.) O objeto Credential resultante é armazenado em uma variável chamada $cred 1. O segundo comando faz a mesma coisa, desta vez retornando um objeto Credential para a conta Ken Myer.

Com os objetos de credenciais em mãos, o terceiro comando determina se esses dois usuários podem ou não fazer logon no Lync Server 2013 e conduzir uma conferência de dados. Para executar essa tarefa, o cmdlet **Test-CsDataConference** é chamado, juntamente com os seguintes parâmetros: TargetFqdn (o FQDN do pool de registrador); SenderSipAddress (o endereço SIP para o primeiro usuário de teste); SenderCredential (o objeto do Windows PowerShell que contém as credenciais para esse mesmo usuário); ReceiverSipAddress (o endereço SIP para o outro usuário de teste); e ReceiverCredential (o objeto do Windows PowerShell que contém as credenciais do outro usuário de teste).

    $credential1 = Get-Credential "litwareinc\pilar" 
    $credential2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinação do sucesso ou falha

Se a conferência de dados estiver configurada corretamente, você receberá uma saída semelhante a essa, com a propriedade Result marcada como **Success:**

FQDN de destino: atl-cs-001.litwareinc.com

Resultado: êxito

Latência: 00:00:00

Mensagem de erro:

Correto

Se os usuários especificados não conseguirem usar o compartilhamento de dados, o resultado será mostrado como uma **falha**, e informações adicionais serão gravadas nas propriedades de erro e diagnóstico:

FQDN de destino: atl-cs-001.litwareinc.com

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

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais **Test-CsDataConference** pode falhar:

  - Um valor de parâmetro incorreto foi fornecido. Se usado, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará. Execute o comando novamente sem os parâmetros opcionais e veja se isso é bem-sucedido.

  - A capacidade de conduzir uma conferência de dados depende da política de conferência que foi atribuída ao usuário que organizou a conferência (no caso do cmdlet **Test-CsDataConference** , que é o "remetente"). Se o organizador não puder incluir atividades colaborativas em sua reunião (por exemplo, se a política de conferência tiver a propriedade EnableDataCollaboration definida como false), o cmdlet **Test-CsDataConference** falhará.

  - Esse comando falhará se o servidor de borda estiver configurado incorretamente ou ainda não foi implantado.

</div>

</div>

<span> </span>

</div>

</div>

</div>

