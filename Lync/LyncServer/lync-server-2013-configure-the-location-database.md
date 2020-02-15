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
ms.openlocfilehash: f79587526172c7ccade1b74574b20657d1a82300
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043203"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-location-database-in-lync-server-2013"></a><span data-ttu-id="ccec7-102">Configurar o banco de dados de localização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccec7-102">Configure the location database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ccec7-103">_**Última modificação do tópico:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="ccec7-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="ccec7-p101">Para que os clientes possam detectar automaticamente seu local na rede, primeiro configure o banco de dados de localização. Se você não configurar o banco de dados de localização e o **Local obrigatório** na política de local for definido como **Sim** ou **Aviso de isenção de responsabilidade**, o sistema solicitará que o usuário insira um local manualmente.</span><span class="sxs-lookup"><span data-stu-id="ccec7-p101">To enable clients to automatically detect their location within a network, you first need to configure the location database. If you do not configure a location database, and **Location Required** in the location policy is set to **Yes** or **Disclaimer**, the user will be prompted to manually enter a location.</span></span>

<span data-ttu-id="ccec7-106">Para configurar o banco de dados local, você executará as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="ccec7-106">To configure the location database, you will perform the following tasks:</span></span>

1.  <span data-ttu-id="ccec7-107">Preencha o banco de dados com um mapeamento dos locais para os elementos de rede.</span><span class="sxs-lookup"><span data-stu-id="ccec7-107">Populate the database with a mapping of network elements to locations.</span></span> <span data-ttu-id="ccec7-108">Se você usar um gateway ELIN (número de identificação de local de emergência), precisará incluir o ELIN \<no\> campo CompanyName.</span><span class="sxs-lookup"><span data-stu-id="ccec7-108">If you use an Emergency Location Identification Number (ELIN) gateway, you need to include the ELIN in the \<CompanyName\> field.</span></span>

2.  <span data-ttu-id="ccec7-109">Valide os endereços em relação ao MSAG (catálogo de endereços principal) mantido pelo provedor de serviços de emergência.</span><span class="sxs-lookup"><span data-stu-id="ccec7-109">Validate the addresses against the master street address guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span>

3.  <span data-ttu-id="ccec7-110">Publicar o banco de dados atualizado.</span><span class="sxs-lookup"><span data-stu-id="ccec7-110">Publish the updated database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ccec7-111">Como alternativa, você pode definir um banco de dados de origem do local secundário, que pode ser usado em vez do banco de dados local.</span><span class="sxs-lookup"><span data-stu-id="ccec7-111">Alternately, you can define a secondary location source database that can be used in placed of the location database.</span></span> <span data-ttu-id="ccec7-112">Para obter detalhes, consulte <A href="lync-server-2013-configure-a-secondary-location-information-service.md">configurar um serviço de informações de local secundário no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ccec7-112">For details, see <A href="lync-server-2013-configure-a-secondary-location-information-service.md">Configure a secondary Location Information service in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ccec7-113">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="ccec7-113">In This Section</span></span>

  - [<span data-ttu-id="ccec7-114">Preencher o banco de dados de localização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccec7-114">Populate the location database in Lync Server 2013</span></span>](lync-server-2013-populate-the-location-database.md)

  - [<span data-ttu-id="ccec7-115">Validar endereços no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccec7-115">Validate addresses in Lync Server 2013</span></span>](lync-server-2013-validate-addresses.md)

  - [<span data-ttu-id="ccec7-116">Publicar o banco de dados de localização do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccec7-116">Publish the location database from Lync Server 2013</span></span>](lync-server-2013-publish-the-location-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

