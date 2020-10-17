---
title: 'Lync Server 2013: testar mensagens usando XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing messaging using XMPP
ms:assetid: ae5305ba-e5fc-4ca0-a805-872b4ebaf981
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727312(v=OCS.15)
ms:contentKeyID: 63969641
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79af6165da1c8d5093912f36413ef98812226cbc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518988"
---
# <a name="testing-messaging-using-xmpp-in-lync-server-2013"></a>Testando mensagens usando o XMPP no Lync Server 2013

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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsXmppIM</strong> . Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsXmppIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O XMPP é um protocolo de comunicações padrão (baseado em XML) usado para enviar mensagens pela Internet. O XMPP foi originalmente nomeado Jabber e é suportado por vários aplicativos de comunicação e mensagens da Internet, como o Google Talk e o chat do Facebook. O cmdlet **Test-CsXmppIM** verifica se um usuário pode trocar mensagens instantâneas com um usuário em uma rede do XMPP. Observe que, para esse teste ser bem-sucedido, você deve ter um endereço SIP válido para o usuário do XMPP e esse endereço SIP deve estar em uma rede configurada como um parceiro do XMPP permitido.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O exemplo a seguir verifica as funcionalidades de mensagens instantâneas do XMPP para o pool atl-cs-001.litwareinc.com. Este comando só funcionará se os usuários de teste estiverem definidos para o pool atl-cs-001.litwareinc.com. Se eles tiverem, o comando determinará se o primeiro usuário de teste pode enviar uma mensagem instantânea XMPP para um usuário que tenha o endereço SIP adelaney@contoso.com.

Se os usuários de teste não estiverem definidos, o comando falhará porque não saberá qual usuário fará logon como. Se você não definiu os usuários de teste para um pool, deverá incluir o parâmetro UserSipAddress e as credenciais do usuário que o comando deve usar ao tentar fazer logon.

    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com"

Os comandos mostrados no exemplo a seguir testam a capacidade de um usuário específico (litwareinc \\ pilar) fazer logon para enviar uma mensagem instantânea XMPP para o usuário adelaney@contoso.com. Para fazer isso, o primeiro comando no exemplo usa o cmdlet Get-Credential para criar um objeto de credencial da interface de linha de comando do Windows PowerShell que contenha o nome e a senha do usuário pilar Ackerman. (Como o nome de logon litwareinc \\ pilar foi incluído como um parâmetro, a caixa de diálogo de solicitação de credenciais do Windows PowerShell só exige que o administrador insira a senha da conta pilar Ackerman.) O objeto Credential resultante é armazenado em uma variável chamada $cred 1.

Em seguida, o segundo comando verifica se esse usuário pode fazer logon no pool atl-cs-001.litwareinc.com e enviar a mensagem instantânea XMPP. Para executar essa tarefa, o cmdlet **Test-CsXmppIm** é chamado, juntamente com quatro parâmetros: TargetFqdn (o FQDN do pool de registrador); Destinatário (o endereço SIP do usuário para o qual a mensagem está sendo endereçada); Usercredential (o objeto Windows PowerShell que contém as credenciais de usuário de pilar Ackerman); e UserSipAddress (o endereço SIP que corresponde às credenciais de usuário fornecidas).

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

Se o sistema de mensagens instantâneas do XMPP estiver configurado corretamente, você receberá uma saída semelhante a esta, com a propriedade Result marcada como **Success:**

FQDN de destino: atl-cs-001.litwareinc.com

Resultado: êxito

Latência: 00:00:02.5361946

Mensagem de erro:

Diagnóstico

Se os usuários especificados não puderem usar o sistema de mensagens instantâneas do XMPP, o resultado será mostrado como **falha**, e informações adicionais serão registradas nas propriedades de erro e diagnóstico:

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

Falha ao responder 10.188.116.96:5061

Exceção interna: falha na tentativa de conexão porque o

a parte conectada não respondeu corretamente após um período de

a hora ou a conexão estabelecida falhou porque o host conectado

Falha ao responder 10.188.116.96:5061

Diagnóstico

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais **Test-CsXmppIM** pode falhar:

  - Um valor de parâmetro incorreto foi fornecido. Se usado, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará. Execute novamente o comando sem os parâmetros opcionais e veja se isso é bem-sucedido.

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

