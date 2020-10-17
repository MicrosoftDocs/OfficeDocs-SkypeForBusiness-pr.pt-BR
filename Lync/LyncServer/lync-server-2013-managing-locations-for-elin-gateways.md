---
title: 'Lync Server 2013: Gerenciando locais para gateways do ELIN'
description: 'Lync Server 2013: Gerenciando locais para gateways do ELIN.'
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
ms.openlocfilehash: 94fe7797c0f25adb219512cef4a6c0fb7d84b48d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557477"
---
# <a name="managing-locations-for-elin-gateways-in-lync-server-2013"></a><span data-ttu-id="23786-103">Gerenciando locais para gateways do ELIN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23786-103">Managing locations for ELIN gateways in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23786-104">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="23786-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="23786-105">Para que o Lync Server forneça automaticamente locais para clientes dentro de uma rede, você precisa executar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="23786-105">To have Lync Server automatically provide locations for clients within a network, you need to perform the following tasks:</span></span>

  - <span data-ttu-id="23786-106">Preencha o banco de dados do serviço de informações de local com um Wiremap de rede e inclua os números de identificação de local de emergência (ELINs) no campo CompanyName.</span><span class="sxs-lookup"><span data-stu-id="23786-106">Populate the Location Information service database with a network wiremap, and include the Emergency Location Identification Numbers (ELINs) in the CompanyName field.</span></span>

  - <span data-ttu-id="23786-107">Publique as localizações, dessa forma, elas estarão disponíveis para os clientes da sua rede.</span><span class="sxs-lookup"><span data-stu-id="23786-107">Publish the locations so that they are available for clients in your network.</span></span>

  - <span data-ttu-id="23786-108">Carregue o ELINs para o banco de dados de identificação de local automática (ALI) da operadora de rede telefônica pública comutada (PSTN).</span><span class="sxs-lookup"><span data-stu-id="23786-108">Upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span>

<span data-ttu-id="23786-109">Para obter detalhes sobre como executar essas tarefas, consulte [Configure the Location Database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="23786-109">For details about how to perform these tasks, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="23786-110">Os locais adicionados ao banco de dados de local central não estão disponíveis para o cliente até serem publicados usando um comando do Shell de gerenciamento do Lync Server e são replicados para os repositórios locais do pool.</span><span class="sxs-lookup"><span data-stu-id="23786-110">Locations added to the central location database are not available to the client until they have been published by using a Lync Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="23786-111">Para obter detalhes, consulte <A href="lync-server-2013-publish-the-location-database.md">publicar o banco de dados de localização no Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="23786-111">For details, see <A href="lync-server-2013-publish-the-location-database.md">Publish the location database from Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="23786-112">Essa seção descreve coisas a serem consideradas conforme você planeja atualizar e manter seu banco de dados de locais.</span><span class="sxs-lookup"><span data-stu-id="23786-112">This section describes things to consider as you plan to update and maintain the location database.</span></span>

<div>

## <a name="planning-emergency-locations"></a><span data-ttu-id="23786-113">Planejando locais de emergência</span><span class="sxs-lookup"><span data-stu-id="23786-113">Planning Emergency Locations</span></span>

<span data-ttu-id="23786-114">Ao usar os gateways do ELIN, você preenche o banco de dados do serviço de informações de local com o endereço cívico, um local específico dentro de um edifício e pelo menos um ELIN para cada local.</span><span class="sxs-lookup"><span data-stu-id="23786-114">When you use ELIN gateways, you populate the Location Information service database with the civic address, a specific location within a building, and at least one ELIN for each location .</span></span> <span data-ttu-id="23786-115">Durante a fase de planejamento, é uma boa ideia decidir como você deseja nomear as localizações e como deseja atribuir ELINs.</span><span class="sxs-lookup"><span data-stu-id="23786-115">During the planning phase, it is a good idea to decide how you want to name the locations and how you want to assign ELINs.</span></span>

<div>

## <a name="planning-location-names"></a><span data-ttu-id="23786-116">Planejando nomes dos locais</span><span class="sxs-lookup"><span data-stu-id="23786-116">Planning Location Names</span></span>

<span data-ttu-id="23786-117">O campo **local** do serviço de informações de local, que mantém o local específico dentro de um edifício, tem um comprimento máximo de 20 caracteres (incluindo espaços).</span><span class="sxs-lookup"><span data-stu-id="23786-117">The Location Information service **Location** field, which holds the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="23786-118">Dentro desse comprimento limitado, tente incluir o seguinte:</span><span class="sxs-lookup"><span data-stu-id="23786-118">Within that limited length, try to include the following:</span></span>

  - <span data-ttu-id="23786-119">Um nome fácil de entender que identifica o local do chamador 911 para ajudar a garantir que os respondedores de emergência encontrem o local específico imediatamente quando chegarem ao endereço civil.</span><span class="sxs-lookup"><span data-stu-id="23786-119">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address.</span></span> <span data-ttu-id="23786-120">Esse nome de local pode incluir um número de edifício, um número de chão, um designador de asa, um número de sala e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="23786-120">This location name may include a building number, floor number, wing designator, room number, and so on.</span></span> <span data-ttu-id="23786-121">Evite apelidos que são conhecidos apenas por funcionários, que podem fazer com que os respondentes de emergência vá para o local errado.</span><span class="sxs-lookup"><span data-stu-id="23786-121">Avoid nicknames that are known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

  - <span data-ttu-id="23786-122">Um identificador de local que ajuda os usuários a ver facilmente que seu cliente do Lync obteve o local correto.</span><span class="sxs-lookup"><span data-stu-id="23786-122">A location identifier that helps users to easily see that their Lync client picked up the correct location.</span></span> <span data-ttu-id="23786-123">O cliente Lync concatena e exibe automaticamente os campos **Location** e **City** descobertos em seu cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="23786-123">The Lync client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="23786-124">Uma boa prática é adicionar o endereço de rua da construção a cada identificador de local (por exemplo, "primeiro andar \<street number\> ").</span><span class="sxs-lookup"><span data-stu-id="23786-124">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor \<street number\>").</span></span> <span data-ttu-id="23786-125">Sem o endereço físico, um identificador de local genérico como "1° andar" pode ser aplicado a qualquer construção na cidade.</span><span class="sxs-lookup"><span data-stu-id="23786-125">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

  - <span data-ttu-id="23786-126">Se o local for aproximado por ser determinado por um ponto de acesso sem fio, é possível adicionar uma palavra Near (por exemplo, "próximo ao 1º andar, 1234").</span><span class="sxs-lookup"><span data-stu-id="23786-126">If the location is approximate because it’s determined by a wireless access point, you may want to add the word Near (for example, "Near 1st Floor 1234").</span></span>

</div>

<div>

## <a name="planning-elins"></a><span data-ttu-id="23786-127">Planejando ELINs</span><span class="sxs-lookup"><span data-stu-id="23786-127">Planning ELINs</span></span>

<span data-ttu-id="23786-128">Depois de decidir como você deseja dividir o espaço de construção em locais, você precisa decidir quantas ELINs atribuir a cada local.</span><span class="sxs-lookup"><span data-stu-id="23786-128">After you decide how you want to divide your building space into locations, you need to decide how many ELINs to assign to each location.</span></span> <span data-ttu-id="23786-129">Por exemplo, em um prédio de multisolo ou de vários locatários, diferentes áreas no edifício podem ser atribuídas a diferentes zonas de emergência.</span><span class="sxs-lookup"><span data-stu-id="23786-129">For example, in a multifloor or multitenant building, different areas in the building can be assigned different emergency zones.</span></span> <span data-ttu-id="23786-130">Normalmente, cada andar de um edifício é designado como um local.</span><span class="sxs-lookup"><span data-stu-id="23786-130">Typically, each floor in a building is designated as a location.</span></span> <span data-ttu-id="23786-131">Em seguida, cada local é atribuído a um ou mais ELINs, que são usados como os números de chamada durante uma chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="23786-131">Each location is then assigned one or more ELINs, which are used as the calling number(s) during an emergency call.</span></span> <span data-ttu-id="23786-132">Entre em contato com a sua operadora da PSTN para números de telefone que você possa com ELIs.</span><span class="sxs-lookup"><span data-stu-id="23786-132">Contact your PSTN carrier for phone numbers that you can use for ELINs.</span></span> <span data-ttu-id="23786-133">A tabela a seguir fornece um exemplo de locais para um endereço de rua específico.</span><span class="sxs-lookup"><span data-stu-id="23786-133">The following table provides an example of locations for a specific street address.</span></span>

### <a name="sample-location-and-elin-assignments"></a><span data-ttu-id="23786-134">Exemplo de local e atribuições de ELIN</span><span class="sxs-lookup"><span data-stu-id="23786-134">Sample Location and ELIN Assignments</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23786-135">Área do edifício</span><span class="sxs-lookup"><span data-stu-id="23786-135">Building Area</span></span></th>
<th><span data-ttu-id="23786-136">Local</span><span class="sxs-lookup"><span data-stu-id="23786-136">Location</span></span></th>
<th><span data-ttu-id="23786-137">ELIN</span><span class="sxs-lookup"><span data-stu-id="23786-137">ELIN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23786-138">1º andar</span><span class="sxs-lookup"><span data-stu-id="23786-138">First floor</span></span></p></td>
<td><p><span data-ttu-id="23786-139">1</span><span class="sxs-lookup"><span data-stu-id="23786-139">1</span></span></p></td>
<td><p><span data-ttu-id="23786-140">425-555-0100</span><span class="sxs-lookup"><span data-stu-id="23786-140">425-555-0100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23786-141">2º andar</span><span class="sxs-lookup"><span data-stu-id="23786-141">Second floor</span></span></p></td>
<td><p><span data-ttu-id="23786-142">duas</span><span class="sxs-lookup"><span data-stu-id="23786-142">2</span></span></p></td>
<td><p><span data-ttu-id="23786-143">425-555-0111</span><span class="sxs-lookup"><span data-stu-id="23786-143">425-555-0111</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23786-144">3º andar</span><span class="sxs-lookup"><span data-stu-id="23786-144">Third floor</span></span></p></td>
<td><p><span data-ttu-id="23786-145">3D</span><span class="sxs-lookup"><span data-stu-id="23786-145">3</span></span></p></td>
<td><p><span data-ttu-id="23786-146">425-555-0123</span><span class="sxs-lookup"><span data-stu-id="23786-146">425-555-0123</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="23786-147">Os locais definidos devem atender aos seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="23786-147">The locations you define should meet the following requirements:</span></span>

  - <span data-ttu-id="23786-148">Cumpra as regulamentações locais e nacionais/regionais em termos de área máxima por local e número de locais por endereço.</span><span class="sxs-lookup"><span data-stu-id="23786-148">Comply with local and national/regional regulations in terms of maximum area per location and number of locations per street address.</span></span>

  - <span data-ttu-id="23786-149">Sejam específicos o suficiente para tornar mais fácil localizar o chamador da emergância.</span><span class="sxs-lookup"><span data-stu-id="23786-149">Are specific enough to make it easy to locate the emergency caller.</span></span>

</div>

</div>

<div>

## <a name="populating-the-location-database"></a><span data-ttu-id="23786-150">Preenchimento do Banco de dados de locais</span><span class="sxs-lookup"><span data-stu-id="23786-150">Populating the Location Database</span></span>

<span data-ttu-id="23786-151">As perguntas a seguir o ajudarão a determinar como preencher o banco de dados de localização.</span><span class="sxs-lookup"><span data-stu-id="23786-151">The following questions will help you determine how to will populate the location database.</span></span>

  - <span data-ttu-id="23786-152">**Qual processo você usará para preencher o banco de dados de local?**</span><span class="sxs-lookup"><span data-stu-id="23786-152">**What process will you use to populate the location database?**</span></span>  
    <span data-ttu-id="23786-p107">Onde os dados existem e quais etapas você precisa executar para converter os dados para o formato necessário pelo banco de dados de local? Você adicionará locais individualmente ou em lote usando um arquivo CSV?</span><span class="sxs-lookup"><span data-stu-id="23786-p107">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database? Will you add locations individually, or in bulk, by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="23786-155">**Você tem um banco de dados de terceiros que já contém um mapeamento de locais?**</span><span class="sxs-lookup"><span data-stu-id="23786-155">**Do you have a third party database that already contains a mapping of locations?**</span></span>  
    <span data-ttu-id="23786-156">Usando a opção de serviço de informações de local secundário do Lync Server para se conectar a um banco de dados de terceiros, é possível agrupar e gerenciar locais usando uma plataforma offline.</span><span class="sxs-lookup"><span data-stu-id="23786-156">By using Lync Server's Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="23786-157">Um benefício dessa abordagem é que além de associar locais aos identificadores de rede, é possível associar locais a um usuário.</span><span class="sxs-lookup"><span data-stu-id="23786-157">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="23786-158">Isso significa que o serviço de informações de local pode retornar vários endereços, originários do serviço de informações de local secundário, para um cliente do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="23786-158">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Lync Server client.</span></span> <span data-ttu-id="23786-159">Em seguida, o usuário pode escolher o local mais apropriado.</span><span class="sxs-lookup"><span data-stu-id="23786-159">The user can then choose the most appropriate location.</span></span>
    
    <span data-ttu-id="23786-160">Para integrar com o serviço de informações de local, o banco de dados de terceiros deve seguir o esquema de solicitação/resposta de local do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="23786-160">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="23786-161">Para obter detalhes, consulte <https://go.microsoft.com/fwlink/p/?linkid=213819> .</span><span class="sxs-lookup"><span data-stu-id="23786-161">For details, see <https://go.microsoft.com/fwlink/p/?linkid=213819>.</span></span> <span data-ttu-id="23786-162">Para obter detalhes sobre a implantação de um serviço de informações de local secundário, consulte [configurar um serviço de informações de local secundário no Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="23786-162">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="23786-163">Para obter detalhes sobre como preencher o banco de dados de local, consulte [Configure the Location Database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="23786-163">For details about populating the location database, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="23786-164">Manutenção do banco de dados Local</span><span class="sxs-lookup"><span data-stu-id="23786-164">Maintaining the Location Database</span></span>

<span data-ttu-id="23786-p110">Depois de preencher o banco de dados de local, é necessário desenvolver uma estratégia para atualização do banco de dados à medida que a configuração de rede muda. As seguintes perguntas ajudarão a determinar como você manterá o banco de dados de local.</span><span class="sxs-lookup"><span data-stu-id="23786-p110">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes. The following questions will help you determine how to maintain the location database.</span></span>

  - <span data-ttu-id="23786-167">**Como você atualizará o banco de dados de local?**</span><span class="sxs-lookup"><span data-stu-id="23786-167">**How will you update the location database?**</span></span>  
    <span data-ttu-id="23786-168">Há vários cenários que exigem uma atualização para o banco de dados de local, incluindo a adição de pontos de acesso sem fio (WAPs), recabeamento do Office (resultando em diferentes atribuições de comutação) e expansão de sub-rede.</span><span class="sxs-lookup"><span data-stu-id="23786-168">There are several scenarios that require an update to the location database, including adding wireless access points (WAPs), office recabling (resulting in different switch assignments), and subnet expansion.</span></span> <span data-ttu-id="23786-169">Você atualizará diretamente cada local individual ou realizará uma atualização em massa de todos os locais usando um arquivo CSV?</span><span class="sxs-lookup"><span data-stu-id="23786-169">Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="23786-170">**Você usará um aplicativo SNMP para corresponder a endereços MAC do cliente do Lync a identificadores de porta e de comutador?**</span><span class="sxs-lookup"><span data-stu-id="23786-170">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>  
    <span data-ttu-id="23786-171">Se você usar um aplicativo SNMP, precisará desenvolver um processo manual para manter as informações de chassi de comutador e de porta consistentes entre o aplicativo SNMP e o banco de dados de local.</span><span class="sxs-lookup"><span data-stu-id="23786-171">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="23786-172">Se o aplicativo SNMP retornar um endereço IP de chassi ou uma ID de porta que não esteja incluída no banco de dados, o serviço de informações de local não poderá retornar um local ao cliente.</span><span class="sxs-lookup"><span data-stu-id="23786-172">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

