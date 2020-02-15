---
title: 'Lync Server 2013: capacidade de teste para se conectar a um domínio federado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to connect to a federated domain
ms:assetid: d8ccfade-ef54-47a4-9f87-36213a635ce5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743840(v=OCS.15)
ms:contentKeyID: 63969653
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82c44cf7cff78fc93054679ae1bc4c66bc6b4c40
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42016232"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-connect-to-a-federated-domain-from-lync-server-2013"></a>Testando a capacidade de se conectar a um domínio federado do Lync Server 2013

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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsFederatedPartner. Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsFederatedPartner&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

Test-CsFederatedPartner verifica sua capacidade de se conectar ao domínio de um parceiro federado. Para verificar a conectividade para um domínio, esse domínio deve ser listado na coleção de domínios permitidos (federados). Você pode recuperar uma lista dos domínios na lista de domínios permitidos usando este comando:

    Get-CsAllowedDomain

Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O cmdlet Test-FederatedPartner requer duas informações: o FQDN do servidor de borda e o FQDN do parceiro federado. Por exemplo, este comando testa a capacidade de se conectar ao domínio contoso.com:

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"

Este comando permite testar as conexões de todos os domínios que estão atualmente na sua lista de domínios permitidos:

    Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Identity}

Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

Se o domínio especificado puder ser contatado, você receberá uma saída semelhante a esta com a propriedade Result marcada como **Success:**

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: êxito

Latência: 00:00:00

Erros

Diagnóstico

Se o domínio especificado não puder ser contatado, o resultado será mostrado como falha, e as informações adicionais serão registradas nas propriedades de erro e diagnóstico:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: falha

Latência: 00:00:00

Erro: 504, tempo limite do servidor

Diagnóstico: ErrorCode = 2, Source = ATL-cs-001. litwareinc. com, razão = Confira

código de resposta e frase de motivo.

Microsoft. RTC. Signaling. DiagnosticHeader

Por exemplo, a saída anterior diz que o teste falhou devido a um erro de tempo limite do servidor. Isso geralmente indica problemas de conectividade de rede ou problemas para entrar em contato com o servidor de borda.

Se Test-CsFederatedPartner falhar, talvez você queira executar novamente o teste, desta vez, incluindo o parâmetro Verbose:

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com" -Verbose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais Test-CsFederatedPartner pode falhar:

  - O servidor de borda pode não estar disponível. Você pode usar os FQDNs dos seus servidores de borda usando este comando:
    
        Get-CsService -EdgeServer | Select-Object PoolFqdn
    
    Você pode então efetuar ping em cada servidor de borda para verificar se ele pode ser acessado pela rede. Por exemplo:
    
        ping atl-edge-001.litwareinc.com

  - O domínio especificado pode não estar listado na lista de domínios permitidos. Para verificar os domínios que foram adicionados à lista de domínios permitidos, use este comando:
    
        Get-CsAllowedDomain
    
    Se quiser ver uma lista de domínios com os quais os usuários foram bloqueados e use este comando:
    
        Get-CsBlockedDomain

</div>

</div>

<span> </span>

</div>

</div>

</div>

