---
title: 'Lync Server 2013: atributos de esquema por classe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema attributes by class
ms:assetid: 72726b43-f1ea-458c-9304-a26e8a12128c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398544(v=OCS.15)
ms:contentKeyID: 48184468
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86c2c4a494408f619fc7162c70cba0570b62bd09
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144139"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="schema-attributes-by-class-in-lync-server-2013"></a><span data-ttu-id="261b6-102">Atributos de esquema por classe no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="261b6-102">Schema attributes by class in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="261b6-103">_**Última modificação do tópico:** 2012-08-29_</span><span class="sxs-lookup"><span data-stu-id="261b6-103">_**Topic Last Modified:** 2012-08-29_</span></span>

<span data-ttu-id="261b6-104">Esta seção lista os atributos de esquema que podem estar contidos em cada classe do Lync Server 2013 e as classes que podem estar contidas em outras classes.</span><span class="sxs-lookup"><span data-stu-id="261b6-104">This section lists the schema attributes that can be contained in each Lync Server 2013 class and the classes that can be contained in other classes.</span></span> <span data-ttu-id="261b6-105">Para obter uma lista de todas as classes e suas descrições, consulte [classes e descrições de esquema no Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="261b6-105">For a list of all the classes and their descriptions, see [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="261b6-106">Para obter uma lista de todos os atributos e suas descrições, confira [atributos e descrições de esquema no Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="261b6-106">For a list of all the attributes and their descriptions, see [Schema attributes and descriptions in Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md).</span></span>

<div>

## <a name="attributes-by-class"></a><span data-ttu-id="261b6-107">Atributos de classe</span><span class="sxs-lookup"><span data-stu-id="261b6-107">Attributes by Class</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="261b6-108">Classe</span><span class="sxs-lookup"><span data-stu-id="261b6-108">Class</span></span></th>
<th><span data-ttu-id="261b6-109">Pode conter esses atributos</span><span class="sxs-lookup"><span data-stu-id="261b6-109">May contain these attributes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="261b6-110">Contato</span><span class="sxs-lookup"><span data-stu-id="261b6-110">Contact</span></span></p></td>
<td><p><span data-ttu-id="261b6-111">msDS-SourceObjectDN</span><span class="sxs-lookup"><span data-stu-id="261b6-111">msDS-SourceObjectDN</span></span></p>
<p><span data-ttu-id="261b6-112">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="261b6-112">msRTCSIP-AcpInfo</span></span></p>
<p><span data-ttu-id="261b6-113">msRTCSIP-ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="261b6-113">msRTCSIP-ApplicationDestination</span></span></p>
<p><span data-ttu-id="261b6-114">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="261b6-114">msRTCSIP-ApplicationOptions</span></span></p>
<p><span data-ttu-id="261b6-115">msRTCSIP-ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="261b6-115">msRTCSIP-ApplicationPrimaryLanguage</span></span></p>
<p><span data-ttu-id="261b6-116">msRTCSIP-ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="261b6-116">msRTCSIP-ApplicationSecondaryLanguages</span></span></p>
<p><span data-ttu-id="261b6-117">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="261b6-117">msRTCSIP-ArchivingEnabled</span></span></p>
<p><span data-ttu-id="261b6-118">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="261b6-118">msRTCSIP-DeploymentLocator</span></span></p>
<p><span data-ttu-id="261b6-119">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="261b6-119">msRTCSIP-FederationEnabled</span></span></p>
<p><span data-ttu-id="261b6-120">msRTCSIP-Groupingid</span><span class="sxs-lookup"><span data-stu-id="261b6-120">msRTCSIP-GroupingID</span></span></p>
<p><span data-ttu-id="261b6-121">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="261b6-121">msRTCSIP-InternetAccessEnabled</span></span></p>
<p><span data-ttu-id="261b6-122">Linha msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="261b6-122">msRTCSIP-Line</span></span></p>
<p><span data-ttu-id="261b6-123">msRTCSIP-LineServer</span><span class="sxs-lookup"><span data-stu-id="261b6-123">msRTCSIP-LineServer</span></span></p>
<p><span data-ttu-id="261b6-124">msRTCSIP-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="261b6-124">msRTCSIP-OptionFlags</span></span></p>
<p><span data-ttu-id="261b6-125">msRTCSIP-OriginatorSid</span><span class="sxs-lookup"><span data-stu-id="261b6-125">msRTCSIP-OriginatorSid</span></span></p>
<p><span data-ttu-id="261b6-126">msRTCSIP-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="261b6-126">msRTCSIP-OwnerUrn</span></span></p>
<p><span data-ttu-id="261b6-127">msRTCSIP-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="261b6-127">msRTCSIP-PrimaryHomeServer</span></span></p>
<p><span data-ttu-id="261b6-128">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="261b6-128">msRTCSIP-PrimaryUserAddress</span></span></p>
<p><span data-ttu-id="261b6-129">msRTCSIP-privado</span><span class="sxs-lookup"><span data-stu-id="261b6-129">msRTCSIP-PrivateLine</span></span></p>
<p><span data-ttu-id="261b6-130">msRTCSIP-ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="261b6-130">msRTCSIP-ProxyAddresses</span></span></p>
<p><span data-ttu-id="261b6-131">msRTCSIP-SourceObjectType</span><span class="sxs-lookup"><span data-stu-id="261b6-131">msRTCSIP-SourceObjectType</span></span></p>
<p><span data-ttu-id="261b6-132">msRTCSIP-TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="261b6-132">msRTCSIP-TargetHomeServer</span></span></p>
<p><span data-ttu-id="261b6-133">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="261b6-133">msRTCSIP-TargetUserPolicies</span></span></p>
<p><span data-ttu-id="261b6-134">msRTCSIP-Tenantid</span><span class="sxs-lookup"><span data-stu-id="261b6-134">msRTCSIP-TenantId</span></span></p>
<p><span data-ttu-id="261b6-135">msRTCSIP-userhabilitado</span><span class="sxs-lookup"><span data-stu-id="261b6-135">msRTCSIP-UserEnabled</span></span></p>
<p><span data-ttu-id="261b6-136">msRTCSIP-userextension</span><span class="sxs-lookup"><span data-stu-id="261b6-136">msRTCSIP-UserExtension</span></span></p>
<p><span data-ttu-id="261b6-137">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="261b6-137">msRTCSIP-UserLocationProfile</span></span></p>
<p><span data-ttu-id="261b6-138">msRTCSIP-userpolicies</span><span class="sxs-lookup"><span data-stu-id="261b6-138">msRTCSIP-UserPolicies</span></span></p>
<p><span data-ttu-id="261b6-139">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="261b6-139">msRTCSIP-UserPolicy</span></span></p>
<p><span data-ttu-id="261b6-140">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="261b6-140">msRTCSIP-UserRoutingGroupId</span></span></p>
<p><span data-ttu-id="261b6-141">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="261b6-141">ProxyAddresses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="261b6-142">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="261b6-142">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="261b6-143">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="261b6-143">msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="261b6-144">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="261b6-144">msExchUserHoldPolicies</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="261b6-145">msRTCSIP-ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="261b6-145">msRTCSIP-ApplicationServerService</span></span></p></td>
<td><p><span data-ttu-id="261b6-146">msRTCSIP-ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="261b6-146">msRTCSIP-ApplicationServerBL</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="261b6-147">msRTCSIP-ApplicationServerSettings</span><span class="sxs-lookup"><span data-stu-id="261b6-147">msRTCSIP-ApplicationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="261b6-148">msRTCSIP-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="261b6-148">msRTCSIP-ApplicationList</span></span></p>
<p><span data-ttu-id="261b6-149">msRTCSIP-ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="261b6-149">msRTCSIP-ApplicationServerPoolLink</span></span></p>
<p><span data-ttu-id="261b6-150">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="261b6-150">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="261b6-151">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="261b6-151">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="261b6-152">msRTCSIP-ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="261b6-152">msRTCSIP-ConferenceDirectory</span></span></p></td>
<td><p><span data-ttu-id="261b6-153">msRTCSIP-ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="261b6-153">msRTCSIP-ConferenceDirectoryHomePool</span></span></p>
<p><span data-ttu-id="261b6-154">msRTCSIP-ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="261b6-154">msRTCSIP-ConferenceDirectoryId</span></span></p>
<p><span data-ttu-id="261b6-155">msRTCSIP-ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="261b6-155">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p>
<p><span data-ttu-id="261b6-156">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="261b6-156">msRTCSIP-ExtensionData</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="261b6-157">msRTCSIP-DefaultCWABank</span><span class="sxs-lookup"><span data-stu-id="261b6-157">msRTCSIP-DefaultCWABank</span></span></p></td>
<td><p><span data-ttu-id="261b6-158">msRTCSIP-DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="261b6-158">msRTCSIP-DefaultCWAExternalURL</span></span></p>
<p><span data-ttu-id="261b6-159">msRTCSIP-DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="261b6-159">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="261b6-160">msRTCSIP-Domain</span><span class="sxs-lookup"><span data-stu-id="261b6-160">msRTCSIP-Domain</span></span></p></td>
<td><p><span data-ttu-id="261b6-161">msRTCSIP-padrão</span><span class="sxs-lookup"><span data-stu-id="261b6-161">msRTCSIP-Default</span></span></p>
<p><span data-ttu-id="261b6-162">msRTCSIP-DomainData</span><span class="sxs-lookup"><span data-stu-id="261b6-162">msRTCSIP-DomainData</span></span></p>
<p><span data-ttu-id="261b6-163">msRTCSIP-DomainName</span><span class="sxs-lookup"><span data-stu-id="261b6-163">msRTCSIP-DomainName</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="261b6-164">msRTCSIP-EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="261b6-164">msRTCSIP-EdgeProxy</span></span></p></td>
<td><p><span data-ttu-id="261b6-165">msRTCSIP-EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="261b6-165">msRTCSIP-EdgeProxyData</span></span></p>
<p><span data-ttu-id="261b6-166">msRTCSIP-EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="261b6-166">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="261b6-167">msRTCSIP-EnterpriseMCUSettings</span><span class="sxs-lookup"><span data-stu-id="261b6-167">msRTCSIP-EnterpriseMCUSettings</span></span></p></td>
<td><p><span data-ttu-id="261b6-168">msRTCSIP-MCUData</span><span class="sxs-lookup"><span data-stu-id="261b6-168">msRTCSIP-MCUData</span></span></p>
<p><span data-ttu-id="261b6-169">msRTCSIP-MCUFactoryAddress</span><span class="sxs-lookup"><span data-stu-id="261b6-169">msRTCSIP-MCUFactoryAddress</span></span></p>
<p><span data-ttu-id="261b6-170">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="261b6-170">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="261b6-171">msRTCSIP-EnterpriseMediationServerSettings</span><span class="sxs-lookup"><span data-stu-id="261b6-171">msRTCSIP-EnterpriseMediationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="261b6-172">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="261b6-172">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="261b6-173">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="261b6-173">msRTCSIP-ServerVersion</span></span></p>
<p><span data-ttu-id="261b6-174">msRTCSIP-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="261b6-174">msRTCSIP-TrustedServiceLinks</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="261b6-175">msRTCSIP-EnterpriseServerSettings</span><span class="sxs-lookup"><span data-stu-id="261b6-175">msRTCSIP-EnterpriseServerSettings</span></span></p></td>
<td><p><span data-ttu-id="261b6-176">msRTCSIP-EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="261b6-176">msRTCSIP-EnterpriseServices</span></span></p>
<p><span data-ttu-id="261b6-177">msRTCSIP-PoolAddress</span><span class="sxs-lookup"><span data-stu-id="261b6-177">msRTCSIP-PoolAddress</span></span></p>
<p><span data-ttu-id="261b6-178">msRTCSIP-Serverrestauração</span><span class="sxs-lookup"><span data-stu-id="261b6-178">msRTCSIP-ServerData</span></span></p>
<p><span data-ttu-id="261b6-179">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="261b6-179">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="261b6-180">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="261b6-180">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="261b6-181">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="261b6-181">msRTCSIP-BackEndServer</span></span></p>
<p><span data-ttu-id="261b6-182">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="261b6-182">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="261b6-183">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="261b6-183">msRTCSIP-MirrorBackEndServer</span></span></p>
<p><span data-ttu-id="261b6-184">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="261b6-184">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="261b6-185">msRTCSIP-LocalNormalization</span><span class="sxs-lookup"><span data-stu-id="261b6-185">msRTCSIP-LocalNormalization</span></span></p></td>
<td><p><span data-ttu-id="261b6-186">msRTCSIP-LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="261b6-186">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="261b6-187">msRTCSIP-LocationContactMapping</span><span class="sxs-lookup"><span data-stu-id="261b6-187">msRTCSIP-LocationContactMapping</span></span></p></td>
<td><p><span data-ttu-id="261b6-188">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="261b6-188">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="261b6-189">msRTCSIP-MappingContact</span><span class="sxs-lookup"><span data-stu-id="261b6-189">msRTCSIP-MappingContact</span></span></p>
<p><span data-ttu-id="261b6-190">msRTCSIP-MappingLocation</span><span class="sxs-lookup"><span data-stu-id="261b6-190">msRTCSIP-MappingLocation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="261b6-191">msRTCSIP-LocationProfile</span><span class="sxs-lookup"><span data-stu-id="261b6-191">msRTCSIP-LocationProfile</span></span></p></td>
<td><p><span data-ttu-id="261b6-192">msRTCSIP-ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="261b6-192">msRTCSIP-ExternalAccessCode</span></span></p>
<p><span data-ttu-id="261b6-193">msRTCSIP-LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="261b6-193">msRTCSIP-LocationProfileOptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="261b6-194">msRTCSIP-MCUFactory</span><span class="sxs-lookup"><span data-stu-id="261b6-194">msRTCSIP-MCUFactory</span></span></p></td>
<td><p><span data-ttu-id="261b6-195">msRTCSIP-MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="261b6-195">msRTCSIP-MCUFactoryData</span></span></p>
<p><span data-ttu-id="261b6-196">msRTCSIP-MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="261b6-196">msRTCSIP-MCUFactoryProviderID</span></span></p>
<p><span data-ttu-id="261b6-197">msRTCSIP-MCUServers</span><span class="sxs-lookup"><span data-stu-id="261b6-197">msRTCSIP-MCUServers</span></span></p>
<p><span data-ttu-id="261b6-198">msRTCSIP-MCUType</span><span class="sxs-lookup"><span data-stu-id="261b6-198">msRTCSIP-MCUType</span></span></p>
<p><span data-ttu-id="261b6-199">msRTCSIP-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="261b6-199">msRTCSIP-MCUVendor</span></span></p>
<p><span data-ttu-id="261b6-200">msRTCSIP-PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="261b6-200">msRTCSIP-PoolAddresses</span></span></p>
<p><span data-ttu-id="261b6-201">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="261b6-201">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="261b6-202">msRTCSIP-MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="261b6-202">msRTCSIP-MCUFactoryService</span></span></p></td>
<td><p><span data-ttu-id="261b6-203">msRTCSIP-MCUFactoryPath</span><span class="sxs-lookup"><span data-stu-id="261b6-203">msRTCSIP-MCUFactoryPath</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="261b6-204">msRTCSIP-mobilidade</span><span class="sxs-lookup"><span data-stu-id="261b6-204">msRTCSIP-Mobility</span></span></p></td>
<td><p><span data-ttu-id="261b6-205">msRTCSIP-MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="261b6-205">msRTCSIP-MobilityFlags</span></span></p>
<p><span data-ttu-id="261b6-206">msRTCSIP-MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="261b6-206">msRTCSIP-MobilityPolicy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="261b6-207">msRTCSIP-MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="261b6-207">msRTCSIP-MonitoringServer</span></span></p></td>
<td><p><span data-ttu-id="261b6-208">dnsHostName</span><span class="sxs-lookup"><span data-stu-id="261b6-208">dnsHostName</span></span></p>
<p><span data-ttu-id="261b6-209">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="261b6-209">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="261b6-210">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="261b6-210">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="261b6-211">msRTCSIP-pool</span><span class="sxs-lookup"><span data-stu-id="261b6-211">msRTCSIP-Pool</span></span></p></td>
<td><p><span data-ttu-id="261b6-212">msRTCSIP-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="261b6-212">msRTCSIP-ApplicationList</span></span></p>
<p><span data-ttu-id="261b6-213">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="261b6-213">msRTCSIP-BackEndServer</span></span></p>
<p><span data-ttu-id="261b6-214">msRTCSIP-dnsHostName</span><span class="sxs-lookup"><span data-stu-id="261b6-214">msRTCSIP-dnsHostName</span></span></p>
<p><span data-ttu-id="261b6-215">msRTCSIP-PoolData</span><span class="sxs-lookup"><span data-stu-id="261b6-215">msRTCSIP-PoolData</span></span></p>
<p><span data-ttu-id="261b6-216">msRTCSIP-PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="261b6-216">msRTCSIP-PoolDisplayName</span></span></p>
<p><span data-ttu-id="261b6-217">msRTCSIP-PoolDomainFQDN</span><span class="sxs-lookup"><span data-stu-id="261b6-217">msRTCSIP-PoolDomainFQDN</span></span></p>
<p><span data-ttu-id="261b6-218">msRTCSIP-PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="261b6-218">msRTCSIP-PoolFunctionality</span></span></p>
<p><span data-ttu-id="261b6-219">msRTCSIP-Pooltype</span><span class="sxs-lookup"><span data-stu-id="261b6-219">msRTCSIP-PoolType</span></span></p>
<p><span data-ttu-id="261b6-220">msRTCSIP-PoolVersion</span><span class="sxs-lookup"><span data-stu-id="261b6-220">msRTCSIP-PoolVersion</span></span></p>
<p><span data-ttu-id="261b6-221">msRTCSIP-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="261b6-221">msRTCSIP-TrustedServiceLinks</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="261b6-222">msRTCSIP-PoolService</span><span class="sxs-lookup"><span data-stu-id="261b6-222">msRTCSIP-PoolService</span></span></p></td>
<td><p><span data-ttu-id="261b6-223">msRTCSIP-FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="261b6-223">msRTCSIP-FrontEndServers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="261b6-224">msRTCSIP-Presence</span><span class="sxs-lookup"><span data-stu-id="261b6-224">msRTCSIP-Presence</span></span></p></td>
<td><p><span data-ttu-id="261b6-225">msRTCSIP-PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="261b6-225">msRTCSIP-PresenceFlags</span></span></p>
<p><span data-ttu-id="261b6-226">msRTCSIP-PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="261b6-226">msRTCSIP-PresencePolicy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="261b6-227">msRTCSIP-TrustedMCU</span><span class="sxs-lookup"><span data-stu-id="261b6-227">msRTCSIP-TrustedMCU</span></span></p></td>
<td><p><span data-ttu-id="261b6-228">msRTCSIP-MCUType</span><span class="sxs-lookup"><span data-stu-id="261b6-228">msRTCSIP-MCUType</span></span></p>
<p><span data-ttu-id="261b6-229">msRTCSIP-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="261b6-229">msRTCSIP-MCUVendor</span></span></p>
<p><span data-ttu-id="261b6-230">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="261b6-230">msRTCSIP-RoutingPoolDN</span></span></p>
<p><span data-ttu-id="261b6-231">msRTCSIP-TrustedMCUData</span><span class="sxs-lookup"><span data-stu-id="261b6-231">msRTCSIP-TrustedMCUData</span></span></p>
<p><span data-ttu-id="261b6-232">msRTCSIP-TrustedMCUFQDN</span><span class="sxs-lookup"><span data-stu-id="261b6-232">msRTCSIP-TrustedMCUFQDN</span></span></p>
<p><span data-ttu-id="261b6-233">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="261b6-233">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="261b6-234">msRTCSIP-TrustedProxy</span><span class="sxs-lookup"><span data-stu-id="261b6-234">msRTCSIP-TrustedProxy</span></span></p></td>
<td><p><span data-ttu-id="261b6-235">msRTCSIP-TrustedProxyData</span><span class="sxs-lookup"><span data-stu-id="261b6-235">msRTCSIP-TrustedProxyData</span></span></p>
<p><span data-ttu-id="261b6-236">msRTCSIP-TrustedProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="261b6-236">msRTCSIP-TrustedProxyFQDN</span></span></p>
<p><span data-ttu-id="261b6-237">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="261b6-237">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="261b6-238">msRTCSIP-TrustedServer</span><span class="sxs-lookup"><span data-stu-id="261b6-238">msRTCSIP-TrustedServer</span></span></p></td>
<td><p><span data-ttu-id="261b6-239">msRTCSIP-TrustedServerData</span><span class="sxs-lookup"><span data-stu-id="261b6-239">msRTCSIP-TrustedServerData</span></span></p>
<p><span data-ttu-id="261b6-240">msRTCSIP-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="261b6-240">msRTCSIP-TrustedServerFQDN</span></span></p>
<p><span data-ttu-id="261b6-241">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="261b6-241">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="261b6-242">msRTCSIP-TrustedService</span><span class="sxs-lookup"><span data-stu-id="261b6-242">msRTCSIP-TrustedService</span></span></p></td>
<td><p><span data-ttu-id="261b6-243">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="261b6-243">msRTCSIP-ExtensionData</span></span></p>
<p><span data-ttu-id="261b6-244">msRTCSIP-roteável</span><span class="sxs-lookup"><span data-stu-id="261b6-244">msRTCSIP-Routable</span></span></p>
<p><span data-ttu-id="261b6-245">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="261b6-245">msRTCSIP-RoutingPoolDN</span></span></p>
<p><span data-ttu-id="261b6-246">msRTCSIP-ServerBL</span><span class="sxs-lookup"><span data-stu-id="261b6-246">msRTCSIP-ServerBL</span></span></p>
<p><span data-ttu-id="261b6-247">msRTCSIP-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="261b6-247">msRTCSIP-TrustedServerFQDN</span></span></p>
<p><span data-ttu-id="261b6-248">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="261b6-248">msRTCSIP-TrustedServerVersion</span></span></p>
<p><span data-ttu-id="261b6-249">msRTCSIP-TrustedServiceFlags</span><span class="sxs-lookup"><span data-stu-id="261b6-249">msRTCSIP-TrustedServiceFlags</span></span></p>
<p><span data-ttu-id="261b6-250">msRTCSIP-TrustedServicePort</span><span class="sxs-lookup"><span data-stu-id="261b6-250">msRTCSIP-TrustedServicePort</span></span></p>
<p><span data-ttu-id="261b6-251">msRTCSIP-TrustedServiceType</span><span class="sxs-lookup"><span data-stu-id="261b6-251">msRTCSIP-TrustedServiceType</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="261b6-252">msRTCSIP-TrustedWebComponentsServer</span><span class="sxs-lookup"><span data-stu-id="261b6-252">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
<td><p><span data-ttu-id="261b6-253">msRTCSIP-TrustedWebComponentsServerData</span><span class="sxs-lookup"><span data-stu-id="261b6-253">msRTCSIP-TrustedWebComponentsServerData</span></span></p>
<p><span data-ttu-id="261b6-254">msRTCSIP-TrustedWebComponentsServerFQDN</span><span class="sxs-lookup"><span data-stu-id="261b6-254">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p>
<p><span data-ttu-id="261b6-255">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="261b6-255">msRTCSIP-TrustedServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="261b6-256">msRTCSIP-WebComponentsService</span><span class="sxs-lookup"><span data-stu-id="261b6-256">msRTCSIP-WebComponentsService</span></span></p></td>
<td><p><span data-ttu-id="261b6-257">msRTCSIP-WebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="261b6-257">msRTCSIP-WebComponentsServers</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="261b6-258">msRTCSIP-WebComponentSettings</span><span class="sxs-lookup"><span data-stu-id="261b6-258">msRTCSIP-WebComponentSettings</span></span></p></td>
<td><p><span data-ttu-id="261b6-259">msRTCSIP-WebComponentsData</span><span class="sxs-lookup"><span data-stu-id="261b6-259">msRTCSIP-WebComponentsData</span></span></p>
<p><span data-ttu-id="261b6-260">msRTCSIP-WebComponentsPoolAddress</span><span class="sxs-lookup"><span data-stu-id="261b6-260">msRTCSIP-WebComponentsPoolAddress</span></span></p>
<p><span data-ttu-id="261b6-261">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="261b6-261">msRTCSIP-ServerVersion</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="261b6-262">Usuário</span><span class="sxs-lookup"><span data-stu-id="261b6-262">User</span></span></p></td>
<td><p><span data-ttu-id="261b6-263">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="261b6-263">msRTCSIP-AcpInfo</span></span></p>
<p><span data-ttu-id="261b6-264">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="261b6-264">msRTCSIP-ApplicationOptions</span></span></p>
<p><span data-ttu-id="261b6-265">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="261b6-265">msRTCSIP-ArchivingEnabled</span></span></p>
<p><span data-ttu-id="261b6-266">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="261b6-266">msRTCSIP-DeploymentLocator</span></span></p>
<p><span data-ttu-id="261b6-267">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="261b6-267">msRTCSIP-FederationEnabled</span></span></p>
<p><span data-ttu-id="261b6-268">msRTCSIP-Groupingid</span><span class="sxs-lookup"><span data-stu-id="261b6-268">msRTCSIP-GroupingID</span></span></p>
<p><span data-ttu-id="261b6-269">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="261b6-269">msRTCSIP-InternetAccessEnabled</span></span></p>
<p><span data-ttu-id="261b6-270">Linha msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="261b6-270">msRTCSIP-Line</span></span></p>
<p><span data-ttu-id="261b6-271">msRTCSIP-LineServer</span><span class="sxs-lookup"><span data-stu-id="261b6-271">msRTCSIP-LineServer</span></span></p>
<p><span data-ttu-id="261b6-272">msRTCSIP-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="261b6-272">msRTCSIP-OptionFlags</span></span></p>
<p><span data-ttu-id="261b6-273">msRTCSIP-OriginatorSid</span><span class="sxs-lookup"><span data-stu-id="261b6-273">msRTCSIP-OriginatorSid</span></span></p>
<p><span data-ttu-id="261b6-274">msRTCSIP-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="261b6-274">msRTCSIP-OwnerUrn</span></span></p>
<p><span data-ttu-id="261b6-275">msRTCSIP-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="261b6-275">msRTCSIP-PrimaryHomeServer</span></span></p>
<p><span data-ttu-id="261b6-276">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="261b6-276">msRTCSIP-PrimaryUserAddress</span></span></p>
<p><span data-ttu-id="261b6-277">msRTCSIP-privado</span><span class="sxs-lookup"><span data-stu-id="261b6-277">msRTCSIP-PrivateLine</span></span></p>
<p><span data-ttu-id="261b6-278">msRTCSIP-TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="261b6-278">msRTCSIP-TargetHomeServer</span></span></p>
<p><span data-ttu-id="261b6-279">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="261b6-279">msRTCSIP-TargetUserPolicies</span></span></p>
<p><span data-ttu-id="261b6-280">msRTCSIP-Tenantid</span><span class="sxs-lookup"><span data-stu-id="261b6-280">msRTCSIP-TenantId</span></span></p>
<p><span data-ttu-id="261b6-281">msRTCSIP-userhabilitado</span><span class="sxs-lookup"><span data-stu-id="261b6-281">msRTCSIP-UserEnabled</span></span></p>
<p><span data-ttu-id="261b6-282">msRTCSIP-userextension</span><span class="sxs-lookup"><span data-stu-id="261b6-282">msRTCSIP-UserExtension</span></span></p>
<p><span data-ttu-id="261b6-283">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="261b6-283">msRTCSIP-UserLocationProfile</span></span></p>
<p><span data-ttu-id="261b6-284">msRTCSIP-userpolicies</span><span class="sxs-lookup"><span data-stu-id="261b6-284">msRTCSIP-UserPolicies</span></span></p>
<p><span data-ttu-id="261b6-285">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="261b6-285">msRTCSIP-UserPolicy</span></span></p>
<p><span data-ttu-id="261b6-286">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="261b6-286">msRTCSIP-UserRoutingGroupId</span></span></p>
<p><span data-ttu-id="261b6-287">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="261b6-287">ProxyAddresses</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="classes-contained-in-other-classes"></a><span data-ttu-id="261b6-288">Classes contidas em outras classes</span><span class="sxs-lookup"><span data-stu-id="261b6-288">Classes Contained in Other Classes</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="261b6-289">Classe</span><span class="sxs-lookup"><span data-stu-id="261b6-289">Class</span></span></th>
<th><span data-ttu-id="261b6-290">Pode conter esta classe</span><span class="sxs-lookup"><span data-stu-id="261b6-290">May contain this class</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="261b6-291">serviceConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="261b6-291">serviceConnectionPoint</span></span></p></td>
<td><p><span data-ttu-id="261b6-292">msRTCSIP-Server</span><span class="sxs-lookup"><span data-stu-id="261b6-292">msRTCSIP-Server</span></span></p>
<p><span data-ttu-id="261b6-293">msRTCSIP-PoolService</span><span class="sxs-lookup"><span data-stu-id="261b6-293">msRTCSIP-PoolService</span></span></p>
<p><span data-ttu-id="261b6-294">msRTCSIP-MCU</span><span class="sxs-lookup"><span data-stu-id="261b6-294">msRTCSIP-MCU</span></span></p>
<p><span data-ttu-id="261b6-295">msRTCSIP-MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="261b6-295">msRTCSIP-MCUFactoryService</span></span></p>
<p><span data-ttu-id="261b6-296">msRTCSIP-WebComponents</span><span class="sxs-lookup"><span data-stu-id="261b6-296">msRTCSIP-WebComponents</span></span></p>
<p><span data-ttu-id="261b6-297">msRTCSIP-WebComponentsService</span><span class="sxs-lookup"><span data-stu-id="261b6-297">msRTCSIP-WebComponentsService</span></span></p>
<p><span data-ttu-id="261b6-298">msRTCSIP-ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="261b6-298">msRTCSIP-ApplicationServerService</span></span></p>
<p><span data-ttu-id="261b6-299">msRTCSIP-Service</span><span class="sxs-lookup"><span data-stu-id="261b6-299">msRTCSIP-Service</span></span></p>
<p><span data-ttu-id="261b6-300">msRTCSIP-ConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="261b6-300">msRTCSIP-ConnectionPoint</span></span></p>
<p><span data-ttu-id="261b6-301">msRTCSIP-MediationServer</span><span class="sxs-lookup"><span data-stu-id="261b6-301">msRTCSIP-MediationServer</span></span></p>
<p><span data-ttu-id="261b6-302">msRTCSIP-ApplicationServer</span><span class="sxs-lookup"><span data-stu-id="261b6-302">msRTCSIP-ApplicationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="261b6-303">msRTCSIP-Service</span><span class="sxs-lookup"><span data-stu-id="261b6-303">msRTCSIP-Service</span></span></p></td>
<td><p><span data-ttu-id="261b6-304">msRTCSIP-GlobalContainer</span><span class="sxs-lookup"><span data-stu-id="261b6-304">msRTCSIP-GlobalContainer</span></span></p>
<p><span data-ttu-id="261b6-305">msRTCSIP-Pools</span><span class="sxs-lookup"><span data-stu-id="261b6-305">msRTCSIP-Pools</span></span></p>
<p><span data-ttu-id="261b6-306">msRTCSIP-MCUFactories</span><span class="sxs-lookup"><span data-stu-id="261b6-306">msRTCSIP-MCUFactories</span></span></p>
<p><span data-ttu-id="261b6-307">msRTCSIP-TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="261b6-307">msRTCSIP-TrustedMCUs</span></span></p>
<p><span data-ttu-id="261b6-308">msRTCSIP-TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="261b6-308">msRTCSIP-TrustedWebComponentsServers</span></span></p>
<p><span data-ttu-id="261b6-309">msRTCSIP-TrustedProxies</span><span class="sxs-lookup"><span data-stu-id="261b6-309">msRTCSIP-TrustedProxies</span></span></p>
<p><span data-ttu-id="261b6-310">msRTCSIP-Trustservices</span><span class="sxs-lookup"><span data-stu-id="261b6-310">msRTCSIP-TrustedServices</span></span></p>
<p><span data-ttu-id="261b6-311">msRTCSIP-ApplicationContacts</span><span class="sxs-lookup"><span data-stu-id="261b6-311">msRTCSIP-ApplicationContacts</span></span></p>
<p><span data-ttu-id="261b6-312">msRTCSIP-LocationContactMappings</span><span class="sxs-lookup"><span data-stu-id="261b6-312">msRTCSIP-LocationContactMappings</span></span></p>
<p><span data-ttu-id="261b6-313">msRTCSIP-ConferenceDirectories</span><span class="sxs-lookup"><span data-stu-id="261b6-313">msRTCSIP-ConferenceDirectories</span></span></p>
<p><span data-ttu-id="261b6-314">msRTCSIP-GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="261b6-314">msRTCSIP-GlobalTopologySettings</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="261b6-315">msRTCSIP-GlobalContainer</span><span class="sxs-lookup"><span data-stu-id="261b6-315">msRTCSIP-GlobalContainer</span></span></p></td>
<td><p><span data-ttu-id="261b6-316">msRTCSIP-Domain</span><span class="sxs-lookup"><span data-stu-id="261b6-316">msRTCSIP-Domain</span></span></p>
<p><span data-ttu-id="261b6-317">msRTCSIP-TrustedServer</span><span class="sxs-lookup"><span data-stu-id="261b6-317">msRTCSIP-TrustedServer</span></span></p>
<p><span data-ttu-id="261b6-318">msRTCSIP-EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="261b6-318">msRTCSIP-EdgeProxy</span></span></p>
<p><span data-ttu-id="261b6-319">msRTCSIP-MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="261b6-319">msRTCSIP-MonitoringServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="261b6-320">msRTCSIP-Pools</span><span class="sxs-lookup"><span data-stu-id="261b6-320">msRTCSIP-Pools</span></span></p></td>
<td><p><span data-ttu-id="261b6-321">msRTCSIP-pool</span><span class="sxs-lookup"><span data-stu-id="261b6-321">msRTCSIP-Pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="261b6-322">msRTCSIP-MCUFactories</span><span class="sxs-lookup"><span data-stu-id="261b6-322">msRTCSIP-MCUFactories</span></span></p></td>
<td><p><span data-ttu-id="261b6-323">msRTCSIP-MCUFactory</span><span class="sxs-lookup"><span data-stu-id="261b6-323">msRTCSIP-MCUFactory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="261b6-324">msRTCSIP-TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="261b6-324">msRTCSIP-TrustedMCUs</span></span></p></td>
<td><p><span data-ttu-id="261b6-325">msRTCSIP-TrustedMCU</span><span class="sxs-lookup"><span data-stu-id="261b6-325">msRTCSIP-TrustedMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="261b6-326">msRTCSIP-TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="261b6-326">msRTCSIP-TrustedWebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="261b6-327">msRTCSIP-TrustedWebComponentsServer</span><span class="sxs-lookup"><span data-stu-id="261b6-327">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="261b6-328">msRTCSIP-TrustedProxies</span><span class="sxs-lookup"><span data-stu-id="261b6-328">msRTCSIP-TrustedProxies</span></span></p></td>
<td><p><span data-ttu-id="261b6-329">msRTCSIP-TrustedProxy</span><span class="sxs-lookup"><span data-stu-id="261b6-329">msRTCSIP-TrustedProxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="261b6-330">msRTCSIP-Trustservices</span><span class="sxs-lookup"><span data-stu-id="261b6-330">msRTCSIP-TrustedServices</span></span></p></td>
<td><p><span data-ttu-id="261b6-331">msRTCSIP-TrustedService</span><span class="sxs-lookup"><span data-stu-id="261b6-331">msRTCSIP-TrustedService</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="261b6-332">msRTCSIP-LocationContactMappings</span><span class="sxs-lookup"><span data-stu-id="261b6-332">msRTCSIP-LocationContactMappings</span></span></p></td>
<td><p><span data-ttu-id="261b6-333">msRTCSIP-LocationContactMapping</span><span class="sxs-lookup"><span data-stu-id="261b6-333">msRTCSIP-LocationContactMapping</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="261b6-334">msRTCSIP-ConferenceDirectories</span><span class="sxs-lookup"><span data-stu-id="261b6-334">msRTCSIP-ConferenceDirectories</span></span></p></td>
<td><p><span data-ttu-id="261b6-335">msRTCSIP-ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="261b6-335">msRTCSIP-ConferenceDirectory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="261b6-336">msRTCSIP-GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="261b6-336">msRTCSIP-GlobalTopologySettings</span></span></p></td>
<td><p><span data-ttu-id="261b6-337">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="261b6-337">msRTCSIP-GlobalTopologySetting</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

