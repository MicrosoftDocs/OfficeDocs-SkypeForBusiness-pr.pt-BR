---
title: Testando endereços cívicos no guia de endereço mestre da rua
description: Teste de endereços cívicos no guia de endereço mestre da rua.
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
ms.openlocfilehash: 16e0d721b70e3db175b2d23ddee6f59d13a13c4e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560697"
---
# <a name="testing-civic-addresses-against-the-master-street-address-guide-in-lync-server-2013"></a><span data-ttu-id="76ff4-103">Testando endereços cívicos no guia de endereço mestre no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76ff4-103">Testing civic addresses against the master street address guide in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76ff4-104">_**Última modificação do tópico:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="76ff4-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76ff4-105">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="76ff4-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="76ff4-106">Diariamente</span><span class="sxs-lookup"><span data-stu-id="76ff4-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76ff4-107">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="76ff4-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="76ff4-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="76ff4-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76ff4-109">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="76ff4-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="76ff4-110">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="76ff4-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="76ff4-111">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsRegistration.</span><span class="sxs-lookup"><span data-stu-id="76ff4-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="76ff4-112">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="76ff4-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisCivicAddress &quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="76ff4-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="76ff4-113">Description</span></span>

<span data-ttu-id="76ff4-114">O cmdlet Test-CsLisCivicAddress é usado para verificar os locais que foram adicionados ao banco de dados do serviço de informações de local (LIS).</span><span class="sxs-lookup"><span data-stu-id="76ff4-114">The Test-CsLisCivicAddress cmdlet is used to verify locations that were added to your Location Information service (LIS) database.</span></span> <span data-ttu-id="76ff4-115">O cmdlet funciona por meio da comparação de locais com os locais encontrados no guia de endereço principal da rua (MSAG) que pertence ao seu provedor de roteamento de rede do E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="76ff4-115">The cmdlet works by comparing locations against the locations found in the Master Street Address Guide (MSAG) that belongs to your E9-1-1 Network Routing Provider.</span></span> <span data-ttu-id="76ff4-116">Se você não tiver um provedor de roteamento de rede ou se o provedor não puder ser acessado, seus testes falharão.</span><span class="sxs-lookup"><span data-stu-id="76ff4-116">If you do not have a network routing provider or if the provider cannot be reached, then your tests will fail.</span></span>

<span data-ttu-id="76ff4-117">Se você adicionar o parâmetro de opção opcional UpdateValidationStatus ao comando, a propriedade de banco de dados MSAGValid correspondente será definida como true para cada endereço passando o teste.</span><span class="sxs-lookup"><span data-stu-id="76ff4-117">If you add the optional switch parameter UpdateValidationStatus to your command, then the corresponding MSAGValid database property will be set to True for each address passing the test.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="76ff4-118">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="76ff4-118">Running the test</span></span>

<span data-ttu-id="76ff4-119">O cmdlet Test-CsLisCivicAddress pode ser usado para testar endereços individuais ou para testar vários endereços.</span><span class="sxs-lookup"><span data-stu-id="76ff4-119">The Test-CsLisCivicAddress cmdlet can be used to test individual addresses or to test multiple addresses.</span></span> <span data-ttu-id="76ff4-120">Por exemplo, este comando testa um único endereço localizado em Redmond, WA:</span><span class="sxs-lookup"><span data-stu-id="76ff4-120">For example, this command tests a single address located in Redmond, WA:</span></span>

    Test-CsLisCivicAddress -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName Main -StreetSuffix St -PostDirectional "" -City Redmond -State WA -PostalCode 98052 -Country US -UpdateValidationStatus

<span data-ttu-id="76ff4-121">Por comparação, este comando testa todos os endereços atualmente no banco de dados LIS:</span><span class="sxs-lookup"><span data-stu-id="76ff4-121">By comparison, this command tests all the addresses currently in your LIS database:</span></span>

    Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus

<span data-ttu-id="76ff4-122">Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="76ff4-122">For more information, see the Help documentation for the [Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="76ff4-123">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="76ff4-123">Determining success or failure</span></span>

<span data-ttu-id="76ff4-124">Test-CsLisCivicAddress irá relatar o êxito ou falha dos endereços fornecidos.</span><span class="sxs-lookup"><span data-stu-id="76ff4-124">Test-CsLisCivicAddress will report back Success or Failure for the supplied addresses.</span></span> <span data-ttu-id="76ff4-125">Um teste de endereço falhará se o endereço não for encontrado ou se o provedor de serviços não puder ser contatado.</span><span class="sxs-lookup"><span data-stu-id="76ff4-125">An address test will fail if the address cannot be found or if the service provider cannot be contacted.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="76ff4-126">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="76ff4-126">Reasons why the test might have failed</span></span>

<span data-ttu-id="76ff4-127">Aqui estão alguns motivos comuns para que Test-CsLisCivicAddress possa falhar:</span><span class="sxs-lookup"><span data-stu-id="76ff4-127">Here are some common reasons why Test-CsLisCivicAddress might fail:</span></span>

  - <span data-ttu-id="76ff4-128">O provedor de serviços LIS pode não estar disponível.</span><span class="sxs-lookup"><span data-stu-id="76ff4-128">The LIS service provider might not be available.</span></span> <span data-ttu-id="76ff4-129">Você pode recuperar a URL do seu provedor de serviços de LIS executando o cmdlet Get-CsLisConfiguration:</span><span class="sxs-lookup"><span data-stu-id="76ff4-129">You can retrieve the URL of your LIS service provider by running the Get-CsLisConfiguration cmdlet:</span></span>
    
        Get-CsLisConfiguration 
    
    <span data-ttu-id="76ff4-130">Em seguida, você pode fazer o ping dessa URL para verificar se o provedor de serviços está disponível.</span><span class="sxs-lookup"><span data-stu-id="76ff4-130">You can then ping that URL to verify that the service provider is available.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

