---
title: 'Lync Server 2013: Gerenciando locais para gateways do ELIN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing locations for ELIN gateways
ms:assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205288(v=OCS.15)
ms:contentKeyID: 48185496
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35c470b704e7467f573cd5e1fec03d63cf1f4b4e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043083"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-elin-gateways-in-lync-server-2013"></a><span data-ttu-id="a727a-102">Gerenciando locais para gateways do ELIN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a727a-102">Managing locations for ELIN gateways in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a727a-103">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="a727a-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="a727a-104">Para que o Lync Server forneça automaticamente locais para clientes dentro de uma rede, você precisa executar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="a727a-104">To have Lync Server automatically provide locations for clients within a network, you need to perform the following tasks:</span></span>

  - <span data-ttu-id="a727a-105">Preencha o banco de dados do serviço de informações de local com um Wiremap de rede e inclua os números de identificação de local de emergência (ELINs) no campo CompanyName.</span><span class="sxs-lookup"><span data-stu-id="a727a-105">Populate the Location Information service database with a network wiremap, and include the Emergency Location Identification Numbers (ELINs) in the CompanyName field.</span></span>

  - <span data-ttu-id="a727a-106">Publique as localizações, dessa forma, elas estarão disponíveis para os clientes da sua rede.</span><span class="sxs-lookup"><span data-stu-id="a727a-106">Publish the locations so that they are available for clients in your network.</span></span>

  - <span data-ttu-id="a727a-107">Carregue o ELINs para o banco de dados de identificação de local automática (ALI) da operadora de rede telefônica pública comutada (PSTN).</span><span class="sxs-lookup"><span data-stu-id="a727a-107">Upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span>

<span data-ttu-id="a727a-108">Para obter detalhes sobre como executar essas tarefas, consulte [Configure the Location Database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="a727a-108">For details about how to perform these tasks, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a727a-109">Os locais adicionados ao banco de dados de local central não estão disponíveis para o cliente até serem publicados usando um comando do Shell de gerenciamento do Lync Server e são replicados para os repositórios locais do pool.</span><span class="sxs-lookup"><span data-stu-id="a727a-109">Locations added to the central location database are not available to the client until they have been published by using a Lync Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="a727a-110">Para obter detalhes, consulte <A href="lync-server-2013-publish-the-location-database.md">publicar o banco de dados de localização no Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="a727a-110">For details, see <A href="lync-server-2013-publish-the-location-database.md">Publish the location database from Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="a727a-111">Essa seção descreve coisas a serem consideradas conforme você planeja atualizar e manter seu banco de dados de locais.</span><span class="sxs-lookup"><span data-stu-id="a727a-111">This section describes things to consider as you plan to update and maintain the location database.</span></span>

<div>

## <a name="planning-emergency-locations"></a><span data-ttu-id="a727a-112">Planejando locais de emergência</span><span class="sxs-lookup"><span data-stu-id="a727a-112">Planning Emergency Locations</span></span>

<span data-ttu-id="a727a-113">Ao usar os gateways do ELIN, você preenche o banco de dados do serviço de informações de local com o endereço cívico, um local específico dentro de um edifício e pelo menos um ELIN para cada local.</span><span class="sxs-lookup"><span data-stu-id="a727a-113">When you use ELIN gateways, you populate the Location Information service database with the civic address, a specific location within a building, and at least one ELIN for each location .</span></span> <span data-ttu-id="a727a-114">Durante a fase de planejamento, é uma boa ideia decidir como você deseja nomear as localizações e como deseja atribuir ELINs.</span><span class="sxs-lookup"><span data-stu-id="a727a-114">During the planning phase, it is a good idea to decide how you want to name the locations and how you want to assign ELINs.</span></span>

<div>

## <a name="planning-location-names"></a><span data-ttu-id="a727a-115">Planejando nomes dos locais</span><span class="sxs-lookup"><span data-stu-id="a727a-115">Planning Location Names</span></span>

<span data-ttu-id="a727a-116">O campo **local** do serviço de informações de local, que mantém o local específico dentro de um edifício, tem um comprimento máximo de 20 caracteres (incluindo espaços).</span><span class="sxs-lookup"><span data-stu-id="a727a-116">The Location Information service **Location** field, which holds the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="a727a-117">Dentro desse comprimento limitado, tente incluir o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a727a-117">Within that limited length, try to include the following:</span></span>

  - <span data-ttu-id="a727a-118">Um nome fácil de entender que identifica o local do chamador 911 para ajudar a garantir que os respondedores de emergência encontrem o local específico imediatamente quando chegarem ao endereço civil.</span><span class="sxs-lookup"><span data-stu-id="a727a-118">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address.</span></span> <span data-ttu-id="a727a-119">Esse nome de local pode incluir um número de edifício, um número de chão, um designador de asa, um número de sala e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="a727a-119">This location name may include a building number, floor number, wing designator, room number, and so on.</span></span> <span data-ttu-id="a727a-120">Evite apelidos que são conhecidos apenas por funcionários, que podem fazer com que os respondentes de emergência vá para o local errado.</span><span class="sxs-lookup"><span data-stu-id="a727a-120">Avoid nicknames that are known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

  - <span data-ttu-id="a727a-121">Um identificador de local que ajuda os usuários a ver facilmente que seu cliente do Lync obteve o local correto.</span><span class="sxs-lookup"><span data-stu-id="a727a-121">A location identifier that helps users to easily see that their Lync client picked up the correct location.</span></span> <span data-ttu-id="a727a-122">O cliente Lync concatena e exibe automaticamente os campos **Location** e **City** descobertos em seu cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="a727a-122">The Lync client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="a727a-123">Uma boa prática é adicionar o endereço de rua da construção a cada identificador de local (por exemplo, "número \<\>da rua do primeiro andar").</span><span class="sxs-lookup"><span data-stu-id="a727a-123">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor \<street number\>").</span></span> <span data-ttu-id="a727a-124">Sem o endereço físico, um identificador de local genérico como "1° andar" pode ser aplicado a qualquer construção na cidade.</span><span class="sxs-lookup"><span data-stu-id="a727a-124">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

  - <span data-ttu-id="a727a-125">Se o local for aproximado por ser determinado por um ponto de acesso sem fio, é possível adicionar uma palavra Near (por exemplo, "próximo ao 1º andar, 1234").</span><span class="sxs-lookup"><span data-stu-id="a727a-125">If the location is approximate because it’s determined by a wireless access point, you may want to add the word Near (for example, "Near 1st Floor 1234").</span></span>

</div>

<div>

## <a name="planning-elins"></a><span data-ttu-id="a727a-126">Planejando ELINs</span><span class="sxs-lookup"><span data-stu-id="a727a-126">Planning ELINs</span></span>

<span data-ttu-id="a727a-127">Depois de decidir como você deseja dividir o espaço de construção em locais, você precisa decidir quantas ELINs atribuir a cada local.</span><span class="sxs-lookup"><span data-stu-id="a727a-127">After you decide how you want to divide your building space into locations, you need to decide how many ELINs to assign to each location.</span></span> <span data-ttu-id="a727a-128">Por exemplo, em um prédio de multisolo ou de vários locatários, diferentes áreas no edifício podem ser atribuídas a diferentes zonas de emergência.</span><span class="sxs-lookup"><span data-stu-id="a727a-128">For example, in a multifloor or multitenant building, different areas in the building can be assigned different emergency zones.</span></span> <span data-ttu-id="a727a-129">Normalmente, cada andar de um edifício é designado como um local.</span><span class="sxs-lookup"><span data-stu-id="a727a-129">Typically, each floor in a building is designated as a location.</span></span> <span data-ttu-id="a727a-130">Em seguida, cada local é atribuído a um ou mais ELINs, que são usados como os números de chamada durante uma chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="a727a-130">Each location is then assigned one or more ELINs, which are used as the calling number(s) during an emergency call.</span></span> <span data-ttu-id="a727a-131">Entre em contato com a sua operadora da PSTN para números de telefone que você possa com ELIs.</span><span class="sxs-lookup"><span data-stu-id="a727a-131">Contact your PSTN carrier for phone numbers that you can use for ELINs.</span></span> <span data-ttu-id="a727a-132">A tabela a seguir fornece um exemplo de locais para um endereço de rua específico.</span><span class="sxs-lookup"><span data-stu-id="a727a-132">The following table provides an example of locations for a specific street address.</span></span>

### <a name="sample-location-and-elin-assignments"></a><span data-ttu-id="a727a-133">Exemplo de local e atribuições de ELIN</span><span class="sxs-lookup"><span data-stu-id="a727a-133">Sample Location and ELIN Assignments</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a727a-134">Área do edifício</span><span class="sxs-lookup"><span data-stu-id="a727a-134">Building Area</span></span></th>
<th><span data-ttu-id="a727a-135">Locais</span><span class="sxs-lookup"><span data-stu-id="a727a-135">Location</span></span></th>
<th><span data-ttu-id="a727a-136">ELIN</span><span class="sxs-lookup"><span data-stu-id="a727a-136">ELIN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a727a-137">1º andar</span><span class="sxs-lookup"><span data-stu-id="a727a-137">First floor</span></span></p></td>
<td><p><span data-ttu-id="a727a-138">1 </span><span class="sxs-lookup"><span data-stu-id="a727a-138">1</span></span></p></td>
<td><p><span data-ttu-id="a727a-139">425-555-0100</span><span class="sxs-lookup"><span data-stu-id="a727a-139">425-555-0100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a727a-140">2º andar</span><span class="sxs-lookup"><span data-stu-id="a727a-140">Second floor</span></span></p></td>
<td><p><span data-ttu-id="a727a-141">2 </span><span class="sxs-lookup"><span data-stu-id="a727a-141">2</span></span></p></td>
<td><p><span data-ttu-id="a727a-142">425-555-0111</span><span class="sxs-lookup"><span data-stu-id="a727a-142">425-555-0111</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a727a-143">3º andar</span><span class="sxs-lookup"><span data-stu-id="a727a-143">Third floor</span></span></p></td>
<td><p><span data-ttu-id="a727a-144">3 </span><span class="sxs-lookup"><span data-stu-id="a727a-144">3</span></span></p></td>
<td><p><span data-ttu-id="a727a-145">425-555-0123</span><span class="sxs-lookup"><span data-stu-id="a727a-145">425-555-0123</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a727a-146">Os locais definidos devem atender aos seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="a727a-146">The locations you define should meet the following requirements:</span></span>

  - <span data-ttu-id="a727a-147">Cumpra as regulamentações locais e nacionais/regionais em termos de área máxima por local e número de locais por endereço.</span><span class="sxs-lookup"><span data-stu-id="a727a-147">Comply with local and national/regional regulations in terms of maximum area per location and number of locations per street address.</span></span>

  - <span data-ttu-id="a727a-148">Sejam específicos o suficiente para tornar mais fácil localizar o chamador da emergância.</span><span class="sxs-lookup"><span data-stu-id="a727a-148">Are specific enough to make it easy to locate the emergency caller.</span></span>

</div>

</div>

<div>

## <a name="populating-the-location-database"></a><span data-ttu-id="a727a-149">Preenchimento do Banco de dados de locais</span><span class="sxs-lookup"><span data-stu-id="a727a-149">Populating the Location Database</span></span>

<span data-ttu-id="a727a-150">As perguntas a seguir o ajudarão a determinar como preencher o banco de dados de localização.</span><span class="sxs-lookup"><span data-stu-id="a727a-150">The following questions will help you determine how to will populate the location database.</span></span>

  - <span data-ttu-id="a727a-151">**Qual processo você usará para preencher o banco de dados de local?**</span><span class="sxs-lookup"><span data-stu-id="a727a-151">**What process will you use to populate the location database?**</span></span>  
    <span data-ttu-id="a727a-p107">Onde os dados existem e quais etapas você precisa executar para converter os dados para o formato necessário pelo banco de dados de local? Você adicionará locais individualmente ou em lote usando um arquivo CSV?</span><span class="sxs-lookup"><span data-stu-id="a727a-p107">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database? Will you add locations individually, or in bulk, by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="a727a-154">**Você tem um banco de dados de terceiros que já contém um mapeamento de locais?**</span><span class="sxs-lookup"><span data-stu-id="a727a-154">**Do you have a third party database that already contains a mapping of locations?**</span></span>  
    <span data-ttu-id="a727a-155">Usando a opção de serviço de informações de local secundário do Lync Server para se conectar a um banco de dados de terceiros, é possível agrupar e gerenciar locais usando uma plataforma offline.</span><span class="sxs-lookup"><span data-stu-id="a727a-155">By using Lync Server's Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="a727a-156">Um benefício dessa abordagem é que além de associar locais aos identificadores de rede, é possível associar locais a um usuário.</span><span class="sxs-lookup"><span data-stu-id="a727a-156">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="a727a-157">Isso significa que o serviço de informações de local pode retornar vários endereços, originários do serviço de informações de local secundário, para um cliente do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a727a-157">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Lync Server client.</span></span> <span data-ttu-id="a727a-158">Em seguida, o usuário pode escolher o local mais apropriado.</span><span class="sxs-lookup"><span data-stu-id="a727a-158">The user can then choose the most appropriate location.</span></span>
    
    <span data-ttu-id="a727a-159">Para integrar com o serviço de informações de local, o banco de dados de terceiros deve seguir o esquema de solicitação/resposta de local do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a727a-159">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="a727a-160">Para obter detalhes, <http://go.microsoft.com/fwlink/p/?linkid=213819>consulte.</span><span class="sxs-lookup"><span data-stu-id="a727a-160">For details, see <http://go.microsoft.com/fwlink/p/?linkid=213819>.</span></span> <span data-ttu-id="a727a-161">Para obter detalhes sobre a implantação de um serviço de informações de local secundário, consulte [configurar um serviço de informações de local secundário no Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="a727a-161">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="a727a-162">Para obter detalhes sobre como preencher o banco de dados de local, consulte [Configure the Location Database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="a727a-162">For details about populating the location database, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="a727a-163">Manutenção do banco de dados Local</span><span class="sxs-lookup"><span data-stu-id="a727a-163">Maintaining the Location Database</span></span>

<span data-ttu-id="a727a-p110">Depois de preencher o banco de dados de local, é necessário desenvolver uma estratégia para atualização do banco de dados à medida que a configuração de rede muda. As seguintes perguntas ajudarão a determinar como você manterá o banco de dados de local.</span><span class="sxs-lookup"><span data-stu-id="a727a-p110">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes. The following questions will help you determine how to maintain the location database.</span></span>

  - <span data-ttu-id="a727a-166">**Como você atualizará o banco de dados de local?**</span><span class="sxs-lookup"><span data-stu-id="a727a-166">**How will you update the location database?**</span></span>  
    <span data-ttu-id="a727a-167">Há vários cenários que exigem uma atualização para o banco de dados de local, incluindo a adição de pontos de acesso sem fio (WAPs), recabeamento do Office (resultando em diferentes atribuições de comutação) e expansão de sub-rede.</span><span class="sxs-lookup"><span data-stu-id="a727a-167">There are several scenarios that require an update to the location database, including adding wireless access points (WAPs), office recabling (resulting in different switch assignments), and subnet expansion.</span></span> <span data-ttu-id="a727a-168">Você atualizará diretamente cada local individual ou realizará uma atualização em massa de todos os locais usando um arquivo CSV?</span><span class="sxs-lookup"><span data-stu-id="a727a-168">Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="a727a-169">**Você usará um aplicativo SNMP para corresponder a endereços MAC do cliente do Lync a identificadores de porta e de comutador?**</span><span class="sxs-lookup"><span data-stu-id="a727a-169">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>  
    <span data-ttu-id="a727a-170">Se você usar um aplicativo SNMP, precisará desenvolver um processo manual para manter as informações de chassi de comutador e de porta consistentes entre o aplicativo SNMP e o banco de dados de local.</span><span class="sxs-lookup"><span data-stu-id="a727a-170">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="a727a-171">Se o aplicativo SNMP retornar um endereço IP de chassi ou uma ID de porta que não esteja incluída no banco de dados, o serviço de informações de local não poderá retornar um local ao cliente.</span><span class="sxs-lookup"><span data-stu-id="a727a-171">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

