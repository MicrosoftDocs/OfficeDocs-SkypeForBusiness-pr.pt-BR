---
title: 'Lync Server 2013: testar acesso anônimo ao aplicativo Web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test anonymous Web App access
ms:assetid: 92f691cd-e05e-4bab-beb5-251d4b837a19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767949(v=OCS.15)
ms:contentKeyID: 63969630
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a3d90d3de8624f9965b04990ad996d9c04a954f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519308"
---
# <a name="test-anonymous-web-app-access-in-lync-server-2013"></a>Testar o acesso ao aplicativo Web anônimo no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsWebAppAnonymous. Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebAppAnonymous&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet Test-CsWebAppAnonymous verifica se um usuário anônimo pode ingressar em conferências do Lync Server usando o Lync Web App. Quando você executa o cmdlet, Test-CsWebAppAnonymous contata o serviço de tíquete da Web para obter uma permissão da Web para o usuário anônimo. Se o cmdlet for bem-sucedido para obter esse tíquete, Test-CsWebAppAnonymous entrará em contato com o Lync Server e tentará estabelecer conferências separadas para mensagens instantâneas, compartilhamento de aplicativos e colaboração de dados.

Observe que Test-CsWebAppAnonymous verifica apenas as APIs e conexões usadas para criar essas conferências. Na verdade, o cmdlet não cria e conduz qualquer conferência.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O cmdlet Test-CsWebAppAnonymous pode ser executado usando um par de contas de teste pré-configuradas ou as contas de dois usuários que estão habilitados para o Lync Server. Para executar esta verificação usando contas de teste, basta especificar o nome de domínio totalmente qualificado do pool do Lync Server que está sendo testado. Por exemplo:

    Test-CsWebAppAnonymous -TargetFqdn atl-cs-001.litwareinc.com

Para executar essa verificação usando contas de usuário reais, você deve criar dois objetos de credenciais do Shell de gerenciamento do Lync Server (objetos que contêm o nome da conta e a senha) para cada conta. Em seguida, você deve incluir esses objetos de credenciais e os endereços SIP das duas contas ao chamar Test-CsWebAppAnonymous:

    $cred1 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1

Para obter mais informações, consulte o tópico de ajuda para o cmdlet Test-CsWebAppAnonymous. Observe que Test-CsWebAppAnonymous é preterida para uso no Lync Server 2013.

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

Se Test-CsWebAppAnonymous puder ingressar o usuário anônimo em suas conferências, o cmdlet retornará o resultado de teste bem-sucedido:

FQDN de destino:

Resultado: êxito

Latência: 00:00:00

Mensagem de erro:

Diagnóstico

Se o usuário anônimo não puder participar das conferências necessárias, o resultado do teste será marcado como falha. Normalmente Test-CsWebAppAnonymous também relatará uma mensagem de erro detalhada e o diagnóstico:

FQDN de destino: atl-cs-001.litwareinc.com

Resultado: falha

Latência: 00:00:05.9746266

Mensagem de erro: nenhuma resposta recebida para o serviço de Web-Ticket

Diagnóstico: a solicitação HTTP não é autorizada com o cliente

esquema de autenticação ' NTLM '. A autenticação

o cabeçalho recebido do servidor era ' Negotiate, NTLM '.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

As falhas de Test-CsWebAppAnonymous geralmente giram em torno de erros de autenticação do usuário: você deve executar o teste usando uma conta de usuário válida, mesmo que o cmdlet esteja verificando a capacidade de um usuário anônimo se conectar ao Lync Server. Se Test-CsWebAppAnonymous falhar, verifique se o usuário especificado tem uma conta de usuário do Lync Server válida. Você pode recuperar informações da conta do Lync Server usando um comando semelhante a este:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Se a propriedade Enabled não for igual a true ou se o comando falhar, isso significa que o usuário não tem uma conta válida do Lync Server.

Você também deve verificar se a senha que você forneceu ao executar o cmdlet é uma senha válida.

Problemas de configuração com o servidor do Office Web Apps também podem causar falhas no Test-CsWebAppAnonymous; Isso geralmente será o caso se você receber o seguinte diagnóstico:

A solicitação HTTP não é autorizada com o esquema de autenticação de cliente ' NTLM '. O cabeçalho de autenticação recebido do servidor era ' Negotiate, NTLM '.

Para obter mais informações sobre como diagnosticar e resolver problemas do servidor do Office Web Apps, consulte o blog post [Office Web Apps server 2013-as máquinas são sempre relatadas como não íntegras](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy).

</div>

</div>

<span> </span>

</div>

</div>

</div>

