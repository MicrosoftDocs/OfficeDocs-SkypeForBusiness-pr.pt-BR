---
title: 'Lync Server 2013: publicar o banco de dados de localização'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the location database
ms:assetid: dd032b5b-df0e-4017-ac46-e17570c1ab1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398974(v=OCS.15)
ms:contentKeyID: 48185598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b773e5332ba05d20da9ece0b7ecb521d664e3b49
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201667"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publish-the-location-database-from-lync-server-2013"></a><span data-ttu-id="267ee-102">Publicar o banco de dados de localização do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="267ee-102">Publish the location database from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="267ee-103">_**Última modificação do tópico:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="267ee-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="267ee-104">Os novos locais adicionados ao banco de dados de local não serão disponibilizados para o cliente até que sejam publicados.</span><span class="sxs-lookup"><span data-stu-id="267ee-104">The new locations that you added to the location database will not be made available to the client until they have been published.</span></span>

<span data-ttu-id="267ee-105">Para obter detalhes, consulte a documentação do Shell de gerenciamento do Lync Server para o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="267ee-105">For details, see the Lync Server Management Shell documentation for the following cmdlet:</span></span>

  - <span data-ttu-id="267ee-106">**Publish-CsLisConfiguration**</span><span class="sxs-lookup"><span data-stu-id="267ee-106">**Publish-CsLisConfiguration**</span></span>

<span data-ttu-id="267ee-107">Se você usar gateways do número de identificação de local de emergência (ELIN), também precisará carregar o ELINs para o banco de dados de identificação automática de local da sua operadora de rede telefônica pública comutada (ALI).</span><span class="sxs-lookup"><span data-stu-id="267ee-107">If you use Emergency Location Identification Number (ELIN) gateways, you also need to upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span> <span data-ttu-id="267ee-108">Sua operadora PSTN pode exigir que você use um formato específico para os registros do ELIN.</span><span class="sxs-lookup"><span data-stu-id="267ee-108">Your PSTN carrier may require you to use a specific format for the ELIN records.</span></span> <span data-ttu-id="267ee-109">Entre em contato com a operadora PSTN para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="267ee-109">Contact your PSTN carrier for details.</span></span> <span data-ttu-id="267ee-110">Você pode exportar os registros do banco de dados do serviço de informações de local e formatá-los conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="267ee-110">You can export the records from the Location Information service database and format them as required.</span></span>

<div>

## <a name="to-publish-the-location-database"></a><span data-ttu-id="267ee-111">Para publicar o banco de dados de local</span><span class="sxs-lookup"><span data-stu-id="267ee-111">To publish the location database</span></span>

  - <span data-ttu-id="267ee-112">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="267ee-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

  - <span data-ttu-id="267ee-113">Execute o cmdlet a seguir para publicar o banco de dados de localização.</span><span class="sxs-lookup"><span data-stu-id="267ee-113">Run the following cmdlet to publish the location database.</span></span>
    
        Publish-CsLisConfiguration

</div>

</div>

<span> </span>

</div>

</div>

</div>

