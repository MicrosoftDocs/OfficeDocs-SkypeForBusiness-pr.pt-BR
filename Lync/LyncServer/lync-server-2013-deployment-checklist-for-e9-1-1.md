---
title: 'Lync Server 2013: lista de verificação de implantação para E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for E9-1-1
ms:assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398864(v=OCS.15)
ms:contentKeyID: 48185655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9a48ba3d999e55106298d7419e4590147e1e9e5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829512"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="46a60-102">Lista de verificação de implantação do E9-1-1 no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46a60-102">Deployment checklist for E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46a60-103">_**Tópico da última modificação:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="46a60-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="46a60-104">Para planejar com eficiência o 9-1-1 aprimorado (E9-1-1), certifique-se de incluir os seguintes requisitos de implantação:</span><span class="sxs-lookup"><span data-stu-id="46a60-104">To plan effectively for Enhanced 9-1-1 (E9-1-1), be sure to include the following deployment requirements:</span></span>

  - <span data-ttu-id="46a60-105">Pré-requisitos para a implantação do E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="46a60-105">Prerequisites for deploying E9-1-1.</span></span>

  - <span data-ttu-id="46a60-106">Etapas necessárias para implantar o E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="46a60-106">Steps that are required to deploy E9-1-1.</span></span>

<div>

## <a name="deployment-prerequisites-for-e9-1-1"></a><span data-ttu-id="46a60-107">Pré-requisitos de implantação para E9-1-1</span><span class="sxs-lookup"><span data-stu-id="46a60-107">Deployment Prerequisites for E9-1-1</span></span>

<span data-ttu-id="46a60-108">Antes de implantar o E9-1-1, você já deve ter implantado seus servidores internos do Lync Server, incluindo um repositório de gerenciamento central, um pool de front-end ou um servidor Standard Edition, um ou mais servidores de mediação ou pools de servidores de mediação e clientes do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="46a60-108">Before you deploy E9-1-1, you must already have deployed your Lync Server internal servers, including a Central Management store, a Front End pool or a Standard Edition server, one or more Mediation Servers or Mediation Server pools, and Lync Server clients.</span></span> <span data-ttu-id="46a60-109">Além disso, uma implantação do E9-1-1 exige um tronco SIP para um provedor de serviços de E9-1-1 qualificado ou um gateway ELIN (Número de Identificação de Local de Emergência) para sua PSTN (Rede Telefônica Pública Comutada).</span><span class="sxs-lookup"><span data-stu-id="46a60-109">In addition, an E9-1-1 deployment requires a SIP trunk to a qualified E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway to your public switched telephone network (PSTN).</span></span> <span data-ttu-id="46a60-110">O Lync Server oferece suporte ao uso de provedores de serviços E9-1-1 apenas nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="46a60-110">Lync Server supports using E9-1-1 service providers only inside the United States.</span></span>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="46a60-111">Processo de implantação</span><span class="sxs-lookup"><span data-stu-id="46a60-111">Deployment Process</span></span>

<span data-ttu-id="46a60-112">A tabela a seguir fornece uma visão geral do processo de implantação de E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="46a60-112">The following table provides an overview of the E9-1-1 deployment process.</span></span> <span data-ttu-id="46a60-113">Para obter detalhes sobre etapas de implantação, consulte [Configurar o 9-1-1 aprimorado no Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="46a60-113">For details about deployment steps, see [Configure Enhanced 9-1-1 in Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46a60-114">Fase</span><span class="sxs-lookup"><span data-stu-id="46a60-114">Phase</span></span></th>
<th><span data-ttu-id="46a60-115">Etapas</span><span class="sxs-lookup"><span data-stu-id="46a60-115">Steps</span></span></th>
<th><span data-ttu-id="46a60-116">Funções</span><span class="sxs-lookup"><span data-stu-id="46a60-116">Roles</span></span></th>
<th><span data-ttu-id="46a60-117">Documentação de implantação</span><span class="sxs-lookup"><span data-stu-id="46a60-117">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46a60-118">Definir utilização de voz, rotas e configurações de tronco</span><span class="sxs-lookup"><span data-stu-id="46a60-118">Configure voice usages, routes, and trunk configurations</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="46a60-p103">Crie um novo registro de uso de PSTN. Este é o mesmo nome utilizado para a configuração de <strong>Uso do PSTN</strong> na política de local.</span><span class="sxs-lookup"><span data-stu-id="46a60-p103">Create a new PSTN usage record. This is the same name that is used for the <strong>PSTN Usage</strong> setting in the location policy.</span></span></p></li>
<li><p><span data-ttu-id="46a60-121">Crie ou atribua uma rota de voz ao registro de uso do PSTN criado na etapa anterior e aponte o atributo gateway para o tronco SIP ou gateway ELIN de E9-1-1. </span><span class="sxs-lookup"><span data-stu-id="46a60-121">Create or assign a voice route to the PSTN usage record created in the previous step and then point the gateway attribute to the E9-1-1 SIP trunk or ELIN gateway.</span></span></p></li>
<li><p><span data-ttu-id="46a60-122">Para um provedor de serviços E9-1-1 por tronco SIP, configure o tronco que tratará das chamadas do serviço E9-1-1 sobre SIP para passar os dados de PIDF-LO usando o cmdlet <strong>Set-CsTrunkConfiguration –EnablePIDFLOSupport</strong>.</span><span class="sxs-lookup"><span data-stu-id="46a60-122">For a SIP trunk E9-1-1 service provider, set the trunk that will be handling E9-1-1 calls over the SIP to pass PIDF-LO data by using the <strong>Set-CsTrunkConfiguration –EnablePIDFLOSupport</strong> cmdlet.</span></span></p></li>
<li><p><span data-ttu-id="46a60-p104">Opcionalmente, para um provedor de serviços de E9-1-1 do tronco SIP, crie ou atribua uma rota PSTN local para chamadas que não são manipuladas pelo tronco SIP do provedor de serviços de E9-1-1. Essa rota será usada se a conexão com o provedor de serviços de E9-1-1 não estiver disponível. Se houver suporte para o provedor de serviços de E9-1-1, atribua uma regra de configuração de tronco ao gateway que converte a cadeia de caracteres de discagem 911 no número DID (discagem direta interna) do ECRC (Centro de resposta de chamada de emergência) nacional.</span><span class="sxs-lookup"><span data-stu-id="46a60-p104">Optionally, for a SIP trunk E9-1-1 service provider, create or assign a local PSTN route for calls that are not handled by the E9-1-1 service provider’s SIP trunk. This route will be used if the connection to the E9-1-1 service provider is not available. If supported by your E9-1-1 service provider, assign a trunk configuration rule to the gateway that translates the 911 dial string into the direct inward dialing (DID) number of the national/regional Emergency Call Response Center (ECRC).</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="46a60-126">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="46a60-126">CSVoiceAdmin</span></span></p></td>
<td><p><span data-ttu-id="46a60-127"><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Configurar uma rota de voz E9-1-1 no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="46a60-127"><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Configure an E9-1-1 voice route in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46a60-128">Criar políticas locais e atribuí-las aos usuários e sub-redes</span><span class="sxs-lookup"><span data-stu-id="46a60-128">Create location policies and assign them to users and subnets</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="46a60-129">Revise a política de de local global.</span><span class="sxs-lookup"><span data-stu-id="46a60-129">Review the global location policy.</span></span></p></li>
<li><p><span data-ttu-id="46a60-130">Crie uma política de local com um escopo no nível do usuário ou no nível do site de rede, se a organização tiver mais de um site com diferentes usos de emergência.</span><span class="sxs-lookup"><span data-stu-id="46a60-130">Create a location policy with a user-level scope; or, if the organization has more than one site with different emergency usages, create a location policy with a network-level scope.</span></span></p></li>
<li><p><span data-ttu-id="46a60-131">Atribua a política de local aos sites de rede.</span><span class="sxs-lookup"><span data-stu-id="46a60-131">Assign the location policy to network sites.</span></span></p></li>
<li><p><span data-ttu-id="46a60-132">Adicione as sub-redes apropriadas ao site da rede.</span><span class="sxs-lookup"><span data-stu-id="46a60-132">Add the appropriate subnets to the network site.</span></span></p></li>
<li><p><span data-ttu-id="46a60-133">(Opcional) Atribua a política de local às políticas de usuário.</span><span class="sxs-lookup"><span data-stu-id="46a60-133">(Optional) Assign the location policy to user policies.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="46a60-134">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="46a60-134">CSVoiceAdmin</span></span></p>
<p><span data-ttu-id="46a60-135">CSLocationAdmin (exceto para a criação de Políticas de Local)</span><span class="sxs-lookup"><span data-stu-id="46a60-135">CSLocationAdmin (except for creating Location Policies)</span></span></p></td>
<td><p><span data-ttu-id="46a60-136"><a href="lync-server-2013-create-location-policies.md">Criar políticas de localização no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="46a60-136"><a href="lync-server-2013-create-location-policies.md">Create location policies in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="46a60-137"><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Adicionar uma política de localização a um site de rede no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="46a60-137"><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Add a location policy to a network site in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="46a60-138"><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">Associar sub-redes a sites de rede para E9-1-1 no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="46a60-138"><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">Associate subnets with network sites for E9-1-1 in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46a60-139">Configurar o banco de dados de localização</span><span class="sxs-lookup"><span data-stu-id="46a60-139">Configure the location database</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="46a60-140">Preencha o banco de dados com um mapeamento de elementos de rede para os locais.</span><span class="sxs-lookup"><span data-stu-id="46a60-140">Populate the database with a mapping of network elements to locations.</span></span></p></li>
<li><p><span data-ttu-id="46a60-141">Para gateways ELIN, adicione o ELINs à coluna &lt;CompanyName&gt; .</span><span class="sxs-lookup"><span data-stu-id="46a60-141">For ELIN gateways, add the ELINs to the &lt;CompanyName&gt; column.</span></span></p></li>
<li><p><span data-ttu-id="46a60-142">Configure a conexão com o provedor de serviço de E9-1-1 para endereços de validação.</span><span class="sxs-lookup"><span data-stu-id="46a60-142">Configure the connection to the E9-1-1 service provider for validating addresses.</span></span></p></li>
<li><p><span data-ttu-id="46a60-143">Valide os endereços com o provedor de serviço de E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="46a60-143">Validate the addresses with the E9-1-1 service provider.</span></span></p></li>
<li><p><span data-ttu-id="46a60-144">Publique o banco de dados atualizado.</span><span class="sxs-lookup"><span data-stu-id="46a60-144">Publish the updated database.</span></span></p></li>
<li><p><span data-ttu-id="46a60-145">Para gateways ELIN, carregue os ELINs no banco de dados de ALI (Automatic Location Identification) da operadora de seu PSTN.</span><span class="sxs-lookup"><span data-stu-id="46a60-145">For ELIN gateways, upload the ELINs to your PSTN carrier's Automatic Location Identification (ALI) database.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="46a60-146">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="46a60-146">CSVoiceAdmin</span></span></p>
<p><span data-ttu-id="46a60-147">CSLocationAdmin</span><span class="sxs-lookup"><span data-stu-id="46a60-147">CSLocationAdmin</span></span></p></td>
<td><p><span data-ttu-id="46a60-148"><a href="lync-server-2013-configure-the-location-database.md">Configure the location database in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="46a60-148"><a href="lync-server-2013-configure-the-location-database.md">Configure the location database in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46a60-149">Configure os Recursos Avançados (opcional)</span><span class="sxs-lookup"><span data-stu-id="46a60-149">Configure Advanced Features (optional)</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="46a60-150">Configure a URL para o aplicativo SNMP.</span><span class="sxs-lookup"><span data-stu-id="46a60-150">Configure the URL for the SNMP application.</span></span></p></li>
<li><p><span data-ttu-id="46a60-151">Configure a URL para o local do serviço de informações de localização secundário.</span><span class="sxs-lookup"><span data-stu-id="46a60-151">Configure the URL for the location of the Secondary Location Information service.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="46a60-152">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="46a60-152">CSVoiceAdmin</span></span></p></td>
<td><p><span data-ttu-id="46a60-153"><a href="lync-server-2013-configure-an-snmp-application.md">Configurar um aplicativo SNMP no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="46a60-153"><a href="lync-server-2013-configure-an-snmp-application.md">Configure an SNMP application in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="46a60-154"><a href="lync-server-2013-configure-a-secondary-location-information-service.md">Configurar um serviço de informações de localização secundário no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="46a60-154"><a href="lync-server-2013-configure-a-secondary-location-information-service.md">Configure a secondary Location Information service in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

