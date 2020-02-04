---
title: 'Lync Server 2013: configurar um serviço de informações de localização secundário'
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
ms.openlocfilehash: c2b7ee9383939e8df5466d615f6fda4a2af33c2b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741361"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-secondary-location-information-service-in-lync-server-2013"></a><span data-ttu-id="cd789-102">Configurar um serviço de informações de localização secundário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd789-102">Configure a secondary Location Information service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd789-103">_**Tópico da última modificação:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="cd789-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="cd789-104">O Lync Server 2013 fornece uma interface de serviço Web que você pode usar para apontar o serviço de informações de localização para um banco de dados de local secundário (SLS).</span><span class="sxs-lookup"><span data-stu-id="cd789-104">Lync Server 2013 provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="cd789-105">A interface do serviço Web que se conecta ao banco de dados SLS deve estar de acordo com o WSDL do serviço de informações de localização.</span><span class="sxs-lookup"><span data-stu-id="cd789-105">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="cd789-106">Se o banco de dados de localização e o banco de dados de local secundário estiverem configurados, o serviço informações de localização primeiro consultará o banco de dados de localização e, se nenhuma correspondência for encontrada, envia a solicitação de localização do cliente para o banco de dados SLS.</span><span class="sxs-lookup"><span data-stu-id="cd789-106">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="cd789-107">Se o local existir no SLS, o serviço de informações de localização enviará o local de volta ao cliente.</span><span class="sxs-lookup"><span data-stu-id="cd789-107">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span>

<span data-ttu-id="cd789-108">Para obter detalhes, consulte a documentação do Shell de gerenciamento do Lync Server para o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="cd789-108">For details, see the Lync Server Management Shell documentation for the following cmdlet:</span></span>

  - <span data-ttu-id="cd789-109">**Set-CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="cd789-109">**Set-CsWebServiceConfiguration**</span></span>

<div>

## <a name="to-configure-secondary-location-database"></a><span data-ttu-id="cd789-110">Para configurar o banco de dados de localização secundário</span><span class="sxs-lookup"><span data-stu-id="cd789-110">To configure Secondary Location database</span></span>

1.  <span data-ttu-id="cd789-111">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="cd789-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="cd789-112">Execute o cmdlet a seguir para configurar o URL para a localização do banco de dados de localização secundária.</span><span class="sxs-lookup"><span data-stu-id="cd789-112">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span>
    
        Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

