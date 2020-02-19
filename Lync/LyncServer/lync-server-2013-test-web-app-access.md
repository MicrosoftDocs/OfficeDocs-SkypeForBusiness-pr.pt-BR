---
title: 'Lync Server 2013: testar o acesso ao aplicativo Web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test Web App access
ms:assetid: 17d67ea3-f74d-4952-ac2b-92c0dacc8014
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767944(v=OCS.15)
ms:contentKeyID: 63969584
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d116adc6b3ece7faf1d6e85b2848b35bdf522f0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-web-app-access-in-lync-server-2013"></a>Testar o acesso do aplicativo Web no Lync Server 2013

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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsWebApp. Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebApp&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet Test-CsWebApp verifica se os usuários autenticados podem participar de conferências do Lync Server usando o Lync Web App. Quando você executa o cmdlet, Test-CsWebApp contata o serviço de tíquete da Web para obter tíquetes da Web para os usuários especificados. Essas permissões agem efetivamente como "tíquetes de admissão" para a conferência do Lync Server. Se as permissões puderem ser recuperadas e se os usuários puderem ser autenticados, o Test-CsWebApp entrará em contato com o Lync Server e tentará estabelecer conferências separadas para mensagens instantâneas, compartilhamento de aplicativos e colaboração de dados.

Observe que Test-CsWebApp apenas verifica as APIs e conexões usadas para criar essas conferências. O cmdlet é projetado para verificar se o Lync Web App pode ser usado para criar e participar de conferências. No entanto, ele não cria e conduz uma conferência.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O cmdlet Test-CsWebApp pode ser executado usando um par de contas de teste pré-configuradas ou as contas de dois usuários que estão habilitados para o Lync Server. Para executar esta verificação usando contas de teste, basta especificar o nome de domínio totalmente qualificado do pool do Lync Server que está sendo testado. Por exemplo:

    Test-CsWebApp -TargetFqdn "atl-cs-001.litwareinc.com"

Para executar essa verificação usando contas de usuário reais, você deve criar dois objetos de credenciais do Windows PowerShell (objetos que contêm o nome da conta e a senha) para cada conta. Em seguida, você deve incluir esses objetos de credenciais e os endereços SIP das duas contas ao chamar Test-CsWebApp:

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1 -User2SipAddress "sip:pilar@litwareinc.com" -User2Credential $cred2

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Test-CsWebApp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) . Observe que Test-CsWebApp foi preterido para uso no Lync Server 2013.

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

Se Test-CsWebApp puder participar dos usuários em suas conferências, o cmdlet retornará o resultado de teste Success:

FQDN de destino:

Resultado: êxito

Latência: 00:00:00

Mensagem de erro:

Diagnóstico

Se os usuários não puderem participar das conferências necessárias, o resultado do teste será marcado como falha. Normalmente, Test-CsWebApp também reportará uma mensagem de erro detalhada e o diagnóstico:

FQDN de destino: atl-cs-001.litwareinc.com

Resultado: falha

Latência: 00:00:00

Mensagem de erro: nenhuma resposta recebida para o serviço de tíquete da Web

Diagnóstico: a solicitação HTTP não é autorizada com o cliente

esquema de autenticação ' NTLM '. A autenticação

o cabeçalho recebido do servidor era ' Negotiate, NTLM '.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Falhas de CsWebApp de teste normalmente envolvem erros de autenticação do usuário. Se Test-CsWebApp falhar, você deve primeiro verificar se os usuários especificados têm contas de usuário válidas e estão habilitados para o Lync Server. Você pode recuperar informações da conta usando um comando semelhante ao seguinte:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Se a propriedade Enabled não for igual a true ou se o comando falhar, isso significa que o usuário não tem uma conta válida do Lync Server. Você também deve verificar se as senhas que você forneceu ao cmdlet são válidas.

</div>

</div>

<span> </span>

</div>

</div>

</div>

