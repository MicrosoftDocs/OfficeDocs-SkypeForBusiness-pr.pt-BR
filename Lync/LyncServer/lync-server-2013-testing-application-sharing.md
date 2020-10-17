---
title: 'Lync Server 2013: testar compartilhamento de aplicativos'
description: 'Lync Server 2013: testar o compartilhamento de aplicativos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing application sharing
ms:assetid: 8d21db9b-10d1-4b43-b057-0deb1df1c205
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727310(v=OCS.15)
ms:contentKeyID: 63969629
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f857908e374239b4054985b88951cd12720ed418
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560717"
---
# <a name="testing-application-sharing-in-lync-server-2013"></a>Testando o compartilhamento de aplicativos no Lync Server 2013

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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsASConference. Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsASConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet **Test-CsASConference** verifica se um par de usuários de teste pode participar de uma conferência online que inclui o compartilhamento de aplicativos. Para fazer isso, o cmdlet registra os dois usuários com o Lync Server 2013 e, em seguida, usa uma das contas de usuário para criar uma nova conferência que inclui o compartilhamento de aplicativos. O cmdlet verifica que o segundo usuário é capaz de ingressar na conferência.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O comando mostrado no Exemplo 1 verifica se uma conferência de Compartilhamento de Aplicativos pode ser conduzida no pool atl-cs-001.litwareinc.com. Este comando assume que você configurou um par de usuários de testes para o pool especificado. Se nenhum usuário de teste existir, o comando falhará.

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com"

O Exemplo 2 testa a capacidade do serviço Join Launcher participar de uma conferência de Compartilhamento de Aplicativos no pool atl-cs-001.litwareinc.com. Observe que este comando testa apenas o próprio serviço. Você não precisa de qualquer dispositivo móvel para executar o comando.

    Test-CsASConference -TargetFqdn "atl-cs-001.litwareinc.com" -TestJoinLauncher 

Os comandos mostrados no exemplo 2 testam a capacidade de um par de usuários (litwareinc \\ pilar e litwareinc \\ kenmyer) para fazer logon no Lync Server 2013 e, em seguida, conduzir uma conferência de compartilhamento de aplicativo. Para fazer isso, o primeiro comando no exemplo usa o cmdlet Get-Credential para criar um objeto de credencial da interface de linha de comando do Windows PowerShell contendo o nome e a senha do usuário pilar Ackerman. (Como o nome de logon, litwareinc \\ pilar, foi incluído como um parâmetro, a caixa de diálogo de solicitação de credencial do Windows PowerShell só exige que o administrador insira a senha da conta pilar Ackerman.) O objeto Credential resultante é armazenado em uma variável chamada $cred 1. O segundo comando fará o mesmo, retornando, desta vez, um objeto de credencial para a conta de Ken Myer.

Com os objetos de credencial em mãos, o terceiro comando determina se esses dois usuários podem ou não fazer logon no Lync Server 2013 e realizar uma conferência de compartilhamento de aplicativo. Para realizar essa tarefa, o cmdlet **Test-CsASConference** é chamado, junto com os seguintes parâmetros: TargetFqdn (o FQDN do pool de registrador); SenderSipAddress (o endereço SIP para o primeiro usuário de teste); SenderCredential (o objeto Windows PowerShell contendo as credenciais desse mesmo usuário); ReceiverSipAddress (o endereço SIP para o outro usuário de teste); e ReceiverCredential (o objeto Windows PowerShell que contém as credenciais para o outro usuário de teste).

    $cred1 = Get-Credential "litwareinc\pilar" 
    $cred2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsASConference -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

Se o compartilhamento de aplicativos estiver configurado corretamente, você receberá uma saída semelhante a esta, com a propriedade Result marcada como **Success:**

FQDN de destino: atl-cs-001.litwareinc.com

Resultado: êxito

Latência: 00:00:01

Mensagem de erro:

Diagnóstico

Se os usuários especificados não puderem compartilhar aplicativos, o resultado será mostrado como falha, e informações adicionais serão registradas nas propriedades de erro e diagnóstico:

FQDN de destino: atl-cs-001.litwareinc.com

Resultado: falha

Latência: 00:00:00

Mensagem de erro: 10060, uma tentativa de conexão falhou porque a parte conectada

Não respondeu corretamente após um período de tempo ou

a conexão estabelecida falhou porque o host conectado tem

Falha ao responder 10.188.116.96:5061

Exceção interna: falha na tentativa de conexão porque o

a parte conectada não respondeu corretamente após um período de

a hora ou a conexão estabelecida falhou porque o host conectado

Falha ao responder 10.188.116.96:5061

Diagnóstico

Por exemplo, a saída anterior inclui a anotação "a parte conectada não respondeu corretamente" que geralmente indica um problema com o servidor de borda.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais **Test-CsASConference** pode falhar:

  - Um valor de parâmetro incorreto foi fornecido. Se usado, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará. Execute novamente o comando sem os parâmetros opcionais e veja se isso é bem-sucedido.

  - Esse comando falhará se os usuários de teste tiverem uma política de conferência atribuída que os impede de usar o compartilhamento de aplicativos.

  - Esse comando falhará se o servidor de borda estiver configurado incorretamente ou ainda não tiver sido implantado.

</div>

<div>

## <a name="see-also"></a>Confira também


[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy)  
[Test-CsDataConference](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

