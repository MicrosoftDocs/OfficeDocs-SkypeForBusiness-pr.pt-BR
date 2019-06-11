---
title: 'Lync Server 2013: testando chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing persistent chat
ms:assetid: d351b6f2-bc31-42e0-9e8d-c347713d6b4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727313(v=OCS.15)
ms:contentKeyID: 63969651
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4f805984382388fd44904db746d818decb8871a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844624"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-persistent-chat-in-lync-server-2013"></a>Testando o chat persistente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-11-03_


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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsPersistentChatMessage</strong> . Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPersistentChatMessage&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet **Test-CsPersistentChatMessage** verifica se um par de usuários de teste podem trocar mensagens usando o serviço de chat persistente. Para fazer isso, o cmdlet registra os dois usuários no Lync Server 2013, conecta os usuários a uma sala de chat persistente, troca um par de mensagens e, em seguida, sai da sala de chat e desconecta os dois usuários. Observe que as chamadas para esse cmdlet falharão se você não tiver criado nenhuma sala de chat ou se as duas contas de usuário de teste não forem atribuídas a uma política de chat persistente que lhes conceda acesso ao serviço de chat persistente.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

Os comandos mostrados no exemplo a seguir testam a capacidade de um par de usuários\\(litwareinc pilar\\e litwareinc kenmyer) para fazer logon no Lync Server 2013 e, em seguida, trocar mensagens usando o serviço de chat persistente. Para fazer isso, o primeiro comando do exemplo usa o cmdlet **Get-Credential** para criar um objeto de credencial da interface de linha de comando do Windows PowerShell que contém o nome e a senha do pilar do usuário Alverca. (Como o nome de logon,\\litwareinc pilar, foi incluído como um parâmetro, a caixa de diálogo solicitação de credenciais do Windows PowerShell exige que o administrador insira a senha para a conta pilar Alverca.) O objeto de credenciais resultante é armazenado em uma variável chamada $cred 1. O segundo comando faz a mesma coisa, desta vez retornando um objeto Credential para a conta Ken Myer.

Com os objetos de credenciais em mãos, o terceiro comando determina se esses dois usuários podem fazer logon no Lync Server 2013 e trocar mensagens usando o chat persistente. Para executar essa tarefa, o cmdlet **Test-CsPersistentChatMessage** é chamado usando os seguintes parâmetros: TargetFqdn (o FQDN do pool de registrador); SenderSipAddress (o endereço SIP para o primeiro usuário de teste); SenderCredential (o objeto do Windows PowerShell que contém as credenciais para esse mesmo usuário); ReceiverSipAddress (o endereço SIP para o outro usuário de teste); e ReceiverCredential (o objeto do Windows PowerShell que contém as credenciais do outro usuário de teste).

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-persistentchat-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinação do sucesso ou falha

Se o usuário especificado tiver uma política de local válida, você receberá uma saída semelhante a essa, com a propriedade Result marcada como **Success**:

FQDN de destino: atl-cs-001.litwareinc.com

Resultado: êxito

Latência: 00:00:00

Mensagem de erro:

Correto

Se os usuários especificados não puderem trocar mensagens usando o serviço de chat persistente, o resultado será mostrado como uma **falha**, e informações adicionais serão gravadas nas propriedades erro e diagnóstico:

Aviso: falha ao ler o número da porta do registrador para o número da porta de dados totalmente qualificado

FQDN (nome de domínio). Usando o número da porta do registrador padrão. Extremamente

System. InvalidOperationException: nenhum cluster correspondente localizado na topologia.

como

Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

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

Aqui estão alguns motivos comuns pelos quais **Test-CsPersistentChatMessage** pode falhar:

  - Um valor de parâmetro incorreto foi fornecido. As contas de teste necessárias podem não existir ou terem sido criadas corretamente.

  - Pode ser que houve um problema de rede causando um atraso inesperado que esgotou o teste.

</div>

<div>

## <a name="see-also"></a>Confira também


[Grant-CsPersistentChatPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsPersistentChatPolicy)  
[New-CsPersistentChatPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsPersistentChatPolicy)  
[Set-CsPersistentChatPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

