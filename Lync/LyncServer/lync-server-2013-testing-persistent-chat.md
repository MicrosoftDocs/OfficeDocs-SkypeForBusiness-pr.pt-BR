---
title: 'Lync Server 2013: testar chat persistente'
description: 'Lync Server 2013: testar chat persistente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing persistent chat
ms:assetid: d351b6f2-bc31-42e0-9e8d-c347713d6b4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727313(v=OCS.15)
ms:contentKeyID: 63969651
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8b1dc4eef1870f1287dacdc1852ab1e24edd169
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556277"
---
# <a name="testing-persistent-chat-in-lync-server-2013"></a>Testando o chat persistente no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-11-03_


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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsPersistentChatMessage</strong> . Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPersistentChatMessage&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet **Test-CsPersistentChatMessage** verifica se um par de usuários de teste podem trocar mensagens usando o serviço de chat persistente. Para fazer isso, o cmdlet registra os dois usuários no Lync Server 2013, conecta os usuários a uma sala de chat persistente, troca um par de mensagens e, em seguida, sai da sala de chat e faz logoff dos dois usuários. Observe que as chamadas para este cmdlet falharão se você não tiver criado nenhuma sala de chat ou se as duas contas de usuário de teste não forem atribuídas a uma política de chat persistente que forneça acesso ao serviço de chat persistente.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

Os comandos mostrados no exemplo a seguir testam a capacidade de um par de usuários (litwareinc \\ pilar e litwareinc \\ kenmyer) para fazer logon no Lync Server 2013 e, em seguida, trocar mensagens usando o serviço de chat persistente. Para fazer isso, o primeiro comando no exemplo usa o cmdlet **Get-Credential** para criar um objeto de credencial da interface de linha de comando do Windows PowerShell que contenha o nome e a senha do usuário pilar Ackerman. (Como o nome de logon, litwareinc \\ pilar, foi incluído como um parâmetro, a caixa de diálogo de solicitação de credencial do Windows PowerShell só exige que o administrador insira a senha da conta pilar Ackerman.) O objeto de credenciais resultante é armazenado em uma variável chamada $cred 1. O segundo comando fará o mesmo, retornando, desta vez, um objeto de credencial para a conta de Ken Myer.

Com os objetos de credencial em mãos, o terceiro comando determina se esses dois usuários podem fazer logon no Lync Server 2013 e trocar mensagens usando o chat persistente. Para realizar essa tarefa, o cmdlet **Test-CsPersistentChatMessage** é chamado usando os seguintes parâmetros: TargetFqdn (o FQDN do pool de registrador); SenderSipAddress (o endereço SIP para o primeiro usuário de teste); SenderCredential (o objeto Windows PowerShell que contém as credenciais desse mesmo usuário); ReceiverSipAddress (o endereço SIP para o outro usuário de teste); e ReceiverCredential (o objeto Windows PowerShell que contém as credenciais para o outro usuário de teste).

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-persistentchat-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

Se o usuário especificado tiver uma política de local válida, você receberá uma saída semelhante a esta, com a propriedade Result marcada como **Success**:

FQDN de destino: atl-cs-001.litwareinc.com

Resultado: êxito

Latência: 00:00:00

Mensagem de erro:

Diagnóstico

Se os usuários especificados não puderem trocar mensagens usando o serviço de chat persistente, o resultado será mostrado como **falha**e informações adicionais serão registradas nas propriedades de erro e diagnóstico:

Aviso: falha ao ler o número da porta do registrador para o fornecido totalmente qualificado

FQDN (nome de domínio). Usando o número da porta do registrador padrão. Exceções

System. InvalidOperationException: nenhum cluster correspondente encontrado na topologia.

por

Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

FQDN de destino: atl-cs-001.litwareinc.com

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

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais **Test-CsPersistentChatMessage** pode falhar:

  - Um valor de parâmetro incorreto foi fornecido. As contas de teste necessárias podem não existir ou terem sido criadas corretamente.

  - Pode ter havido um problema de rede causando um atraso inesperado que esgotou o tempo de teste.

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

