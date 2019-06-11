---
title: 'Lync Server 2013: testando a capacidade de se conectar a um domínio federado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing ability to connect to a federated domain
ms:assetid: d8ccfade-ef54-47a4-9f87-36213a635ce5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743840(v=OCS.15)
ms:contentKeyID: 63969653
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2176008e3e941068f61a2fb385fa6230df6b25dd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844659"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-connect-to-a-federated-domain-from-lync-server-2013"></a>Testar a capacidade de se conectar a um domínio federado pelo Lync Server 2013

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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsFederatedPartner. Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsFederatedPartner&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

Test-CsFederatedPartner verifica sua capacidade de conexão com o domínio de um parceiro federado. Para verificar a conectividade de um domínio, esse domínio deve estar listado na coleção de domínios permitidos (federados). Você pode recuperar uma lista dos domínios na lista de domínios permitidos usando este comando:

    Get-CsAllowedDomain

Para obter mais informações, consulte a documentação da ajuda para o cmdlet [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O cmdlet Test-FederatedPartner requer duas informações: o FQDN do servidor de borda e o FQDN do parceiro federado. Por exemplo, este comando testa a capacidade de conexão com o domínio contoso.com:

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"

Este comando permite testar as conexões com todos os domínios atualmente na lista de domínios permitidos:

    Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Identity}

Para obter mais informações, consulte a documentação da ajuda para o cmdlet [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinação do sucesso ou falha

Se o domínio especificado puder ser contatado, você receberá uma saída semelhante a isso com a propriedade Result marcada como **Success:**

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: êxito

Latência: 00:00:00

Erros

Correto

Se o domínio especificado não puder ser contatado, o resultado será mostrado como uma falha, e informações adicionais serão gravadas nas propriedades de erro e diagnóstico:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: falha

Latência: 00:00:00

Erro: 504, tempo limite do servidor

Diagnóstico: ErrorCode = 2, origem = ATL-cs-001. litwareinc. com, motivo = Veja

código de resposta e frase de motivo.

Microsoft. RTC. Signaling. DiagnosticHeader

Por exemplo, a saída anterior informa que o teste falhou devido a um erro de tempo limite do servidor. Isso geralmente indica problemas de conectividade de rede ou problemas para entrar em contato com o servidor de borda.

Se Test-CsFederatedPartner falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com" -Verbose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais Test-CsFederatedPartner pode falhar:

  - O servidor de borda pode não estar disponível. Você pode usar este comando para os FQDNs dos seus servidores de borda:
    
        Get-CsService -EdgeServer | Select-Object PoolFqdn
    
    Em seguida, você pode efetuar ping em cada servidor de borda para verificar se ele pode ser acessado pela rede. Por exemplo:
    
        ping atl-edge-001.litwareinc.com

  - O domínio especificado pode não estar listado na lista de domínios permitidos. Para verificar os domínios que foram adicionados à lista de domínios permitidos, use este comando:
    
        Get-CsAllowedDomain
    
    Se você quiser ver uma lista de domínios com os quais os usuários estavam bloqueados e, em seguida, use este comando:
    
        Get-CsBlockedDomain

</div>

</div>

<span> </span>

</div>

</div>

</div>

