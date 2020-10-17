---
title: 'Lync Server 2013: validar endereços'
description: 'Lync Server 2013: validar endereços.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validate addresses
ms:assetid: aae557c9-e6f5-4d23-8af1-1d4cd7968c54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412808(v=OCS.15)
ms:contentKeyID: 48185108
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bcbb8789912b3bcbcfb60dd79807f06c2957c1f6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547267"
---
# <a name="validate-addresses-in-lync-server-2013"></a><span data-ttu-id="94e88-103">Validar endereços no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94e88-103">Validate addresses in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94e88-104">_**Última modificação do tópico:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="94e88-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="94e88-105">Antes de publicar o banco de dados local, você deverá validar novas localizações em relação ao MSAG (Master Street Address Guide) mantido pelo seu tronco SIP ou pelo provedor de serviços de rede telefônica pública comutada (PSTN) E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="94e88-105">Before publishing the location database, you must validate new locations against the Master Street Address Guide (MSAG) that is maintained by your SIP trunk or public switched telephone network (PSTN) E9-1-1 service provider.</span></span>

<span data-ttu-id="94e88-106">Para obter detalhes sobre os provedores de serviço E9-1-1 do tronco SIP, consulte [escolhendo um provedor de serviço E9-1-1 para o Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).</span><span class="sxs-lookup"><span data-stu-id="94e88-106">For details about SIP trunk E9-1-1 service providers, see [Choosing an E9-1-1 service provider for Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).</span></span>

<span data-ttu-id="94e88-107">Para obter detalhes sobre como validar endereços, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="94e88-107">For details about validating addresses, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="94e88-108">**Get-CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="94e88-108">**Get-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="94e88-109">**Set-CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="94e88-109">**Set-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="94e88-110">**Remove-CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="94e88-110">**Remove-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="94e88-111">**Get-CsLisCivicAddress**</span><span class="sxs-lookup"><span data-stu-id="94e88-111">**Get-CsLisCivicAddress**</span></span>

  - <span data-ttu-id="94e88-112">**Test-CsLisCivicAddress**</span><span class="sxs-lookup"><span data-stu-id="94e88-112">**Test-CsLisCivicAddress**</span></span>

<div>

## <a name="to-validate-addresses-located-in-the-location-database"></a><span data-ttu-id="94e88-113">Para validar endereços localizados no banco de dados de localização</span><span class="sxs-lookup"><span data-stu-id="94e88-113">To validate addresses located in the location database</span></span>

1.  <span data-ttu-id="94e88-114">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="94e88-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="94e88-115">Execute os cmdlets a seguir para configurar a conexão com o provedor de serviços de emergência.</span><span class="sxs-lookup"><span data-stu-id="94e88-115">Run the following cmdlets to configure the emergency service provider connection.</span></span>
    
        $pwd = Read-Host -AsSecureString <password>
        Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

3.  <span data-ttu-id="94e88-116">Execute o cmdlet a seguir para validar os endereços no banco de dados de localização.</span><span class="sxs-lookup"><span data-stu-id="94e88-116">Run the following cmdlet to validate the addresses in the location database.</span></span>
    
        Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
    
    <span data-ttu-id="94e88-117">Você também pode usar o cmdlet **Test-CsLisCivicAddress** para validar endereços individuais.</span><span class="sxs-lookup"><span data-stu-id="94e88-117">You can also use the **Test-CsLisCivicAddress** cmdlet to validate individual addresses.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

