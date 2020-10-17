---
title: 'Lync Server 2013: classes e descrições de esquema'
description: 'Lync Server 2013: classes e descrições de esquema.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema classes and descriptions
ms:assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398625(v=OCS.15)
ms:contentKeyID: 48184612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec27c2e00a7f969dbc13c91b06313c8045894a9e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557097"
---
# <a name="schema-classes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="93326-103">Classes e descrições de esquema no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93326-103">Schema classes and descriptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93326-104">_**Última modificação do tópico:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="93326-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="93326-105">Esta seção descreve todas as classes de esquema usadas pelo Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="93326-105">This section describes all the schema classes used by Lync Server 2013.</span></span>

<div>

## <a name="schema-classes-and-descriptions"></a><span data-ttu-id="93326-106">Classes e descrições de esquema</span><span class="sxs-lookup"><span data-stu-id="93326-106">Schema Classes and Descriptions</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93326-107">Classe</span><span class="sxs-lookup"><span data-stu-id="93326-107">Class</span></span></th>
<th><span data-ttu-id="93326-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="93326-108">Description</span></span></th>
<th><span data-ttu-id="93326-109">Comments</span><span class="sxs-lookup"><span data-stu-id="93326-109">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93326-110">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="93326-110">Mail-Recipient</span></span></p></td>
<td><p><span data-ttu-id="93326-111">Destinatário de email de Unificação de mensagens (UM) do Exchange.</span><span class="sxs-lookup"><span data-stu-id="93326-111">Exchange Unified Messaging (UM) email recipient.</span></span></p></td>
<td><p><span data-ttu-id="93326-112">Essa classe auxiliar é compartilhada com a UM do Exchange.</span><span class="sxs-lookup"><span data-stu-id="93326-112">This auxiliary class is shared with Exchange UM.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93326-113">msRTCSIP-ApplicationContacts</span><span class="sxs-lookup"><span data-stu-id="93326-113">msRTCSIP-ApplicationContacts</span></span></p></td>
<td><p><span data-ttu-id="93326-114">Esta classe é um contêiner para vários contatos de aplicativo e não contém atributos próprios.</span><span class="sxs-lookup"><span data-stu-id="93326-114">This class is a container for multiple application contacts and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="93326-115">Novo no Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="93326-115">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93326-116">msRTCSIP-ApplicationServer</span><span class="sxs-lookup"><span data-stu-id="93326-116">msRTCSIP-ApplicationServer</span></span></p></td>
<td><p><span data-ttu-id="93326-117">Esta classe contém a entrada para o ponto de controle de serviço a uma instância de UCAS (serviços de aplicativos de comunicação unificados).</span><span class="sxs-lookup"><span data-stu-id="93326-117">This class holds the entry for the service control point for an instance of Unified Communications Application Services (UCAS).</span></span></p></td>
<td><p><span data-ttu-id="93326-118">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="93326-118">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93326-119">msRTCSIP-ApplicationServerService</span><span class="sxs-lookup"><span data-stu-id="93326-119">msRTCSIP-ApplicationServerService</span></span></p></td>
<td><p><span data-ttu-id="93326-120">Esta classe fornece uma associação de um pool específico com seu serviço de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="93326-120">This class provides an association from a specific pool to its Application service.</span></span></p></td>
<td><p><span data-ttu-id="93326-121">Novo no Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="93326-121">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93326-122">msRTCSIP-ApplicationServerSettings</span><span class="sxs-lookup"><span data-stu-id="93326-122">msRTCSIP-ApplicationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="93326-123">Essa classe auxiliar para msRTCSIP-ApplicationServer contém atributos que representam as configurações de instâncias do serviço de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="93326-123">This auxiliary class to msRTCSIP-ApplicationServer holds attributes representing settings for instances of the Application service.</span></span></p></td>
<td><p><span data-ttu-id="93326-124">Novo no Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="93326-124">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93326-125">msRTCSIP-Archive (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="93326-125">msRTCSIP-Archive (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="93326-126">Esta classe auxiliar de msRTCSIP-GlobalContainer contém todas as configurações relacionadas ao arquivamento.</span><span class="sxs-lookup"><span data-stu-id="93326-126">This auxiliary class to msRTCSIP-GlobalContainer holds all settings related to archiving.</span></span></p></td>
<td><p><span data-ttu-id="93326-127">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="93326-127">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93326-128">msRTCSIP-ArchivingServer (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="93326-128">msRTCSIP-ArchivingServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="93326-p101">Esta classe representa um único servidor de arquivamento de mensagens de instantâneas. Uma instância dessa classe é criada quando um computador é ativado como um servidor de arquivamento de mensagens de instantâneas, como um computador com o serviço de arquivamento de mensagens instantâneas instalado.</span><span class="sxs-lookup"><span data-stu-id="93326-p101">This class represents a single instant messaging Archiving Server. An instance of this class is created when a computer is activated as an instant messaging Archiving Server, such as a computer with the Instant Messaging Archiving service installed.</span></span></p></td>
<td><p><span data-ttu-id="93326-131">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="93326-131">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93326-132">msRTCSIP-ConferenceDirectories</span><span class="sxs-lookup"><span data-stu-id="93326-132">msRTCSIP-ConferenceDirectories</span></span></p></td>
<td><p><span data-ttu-id="93326-133">Esta classe é um contêiner para várias instâncias de diretórios de conferência e não contém atributos próprios.</span><span class="sxs-lookup"><span data-stu-id="93326-133">This class is a container for multiple instances of conference directories and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="93326-134">Novo no Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="93326-134">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93326-135">msRTCSIP-ConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="93326-135">msRTCSIP-ConferenceDirectory</span></span></p></td>
<td><p><span data-ttu-id="93326-136">Esta classe contém atributos que representam configurações de um diretório de conferência específico.</span><span class="sxs-lookup"><span data-stu-id="93326-136">This class holds attributes representing settings for a specific conference directory.</span></span></p></td>
<td><p><span data-ttu-id="93326-137">Novo no Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="93326-137">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93326-138">msRTCSIP-ConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="93326-138">msRTCSIP-ConnectionPoint</span></span></p></td>
<td><p><span data-ttu-id="93326-139">Ponto de controle de serviço (SCP) genérico para especificar o computador como um servidor que executa o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="93326-139">Generic service control point (SCP) to specify the computer as a server running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="93326-140">Novo no Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="93326-140">New in Lync 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93326-141">msRTCSIP-DefaultCWABank</span><span class="sxs-lookup"><span data-stu-id="93326-141">msRTCSIP-DefaultCWABank</span></span></p></td>
<td><p><span data-ttu-id="93326-142">Essa classe auxiliar contém as configurações para um banco do Microsoft Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="93326-142">This auxiliary class holds the settings for a Microsoft Lync Web App bank.</span></span></p></td>
<td><p><span data-ttu-id="93326-143">Novo no Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="93326-143">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93326-144">msRTCSIP-Domain</span><span class="sxs-lookup"><span data-stu-id="93326-144">msRTCSIP-Domain</span></span></p></td>
<td><p><span data-ttu-id="93326-145">Esta classe contém os atributos que definem os domínios configurados do registrador SIP.</span><span class="sxs-lookup"><span data-stu-id="93326-145">This class holds attributes that define the configured domains of the SIP Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93326-146">msRTCSIP-EdgeProxy</span><span class="sxs-lookup"><span data-stu-id="93326-146">msRTCSIP-EdgeProxy</span></span></p></td>
<td><p><span data-ttu-id="93326-147">Este contêiner de classe representa um único serviço de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="93326-147">This class container represents a single Access Edge service.</span></span> <span data-ttu-id="93326-148">Como um serviço de borda de acesso é implantado na rede de perímetro e os clientes normalmente não permitem o acesso dos serviços de domínio do Active Directory a partir da rede de perímetro, as instâncias do serviço de borda de acesso não estão associadas à rede do Active Directory da intranet.</span><span class="sxs-lookup"><span data-stu-id="93326-148">Because an Access Edge service is deployed in the perimeter network and customers usually do not allow Active Directory Domain Services access from the perimeter network, instances of Access Edge service are not joined to the intranet’s Active Directory network.</span></span> <span data-ttu-id="93326-149">Portanto, os Proxies de acesso não são automaticamente registrados no AD DS.</span><span class="sxs-lookup"><span data-stu-id="93326-149">Therefore, Access Proxies are not automatically registered in AD DS.</span></span> <span data-ttu-id="93326-150">O administrador deve configurar manualmente a existência de cada instância do serviço de borda de acesso no AD DS.</span><span class="sxs-lookup"><span data-stu-id="93326-150">The administrator must manually configure the existence of each instance of Access Edge service in AD DS.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93326-151">msRTCSIP-EnterpriseMCUSettings</span><span class="sxs-lookup"><span data-stu-id="93326-151">msRTCSIP-EnterpriseMCUSettings</span></span></p></td>
<td><p><span data-ttu-id="93326-152">Esta classe auxiliar de msRTCSIP-MCU contém atributos que representam configurações de servidores de conferência.</span><span class="sxs-lookup"><span data-stu-id="93326-152">This auxiliary class to msRTCSIP-MCU holds attributes representing settings for Conferencing servers.</span></span></p></td>
<td><p><span data-ttu-id="93326-153">Novo no Microsoft Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="93326-153">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93326-154">msRTCSIP-EnterpriseMediationServerSettings</span><span class="sxs-lookup"><span data-stu-id="93326-154">msRTCSIP-EnterpriseMediationServerSettings</span></span></p></td>
<td><p><span data-ttu-id="93326-155">Esta classe auxiliar de msRTCSIP-MediationServer contém atributos que representam configurações de Servidores de Mediação.</span><span class="sxs-lookup"><span data-stu-id="93326-155">This auxiliary class to msRTCSIP-MediationServer holds attributes representing settings for Mediation Servers.</span></span></p></td>
<td><p><span data-ttu-id="93326-156">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="93326-156">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93326-157">msRTCSIP-EnterpriseServerSettings</span><span class="sxs-lookup"><span data-stu-id="93326-157">msRTCSIP-EnterpriseServerSettings</span></span></p></td>
<td><p><span data-ttu-id="93326-158">Esta classe auxiliar de msRTCSIP-Server contém atributos que representam configurações de servidores SIP.</span><span class="sxs-lookup"><span data-stu-id="93326-158">This auxiliary class to msRTCSIP-Server holds attributes representing settings for SIP servers.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93326-159">msRTCSIP-Federation</span><span class="sxs-lookup"><span data-stu-id="93326-159">msRTCSIP-Federation</span></span></p></td>
<td><p><span data-ttu-id="93326-160">Esta classe auxiliar de msRTCSIP-GlobalContainer contém todas as configurações relacionadas à federação.</span><span class="sxs-lookup"><span data-stu-id="93326-160">This auxiliary class to msRTCSIP-GlobalContainer holds all settings related to federation.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93326-161">msRTCSIP-GlobalContainer</span><span class="sxs-lookup"><span data-stu-id="93326-161">msRTCSIP-GlobalContainer</span></span></p></td>
<td><p><span data-ttu-id="93326-162">Essa classe contém todas as configurações que se aplicam em uma implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="93326-162">This class holds all settings that apply throughout a Lync Server deployment.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93326-163">msRTCSIP-GlobalUserPolicy (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="93326-163">msRTCSIP-GlobalUserPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="93326-164">Esta classe representa uma única política de reunião do Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="93326-164">This class represents a single Office Communications Server meeting policy.</span></span></p></td>
<td><p><span data-ttu-id="93326-165">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="93326-165">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93326-166">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="93326-166">msRTCSIP-GlobalTopologySetting</span></span></p></td>
<td><p><span data-ttu-id="93326-167">O objeto de configuração da topologia global local.</span><span class="sxs-lookup"><span data-stu-id="93326-167">The local global topology setting object.</span></span></p></td>
<td><p><span data-ttu-id="93326-168">Novo no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="93326-168">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93326-169">msRTCSIP-GlobalTopologySettings</span><span class="sxs-lookup"><span data-stu-id="93326-169">msRTCSIP-GlobalTopologySettings</span></span></p></td>
<td><p><span data-ttu-id="93326-170">Container para manter os objetos de configuração da topologia global.</span><span class="sxs-lookup"><span data-stu-id="93326-170">Container to hold global topology setting objects.</span></span></p></td>
<td><p><span data-ttu-id="93326-171">Novo no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="93326-171">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93326-172">msRTCSIP-LocalNormalization</span><span class="sxs-lookup"><span data-stu-id="93326-172">msRTCSIP-LocalNormalization</span></span></p></td>
<td><p><span data-ttu-id="93326-173">Esta classe é um contêiner que representa uma instância de uma regra de normalização de local.</span><span class="sxs-lookup"><span data-stu-id="93326-173">This class is a container that represents an instance of a location normalization rule.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93326-174">msRTCSIP-LocationContactMapping</span><span class="sxs-lookup"><span data-stu-id="93326-174">msRTCSIP-LocationContactMapping</span></span></p></td>
<td><p><span data-ttu-id="93326-175">Essa classe é criada pelo aplicativo atendedor de conferência e mantém os atributos usados para categorizar os números de telefone de conferência por região.</span><span class="sxs-lookup"><span data-stu-id="93326-175">This class is created by the Conferencing Attendant application and holds attributes used to categorize conference telephone numbers by region.</span></span></p></td>
<td><p><span data-ttu-id="93326-176">Novo no Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="93326-176">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93326-177">msRTCSIP-LocationContactMappings</span><span class="sxs-lookup"><span data-stu-id="93326-177">msRTCSIP-LocationContactMappings</span></span></p></td>
<td><p><span data-ttu-id="93326-178">Esta classe é um contêiner para várias instâncias de mapeamentos de contato de localização e não contém atributos próprios.</span><span class="sxs-lookup"><span data-stu-id="93326-178">This class is a container for multiple instances of location contact mappings and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="93326-179">Novo no Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="93326-179">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93326-180">msRTCSIP-LocationProfile</span><span class="sxs-lookup"><span data-stu-id="93326-180">msRTCSIP-LocationProfile</span></span></p></td>
<td><p><span data-ttu-id="93326-181">Esta classe é um contêiner que representa um perfil de localidade específico.</span><span class="sxs-lookup"><span data-stu-id="93326-181">This class is a container that represents a specific location profile.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93326-182">msRTCSIP-LocationProfiles (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="93326-182">msRTCSIP-LocationProfiles (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="93326-183">Esta classe é um contêiner para vários perfis de localidade e não contém atributos próprios.</span><span class="sxs-lookup"><span data-stu-id="93326-183">This class is a container for multiple location profiles and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="93326-184">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="93326-184">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93326-185">msRTCSIP-LocalNormalizations (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="93326-185">msRTCSIP-LocalNormalizations (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="93326-186">Esta classe é um contêiner para várias regras de normalização de local e não contém atributos próprios.</span><span class="sxs-lookup"><span data-stu-id="93326-186">This class is a container for multiple local normalization rules and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="93326-187">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="93326-187">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93326-188">msRTCSIP-MCU</span><span class="sxs-lookup"><span data-stu-id="93326-188">msRTCSIP-MCU</span></span></p></td>
<td><p><span data-ttu-id="93326-189">Esta classe representa um único servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="93326-189">This class represents a single Conferencing server.</span></span></p></td>
<td><p><span data-ttu-id="93326-190">Novidade no Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="93326-190">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93326-191">msRTCSIP-MCUFactories</span><span class="sxs-lookup"><span data-stu-id="93326-191">msRTCSIP-MCUFactories</span></span></p></td>
<td><p><span data-ttu-id="93326-192">Esta classe contém várias classes msRTCSIP-MCUFactory e não tem atributos próprios.</span><span class="sxs-lookup"><span data-stu-id="93326-192">This class holds multiple msRTCSIP-MCUFactory classes and does not have attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="93326-193">Novidade no Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="93326-193">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93326-194">msRTCSIP-MCUFactory</span><span class="sxs-lookup"><span data-stu-id="93326-194">msRTCSIP-MCUFactory</span></span></p></td>
<td><p><span data-ttu-id="93326-p103">Essa classe é um contêiner que representa uma fábrica de servidor de conferência para um único tipo de mídia. Uma instância dessa classe é criada quando o primeiro servidor de conferência para este tipo e fornecedor  específicos é ativado.</span><span class="sxs-lookup"><span data-stu-id="93326-p103">This class is a container representing a Conferencing Server Factory for a single medium type. An instance of this class is created when the first Conferencing server for this particular type and vendor is activated.</span></span></p></td>
<td><p><span data-ttu-id="93326-197">Novidade no Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="93326-197">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93326-198">msRTCSIP-MCUFactoryService</span><span class="sxs-lookup"><span data-stu-id="93326-198">msRTCSIP-MCUFactoryService</span></span></p></td>
<td><p><span data-ttu-id="93326-199">Esta classe fornece uma associação de um pool específico com o respectivo Alocador de Servidores de Conferência.</span><span class="sxs-lookup"><span data-stu-id="93326-199">This class provides an association from a specific pool to its Conferencing Server Factory.</span></span></p></td>
<td><p><span data-ttu-id="93326-200">Novidade no Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="93326-200">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93326-201">msRTCSIP-MediationServer</span><span class="sxs-lookup"><span data-stu-id="93326-201">msRTCSIP-MediationServer</span></span></p></td>
<td><p><span data-ttu-id="93326-202">Esta classe contém a entrada do ponto de controle de serviço de um Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="93326-202">This class holds the entry for the service control point for a Mediation Server.</span></span></p></td>
<td><p><span data-ttu-id="93326-203">Novidade no Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="93326-203">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93326-204">msRTCSIP-Meeting (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="93326-204">msRTCSIP-Meeting (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="93326-205">Esta classe auxiliar de msRTCSIP-GlobalContainer contém atributos que representam configurações de reunião que podem ser definidas.</span><span class="sxs-lookup"><span data-stu-id="93326-205">This auxiliary class to msRTCSIP-GlobalContainer holds attributes representing configurable meeting settings.</span></span></p></td>
<td><p><span data-ttu-id="93326-206">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="93326-206">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93326-207">msRTCSIP-mobilidade</span><span class="sxs-lookup"><span data-stu-id="93326-207">msRTCSIP-Mobility</span></span></p></td>
<td><p><span data-ttu-id="93326-208">Contâiner que armazena as configurações de mobilidade global.</span><span class="sxs-lookup"><span data-stu-id="93326-208">Container that stores the global mobility settings.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93326-209">msRTCSIP-MonitoringServer</span><span class="sxs-lookup"><span data-stu-id="93326-209">msRTCSIP-MonitoringServer</span></span></p></td>
<td><p><span data-ttu-id="93326-210">Esta classe contém atributos que representam as configurações de um único servidor de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="93326-210">This class holds attributes that represent settings for a single Monitoring Server.</span></span></p></td>
<td><p><span data-ttu-id="93326-211">Novo no Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="93326-211">New in Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93326-212">msRTCSIP-PhoneRoute (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="93326-212">msRTCSIP-PhoneRoute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="93326-p104">Esta classe é um contêiner que representa uma instância de uma rota de custo mínimo para um gateway ou um conjunto de gateways. Essa informação é usada por todos os pools Enterprise ou servidores executando o Standard Edition para rotear chamadas de saída à rede telefônica pública comutada (PSTN) da maneira mais econômica.</span><span class="sxs-lookup"><span data-stu-id="93326-p104">This class is a container representing an instance of a least cost route to a gateway or set of gateways. This information is used by all Enterprise pools or servers running Standard Edition to route outgoing calls to the public switched telephone network (PSTN) in the most cost effective way.</span></span></p></td>
<td><p><span data-ttu-id="93326-215">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="93326-215">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93326-216">msRTCSIP-PhoneRoutes (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="93326-216">msRTCSIP-PhoneRoutes (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="93326-217">Esta classe é um contêiner para várias rotas econômicas e não contém atributos próprios.</span><span class="sxs-lookup"><span data-stu-id="93326-217">This class is a container for multiple, least cost routes and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="93326-218">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="93326-218">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93326-219">msRTCSIP-Policies (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="93326-219">msRTCSIP-Policies (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="93326-220">Esta classe contém várias classes de política do Lync Server e não tem atributos próprios.</span><span class="sxs-lookup"><span data-stu-id="93326-220">This class holds multiple Lync Server policy classes and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="93326-221">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="93326-221">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93326-222">msRTCSIP-pool</span><span class="sxs-lookup"><span data-stu-id="93326-222">msRTCSIP-Pool</span></span></p></td>
<td><p><span data-ttu-id="93326-223">Esta classe representa um único pool do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="93326-223">This class represents a single Lync Server pool.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93326-224">msRTCSIP-Pools</span><span class="sxs-lookup"><span data-stu-id="93326-224">msRTCSIP-Pools</span></span></p></td>
<td><p><span data-ttu-id="93326-225">Essa classe contém vários pools do Lync Server e não tem atributos próprios.</span><span class="sxs-lookup"><span data-stu-id="93326-225">This class holds multiple Lync Server pools and does not have any attributes itself.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93326-226">msRTCSIP-PoolService</span><span class="sxs-lookup"><span data-stu-id="93326-226">msRTCSIP-PoolService</span></span></p></td>
<td><p><span data-ttu-id="93326-p105">Esta classe representa o ponto de controle de serviço de um pool. Os usuários hospedados em um pool têm o seu ponto de atributo msRTCSIP-PrimaryHomeServer a uma instância desta classe.</span><span class="sxs-lookup"><span data-stu-id="93326-p105">This class represents the service control pointservice control point of a pool. Users hosted on a pool have their msRTCSIP-PrimaryHomeServer attribute point to an instance of this class.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93326-229">msRTCSIP-Presence</span><span class="sxs-lookup"><span data-stu-id="93326-229">msRTCSIP-Presence</span></span></p></td>
<td><p><span data-ttu-id="93326-230">Contâiner que armazena as configurações de presença global.</span><span class="sxs-lookup"><span data-stu-id="93326-230">Container that stores the global presence settings.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93326-231">msRTCSIP-registrador</span><span class="sxs-lookup"><span data-stu-id="93326-231">msRTCSIP-Registrar</span></span></p></td>
<td><p><span data-ttu-id="93326-232">Esta classe auxiliar de msRTCSIP-GlobalContainer contém atributos que representam configurações de usuário mantidas pelos servidores do registrador SIP.</span><span class="sxs-lookup"><span data-stu-id="93326-232">This auxiliary class to msRTCSIP-GlobalContainer holds attributes representing user settings maintained by the SIP Registrar servers.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93326-233">msRTCSIP-RouteUsage (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="93326-233">msRTCSIP-RouteUsage (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="93326-p106">Esta classe é um contêiner que representa uma instância de uso de uma rota telefônica. Uma classe de rota de uso telefônica consiste em um campo de atributo e um campo de descrição. O campo de atributo define um tipo de uso. O campo da descrição permite que os administradores descrever o uso para este atributo na rota telefônica.</span><span class="sxs-lookup"><span data-stu-id="93326-p106">This class is a container representing an instance of a phone route usage. A phone route usage class consists of an attribute field and a description field. The attribute field defines a usage type. The description field allows administrators to describe the usage for this attribute in the phone route.</span></span></p></td>
<td><p><span data-ttu-id="93326-238">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="93326-238">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93326-239">msRTCSIP-RouteUsages (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="93326-239">msRTCSIP-RouteUsages (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="93326-240">Esta classe contém várias instâncias da classe msRTCSIP-RouteUsage e não tem atributos próprios.</span><span class="sxs-lookup"><span data-stu-id="93326-240">This class holds multiple instances of the msRTCSIP-RouteUsage class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="93326-241">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="93326-241">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93326-242">msRTCSIP-Search</span><span class="sxs-lookup"><span data-stu-id="93326-242">msRTCSIP-Search</span></span></p></td>
<td><p><span data-ttu-id="93326-243">Esta classe auxiliar de msRTCSIP-GlobalContainer contém atributos que limitam e controlam o escopo dos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="93326-243">This auxiliary class to msRTCSIP-GlobalContainer holds attributes that limit and control the scope of search results.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93326-244">msRTCSIP-Server</span><span class="sxs-lookup"><span data-stu-id="93326-244">msRTCSIP-Server</span></span></p></td>
<td><p><span data-ttu-id="93326-245">Esta classe representa um único servidor executando o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="93326-245">This class represents a single server running Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93326-246">msRTCSIP-Service</span><span class="sxs-lookup"><span data-stu-id="93326-246">msRTCSIP-Service</span></span></p></td>
<td><p><span data-ttu-id="93326-247">Esta classe contém o contêiner de configurações globais e os objetos msRTCSIP-Domain.</span><span class="sxs-lookup"><span data-stu-id="93326-247">This class holds the global settings container and msRTCSIP-Domain objects.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93326-248">msRTCSIP-TrustedMCU</span><span class="sxs-lookup"><span data-stu-id="93326-248">msRTCSIP-TrustedMCU</span></span></p></td>
<td><p><span data-ttu-id="93326-249">Esta classe contém atributos que representam configurações de um único servidor de conferência confiável.</span><span class="sxs-lookup"><span data-stu-id="93326-249">This class holds attributes that represent settings for a trusted Conferencing server.</span></span></p></td>
<td><p><span data-ttu-id="93326-250">Novidade no Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="93326-250">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93326-251">msRTCSIP-TrustedMCUs</span><span class="sxs-lookup"><span data-stu-id="93326-251">msRTCSIP-TrustedMCUs</span></span></p></td>
<td><p><span data-ttu-id="93326-252">Esta classe contém várias instâncias da classe msRTCSIP-TrustedMCU e não tem atributos próprios.</span><span class="sxs-lookup"><span data-stu-id="93326-252">This class holds multiple instances of the msRTCSIP-TrustedMCU class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="93326-253">Novidade no Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="93326-253">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93326-254">msRTCSIP-TrustedProxies</span><span class="sxs-lookup"><span data-stu-id="93326-254">msRTCSIP-TrustedProxies</span></span></p></td>
<td><p><span data-ttu-id="93326-255">Esta classe contém várias classes msRTCSIP-TrustedProxy e não tem atributos próprios.</span><span class="sxs-lookup"><span data-stu-id="93326-255">This class holds multiple msRTCSIP-TrustedProxy classes and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="93326-256">Novidade no Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="93326-256">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93326-257">msRTCSIP-TrustedProxy</span><span class="sxs-lookup"><span data-stu-id="93326-257">msRTCSIP-TrustedProxy</span></span></p></td>
<td><p><span data-ttu-id="93326-p107">Essa classe é um contêiner que representa um servidor executando o servidor Proxy. Uma instância desta classe é criada ao ativar um novo servidor de Proxy em um computador associado ao AD DS.</span><span class="sxs-lookup"><span data-stu-id="93326-p107">This class is a container representing a server running Proxy Server. An instance of this class is created when activating a new Proxy Server on a computer joined to AD DS.</span></span></p></td>
<td><p><span data-ttu-id="93326-260">Novidade no Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="93326-260">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93326-261">msRTCSIP-TrustedServer</span><span class="sxs-lookup"><span data-stu-id="93326-261">msRTCSIP-TrustedServer</span></span></p></td>
<td><p><span data-ttu-id="93326-262">Esta classe contém atributos que representam configurações de um único servidor confiável.</span><span class="sxs-lookup"><span data-stu-id="93326-262">This class holds attributes that represent settings for a trusted server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93326-263">msRTCSIP-TrustedService</span><span class="sxs-lookup"><span data-stu-id="93326-263">msRTCSIP-TrustedService</span></span></p></td>
<td><p><span data-ttu-id="93326-264">Esta classe é um contêiner que representa um serviço confiável que é roteável usando um URI de operador usuário de encaminhamento global (GRUU).</span><span class="sxs-lookup"><span data-stu-id="93326-264">This class is a container representing a trusted service that is routable using a Globally Routable User Agent URI (GRUU) address.</span></span> <span data-ttu-id="93326-265">Uma instância dessa classe é criada quando um novo servidor de confiança do Lync Server é ativado.</span><span class="sxs-lookup"><span data-stu-id="93326-265">An instance of this class is created when a new server that is trusted by Lync Server is activated.</span></span> <span data-ttu-id="93326-266">O servidor confiáve deve ser associado a um domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="93326-266">This trusted server must be joined to an Active Directory domain.</span></span></p></td>
<td><p><span data-ttu-id="93326-267">Novidade no Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="93326-267">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93326-268">msRTCSIP-Trustservices</span><span class="sxs-lookup"><span data-stu-id="93326-268">msRTCSIP-TrustedServices</span></span></p></td>
<td><p><span data-ttu-id="93326-269">Esta classe é um contêiner para vários servidores GRUU e não contém atributos próprios.</span><span class="sxs-lookup"><span data-stu-id="93326-269">This class is a container for multiple GRUU servers and does not contain any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="93326-270">Novidade no Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="93326-270">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93326-271">msRTCSIP-TrustedWebComponentsServer</span><span class="sxs-lookup"><span data-stu-id="93326-271">msRTCSIP-TrustedWebComponentsServer</span></span></p></td>
<td><p><span data-ttu-id="93326-272">Esta classe contém atributos que representam as configurações de um componente da web confiável.</span><span class="sxs-lookup"><span data-stu-id="93326-272">This class holds attributes that represent the settings for a trusted web component.</span></span></p></td>
<td><p><span data-ttu-id="93326-273">Novidade no Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="93326-273">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93326-274">msRTCSIP-TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="93326-274">msRTCSIP-TrustedWebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="93326-275">Esta classe contém várias instâncias da classe msRTCSIP-TrustedWebComponentServer e não tem atributos próprios.</span><span class="sxs-lookup"><span data-stu-id="93326-275">This class holds multiple instances of the msRTCSIP-TrustedWebComponentServer class and does not have any attributes itself.</span></span></p></td>
<td><p><span data-ttu-id="93326-276">Novidade no Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="93326-276">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93326-277">msRTCSIP-UnifiedCommunications (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="93326-277">msRTCSIP-UnifiedCommunications (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="93326-278">Esta classe auxiliar de msRTCSIP-GlobalContainer contém atributos relacionados à comunicação unificada.</span><span class="sxs-lookup"><span data-stu-id="93326-278">This auxiliary class to msRTCSIP-GlobalContainer holds attributes related to unified communications.</span></span></p></td>
<td><p><span data-ttu-id="93326-279">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="93326-279">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93326-280">msRTCSIP-WebComponents</span><span class="sxs-lookup"><span data-stu-id="93326-280">msRTCSIP-WebComponents</span></span></p></td>
<td><p><span data-ttu-id="93326-p109">Esta classe contém o ponto de controle do serviço IIS (Internet Information Server). Ele identifica um servidor como um servidor de componentes web.</span><span class="sxs-lookup"><span data-stu-id="93326-p109">This class holds the service control pointservice control point for Internet Information Server (IIS). It identifies a server as a web components server.</span></span></p></td>
<td><p><span data-ttu-id="93326-283">Novidade no Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="93326-283">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93326-284">msRTCSIP-WebComponentsService</span><span class="sxs-lookup"><span data-stu-id="93326-284">msRTCSIP-WebComponentsService</span></span></p></td>
<td><p><span data-ttu-id="93326-285">Esta classe fornece uma associação de um pool específico com os componentes web que ele usará.</span><span class="sxs-lookup"><span data-stu-id="93326-285">This class provides an association from a specific pool to the web components that the pool will use.</span></span></p></td>
<td><p><span data-ttu-id="93326-286">Novidade no Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="93326-286">New in Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93326-287">msRTCSIP-WebComponentSettings</span><span class="sxs-lookup"><span data-stu-id="93326-287">msRTCSIP-WebComponentSettings</span></span></p></td>
<td><p><span data-ttu-id="93326-288">Esta classe auxiliar de msRTCSIP-WebComponents contém atributos que representam configurações de componentes web.</span><span class="sxs-lookup"><span data-stu-id="93326-288">This auxiliary class to msRTCSIP-WebComponents holds attributes representing settings for web components.</span></span></p></td>
<td><p><span data-ttu-id="93326-289">Novidade no Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="93326-289">New in Communications Server 2007.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

