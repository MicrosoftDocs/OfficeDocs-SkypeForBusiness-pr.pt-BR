---
title: 'Lync Server 2013: Validando consulta da Web do catálogo de endereços'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book web query
ms:assetid: e6ae0a5a-e131-4cfe-9a33-6e611831072d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720925(v=OCS.15)
ms:contentKeyID: 63969662
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 548ec62a56de829955647a696e33578b9ab3dfd8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-address-book-web-query-in-lync-server-2013"></a>Validando a consulta da Web do catálogo de endereços no Lync Server 2013

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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsAddressBookWebQuery. Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookWebQuery&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet Test-CsAddressBookWebQuery permite que os administradores verifiquem se os usuários podem usar o serviço de consulta da Web do catálogo de endereços para pesquisar um contato específico. Quando você executar o cmdlet, Test-CsAddressBookWebQuery primeiro se conectará ao serviço de tíquete da Web para ser autenticado. Se a autenticação for bem-sucedida, o cmdlet será conectado ao serviço de consulta à Web do catálogo de endereços e pesquisará o contato especificado. Se esse contato for encontrado, o cmdlet tentará retornar essas informações para o computador local. O teste será marcado como êxito apenas se todas as etapas puderem ser concluídas.

Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O cmdlet Test-CsAddressBookWebQuery pode ser executado usando uma conta de teste pré-configurada (consulte Configurando contas de teste para executar testes do Lync Server) ou a conta de qualquer usuário habilitado para o Lync Server. Para executar essa verificação usando uma conta de teste, basta especificar o FQDN do pool do Lync Server e o endereço SIP do usuário que atua como o destino da pesquisa. Por exemplo:

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com"

Para executar essa verificação usando uma conta de usuário real, você deve criar um objeto de credenciais do Windows PowerShell que contenha um nome de usuário e uma senha válidos. Em seguida, você deve incluir o objeto Credentials e o endereço SIP atribuído à conta quando o código chamar Test-CsAddressBookWebQuery:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

Se o usuário especificado puder se conectar ao serviço de catálogo de endereços e recuperar o endereço de usuário de destino, você retornará uma saída semelhante a esta com a propriedade Result marcada como êxito:

TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: êxito

Latência: 00:00:06.2611356

Erros

Diagnóstico

Se o usuário especificado não puder se conectar ou se o endereço do usuário de destino não puder ser recuperado, o resultado será mostrado como falha, e informações adicionais serão registradas nas propriedades de erro e diagnóstico:

TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: falha

Latência: 00:00:00

Erro: a solicitação de serviço Web do catálogo de endereços falhou com o código de resposta

NoEntryFound.

Diagnóstico

A saída anterior indica que o teste falhou porque o usuário de destino não pôde ser encontrado. Você pode determinar se um endereço SIP válido foi passado para Test-CsAddressBookWebQuery executando um comando semelhante ao seguinte:

    Get-CsUser | Where-Object {$_.SipAddress -eq "sip:davidlongmire@litwareinc.com"

Se Test-CsAddressBookWebQuery falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -Verbose

Quando o parâmetro Verbose for incluído, o Test-CsAddressBookWebQuery retornará uma conta passo a passo de cada ação tentada durante a verificação da capacidade do usuário especificado de fazer logon no Lync Server. Por exemplo, essa saída indica que Test-CsAddressBookWebQuery foi capaz de se conectar ao serviço de catálogo de endereços, mas não pôde localizar o endereço SIP de destino:

Atividade ' QueryAddressBookWebService ' iniciada.

Chamando o serviço de consulta da Web do catálogo de endereços. URL ABWS =

https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

Exceção de consulta do catálogo de endereços: a solicitação de serviço Web do catálogo de endereços falhou com o código de resposta NoEntryFound.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais Test-CsAddressBookWebQuery pode falhar:

  - Você especificou uma conta de usuário inválida. Você pode verificar se uma conta de usuário existe executando um comando semelhante a este:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - A conta de usuário é válida, mas a conta não está atualmente habilitada para o Lync Server. Para verificar se uma conta de usuário foi habilitada para o Lync Server, execute um comando semelhante ao seguinte:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Se a propriedade Enabled estiver definida como false, isso significa que o usuário não está atualmente habilitado para o Lync Server.

  - O usuário de destino pode não estar no catálogo de endereços.

  - O catálogo de endereços pode não ter sido totalmente atualizado e replicado. Você pode forçar uma atualização de todos os servidores de catálogo de endereços em sua organização executando o seguinte comando:
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

