---
title: 'Lync Server 2013: gerenciar locais para provedores de serviço de tronco SIP'
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
ms.openlocfilehash: e9ebc471459c8e406914f5a075d7e4cf8b69fadd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762089"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-sip-trunk-service-providers-in-lync-server-2013"></a><span data-ttu-id="f338e-102">Gerenciando locais para provedores de serviço de tronco SIP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f338e-102">Managing locations for SIP trunk service providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f338e-103">_**Tópico da última modificação:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="f338e-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="f338e-104">Para configurar o Lync Server para localizar automaticamente clientes em uma rede, você precisa preencher o banco de dados do serviço de informações de localização com um Wiremap de rede e publicar os locais, ou vincular a um banco de dados externo que já contém o mapeamentos.</span><span class="sxs-lookup"><span data-stu-id="f338e-104">To configure Lync Server to automatically locate clients within a network, you need to either populate the Location Information service database with a network wiremap and publish the locations, or link to an external database that already contains the correct mappings.</span></span> <span data-ttu-id="f338e-105">Como parte desse processo, é necessário validar os endereços cívicos dos locais com seu provedor de serviço de E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="f338e-105">As part of this process, you need to validate the civic addresses of the locations with your E9-1-1 service provider.</span></span> <span data-ttu-id="f338e-106">Para obter detalhes, consulte [Configurar o banco de dados de localização no Lync Server 2013](lync-server-2013-configure-the-location-database.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="f338e-106">For details, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

<span data-ttu-id="f338e-107">Você preenche o banco de dados do Serviço de Informações de Local com um Local de Resposta de Emergência (ERL), que consiste de um endereço civil e o endereço específico dentro de um edifício.</span><span class="sxs-lookup"><span data-stu-id="f338e-107">You populate the Location Information service database with an Emergency Response Location (ERL), which consists of a civic address and the specific address within a building.</span></span> <span data-ttu-id="f338e-108">O campo **local** do serviço de informações de localização, que é o local específico dentro de um edifício, tem um tamanho máximo de 20 caracteres (incluindo espaços).</span><span class="sxs-lookup"><span data-stu-id="f338e-108">The Location Information service **Location** field, which is the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="f338e-109">Dentro deste comprimento limitado, tente incluir o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f338e-109">Within that limited length, try to include the following:</span></span>

  - <span data-ttu-id="f338e-p103">Um nome fácil de entender que identifica o local do chamador de 911 para ajudar a garantir que os respondentes de emergência encontrem o local correto quando chegarem ao endereço cívico. Esse nome de local pode incluir um número de edifício, número do andar, designador de ala, número da sala, etc. Evite apelidos conhecidos apenas pelos funcionários, que pode fazer com que os respondentes de emergência cheguem ao local errado.</span><span class="sxs-lookup"><span data-stu-id="f338e-p103">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address. This location name may include a building number, floor number, wing designator, room number, and so on. Avoid nicknames known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

  - <span data-ttu-id="f338e-113">Um identificador de localização que ajuda os usuários a ver facilmente que o cliente do Lync selecionou o local correto.</span><span class="sxs-lookup"><span data-stu-id="f338e-113">A location identifier that helps users to easily see that their Lync client picked up the correct location.</span></span> <span data-ttu-id="f338e-114">O cliente Lync concatena e exibe automaticamente os campos **local** e **cidade** descobertos no cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="f338e-114">The Lync client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="f338e-115">Uma prática recomendada é adicionar o endereço do edifício a cada identificador de localização (por exemplo, "número \<\>do 1ª andar").</span><span class="sxs-lookup"><span data-stu-id="f338e-115">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor \<street number\>").</span></span> <span data-ttu-id="f338e-116">Sem o endereço físico, um identificador de local genérico como "1° andar" pode ser aplicado a qualquer edifício na cidade.</span><span class="sxs-lookup"><span data-stu-id="f338e-116">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

  - <span data-ttu-id="f338e-117">Se o local for aproximado por ser determinado por um ponto de acesso sem fio, convém adicionar a palavra Near (por exemplo, "próximo ao 1º andar, 1234").</span><span class="sxs-lookup"><span data-stu-id="f338e-117">If the location is approximate because it’s determined by a wireless access point, you can add the word Near (for example, "Near 1st Floor 1234").</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f338e-118">Os locais adicionados ao banco de dados do local central não estarão disponíveis para o cliente até serem publicados usando um comando shell do Shell de gerenciamento do Lync Server e serão duplicados para os armazenamentos locais do pool.</span><span class="sxs-lookup"><span data-stu-id="f338e-118">Locations added to the central location database are not available to the client until they are published by using a Lync Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="f338e-119">Para obter detalhes, consulte <A href="lync-server-2013-publish-the-location-database.md">publicar o banco de dados de local do Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="f338e-119">For details, see <A href="lync-server-2013-publish-the-location-database.md">Publish the location database from Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="f338e-120">As seções a seguir discutem as considerações que devem ser analisadas ao preencher e manter o banco de dados de local.</span><span class="sxs-lookup"><span data-stu-id="f338e-120">The following sections discuss considerations that you need to take into account when populating and maintaining the location database.</span></span>

<div>

## <a name="populating-the-location-database"></a><span data-ttu-id="f338e-121">Preenchendo o banco de dados de local</span><span class="sxs-lookup"><span data-stu-id="f338e-121">Populating the Location Database</span></span>

<span data-ttu-id="f338e-122">As seguintes perguntas ajudam a determinar como você preencherá o banco de dados de local.</span><span class="sxs-lookup"><span data-stu-id="f338e-122">The following questions can help you determine how to populate the location database.</span></span>

  - <span data-ttu-id="f338e-123">**Qual processo você usará para preencher o banco de dados de local?**</span><span class="sxs-lookup"><span data-stu-id="f338e-123">**What process will you use to populate the location database?**</span></span>  
    <span data-ttu-id="f338e-p106">Onde estão os dados e quais etapas você precisa executar para convertê-los para o formato necessário pelo banco de dados de local? Você adicionará locais individualmente ou em lote usando um arquivo CSV?</span><span class="sxs-lookup"><span data-stu-id="f338e-p106">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database? Will you add locations individually, or in bulk, by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="f338e-126">**Você tem um banco de dados de terceiro que já contém um mapeamento de locais?**</span><span class="sxs-lookup"><span data-stu-id="f338e-126">**Do you have a third party database that already contains a mapping of locations?**</span></span>  
    <span data-ttu-id="f338e-127">Ao usar a opção do serviço de informações de localização secundária do Lync Server para se conectar a um banco de dados de terceiros, você pode agrupar e gerenciar locais usando uma plataforma offline.</span><span class="sxs-lookup"><span data-stu-id="f338e-127">By using Lync Server's Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="f338e-128">Um benefício dessa abordagem é que além de associar locais aos identificadores de rede, é possível associar locais a um usuário.</span><span class="sxs-lookup"><span data-stu-id="f338e-128">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="f338e-129">Isso significa que o serviço de informações de localização pode retornar vários endereços, originários do serviço de informações de localização secundário, para um cliente do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f338e-129">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Lync Server client.</span></span> <span data-ttu-id="f338e-130">Em seguida, o usuário pode escolher o local mais apropriado.</span><span class="sxs-lookup"><span data-stu-id="f338e-130">The user can then choose the most appropriate location.</span></span>
    
    <span data-ttu-id="f338e-131">Para integrar-se com o serviço informações de localização, o banco de dados de terceiros deve seguir o esquema de solicitação/resposta de localização do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f338e-131">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="f338e-132">Para obter detalhes, consulte\["MS-\]E911WS: Web Service for E911 support Protocol Specification" <http://go.microsoft.com/fwlink/p/?linkid=213819>em.</span><span class="sxs-lookup"><span data-stu-id="f338e-132">For details, see "\[MS-E911WS\]: Web Service for E911 Support Protocol Specification" at <http://go.microsoft.com/fwlink/p/?linkid=213819>.</span></span> <span data-ttu-id="f338e-133">Para obter detalhes sobre a implantação de um serviço de informações de localização secundário, consulte [configurar um serviço de informações de localização secundário no Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="f338e-133">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="f338e-134">Para obter detalhes sobre como preencher o banco de dados de localização, consulte [Configurar o banco de dados de localização no Lync Server 2013](lync-server-2013-configure-the-location-database.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="f338e-134">For details about populating the location database, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="f338e-135">Manutenção do banco de dados de local</span><span class="sxs-lookup"><span data-stu-id="f338e-135">Maintaining the Location Database</span></span>

<span data-ttu-id="f338e-p109">Depois de preencher o banco de dados de local, é necessário desenvolver uma estratégia para atualização do banco de dados à medida que a configuração de rede mudar. As seguintes perguntas ajudarão a determinar como você manterá o banco de dados de local.</span><span class="sxs-lookup"><span data-stu-id="f338e-p109">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes. The following questions will help you determine how to maintain the location database.</span></span>

  - <span data-ttu-id="f338e-138">**Como você atualizará o banco de dados de local?**</span><span class="sxs-lookup"><span data-stu-id="f338e-138">**How will you update the location database?**</span></span>  
    <span data-ttu-id="f338e-p110">Há diversos cenários que exigem uma atualização para o banco de dados de local, incluindo a adição de WAPs, recabeamento do escritório (resultando em atribuições de comutação diferentes) e expansão da subrede. Você atualizará diretamente cada local individual ou realizará uma atualização em massa de todos os locais usando um arquivo CSV?</span><span class="sxs-lookup"><span data-stu-id="f338e-p110">There are several scenarios that require an update to the location database, including adding WAPs, office recabling (resulting in different switch assignments), and subnet expansion. Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="f338e-141">**Você usará um aplicativo SNMP para que os endereços do MAC do cliente do Skype sejam compatíveis aos identificadores de porta e de comutador?**</span><span class="sxs-lookup"><span data-stu-id="f338e-141">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>  
    <span data-ttu-id="f338e-142">Se você usar um aplicativo SNMP, precisará desenvolver um processo manual para manter as informações de porta e chassis de comutador consistentes entre o aplicativo SNMP e o banco de dados de local.</span><span class="sxs-lookup"><span data-stu-id="f338e-142">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="f338e-143">Se o aplicativo SNMP retornar um endereço IP de chassi ou uma ID de porta que não está incluída no banco de dados, o serviço de informações de localização não poderá retornar um local ao cliente.</span><span class="sxs-lookup"><span data-stu-id="f338e-143">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

