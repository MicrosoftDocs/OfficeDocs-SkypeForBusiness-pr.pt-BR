---
title: 'Lync Server 2013: testando conexão do usuário para UM Exchange UM'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user connection to Exchange UM
ms:assetid: 0b83fbf4-e124-4efd-a0a9-202eb849af82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727300(v=OCS.15)
ms:contentKeyID: 63969573
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d4a4c4194ad730a64b167aaaf33151c8a7684e8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745361"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-user-connection-to-exchange-um-in-lync-server-2013"></a>Testando a conexão do usuário com o Exchange UM no Lync Server 2013

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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsExUMConnectivity</strong> . Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMConnectivity&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet **Test-CsExUMConnectivity** verifica se o usuário especificado pode se conectar ao serviço de Unificação de mensagens do Microsoft Exchange Server 2013. Observe que esse cmdlet verifica somente se uma conexão pode ser feita com o serviço. Ele não testa o próprio serviço. Para testar o serviço de Unificação de mensagens (executando um cmdlet de transação sintético que realmente deixa uma mensagem de caixa postal em uma caixa de correio do usuário), use o cmdlet Test-CsExUMVoiceMail.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O exemplo a seguir testa a conectividade da Unificação de mensagens do Exchange para o pool atl-cs-001.litwareinc.com. Esse comando funcionará apenas se os usuários de teste tiverem sido definidos para o pool atl-cs-001.litwareinc.com. Se eles tiverem, o comando determinará se o primeiro usuário de teste pode se conectar à unificação de mensagens. Se os usuários de teste não tiverem sido configurados para o pool, o comando irá falhar.

    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" 

Os comandos mostrados no exemplo a seguir testam a conectividade de Unificação\\de mensagens do Exchange para o usuário litwareinc kenmyer. Para fazer isso, o primeiro comando do exemplo usa o cmdlet **Get-Credential** para criar um objeto de credenciais da interface de linha de comando do Windows PowerShell para\\o usuário litwareinc kenmyer. Observe que você deve fornecer a senha desta conta para criar um objeto de credenciais válido e para garantir que o cmdlet **Test-CsExUMConnectivity** possa executar sua verificação.

O segundo comando do exemplo usa o objeto de credenciais fornecido ($x) e o endereço SIP do usuário litwareinc\\kenmyer para determinar se ou este usuário pode se conectar a uma Unificação de mensagens do Exchange.

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

O comando mostrado no próximo exemplo é uma variação do comando que acabou de ser mostrado. Nesse caso, o parâmetro OutLoggerVariable é incluído para gerar um log detalhado de cada etapa feita pelo **Test-CsExUMConnectivity** cmdletand o êxito ou falha de cada uma dessas etapas. Para fazer isso, o parâmetro OutLoggerVariable é adicionado juntamente com o valor de parâmetro ExumText; Isso faz com que as informações de registro detalhadas sejam armazenadas em uma variável chamada $ExumTest. No comando final do exemplo, o método ToXML () é usado para converter as informações de log em formato XML. Em seguida, esses dados XML são gravados em um arquivo chamado C\\:\\registra o ExumTest. xml usando o cmdlet Out-File.

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -OutLoggerVariable ExumTest 
    $ExumTest.ToXML() | Out-File C:\Logs\ExumTest.xml 

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinação do sucesso ou falha

Se a integração com o Exchange estiver configurada corretamente, você receberá uma saída semelhante a isso, com a propriedade Result marcada como **Success**:

FQDN de destino: atl-cs-001.litwareinc.com

Resultado: êxito

Latência: 00:00:00

Mensagem de erro:

Correto

Se o usuário especificado não puder receber notificações, o resultado será mostrado como uma **falha**, e informações adicionais serão gravadas nas propriedades de erro e diagnóstico:

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

Aqui estão alguns motivos comuns pelos quais **Test-CsExUMConnectivity** pode falhar:

  - Um valor de parâmetro incorreto foi fornecido. Se usado, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará. Execute o comando novamente sem os parâmetros opcionais e veja se isso é bem-sucedido.

  - Esse comando falhará se o Exchange Server estiver configurado incorretamente ou ainda não foi implantado.

  - Esse comando falhará se o Exchange Server não puder ser acessado pela rede.

</div>

<div>

## <a name="see-also"></a>Confira também


[Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

