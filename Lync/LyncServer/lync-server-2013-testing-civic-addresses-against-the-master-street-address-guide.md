---
title: Testando endereços cívicos no guia de endereço mestre da rua
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing civic addresses against the master street address guide
ms:assetid: dc680de9-2a0f-4fd3-a99e-9bab0bc30ae5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690132(v=OCS.15)
ms:contentKeyID: 63969657
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d03647df3752860c114a16967a3bea5271a89d4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527808"
---
# <a name="testing-civic-addresses-against-the-master-street-address-guide-in-lync-server-2013"></a>Testando endereços cívicos no guia de endereço mestre no Lync Server 2013

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
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsRegistration. Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisCivicAddress &quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet Test-CsLisCivicAddress é usado para verificar os locais que foram adicionados ao banco de dados do serviço de informações de local (LIS). O cmdlet funciona por meio da comparação de locais com os locais encontrados no guia de endereço principal da rua (MSAG) que pertence ao seu provedor de roteamento de rede do E9-1-1. Se você não tiver um provedor de roteamento de rede ou se o provedor não puder ser acessado, seus testes falharão.

Se você adicionar o parâmetro de opção opcional UpdateValidationStatus ao comando, a propriedade de banco de dados MSAGValid correspondente será definida como true para cada endereço passando o teste.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

O cmdlet Test-CsLisCivicAddress pode ser usado para testar endereços individuais ou para testar vários endereços. Por exemplo, este comando testa um único endereço localizado em Redmond, WA:

    Test-CsLisCivicAddress -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName Main -StreetSuffix St -PostDirectional "" -City Redmond -State WA -PostalCode 98052 -Country US -UpdateValidationStatus

Por comparação, este comando testa todos os endereços atualmente no banco de dados LIS:

    Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus

Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15)) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinando o sucesso ou a falha

Test-CsLisCivicAddress irá relatar o êxito ou falha dos endereços fornecidos. Um teste de endereço falhará se o endereço não for encontrado ou se o provedor de serviços não puder ser contatado.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos pelos quais o teste pode ter falhado

Aqui estão alguns motivos comuns para que Test-CsLisCivicAddress possa falhar:

  - O provedor de serviços LIS pode não estar disponível. Você pode recuperar a URL do seu provedor de serviços de LIS executando o cmdlet Get-CsLisConfiguration:
    
        Get-CsLisConfiguration 
    
    Em seguida, você pode fazer o ping dessa URL para verificar se o provedor de serviços está disponível.

</div>

</div>

<span> </span>

</div>

</div>

</div>

