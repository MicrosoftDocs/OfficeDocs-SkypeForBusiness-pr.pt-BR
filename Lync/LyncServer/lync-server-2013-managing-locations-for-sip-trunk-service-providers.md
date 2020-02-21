---
title: 'Lync Server 2013: Gerenciando locais para provedores de serviço de tronco SIP'
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
ms.openlocfilehash: f27eeac11006eab2209bb5491d991a677e3a2887
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42218077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-sip-trunk-service-providers-in-lync-server-2013"></a><span data-ttu-id="e62ee-102">Gerenciando locais para provedores de serviço de tronco SIP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e62ee-102">Managing locations for SIP trunk service providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e62ee-103">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="e62ee-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e62ee-104">Para configurar o Lync Server para localizar automaticamente clientes dentro de uma rede, você precisa preencher o banco de dados do serviço de informações de local com um Wiremap de rede e publicar os locais ou vincular a um banco de dados externo que já contém o mapeamentos.</span><span class="sxs-lookup"><span data-stu-id="e62ee-104">To configure Lync Server to automatically locate clients within a network, you need to either populate the Location Information service database with a network wiremap and publish the locations, or link to an external database that already contains the correct mappings.</span></span> <span data-ttu-id="e62ee-105">Como parte desse processo, é necessário validar os endereços cívicos dos locais com seu provedor de serviço de E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="e62ee-105">As part of this process, you need to validate the civic addresses of the locations with your E9-1-1 service provider.</span></span> <span data-ttu-id="e62ee-106">Para obter detalhes, consulte [Configure the Location Database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="e62ee-106">For details, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

<span data-ttu-id="e62ee-107">Você preenche o banco de dados de serviço de Informação de Local com um Local de Resposta de Emergência (ERL), que consiste de um endereço civil e o endereço específico dentro de uma construção.</span><span class="sxs-lookup"><span data-stu-id="e62ee-107">You populate the Location Information service database with an Emergency Response Location (ERL), which consists of a civic address and the specific address within a building.</span></span> <span data-ttu-id="e62ee-108">O campo **local** do serviço de informações de local, que é o local específico dentro de um edifício, tem um comprimento máximo de 20 caracteres (incluindo espaços).</span><span class="sxs-lookup"><span data-stu-id="e62ee-108">The Location Information service **Location** field, which is the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="e62ee-109">Dentro desse comprimento limitado, tente incluir o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e62ee-109">Within that limited length, try to include the following:</span></span>

  - <span data-ttu-id="e62ee-p103">Forneça um nome fácil de entender que identifica o local do chamador de 911 para garantir que os respondentes de emergência encontrem a localização específica prontamente, assim que eles chegarem ao endereço residencial. Esse nome de local pode incluir um número de edifício, número do andar, designador de ala, número do quarto, etc. Evite usar apelidos que apenas os funcionários conheçam, pois isso pode fazer com que os respondentes de emergência cheguem ao local errado.</span><span class="sxs-lookup"><span data-stu-id="e62ee-p103">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address. This location name may include a building number, floor number, wing designator, room number, and so on. Avoid nicknames known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

  - <span data-ttu-id="e62ee-113">Um identificador de local que ajuda os usuários a ver facilmente que seu cliente do Lync obteve o local correto.</span><span class="sxs-lookup"><span data-stu-id="e62ee-113">A location identifier that helps users to easily see that their Lync client picked up the correct location.</span></span> <span data-ttu-id="e62ee-114">O cliente Lync concatena e exibe automaticamente os campos **Location** e **City** descobertos em seu cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="e62ee-114">The Lync client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="e62ee-115">Uma boa prática é adicionar o endereço de rua da construção a cada identificador de local (por exemplo, "número \<\>da rua do primeiro andar").</span><span class="sxs-lookup"><span data-stu-id="e62ee-115">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor \<street number\>").</span></span> <span data-ttu-id="e62ee-116">Sem o endereço físico, um identificador de local genérico como "1° andar" pode ser aplicado a qualquer construção na cidade.</span><span class="sxs-lookup"><span data-stu-id="e62ee-116">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

  - <span data-ttu-id="e62ee-117">Se o local for aproximado por ser determinado por um ponto de acesso sem fio, convém adicionar a palavra Near (por exemplo, "próximo ao 1º andar, 1234").</span><span class="sxs-lookup"><span data-stu-id="e62ee-117">If the location is approximate because it’s determined by a wireless access point, you can add the word Near (for example, "Near 1st Floor 1234").</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e62ee-118">Os locais adicionados ao banco de dados de local central não estão disponíveis para o cliente até serem publicados usando um comando do Shell de gerenciamento do Lync Server e são replicados para os repositórios locais do pool.</span><span class="sxs-lookup"><span data-stu-id="e62ee-118">Locations added to the central location database are not available to the client until they are published by using a Lync Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="e62ee-119">Para obter detalhes, consulte <A href="lync-server-2013-publish-the-location-database.md">publicar o banco de dados de localização no Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="e62ee-119">For details, see <A href="lync-server-2013-publish-the-location-database.md">Publish the location database from Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="e62ee-120">As seções a seguir discutem as considerações que devem ser analisadas ao preencher e manter o banco de dados de local.</span><span class="sxs-lookup"><span data-stu-id="e62ee-120">The following sections discuss considerations that you need to take into account when populating and maintaining the location database.</span></span>

<div>

## <a name="populating-the-location-database"></a><span data-ttu-id="e62ee-121">Preenchendo o banco de dados Local</span><span class="sxs-lookup"><span data-stu-id="e62ee-121">Populating the Location Database</span></span>

<span data-ttu-id="e62ee-122">As seguintes perguntas podem ajudar a determinar como você preencherá o banco de dados de local.</span><span class="sxs-lookup"><span data-stu-id="e62ee-122">The following questions can help you determine how to populate the location database.</span></span>

  - <span data-ttu-id="e62ee-123">**Qual processo você usará para preencher o banco de dados de local?**</span><span class="sxs-lookup"><span data-stu-id="e62ee-123">**What process will you use to populate the location database?**</span></span>  
    <span data-ttu-id="e62ee-p106">Onde os dados existem e quais etapas você precisa executar para converter os dados para o formato necessário pelo banco de dados de local? Você adicionará locais individualmente ou em lote usando um arquivo CSV?</span><span class="sxs-lookup"><span data-stu-id="e62ee-p106">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database? Will you add locations individually, or in bulk, by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="e62ee-126">**Você tem um banco de dados de terceiros que já contém um mapeamento de locais?**</span><span class="sxs-lookup"><span data-stu-id="e62ee-126">**Do you have a third party database that already contains a mapping of locations?**</span></span>  
    <span data-ttu-id="e62ee-127">Usando a opção de serviço de informações de local secundário do Lync Server para se conectar a um banco de dados de terceiros, é possível agrupar e gerenciar locais usando uma plataforma offline.</span><span class="sxs-lookup"><span data-stu-id="e62ee-127">By using Lync Server's Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="e62ee-128">Um benefício dessa abordagem é que além de associar locais aos identificadores de rede, é possível associar locais a um usuário.</span><span class="sxs-lookup"><span data-stu-id="e62ee-128">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="e62ee-129">Isso significa que o serviço de informações de local pode retornar vários endereços, originários do serviço de informações de local secundário, para um cliente do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e62ee-129">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Lync Server client.</span></span> <span data-ttu-id="e62ee-130">Em seguida, o usuário pode escolher o local mais apropriado.</span><span class="sxs-lookup"><span data-stu-id="e62ee-130">The user can then choose the most appropriate location.</span></span>
    
    <span data-ttu-id="e62ee-131">Para integrar com o serviço de informações de local, o banco de dados de terceiros deve seguir o esquema de solicitação/resposta de local do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e62ee-131">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="e62ee-132">Para obter detalhes, consulte\["MS-\]E911WS: Web Service for E911 support Protocol Specification" <https://go.microsoft.com/fwlink/p/?linkid=213819>em.</span><span class="sxs-lookup"><span data-stu-id="e62ee-132">For details, see "\[MS-E911WS\]: Web Service for E911 Support Protocol Specification" at <https://go.microsoft.com/fwlink/p/?linkid=213819>.</span></span> <span data-ttu-id="e62ee-133">Para obter detalhes sobre a implantação de um serviço de informações de local secundário, consulte [configurar um serviço de informações de local secundário no Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="e62ee-133">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="e62ee-134">Para obter detalhes sobre como preencher o banco de dados de local, consulte [Configure the Location Database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="e62ee-134">For details about populating the location database, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="e62ee-135">Manutenção do banco de dados Local</span><span class="sxs-lookup"><span data-stu-id="e62ee-135">Maintaining the Location Database</span></span>

<span data-ttu-id="e62ee-p109">Depois de preencher o banco de dados de local, é necessário desenvolver uma estratégia para atualização do banco de dados à medida que a configuração de rede muda. As seguintes perguntas ajudarão a determinar como você manterá o banco de dados de local.</span><span class="sxs-lookup"><span data-stu-id="e62ee-p109">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes. The following questions will help you determine how to maintain the location database.</span></span>

  - <span data-ttu-id="e62ee-138">**Como você atualizará o banco de dados de local?**</span><span class="sxs-lookup"><span data-stu-id="e62ee-138">**How will you update the location database?**</span></span>  
    <span data-ttu-id="e62ee-p110">Há diversos cenários que exigem uma atualização para o banco de dados de local, incluindo a adição de WAPs, recabeamento do escritório (resultando em atribuições de comutação diferentes) e expansão da subrede. Você atualizará diretamente cada local individual ou realizará uma atualização em massa de todos os locais usando um arquivo CSV?</span><span class="sxs-lookup"><span data-stu-id="e62ee-p110">There are several scenarios that require an update to the location database, including adding WAPs, office recabling (resulting in different switch assignments), and subnet expansion. Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="e62ee-141">**Você usará um aplicativo SNMP para corresponder a endereços do MAC do cliente do Lync a identificadores de porta e de comutador?**</span><span class="sxs-lookup"><span data-stu-id="e62ee-141">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>  
    <span data-ttu-id="e62ee-142">Se você usar um aplicativo SNMP, precisará desenvolver um processo manual para manter as informações de chassi de comutador e de porta consistentes entre o aplicativo SNMP e o banco de dados de local.</span><span class="sxs-lookup"><span data-stu-id="e62ee-142">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="e62ee-143">Se o aplicativo SNMP retornar um endereço IP de chassi ou uma ID de porta que não esteja incluída no banco de dados, o serviço de informações de local não poderá retornar um local ao cliente.</span><span class="sxs-lookup"><span data-stu-id="e62ee-143">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

