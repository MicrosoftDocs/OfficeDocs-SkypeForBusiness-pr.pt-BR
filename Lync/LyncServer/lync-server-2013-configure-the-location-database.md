---
title: 'Lync Server 2013: configurar o banco de dados de localização'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the location database
ms:assetid: 8544be31-6958-47ef-b926-fdc80d56191c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398679(v=OCS.15)
ms:contentKeyID: 48184704
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2b15f0c679e9380a1f1a624f00f6c19384878fd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-location-database-in-lync-server-2013"></a><span data-ttu-id="7fb5e-102">Configure the location database in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fb5e-102">Configure the location database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7fb5e-103">_**Tópico da última modificação:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="7fb5e-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="7fb5e-104">Para que os clientes possam detectar automaticamente seu local na rede, primeiro configure o banco de dados de localização.</span><span class="sxs-lookup"><span data-stu-id="7fb5e-104">To enable clients to automatically detect their location within a network, you first need to configure the location database.</span></span> <span data-ttu-id="7fb5e-105">Se você não configurar um banco de dados de local e a **localização necessária** na política de localização estiver definida como **Sim** ou **isenção de responsabilidade**, o usuário será solicitado a inserir um local manualmente.</span><span class="sxs-lookup"><span data-stu-id="7fb5e-105">If you do not configure a location database, and **Location Required** in the location policy is set to **Yes** or **Disclaimer**, the user will be prompted to manually enter a location.</span></span>

<span data-ttu-id="7fb5e-106">Para configurar o banco de dados de localização, você executará as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="7fb5e-106">To configure the location database, you will perform the following tasks:</span></span>

1.  <span data-ttu-id="7fb5e-107">Preencha o banco de dados com um mapeamento de elementos de rede para os locais.</span><span class="sxs-lookup"><span data-stu-id="7fb5e-107">Populate the database with a mapping of network elements to locations.</span></span> <span data-ttu-id="7fb5e-108">Se você usar um gateway de número de identificação de localização de emergência (ELIN), precisará incluir o \<Elin\> no campo CompanyName.</span><span class="sxs-lookup"><span data-stu-id="7fb5e-108">If you use an Emergency Location Identification Number (ELIN) gateway, you need to include the ELIN in the \<CompanyName\> field.</span></span>

2.  <span data-ttu-id="7fb5e-109">Valide os endereços em relação ao MSAG (catálogo de endereços principal) mantido pelo provedor de serviços de emergência.</span><span class="sxs-lookup"><span data-stu-id="7fb5e-109">Validate the addresses against the master street address guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span>

3.  <span data-ttu-id="7fb5e-110">Publique o banco de dados atualizado.</span><span class="sxs-lookup"><span data-stu-id="7fb5e-110">Publish the updated database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7fb5e-111">Como alternativa, você pode definir um banco de dados de origem de local secundário que pode ser usado no banco de dados de localização.</span><span class="sxs-lookup"><span data-stu-id="7fb5e-111">Alternately, you can define a secondary location source database that can be used in placed of the location database.</span></span> <span data-ttu-id="7fb5e-112">Para obter detalhes, consulte <A href="lync-server-2013-configure-a-secondary-location-information-service.md">configurar um serviço de informações de localização secundário no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7fb5e-112">For details, see <A href="lync-server-2013-configure-a-secondary-location-information-service.md">Configure a secondary Location Information service in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7fb5e-113">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="7fb5e-113">In This Section</span></span>

  - [<span data-ttu-id="7fb5e-114">Preencher o banco de dados de localização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fb5e-114">Populate the location database in Lync Server 2013</span></span>](lync-server-2013-populate-the-location-database.md)

  - [<span data-ttu-id="7fb5e-115">Validar endereços no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fb5e-115">Validate addresses in Lync Server 2013</span></span>](lync-server-2013-validate-addresses.md)

  - [<span data-ttu-id="7fb5e-116">Publicar o banco de dados de localização do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fb5e-116">Publish the location database from Lync Server 2013</span></span>](lync-server-2013-publish-the-location-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

