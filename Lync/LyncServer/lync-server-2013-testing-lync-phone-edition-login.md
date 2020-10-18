---
title: 'Lync Server 2013: testar o logon do Lync Phone Edition'
description: 'Lync Server 2013: testando o logon do Lync Phone Edition.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Phone Edition login
ms:assetid: 1ccde6bf-9a2d-4fcf-b81f-1bc9fee2cfbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690128(v=OCS.15)
ms:contentKeyID: 63969583
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d21d65676c4f5e0f867c7d9556cdea50419be69b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575237"
---
# <a name="testing-lync-phone-edition-login-in-lync-server-2013"></a>Testando o logon do Lync Phone Edition no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-06-05_


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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsPhoneBootstrap. Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPhoneBootstrap&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet Test-CsPhoneBootstrap permite que os administradores verifiquem se um determinado usuário, usando o número de telefone e o PIN atribuído a ele, podem fazer logon no sistema de um dispositivo compatível com Lync 2013 Phone Edition. (Nenhum dispositivo é realmente necessário para executar o teste).

Para que Test-CsPhoneBootstrap possa realizar essa verificação, é necessário que o pool de registradores que hospeda a conta do usuário testada seja detectável usando-se o DHCP. Para determinar se um registrador é detectável dessa maneira, use o cmdlet Get-CsRegistrarConfiguration e verifique o valor da propriedade EnableDHCPServer. Se essa propriedade for definida como false, você deverá usar Set-CsRegistrarConfiguration para definir o valor da propriedade como true e tornar o registrador detectável usando DHCP. Isso também pode ser feito usando o servidor DHCP corporativo e configurando as opções específicas do Lync Server.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

Para executar o cmdlet Test-CsPhoneBootstrap, você deve, no mínimo, fornecer o número de telefone e o PIN (número de identificação pessoal) do cliente para um usuário válido do Lync Server. Por exemplo, este comando testa a capacidade de logon do usuário que possui o número de telefone 12065551219 e o PIN 0712:

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712"

Para uma verificação mais abrangente, você também pode incluir o endereço SIP do usuário. Nesse caso, o número de telefone, PIN do cliente e endereço SIP devem ser válidos para que o teste seja bem-sucedido:

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -UserSipAddress "sip:kenmyer@litwareinc.com"

Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

Se o usuário especificado foi capaz de se conectar ao Lync Server, você receberá uma saída semelhante a esta, com a propriedade Result marcada como **êxito:**

TargetUri https://atl-cs-001.litwareinc.com:443/CertProv/

CertProvisioningService. svc

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: êxito

Latência: 00:00:06.3981276

Erros

Diagnóstico

Se o usuário especificado não foi capaz de fazer uma conexão, o resultado será mostrado como falha, e informações adicionais serão registradas nas propriedades de erro e diagnóstico:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: falha

Latência: 00:00:04.1993845

Erro: erro-nenhuma resposta recebida para o serviço de Web-Ticket.

Diagnóstico

A saída anterior indica que o teste falhou porque o serviço de tíquete da Web não respondeu. Isso pode ser devido a um problema com o serviço em si ou pode ser devido ao endereço SIP, número de telefone ou PIN do cliente passado para Test-CsPhoneBootstrap. Você pode verificar o endereço SIP do usuário e o número de telefone usando um comando semelhante a este:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, LineUri

E você pode verificar se o usuário tem um PIN válido usando um comando da seguinte maneira:

    Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com" 

Se Test-CsPhoneBootstrap falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -Verbose

Quando o parâmetro Verbose é incluído, Test-CsPhoneBootstrap retornará uma conta passo a passo de cada ação que tentou quando verificou a capacidade do usuário especificado fazer logon no Lync Server. Por exemplo, aqui está uma parte da saída de um logon não bem-sucedido, uma sessão na qual um PIN incorreto foi incluído:

Usando o PIN auth com \\ ramal de telefone: 12065551219 PIN: 0712

Não foi possível obter o tíquete da Web

Fira

\- A URL do serviço Web é válida e os serviços Web são funcionais

\- Se estiver usando \\ o PIN PhoneNo para autenticação, certifique-se de que eles correspondam ao URI do usuário

\- Se estiver usando a \\ autenticação Kerberos NTLM, certifique-se de ter fornecido credenciais válidas

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns para que Test-CsPhoneBootstrap possa falhar:

  - Você pode ter especificado um endereço SIP que não é válido. Você pode verificar se um endereço SIP está correto usando um comando como este:
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com"

  - Você pode ter especificado um PIN que não é válido. Embora não seja possível recuperar o número PIN do usuário, você pode verificar se o usuário pelo menos tem um número PIN usando um comando semelhante a este:
    
        Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com"

  - Você pode ter especificado um número de telefone que não seja válido. Você pode verificar o telefone de um usuário usando um comando semelhante ao seguinte:
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object LineUri

  - O pool de registradores não está habilitado para DHCP. Para determinar se o seu pool de registradores está habilitado para DHCP, execute o cmdlet Get-CsRegistrarConfiguration e verifique o valor da propriedade EnableDHCPServer. Por exemplo:
    
        Get-CsRegistrarConfiguration -Identity "global"

</div>

</div>

<span> </span>

</div>

</div>

</div>

