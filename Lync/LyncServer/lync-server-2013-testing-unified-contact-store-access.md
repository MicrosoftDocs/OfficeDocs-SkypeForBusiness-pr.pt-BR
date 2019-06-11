---
title: 'Lync Server 2013: testando o acesso ao repositório de contatos unificado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing Unified Contact Store access
ms:assetid: 761f46bd-2e14-4f40-82b9-afa1eaa816b0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727309(v=OCS.15)
ms:contentKeyID: 63969621
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef1d8d8930b9e732faeef02c76d722331c726b67
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844601"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-unified-contact-store-access-in-lync-server-2013"></a>Testando o acesso a repositório de contatos unificado no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2015-05-15_


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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsUnifiedContactStore</strong> . Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUnifiedContactStore&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O repositório de contatos Unificado apresentado no Lync Server 2013 fornece aos administradores a opção de armazenar os contatos de um usuário no Microsoft Exchange Server 2013 em vez de no Lync Server. Isso permite que o usuário acesse o mesmo conjunto de contatos no Outlook Web Access, além do Lync 2013. (Ou você pode continuar a armazenar contatos no Lync Server. Nesse caso, os usuários precisarão manter dois conjuntos de contatos separados: um para uso com o Outlook e o Outlook Web Access e um para uso com o Lync 2013.)

Você pode determinar se os contatos de um usuário foram movidos para o repositório de contatos unificado executando o cmdlet **Test-CsUnifiedContactStore** . O cmdlet **Test-CsUnifiedContactStore** usará a conta de usuário especificada, se conectará ao repositório de contatos unificado e tentará recuperar um contato para o usuário. Se não for possível recuperar nenhum contato, o comando falhará junto com a mensagem "nenhum contato foi recebido para o usuário. Verifique se os contatos existem para o usuário. "

Observe que o cmdlet **Test-CsUnifiedContactStore** falhará se o usuário tiver migrado com êxito para o repositório de contatos unificado, mas não tiver contatos na lista de contatos dela. O usuário especificado deve ter pelo menos um contato para que o cmdlet **Test-CsUnifiedContactStore** seja concluído com êxito.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

Os comandos mostrados no exemplo a seguir determinam se os contatos do\\usuário litwareinc kenmyer podem ser encontrados no repositório de contatos unificado. Para fazer isso, o primeiro comando do exemplo usa o cmdlet **Get-Credential** para criar um objeto de credenciais da interface de linha de comando do Windows PowerShell para\\o usuário litwareinc kenmyer. Observe que você deve fornecer a senha desta conta para criar um objeto de credenciais válido e verificar se o cmdlet **Test-CsUnifiedContactStore** pode executar sua verificação.

O segundo comando do exemplo usa o objeto de credenciais fornecido ($x) e o endereço SIP do usuário litwareinc\\kenmyer para determinar se seus contatos podem ser encontrados no repositório de contatos unificado.

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsUnifiedContactStore -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinação do sucesso ou falha

Se o acesso ao repositório de contatos estiver configurado corretamente, você receberá uma saída semelhante a isso, com a propriedade Result marcada como **Success:**

FQDN de destino: atl-cs-001.litwareinc.com

Resultado: êxito

Latência: 00:00:14.9862716

Mensagem de erro:

Correto

Se o acesso ao repositório de contatos não estiver configurado corretamente, o resultado será mostrado como uma **falha**, e informações adicionais serão gravadas nas propriedades de erro e diagnóstico:

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

Aqui estão alguns motivos comuns pelos quais **Test-CsUnifiedContactStore** pode falhar:

  - Um valor de parâmetro incorreto foi fornecido. Se usado, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará. Execute o comando novamente sem os parâmetros opcionais e veja se isso é bem-sucedido.

  - Não foi possível conectar-se ao repositório de contatos unificado, e a tentativa de recuperar um contato para o usuário não foi possível. Pode haver problemas de conectividade de rede.

</div>

<div>

## <a name="see-also"></a>Confira também


[New-CsUserServicesPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)  
[Set-CsUserServicesPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

