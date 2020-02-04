---
title: 'Lync Server 2013: gerenciar locais para gateways ELIN'
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
ms.openlocfilehash: ba5a7e9067e4cd59ca42e60c620dbb4e8ee5b901
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762099"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-elin-gateways-in-lync-server-2013"></a><span data-ttu-id="853ba-102">Gerenciando locais para gateways do ELIN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="853ba-102">Managing locations for ELIN gateways in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="853ba-103">_**Tópico da última modificação:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="853ba-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="853ba-104">Para que o Lync Server forneça automaticamente locais para clientes em uma rede, você precisa executar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="853ba-104">To have Lync Server automatically provide locations for clients within a network, you need to perform the following tasks:</span></span>

  - <span data-ttu-id="853ba-105">Preencha o banco de dados do serviço de informações de localização com uma rede Wiremap e inclua os números de identificação de localização de emergência (ELINs) no campo CompanyName.</span><span class="sxs-lookup"><span data-stu-id="853ba-105">Populate the Location Information service database with a network wiremap, and include the Emergency Location Identification Numbers (ELINs) in the CompanyName field.</span></span>

  - <span data-ttu-id="853ba-106">Publique os locais para que estejam disponíveis para clientes em sua rede.</span><span class="sxs-lookup"><span data-stu-id="853ba-106">Publish the locations so that they are available for clients in your network.</span></span>

  - <span data-ttu-id="853ba-107">Carregue os ELINs no banco de dados de Identificação de Localização Automática (ALI) da transportadora PSTN.</span><span class="sxs-lookup"><span data-stu-id="853ba-107">Upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span>

<span data-ttu-id="853ba-108">Para obter detalhes sobre como executar essas tarefas, consulte [Configurar o banco de dados de localização no Lync Server 2013](lync-server-2013-configure-the-location-database.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="853ba-108">For details about how to perform these tasks, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="853ba-109">Os locais adicionados ao banco de dados do local central não estarão disponíveis para o cliente até serem publicados usando um comando shell do Shell de gerenciamento do Lync Server e serão duplicados para os armazenamentos locais do pool.</span><span class="sxs-lookup"><span data-stu-id="853ba-109">Locations added to the central location database are not available to the client until they have been published by using a Lync Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="853ba-110">Para obter detalhes, consulte <A href="lync-server-2013-publish-the-location-database.md">publicar o banco de dados de local do Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="853ba-110">For details, see <A href="lync-server-2013-publish-the-location-database.md">Publish the location database from Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="853ba-111">Esta seção descreve coisas a considerar conforme você planeja atualizar e manter o banco de dados de localização.</span><span class="sxs-lookup"><span data-stu-id="853ba-111">This section describes things to consider as you plan to update and maintain the location database.</span></span>

<div>

## <a name="planning-emergency-locations"></a><span data-ttu-id="853ba-112">Planejamento de locais de emergência</span><span class="sxs-lookup"><span data-stu-id="853ba-112">Planning Emergency Locations</span></span>

<span data-ttu-id="853ba-113">Ao usar gateways do ELIN, você preenche o banco de dados do serviço de informações de localização com o endereço cívico, um local específico dentro de um edifício e pelo menos um ELIN para cada local.</span><span class="sxs-lookup"><span data-stu-id="853ba-113">When you use ELIN gateways, you populate the Location Information service database with the civic address, a specific location within a building, and at least one ELIN for each location .</span></span> <span data-ttu-id="853ba-114">Durante a fase de planejamento, é uma boa ideia decidir como deseja nomear os locais e como você deseja atribuir os ELINs.</span><span class="sxs-lookup"><span data-stu-id="853ba-114">During the planning phase, it is a good idea to decide how you want to name the locations and how you want to assign ELINs.</span></span>

<div>

## <a name="planning-location-names"></a><span data-ttu-id="853ba-115">Planejamento dos nomes de local</span><span class="sxs-lookup"><span data-stu-id="853ba-115">Planning Location Names</span></span>

<span data-ttu-id="853ba-116">O campo **local** do serviço de informações de localização, que contém o local específico dentro de um edifício, tem um comprimento máximo de 20 caracteres (incluindo espaços).</span><span class="sxs-lookup"><span data-stu-id="853ba-116">The Location Information service **Location** field, which holds the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="853ba-117">Dentro deste comprimento limitado, tente incluir o seguinte:</span><span class="sxs-lookup"><span data-stu-id="853ba-117">Within that limited length, try to include the following:</span></span>

  - <span data-ttu-id="853ba-p104">Um nome fácil de compreender que identifica o local do chamador 911 para ajudar a garantir que os respondedores da emergência encontrem o local específico rapidamente quando chegarem ao endereço civil. Este nome de local pode incluir um número de construção, número do piso, designador de asa, número da sala e assim por diante. Evite apelidos que são conhecidos apenas pelos funcionários, que pode fazer com que os respondedores de emergência vão para o local incorreto.</span><span class="sxs-lookup"><span data-stu-id="853ba-p104">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address. This location name may include a building number, floor number, wing designator, room number, and so on. Avoid nicknames that are known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

  - <span data-ttu-id="853ba-121">Um identificador de localização que ajuda os usuários a ver facilmente que o cliente do Lync selecionou o local correto.</span><span class="sxs-lookup"><span data-stu-id="853ba-121">A location identifier that helps users to easily see that their Lync client picked up the correct location.</span></span> <span data-ttu-id="853ba-122">O cliente Lync concatena e exibe automaticamente os campos **local** e **cidade** descobertos no cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="853ba-122">The Lync client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="853ba-123">Uma prática recomendada é adicionar o endereço do edifício a cada identificador de localização (por exemplo, "número \<\>do 1ª andar").</span><span class="sxs-lookup"><span data-stu-id="853ba-123">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor \<street number\>").</span></span> <span data-ttu-id="853ba-124">Sem o endereço físico, um identificador de local genérico como "1° andar" pode ser aplicado a qualquer edifício na cidade.</span><span class="sxs-lookup"><span data-stu-id="853ba-124">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

  - <span data-ttu-id="853ba-125">Se o local for aproximado por ser determinado por um ponto de acesso sem fio, convém adicionar a palavra  Near (por exemplo, próximo ao 1º andar, 1234).</span><span class="sxs-lookup"><span data-stu-id="853ba-125">If the location is approximate because it’s determined by a wireless access point, you may want to add the word Near (for example, "Near 1st Floor 1234").</span></span>

</div>

<div>

## <a name="planning-elins"></a><span data-ttu-id="853ba-126">Planejamento de ELINs</span><span class="sxs-lookup"><span data-stu-id="853ba-126">Planning ELINs</span></span>

<span data-ttu-id="853ba-p106">Após decidir como você deseja dividir o espaço da construção em locais, é necessário decidir quantos ELINs atribuir em cada local. Por exemplo, em uma construção de vários locais ou pisos, diferentes áreas na construção podem ser atribuídas com zonas de emergência diferentes. Geralmente, cada piso na construção é designado como um local. Cada local é atribuído com um ou mais ELINs, que são usados como números de chamada durante uma chamada de emergência. Entre em contato com sua transportadora PSTN para obter os números de telefone que você pode usar para ELINs. A tabela a seguir oferece um exemplo de locais para um endereço específico.</span><span class="sxs-lookup"><span data-stu-id="853ba-p106">After you decide how you want to divide your building space into locations, you need to decide how many ELINs to assign to each location. For example, in a multifloor or multitenant building, different areas in the building can be assigned different emergency zones. Typically, each floor in a building is designated as a location. Each location is then assigned one or more ELINs, which are used as the calling number(s) during an emergency call. Contact your PSTN carrier for phone numbers that you can use for ELINs. The following table provides an example of locations for a specific street address.</span></span>

### <a name="sample-location-and-elin-assignments"></a><span data-ttu-id="853ba-133">Local de amostra e Atribuições de ELIN</span><span class="sxs-lookup"><span data-stu-id="853ba-133">Sample Location and ELIN Assignments</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="853ba-134">Área de construção</span><span class="sxs-lookup"><span data-stu-id="853ba-134">Building Area</span></span></th>
<th><span data-ttu-id="853ba-135">Local</span><span class="sxs-lookup"><span data-stu-id="853ba-135">Location</span></span></th>
<th><span data-ttu-id="853ba-136">ELIN</span><span class="sxs-lookup"><span data-stu-id="853ba-136">ELIN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="853ba-137">Primeiro andar</span><span class="sxs-lookup"><span data-stu-id="853ba-137">First floor</span></span></p></td>
<td><p><span data-ttu-id="853ba-138">1</span><span class="sxs-lookup"><span data-stu-id="853ba-138">1</span></span></p></td>
<td><p><span data-ttu-id="853ba-139">425-555-0100</span><span class="sxs-lookup"><span data-stu-id="853ba-139">425-555-0100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="853ba-140">Segundo andar</span><span class="sxs-lookup"><span data-stu-id="853ba-140">Second floor</span></span></p></td>
<td><p><span data-ttu-id="853ba-141">2</span><span class="sxs-lookup"><span data-stu-id="853ba-141">2</span></span></p></td>
<td><p><span data-ttu-id="853ba-142">425-555-0111</span><span class="sxs-lookup"><span data-stu-id="853ba-142">425-555-0111</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="853ba-143">Terceiro andar</span><span class="sxs-lookup"><span data-stu-id="853ba-143">Third floor</span></span></p></td>
<td><p><span data-ttu-id="853ba-144">3</span><span class="sxs-lookup"><span data-stu-id="853ba-144">3</span></span></p></td>
<td><p><span data-ttu-id="853ba-145">425-555-0123</span><span class="sxs-lookup"><span data-stu-id="853ba-145">425-555-0123</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="853ba-146">Os locais definidos devem atender os seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="853ba-146">The locations you define should meet the following requirements:</span></span>

  - <span data-ttu-id="853ba-147">Cumpre os regulamentos locais e nacionais/regionais em termos de área máxima por local e número de locais por endereço.</span><span class="sxs-lookup"><span data-stu-id="853ba-147">Comply with local and national/regional regulations in terms of maximum area per location and number of locations per street address.</span></span>

  - <span data-ttu-id="853ba-148">São específicos o suficiente para tornar fácil localizar o chamador de emergência.</span><span class="sxs-lookup"><span data-stu-id="853ba-148">Are specific enough to make it easy to locate the emergency caller.</span></span>

</div>

</div>

<div>

## <a name="populating-the-location-database"></a><span data-ttu-id="853ba-149">Preenchendo o banco de dados Local</span><span class="sxs-lookup"><span data-stu-id="853ba-149">Populating the Location Database</span></span>

<span data-ttu-id="853ba-150">As seguintes perguntas ajudarão a determinar como preencher o banco de dados de local.</span><span class="sxs-lookup"><span data-stu-id="853ba-150">The following questions will help you determine how to will populate the location database.</span></span>

  - <span data-ttu-id="853ba-151">**Qual processo você usará para preencher o banco de dados de local?**</span><span class="sxs-lookup"><span data-stu-id="853ba-151">**What process will you use to populate the location database?**</span></span>  
    <span data-ttu-id="853ba-p107">Onde estão os dados e quais etapas você precisa executar para convertê-los para o formato necessário pelo banco de dados de local? Você adicionará locais individualmente ou em lote usando um arquivo CSV?</span><span class="sxs-lookup"><span data-stu-id="853ba-p107">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database? Will you add locations individually, or in bulk, by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="853ba-154">**Você tem um banco de dados de terceiro que já contém um mapeamento de locais?**</span><span class="sxs-lookup"><span data-stu-id="853ba-154">**Do you have a third party database that already contains a mapping of locations?**</span></span>  
    <span data-ttu-id="853ba-155">Ao usar a opção do serviço de informações de localização secundária do Lync Server para se conectar a um banco de dados de terceiros, você pode agrupar e gerenciar locais usando uma plataforma offline.</span><span class="sxs-lookup"><span data-stu-id="853ba-155">By using Lync Server's Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="853ba-156">Um benefício dessa abordagem é que além de associar locais aos identificadores de rede, é possível associar locais a um usuário.</span><span class="sxs-lookup"><span data-stu-id="853ba-156">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="853ba-157">Isso significa que o serviço de informações de localização pode retornar vários endereços, originários do serviço de informações de localização secundário, para um cliente do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="853ba-157">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Lync Server client.</span></span> <span data-ttu-id="853ba-158">Em seguida, o usuário pode escolher o local mais apropriado.</span><span class="sxs-lookup"><span data-stu-id="853ba-158">The user can then choose the most appropriate location.</span></span>
    
    <span data-ttu-id="853ba-159">Para integrar-se com o serviço informações de localização, o banco de dados de terceiros deve seguir o esquema de solicitação/resposta de localização do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="853ba-159">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="853ba-160">Para obter detalhes, <http://go.microsoft.com/fwlink/p/?linkid=213819>consulte.</span><span class="sxs-lookup"><span data-stu-id="853ba-160">For details, see <http://go.microsoft.com/fwlink/p/?linkid=213819>.</span></span> <span data-ttu-id="853ba-161">Para obter detalhes sobre a implantação de um serviço de informações de localização secundário, consulte [configurar um serviço de informações de localização secundário no Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="853ba-161">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="853ba-162">Para obter detalhes sobre como preencher o banco de dados de localização, consulte [Configurar o banco de dados de localização no Lync Server 2013](lync-server-2013-configure-the-location-database.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="853ba-162">For details about populating the location database, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="853ba-163">Manutenção do banco de dados de local</span><span class="sxs-lookup"><span data-stu-id="853ba-163">Maintaining the Location Database</span></span>

<span data-ttu-id="853ba-p110">Depois de preencher o banco de dados de local, é necessário desenvolver uma estratégia para atualização do banco de dados à medida que a configuração de rede mudar. As seguintes perguntas ajudarão a determinar como você manterá o banco de dados de local.</span><span class="sxs-lookup"><span data-stu-id="853ba-p110">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes. The following questions will help you determine how to maintain the location database.</span></span>

  - <span data-ttu-id="853ba-166">**Como você atualizará o banco de dados de local?**</span><span class="sxs-lookup"><span data-stu-id="853ba-166">**How will you update the location database?**</span></span>  
    <span data-ttu-id="853ba-p111">Há diversos cenários que exigem uma atualização para o banco de dados de local, incluindo a adição de WAPs (pontos de acesso sem fio), recabeamento do escritório (resultando em atribuições de comutação diferentes) e expansão da subrede. Você atualizará diretamente cada local individual ou realizará uma atualização em massa de todos os locais usando um arquivo CSV?</span><span class="sxs-lookup"><span data-stu-id="853ba-p111">There are several scenarios that require an update to the location database, including adding wireless access points (WAPs), office recabling (resulting in different switch assignments), and subnet expansion. Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="853ba-169">**Você usará um aplicativo SNMP para que os endereços do MAC do cliente do Skype sejam compatíveis aos identificadores de porta e de comutador?**</span><span class="sxs-lookup"><span data-stu-id="853ba-169">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>  
    <span data-ttu-id="853ba-170">Se você usar um aplicativo SNMP, precisará desenvolver um processo manual para manter as informações de porta e chassis de comutador consistentes entre o aplicativo SNMP e o banco de dados de local.</span><span class="sxs-lookup"><span data-stu-id="853ba-170">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="853ba-171">Se o aplicativo SNMP retornar um endereço IP de chassi ou uma ID de porta que não está incluída no banco de dados, o serviço de informações de localização não poderá retornar um local ao cliente.</span><span class="sxs-lookup"><span data-stu-id="853ba-171">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

