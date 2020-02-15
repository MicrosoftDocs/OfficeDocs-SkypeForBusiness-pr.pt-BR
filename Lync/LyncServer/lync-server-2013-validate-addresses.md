---
title: 'Lync Server 2013: validar endereços'
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
ms.openlocfilehash: 75eeabe640c9d66c897d59f4e06bb485a482ed04
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007440"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-addresses-in-lync-server-2013"></a><span data-ttu-id="953c7-102">Validar endereços no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="953c7-102">Validate addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="953c7-103">_**Última modificação do tópico:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="953c7-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="953c7-104">Antes de publicar o banco de dados local, você deverá validar novas localizações em relação ao MSAG (Master Street Address Guide) mantido pelo seu tronco SIP ou pelo provedor de serviços de rede telefônica pública comutada (PSTN) E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="953c7-104">Before publishing the location database, you must validate new locations against the Master Street Address Guide (MSAG) that is maintained by your SIP trunk or public switched telephone network (PSTN) E9-1-1 service provider.</span></span>

<span data-ttu-id="953c7-105">Para obter detalhes sobre os provedores de serviço E9-1-1 do tronco SIP, consulte [escolhendo um provedor de serviço E9-1-1 para o Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).</span><span class="sxs-lookup"><span data-stu-id="953c7-105">For details about SIP trunk E9-1-1 service providers, see [Choosing an E9-1-1 service provider for Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).</span></span>

<span data-ttu-id="953c7-106">Para obter detalhes sobre como validar endereços, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="953c7-106">For details about validating addresses, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="953c7-107">**Get-CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="953c7-107">**Get-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="953c7-108">**Set-CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="953c7-108">**Set-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="953c7-109">**Remove-CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="953c7-109">**Remove-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="953c7-110">**Get-CsLisCivicAddress**</span><span class="sxs-lookup"><span data-stu-id="953c7-110">**Get-CsLisCivicAddress**</span></span>

  - <span data-ttu-id="953c7-111">**Test-CsLisCivicAddress**</span><span class="sxs-lookup"><span data-stu-id="953c7-111">**Test-CsLisCivicAddress**</span></span>

<div>

## <a name="to-validate-addresses-located-in-the-location-database"></a><span data-ttu-id="953c7-112">Para validar endereços localizados no banco de dados de localização</span><span class="sxs-lookup"><span data-stu-id="953c7-112">To validate addresses located in the location database</span></span>

1.  <span data-ttu-id="953c7-113">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="953c7-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="953c7-114">Execute os cmdlets a seguir para configurar a conexão com o provedor de serviços de emergência.</span><span class="sxs-lookup"><span data-stu-id="953c7-114">Run the following cmdlets to configure the emergency service provider connection.</span></span>
    
        $pwd = Read-Host -AsSecureString <password>
        Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

3.  <span data-ttu-id="953c7-115">Execute o cmdlet a seguir para validar os endereços no banco de dados de localização.</span><span class="sxs-lookup"><span data-stu-id="953c7-115">Run the following cmdlet to validate the addresses in the location database.</span></span>
    
        Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
    
    <span data-ttu-id="953c7-116">Você também pode usar o cmdlet **Test-CsLisCivicAddress** para validar endereços individuais.</span><span class="sxs-lookup"><span data-stu-id="953c7-116">You can also use the **Test-CsLisCivicAddress** cmdlet to validate individual addresses.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

