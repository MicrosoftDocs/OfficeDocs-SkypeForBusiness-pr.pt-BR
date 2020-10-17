---
title: 'Lync Server 2013: Gerenciando locais para provedores de serviço de tronco SIP'
description: 'Lync Server 2013: Gerenciando locais para provedores de serviço de tronco SIP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing locations for SIP trunk service providers
ms:assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398959(v=OCS.15)
ms:contentKeyID: 48185548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 062c55f6e8484121c91b28f4926e37f85a25c0a7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545187"
---
# <a name="managing-locations-for-sip-trunk-service-providers-in-lync-server-2013"></a><span data-ttu-id="46d1f-103">Gerenciando locais para provedores de serviço de tronco SIP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46d1f-103">Managing locations for SIP trunk service providers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46d1f-104">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="46d1f-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="46d1f-105">Para configurar o Lync Server para localizar automaticamente clientes dentro de uma rede, você precisa preencher o banco de dados do serviço de informações de local com um Wiremap de rede e publicar os locais ou vincular a um banco de dados externo que já contém os mapeamentos corretos.</span><span class="sxs-lookup"><span data-stu-id="46d1f-105">To configure Lync Server to automatically locate clients within a network, you need to either populate the Location Information service database with a network wiremap and publish the locations, or link to an external database that already contains the correct mappings.</span></span> <span data-ttu-id="46d1f-106">Como parte desse processo, é necessário validar os endereços cívicos dos locais com seu provedor de serviço de E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="46d1f-106">As part of this process, you need to validate the civic addresses of the locations with your E9-1-1 service provider.</span></span> <span data-ttu-id="46d1f-107">Para obter detalhes, consulte [Configure the Location Database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="46d1f-107">For details, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

<span data-ttu-id="46d1f-108">Você preenche o banco de dados de serviço de Informação de Local com um Local de Resposta de Emergência (ERL), que consiste de um endereço civil e o endereço específico dentro de uma construção.</span><span class="sxs-lookup"><span data-stu-id="46d1f-108">You populate the Location Information service database with an Emergency Response Location (ERL), which consists of a civic address and the specific address within a building.</span></span> <span data-ttu-id="46d1f-109">O campo **local** do serviço de informações de local, que é o local específico dentro de um edifício, tem um comprimento máximo de 20 caracteres (incluindo espaços).</span><span class="sxs-lookup"><span data-stu-id="46d1f-109">The Location Information service **Location** field, which is the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="46d1f-110">Dentro desse comprimento limitado, tente incluir o seguinte:</span><span class="sxs-lookup"><span data-stu-id="46d1f-110">Within that limited length, try to include the following:</span></span>

  - <span data-ttu-id="46d1f-p103">Forneça um nome fácil de entender que identifica o local do chamador de 911 para garantir que os respondentes de emergência encontrem a localização específica prontamente, assim que eles chegarem ao endereço residencial. Esse nome de local pode incluir um número de edifício, número do andar, designador de ala, número do quarto, etc. Evite usar apelidos que apenas os funcionários conheçam, pois isso pode fazer com que os respondentes de emergência cheguem ao local errado.</span><span class="sxs-lookup"><span data-stu-id="46d1f-p103">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address. This location name may include a building number, floor number, wing designator, room number, and so on. Avoid nicknames known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

  - <span data-ttu-id="46d1f-114">Um identificador de local que ajuda os usuários a ver facilmente que seu cliente do Lync obteve o local correto.</span><span class="sxs-lookup"><span data-stu-id="46d1f-114">A location identifier that helps users to easily see that their Lync client picked up the correct location.</span></span> <span data-ttu-id="46d1f-115">O cliente Lync concatena e exibe automaticamente os campos **Location** e **City** descobertos em seu cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="46d1f-115">The Lync client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="46d1f-116">Uma boa prática é adicionar o endereço de rua da construção a cada identificador de local (por exemplo, "primeiro andar \<street number\> ").</span><span class="sxs-lookup"><span data-stu-id="46d1f-116">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor \<street number\>").</span></span> <span data-ttu-id="46d1f-117">Sem o endereço físico, um identificador de local genérico como "1° andar" pode ser aplicado a qualquer construção na cidade.</span><span class="sxs-lookup"><span data-stu-id="46d1f-117">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

  - <span data-ttu-id="46d1f-118">Se o local for aproximado por ser determinado por um ponto de acesso sem fio, convém adicionar a palavra Near (por exemplo, "próximo ao 1º andar, 1234").</span><span class="sxs-lookup"><span data-stu-id="46d1f-118">If the location is approximate because it’s determined by a wireless access point, you can add the word Near (for example, "Near 1st Floor 1234").</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="46d1f-119">Os locais adicionados ao banco de dados de local central não estão disponíveis para o cliente até serem publicados usando um comando do Shell de gerenciamento do Lync Server e são replicados para os repositórios locais do pool.</span><span class="sxs-lookup"><span data-stu-id="46d1f-119">Locations added to the central location database are not available to the client until they are published by using a Lync Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="46d1f-120">Para obter detalhes, consulte <A href="lync-server-2013-publish-the-location-database.md">publicar o banco de dados de localização no Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="46d1f-120">For details, see <A href="lync-server-2013-publish-the-location-database.md">Publish the location database from Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="46d1f-121">As seções a seguir discutem as considerações que devem ser analisadas ao preencher e manter o banco de dados de local.</span><span class="sxs-lookup"><span data-stu-id="46d1f-121">The following sections discuss considerations that you need to take into account when populating and maintaining the location database.</span></span>

<div>

## <a name="populating-the-location-database"></a><span data-ttu-id="46d1f-122">Preenchendo o banco de dados Local</span><span class="sxs-lookup"><span data-stu-id="46d1f-122">Populating the Location Database</span></span>

<span data-ttu-id="46d1f-123">As seguintes perguntas podem ajudar a determinar como você preencherá o banco de dados de local.</span><span class="sxs-lookup"><span data-stu-id="46d1f-123">The following questions can help you determine how to populate the location database.</span></span>

  - <span data-ttu-id="46d1f-124">**Qual processo você usará para preencher o banco de dados de local?**</span><span class="sxs-lookup"><span data-stu-id="46d1f-124">**What process will you use to populate the location database?**</span></span>  
    <span data-ttu-id="46d1f-p106">Onde os dados existem e quais etapas você precisa executar para converter os dados para o formato necessário pelo banco de dados de local? Você adicionará locais individualmente ou em lote usando um arquivo CSV?</span><span class="sxs-lookup"><span data-stu-id="46d1f-p106">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database? Will you add locations individually, or in bulk, by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="46d1f-127">**Você tem um banco de dados de terceiros que já contém um mapeamento de locais?**</span><span class="sxs-lookup"><span data-stu-id="46d1f-127">**Do you have a third party database that already contains a mapping of locations?**</span></span>  
    <span data-ttu-id="46d1f-128">Usando a opção de serviço de informações de local secundário do Lync Server para se conectar a um banco de dados de terceiros, é possível agrupar e gerenciar locais usando uma plataforma offline.</span><span class="sxs-lookup"><span data-stu-id="46d1f-128">By using Lync Server's Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="46d1f-129">Um benefício dessa abordagem é que além de associar locais aos identificadores de rede, é possível associar locais a um usuário.</span><span class="sxs-lookup"><span data-stu-id="46d1f-129">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="46d1f-130">Isso significa que o serviço de informações de local pode retornar vários endereços, originários do serviço de informações de local secundário, para um cliente do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="46d1f-130">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Lync Server client.</span></span> <span data-ttu-id="46d1f-131">Em seguida, o usuário pode escolher o local mais apropriado.</span><span class="sxs-lookup"><span data-stu-id="46d1f-131">The user can then choose the most appropriate location.</span></span>
    
    <span data-ttu-id="46d1f-132">Para integrar com o serviço de informações de local, o banco de dados de terceiros deve seguir o esquema de solicitação/resposta de local do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="46d1f-132">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="46d1f-133">Para obter detalhes, consulte " \[ MS-E911WS \] : Web Service for E911 support Protocol Specification" em <https://go.microsoft.com/fwlink/p/?linkid=213819> .</span><span class="sxs-lookup"><span data-stu-id="46d1f-133">For details, see "\[MS-E911WS\]: Web Service for E911 Support Protocol Specification" at <https://go.microsoft.com/fwlink/p/?linkid=213819>.</span></span> <span data-ttu-id="46d1f-134">Para obter detalhes sobre a implantação de um serviço de informações de local secundário, consulte [configurar um serviço de informações de local secundário no Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="46d1f-134">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="46d1f-135">Para obter detalhes sobre como preencher o banco de dados de local, consulte [Configure the Location Database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="46d1f-135">For details about populating the location database, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="46d1f-136">Manutenção do banco de dados Local</span><span class="sxs-lookup"><span data-stu-id="46d1f-136">Maintaining the Location Database</span></span>

<span data-ttu-id="46d1f-p109">Depois de preencher o banco de dados de local, é necessário desenvolver uma estratégia para atualização do banco de dados à medida que a configuração de rede muda. As seguintes perguntas ajudarão a determinar como você manterá o banco de dados de local.</span><span class="sxs-lookup"><span data-stu-id="46d1f-p109">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes. The following questions will help you determine how to maintain the location database.</span></span>

  - <span data-ttu-id="46d1f-139">**Como você atualizará o banco de dados de local?**</span><span class="sxs-lookup"><span data-stu-id="46d1f-139">**How will you update the location database?**</span></span>  
    <span data-ttu-id="46d1f-p110">Há diversos cenários que exigem uma atualização para o banco de dados de local, incluindo a adição de WAPs, recabeamento do escritório (resultando em atribuições de comutação diferentes) e expansão da subrede. Você atualizará diretamente cada local individual ou realizará uma atualização em massa de todos os locais usando um arquivo CSV?</span><span class="sxs-lookup"><span data-stu-id="46d1f-p110">There are several scenarios that require an update to the location database, including adding WAPs, office recabling (resulting in different switch assignments), and subnet expansion. Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="46d1f-142">**Você usará um aplicativo SNMP para corresponder a endereços do MAC do cliente do Lync a identificadores de porta e de comutador?**</span><span class="sxs-lookup"><span data-stu-id="46d1f-142">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>  
    <span data-ttu-id="46d1f-143">Se você usar um aplicativo SNMP, precisará desenvolver um processo manual para manter as informações de chassi de comutador e de porta consistentes entre o aplicativo SNMP e o banco de dados de local.</span><span class="sxs-lookup"><span data-stu-id="46d1f-143">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="46d1f-144">Se o aplicativo SNMP retornar um endereço IP de chassi ou uma ID de porta que não esteja incluída no banco de dados, o serviço de informações de local não poderá retornar um local ao cliente.</span><span class="sxs-lookup"><span data-stu-id="46d1f-144">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

