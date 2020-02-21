---
title: 'Lync Server 2013: testar o compartilhamento em conferências'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing sharing in conferences
ms:assetid: e6021d70-6ed9-414d-954c-06eef397dc1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727314(v=OCS.15)
ms:contentKeyID: 63969660
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b46fba4c9426a76bfb7c8ca9f15e7cba4950e8f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193884"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-sharing-in-conferences-in-lync-server-2013"></a>Testando o compartilhamento em conferências no Lync Server 2013

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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsDataConference</strong> . Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDataConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

No Lync Server 2013, uma conferência de dados é qualquer conferência onde atividades colaborativas, como quadro de comunicações ou anotações, são usadas. O cmdlet **Test-CsDataConference** permite verificar se um par de usuários pode participar de uma conferência de dados.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O comando mostrado no Exemplo 1 verifica se uma conferência de dados pode ser conduzida no pool atl-cs-001.litwareinc.com. Este comando assume que você configurou um par de usuários de teste para o pool especificado. Se nenhum usuário de teste existir, o comando falhará.

    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" 

Os comandos mostrados no exemplo 2 testam a capacidade de um par de usuários\\(litwareinc pilar\\e litwareinc kenmyer) para fazer logon no Lync Server 2013 e, em seguida, conduzir uma conferência de dados. Para fazer isso, o primeiro comando no exemplo usa o cmdlet **Get-Credential** para criar um objeto de credencial da interface de linha de comando do Windows PowerShell contendo o nome e a senha do usuário pilar Ackerman. (Como o nome de logon,\\litwareinc pilar, foi incluído como um parâmetro, a caixa de diálogo de solicitação de credencial do Windows PowerShell só exige que o administrador insira a senha da conta pilar Ackerman.) O objeto Credential resultante é armazenado em uma variável chamada $cred 1. O segundo comando fará o mesmo, retornando, desta vez, um objeto de credencial para a conta de Ken Myer.

Com os objetos de credencial em mãos, o terceiro comando determina se esses dois usuários podem ou não fazer logon no Lync Server 2013 e realizar uma conferência de dados. Para realizar essa tarefa, o cmdlet **Test-CsDataConference** é chamado, junto com os seguintes parâmetros: TargetFqdn (o FQDN do pool de registrador); SenderSipAddress (o endereço SIP para o primeiro usuário de teste); SenderCredential (o objeto Windows PowerShell contendo as credenciais desse mesmo usuário); ReceiverSipAddress (o endereço SIP para o outro usuário de teste); e ReceiverCredential (o objeto Windows PowerShell que contém as credenciais para o outro usuário de teste).

    $credential1 = Get-Credential "litwareinc\pilar" 
    $credential2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

Se a conferência de dados estiver configurada corretamente, você receberá uma saída semelhante a esta, com a propriedade Result marcada como **Success:**

FQDN de destino: atl-cs-001.litwareinc.com

Resultado: êxito

Latência: 00:00:00

Mensagem de erro:

Diagnóstico

Se os usuários especificados não puderem usar o compartilhamento de dados, o resultado será mostrado como **falha**e informações adicionais serão registradas nas propriedades de erro e diagnóstico:

FQDN de destino: atl-cs-001.litwareinc.com

Resultado: falha

Latência: 00:00:00

Mensagem de erro: 10060, uma tentativa de conexão falhou porque a parte conectada

Não respondeu corretamente após um período de tempo ou

a conexão estabelecida falhou porque o host conectado tem

Falha ao responder \[2001:4898: E8: f39e: 5c9a\]: ad83:81b3:9944:5061

Exceção interna: falha na tentativa de conexão porque o

a parte conectada não respondeu corretamente após um período de

a hora ou a conexão estabelecida falhou porque o host conectado

falhou ao responder

\[2001:4898: E8: f39e: 5c9a\]: ad83:81b3:5061

Diagnóstico

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais **Test-CsDataConference** pode falhar:

  - Um valor de parâmetro incorreto foi fornecido. Se usado, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará. Execute novamente o comando sem os parâmetros opcionais e veja se isso é bem-sucedido.

  - A capacidade de realizar uma conferência de dados depende da política de conferência que foi atribuída ao usuário que organizou a conferência (no caso do cmdlet **Test-CsDataConference** , que é o "remetente"). Se o organizador não tiver permissão para incluir atividades colaborativas em sua reunião (por exemplo, se a política de conferência tiver a propriedade EnableDataCollaboration definida como false), o cmdlet **Test-CsDataConference** falhará.

  - Esse comando falhará se o servidor de borda estiver configurado incorretamente ou ainda não tiver sido implantado.

</div>

</div>

<span> </span>

</div>

</div>

</div>

