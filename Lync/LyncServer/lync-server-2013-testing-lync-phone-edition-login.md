---
title: 'Lync Server 2013: testando o logon no Lync Phone Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing Lync Phone Edition login
ms:assetid: 1ccde6bf-9a2d-4fcf-b81f-1bc9fee2cfbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690128(v=OCS.15)
ms:contentKeyID: 63969583
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb2cf0dae748cf82e83e86389abf55c55c8c70e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844635"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-phone-edition-login-in-lync-server-2013"></a>Testando o login do Lync Phone Edition no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-06-05_


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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsPhoneBootstrap. Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPhoneBootstrap&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet Test-CsPhoneBootstrap permite que os administradores verifiquem se um determinado usuário, usando o número de telefone e o PIN atribuído a ele ou dele, pode fazer logon no sistema a partir de um dispositivo compatível com o Lync 2013 Phone Edition. (Nenhum dispositivo é realmente necessário para executar o teste.)

Para que o CsPhoneBootstrap seja verificado, o pool de registradores que hospeda a conta de usuário que está sendo testada deve ser detectável usando DHCP. Para determinar se um registrador é detectável dessa maneira, use o cmdlet Get-CsRegistrarConfiguration e verifique o valor da propriedade EnableDHCPServer. Se essa propriedade for definida como false, você deverá usar set-CsRegistrarConfiguration para definir o valor da propriedade como true e torná-lo detectável usando DHCP. Isso também pode ser feito usando o servidor DHCP corporativo e configurando as opções específicas do Lync Server.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

Para executar o cmdlet Test-CsPhoneBootstrap, você deve, no mínimo, fornecer o número de telefone e o PIN (número de identificação pessoal) do cliente para um usuário válido do Lync Server. Por exemplo, esse comando testa a capacidade de logon do usuário que tem o número de telefone 12065551219 e o pino 0712:

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712"

Para uma verificação mais abrangente, você também pode incluir o endereço SIP do usuário. Nesse caso, o número de telefone, o PIN do cliente e o endereço SIP devem ser todos válidos para que o teste seja bem-sucedido:

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -UserSipAddress "sip:kenmyer@litwareinc.com"

Para obter mais informações, consulte a documentação da ajuda para o cmdlet [Test-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinação do sucesso ou falha

Se o usuário especificado tiver conseguido se conectar ao Lync Server, você receberá uma saída semelhante a isso, com a propriedade Result marcada como **Success:**

TargetUri :https://atl-cs-001.litwareinc.com:443/CertProv/

CertProvisioningService. svc

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: êxito

Latência: 00:00:06.3981276

Erros

Correto

Se o usuário especificado não puder fazer uma conexão, o resultado será mostrado como uma falha, e informações adicionais serão gravadas nas propriedades de erro e diagnóstico:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: falha

Latência: 00:00:04.1993845

Erro: erro-nenhuma resposta recebida para o serviço Web-ticket.

Correto

A saída anterior informa que o teste falhou porque o serviço de tíquete da Web não respondeu. Isso pode ser devido a um problema com o próprio serviço ou pode ser devido ao endereço SIP, número de telefone ou PIN do cliente aprovado para Test-CsPhoneBootstrap. Você pode verificar o endereço SIP do usuário e o número de telefone usando um comando semelhante a este:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, LineUri

E você pode verificar se o usuário tem um PIN válido usando um comando da seguinte maneira:

    Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com" 

Se Test-CsPhoneBootstrap falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -Verbose

Quando o parâmetro Verbose estiver incluído, Test-CsPhoneBootstrap retornará uma conta passo a passo de cada ação que tentou verificar quando verificou a capacidade do usuário especificado para fazer logon no Lync Server. Por exemplo, aqui está uma parte da saída de um logon malsucedido, uma sessão na qual um PIN incorreto foi incluído:

Usando a autenticação de PIN\\com a extensão de telefone: 12065551219 pino: 0712

Não foi possível obter a permissão da Web

SELECIONAR

\-A URL do serviço Web é válida e os serviços Web são funcionais

\-Se estiver usando\\o pino PhoneNo para autenticar, certifique-se de que correspondam ao URI do usuário

\-Se estiver usando\\a autenticação Kerberos NTLM, certifique-se de que você forneceu credenciais válidas

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais Test-CsPhoneBootstrap pode falhar:

  - Você pode ter especificado um endereço SIP que não é válido. Você pode verificar se um endereço SIP está correto usando um comando como este:
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com"

  - Você pode ter especificado um PIN que não é válido. Embora não seja possível recuperar o número PIN do usuário, você pode verificar se o usuário pelo menos tem um número PIN usando um comando semelhante a este:
    
        Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com"

  - Você pode ter especificado um número de telefone inválido. Você pode verificar o telefone de um usuário usando um comando semelhante ao seguinte:
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object LineUri

  - O pool de registradores não está habilitado para DHCP. Para determinar se o pool de registrador está habilitado para DHCP, execute o cmdlet Get-CsRegistrarConfiguration e verifique o valor da propriedade EnableDHCPServer. Por exemplo:
    
        Get-CsRegistrarConfiguration -Identity "global"

</div>

</div>

<span> </span>

</div>

</div>

</div>

