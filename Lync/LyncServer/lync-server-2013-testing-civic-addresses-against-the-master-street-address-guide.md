---
title: Testando endereços cívicos no guia de endereço principal do Street
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing civic addresses against the master street address guide
ms:assetid: dc680de9-2a0f-4fd3-a99e-9bab0bc30ae5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690132(v=OCS.15)
ms:contentKeyID: 63969657
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfa4dd28ec05546366e029b6fb9fdf1c4b3ae310
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844648"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-civic-addresses-against-the-master-street-address-guide-in-lync-server-2013"></a>Testando endereços cívicos em relação ao guia de endereço mestre do Lync Server 2013

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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsRegistration. Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisCivicAddress &quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet Test-CsLisCivicAddress é usado para verificar os locais que foram adicionados ao seu banco de dados do serviço de informações de localização (LIS). O cmdlet funciona comparando os locais com base nos locais encontrados no guia de endereço mestre do Street (MSAG) que pertence ao seu provedor de roteamento de rede do E9-1. Se você não tiver um provedor de roteamento de rede ou se o provedor não puder ser acessado, seus testes falharão.

Se você adicionar o parâmetro de opção opcional UpdateValidationStatus ao seu comando, a propriedade de banco de dados MSAGValid correspondente será definida como true para cada endereço passando pelo teste.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O cmdlet Test-CsLisCivicAddress pode ser usado para testar endereços individuais ou testar vários endereços. Por exemplo, este comando testa um único endereço localizado em Redmond, WA:

    Test-CsLisCivicAddress -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName Main -StreetSuffix St -PostDirectional "" -City Redmond -State WA -PostalCode 98052 -Country US -UpdateValidationStatus

Por comparação, esse comando testa todos os endereços atualmente em seu banco de dados LIS:

    Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus

Para obter mais informações, consulte a documentação da ajuda para o cmdlet [Test-CsRegistration](https://technet.microsoft.com/en-us/library/Gg412737(v=OCS.15)) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinação do sucesso ou falha

Test-CsLisCivicAddress reportará o êxito ou falha dos endereços fornecidos. Um teste de endereço falhará se o endereço não for encontrado ou se não for possível entrar em contato com o provedor de serviço.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns pelos quais Test-CsLisCivicAddress pode falhar:

  - O provedor de serviço LIS pode não estar disponível. Você pode recuperar a URL do seu provedor de serviços LIS executando o cmdlet Get-CsLisConfiguration:
    
        Get-CsLisConfiguration 
    
    Em seguida, você pode executar o ping nesse URL para verificar se o provedor de serviço está disponível.

</div>

</div>

<span> </span>

</div>

</div>

</div>

