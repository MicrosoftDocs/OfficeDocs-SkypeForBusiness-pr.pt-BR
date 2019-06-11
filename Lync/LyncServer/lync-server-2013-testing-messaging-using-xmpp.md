---
title: 'Lync Server 2013: testando mensagens usando o XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing messaging using XMPP
ms:assetid: ae5305ba-e5fc-4ca0-a805-872b4ebaf981
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727312(v=OCS.15)
ms:contentKeyID: 63969641
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: acd03cdf2a5215c980b788dbaffafc5936fe5b5e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844633"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-messaging-using-xmpp-in-lync-server-2013"></a>Testando mensagens usando o XMPP no Lync Server 2013

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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsXmppIM</strong> . Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsXmppIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O protocolo de comunicação e mensagens extensíveis (XMPP) é um protocolo de comunicação padrão (baseado em XML) usado para enviar mensagens pela Internet. O XMPP foi nomeado originalmente como Jabber e é compatível com diversos aplicativos de comunicação e mensagens pela Internet, como Google Talk e chat do Facebook. O cmdlet **Test-CsXmppIM** verifica se um usuário pode trocar mensagens de chat com um usuário em uma rede do XMPP. Observe que, para esse teste ter êxito, você deve ter um endereço SIP válido para o usuário do XMPP e esse endereço SIP deve estar em uma rede que foi configurada como um parceiro de XMPP permitido.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O exemplo a seguir verifica os recursos de mensagem instantânea do XMPP para o pool atl-cs-001.litwareinc.com. Esse comando funcionará apenas se os usuários de teste estiverem definidos para o pool atl-cs-001.litwareinc.com. Se eles tiverem, o comando determinará se o primeiro usuário de teste pode enviar uma mensagem de chat do XMPP para um usuário que tenha o endereço SIP adelaney@contoso.com.

Se os usuários de teste não estiverem definidos, o comando falhará porque não saberá qual usuário deve fazer logon. Se você não definiu usuários de teste para um pool, deve incluir o parâmetro UserSipAddress e as credenciais do usuário que o comando deve usar ao tentar fazer logon.

    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com"

Os comandos mostrados no próximo exemplo testam a capacidade de um usuário específico (\\litwareinc pilar) para fazer logon para enviar uma mensagem de chat do XMPP para o adelaney@contoso.com do usuário. Para fazer isso, o primeiro comando do exemplo usa o cmdlet Get-Credential para criar um objeto de credencial da interface de linha de comando do Windows PowerShell que contém o nome e a senha do pilar do usuário Alverca. (Como o nome de logon\\litwareinc pilar foi incluído como um parâmetro, a caixa de diálogo solicitação de credenciais do Windows PowerShell exige que o administrador insira a senha para a conta pilar Alverca.) O objeto Credential resultante é armazenado em uma variável chamada $cred 1.

Em seguida, o segundo comando verifica se esse usuário pode fazer logon no pool atl-cs-001.litwareinc.com e envia a mensagem de chat do XMPP. Para executar essa tarefa, o cmdlet **Test-CsXmppIm** é chamado, juntamente com quatro parâmetros: TargetFqdn (o FQDN do pool de registrador); Destinatário (o endereço SIP do usuário ao qual a mensagem está sendo endereçada); Usercredential (o objeto do Windows PowerShell que contém as credenciais de usuário de pilar Alverca); e UserSipAddress (o endereço SIP correspondente às credenciais de usuário fornecidas).

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinação do sucesso ou falha

Se XMPP mensagem instantânea estiver configurada corretamente, você receberá uma saída semelhante a essa, com a propriedade Result marcada como **Success:**

FQDN de destino: atl-cs-001.litwareinc.com

Resultado: êxito

Latência: 00:00:02.5361946

Mensagem de erro:

Correto

Se os usuários especificados não puderem usar mensagens instantâneas do XMPP, o resultado será mostrado como uma **falha**, e informações adicionais serão gravadas nas propriedades de erro e diagnóstico:

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

Falha ao responder 10.188.116.96:5061

Exceção interna: falha na tentativa de conexão porque o

a parte conectada não respondeu corretamente após um período de

falha na hora ou estabelecida a conexão porque o host conectado

falhou ao responder 10.188.116.96:5061

Correto

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais **Test-CsXmppIM** pode falhar:

  - Um valor de parâmetro incorreto foi fornecido. Se usado, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará. Execute o comando novamente sem os parâmetros opcionais e veja se isso é bem-sucedido.

  - Esse comando falhará se a configuração de gateway do XMPP estiver configurada incorretamente ou ainda não tiver sido implantada.

</div>

<div>

## <a name="see-also"></a>Confira também


[Set-CsXmppGatewayConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsXmppGatewayConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

