---
title: 'Lync Server 2013: Validando o acesso ao catálogo de endereços'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating address book access
ms:assetid: 630682c6-9262-46c5-9af1-6193db70374b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720916(v=OCS.15)
ms:contentKeyID: 63969611
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 233ad9804ea0f9ddd1075ea01bf7a4c8f35da819
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844437"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-access-in-lync-server-2013"></a>Validando o acesso ao catálogo de endereços no Lync Server 2013

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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsAddressBookService. Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet Test-CsAddressBookService fornece uma maneira de verificar se um usuário pode se conectar ao serviço Web de download do catálogo de endereços. Quando você executa o cmdlet, Test-CsAddressBookService conecta-se ao serviço Web de download do catálogo de endereços no pool especificado e solicita o local dos arquivos do catálogo de endereços. Se o serviço Web de download do catálogo de endereços fornecer essa localização, o teste será considerado com êxito. Se a solicitação for negada, o teste será considerado uma falha.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O cmdlet Test-CsAddressBookService pode ser executado usando uma conta de teste pré-configurada (consulte Configurando contas de teste para executar testes do Lync Server) ou a conta de qualquer usuário que tenha sido habilitado para o Lync Server. Para executar essa verificação usando uma conta de teste, tudo o que você precisa fazer é especificar o nome de domínio totalmente qualificado (FQDN) do pool do servidor do Lync que está sendo testado. Por exemplo:

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

Para executar essa verificação usando uma conta de usuário real, primeiro você deve criar um objeto de credenciais do Windows PowerShell que contenha o nome da conta e a senha. Em seguida, você deve incluir esse objeto de credenciais e o endereço SIP atribuído à conta ao chamar Test-CsAddressBookService:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Para obter mais informações, consulte a documentação da ajuda para o cmdlet [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinação do sucesso ou falha

Se o usuário especificado for capaz de se conectar ao serviço de catálogo de endereços, você receberá uma saída semelhante a isso, com a propriedade Result marcada como **Success**:

TargetUri :https://lync-se.fabrikam.com:443/abs/handler

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: êxito

Latência: 00:00:06.2260399

Erros

Correto

Se o usuário especificado não puder fazer essa conexão, o resultado será mostrado como uma falha, e informações adicionais serão gravadas nas propriedades de erro e diagnóstico:

TargetUri :

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: falha

Latência: 00:00:00

Diagnóstico: ErrorCode = 4005, Source = ATL-cs-001.litwareinc.com,

Motivo = o URI de destino não está habilitado para SIP ou não

Existem.

Microsoft. RTC. Signaling. DiagnosticHeader

Por exemplo, a saída anterior informa que o teste falhou porque o usuário especificado (isto é, o "URI de destino") não existe ou não foi habilitado para o Lync Server. Você pode verificar se uma conta de usuário é válida e se você forneceu o endereço SIP correto executando um comando como este:

Get-CsUser-identidade "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

Se Test-CsAddressBookService falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:

Test-CsAddressBookService-TargetFqdn "atl-cs-001.litwareinc.com"-detalhado

Quando o parâmetro Verbose for incluído, Test-CsAddressBookService retornará uma conta passo a passo de cada ação tentada ao verificar a capacidade do usuário especificado de fazer logon no Lync Server. Por exemplo, esta saída de exemplo mostra que Test-CsAddressBookService, pelo menos neste exemplo, pôde baixar o arquivo do catálogo de endereços:

Enviando solicitação HTTP GET.

Caminho do arquivo =https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs

Número da tentativa = 1

Tempo limite (mseg) = 60000

O arquivo ABS foi baixado com êxitohttps://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais Test-CsAddressBookService pode falhar:

  - Você especificou uma conta de usuário inválida. Você pode verificar se existe uma conta de usuário executando um comando semelhante a este:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - A conta de usuário é válida, mas a conta não está habilitada no momento para o Lync Server. Para verificar se uma conta de usuário foi habilitada para o Lync Server, execute um comando semelhante ao seguinte:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está habilitado no momento para o Lync Server.

</div>

<div>

## <a name="see-also"></a>Confira também


[Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

