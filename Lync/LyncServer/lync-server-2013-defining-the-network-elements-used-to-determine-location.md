---
title: 'Lync Server 2013: definindo os elementos de rede usados para determinar o local'
description: 'Lync Server 2013: definindo os elementos de rede usados para determinar o local.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the network elements used to determine location
ms:assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398567(v=OCS.15)
ms:contentKeyID: 48184508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a77ad0a7d704bf2cc43118db45d9bcfb89daa327
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576277"
---
# <a name="defining-the-network-elements-used-to-determine-location-in-lync-server-2013"></a><span data-ttu-id="dd485-103">Definir os elementos de rede usados para determinar o local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd485-103">Defining the network elements used to determine location in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd485-104">_**Última modificação do tópico:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="dd485-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="dd485-105">Se você estiver configurando sua infraestrutura do Lync Server para oferecer suporte à detecção automática de local de cliente, primeiro será necessário decidir quais elementos de rede você usará para mapear chamadores para locais.</span><span class="sxs-lookup"><span data-stu-id="dd485-105">If you are setting up your Lync Server infrastructure to support automatic client location detection, you first need to decide which network elements you are going to use to map callers to locations.</span></span> <span data-ttu-id="dd485-106">No Lync Server 2013, você pode associar os seguintes elementos de rede de camada 2 e camada 3 com locais:</span><span class="sxs-lookup"><span data-stu-id="dd485-106">In Lync Server 2013, you can associate the following Layer 2 and Layer 3 network elements with locations:</span></span>

  - <span data-ttu-id="dd485-107">Endereços de BSSID (Identificação de Conjunto de Serviço Básico) do ponto de acesso sem fio (WAP) (Camada 2)</span><span class="sxs-lookup"><span data-stu-id="dd485-107">Wireless access point (WAP) Basic Service Set Identification (BSSID) addresses (Layer 2)</span></span>

  - <span data-ttu-id="dd485-108">Porta de comutador LLDP (Camada 2)</span><span class="sxs-lookup"><span data-stu-id="dd485-108">LLDP switch port (Layer 2)</span></span>

  - <span data-ttu-id="dd485-109">IDs de chassi do comutador LLDP (Camada 2)</span><span class="sxs-lookup"><span data-stu-id="dd485-109">LLDP switch chassis IDs (Layer 2)</span></span>

  - <span data-ttu-id="dd485-110">Sub-redes IP (Camada 3)</span><span class="sxs-lookup"><span data-stu-id="dd485-110">IP subnets (Layer 3)</span></span>

  - <span data-ttu-id="dd485-111">Endereços MAC do cliente (Camada 2)</span><span class="sxs-lookup"><span data-stu-id="dd485-111">Client MAC addresses (Layer 2)</span></span>

<span data-ttu-id="dd485-112">Os elementos de rede estão listados em ordem de precedência.</span><span class="sxs-lookup"><span data-stu-id="dd485-112">The network elements are listed in order of precedence.</span></span> <span data-ttu-id="dd485-113">Se um cliente puder ser localizado usando mais de um elemento de rede, o Lync Server usará a ordem de precedência para determinar o mecanismo a ser usado.</span><span class="sxs-lookup"><span data-stu-id="dd485-113">If a client can be located by using more than one network element, Lync Server uses the order of precedence to determine which mechanism to use.</span></span>

<span data-ttu-id="dd485-114">As seções a seguir fornecem mais detalhes de uso de cada elemento da rede.</span><span class="sxs-lookup"><span data-stu-id="dd485-114">The following sections provide more details for using each network element.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="dd485-115">Quando você usa elementos de rede para mapear chamadores para locais, é da importância máxima em que você mantém atualizado o banco de dados do serviço de informações de local.</span><span class="sxs-lookup"><span data-stu-id="dd485-115">When you use network elements to map callers to locations, it is of utmost importance that you keep the Location Information service database up-to-date.</span></span> <span data-ttu-id="dd485-116">Por exemplo, se você adicionar ou alterar um elemento de rede (como adicionar um WAP), será necessário excluir a entrada antiga e adicionar a nova no banco de dados de local.</span><span class="sxs-lookup"><span data-stu-id="dd485-116">For example, if you add or change a network element, such as adding a WAP, you must delete the old entry and add the new entry in the location database.</span></span>



</div>

<div>

## <a name="wireless-access-point"></a><span data-ttu-id="dd485-117">Ponto de acesso sem fio</span><span class="sxs-lookup"><span data-stu-id="dd485-117">Wireless Access Point</span></span>

<span data-ttu-id="dd485-118">Quando um cliente se conecta à rede sem fio, a solicitação de local usa o endereço BSSID do WAP para determinar a sua localização.</span><span class="sxs-lookup"><span data-stu-id="dd485-118">When a client connects to the network wirelessly, the location request uses the BSSID address of the WAP to determine its location.</span></span> <span data-ttu-id="dd485-119">Se o cliente estiver em roaming, o WAP indicado pode não ser o mais próximo, e é até possível obter um WAP que esteja em outro andar do edifício.</span><span class="sxs-lookup"><span data-stu-id="dd485-119">If the client is roaming, the WAP indicated may not be the closest one, and it’s even possible to pick up a WAP that is on a different floor of the building.</span></span> <span data-ttu-id="dd485-120">Para indicar que o local é aproximado, você pode colocar o valor do local com um descritor Near ou Close to.</span><span class="sxs-lookup"><span data-stu-id="dd485-120">To indicate that the location is approximate, you can prepend the location value with a Near or Close to descriptor.</span></span>

<span data-ttu-id="dd485-121">Este método local supõe que o BSSID de cada WAP é estático.</span><span class="sxs-lookup"><span data-stu-id="dd485-121">This location method assumes that the BSSID of each WAP is static.</span></span> <span data-ttu-id="dd485-122">Entretanto, se o seu fornecedor WAP usa BSSIDs atribuídos dinamicamente, o BSSID obtido de um WAP poderia ser alterado (isso pode acontecer após a alteração de uma configuração WAP) e clientes sem fio podem ser deixados em uma situação onde não recebem um local.</span><span class="sxs-lookup"><span data-stu-id="dd485-122">However, if your WAP vendor uses dynamically-assigned BSSIDs, the BSSID that is obtained from a WAP could change (this can happen following a WAP configuration change), and wireless clients could be left in a situation where they don’t receive a location.</span></span> <span data-ttu-id="dd485-123">Para evitar essa possibilidade, você precisa preencher o banco de dados do serviço de informações de local com o ERLs para todos os endereços BSSID possíveis usados por cada WAP.</span><span class="sxs-lookup"><span data-stu-id="dd485-123">To prevent this possibility, you need to populate the Location Information service database with ERLs for all possible BSSID addresses used by each WAP.</span></span>

</div>

<div>

## <a name="lldp-ports-and-switches"></a><span data-ttu-id="dd485-124">Comutadores e portas LLDP</span><span class="sxs-lookup"><span data-stu-id="dd485-124">LLDP Ports and Switches</span></span>

<span data-ttu-id="dd485-p106">Os comutadores Ethernet gerenciados que oferecem suporte ao protocolo LLDP-MED podem anunciar suas informações de identidade e a porta a clientes compatíveis com LLDP-MED, que podem ser consultados em relação ao banco de dados de local para fornecer o local do dispositivo. Você pode associar ERLs exclusivamente na identificação de chassi de comutador ou pode mapeá-los ao nível de porta.</span><span class="sxs-lookup"><span data-stu-id="dd485-p106">Managed Ethernet switches that support Link Layer Discovery Protocol-Media Endpoint Discover (LLDP-MED) can advertise their identity and port information to LLDP-MED compatible clients, which then can be queried against the location database to provide the location of the device. You can associate ERLs solely on the switch chassis ID, or you can map them down to the port level.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dd485-127">O Lync Server 2013 oferece suporte ao uso de LLDP-MED para determinar os locais apenas dos dispositivos do Lync Phone Edition e do Lync 2013 em execução no Windows 8.</span><span class="sxs-lookup"><span data-stu-id="dd485-127">Lync Server 2013 supports using LLDP-MED for determining locations only of Lync Phone Edition devices and Lync 2013 running on Windows 8.</span></span> <span data-ttu-id="dd485-128">Se você precisar usar dados de camada 2 de nível de alternância para determinar o local de outros clientes Lync baseados em computador com fio, será necessário usar o método de endereço MAC do cliente.</span><span class="sxs-lookup"><span data-stu-id="dd485-128">If you need to use switch-level Layer 2 data to determine the location of other wired PC-based Lync clients, you need to use the client MAC address method.</span></span>



</div>

</div>

<div>

## <a name="subnet"></a><span data-ttu-id="dd485-129">Sub-rede</span><span class="sxs-lookup"><span data-stu-id="dd485-129">Subnet</span></span>

<span data-ttu-id="dd485-130">As sub-redes IP de camada 3 fornecem um mecanismo suportado por todos os clientes do Lync Server que podem ser usados para detectar automaticamente o local do cliente.</span><span class="sxs-lookup"><span data-stu-id="dd485-130">Layer 3 IP subnets provide a mechanism supported by all Lync Server clients that can be used to automatically detect client location.</span></span> <span data-ttu-id="dd485-131">O uso de sub-redes IP é o método de localização mais fácil de configurar e gerenciar os clientes com fio.</span><span class="sxs-lookup"><span data-stu-id="dd485-131">Using IP subnets is the easiest location method to configure and manage wired clients.</span></span> <span data-ttu-id="dd485-132">Porém, antes de decidir usar as sub-redes, você deve usar as seguintes perguntas para ajudar a determinar se a especificidade do local da sub-rede é boa o suficiente para localizar com precisão um cliente:</span><span class="sxs-lookup"><span data-stu-id="dd485-132">Before you decide to use subnets, however, use the following questions to help determine if the location specificity of the subnet is sufficiently fine to accurately locate a client:</span></span>

  - <span data-ttu-id="dd485-133">Uma ou mais sub-redes de cliente abrangem vários andares?</span><span class="sxs-lookup"><span data-stu-id="dd485-133">Do one or more client subnets cover multiple floors?</span></span>

  - <span data-ttu-id="dd485-134">Uma ou mais sub-redes abrangem mais de um edifício?</span><span class="sxs-lookup"><span data-stu-id="dd485-134">Do one or more subnets cover more than one building?</span></span>

  - <span data-ttu-id="dd485-135">Quanto espaço é coberto por cada sub-rede do cliente?</span><span class="sxs-lookup"><span data-stu-id="dd485-135">How much floor space is covered by each client subnet?</span></span>

<span data-ttu-id="dd485-p109">Se a sub-rede abrange uma área muito ampla, talvez seja necessário usar outro mecanismo para localizar clientes. No entanto, se for prático, recomendamos que os clientes reorganizem suas sub-redes IP para atender aos requisitos de especificidade de local ERL, em vez de assumir os custos e a complexidade de soluções de terceiros baseadas em SNMP.</span><span class="sxs-lookup"><span data-stu-id="dd485-p109">If the subnet covers too broad an area, you may need to use another mechanism to locate clients. However, if at all practical, we recommend that customers reorganize their IP subnetting to meet the ERL location specificity requirements rather than incurring the cost and complexity of third-party SNMP-based solutions.</span></span>

</div>

<div>

## <a name="client-mac-address"></a><span data-ttu-id="dd485-138">Endereço MAC do cliente</span><span class="sxs-lookup"><span data-stu-id="dd485-138">Client MAC Address</span></span>

<span data-ttu-id="dd485-139">Para usar o endereço MAC do computador cliente para localizar um chamador, você precisa de comutadores Ethernet gerenciados e deve implantar uma solução SNMP de terceiros que possa descobrir os endereços MAC de clientes Lync conectados a (ou através de) esses comutadores.</span><span class="sxs-lookup"><span data-stu-id="dd485-139">To use a client computer's MAC address to locate a caller, you need managed Ethernet switches, and you must deploy a third-party SNMP solution that can discover the MAC addresses of Lync clients connected to (or through) those switches.</span></span> <span data-ttu-id="dd485-140">A solução SNMP continuamente controla os comutadores gerenciados para obter mapeamentos atuais dos endereços MAC de extremidade conectados a cada porta e obtém os IDs de porta correspondentes.</span><span class="sxs-lookup"><span data-stu-id="dd485-140">The SNMP solution continually polls the managed switches to get the current mappings of the endpoint MAC addresses connected to each port and obtains the corresponding port IDs.</span></span> <span data-ttu-id="dd485-141">Durante uma solicitação do cliente Lync para o serviço de informações de local, o serviço de informações de local consulta o aplicativo de terceiros usando o endereço MAC do cliente e, em seguida, retorna qualquer endereço IP de comutação correspondente e IDs de porta.</span><span class="sxs-lookup"><span data-stu-id="dd485-141">During a Lync client’s request to the Location Information service, the Location Information service queries the third-party application by using the client’s MAC address, and then returns any matching switch IP addresses and port IDs.</span></span> <span data-ttu-id="dd485-142">O serviço de informações de local usa essas informações para consultar sua Wiremap da camada 2 publicada de um registro correspondente e retorna o local para o cliente.</span><span class="sxs-lookup"><span data-stu-id="dd485-142">The Location Information service uses this information to query its published Layer 2 wiremap for a matching record and returns the location to the client.</span></span> <span data-ttu-id="dd485-143">Se você usar esta opção, verifique se os identificadores de porta do comutador são consistentes entre o aplicativo SNMP e os registros publicados do banco de dados de local.</span><span class="sxs-lookup"><span data-stu-id="dd485-143">If you use this option, make sure that the switch port identifiers are consistent between the SNMP application and the published location database records.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dd485-144">Algumas soluções SNMP de terceiros podem oferecer suporte a comutadores de acesso não gerenciados; se a opção de atendimento ao cliente Lync não for gerenciada, mas tem um uplink a um comutador de distribuição gerenciado, o comutador gerenciado pode relatar os endereços MAC dos clientes conectados ao comutador de acesso ao aplicativo SNMP.</span><span class="sxs-lookup"><span data-stu-id="dd485-144">Some third-party SNMP solutions can support unmanaged access switches; if the switch that services the Lync client is unmanaged but has an uplink to a managed distribution switch, the managed switch can report back to the SNMP application the MAC addresses of the clients connected to the access switch.</span></span> <span data-ttu-id="dd485-145">Essas informações permitem que o serviço de informações de local identifique o local do usuário.</span><span class="sxs-lookup"><span data-stu-id="dd485-145">This information enables the Location Information service to identify the location of the user.</span></span> <span data-ttu-id="dd485-146">No entanto, só é possível atribuir um único ERL a todas as portas no comutador não gerenciado, para que a especificidade do local só esteja disponível a nível do chassi do comutador de acesso, não a nível de porta.</span><span class="sxs-lookup"><span data-stu-id="dd485-146">However, it is possible to assign only a single ERL to all ports on the unmanaged switch, so the location specificity is available only at the chassis level of the access switch, not the port level.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

