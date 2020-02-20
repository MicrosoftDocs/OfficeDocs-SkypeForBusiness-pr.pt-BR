---
title: 'Lync Server 2013: opções de implantação de SIP direto'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Direct SIP deployment options
ms:assetid: 84691944-03f2-4a89-9f2b-1ab3d7f388cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398672(v=OCS.15)
ms:contentKeyID: 48184692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03d3d51c8323ab448951255ac9f7cf8d284896ba
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="direct-sip-deployment-options-in-lync-server-2013"></a><span data-ttu-id="83973-102">Opções de implantação de SIP direto no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83973-102">Direct SIP deployment options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83973-103">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="83973-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="83973-104">Este tópico fornece exemplos de topologias para a implantação de conexões SIP diretas.</span><span class="sxs-lookup"><span data-stu-id="83973-104">This topic provides example topologies for deploying direct SIP connections.</span></span>

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a><span data-ttu-id="83973-105">Lync Server autônomo</span><span class="sxs-lookup"><span data-stu-id="83973-105">Lync Server Stand-Alone</span></span>

<span data-ttu-id="83973-106">Se sua organização usa uma das implantações descritas nesta seção, você pode usar o Lync Server 2013 como a única solução de telefonia de parte ou de uma organização.</span><span class="sxs-lookup"><span data-stu-id="83973-106">If your organization uses one of the deployments described in this section, you can use Lync Server 2013 as the sole telephony solution for part or all of an organization.</span></span> <span data-ttu-id="83973-107">Esta seção descreve as seguintes implantações em detalhes:</span><span class="sxs-lookup"><span data-stu-id="83973-107">This section describes the following deployments in detail:</span></span>

  - <span data-ttu-id="83973-108">**Implantação incremental:** Essa opção pressupõe que você tenha uma infraestrutura existente de PBX (central privada de comutação de negócios) e você pretende introduzir o Enterprise Voice de forma incremental para grupos menores ou equipes dentro da sua organização.</span><span class="sxs-lookup"><span data-stu-id="83973-108">**Incremental deployment:** This option assumes that you have an existing private branch exchange (PBX) infrastructure and you intend to introduce Enterprise Voice incrementally to smaller groups or teams within your organization.</span></span>

  - <span data-ttu-id="83973-109">**Implantação somente VoIP do Lync Server:** essa opção pressupõe que você está pensando em implantar o Enterprise Voice em um site que não tem uma infraestrutura de telefonia tradicional.</span><span class="sxs-lookup"><span data-stu-id="83973-109">**Lync Server VoIP-only deployment:** this option assumes that you are considering deploying Enterprise Voice at a site that does not have a traditional telephony infrastructure.</span></span>

<div>

## <a name="incremental-deployment"></a><span data-ttu-id="83973-110">Implantação incremental</span><span class="sxs-lookup"><span data-stu-id="83973-110">Incremental Deployment</span></span>

<span data-ttu-id="83973-111">Na implantação incremental, o Lync Server 2013 é a única solução de telefonia para equipes ou departamentos individuais, enquanto o restante dos usuários em uma organização continuam a usar um PBX.</span><span class="sxs-lookup"><span data-stu-id="83973-111">In incremental deployment, Lync Server 2013 is the sole telephony solution for individual teams or departments, while the rest of the users in an organization continue to use a PBX.</span></span> <span data-ttu-id="83973-112">Essa estratégia de implantação incremental oferece uma maneira de introduzir a telefonia IP em sua empresa por meio de programas piloto controlados.</span><span class="sxs-lookup"><span data-stu-id="83973-112">This incremental deployment strategy provides one way to introduce IP telephony into your enterprise through controlled pilot programs.</span></span> <span data-ttu-id="83973-113">Os grupos de usuários cujas necessidades de comunicação são mais bem servidas pela comunicação unificada da Microsoft são movidos para o Enterprise Voice, enquanto outros usuários permanecem no PBX existente.</span><span class="sxs-lookup"><span data-stu-id="83973-113">Workgroups whose communication needs are best served by Microsoft Unified Communications are moved to Enterprise Voice, while other users remain on the existing PBX.</span></span> <span data-ttu-id="83973-114">Os grupos de gerenciamento adicionais podem ser migrados para o Enterprise Voice, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="83973-114">Additional workgroups can be migrated to Enterprise Voice, as needed.</span></span>

<span data-ttu-id="83973-115">A opção incremental é recomendada se você tiver definido claramente os grupos de usuários que têm requisitos de comunicação em comum e que se conservem para o gerenciamento centralizado.</span><span class="sxs-lookup"><span data-stu-id="83973-115">The incremental option is recommended if you have clearly defined user groups that have communication requirements in common and that lend themselves to centralized management.</span></span> <span data-ttu-id="83973-116">Essa opção também é eficaz se você tiver equipes ou departamentos que estão espalhados por áreas geográficas amplas, onde a economia nos encargos de longa distância pode ser significativa.</span><span class="sxs-lookup"><span data-stu-id="83973-116">This option is also effective if you have teams or departments that are spread over wide geographic areas, where the savings in long-distance charges can be significant.</span></span> <span data-ttu-id="83973-117">Na verdade, essa opção é útil para criar equipes virtuais cujos membros podem ser espalhados pelo mundo.</span><span class="sxs-lookup"><span data-stu-id="83973-117">In fact, this option is useful for creating virtual teams whose members may be scattered across the globe.</span></span> <span data-ttu-id="83973-118">Você pode criar, modificar ou disband essas equipes em resposta rápida para mudar os requisitos de negócios.</span><span class="sxs-lookup"><span data-stu-id="83973-118">You can create, modify, or disband such teams in rapid response to shifting business requirements.</span></span>

<span data-ttu-id="83973-119">A figura a seguir mostra a topologia genérica para a implantação do Enterprise Voice atrás de um PBX.</span><span class="sxs-lookup"><span data-stu-id="83973-119">The following figure shows the generic topology for deployment of Enterprise Voice behind a PBX.</span></span> <span data-ttu-id="83973-120">Esta é a topologia recomendada para implantação incremental.</span><span class="sxs-lookup"><span data-stu-id="83973-120">This is the recommended topology for incremental deployment.</span></span>

<span data-ttu-id="83973-121">**Opção de implantação incremental**</span><span class="sxs-lookup"><span data-stu-id="83973-121">**Incremental deployment option**</span></span>

<span data-ttu-id="83973-122">![Diagrama de opções de migração departamental](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Diagrama de opções de migração departamental")</span><span class="sxs-lookup"><span data-stu-id="83973-122">![Departmental Migration Option diagram](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Departmental Migration Option diagram")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="83973-123">Se você estiver conectando sua implantação do Lync Server a um parceiro SIP direto certificado, um gateway PSTN (rede telefônica pública comutada) entre o servidor de mediação e o PBX não é necessário.</span><span class="sxs-lookup"><span data-stu-id="83973-123">If you are connecting your Lync Server deployment to a certified Direct SIP partner, a public switched telephone network (PSTN) gateway between the Mediation Server and the PBX is not required.</span></span> <span data-ttu-id="83973-124">Para obter uma lista de parceiros de SIP diretos certificados, consulte o site do programa de interoperabilidade aberta do Microsoft Unified Communications em <A href="https://go.microsoft.com/fwlink/p/?linkid=203309">https://go.microsoft.com/fwlink/p/?linkId=203309</A>.</span><span class="sxs-lookup"><span data-stu-id="83973-124">For a list of certified Direct SIP partners, see the Microsoft Unified Communications Open Interoperability Program website at <A href="https://go.microsoft.com/fwlink/p/?linkid=203309">https://go.microsoft.com/fwlink/p/?linkId=203309</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="83973-125">O caminho de mídia mostrado nesta figura tem o bypass de mídia habilitado (a configuração recomendada).</span><span class="sxs-lookup"><span data-stu-id="83973-125">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="83973-126">Se você optar por desabilitar o bypass de mídia, o caminho de mídia será roteado através do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="83973-126">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

<span data-ttu-id="83973-127">Nesta topologia, os departamentos selecionados ou os grupos de gerenciamento estão habilitados para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="83973-127">In this topology, selected departments or workgroups are enabled for Enterprise Voice.</span></span> <span data-ttu-id="83973-128">Um gateway PSTN vincula o grupo de trabalho habilitado para VoIP (Voice over Internet Protocol) ao PBX.</span><span class="sxs-lookup"><span data-stu-id="83973-128">A PSTN gateway links the Voice over Internet Protocol (VoIP)-enabled workgroup to the PBX.</span></span> <span data-ttu-id="83973-129">Usuários habilitados para o Enterprise Voice, incluindo funcionários remotos, se comunicam através da rede IP.</span><span class="sxs-lookup"><span data-stu-id="83973-129">Users who are enabled for Enterprise Voice, including remote workers, communicate across the IP network.</span></span> <span data-ttu-id="83973-130">As chamadas de usuários do Enterprise Voice para o PSTN e para os colegas de trabalho que não estão habilitados para Enterprise Voice são roteadas para o gateway PSTN apropriado.</span><span class="sxs-lookup"><span data-stu-id="83973-130">Calls by Enterprise Voice users to the PSTN and to coworkers who are not enabled for Enterprise Voice are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="83973-131">As chamadas de colegas que ainda estão no sistema PBX ou de chamadores no PSTN são roteadas para o gateway PSTN, que encaminha as chamadas para o Lync Server para roteamento.</span><span class="sxs-lookup"><span data-stu-id="83973-131">Calls from colleagues who are still on the PBX system, or from callers on the PSTN, are routed to the PSTN gateway, which forwards the calls to Lync Server for routing.</span></span>

<span data-ttu-id="83973-132">Há duas configurações recomendadas para conectar o Enterprise Voice a uma infraestrutura de PBX existente para interoperabilidade: Enterprise Voice atrás do PBX e Enterprise Voice na frente do PBX.</span><span class="sxs-lookup"><span data-stu-id="83973-132">There are two recommended configurations for connecting Enterprise Voice to an existing PBX infrastructure for interoperability: Enterprise Voice behind the PBX and Enterprise Voice in front of the PBX.</span></span>

<div>

## <a name="enterprise-voice-behind-the-pbx"></a><span data-ttu-id="83973-133">Enterprise Voice atrás do PBX</span><span class="sxs-lookup"><span data-stu-id="83973-133">Enterprise Voice Behind the PBX</span></span>

<span data-ttu-id="83973-134">Quando o Enterprise Voice é implantado por trás do PBX, todas as chamadas de PSTN chegam no PBX, que roteia chamadas para usuários do Enterprise Voice para um gateway PSTN e chamadas para usuários PBX para o PBX.</span><span class="sxs-lookup"><span data-stu-id="83973-134">When Enterprise Voice is deployed behind the PBX, all calls from the PSTN arrive at the PBX, which routes calls to Enterprise Voice users to a PSTN gateway, and calls to PBX users to the PBX.</span></span>

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a><span data-ttu-id="83973-135">Enterprise Voice na frente do PBX</span><span class="sxs-lookup"><span data-stu-id="83973-135">Enterprise Voice in Front of the PBX</span></span>

<span data-ttu-id="83973-136">Quando o Enterprise Voice é implantado na frente do PBX, todas as chamadas chegam no gateway PSTN, que roteia chamadas para usuários do Enterprise Voice para o Lync Server e chamadas para usuários PBX para o PBX.</span><span class="sxs-lookup"><span data-stu-id="83973-136">When Enterprise Voice is deployed in front of the PBX, all calls arrive at the PSTN gateway, which routes calls for Enterprise Voice users to Lync Server and calls for PBX users to the PBX.</span></span> <span data-ttu-id="83973-137">As chamadas para a PSTN de usuários do Enterprise Voice e PBX são roteadas pela rede IP para o gateway PSTN mais econômico.</span><span class="sxs-lookup"><span data-stu-id="83973-137">Calls to the PSTN from both Enterprise Voice and PBX users are routed over the IP network to the most cost-efficient PSTN gateway.</span></span> <span data-ttu-id="83973-138">A tabela a seguir mostra as vantagens e desvantagens dessa configuração.</span><span class="sxs-lookup"><span data-stu-id="83973-138">The following table shows the advantages and disadvantages of this configuration.</span></span>

### <a name="advantages-and-disadvantages-of-deploying-enterprise-voice-in-front-of-pbx"></a><span data-ttu-id="83973-139">Vantagens e desvantagens da implantação do Enterprise Voice na frente do PBX</span><span class="sxs-lookup"><span data-stu-id="83973-139">Advantages and Disadvantages of Deploying Enterprise Voice in Front of PBX</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83973-140">Vantagens</span><span class="sxs-lookup"><span data-stu-id="83973-140">Advantages</span></span></th>
<th><span data-ttu-id="83973-141">Desvantagens</span><span class="sxs-lookup"><span data-stu-id="83973-141">Disadvantages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83973-142">O PBX ainda atende aos usuários não habilitados para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="83973-142">PBX still serves users not enabled for Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="83973-143">Os gateways existentes podem não oferecer suporte aos recursos ou à capacidade desejados.</span><span class="sxs-lookup"><span data-stu-id="83973-143">Existing gateways may not support the features or capacity that you want.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83973-144">O PBX trata de todos os dispositivos anteriores.</span><span class="sxs-lookup"><span data-stu-id="83973-144">PBX handles all earlier devices.</span></span></p></td>
<td><p><span data-ttu-id="83973-145">Requer um tronco do gateway para o PBX e do gateway para o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="83973-145">Requires a trunk from gateway to the PBX and from the gateway to the Mediation Server.</span></span> <span data-ttu-id="83973-146">Você pode precisar de mais troncos do provedor de serviços.</span><span class="sxs-lookup"><span data-stu-id="83973-146">You may need more trunks from the service provider.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83973-147">Os usuários do Enterprise Voice mantêm os mesmos números de telefone.</span><span class="sxs-lookup"><span data-stu-id="83973-147">Enterprise Voice users keep the same phone numbers.</span></span></p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a><span data-ttu-id="83973-148">Implantação somente VoIP do Lync Server</span><span class="sxs-lookup"><span data-stu-id="83973-148">Lync Server VoIP-Only Deployment</span></span>

<span data-ttu-id="83973-149">O Enterprise Voice oferece novos negócios e novos sites do Office para empresas existentes, com a oportunidade de implementar uma solução VoIP completa sem ter que se preocupar com a integração de PBX ou incorrer à implantação e à manutenção substanciais custos de uma infraestrutura IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="83973-149">Enterprise Voice provides new businesses, and also new office sites for existing businesses, with the opportunity to implement a full-featured VoIP solution without having to worry about PBX integration or incurring the substantial deployment and maintenance costs of an IP-PBX infrastructure.</span></span> <span data-ttu-id="83973-150">Esta solução oferece suporte a funcionários remotos e no local.</span><span class="sxs-lookup"><span data-stu-id="83973-150">This solution supports both on-site and remote workers.</span></span>

<span data-ttu-id="83973-151">Nesta implantação, todas as chamadas são roteadas pela rede IP.</span><span class="sxs-lookup"><span data-stu-id="83973-151">In this deployment, all calls are routed over the IP network.</span></span> <span data-ttu-id="83973-152">As chamadas para a PSTN são roteadas para o gateway PSTN apropriado.</span><span class="sxs-lookup"><span data-stu-id="83973-152">Calls to the PSTN are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="83973-153">O Lync 2013 ou o Lync Phone Edition serve como softphone.</span><span class="sxs-lookup"><span data-stu-id="83973-153">Lync 2013 or Lync Phone Edition serves as a softphone.</span></span> <span data-ttu-id="83973-154">O controle de chamada remota não está disponível e é desnecessário porque não há telefones PBX para que os usuários controlem.</span><span class="sxs-lookup"><span data-stu-id="83973-154">Remote call control is unavailable and unnecessary because there are no PBX phones for users to control.</span></span> <span data-ttu-id="83973-155">Os serviços de caixa postal e atendedor automático estão disponíveis por meio da implantação opcional da Unificação de mensagens (UM) do Exchange.</span><span class="sxs-lookup"><span data-stu-id="83973-155">Voice mail and auto-attendant services are available through the optional deployment of Exchange Unified Messaging (UM).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="83973-156">Além da infraestrutura de rede necessária para oferecer suporte ao Lync Server 2013, uma implantação somente VoIP pode usar um gateway pequeno e qualificado para suportar máquinas de fax e dispositivos analógicos.</span><span class="sxs-lookup"><span data-stu-id="83973-156">In addition to the network infrastructure that is required to support Lync Server 2013, a VoIP-only deployment can use a small, qualified gateway to support fax machines and analog devices.</span></span>



</div>

<span data-ttu-id="83973-157">A figura a seguir mostra uma topologia típica para uma implantação somente VoIP.</span><span class="sxs-lookup"><span data-stu-id="83973-157">The following figure shows a typical topology for a VoIP-only deployment.</span></span>

<span data-ttu-id="83973-158">**Opção de implantação somente VoIP**</span><span class="sxs-lookup"><span data-stu-id="83973-158">**VoIP-only deployment option**</span></span>

<span data-ttu-id="83973-159">![Opção de implantação Greenfidle](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Opção de implantação Greenfidle")</span><span class="sxs-lookup"><span data-stu-id="83973-159">![Greenfidle deployment option](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle deployment option")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="83973-160">O caminho de mídia mostrado nesta figura tem o bypass de mídia habilitado (a configuração recomendada).</span><span class="sxs-lookup"><span data-stu-id="83973-160">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="83973-161">Se você optar por desabilitar o bypass de mídia, o caminho de mídia será roteado através do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="83973-161">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

