---
title: 'Lync Server 2013: configurar um serviço de informações de local secundário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a secondary Location Information service
ms:assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398138(v=OCS.15)
ms:contentKeyID: 48183334
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44ffb1968197e79ae9b9fc87913c2e7876a21f8b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507718"
---
# <a name="configure-a-secondary-location-information-service-in-lync-server-2013"></a><span data-ttu-id="87c11-102">Configurar um serviço de informações de local secundário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87c11-102">Configure a secondary Location Information service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87c11-103">_**Última modificação do tópico:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="87c11-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="87c11-104">O Lync Server 2013 fornece uma interface de serviço Web que você pode usar para apontar o serviço de informações de local para um banco de dados de endereço de origem de local secundário (SLS).</span><span class="sxs-lookup"><span data-stu-id="87c11-104">Lync Server 2013 provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="87c11-105">A interface de serviço Web que se conecta ao banco de dados de SLS deve estar de acordo com o serviço de informações de local WSDL.</span><span class="sxs-lookup"><span data-stu-id="87c11-105">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="87c11-106">Se um banco de dados de local e um banco de dados de local secundário estiverem configurados, o serviço de informações de local consulta primeiro o banco de dados de local e, se nenhuma correspondência for encontrada, envia a solicitação de local do cliente para o banco de dados SLS.</span><span class="sxs-lookup"><span data-stu-id="87c11-106">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="87c11-107">Se o local existir no SLS, o serviço de informações de local enviará o local de volta para o cliente.</span><span class="sxs-lookup"><span data-stu-id="87c11-107">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span>

<span data-ttu-id="87c11-108">Para obter detalhes, consulte a documentação do Shell de gerenciamento do Lync Server para o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="87c11-108">For details, see the Lync Server Management Shell documentation for the following cmdlet:</span></span>

  - <span data-ttu-id="87c11-109">**Set-CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="87c11-109">**Set-CsWebServiceConfiguration**</span></span>

<div>

## <a name="to-configure-secondary-location-database"></a><span data-ttu-id="87c11-110">Para configurar o banco de dados de localização secundária</span><span class="sxs-lookup"><span data-stu-id="87c11-110">To configure Secondary Location database</span></span>

1.  <span data-ttu-id="87c11-111">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="87c11-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="87c11-112">Execute o cmdlet a seguir para configurar o URL para a localização do banco de dados de localização secundária.</span><span class="sxs-lookup"><span data-stu-id="87c11-112">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span>
    
        Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

