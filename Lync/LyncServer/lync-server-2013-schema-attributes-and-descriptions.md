---
title: 'Lync Server 2013: atributos e descrições de esquema'
description: 'Lync Server 2013: atributos e descrições de esquema.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema attributes and descriptions
ms:assetid: b009df76-9c22-471d-b57a-bda009a98261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412841(v=OCS.15)
ms:contentKeyID: 48185083
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18888d20a772b3e84970e7d874bd6b6964affc75
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557187"
---
# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="aee40-103">Atributos e descrições de esquema no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aee40-103">Schema attributes and descriptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aee40-104">_**Última modificação do tópico:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="aee40-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="aee40-105">Esta seção descreve todos os atributos de esquema usados pelo Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aee40-105">This section describes all the schema attributes used by Lync Server 2013.</span></span> <span data-ttu-id="aee40-106">Para as classes associadas a atributos, confira [atributos de esquema por classe no Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="aee40-106">For the classes associated with attributes, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span> <span data-ttu-id="aee40-107">Para obter uma lista de classes e atributos que são novos no Lync Server 2013, consulte [Schema Changes in Lync server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="aee40-107">For a list of classes and attributes that are new in Lync Server 2013, see [Schema changes in Lync Server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span></span>

<span data-ttu-id="aee40-108">Os atributos que são pares vinculados são especificados como links de encaminhamento ou links de volta.</span><span class="sxs-lookup"><span data-stu-id="aee40-108">Attributes that are linked pairs are specified as forward links or back links.</span></span> <span data-ttu-id="aee40-109">Um atributo que se refere a outro objeto é um vínculo progressivo; o atributo do outro objeto que se refere novamente ao primeiro objeto é um vínculo inverso.</span><span class="sxs-lookup"><span data-stu-id="aee40-109">An attribute that refers to another object is a forward link; the attribute of the other object that refers back to the first object is a back link.</span></span> <span data-ttu-id="aee40-110">Os links de encaminhamento são atualizáveis, enquanto os links de volta são somente leitura.</span><span class="sxs-lookup"><span data-stu-id="aee40-110">Forward links are updatable, while back links are read-only.</span></span>

<span data-ttu-id="aee40-111">Alguns atributos têm um valor de máscara de bits.</span><span class="sxs-lookup"><span data-stu-id="aee40-111">Some attributes have a bit-mask value.</span></span> <span data-ttu-id="aee40-112">Para esses atributos, cada configuração é representada por um bit e o valor decimal exibido representa a posição de bit.</span><span class="sxs-lookup"><span data-stu-id="aee40-112">For these attributes, each setting is represented by a bit, and the displayed decimal value represents the bit position.</span></span> <span data-ttu-id="aee40-113">As posições de bit começam com bit 0.</span><span class="sxs-lookup"><span data-stu-id="aee40-113">Bit positions start with bit 0.</span></span> <span data-ttu-id="aee40-114">Por exemplo, 1 (binário) é bit 0 definido e 10000 (binário) é um bit 4 definido.</span><span class="sxs-lookup"><span data-stu-id="aee40-114">For example, 1 (binary) is bit 0 set and 10000 (binary) is bit 4 set.</span></span> <span data-ttu-id="aee40-115">Cada bit representa uma propriedade.</span><span class="sxs-lookup"><span data-stu-id="aee40-115">Each bit represents a property.</span></span> <span data-ttu-id="aee40-116">Estes são alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="aee40-116">The following are some examples:</span></span>

  - <span data-ttu-id="aee40-117">10000 (binário) tem um valor decimal de 16 (ou seja, o bit 4 é definido).</span><span class="sxs-lookup"><span data-stu-id="aee40-117">10000 (binary) has a decimal value of 16 (that is, bit 4 is set).</span></span>

  - <span data-ttu-id="aee40-118">100 milhões (binário) tem um valor decimal de 256 (ou seja, o bit 8 é definido).</span><span class="sxs-lookup"><span data-stu-id="aee40-118">100000000 (binary) has a decimal value of 256 (that is, bit 8 is set).</span></span>

  - <span data-ttu-id="aee40-119">1100 (binário) tem um valor decimal de 12 (ou seja, os bits 2 e 3 são definidos; as propriedades representadas por ambos os bits estão habilitadas).</span><span class="sxs-lookup"><span data-stu-id="aee40-119">1100 (binary) has a decimal value of 12 (that is, bits 2 and 3 are set; properties represented by both bits are enabled).</span></span>

  - <span data-ttu-id="aee40-120">1111000001 (binário) tem um valor decimal de 961 (ou seja, os bits 0, 6, 7, 8 e 9 são definidos; as propriedades de cada um desses bits estão habilitadas).</span><span class="sxs-lookup"><span data-stu-id="aee40-120">1111000001 (binary) has a decimal value of 961 (that is, bits 0, 6, 7, 8, and 9 are set; properties for each of these bits are enabled).</span></span>

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a><span data-ttu-id="aee40-121">Atributos de esquema para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aee40-121">Schema Attributes for Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aee40-122">Atributo</span><span class="sxs-lookup"><span data-stu-id="aee40-122">Attribute</span></span></th>
<th><span data-ttu-id="aee40-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="aee40-123">Description</span></span></th>
<th><span data-ttu-id="aee40-124">Comments</span><span class="sxs-lookup"><span data-stu-id="aee40-124">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aee40-125">dnsHostName</span><span class="sxs-lookup"><span data-stu-id="aee40-125">dnsHostName</span></span></p></td>
<td><p><span data-ttu-id="aee40-126">Um atributo existente nos serviços de domínio do Active Directory que agora está associado às classes <strong>msRTCSIP-pool</strong> e <strong>msRTCSIP-MonitoringServer</strong> .</span><span class="sxs-lookup"><span data-stu-id="aee40-126">An existing attribute in Active Directory Domain Services that is now associated with the <strong>msRTCSIP-Pool</strong> and <strong>msRTCSIP-MonitoringServer</strong> classes.</span></span> <span data-ttu-id="aee40-127">Este atributo especifica o FQDN (nome de domínio totalmente qualificado) de um pool ou de um servidor de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="aee40-127">This attribute specifies the fully qualified domain name (FQDN) of a pool or Monitoring Server.</span></span></p>
<p><span data-ttu-id="aee40-128">Um valor válido para cada segmento é 63 caracteres; um valor válido para o FQDN inteiro é de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="aee40-128">A valid value for each segment is 63 characters; a valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="aee40-129">Novo no Microsoft Office Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="aee40-129">New in Microsoft Office Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-130">msDS-SourceObjectDN</span><span class="sxs-lookup"><span data-stu-id="aee40-130">msDS-SourceObjectDN</span></span></p></td>
<td><p><span data-ttu-id="aee40-131">Este atributo contém a representação de cadeia de caracteres do DN (nome diferenciado) do objeto em outra floresta que corresponde a esse objeto.</span><span class="sxs-lookup"><span data-stu-id="aee40-131">This attribute contains the string representation of the distinguished name (DN) of the object in another forest that corresponds to this object.</span></span> <span data-ttu-id="aee40-132">Este atributo é usado para expansão de grupo de distribuição e presença automática.</span><span class="sxs-lookup"><span data-stu-id="aee40-132">This attribute is used for distribution group expansion and auto attendance.</span></span> <span data-ttu-id="aee40-133">Esse atributo é definido no esquema padrão do Active Directory para o Windows Server 2003 R2.</span><span class="sxs-lookup"><span data-stu-id="aee40-133">This attribute is defined in the default Active Directory schema for Windows Server 2003 R2.</span></span></p>
<p><span data-ttu-id="aee40-134">Para evitar a necessidade de uma atualização do AD DS para o Windows Server 2003 R2, a preparação do esquema do Active Directory estende o esquema do Windows Server 2003 com essa definição de atributo.</span><span class="sxs-lookup"><span data-stu-id="aee40-134">To avoid requiring an upgrade of AD DS to Windows Server 2003 R2, Active Directory schema preparation extends the Windows Server 2003 schema with this attribute definition.</span></span></p></td>
<td><p><span data-ttu-id="aee40-135">Novo no Microsoft Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-135">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-136">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="aee40-136">msExchUCVoiceMailSettings</span></span></p></td>
<td><p><span data-ttu-id="aee40-137">Este atributo com valores múltiplos contém configurações de caixa postal.</span><span class="sxs-lookup"><span data-stu-id="aee40-137">This multi-valued attribute holds voice mail settings.</span></span> <span data-ttu-id="aee40-138">Este atributo é compartilhado com a Unificação de mensagens (UM) do Exchange.</span><span class="sxs-lookup"><span data-stu-id="aee40-138">This attribute is shared with Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="aee40-139">Novo no Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-139">New in Microsoft Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-140">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="aee40-140">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="aee40-141">Este atributo de vários valores mantém identificadores para manter políticas aplicadas ao usuário.</span><span class="sxs-lookup"><span data-stu-id="aee40-141">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="aee40-142">Políticas de retenção preservam os itens das caixas de correio para o usuário pela duração da retenção.</span><span class="sxs-lookup"><span data-stu-id="aee40-142">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="aee40-143">Este atributo é compartilhado com o Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="aee40-143">This attribute is shared with Exchange 2013.</span></span></p></td>
<td><p><span data-ttu-id="aee40-144">Novo no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aee40-144">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-145">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="aee40-145">msRTCSIP-AcpInfo</span></span></p></td>
<td><p><span data-ttu-id="aee40-146">Este atributo armazena informações do provedor de audioconferência para um usuário.</span><span class="sxs-lookup"><span data-stu-id="aee40-146">This attribute stores audio conferencing provider information for a user.</span></span></p></td>
<td><p><span data-ttu-id="aee40-147">Novo no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-147">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-148">msRTCSIP-ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="aee40-148">msRTCSIP-ApplicationDestination</span></span></p></td>
<td><p><span data-ttu-id="aee40-149">Este atributo aponta para a entrada de serviço confiável para o contato de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="aee40-149">This attribute points to the trusted service entry for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="aee40-150">Novo no Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="aee40-150">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-151">msRTCSIP-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="aee40-151">msRTCSIP-ApplicationList</span></span></p></td>
<td><p><span data-ttu-id="aee40-152">Este atributo contém uma lista de aplicativos hospedados no servidor de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="aee40-152">This attribute contains a list of hosted applications on the application server.</span></span></p></td>
<td><p><span data-ttu-id="aee40-153">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="aee40-153">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-154">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="aee40-154">msRTCSIP-ApplicationOptions</span></span></p></td>
<td><p><span data-ttu-id="aee40-155">Este atributo especifica as opções para o contato de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="aee40-155">This attribute specifies the options for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="aee40-156">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="aee40-156">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-157">msRTCSIP-ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="aee40-157">msRTCSIP-ApplicationPrimaryLanguage</span></span></p></td>
<td><p><span data-ttu-id="aee40-158">Este atributo contém o idioma principal para o contato de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="aee40-158">This attribute contains the primary language for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="aee40-159">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="aee40-159">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-160">msRTCSIP-ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="aee40-160">msRTCSIP-ApplicationSecondaryLanguages</span></span></p></td>
<td><p><span data-ttu-id="aee40-161">Este atributo de vários valores contém os idiomas secundários para o contato de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="aee40-161">This multiple value attribute contains the secondary languages for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="aee40-162">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="aee40-162">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-163">msRTCSIP-ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="aee40-163">msRTCSIP-ApplicationServerBL</span></span></p></td>
<td><p><span data-ttu-id="aee40-164">Este atributo contém uma lista de servidores de aplicativos que pertencem a esse pool.</span><span class="sxs-lookup"><span data-stu-id="aee40-164">This attribute contains a list of application servers that belong to this pool.</span></span> <span data-ttu-id="aee40-165">O vínculo sequencial correspondente a este atributo de vínculo inverso é <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span><span class="sxs-lookup"><span data-stu-id="aee40-165">The corresponding forward link to this back link attribute is <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span></span></p></td>
<td><p><span data-ttu-id="aee40-166">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="aee40-166">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-167">msRTCSIP-ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="aee40-167">msRTCSIP-ApplicationServerPoolLink</span></span></p></td>
<td><p><span data-ttu-id="aee40-168">Este atributo aponta para o pool ao qual pertence este servidor de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="aee40-168">This attribute points to the pool to which this application server belongs.</span></span> <span data-ttu-id="aee40-169">Este é o link de encaminhamento.</span><span class="sxs-lookup"><span data-stu-id="aee40-169">This is the forward link.</span></span> <span data-ttu-id="aee40-170">O vínculo inverso correspondente é <strong>msRTCSIP-ApplicationServerBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="aee40-170">The corresponding backward link is <strong>msRTCSIP-ApplicationServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="aee40-171">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="aee40-171">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-172">msRTCSIP-ArchiveDefault (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-172">msRTCSIP-ArchiveDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="aee40-173">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="aee40-173">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="aee40-174">Obsoleto no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-174">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-175">msRTCSIP-ArchiveDefaultFlags (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-175">msRTCSIP-ArchiveDefaultFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-176">Este atributo especifica o padrão global dentro do limite da floresta para o arquivamento de todas as comunicações do usuário.</span><span class="sxs-lookup"><span data-stu-id="aee40-176">This attribute specifies the global default within the forest boundary for archiving all user communications.</span></span> <span data-ttu-id="aee40-177">Isso é imposto pela camada do agente de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="aee40-177">This is enforced by the archiving agent layer.</span></span> <span data-ttu-id="aee40-178">O intervalo de valores para esse atributo é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="aee40-178">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="aee40-179"><strong>True</strong>: arquivar todos os usuários</span><span class="sxs-lookup"><span data-stu-id="aee40-179"><strong>TRUE</strong>: Archive all users</span></span></p></li>
<li><p><span data-ttu-id="aee40-180"><strong>False</strong>: Não arquivar todos os usuários</span><span class="sxs-lookup"><span data-stu-id="aee40-180"><strong>FALSE</strong>: Do not archive all users</span></span></p></li>
</ul>
<p><span data-ttu-id="aee40-181">Este atributo controla globalmente, dentro do limite da floresta, como as comunicações do usuário em uma rede interna são arquivadas.</span><span class="sxs-lookup"><span data-stu-id="aee40-181">This attribute globally controls, within the forest boundary, how user communications within an internal network are archived.</span></span></p>
<p><span data-ttu-id="aee40-182"><strong>Comportamento do Live Communications Server 2005 (agora desativado)</strong></span><span class="sxs-lookup"><span data-stu-id="aee40-182"><strong>Live Communications Server 2005 behavior (now retired)</strong></span></span></p>
<p><span data-ttu-id="aee40-183">O intervalo de valores para esse atributo é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="aee40-183">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="aee40-184">0: arquivar o corpo da mensagem [bit 0]</span><span class="sxs-lookup"><span data-stu-id="aee40-184">0: Archive the message body [bit 0]</span></span></p></li>
<li><p><span data-ttu-id="aee40-185">1: não arquiva o corpo da mensagem [bit 0]</span><span class="sxs-lookup"><span data-stu-id="aee40-185">1: Do not archive the message body [bit 0]</span></span></p></li>
</ul>
<p><span data-ttu-id="aee40-186"><strong>Comportamento do Office Communications Server 2007</strong></span><span class="sxs-lookup"><span data-stu-id="aee40-186"><strong>Office Communications Server 2007 behavior</strong></span></span></p>
<p><span data-ttu-id="aee40-187">O intervalo de valores para esse atributo é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="aee40-187">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="aee40-188">0: ArchiveFederationDefaultWithoutBody (desativado)</span><span class="sxs-lookup"><span data-stu-id="aee40-188">0: ArchiveFederationDefaultWithoutBody (retired)</span></span></p></li>
<li><p><span data-ttu-id="aee40-189">1-2: ArchiveInternalCommunications</span><span class="sxs-lookup"><span data-stu-id="aee40-189">1-2: ArchiveInternalCommunications</span></span></p></li>
<li><p><span data-ttu-id="aee40-190">3-4: ArchiveFederatedCommunications</span><span class="sxs-lookup"><span data-stu-id="aee40-190">3-4: ArchiveFederatedCommunications</span></span></p></li>
<li><p><span data-ttu-id="aee40-191">5: RecordPresenceRegistrations</span><span class="sxs-lookup"><span data-stu-id="aee40-191">5: RecordPresenceRegistrations</span></span></p></li>
<li><p><span data-ttu-id="aee40-192">6: RecordIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="aee40-192">6: RecordIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="aee40-193">7: RecordGroupIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="aee40-193">7: RecordGroupIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="aee40-194">8: RecordFileTransferInstances</span><span class="sxs-lookup"><span data-stu-id="aee40-194">8: RecordFileTransferInstances</span></span></p></li>
<li><p><span data-ttu-id="aee40-195">9: RecordAudioCallDetails</span><span class="sxs-lookup"><span data-stu-id="aee40-195">9: RecordAudioCallDetails</span></span></p></li>
<li><p><span data-ttu-id="aee40-196">10: RecordVideoCallDetails</span><span class="sxs-lookup"><span data-stu-id="aee40-196">10: RecordVideoCallDetails</span></span></p></li>
<li><p><span data-ttu-id="aee40-197">11: RecordRemoteAssistanceCallDetails</span><span class="sxs-lookup"><span data-stu-id="aee40-197">11: RecordRemoteAssistanceCallDetails</span></span></p></li>
<li><p><span data-ttu-id="aee40-198">12: RecordApplicationSharingDetails</span><span class="sxs-lookup"><span data-stu-id="aee40-198">12: RecordApplicationSharingDetails</span></span></p></li>
<li><p><span data-ttu-id="aee40-199">13: RecordMeetingInstantiations</span><span class="sxs-lookup"><span data-stu-id="aee40-199">13: RecordMeetingInstantiations</span></span></p></li>
<li><p><span data-ttu-id="aee40-200">14: RecordMeetingJoins</span><span class="sxs-lookup"><span data-stu-id="aee40-200">14: RecordMeetingJoins</span></span></p></li>
<li><p><span data-ttu-id="aee40-201">15: RecordDataJoins</span><span class="sxs-lookup"><span data-stu-id="aee40-201">15: RecordDataJoins</span></span></p></li>
<li><p><span data-ttu-id="aee40-202">16: RecordAVJoins</span><span class="sxs-lookup"><span data-stu-id="aee40-202">16: RecordAVJoins</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="aee40-203">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="aee40-203">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="aee40-204">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-204">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-205">msRTCSIP-ArchiveFederationDefault (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-205">msRTCSIP-ArchiveFederationDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="aee40-206">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="aee40-206">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="aee40-207">Obsoleto no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-207">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-208">msRTCSIP-ArchiveFederationDefaultFlags (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-208">msRTCSIP-ArchiveFederationDefaultFlags (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="aee40-209">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="aee40-209">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="aee40-210">Obsoleto no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-210">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-211">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="aee40-211">msRTCSIP-ArchivingEnabled</span></span></p></td>
<td><p><span data-ttu-id="aee40-212">Este atributo é um inteiro usado como um campo de bits para controlar se as comunicações de um único usuário devem ser arquivadas.</span><span class="sxs-lookup"><span data-stu-id="aee40-212">This attribute is an integer used as a bit field to control whether a single user’s communications are to be archived.</span></span> <span data-ttu-id="aee40-213">Esse controle é imposto pela camada do agente de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="aee40-213">This control is enforced by the archiving agent layer.</span></span> <span data-ttu-id="aee40-214">Ele está marcado para replicação do catálogo global.</span><span class="sxs-lookup"><span data-stu-id="aee40-214">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="aee40-215">O escopo desse atributo é específico para um único usuário ou contato.</span><span class="sxs-lookup"><span data-stu-id="aee40-215">The scope of this attribute is specific to a single user or contact.</span></span> <span data-ttu-id="aee40-216">Os valores válidos (e posições de bit associadas) no Lync Server são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="aee40-216">The valid values (and associated bit positions) in Lync Server are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="aee40-217">0: Não arquivar (sem conjunto de bits)</span><span class="sxs-lookup"><span data-stu-id="aee40-217">0: Do not archive (no bit set)</span></span></p></li>
<li><p><span data-ttu-id="aee40-218">1: desativado (posição de bit 0)</span><span class="sxs-lookup"><span data-stu-id="aee40-218">1: Retired (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="aee40-219">2: desativado (posição de bit 1)</span><span class="sxs-lookup"><span data-stu-id="aee40-219">2: Retired (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="aee40-220">4: Arquivar comunicações internas (posição de bit 2)</span><span class="sxs-lookup"><span data-stu-id="aee40-220">4: Archive internal communications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="aee40-221">8: Arquivar comunicações federadas (posição de bit 3)</span><span class="sxs-lookup"><span data-stu-id="aee40-221">8: Archive federated communications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="aee40-222">Os valores válidos anteriormente no Live Communications Server 2005 são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="aee40-222">Previously valid values in Live Communications Server 2005 are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="aee40-223">0: Use o valor padrão definido pelo <strong>msRTCSIP-ArchiveDefault</strong> e <strong>msRTCSIP-ArchiveFederation</strong> nesta ordem de precedência:</span><span class="sxs-lookup"><span data-stu-id="aee40-223">0:Use the default value defined by <strong>msRTCSIP-ArchiveDefault</strong> and <strong>msRTCSIP-ArchiveFederation</strong> in this order of precedence:</span></span></p>
<ul>
<li><p><span data-ttu-id="aee40-224">1: arquivar</span><span class="sxs-lookup"><span data-stu-id="aee40-224">1: Archive</span></span></p></li>
<li><p><span data-ttu-id="aee40-225">2: Não arquivar</span><span class="sxs-lookup"><span data-stu-id="aee40-225">2: Do not archive</span></span></p></li>
<li><p><span data-ttu-id="aee40-226">3: arquivar sem o corpo da mensagem</span><span class="sxs-lookup"><span data-stu-id="aee40-226">3: Archive without the message body</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="aee40-227">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="aee40-227">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-228">msRTCSIP-ArchivingServerData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-228">msRTCSIP-ArchivingServerData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-229">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="aee40-229">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="aee40-230">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-230">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-231">msRTCSIP-ArchivingServerVersion (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-231">msRTCSIP-ArchivingServerVersion (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-232">Este atributo define a versão do serviço de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="aee40-232">This attribute defines the version of the Archiving service.</span></span> <span data-ttu-id="aee40-233">Este atributo é um tipo inteiro de monotonously que aumenta com cada versão oficial do produto.</span><span class="sxs-lookup"><span data-stu-id="aee40-233">This attribute is a monotonously increasing integer type that increments with each official product release.</span></span> <span data-ttu-id="aee40-234">Os valores válidos possíveis são:</span><span class="sxs-lookup"><span data-stu-id="aee40-234">The possible valid values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="aee40-235">Indefinido: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="aee40-235">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="aee40-236">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="aee40-236">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="aee40-237">                 Live Communications Server 2005 with SP1</span><span class="sxs-lookup"><span data-stu-id="aee40-237">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="aee40-238">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="aee40-238">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="aee40-239">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="aee40-239">4: Office Communications Server 2007 R2</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="aee40-240">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-240">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="aee40-241">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-241">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-242">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="aee40-242">msRTCSIP-BackEndServer</span></span></p></td>
<td><p><span data-ttu-id="aee40-243">Este atributo especifica o FQDN do servidor back-end do pool.</span><span class="sxs-lookup"><span data-stu-id="aee40-243">This attribute specifies the FQDN of the Back End Server of the pool.</span></span> <span data-ttu-id="aee40-244">Como só pode haver um único servidor back-end por pool, este é um atributo de valor único.</span><span class="sxs-lookup"><span data-stu-id="aee40-244">Because there can only be a single Back End Server per pool, this is a single-valued attribute.</span></span></p>
<p><span data-ttu-id="aee40-245">O valor válido para cada segmento é 63 caracteres; o valor válido para o FQDN inteiro é de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="aee40-245">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="aee40-246">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="aee40-246">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-247">msRTCSIP-ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="aee40-247">msRTCSIP-ConferenceDirectoryHomePool</span></span></p></td>
<td><p><span data-ttu-id="aee40-248">Este atributo contém o identificador do pool que hospeda o diretório de conferências.</span><span class="sxs-lookup"><span data-stu-id="aee40-248">This attribute contains the identifier of the pool that hosts the conference directory.</span></span></p></td>
<td><p><span data-ttu-id="aee40-249">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="aee40-249">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-250">msRTCSIP-ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="aee40-250">msRTCSIP-ConferenceDirectoryId</span></span></p></td>
<td><p><span data-ttu-id="aee40-251">Este atributo contém o identificador de um diretório de conferência.</span><span class="sxs-lookup"><span data-stu-id="aee40-251">This attribute contains the identifier of a conference directory.</span></span></p></td>
<td><p><span data-ttu-id="aee40-252">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="aee40-252">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-253">msRTCSIP-ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="aee40-253">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p></td>
<td><p><span data-ttu-id="aee40-254">Este atributo contém o identificador do pool ao qual o diretório de conferência está sendo movido.</span><span class="sxs-lookup"><span data-stu-id="aee40-254">This attribute contains the identifier of the pool to which the conference directory is being moved.</span></span></p></td>
<td><p><span data-ttu-id="aee40-255">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="aee40-255">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-256">msRTCSIP-padrão</span><span class="sxs-lookup"><span data-stu-id="aee40-256">msRTCSIP-Default</span></span></p></td>
<td><p><span data-ttu-id="aee40-257">Este atributo booliano define se o uso do telefone é um uso padrão.</span><span class="sxs-lookup"><span data-stu-id="aee40-257">This Boolean attribute defines whether the phone usage is a default usage.</span></span> <span data-ttu-id="aee40-258">Se esse atributo for definido como <strong>true</strong>, o uso de telefone será um uso padrão e não poderá ser excluído pelo administrador.</span><span class="sxs-lookup"><span data-stu-id="aee40-258">If this attribute is set to <strong>TRUE</strong>, the phone usage is a default usage and cannot be deleted by the administrator.</span></span> <span data-ttu-id="aee40-259">Se esse atributo for definido como <strong>false</strong>, o uso poderá ser excluído.</span><span class="sxs-lookup"><span data-stu-id="aee40-259">If this attribute is set to <strong>FALSE</strong>, the usage can be deleted.</span></span></p></td>
<td><p><span data-ttu-id="aee40-260">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-260">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-261">msRTCSIP-DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="aee40-261">msRTCSIP-DefaultCWAExternalURL</span></span></p></td>
<td><p><span data-ttu-id="aee40-262">Este atributo identifica a URL do Communicator Web Access para usuários que estão fora da organização.</span><span class="sxs-lookup"><span data-stu-id="aee40-262">This attribute identifies the Communicator Web Access URL for users who are outside the organization.</span></span></p></td>
<td><p><span data-ttu-id="aee40-263">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="aee40-263">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-264">msRTCSIP-DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="aee40-264">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
<td><p><span data-ttu-id="aee40-265">Este atributo identifica a URL do Communicator Web Access para usuários que estão dentro da organização.</span><span class="sxs-lookup"><span data-stu-id="aee40-265">This attribute identifies the Communicator Web Access URL for users who are inside the organization.</span></span></p></td>
<td><p><span data-ttu-id="aee40-266">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="aee40-266">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-267">msRTCSIP-DefaultLocationProfileLink (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-267">msRTCSIP-DefaultLocationProfileLink (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-268">Este atributo de valor único contém o nome diferenciado (DN) de um objeto de classe de perfil de local atribuído a ele.</span><span class="sxs-lookup"><span data-stu-id="aee40-268">This single-valued attribute contains the distinguished name (DN) of a location profile class object assigned to it.</span></span></p>
<p><span data-ttu-id="aee40-269">Link encaminhar: <strong>link ID 11036</strong></span><span class="sxs-lookup"><span data-stu-id="aee40-269">Forward link: <strong>Link ID 11036</strong></span></span></p>
<p><span data-ttu-id="aee40-270">O vínculo inverso correspondente é <strong>msRTCSIP-ServerReferenceBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="aee40-270">The corresponding backward link is <strong>msRTCSIP-ServerReferenceBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="aee40-271">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-271">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-272">msRTCSIP-DefaultPolicy (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-272">msRTCSIP-DefaultPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-273">Este atributo booliano especifica se a política é uma política padrão.</span><span class="sxs-lookup"><span data-stu-id="aee40-273">This Boolean attribute specifies whether the policy is a default policy.</span></span> <span data-ttu-id="aee40-274">A política é uma política padrão quando definida como <strong>true</strong>.</span><span class="sxs-lookup"><span data-stu-id="aee40-274">The policy is a default policy when set to <strong>TRUE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="aee40-275">Novo no Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="aee40-275">New in Office Communications Server 2007</span></span></p>
<p><span data-ttu-id="aee40-276">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-276">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-277">msRTCSIP-DefaultRouteToEdgeProxy (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-277">msRTCSIP-DefaultRouteToEdgeProxy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-278">Este atributo especifica o FQDN do servidor de borda que executa o serviço de borda de acesso, se ele puder ser acessado diretamente ou do balanceador de carga de hardware para um pool de servidores que executam o serviço de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="aee40-278">This attribute specifies the FQDN of either the Edge Server running the Access Edge service, if it can be accessed directly, or of the hardware load balancer for a pool of servers running Access Edge service.</span></span> <span data-ttu-id="aee40-279">Se os servidores que executam o serviço de borda de acesso podem ser acessados apenas por um ou mais directors, este atributo especifica o FQDN e, opcionalmente, o número da porta do diretor ou do balanceador de carga de hardware que atendem a um pool de diretores.</span><span class="sxs-lookup"><span data-stu-id="aee40-279">If the servers running Access Edge service can be accessed only through one or more Directors, this attribute specifies the FQDN and, optionally, the port number of the Director or of the hardware load balancer serving a Director pool.</span></span></p>
<p><span data-ttu-id="aee40-280">O valor válido para cada segmento é 63 caracteres; o valor válido para o FQDN inteiro é de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="aee40-280">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="aee40-281">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="aee40-281">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="aee40-282">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-282">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-283">msRTCSIP-DefaultRouteToEdgeProxyPort (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-283">msRTCSIP-DefaultRouteToEdgeProxyPort (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-284">Este atributo representa o número da porta que deve ser usada para se conectar ao servidor que executa o serviço de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="aee40-284">This attribute represents the port number that should be used to connect to the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="aee40-285">O valor válido é um valor inteiro que especifica a porta a ser usada.</span><span class="sxs-lookup"><span data-stu-id="aee40-285">The valid value is an integer value specifying the port to be used.</span></span> <span data-ttu-id="aee40-286">O valor padrão é 5061.</span><span class="sxs-lookup"><span data-stu-id="aee40-286">The default value is 5061.</span></span></p></td>
<td><p><span data-ttu-id="aee40-287">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="aee40-287">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="aee40-288">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-288">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-289">msRTCSIP-DefPresenceSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-289">msRTCSIP-DefPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-290">Este atributo representa o período de tempo limite da assinatura de presença padrão.</span><span class="sxs-lookup"><span data-stu-id="aee40-290">This attribute represents the default presence subscription time-out period.</span></span></p></td>
<td><p><span data-ttu-id="aee40-291">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-291">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-292">msRTCSIP-DefRegistrationTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-292">msRTCSIP-DefRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-293">Este atributo representa a janela do tempo limite de registro padrão.</span><span class="sxs-lookup"><span data-stu-id="aee40-293">This attribute represents the default registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="aee40-294">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-294">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-295">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-295">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-296">Este atributo representa a janela de tempo limite da assinatura de dados de roaming padrão.</span><span class="sxs-lookup"><span data-stu-id="aee40-296">This attribute represents the default roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="aee40-297">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-297">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-298">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="aee40-298">msRTCSIP-DeploymentLocator</span></span></p></td>
<td><p><span data-ttu-id="aee40-299">Este atributo é usado em uma topologia de domínio dividido e contém um FQDN (nome de domínio totalmente qualificado).</span><span class="sxs-lookup"><span data-stu-id="aee40-299">This attribute is used in a split domain topology and contains a fully qualified domain name (FQDN).</span></span></p></td>
<td><p><span data-ttu-id="aee40-300">Novo no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-300">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-301">msRTCSIP-Description (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-301">msRTCSIP-Description (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-302">Este atributo de cadeia de caracteres UNICODE de valor único contém uma descrição amigável da rota de telefone ou da regra de normalização.</span><span class="sxs-lookup"><span data-stu-id="aee40-302">This single-valued UNICODE string attribute contains a friendly description of this phone route or normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="aee40-303">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-303">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="aee40-304">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-304">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-305">msRTCSIP-DomainData</span><span class="sxs-lookup"><span data-stu-id="aee40-305">msRTCSIP-DomainData</span></span></p></td>
<td><p><span data-ttu-id="aee40-306">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="aee40-306">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-307">msRTCSIP-DomainName</span><span class="sxs-lookup"><span data-stu-id="aee40-307">msRTCSIP-DomainName</span></span></p></td>
<td><p><span data-ttu-id="aee40-308">Este atributo representa um domínio configurado para o registrador.</span><span class="sxs-lookup"><span data-stu-id="aee40-308">This attribute represents a domain configured for the Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-309">msRTCSIP-EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="aee40-309">msRTCSIP-EdgeProxyData</span></span></p></td>
<td><p><span data-ttu-id="aee40-310">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="aee40-310">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="aee40-311">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="aee40-311">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-312">msRTCSIP-EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="aee40-312">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="aee40-313">Este atributo especifica o FQDN do servidor que executa o serviço de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="aee40-313">This attribute specifies the FQDN of the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="aee40-314">O valor válido para cada segmento é 63 caracteres; o valor válido para o FQDN inteiro é de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="aee40-314">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="aee40-315">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="aee40-315">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-316">msRTCSIP-EnableBestEffortNotify (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-316">msRTCSIP-EnableBestEffortNotify (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-317">Este atributo controla se um servidor gera uma solicitação de notificação de melhor esforço (benotificar), em vez de uma solicitação de notificação, em resposta a uma solicitação de assinatura de um cliente.</span><span class="sxs-lookup"><span data-stu-id="aee40-317">This attribute controls whether a server generates a Best Effort NOTIFY (BENOTIFY) request, instead of a NOTIFY request, in response to a SUBSCRIBE request from a client.</span></span> <span data-ttu-id="aee40-318">BENOTIFY é uma extensão de aumento de desempenho para o handshake de notificação de assinatura onde o servidor gera solicitações de notificação de atendimento, em vez de solicitações de notificação regulares.</span><span class="sxs-lookup"><span data-stu-id="aee40-318">BENOTIFY is a performance-enhancing extension to the subscribe notification handshake where the server generates BENOTIFY requests, instead of regular NOTIFY requests.</span></span> <span data-ttu-id="aee40-319">O benefício de desempenho é que uma solicitação de notificação de atendimento não requer uma resposta de 200 OK do cliente à medida que a solicitação de notificação faz.</span><span class="sxs-lookup"><span data-stu-id="aee40-319">The performance benefit is that a BENOTIFY request does not require a 200 OK response from the client as the NOTIFY request does.</span></span></p>
<p><span data-ttu-id="aee40-320">Os valores válidos são <strong>true</strong> ou <strong>false</strong>.</span><span class="sxs-lookup"><span data-stu-id="aee40-320">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="aee40-321">O Live Communications Server 2003 não dá suporte a solicitações de notificação de notificações.</span><span class="sxs-lookup"><span data-stu-id="aee40-321">Live Communications Server 2003 does not support BENOTIFY requests.</span></span> <span data-ttu-id="aee40-322">Para interoperar com aplicativos de servidor escritos com a API de servidor do Live Communications Server 2003 em execução no Live Communications Server 2005 e servidores de terceiros, as solicitações de notificações podem ser desabilitadas definindo seu valor como <STRONG>false</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="aee40-322">To interoperate with server applications written with the Live Communications Server 2003 server API running on Live Communications Server 2005 and third-party servers, BENOTIFY requests can be disabled by setting its value to <STRONG>FALSE</STRONG>.</span></span> <span data-ttu-id="aee40-323">O benotification não faz parte do processo de padronização SIP do IETF (Internet Engineering Task Force).</span><span class="sxs-lookup"><span data-stu-id="aee40-323">BENOTIFY is not currently part of the IETF (Internet Engineering Task Force) SIP standardization process.</span></span>


</div></td>
<td><p><span data-ttu-id="aee40-324">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="aee40-324">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="aee40-325">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-325">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-326">msRTCSIP-EnableFederation (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-326">msRTCSIP-EnableFederation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-327">Este atributo é uma opção global que os administradores de ti usam para configurar se os usuários têm permissão para se comunicar com os usuários de outras organizações.</span><span class="sxs-lookup"><span data-stu-id="aee40-327">This attribute is a global switch that IT administrators use to configure whether users are allowed to communicate with users from other organizations.</span></span> <span data-ttu-id="aee40-328">Permite que um administrador substitua o atributo <strong>FederationEnabled</strong> de um usuário individual.</span><span class="sxs-lookup"><span data-stu-id="aee40-328">It enables an administrator to overwrite an individual user’s <strong>FederationEnabled</strong> attribute.</span></span> <span data-ttu-id="aee40-329">Esse atributo pode ser útil para ajudar a proteger a rede interna contra ataques da Internet que podem ser causados por worms, vírus ou ataques direcionados à empresa.</span><span class="sxs-lookup"><span data-stu-id="aee40-329">This attribute can be useful to help protect the internal network from Internet attacks that may be caused by worms, viruses, or targeted attacks on the company.</span></span></p>
<p><span data-ttu-id="aee40-330">Os valores válidos (e as posições de bit associadas) são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="aee40-330">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="aee40-331">1: habilitado para conectividade de IM pública (posição de bit 0)</span><span class="sxs-lookup"><span data-stu-id="aee40-331">1: Enabled for public IM connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="aee40-332">2: reservado (posição de bit 1)</span><span class="sxs-lookup"><span data-stu-id="aee40-332">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="aee40-333">4: reservado (posição de bit 2)</span><span class="sxs-lookup"><span data-stu-id="aee40-333">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="aee40-334">8: reservado (posição de bit 3)</span><span class="sxs-lookup"><span data-stu-id="aee40-334">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="aee40-335">16: controle de chamada remota habilitado [telefonia] (posição de bit 4)</span><span class="sxs-lookup"><span data-stu-id="aee40-335">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="aee40-336">64: AllowOrganizeMeetingWithAnonymousParticipants is (permitir que os usuários convidem usuários anônimos para reuniões (posição de bit 6)</span><span class="sxs-lookup"><span data-stu-id="aee40-336">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="aee40-337">128: UCEnabled (habilitar usuários para comunicações unificadas) (posição de bit 7)</span><span class="sxs-lookup"><span data-stu-id="aee40-337">128: UCEnabled (enable users for unified communications) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="aee40-338">256: EnabledForEnhancedPresence (habilitar usuário para conectividade de IM pública) (posição de bit 8)</span><span class="sxs-lookup"><span data-stu-id="aee40-338">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="aee40-339">512: RemoteCallControlDualMode (posição de bit 9)</span><span class="sxs-lookup"><span data-stu-id="aee40-339">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="aee40-340">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="aee40-340">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="aee40-341">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-341">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-342">msRTCSIP-EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="aee40-342">msRTCSIP-EnterpriseServices</span></span></p></td>
<td><p><span data-ttu-id="aee40-343">Este atributo indica se os serviços corporativos são carregados em um determinado servidor.</span><span class="sxs-lookup"><span data-stu-id="aee40-343">This attribute indicates whether the Enterprise Services are loaded on the given server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-344">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="aee40-344">msRTCSIP-ExtensionData</span></span></p></td>
<td><p><span data-ttu-id="aee40-345">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="aee40-345">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-346">msRTCSIP-ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="aee40-346">msRTCSIP-ExternalAccessCode</span></span></p></td>
<td><p><span data-ttu-id="aee40-347">Este atributo contém o código de discagem para acesso externo.</span><span class="sxs-lookup"><span data-stu-id="aee40-347">This attribute contains the dial code for external access.</span></span></p></td>
<td><p><span data-ttu-id="aee40-348">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="aee40-348">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-349">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="aee40-349">msRTCSIP-FederationEnabled</span></span></p></td>
<td><p><span data-ttu-id="aee40-350">Este atributo controla se um único usuário está habilitado para Federação.</span><span class="sxs-lookup"><span data-stu-id="aee40-350">This attribute controls whether a single user is enabled for federation.</span></span> <span data-ttu-id="aee40-351">Ela é imposta pela camada de serviços corporativos.</span><span class="sxs-lookup"><span data-stu-id="aee40-351">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="aee40-352">Ele está marcado para replicação do catálogo global.</span><span class="sxs-lookup"><span data-stu-id="aee40-352">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="aee40-353">Os valores válidos são <strong>true</strong> ou <strong>false</strong>.</span><span class="sxs-lookup"><span data-stu-id="aee40-353">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="aee40-354">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="aee40-354">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-355">msRTCSIP-FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="aee40-355">msRTCSIP-FrontEndServers</span></span></p></td>
<td><p><span data-ttu-id="aee40-356">Este atributo é uma lista de vários valores dos nomes de domínio de todos os servidores Enterprise Edition associados a um pool.</span><span class="sxs-lookup"><span data-stu-id="aee40-356">This attribute is a multi-valued list of the domain names of all Enterprise Edition servers associated with a pool.</span></span></p>
<p><span data-ttu-id="aee40-357">Vínculo inverso: <strong>link ID 11023</strong></span><span class="sxs-lookup"><span data-stu-id="aee40-357">Back link: <strong>Link ID 11023</strong></span></span></p>
<p><span data-ttu-id="aee40-358">O vínculo sequencial correspondente a este vínculo inverso é <strong>msRTCSIP-PoolAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="aee40-358">The corresponding forward link to this back link is <strong>msRTCSIP-PoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="aee40-359">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="aee40-359">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-360">msRTCSIP-gateways (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-360">msRTCSIP-Gateways (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-361">Este atributo de cadeia de caracteres de valores múltiplos contém uma lista de gateways e portas (por gateway).</span><span class="sxs-lookup"><span data-stu-id="aee40-361">This multi-valued string attribute contains a list of gateways and ports (per gateway).</span></span></p></td>
<td><p><span data-ttu-id="aee40-362">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-362">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-363">msRTCSIP-GlobalSettingsData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-363">msRTCSIP-GlobalSettingsData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-364">Este atributo armazena nomes: pares de valores.</span><span class="sxs-lookup"><span data-stu-id="aee40-364">This attribute stores name:value pairs.</span></span> <span data-ttu-id="aee40-365">O par nome já definido: valor é para a configuração <strong>permitir sondagem de presença</strong> .</span><span class="sxs-lookup"><span data-stu-id="aee40-365">The already-defined name:value pair is for the <strong>allow polling for presence</strong> setting.</span></span></p></td>
<td><p><span data-ttu-id="aee40-366">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-366">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-367">msRTCSIP-Groupingid</span><span class="sxs-lookup"><span data-stu-id="aee40-367">msRTCSIP-GroupingID</span></span></p></td>
<td><p><span data-ttu-id="aee40-368">Este atributo é um identificador exclusivo de um grupo usado para agrupar entradas do catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="aee40-368">This attribute is a unique identifier of a group that is used to group address book entries.</span></span></p></td>
<td><p><span data-ttu-id="aee40-369">Novo no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-369">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-370">msRTCSIP-HomeServer (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-370">msRTCSIP-HomeServer (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="aee40-371">Novo no Live Communications Server 2003 (não usado).</span><span class="sxs-lookup"><span data-stu-id="aee40-371">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="aee40-372">Obsoleto no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="aee40-372">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-373">msRTCSIP-HomeServerString (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-373">msRTCSIP-HomeServerString (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="aee40-374">Novo no Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="aee40-374">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="aee40-375">Obsoleto no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="aee40-375">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-376">msRTCSIP-HomeUsers (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-376">msRTCSIP-HomeUsers (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="aee40-377">Novo no Live Communications Server 2003 (não usado).</span><span class="sxs-lookup"><span data-stu-id="aee40-377">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="aee40-378">Obsoleto no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="aee40-378">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-379">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="aee40-379">msRTCSIP-InternetAccessEnabled</span></span></p></td>
<td><p><span data-ttu-id="aee40-380">Este atributo controla se um único usuário está habilitado para o acesso de usuário externo.</span><span class="sxs-lookup"><span data-stu-id="aee40-380">This attribute controls whether a single user is enabled for outside user access.</span></span> <span data-ttu-id="aee40-381">Ela é imposta pela camada de serviços corporativos.</span><span class="sxs-lookup"><span data-stu-id="aee40-381">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="aee40-382">Ele está marcado para replicação do catálogo global.</span><span class="sxs-lookup"><span data-stu-id="aee40-382">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="aee40-383">Os valores válidos são <strong>true</strong> ou <strong>false</strong>.</span><span class="sxs-lookup"><span data-stu-id="aee40-383">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="aee40-384">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="aee40-384">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-385">msRTCSIP-IsMaster (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-385">msRTCSIP-IsMaster (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="aee40-386">Novo no Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="aee40-386">New in Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="aee40-387">Obsoleto no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="aee40-387">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-388">Linha msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="aee40-388">msRTCSIP-Line</span></span></p></td>
<td><p><span data-ttu-id="aee40-389">Este atributo de valor único contém a ID do dispositivo (o URI do SIP ou o URI de TEL do telefone que os controles de usuário) usados pelo Lync para telefonia.</span><span class="sxs-lookup"><span data-stu-id="aee40-389">This single-valued attribute contains the device ID (either the SIP URI or the TEL URI of the phone the user controls) used by Lync for telephony.</span></span> <span data-ttu-id="aee40-390">Esse atributo é marcado para replicação de catálogo global e é indexado.</span><span class="sxs-lookup"><span data-stu-id="aee40-390">This attribute is marked for Global Catalog replication and is indexed.</span></span> <span data-ttu-id="aee40-391">Se um usuário estiver habilitado para o Enterprise Voice, este atributo armazenará a versão normalizada E. 164 do número de telefone do usuário.</span><span class="sxs-lookup"><span data-stu-id="aee40-391">If a user is enabled for Enterprise Voice, this attribute stores the E.164 normalized version of the user’s phone number.</span></span></p></td>
<td><p><span data-ttu-id="aee40-392">Novo no Microsoft Office Live Communications Server 2005 com SP1</span><span class="sxs-lookup"><span data-stu-id="aee40-392">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-393">msRTCSIP-LineServer</span><span class="sxs-lookup"><span data-stu-id="aee40-393">msRTCSIP-LineServer</span></span></p></td>
<td><p><span data-ttu-id="aee40-394">Este atributo de valor único contém o URI SIP do servidor de gateway CSTA-SIP.</span><span class="sxs-lookup"><span data-stu-id="aee40-394">This single-valued attribute contains the SIP URI of the CSTA-SIP gateway server.</span></span> <span data-ttu-id="aee40-395">Este atributo está marcado para replicação de catálogo global, mas não está indexado.</span><span class="sxs-lookup"><span data-stu-id="aee40-395">This attribute is marked for Global Catalog replication but is not indexed.</span></span></p></td>
<td><p><span data-ttu-id="aee40-396">Novo no Microsoft Office Live Communications Server 2005 com SP1</span><span class="sxs-lookup"><span data-stu-id="aee40-396">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-397">msRTCSIP-LocalNormalizationData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-397">msRTCSIP-LocalNormalizationData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-398">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="aee40-398">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="aee40-399">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-399">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="aee40-400">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-400">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-401">msRTCSIP-LocalNormalizationLinks (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-401">msRTCSIP-LocalNormalizationLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-402">Este atributo com valores múltiplos contém uma lista de nomes distintos de normalização (DN) locais associados a esse perfil de local.</span><span class="sxs-lookup"><span data-stu-id="aee40-402">This multi-valued attribute contains a list of local normalization distinguished names (DN) associated with this location profile.</span></span> <span data-ttu-id="aee40-403">O tipo desse atributo é um binário DN.</span><span class="sxs-lookup"><span data-stu-id="aee40-403">The type of this attribute is a DN binary.</span></span> <span data-ttu-id="aee40-404">Há uma relação um-para-muitos entre o perfil de local e as regras de normalização local.</span><span class="sxs-lookup"><span data-stu-id="aee40-404">There is a one-to-many relationship between location profile and local normalization rules.</span></span> <span data-ttu-id="aee40-405">A ordenação da lista de DNs de normalização local deve ser mantida na ordem especificada pelo administrador.</span><span class="sxs-lookup"><span data-stu-id="aee40-405">The ordering of the list of local normalization DNs must be maintained in the order specified by the administrator.</span></span> <span data-ttu-id="aee40-406">A preservação do pedido é mantida pela parte binária do binário DN, que especifica o índice de pedidos.</span><span class="sxs-lookup"><span data-stu-id="aee40-406">The preservation of order is maintained by the binary portion of the DN binary, which specifies the order index.</span></span></p>
<p><span data-ttu-id="aee40-407">Link encaminhar: <strong>link ID 11034</strong></span><span class="sxs-lookup"><span data-stu-id="aee40-407">Forward link: <strong>Link ID 11034</strong></span></span></p>
<p><span data-ttu-id="aee40-408">O vínculo inverso correspondente a este atributo de vínculo sequencial é <strong>msRTCSIP-LocationProfileBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="aee40-408">The corresponding back link to this forward link attribute is <strong>msRTCSIP-LocationProfileBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="aee40-409">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-409">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="aee40-410">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-410">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-411">msRTCSIP-LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="aee40-411">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
<td><p><span data-ttu-id="aee40-412">Este atributo contém uma lista de opções para a regra de normalização.</span><span class="sxs-lookup"><span data-stu-id="aee40-412">This attribute contains a list of options for the normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="aee40-413">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="aee40-413">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-414">msRTCSIP-LocationName (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-414">msRTCSIP-LocationName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-415">Esse atributo de valor único contém um nome amigável para o perfil de local que indica qual local esse perfil representa.</span><span class="sxs-lookup"><span data-stu-id="aee40-415">This single-valued attribute contains a friendly name for the location profile that indicates which location this profile represents.</span></span> <span data-ttu-id="aee40-416">Como pode haver vários perfis de local, o administrador precisa de uma maneira de distinguir entre diferentes perfis.</span><span class="sxs-lookup"><span data-stu-id="aee40-416">Because there can be multiple location profiles, the administrator needs a way to distinguish between different profiles.</span></span></p></td>
<td><p><span data-ttu-id="aee40-417">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-417">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="aee40-418">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-418">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-419">msRTCSIP-locationProfileBL (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-419">msRTCSIP-locationProfileBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-420">Este atributo com valores múltiplos contém uma lista de nomes distintos do perfil de local.</span><span class="sxs-lookup"><span data-stu-id="aee40-420">This multi-valued attribute contains a list of location profile distinguished names.</span></span> <span data-ttu-id="aee40-421">Este atributo especifica o vínculo inverso com um ou mais perfis de local.</span><span class="sxs-lookup"><span data-stu-id="aee40-421">This attribute specifies the back link to one or more location profiles.</span></span></p>
<p><span data-ttu-id="aee40-422">Vínculo inverso: <strong>link ID 11035</strong></span><span class="sxs-lookup"><span data-stu-id="aee40-422">Back link: <strong>Link ID 11035</strong></span></span></p>
<p><span data-ttu-id="aee40-423">Este atributo corresponde ao vínculo sequencial <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="aee40-423">This attribute corresponds to the forward link <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="aee40-424">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-424">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="aee40-425">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-425">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-426">msRTCSIP-LocationProfileData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-426">msRTCSIP-LocationProfileData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-427">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="aee40-427">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="aee40-428">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-428">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="aee40-429">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-429">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-430">msRTCSIP-LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="aee40-430">msRTCSIP-LocationProfileOptions</span></span></p></td>
<td><p><span data-ttu-id="aee40-431">Este atributo contém as opções para o perfil de local.</span><span class="sxs-lookup"><span data-stu-id="aee40-431">This attribute contains the options for the location profile.</span></span></p></td>
<td><p><span data-ttu-id="aee40-432">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="aee40-432">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-433">msRTCSIP-MappingContact</span><span class="sxs-lookup"><span data-stu-id="aee40-433">msRTCSIP-MappingContact</span></span></p></td>
<td><p><span data-ttu-id="aee40-434">Este atributo de vários valores contém uma lista de contatos de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="aee40-434">This multiple-value attribute holds a list of application contacts.</span></span></p></td>
<td><p><span data-ttu-id="aee40-435">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="aee40-435">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-436">msRTCSIP-MappingLocation</span><span class="sxs-lookup"><span data-stu-id="aee40-436">msRTCSIP-MappingLocation</span></span></p></td>
<td><p><span data-ttu-id="aee40-437">Este atributo de vários valores contém uma lista de perfis de local.</span><span class="sxs-lookup"><span data-stu-id="aee40-437">This multiple-value attribute holds a list of location profiles.</span></span></p></td>
<td><p><span data-ttu-id="aee40-438">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="aee40-438">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-439">msRTCSIP-MaxNumOutstandingSearchPerServer (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-439">msRTCSIP-MaxNumOutstandingSearchPerServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-440">Este atributo representa o número máximo de solicitações de pesquisa pendentes por servidor.</span><span class="sxs-lookup"><span data-stu-id="aee40-440">This attribute represents the maximum number of outstanding search requests per server.</span></span></p></td>
<td><p><span data-ttu-id="aee40-441">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-441">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-442">msRTCSIP-MaxNumSubscriptionsPerUser (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-442">msRTCSIP-MaxNumSubscriptionsPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-443">O atributo representa o número máximo de inscrições por usuário.</span><span class="sxs-lookup"><span data-stu-id="aee40-443">The attribute represents the maximum number of subscriptions per user.</span></span></p></td>
<td><p><span data-ttu-id="aee40-444">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-444">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-445">msRTCSIP-MaxPresenceSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-445">msRTCSIP-MaxPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-446">Este atributo representa a janela de tempo limite máximo da assinatura.</span><span class="sxs-lookup"><span data-stu-id="aee40-446">This attribute represents the maximum subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="aee40-447">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-447">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-448">msRTCSIP-MaxRegistrationsTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-448">msRTCSIP-MaxRegistrationsTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-449">Este atributo representa a janela de tempo limite de registros máximos.</span><span class="sxs-lookup"><span data-stu-id="aee40-449">This attribute represents the maximum registrations time-out window.</span></span></p></td>
<td><p><span data-ttu-id="aee40-450">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-450">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-451">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-451">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-452">Este atributo representa a janela de tempo limite máximo de assinaturas de dados móveis.</span><span class="sxs-lookup"><span data-stu-id="aee40-452">This attribute represents the maximum roaming data subscriptions time-out window.</span></span></p></td>
<td><p><span data-ttu-id="aee40-453">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-453">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-454">msRTCSIP-MCUData</span><span class="sxs-lookup"><span data-stu-id="aee40-454">msRTCSIP-MCUData</span></span></p></td>
<td><p><span data-ttu-id="aee40-455">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="aee40-455">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="aee40-456">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-456">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-457">msRTCSIP-MCUFactoryAddress</span><span class="sxs-lookup"><span data-stu-id="aee40-457">msRTCSIP-MCUFactoryAddress</span></span></p></td>
<td><p><span data-ttu-id="aee40-458">Este atributo é um atributo de ponto de controle de serviço na classe Computer que especifica um link de volta à fábrica da unidade de controle multiponto (MCU) à qual ele pertence.</span><span class="sxs-lookup"><span data-stu-id="aee40-458">This attribute is a service control point attribute under the computer class that specifies a link back to the multipoint control unit (MCU) Factory to which it belongs.</span></span> <span data-ttu-id="aee40-459">Esse atributo e o ponto de controle de serviço são criados para cada Microsoft MCU.</span><span class="sxs-lookup"><span data-stu-id="aee40-459">This service control point and attribute is created for every Microsoft MCU.</span></span> <span data-ttu-id="aee40-460">Cada Microsoft MCU deve localizar o servidor back-end do pool ao qual ele pertence, para recuperar as configurações de nível de pool.</span><span class="sxs-lookup"><span data-stu-id="aee40-460">Each Microsoft MCU must find the Back End Server of the pool to which it belongs, in order to retrieve pool-level settings from it.</span></span></p>
<p><span data-ttu-id="aee40-461">O valor desse atributo é o nome diferenciado (DN) da fábrica MCU.</span><span class="sxs-lookup"><span data-stu-id="aee40-461">The value of this attribute is the distinguished name (DN) of the MCU Factory.</span></span> <span data-ttu-id="aee40-462">Este é um atributo de valor único e marcado para replicação de catálogo global.</span><span class="sxs-lookup"><span data-stu-id="aee40-462">This is a single-valued attribute and marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="aee40-463">Link encaminhar: <strong>link ID 11026</strong></span><span class="sxs-lookup"><span data-stu-id="aee40-463">Forward link: <strong>Link ID 11026</strong></span></span></p>
<p><span data-ttu-id="aee40-464">O vínculo inverso correspondente a este atributo de vínculo sequencial é <strong>msRTCSIP-MCUServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="aee40-464">The corresponding back link to this forward link attribute is <strong>msRTCSIP-MCUServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="aee40-465">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-465">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-466">msRTCSIP-MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="aee40-466">msRTCSIP-MCUFactoryData</span></span></p></td>
<td><p><span data-ttu-id="aee40-467">Este é um atributo reservado de cadeia de caracteres múltipla.</span><span class="sxs-lookup"><span data-stu-id="aee40-467">This is a multi-string reserved attribute.</span></span> <span data-ttu-id="aee40-468">As configurações armazenadas nesse atributo são representadas como pares nome = valor.</span><span class="sxs-lookup"><span data-stu-id="aee40-468">Settings stored in this attribute are represented as name=value pairs.</span></span> <span data-ttu-id="aee40-469">Os pares name = value atualmente definidos são:</span><span class="sxs-lookup"><span data-stu-id="aee40-469">Currently defined name=value pairs are:</span></span></p>
<ul>
<li><p><span data-ttu-id="aee40-470">FactoryURL = &lt; URL&gt;</span><span class="sxs-lookup"><span data-stu-id="aee40-470">FactoryURL = &lt;URL&gt;</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="aee40-471">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-471">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-472">msRTCSIP-MCUFactoryPath</span><span class="sxs-lookup"><span data-stu-id="aee40-472">msRTCSIP-MCUFactoryPath</span></span></p></td>
<td><p><span data-ttu-id="aee40-473">Este é um atributo de valor único que contém o nome diferenciado (DN) de uma única fábrica de MCU associada a um pool.</span><span class="sxs-lookup"><span data-stu-id="aee40-473">This is a single-valued attribute that contains the distinguished name (DN) of a single MCU factory associated with a pool.</span></span></p>
<p><span data-ttu-id="aee40-474">Link encaminhar: <strong>link ID 11024</strong></span><span class="sxs-lookup"><span data-stu-id="aee40-474">Forward link: <strong>Link ID 11024</strong></span></span></p>
<p><span data-ttu-id="aee40-475">O vínculo inverso correspondente a este atributo de vínculo sequencial é <strong>msRTCSIP-PoolAddresses</strong>.</span><span class="sxs-lookup"><span data-stu-id="aee40-475">The corresponding back link to this forward link attribute is <strong>msRTCSIP-PoolAddresses</strong>.</span></span></p></td>
<td><p><span data-ttu-id="aee40-476">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-476">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-477">msRTCSIP-MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="aee40-477">msRTCSIP-MCUFactoryProviderID</span></span></p></td>
<td><p><span data-ttu-id="aee40-478">Este atributo é uma cadeia de caracteres de valor único que especifica o GUID do provedor de fábrica MCU.</span><span class="sxs-lookup"><span data-stu-id="aee40-478">This attribute is a single-valued string that specifies the GUID of the MCU factory provider.</span></span> <span data-ttu-id="aee40-479">Com base no valor de GUID, o processo de fábrica da MCU determina se deve ser atendido este tipo de MCU.</span><span class="sxs-lookup"><span data-stu-id="aee40-479">Based on the GUID value, the MCU factory process determines whether to service this MCU type.</span></span> <span data-ttu-id="aee40-480">Se o valor de GUID for <strong>{F0810510-424F-46ef-84fe-6CC720DF1791}</strong>, o processo de fábrica MCU (disponível por padrão no Lync Server) o processará.</span><span class="sxs-lookup"><span data-stu-id="aee40-480">If the GUID value is <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, then the MCU factory process (available by default in Lync Server) will process it.</span></span> <span data-ttu-id="aee40-481">Para qualquer outro valor de GUID, o processo de fábrica MCU não irá atender ao tipo MCU.</span><span class="sxs-lookup"><span data-stu-id="aee40-481">For any other GUID value, the MCU factory process will not service the MCU type.</span></span></p></td>
<td><p><span data-ttu-id="aee40-482">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-482">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-483">msRTCSIP-MCUServers</span><span class="sxs-lookup"><span data-stu-id="aee40-483">msRTCSIP-MCUServers</span></span></p></td>
<td><p><span data-ttu-id="aee40-484">Este atributo é uma lista de vários valores de nomes diferenciados (DN).</span><span class="sxs-lookup"><span data-stu-id="aee40-484">This attribute is a multi-valued list of distinguished names (DN).</span></span> <span data-ttu-id="aee40-485">Este atributo contém uma lista de todos os servidores MCU do mesmo tipo e fornecedor associados a essa fábrica de MCU.</span><span class="sxs-lookup"><span data-stu-id="aee40-485">This attribute contains a list of all MCU servers of the same type and vendor associated with this MCU factory.</span></span> <span data-ttu-id="aee40-486">O valor válido para cada segmento é 63 caracteres; o valor válido para o FQDN inteiro é de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="aee40-486">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p>
<p><span data-ttu-id="aee40-487">Vínculo inverso: link ID 11027</span><span class="sxs-lookup"><span data-stu-id="aee40-487">Back link: Link ID 11027</span></span></p>
<p><span data-ttu-id="aee40-488">O vínculo sequencial correspondente a este vínculo inverso é <strong>msRTCSIP-MCUFactoryAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="aee40-488">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="aee40-489">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-489">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-490">msRTCSIP-MCUType</span><span class="sxs-lookup"><span data-stu-id="aee40-490">msRTCSIP-MCUType</span></span></p></td>
<td><p><span data-ttu-id="aee40-491">Este atributo é uma cadeia de caracteres de valor único que especifica o meio que o MCU pode lidar.</span><span class="sxs-lookup"><span data-stu-id="aee40-491">This attribute is a single-valued string that specifies the medium the MCU can handle.</span></span></p>
<p><span data-ttu-id="aee40-492">Os tipos válidos suportados são:</span><span class="sxs-lookup"><span data-stu-id="aee40-492">Supported valid types are:</span></span></p>
<ul>
<li><p><span data-ttu-id="aee40-493">Atenda</span><span class="sxs-lookup"><span data-stu-id="aee40-493">meeting</span></span></p></li>
<li><p><span data-ttu-id="aee40-494">áudio-vídeo</span><span class="sxs-lookup"><span data-stu-id="aee40-494">audio-video</span></span></p></li>
<li><p><span data-ttu-id="aee40-495">chat</span><span class="sxs-lookup"><span data-stu-id="aee40-495">chat</span></span></p></li>
<li><p><span data-ttu-id="aee40-496">Phone-conf</span><span class="sxs-lookup"><span data-stu-id="aee40-496">phone-conf</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="aee40-497">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-497">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-498">msRTCSIP-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="aee40-498">msRTCSIP-MCUVendor</span></span></p></td>
<td><p><span data-ttu-id="aee40-499">Este atributo é uma cadeia de caracteres de valor único que especifica o nome de um fornecedor MCU.</span><span class="sxs-lookup"><span data-stu-id="aee40-499">This attribute is a single-valued string that specifies an MCU vendor’s name.</span></span> <span data-ttu-id="aee40-500">Todos os Microsoft MCUs especificarão esse atributo como <strong>Microsoft Corporation</strong>.</span><span class="sxs-lookup"><span data-stu-id="aee40-500">All Microsoft MCUs will specify this attribute to be <strong>Microsoft Corporation</strong>.</span></span></p></td>
<td><p><span data-ttu-id="aee40-501">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-501">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-502">msRTCSIP-MeetingFlags (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-502">msRTCSIP-MeetingFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-503">Este atributo define opções de reunião diferentes que são habilitadas globalmente para todos os usuários ou objetos de contato.</span><span class="sxs-lookup"><span data-stu-id="aee40-503">This attribute defines different meeting options that are enabled globally for all users or contact objects.</span></span> <span data-ttu-id="aee40-504">Este atributo é um valor de máscara de bits de tipo inteiro.</span><span class="sxs-lookup"><span data-stu-id="aee40-504">This attribute is a bit-mask value of integer type.</span></span></p>
<p><span data-ttu-id="aee40-505">Os valores válidos (e as posições de bit associadas) são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="aee40-505">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="aee40-506">0: AllowOrganizeMeetingWithAnonymousParticipants is é nenhum (não permitir que os usuários convidem usuários anônimos para reuniões) (nenhum bit definido)</span><span class="sxs-lookup"><span data-stu-id="aee40-506">0: AllowOrganizeMeetingWithAnonymousParticipants is None (do not allow users to invite anonymous users to meetings) (no bits set)</span></span></p></li>
<li><p><span data-ttu-id="aee40-507">4: AllowOrganizeMeetingWithAnonymousParticipants is é todos (permitir que todos os usuários convidem usuários anônimos para reuniões) (posição de bit 2)</span><span class="sxs-lookup"><span data-stu-id="aee40-507">4: AllowOrganizeMeetingWithAnonymousParticipants is Everyone (allow all users to invite anonymous users to meetings) (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="aee40-508">8: AllowOrganizeMeetingWithAnonymousParticipants is é UsePerUserSetting (permitir que os usuários convidem usuários anônimos para reuniões com base na configuração do usuário) (posição de bit 3)</span><span class="sxs-lookup"><span data-stu-id="aee40-508">8: AllowOrganizeMeetingWithAnonymousParticipants is UsePerUserSetting (allow users to invite anonymous users to meetings based on per user setting) (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="aee40-509">16: UserPerUserMeetingPolicy (a política de reunião é definida por usuário) (posição de bit 4)</span><span class="sxs-lookup"><span data-stu-id="aee40-509">16: UserPerUserMeetingPolicy (meeting policy is defined per user) (bit position 4)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="aee40-510">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-510">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="aee40-511">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-511">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-512">msRTCSIP-MeetingPolicy (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-512">msRTCSIP-MeetingPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-513">Este atributo especifica o nome diferenciado (DN) da política que o administrador atribuiu a este usuário como um atributo de valor único.</span><span class="sxs-lookup"><span data-stu-id="aee40-513">This attribute specifies the distinguished name (DN) of the policy the administrator has assigned for this user as a single-valued attribute.</span></span></p></td>
<td><p><span data-ttu-id="aee40-514">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-514">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="aee40-515">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-515">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-516">msRTCSIP-MinPresenceSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-516">msRTCSIP-MinPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-517">Este atributo representa a janela de tempo limite de assinatura de presença mínima.</span><span class="sxs-lookup"><span data-stu-id="aee40-517">This attribute represents the minimum presence subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="aee40-518">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-518">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-519">msRTCSIP-MinRegistrationTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-519">msRTCSIP-MinRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-520">Este atributo representa a janela do tempo limite mínimo de registro.</span><span class="sxs-lookup"><span data-stu-id="aee40-520">This attribute represents the minimum registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="aee40-521">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-521">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="aee40-522">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-522">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-523">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-523">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-524">Este atributo representa a janela de tempo limite de assinatura de dados de roaming mínimo.</span><span class="sxs-lookup"><span data-stu-id="aee40-524">This attribute represents the minimum roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="aee40-525">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-525">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="aee40-526">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-526">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-527">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="aee40-527">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="aee40-528">Este atributo é usado para armazenar o backend do SQL Server espelhado usado pelo pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="aee40-528">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
<td><p><span data-ttu-id="aee40-529">Novo no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aee40-529">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-530">msRTCSIP-MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="aee40-530">msRTCSIP-MobilityFlags</span></span></p></td>
<td><p><span data-ttu-id="aee40-531">Este atributo contém opções e sinalizadores que definem as configurações de mobilidade.</span><span class="sxs-lookup"><span data-stu-id="aee40-531">This attribute contains options and flags that define mobility settings.</span></span></p></td>
<td><p><span data-ttu-id="aee40-532">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="aee40-532">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-533">msRTCSIP-MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="aee40-533">msRTCSIP-MobilityPolicy</span></span></p></td>
<td><p><span data-ttu-id="aee40-534">Este atributo contém o DN de um objeto de política de mobilidade.</span><span class="sxs-lookup"><span data-stu-id="aee40-534">This attribute contains the DN for a mobility policy object.</span></span></p></td>
<td><p><span data-ttu-id="aee40-535">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="aee40-535">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-536">msRTCSIP-NumDevicesPerUser (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-536">msRTCSIP-NumDevicesPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-537">Este atributo representa o número permitido de dispositivos nos quais um usuário pode se registrar para comunicações SIP e inscrever-se em presença.</span><span class="sxs-lookup"><span data-stu-id="aee40-537">This attribute represents the allowed number of devices on which a user can register for SIP communications and subscribe to presence.</span></span></p></td>
<td><p><span data-ttu-id="aee40-538">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-538">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="aee40-539">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-539">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-540">msRTCSIP-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="aee40-540">msRTCSIP-OptionFlags</span></span></p></td>
<td><p><span data-ttu-id="aee40-541">Este atributo especifica as opções que são habilitadas para o usuário ou objeto de contato.</span><span class="sxs-lookup"><span data-stu-id="aee40-541">This attribute specifies the options that are enabled for the user or contact object.</span></span> <span data-ttu-id="aee40-542">Este atributo é um valor de máscara de bits do tipo inteiro.</span><span class="sxs-lookup"><span data-stu-id="aee40-542">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="aee40-543">Cada opção é representada por um bit.</span><span class="sxs-lookup"><span data-stu-id="aee40-543">Each option is represented by a bit.</span></span> <span data-ttu-id="aee40-544">Este atributo está marcado para replicação de catálogo global.</span><span class="sxs-lookup"><span data-stu-id="aee40-544">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="aee40-545">Os valores válidos (e as posições de bit associadas) são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="aee40-545">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="aee40-546">1: habilitado para conectividade de mensagens instantâneas públicas (IM) (posição de bit 0)</span><span class="sxs-lookup"><span data-stu-id="aee40-546">1: Enabled for public instant messaging (IM) connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="aee40-547">2: reservado (posição de bit 1)</span><span class="sxs-lookup"><span data-stu-id="aee40-547">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="aee40-548">4: reservado (posição de bit 2)</span><span class="sxs-lookup"><span data-stu-id="aee40-548">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="aee40-549">8: reservado (posição de bit 3)</span><span class="sxs-lookup"><span data-stu-id="aee40-549">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="aee40-550">16: controle de chamada remota habilitado [telefonia] (posição de bit 4)</span><span class="sxs-lookup"><span data-stu-id="aee40-550">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="aee40-551">64: AllowOrganizeMeetingWithAnonymousParticipants is (permitir que os usuários convidem usuários anônimos para reuniões (posição de bit 6)</span><span class="sxs-lookup"><span data-stu-id="aee40-551">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="aee40-552">128: UCEnabled (habilitar usuários para UC) (posição de bit 7)</span><span class="sxs-lookup"><span data-stu-id="aee40-552">128: UCEnabled (enable users for UC) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="aee40-553">256: EnabledForEnhancedPresence (habilitar usuário para conectividade de IM pública) (posição de bit 8)</span><span class="sxs-lookup"><span data-stu-id="aee40-553">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="aee40-554">512: RemoteCallControlDualMode (posição de bit 9)</span><span class="sxs-lookup"><span data-stu-id="aee40-554">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="aee40-555">Novo no Live Communications Server 2005 com SP1.</span><span class="sxs-lookup"><span data-stu-id="aee40-555">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-556">msRTCSIP-OriginatorSID</span><span class="sxs-lookup"><span data-stu-id="aee40-556">msRTCSIP-OriginatorSID</span></span></p></td>
<td><p><span data-ttu-id="aee40-557">Esse atributo é usado em topologias de floresta central e de recursos para habilitar o logon único quando o objeto userid da conta principal do Windows NT Server é copiado para este atributo do usuário ou do objeto de contato correspondente na floresta de recursos ou central.</span><span class="sxs-lookup"><span data-stu-id="aee40-557">This attribute is used in resource and central forest topologies to enable single sign-on when a user’s ObjectSID from the Windows NT Server principal account is copied into this attribute of the corresponding user or contact object in the resource or central forest.</span></span> <span data-ttu-id="aee40-558">O Communicator Web Access pesquisa um usuário no AD DS usando este atributo ou o objeto userid.</span><span class="sxs-lookup"><span data-stu-id="aee40-558">Communicator Web Access searches for a user in AD DS using this attribute or the user’s ObjectSID.</span></span> <span data-ttu-id="aee40-559">Este atributo está marcado para replicação de catálogo global.</span><span class="sxs-lookup"><span data-stu-id="aee40-559">This attribute is marked for global catalog replication.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-560">msRTCSIP-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="aee40-560">msRTCSIP-OwnerUrn</span></span></p></td>
<td><p><span data-ttu-id="aee40-561">Este atributo é o nome de recurso uniforme (URN) do proprietário de um contato de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="aee40-561">This attribute is the Uniform Resource Name (URN) of the owner for an application contact.</span></span></p></td>
<td><p><span data-ttu-id="aee40-562">Novo no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-562">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-563">msRTCSIP-Pattern (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-563">msRTCSIP-Pattern (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-564">Este atributo de cadeia de caracteres de valor único contém um padrão usado para números de discagem correspondentes no formato E. 164.</span><span class="sxs-lookup"><span data-stu-id="aee40-564">This single-valued string attribute contains a pattern used for matching dial numbers into E.164 format.</span></span> <span data-ttu-id="aee40-565">Se o número de discagem corresponder a este padrão, a tradução será aplicada ao número discado.</span><span class="sxs-lookup"><span data-stu-id="aee40-565">If the dial number matches this pattern, the translation is applied to the dialed number.</span></span></p></td>
<td><p><span data-ttu-id="aee40-566">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-566">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="aee40-567">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-567">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-568">msRTCSIP-PhoneRouteBL (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-568">msRTCSIP-PhoneRouteBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-569">Este atributo com valores múltiplos contém uma lista de nomes distintos de rotas de telefone (DN).</span><span class="sxs-lookup"><span data-stu-id="aee40-569">This multi-valued attribute contains a list of phone route distinguished names (DN).</span></span> <span data-ttu-id="aee40-570">Este atributo especifica o vínculo inverso com uma ou mais rotas de telefone.</span><span class="sxs-lookup"><span data-stu-id="aee40-570">This attribute specifies the back link to one or more phone routes.</span></span></p>
<p><span data-ttu-id="aee40-571">Vínculo inverso: <strong>link ID 11033</strong></span><span class="sxs-lookup"><span data-stu-id="aee40-571">Back link: <strong>Link ID 11033</strong></span></span></p>
<p><span data-ttu-id="aee40-572">Este atributo corresponde ao vínculo sequencial <strong>msRTCSIP-RouteUsageLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="aee40-572">This attribute corresponds to the forward link <strong>msRTCSIP-RouteUsageLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="aee40-573">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-573">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="aee40-574">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-574">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-575">msRTCSIP-PhoneRouteData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-575">msRTCSIP-PhoneRouteData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-576">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="aee40-576">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="aee40-577">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-577">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-578">msRTCSIP-PhoneRouteName (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-578">msRTCSIP-PhoneRouteName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-579">Este atributo de cadeia de caracteres UNICODE de valor único especifica o nome amigável da rota de telefone, para que possa ser facilmente referenciado pelo administrador.</span><span class="sxs-lookup"><span data-stu-id="aee40-579">This single valued UNICODE string attribute specifies the friendly name of the phone route, so it can easily be referenced by the administrator.</span></span></p></td>
<td><p><span data-ttu-id="aee40-580">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-580">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-581">msRTCSIP-PhoneUsageData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-581">msRTCSIP-PhoneUsageData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-582">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="aee40-582">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="aee40-583">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-583">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="aee40-584">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-584">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-585">msRTCSIP-PolicyContent (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-585">msRTCSIP-PolicyContent (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-586">Este atributo é uma cadeia de caracteres Unicode de valor único.</span><span class="sxs-lookup"><span data-stu-id="aee40-586">This attribute is a single-valued Unicode string.</span></span> <span data-ttu-id="aee40-587">Este atributo de cadeia de caracteres contém a definição de política no formato XML.</span><span class="sxs-lookup"><span data-stu-id="aee40-587">This string attribute contains the policy definition in XML format.</span></span> <span data-ttu-id="aee40-588">A definição de esquema XML é comum entre diferentes tipos de política, apenas as configurações são diferentes para cada tipo de política.</span><span class="sxs-lookup"><span data-stu-id="aee40-588">The XML schema definition is common across different policy types, only the settings are different for each policy type.</span></span></p>
<p><span data-ttu-id="aee40-589">A definição de esquema XML (XSD) é definida da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="aee40-589">The XML schema definition (XSD) is defined as follows:</span></span></p>
<pre><code>&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;
&lt;xs:schema id=&quot;instance&quot; xmlns=&quot;&quot; xmlns:xs=&quot;http://www.w3.org/2001/XMLSchema&quot; xmlns:msdata=&quot;urn:schemas-microsoft-com:xml-msdata&quot;&gt;
  &lt;xs:element name=&quot;instance&quot; msdata:IsDataSet=&quot;true&quot;&gt;
    &lt;xs:complexType&gt;
      &lt;xs:choice maxOccurs=&quot;unbounded&quot;&gt;
        &lt;xs:element name=&quot;property&quot; nillable=&quot;true&quot;&gt;
          &lt;xs:complexType&gt;
            &lt;xs:simpleContent msdata:ColumnName=&quot;property_Text&quot; msdata:Ordinal=&quot;1&quot;&gt;
              &lt;xs:extension base=&quot;xs:string&quot;&gt;
                &lt;xs:attribute name=&quot;name&quot; type=&quot;xs:string&quot; /&gt;
              &lt;/xs:extension&gt;
            &lt;/xs:simpleContent&gt;
          &lt;/xs:complexType&gt;
        &lt;/xs:element&gt;
      &lt;/xs:choice&gt;
    &lt;/xs:complexType&gt;
  &lt;/xs:element&gt;
&lt;/xs:schema&gt;</code></pre></td>
<td><p><span data-ttu-id="aee40-590">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-590">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="aee40-591">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-591">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-592">msRTCSIP-PolicyData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-592">msRTCSIP-PolicyData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-593">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="aee40-593">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="aee40-594">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-594">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="aee40-595">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-595">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-596">msRTCSIP-PolicyType (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-596">msRTCSIP-PolicyType (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-597">Este atributo de cadeia de caracteres Unicode de valor único contém o tipo de política.</span><span class="sxs-lookup"><span data-stu-id="aee40-597">This single-valued Unicode string attribute contains the policy type.</span></span> <span data-ttu-id="aee40-598">Os tipos de política válidos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="aee40-598">Valid policy types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="aee40-599">Atenda</span><span class="sxs-lookup"><span data-stu-id="aee40-599">meeting</span></span></p></li>
<li><p><span data-ttu-id="aee40-600">telefonia</span><span class="sxs-lookup"><span data-stu-id="aee40-600">telephony</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="aee40-601">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-601">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="aee40-602">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-602">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-603">msRTCSIP-PoolAddress</span><span class="sxs-lookup"><span data-stu-id="aee40-603">msRTCSIP-PoolAddress</span></span></p></td>
<td><p><span data-ttu-id="aee40-604">Este atributo especifica um link de volta para o pool ao qual um computador pertence.</span><span class="sxs-lookup"><span data-stu-id="aee40-604">This attribute specifies a link back to the pool to which a computer belongs.</span></span> <span data-ttu-id="aee40-605">Esse atributo é definido independentemente se o computador está executando a edição Standard ou Enterprise Edition do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aee40-605">This attribute is set regardless of whether the computer is running the Standard Edition or the Enterprise Edition of Lync Server.</span></span> <span data-ttu-id="aee40-606">Este atributo está marcado para replicação de catálogo global.</span><span class="sxs-lookup"><span data-stu-id="aee40-606">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="aee40-607">O valor válido é o nome de domínio do pool.</span><span class="sxs-lookup"><span data-stu-id="aee40-607">The valid value is the domain name of the pool.</span></span></p>
<p><span data-ttu-id="aee40-608">Link encaminhar: <strong>link ID 11022</strong></span><span class="sxs-lookup"><span data-stu-id="aee40-608">Forward link: <strong>Link ID 11022</strong></span></span></p>
<p><span data-ttu-id="aee40-609">O vínculo inverso correspondente a este atributo de vínculo sequencial é <strong>msRTCSIP-FrontEndServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="aee40-609">The corresponding back link to this forward link attribute is <strong>msRTCSIP-FrontEndServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="aee40-610">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="aee40-610">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-611">msRTCSIP-PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="aee40-611">msRTCSIP-PoolAddresses</span></span></p></td>
<td><p><span data-ttu-id="aee40-612">Este é um atributo com valores múltiplos que contém uma lista de nomes diferenciados (DN) de pools com os quais a fábrica MCU está associada.</span><span class="sxs-lookup"><span data-stu-id="aee40-612">This is a multi-valued attribute that contains a list of the distinguished names (DN) of pools with which the MCU factory is associated.</span></span></p>
<p><span data-ttu-id="aee40-613">Vínculo inverso: <strong>link ID 11025</strong></span><span class="sxs-lookup"><span data-stu-id="aee40-613">Back link: <strong>Link ID 11025</strong></span></span></p>
<p><span data-ttu-id="aee40-614">O vínculo sequencial correspondente a este vínculo inverso é <strong>msRTCSIP-MCUFactoryPath</strong>.</span><span class="sxs-lookup"><span data-stu-id="aee40-614">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryPath</strong>.</span></span></p></td>
<td><p><span data-ttu-id="aee40-615">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-615">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-616">msRTCSIP-PoolData</span><span class="sxs-lookup"><span data-stu-id="aee40-616">msRTCSIP-PoolData</span></span></p></td>
<td><p><span data-ttu-id="aee40-617">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="aee40-617">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="aee40-618">Novo no Live Communications Server 2005 com SP1.</span><span class="sxs-lookup"><span data-stu-id="aee40-618">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-619">msRTCSIP-PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="aee40-619">msRTCSIP-PoolDisplayName</span></span></p></td>
<td><p><span data-ttu-id="aee40-620">Este atributo especifica um nome arbitrário para um pool que é exibido pelo console de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="aee40-620">This attribute specifies an arbitrary name for a pool that is displayed by the management console.</span></span> <span data-ttu-id="aee40-621">Esse nome pode ser alterado pelo administrador.</span><span class="sxs-lookup"><span data-stu-id="aee40-621">This name can be changed by the administrator.</span></span></p>
<p><span data-ttu-id="aee40-622">O valor válido é uma cadeia de caracteres que representa o nome de um pool.</span><span class="sxs-lookup"><span data-stu-id="aee40-622">The valid value is a string representing the name of a pool.</span></span></p></td>
<td><p><span data-ttu-id="aee40-623">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="aee40-623">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-624">msRTCSIP-PoolDomainFQDN</span><span class="sxs-lookup"><span data-stu-id="aee40-624">msRTCSIP-PoolDomainFQDN</span></span></p></td>
<td><p><span data-ttu-id="aee40-625">Este atributo é um valor de cadeia de caracteres de valor único.</span><span class="sxs-lookup"><span data-stu-id="aee40-625">This attribute is a single-valued string value.</span></span> <span data-ttu-id="aee40-626">O valor desse atributo, quando presente, representa o FQDN do domínio do pool se o administrador quiser criar um pool de front-ends com um FQDN que não esteja em conformidade com a estrutura de domínio do Active Directory na qual o pool de front-ends é criado (por exemplo, um namespace SIP é desassociado do namespace DNS).</span><span class="sxs-lookup"><span data-stu-id="aee40-626">The value of this attribute, when present, represents the pool’s domain FQDN if the administrator wants to create a Front End pool with an FQDN that does not conform to the Active Directory domain structure in which the Front End pool is created (for example, a SIP namespace disjoined from Domain Name System (DNS) namespace).</span></span></p>
<p><span data-ttu-id="aee40-627">Recomendamos que você mapeie o FQDN do domínio do pool de front-ends para a parte do nome de domínio como o domínio do Active Directory no qual o pool reside.</span><span class="sxs-lookup"><span data-stu-id="aee40-627">We recommend that you map the Front End pool domain FQDN to the domain name portion as the Active Directory domain in which the pool resides.</span></span> <span data-ttu-id="aee40-628">Portanto, quando nenhum valor estiver presente nesse atributo, o FQDN do pool de front-ends será o padrão para a estrutura de nome de domínio do Active Directory, conforme indicado pelo atributo <strong>dNSHostName</strong> .</span><span class="sxs-lookup"><span data-stu-id="aee40-628">Therefore, when no value is present in this attribute, the Front End pool FQDN will default to the Active Directory domain name structure, as denoted by the <strong>dnsHostName</strong> attribute.</span></span></p></td>
<td><p><span data-ttu-id="aee40-629">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-629">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-630">msRTCSIP-PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="aee40-630">msRTCSIP-PoolFunctionality</span></span></p></td>
<td><p><span data-ttu-id="aee40-631">Uma lista de vários valores dos nomes de domínio de todos os servidores do Lync Server, Enterprise Edition associados a um pool.</span><span class="sxs-lookup"><span data-stu-id="aee40-631">A multi-valued list of the domain names of all Lync Server, Enterprise Edition servers associated with a pool.</span></span> <span data-ttu-id="aee40-632">Este atributo do tipo Integer define se o pool é capaz de mensagens instantâneas (IM) e presença e reuniões.</span><span class="sxs-lookup"><span data-stu-id="aee40-632">This attribute of type integer defines whether the pool is capable of instant messaging (IM) and presence, and meetings.</span></span></p>
<p><span data-ttu-id="aee40-633">Os tipos de valor válidos possíveis são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="aee40-633">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="aee40-634">Indefinido: serviço de mensagens instantâneas e presença (Live Communications Server 2005 e 2003)</span><span class="sxs-lookup"><span data-stu-id="aee40-634">Undefined: IM and Presence Service (Live Communications Server 2005 and 2003)</span></span></p></li>
<li><p><span data-ttu-id="aee40-635">1: serviço de mensagens instantâneas e presença (Lync Server)</span><span class="sxs-lookup"><span data-stu-id="aee40-635">1: IM and Presence Service (Lync Server)</span></span></p></li>
<li><p><span data-ttu-id="aee40-636">2: mensagens instantâneas e serviços de presença e de reunião (Lync Server)</span><span class="sxs-lookup"><span data-stu-id="aee40-636">2: IM and Presence and Meeting Service (Lync Server)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="aee40-637">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-637">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-638">msRTCSIP-Pooltype</span><span class="sxs-lookup"><span data-stu-id="aee40-638">msRTCSIP-PoolType</span></span></p></td>
<td><p><span data-ttu-id="aee40-639">Este atributo especifica se um pool de servidores está executando o Standard Edition Server ou o servidor Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="aee40-639">This attribute specifies whether a server pool is running Standard Edition server or Enterprise Edition server.</span></span> <span data-ttu-id="aee40-640">Este atributo é um valor de máscara de bits do tipo inteiro.</span><span class="sxs-lookup"><span data-stu-id="aee40-640">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="aee40-641">Cada opção é representada por um bit.</span><span class="sxs-lookup"><span data-stu-id="aee40-641">Each option is represented by a bit.</span></span></p>
<p><span data-ttu-id="aee40-642">Os valores válidos (e as posições de bit associadas) são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="aee40-642">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="aee40-643">1: servidor Standard Edition, hospeda usuários (posição de bit 0)</span><span class="sxs-lookup"><span data-stu-id="aee40-643">1: Standard Edition server, hosts users (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="aee40-644">2: servidor Enterprise Edition, hospeda usuários (posição de bit 1)</span><span class="sxs-lookup"><span data-stu-id="aee40-644">2: Enterprise Edition server, hosts users (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="aee40-645">4: servidor Standard Edition, hospeda aplicativos (posição de bit 2)</span><span class="sxs-lookup"><span data-stu-id="aee40-645">4: Standard Edition server, hosts applications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="aee40-646">8: servidor Enterprise Edition, hospeda aplicativos (posição de bit 3)</span><span class="sxs-lookup"><span data-stu-id="aee40-646">8: Enterprise Edition server, hosts applications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="aee40-647">Como o Lync Server não dá suporte a pools que hospedam apenas aplicativos, os únicos valores válidos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="aee40-647">Because Lync Server does not support pools that host only applications, the only valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="aee40-648">5: servidor Standard Edition, hospeda usuários e aplicativos (posições de bit 0 e 2)</span><span class="sxs-lookup"><span data-stu-id="aee40-648">5: Standard Edition server, hosts users and applications (bit positions 0 and 2)</span></span></p></li>
<li><p><span data-ttu-id="aee40-649">10: servidor Enterprise Edition, hospeda usuários e aplicativos (posições de bit 1 e 3)</span><span class="sxs-lookup"><span data-stu-id="aee40-649">10: Enterprise Edition server, hosts users and applications (bit positions 1 and 3)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="aee40-650">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="aee40-650">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-651">msRTCSIP-PoolVersion</span><span class="sxs-lookup"><span data-stu-id="aee40-651">msRTCSIP-PoolVersion</span></span></p></td>
<td><p><span data-ttu-id="aee40-652">Este atributo define a versão do pool.</span><span class="sxs-lookup"><span data-stu-id="aee40-652">This attribute defines the pool version.</span></span> <span data-ttu-id="aee40-653">É um tipo inteiro que é incrementado com cada lançamento de produto principal.</span><span class="sxs-lookup"><span data-stu-id="aee40-653">It is an integer type that is incremented with each major product release.</span></span></p>
<p><span data-ttu-id="aee40-654">Os tipos de valor válidos possíveis são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="aee40-654">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="aee40-655">0: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="aee40-655">0: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="aee40-656">1: Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="aee40-656">1: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="aee40-657">2: Live Communications Server 2005 com SP1</span><span class="sxs-lookup"><span data-stu-id="aee40-657">2: Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="aee40-658">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="aee40-658">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="aee40-659">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="aee40-659">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="aee40-660">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="aee40-660">5: Lync Server 2010</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="aee40-661">Live Communications Server 2005 com SP1.</span><span class="sxs-lookup"><span data-stu-id="aee40-661">Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-662">msRTCSIP-PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="aee40-662">msRTCSIP-PresenceFlags</span></span></p></td>
<td><p><span data-ttu-id="aee40-663">Este atributo contém opções e sinalizadores que definem configurações de presença.</span><span class="sxs-lookup"><span data-stu-id="aee40-663">This attribute contains options and flags that define presence settings.</span></span></p></td>
<td><p><span data-ttu-id="aee40-664">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="aee40-664">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-665">msRTCSIP-PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="aee40-665">msRTCSIP-PresencePolicy</span></span></p></td>
<td><p><span data-ttu-id="aee40-666">Este atributo contém o DN de um objeto de política de presença.</span><span class="sxs-lookup"><span data-stu-id="aee40-666">This attribute contains the DN for a presence policy object.</span></span></p></td>
<td><p><span data-ttu-id="aee40-667">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="aee40-667">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-668">msRTCSIP-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="aee40-668">msRTCSIP-PrimaryHomeServer</span></span></p></td>
<td><p><span data-ttu-id="aee40-669">Este atributo habilita um usuário ou contato para mensagens SIP.</span><span class="sxs-lookup"><span data-stu-id="aee40-669">This attribute enables a user or contact for SIP messaging.</span></span> <span data-ttu-id="aee40-670">Ela é adicionada à classe Contact porque na topologia de floresta central, os objetos de contato, não os objetos de usuário, estão habilitados para SIP.</span><span class="sxs-lookup"><span data-stu-id="aee40-670">It is added to the contact class because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="aee40-671">O valor válido é o DN do servidor Standard Edition ou pool de front-ends Enterprise Edition onde um usuário está hospedado.</span><span class="sxs-lookup"><span data-stu-id="aee40-671">The valid value is the DN of the Standard Edition server or Enterprise Edition Front End pool where a user is homed.</span></span></p></td>
<td><p><span data-ttu-id="aee40-672">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="aee40-672">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-673">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="aee40-673">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="aee40-674">Este atributo contém o endereço SIP de um determinado usuário.</span><span class="sxs-lookup"><span data-stu-id="aee40-674">This attribute contains the SIP address of a given user.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-675">msRTCSIP-privado</span><span class="sxs-lookup"><span data-stu-id="aee40-675">msRTCSIP-PrivateLine</span></span></p></td>
<td><p><span data-ttu-id="aee40-676">Este atributo contém a ID do dispositivo de linha privada.</span><span class="sxs-lookup"><span data-stu-id="aee40-676">This attribute contains the device ID of the private line device.</span></span></p></td>
<td><p><span data-ttu-id="aee40-677">Novo no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-677">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-678">msRTCSIP-roteável</span><span class="sxs-lookup"><span data-stu-id="aee40-678">msRTCSIP-Routable</span></span></p></td>
<td><p><span data-ttu-id="aee40-679">Este atributo é um atributo booliano usado para determinar se o Lync Server está autorizado a encaminhar para esse serviço usando seu endereço GRUU.</span><span class="sxs-lookup"><span data-stu-id="aee40-679">This attribute is a Boolean attribute used to determine whether Lync Server is authorized to route to this service using its GRUU address.</span></span> <span data-ttu-id="aee40-680">Se esse valor for definido como <strong>true</strong>, o Lync Server estará autorizado a encaminhar para esse serviço.</span><span class="sxs-lookup"><span data-stu-id="aee40-680">If this value is set to <strong>TRUE</strong>, Lync Server is authorized to route to this service.</span></span> <span data-ttu-id="aee40-681">Se esse valor for definido como <strong>false</strong>, o Lync Server não está autorizado a encaminhar para esse serviço.</span><span class="sxs-lookup"><span data-stu-id="aee40-681">If this value is set to <strong>FALSE</strong>, Lync Server is not authorized to route to this service.</span></span></p></td>
<td><p><span data-ttu-id="aee40-682">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-682">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-683">msRTCSIP-RouteUsageAttribute (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-683">msRTCSIP-RouteUsageAttribute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-684">Este atributo de cadeia de caracteres UNICODE de valor único define um atributo que qualifica o uso de uma rota de telefone.</span><span class="sxs-lookup"><span data-stu-id="aee40-684">This single-valued UNICODE string attribute defines an attribute that qualifies the usage for a phone route.</span></span> <span data-ttu-id="aee40-685">A seleção de uma rota de telefone é determinada com base em dois elementos: o atributo de uso atribuído à rota de telefone e os atributos de uso de política permitidos do chamador.</span><span class="sxs-lookup"><span data-stu-id="aee40-685">Selection of a phone route is determined based on two elements: the usage attribute assigned to the phone route and the caller’s allowed policy usage attributes.</span></span> <span data-ttu-id="aee40-686">A primeira rota de telefone com um atributo de uso que corresponda ao uso permitido pelo chamador está selecionada.</span><span class="sxs-lookup"><span data-stu-id="aee40-686">The first phone route with a usage attribute that matches the caller’s allowed usage is selected.</span></span></p></td>
<td><p><span data-ttu-id="aee40-687">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-687">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="aee40-688">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-688">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-689">msRTCSIP-RouteUsageLinks (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-689">msRTCSIP-RouteUsageLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-690">Este atributo de nome diferenciado (DN) com valores múltiplos contém uma lista de nomes diferenciados de uso de rota.</span><span class="sxs-lookup"><span data-stu-id="aee40-690">This multi-valued distinguished name (DN) attribute contains a list of route usage distinguished names.</span></span></p>
<p><span data-ttu-id="aee40-691">Link encaminhar: <strong>link ID 11032</strong></span><span class="sxs-lookup"><span data-stu-id="aee40-691">Forward link: <strong>Link ID 11032</strong></span></span></p>
<p><span data-ttu-id="aee40-692">Este atributo é um link de encaminhamento para o vínculo inverso correspondente <strong>msRTCSIP-PhoneRouteBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="aee40-692">This attribute is a forward link to the corresponding back link <strong>msRTCSIP-PhoneRouteBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="aee40-693">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-693">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-694">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="aee40-694">msRTCSIP-RoutingPoolDN</span></span></p></td>
<td><p><span data-ttu-id="aee40-695">Este atributo contém o DN que aponta para o pool que todo o tráfego SIP endereçado a essa MCU ou serviço confiável deve passar.</span><span class="sxs-lookup"><span data-stu-id="aee40-695">This attribute contains the DN that points to the pool that all SIP traffic addressed to this MCU or Trusted Service must go through.</span></span></p></td>
<td><p><span data-ttu-id="aee40-696">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="aee40-696">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-697">msRTCSIP-RuleName (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-697">msRTCSIP-RuleName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-698">Este atributo de cadeia de caracteres UNICODE de valor único especifica o nome amigável da regra de normalização, para que possa ser facilmente referenciado por um administrador.</span><span class="sxs-lookup"><span data-stu-id="aee40-698">This single-valued UNICODE string attribute specifies the friendly name of the normalization rule, so it can easily be referenced by an administrator.</span></span></p></td>
<td><p><span data-ttu-id="aee40-699">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-699">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="aee40-700">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-700">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-701">msRTCSIP-SchemaVersion</span><span class="sxs-lookup"><span data-stu-id="aee40-701">msRTCSIP-SchemaVersion</span></span></p></td>
<td><p><span data-ttu-id="aee40-702">Este atributo representa a versão do esquema atualmente implantada na organização.</span><span class="sxs-lookup"><span data-stu-id="aee40-702">This attribute represents the schema version currently deployed in the organization.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-703">msRTCSIP-SearchMaxRequests (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-703">msRTCSIP-SearchMaxRequests (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-704">Este atributo limita o número de resultados de pesquisa a serem retornados de uma pesquisa de diretório quando um usuário procura um contato usando o Communicator.</span><span class="sxs-lookup"><span data-stu-id="aee40-704">This attribute limits the number of search results to be returned from a directory search when a user searches for a contact using Communicator.</span></span> <span data-ttu-id="aee40-705">Este atributo substituirá o valor fornecido pelo cliente.</span><span class="sxs-lookup"><span data-stu-id="aee40-705">This attribute will override the value provided by the client.</span></span></p></td>
<td><p><span data-ttu-id="aee40-706">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-706">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-707">msRTCSIP-SearchMaxResults (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-707">msRTCSIP-SearchMaxResults (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-708">Esse atributo limita o número de solicitações de pesquisa retornadas.</span><span class="sxs-lookup"><span data-stu-id="aee40-708">This attribute limits the number of search requests returned.</span></span></p></td>
<td><p><span data-ttu-id="aee40-709">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-709">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-710">msRTCSIP-ServerBL</span><span class="sxs-lookup"><span data-stu-id="aee40-710">msRTCSIP-ServerBL</span></span></p></td>
<td><p><span data-ttu-id="aee40-711">Esse atributo com valores múltiplos é um vínculo inverso que contém uma lista de nomes diferenciados (DN).</span><span class="sxs-lookup"><span data-stu-id="aee40-711">This multi-valued attribute is a back link that contains a list of distinguished names (DN).</span></span> <span data-ttu-id="aee40-712">Esse DNs aponta para um objeto pool ou <strong>TrustedService</strong> .</span><span class="sxs-lookup"><span data-stu-id="aee40-712">These DNs point to a pool or <strong>TrustedService</strong> object.</span></span></p>
<p><span data-ttu-id="aee40-713">Este atributo corresponde ao vínculo sequencial <strong>msRTCSIP-TrustedServiceLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="aee40-713">This attribute corresponds to the forward link <strong>msRTCSIP-TrustedServiceLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="aee40-714">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-714">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-715">msRTCSIP-Serverrestauração</span><span class="sxs-lookup"><span data-stu-id="aee40-715">msRTCSIP-ServerData</span></span></p></td>
<td><p><span data-ttu-id="aee40-716">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="aee40-716">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-717">msRTCSIP-ServerReferenceBL (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-717">msRTCSIP-ServerReferenceBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-718">Este atributo com valores múltiplos contém uma lista de nomes distintos.</span><span class="sxs-lookup"><span data-stu-id="aee40-718">This multi-valued attribute contains a list of distinguished names.</span></span> <span data-ttu-id="aee40-719">Esses nomes distintos são links de volta que fazem referência a outros objetos de servidor que podem ser atribuídos a um perfil de local padrão.</span><span class="sxs-lookup"><span data-stu-id="aee40-719">These distinguished names are back links that reference other server objects that can be assigned a default location profile.</span></span></p>
<p><span data-ttu-id="aee40-720">Vínculo inverso: <strong>link ID 11037</strong></span><span class="sxs-lookup"><span data-stu-id="aee40-720">Back link: <strong>Link ID 11037</strong></span></span></p>
<p><span data-ttu-id="aee40-721">O vínculo sequencial correspondente a este vínculo inverso é <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span><span class="sxs-lookup"><span data-stu-id="aee40-721">The corresponding forward link to this back link is <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span></span></p>
<p><span data-ttu-id="aee40-722">Este atributo de vínculo inverso faz referência somente a pools e servidores de mediação.</span><span class="sxs-lookup"><span data-stu-id="aee40-722">This back link attribute references pools and Mediation Servers only.</span></span></p></td>
<td><p><span data-ttu-id="aee40-723">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-723">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="aee40-724">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-724">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-725">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="aee40-725">msRTCSIP-ServerVersion</span></span></p></td>
<td><p><span data-ttu-id="aee40-726">Este atributo define as informações de versão do servidor.</span><span class="sxs-lookup"><span data-stu-id="aee40-726">This attribute defines the version information of the server.</span></span> <span data-ttu-id="aee40-727">Este número de versão se aplica a todas as funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="aee40-727">This version number applies to all server roles.</span></span> <span data-ttu-id="aee40-728">É um número inteiro de monotonously que aumenta com o lançamento de cada produto oficial.</span><span class="sxs-lookup"><span data-stu-id="aee40-728">It is a monotonously increasing integer that increments with each official product release.</span></span></p>
<p><span data-ttu-id="aee40-729">Os valores válidos possíveis são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="aee40-729">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="aee40-730">Indefinido: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="aee40-730">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="aee40-731">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="aee40-731">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="aee40-732">                 Live Communications Server 2005 with SP1</span><span class="sxs-lookup"><span data-stu-id="aee40-732">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="aee40-733">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="aee40-733">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="aee40-734">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="aee40-734">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="aee40-735">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="aee40-735">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="aee40-736">6: Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aee40-736">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="aee40-737">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-737">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-738">msRTCSIP-SourceObjectType</span><span class="sxs-lookup"><span data-stu-id="aee40-738">msRTCSIP-SourceObjectType</span></span></p></td>
<td><p><span data-ttu-id="aee40-739">Este atributo de valor único de tipo inteiro especifica o tipo de objeto ao qual o <strong>msDS-SourceObjectDN</strong> aponta, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="aee40-739">This single-valued attribute of integer type specifies the type of object the <strong>msDS-SourceObjectDN</strong> points to, as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="aee40-740">nulo | 0x00000001: representa um objeto de usuário principal do Windows NT Server de uma floresta diferente</span><span class="sxs-lookup"><span data-stu-id="aee40-740">null | 0x00000001: Represents a Windows NT Server principal user object from a different forest</span></span></p></li>
<li><p><span data-ttu-id="aee40-741">Os atributos a seguir representam um tipo de grupo de uma floresta diferente para expansão de grupo de distribuição:</span><span class="sxs-lookup"><span data-stu-id="aee40-741">The following attributes represent a group type from a different forest for distribution group expansion:</span></span></p>
<ul>
<li><p><span data-ttu-id="aee40-742">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="aee40-742">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="aee40-743">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="aee40-743">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="aee40-744">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="aee40-744">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="aee40-745">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="aee40-745">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="aee40-746">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span><span class="sxs-lookup"><span data-stu-id="aee40-746">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span></span></p></li>
<li><p><span data-ttu-id="aee40-747">0x90000000: representa um objeto de atendedor automático ou de acesso de assinante da mesma floresta ou de uma floresta diferente</span><span class="sxs-lookup"><span data-stu-id="aee40-747">0x90000000: Represents an Auto-Attendant or subscriber access object from the same forest or a different forest</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="aee40-748">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-748">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-749">msRTCSIP-SubscriptionAuthRequired (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-749">msRTCSIP-SubscriptionAuthRequired (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="aee40-750">Novo no Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="aee40-750">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="aee40-751">Obsoleto no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="aee40-751">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-752">msRTCSIP-TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="aee40-752">msRTCSIP-TargetHomeServer</span></span></p></td>
<td><p><span data-ttu-id="aee40-753">Este atributo permite mover um objeto de usuário ou de contato de um pool do Lync Server para outro.</span><span class="sxs-lookup"><span data-stu-id="aee40-753">This attribute enables you to move a user or contact object from one Lync Server pool to another.</span></span> <span data-ttu-id="aee40-754">Esse atributo é adicionado à classe Contact, porque na topologia de floresta central, os objetos de contato, não os objetos de usuário, estão habilitados para SIP.</span><span class="sxs-lookup"><span data-stu-id="aee40-754">This attribute is added to the contact class, because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="aee40-755">O valor válido é o DN do servidor Standard Edition ou pool de front-ends para o qual o usuário deve ser movido.</span><span class="sxs-lookup"><span data-stu-id="aee40-755">The valid value is the DN of the destination Standard Edition server or Front End pool to which a user is to be moved.</span></span></p></td>
<td><p><span data-ttu-id="aee40-756">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="aee40-756">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-757">msRTCSIP-TargetPhoneNumber (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-757">msRTCSIP-TargetPhoneNumber (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-758">Este atributo de cadeia de caracteres de valor único contém um padrão ou intervalo de números de telefone para rotear para os gateways especificados em <strong>msRTCSIP-gateways</strong>.</span><span class="sxs-lookup"><span data-stu-id="aee40-758">This single-valued string attribute contains a phone number pattern or range to route to the specified gateways defined in <strong>msRTCSIP-Gateways</strong>.</span></span></p></td>
<td><p><span data-ttu-id="aee40-759">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-759">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-760">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="aee40-760">msRTCSIP-TargetUserPolicies</span></span></p></td>
<td><p><span data-ttu-id="aee40-761">Este atributo armazena pares nome-valor para políticas de destino para usuários do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aee40-761">This attribute stores name-value pairs for target policies for Lync Server users.</span></span></p></td>
<td><p><span data-ttu-id="aee40-762">Novo no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-762">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-763">msRTCSIP-Tenantid</span><span class="sxs-lookup"><span data-stu-id="aee40-763">msRTCSIP-TenantId</span></span></p></td>
<td><p><span data-ttu-id="aee40-764">Este atributo armazena o identificador exclusivo de um locatário.</span><span class="sxs-lookup"><span data-stu-id="aee40-764">This attribute stores the unique identifier for a tenant.</span></span></p></td>
<td><p><span data-ttu-id="aee40-765">Novo no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-765">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-766">msRTCSIP-Translation (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-766">msRTCSIP-Translation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-767">Este atributo é usado pelo recurso de voz do Lync Server e contém a cadeia de caracteres de conversão a ser aplicada no número discado, se uma correspondência for encontrada.</span><span class="sxs-lookup"><span data-stu-id="aee40-767">This attribute is used by the voice feature of Lync Server and contains the translation string to apply on the dialed number, if a match is found.</span></span></p></td>
<td><p><span data-ttu-id="aee40-768">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-768">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="aee40-769">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-769">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-770">msRTCSIP-TrustedMCUData</span><span class="sxs-lookup"><span data-stu-id="aee40-770">msRTCSIP-TrustedMCUData</span></span></p></td>
<td><p><span data-ttu-id="aee40-771">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="aee40-771">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="aee40-772">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-772">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-773">msRTCSIP-TrustedMCUFQDN</span><span class="sxs-lookup"><span data-stu-id="aee40-773">msRTCSIP-TrustedMCUFQDN</span></span></p></td>
<td><p><span data-ttu-id="aee40-774">Este atributo é um valor String que contém o FQDN do MCU.</span><span class="sxs-lookup"><span data-stu-id="aee40-774">This attribute is a string value that contains the FQDN of the MCU.</span></span> <span data-ttu-id="aee40-775">Este é um atributo de valor único.</span><span class="sxs-lookup"><span data-stu-id="aee40-775">This is a single-valued attribute.</span></span> <span data-ttu-id="aee40-776">O valor válido para cada segmento é 63 caracteres; o valor válido para o FQDN inteiro é de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="aee40-776">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="aee40-777">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-777">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-778">msRTCSIP-TrustedProxyData</span><span class="sxs-lookup"><span data-stu-id="aee40-778">msRTCSIP-TrustedProxyData</span></span></p></td>
<td><p><span data-ttu-id="aee40-779">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="aee40-779">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="aee40-780">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-780">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-781">msRTCSIP-TrustedProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="aee40-781">msRTCSIP-TrustedProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="aee40-782">Este atributo é um valor String que contém o FQDN do servidor de proxy em execução.</span><span class="sxs-lookup"><span data-stu-id="aee40-782">This attribute is a string value that contains the FQDN of the server running Proxy Server.</span></span> <span data-ttu-id="aee40-783">Este atributo tem valor único.</span><span class="sxs-lookup"><span data-stu-id="aee40-783">This attribute is single-valued.</span></span> <span data-ttu-id="aee40-784">O valor válido para cada segmento é 63 caracteres; o valor válido para o FQDN inteiro é de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="aee40-784">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="aee40-785">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-785">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-786">msRTCSIP-TrustedServerData</span><span class="sxs-lookup"><span data-stu-id="aee40-786">msRTCSIP-TrustedServerData</span></span></p></td>
<td><p><span data-ttu-id="aee40-787">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="aee40-787">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-788">msRTCSIP-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="aee40-788">msRTCSIP-TrustedServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="aee40-789">Este atributo é um atributo de valor único que representa o FQDN de um servidor confiável.</span><span class="sxs-lookup"><span data-stu-id="aee40-789">This attribute is a single-valued attribute that represents the FQDN of a trusted server.</span></span></p></td>
<td><p><span data-ttu-id="aee40-790">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="aee40-790">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-791">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="aee40-791">msRTCSIP-TrustedServerVersion</span></span></p></td>
<td><p><span data-ttu-id="aee40-792">Este atributo especifica o número de versão de um servidor na lista de servidores confiáveis.</span><span class="sxs-lookup"><span data-stu-id="aee40-792">This attribute specifies the version number of a server in the trusted server list.</span></span></p>
<p><span data-ttu-id="aee40-793">Os valores válidos possíveis são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="aee40-793">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="aee40-794">NULO: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="aee40-794">NULL: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="aee40-795">2: Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="aee40-795">2: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="aee40-796">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="aee40-796">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="aee40-797">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="aee40-797">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="aee40-798">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="aee40-798">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="aee40-799">6: Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aee40-799">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="aee40-800">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="aee40-800">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-801">msRTCSIP-TrustedServiceFlags</span><span class="sxs-lookup"><span data-stu-id="aee40-801">msRTCSIP-TrustedServiceFlags</span></span></p></td>
<td><p><span data-ttu-id="aee40-802">Este atributo define as opções que são habilitadas para o serviço confiável.</span><span class="sxs-lookup"><span data-stu-id="aee40-802">This attribute defines the options that are enabled for the trusted service.</span></span></p></td>
<td><p><span data-ttu-id="aee40-803">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="aee40-803">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-804">msRTCSIP-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="aee40-804">msRTCSIP-TrustedServiceLinks</span></span></p></td>
<td><p><span data-ttu-id="aee40-805">Este atributo com valores múltiplos contém uma lista de nomes diferenciados (DN) que fazem referência a um objeto de serviço confiável, como um serviço de autenticação de retransmissão de mídia.</span><span class="sxs-lookup"><span data-stu-id="aee40-805">This multi-valued attribute contains a list of distinguished names (DN) that reference a trusted service object, such as a Media Relay Authentication Service.</span></span> <span data-ttu-id="aee40-806">Um serviço de autenticação de retransmissão de mídia (colocado fisicamente no servidor de borda executando o serviço de conferência A/V) deve estar associado a um pool para dar suporte a cenários de áudio para usuários remotos.</span><span class="sxs-lookup"><span data-stu-id="aee40-806">A Media Relay Authentication Service (physically collocated on the Edge Server running the A/V Conferencing service) must be associated with a pool to support audio scenarios for remote users.</span></span></p>
<p><span data-ttu-id="aee40-807">O vínculo inverso correspondente a este atributo de vínculo sequencial é <strong>msRTCSIP-ServerBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="aee40-807">The corresponding back link to this forward link attribute is <strong>msRTCSIP-ServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="aee40-808">UC</span><span class="sxs-lookup"><span data-stu-id="aee40-808">UC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-809">msRTCSIP-TrustedServicePort</span><span class="sxs-lookup"><span data-stu-id="aee40-809">msRTCSIP-TrustedServicePort</span></span></p></td>
<td><p><span data-ttu-id="aee40-810">Este atributo é um número inteiro que define o número da porta usada para se conectar ao serviço GRUU.</span><span class="sxs-lookup"><span data-stu-id="aee40-810">This attribute is an integer that defines the port number used to connect to this GRUU service.</span></span></p></td>
<td><p><span data-ttu-id="aee40-811">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-811">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-812">msRTCSIP-TrustedServiceType</span><span class="sxs-lookup"><span data-stu-id="aee40-812">msRTCSIP-TrustedServiceType</span></span></p></td>
<td><p><span data-ttu-id="aee40-813">Este atributo é um valor String que define o tipo de serviço GRUU que ele representa.</span><span class="sxs-lookup"><span data-stu-id="aee40-813">This attribute is a string value that defines the type of GRUU service it represents.</span></span></p>
<p><span data-ttu-id="aee40-814">Os tipos de serviço válidos do GRUU são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="aee40-814">The valid GRUU service types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="aee40-815">MediationServer</span><span class="sxs-lookup"><span data-stu-id="aee40-815">MediationServer</span></span></p></li>
<li><p><span data-ttu-id="aee40-816">Gateway</span><span class="sxs-lookup"><span data-stu-id="aee40-816">Gateway</span></span></p></li>
<li><p><span data-ttu-id="aee40-817">Serviço de autenticação de retransmissão de mídia (MRAS)</span><span class="sxs-lookup"><span data-stu-id="aee40-817">Media Relay Authentication Service (MRAS)</span></span></p></li>
<li><p><span data-ttu-id="aee40-818">QoSM</span><span class="sxs-lookup"><span data-stu-id="aee40-818">QoSM</span></span></p></li>
<li><p><span data-ttu-id="aee40-819">msRTCSIP-userextension CWA</span><span class="sxs-lookup"><span data-stu-id="aee40-819">msRTCSIP-UserExtension CWA</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="aee40-820">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-820">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-821">msRTCSIP-TrustedWebComponentsServerData</span><span class="sxs-lookup"><span data-stu-id="aee40-821">msRTCSIP-TrustedWebComponentsServerData</span></span></p></td>
<td><p><span data-ttu-id="aee40-822">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="aee40-822">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="aee40-823">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-823">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-824">msRTCSIP-TrustedWebComponentsServerFQDN</span><span class="sxs-lookup"><span data-stu-id="aee40-824">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="aee40-825">Este atributo é um valor String que contém o FQDN do IIS que executa os serviços Web do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aee40-825">This attribute is a string value that contains the FQDN of the IIS running Lync Server Web Services.</span></span> <span data-ttu-id="aee40-826">Este é um atributo de valor único.</span><span class="sxs-lookup"><span data-stu-id="aee40-826">This is a single-valued attribute.</span></span> <span data-ttu-id="aee40-827">O valor válido para cada segmento é 63 caracteres; o valor válido para o FQDN inteiro é de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="aee40-827">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="aee40-828">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-828">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-829">msRTCSIP-UCFlags (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-829">msRTCSIP-UCFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-830">Este atributo define opções de UC diferentes que são habilitadas globalmente para todos os objetos de contato ou usuário.</span><span class="sxs-lookup"><span data-stu-id="aee40-830">This attribute defines different UC options that are enabled globally to all user or contact objects.</span></span> <span data-ttu-id="aee40-831">Este atributo é um valor de máscara de bits de tipo inteiro.</span><span class="sxs-lookup"><span data-stu-id="aee40-831">This attribute is a bit-mask value of integer type.</span></span> <span data-ttu-id="aee40-832">Cada opção é representada pela presença de um bit.</span><span class="sxs-lookup"><span data-stu-id="aee40-832">Each option is represented by the presence of a bit.</span></span></p>
<p><span data-ttu-id="aee40-833">O valor válido possível (e a posição de bit associada) são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="aee40-833">The possible valid value (and associated bit position) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="aee40-834">4: UsePerUserUCPolicy (posição de bit 2)</span><span class="sxs-lookup"><span data-stu-id="aee40-834">4: UsePerUserUCPolicy (bit position 2)</span></span></p></li>
</ul>
<p><span data-ttu-id="aee40-835">Quando esse bit é definido, a política de UC é definida por usuário.</span><span class="sxs-lookup"><span data-stu-id="aee40-835">When this bit is set, the UC policy is defined per user.</span></span></p></td>
<td><p><span data-ttu-id="aee40-836">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-836">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-837">msRTCSIP-UCPolicy (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-837">msRTCSIP-UCPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-838">Este atributo de valor único contém o nome diferenciado (DN) da política de UC que o administrador atribuiu para este usuário.</span><span class="sxs-lookup"><span data-stu-id="aee40-838">This single-valued attribute contains the distinguished name (DN) of the UC policy that the administrator has assigned for this user.</span></span></p></td>
<td><p><span data-ttu-id="aee40-839">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-839">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-840">msRTCSIP-userdomainlist (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-840">msRTCSIP-UserDomainList (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="aee40-841">Este atributo fornece uma lista de todos os domínios em uma floresta que hospedam usuários habilitados para SIP.</span><span class="sxs-lookup"><span data-stu-id="aee40-841">This attribute provides a list of all the domains in a forest that host SIP-enabled users.</span></span> <span data-ttu-id="aee40-842">O padrão é uma lista vazia, indicando que todos os domínios na floresta são habilitados para SIP.</span><span class="sxs-lookup"><span data-stu-id="aee40-842">The default is an empty list, indicating that all domains in the forest are SIP-enabled.</span></span></p>
<p><span data-ttu-id="aee40-843">Os valores válidos são várias cadeias de caracteres que representam os nomes de domínio de domínios individuais.</span><span class="sxs-lookup"><span data-stu-id="aee40-843">Valid values are multiple strings representing the domain names of individual domains.</span></span></p></td>
<td><p><span data-ttu-id="aee40-844">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="aee40-844">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="aee40-845">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-845">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-846">msRTCSIP-userhabilitado</span><span class="sxs-lookup"><span data-stu-id="aee40-846">msRTCSIP-UserEnabled</span></span></p></td>
<td><p><span data-ttu-id="aee40-847">Este atributo determina se o usuário está atualmente habilitado para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aee40-847">This attribute determines whether the user is currently enabled for Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-848">msRTCSIP-userextension</span><span class="sxs-lookup"><span data-stu-id="aee40-848">msRTCSIP-UserExtension</span></span></p></td>
<td><p><span data-ttu-id="aee40-849">Este atributo com valores múltiplos contém uma lista de pares nome-valor no formato de &quot; nome = valor. &quot; Este atributo está marcado para replicação de catálogo global.</span><span class="sxs-lookup"><span data-stu-id="aee40-849">This multi-valued attribute contains a list of name-value pairs in the format of &quot;name=value.&quot; This attribute is marked for global catalog replication.</span></span></p></td>
<td><p><span data-ttu-id="aee40-850">Novo no Live Communications Server 2005 com SP1.</span><span class="sxs-lookup"><span data-stu-id="aee40-850">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-851">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="aee40-851">msRTCSIP-UserLocationProfile</span></span></p></td>
<td><p><span data-ttu-id="aee40-852">Este atributo contém o nome diferenciado (DN) que aponta para um objeto de perfil de local.</span><span class="sxs-lookup"><span data-stu-id="aee40-852">This attribute contains the distinguished name (DN) that points to a location profile object.</span></span></p></td>
<td><p><span data-ttu-id="aee40-853">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="aee40-853">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-854">msRTCSIP-userpolicies</span><span class="sxs-lookup"><span data-stu-id="aee40-854">msRTCSIP-UserPolicies</span></span></p></td>
<td><p><span data-ttu-id="aee40-855">Este atributo armazena pares nome-valor para políticas de usuário.</span><span class="sxs-lookup"><span data-stu-id="aee40-855">This attribute stores name-value pairs for user policies.</span></span></p></td>
<td><p><span data-ttu-id="aee40-856">Novo no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="aee40-856">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-857">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="aee40-857">msRTCSIP-UserPolicy</span></span></p></td>
<td><p><span data-ttu-id="aee40-858">Este é um atributo com valores múltiplos contendo uma lista de nomes distintos com binário (DN_WITH_BINARY) apontando para políticas de usuário global de tipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="aee40-858">This is a multi-valued attribute containing a list of distinguished names with binary (DN_WITH_BINARY) pointing to global user policies of different types.</span></span> <span data-ttu-id="aee40-859">A parte binária indica o tipo de política para o qual a parte DN aponta.</span><span class="sxs-lookup"><span data-stu-id="aee40-859">The binary part indicates the type of policy to which the DN portion points.</span></span></p>
<p><span data-ttu-id="aee40-860">Os valores binários válidos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="aee40-860">The valid binary values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="aee40-861">0x00000001: política de reunião</span><span class="sxs-lookup"><span data-stu-id="aee40-861">0x00000001: Meeting policy</span></span></p></li>
<li><p><span data-ttu-id="aee40-862">0x00000002: política de UC</span><span class="sxs-lookup"><span data-stu-id="aee40-862">0x00000002: UC policy</span></span></p></li>
<li><p><span data-ttu-id="aee40-863">0x00000005: política de presença</span><span class="sxs-lookup"><span data-stu-id="aee40-863">0x00000005: Presence policy</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="aee40-864">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-864">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-865">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="aee40-865">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="aee40-p165">Este é o ID do grupo de roteamento SIP. Os usuários no mesmo grupo irão ser registrados para o mesmo Servidor de Front-end.</span><span class="sxs-lookup"><span data-stu-id="aee40-p165">This is the SIP routing group ID. Users in the same group will register to the same Front End Server.</span></span></p></td>
<td><p><span data-ttu-id="aee40-868">Novo no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aee40-868">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-869">msRTCSIP-WebComponentsData</span><span class="sxs-lookup"><span data-stu-id="aee40-869">msRTCSIP-WebComponentsData</span></span></p></td>
<td><p><span data-ttu-id="aee40-870">Este é um atributo com vários valores.</span><span class="sxs-lookup"><span data-stu-id="aee40-870">This is a multi-valued attribute.</span></span> <span data-ttu-id="aee40-871">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="aee40-871">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="aee40-872">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-872">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-873">msRTCSIP-WebComponentsPoolAddress</span><span class="sxs-lookup"><span data-stu-id="aee40-873">msRTCSIP-WebComponentsPoolAddress</span></span></p></td>
<td><p><span data-ttu-id="aee40-874">Esse atributo de valor único aponta para o pool ou servidor Standard Edition ao qual os componentes Web pertencem.</span><span class="sxs-lookup"><span data-stu-id="aee40-874">This single-valued attribute points to the pool or Standard Edition server to which the web components belong.</span></span></p>
<p><span data-ttu-id="aee40-875">Link encaminhar: <strong>link ID 11028</strong></span><span class="sxs-lookup"><span data-stu-id="aee40-875">Forward link: <strong>Link ID 11028</strong></span></span></p>
<p><span data-ttu-id="aee40-876">O vínculo inverso correspondente a este atributo de vínculo sequencial é <strong>msRTCSIP-WebComponentsServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="aee40-876">The corresponding back link to this forward link attribute is <strong>msRTCSIP-WebComponentsServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="aee40-877">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-877">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-878">msRTCSIP-WebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="aee40-878">msRTCSIP-WebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="aee40-879">Este atributo é uma lista de vários valores de nomes distintos.</span><span class="sxs-lookup"><span data-stu-id="aee40-879">This attribute is a multi-valued list of distinguished names.</span></span> <span data-ttu-id="aee40-880">Este atributo contém uma lista de todos os servidores Web associados a esse pool.</span><span class="sxs-lookup"><span data-stu-id="aee40-880">This attribute contains a list of all Web servers associated with this pool.</span></span></p>
<p><span data-ttu-id="aee40-881">Vínculo inverso: <strong>link ID 11029</strong></span><span class="sxs-lookup"><span data-stu-id="aee40-881">Back link: <strong>Link ID 11029</strong></span></span></p>
<p><span data-ttu-id="aee40-882">O vínculo sequencial correspondente a este vínculo inverso é <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="aee40-882">The corresponding forward link to this back link is <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="aee40-883">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="aee40-883">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-884">msRTCSIP-WMIInstanceId (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="aee40-884">msRTCSIP-WMIInstanceId (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="aee40-885">Novo no Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="aee40-885">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="aee40-886">Obsoleto no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="aee40-886">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-887">OtherIPPhone</span><span class="sxs-lookup"><span data-stu-id="aee40-887">OtherIPPhone</span></span></p></td>
<td><p><span data-ttu-id="aee40-888">Esse atributo existente do Active Directory é usado por telefonia para especificar a lista de endereços TCP/IP alternativos de um telefone.</span><span class="sxs-lookup"><span data-stu-id="aee40-888">This existing Active Directory attribute is used by telephony to specify the list of alternate TCP/IP addresses for a phone.</span></span></p></td>
<td><p><span data-ttu-id="aee40-889">Novo no sistema operacional Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="aee40-889">New in Windows Server 2008 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-890">PhoneOfficeOther</span><span class="sxs-lookup"><span data-stu-id="aee40-890">PhoneOfficeOther</span></span></p></td>
<td><p><span data-ttu-id="aee40-891">Este atributo existente do Active Directory é usado pelos componentes de voz no Lync Server, apenas para objetos de contato, para fins de roteamento de chamadas para o atendedor automático da Unificação de mensagens e os números de acesso do Assinante.</span><span class="sxs-lookup"><span data-stu-id="aee40-891">This existing Active Directory attribute is used by the voice components in Lync Server, for contact objects only, for the purpose of routing calls to the unified messaging auto-attendant and subscriber access numbers.</span></span> <span data-ttu-id="aee40-892">O endereço de encaminhamento de chamadas não condicional é armazenado nesse atributo com valores múltiplos.</span><span class="sxs-lookup"><span data-stu-id="aee40-892">The unconditional call forwarding address is stored in this multi-valued attribute.</span></span> <span data-ttu-id="aee40-893">Essa conta é criada para a finalidade específica do atendedor automático e acesso ao Assinante.</span><span class="sxs-lookup"><span data-stu-id="aee40-893">This account is created for the specific purpose of auto-attendant and subscriber access.</span></span> <span data-ttu-id="aee40-894">Os atributos da conta não devem ser modificados pelos administradores.</span><span class="sxs-lookup"><span data-stu-id="aee40-894">This account’s attributes should not be modified by administrators.</span></span></p></td>
<td><p><span data-ttu-id="aee40-895">Novo no sistema operacional Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="aee40-895">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aee40-896">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="aee40-896">ProxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="aee40-897">Este atributo de múltiplos valores do Active Directory existente é parte do esquema base do Active Directory introduzido no Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="aee40-897">This existing Active Directory multi-valued attribute is part of the base Active Directory schema introduced in Windows 2000.</span></span> <span data-ttu-id="aee40-898">Este atributo contém os vários endereços X400, X500 e SMTP do email do usuário.</span><span class="sxs-lookup"><span data-stu-id="aee40-898">This attribute contains the various X400, X500, and SMTP addresses of the user’s email.</span></span> <span data-ttu-id="aee40-899">No Live Communications Server 2003 e posterior, o URI do SIP do usuário é adicionado a essa lista, usando a &quot; marca SIP: &quot; .</span><span class="sxs-lookup"><span data-stu-id="aee40-899">In Live Communications Server 2003 and later, the user’s SIP URI is added to this list, using the &quot;sip:&quot; tag.</span></span></p>
<p><span data-ttu-id="aee40-900">Os seguintes aplicativos pesquisam o URI do SIP do usuário a partir deste atributo:</span><span class="sxs-lookup"><span data-stu-id="aee40-900">The following applications search the user’s SIP URI from this attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="aee40-901">Cliente de mensagens e colaboração do Microsoft Office Outlook 2003</span><span class="sxs-lookup"><span data-stu-id="aee40-901">Microsoft Office Outlook 2003 messaging and collaboration client</span></span></p></li>
<li><p><span data-ttu-id="aee40-902">Microsoft Office SharePoint Server 2007</span><span class="sxs-lookup"><span data-stu-id="aee40-902">Microsoft Office SharePoint Server 2007</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="aee40-903">Novo no sistema operacional Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="aee40-903">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aee40-904">TelephoneNumber</span><span class="sxs-lookup"><span data-stu-id="aee40-904">TelephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="aee40-905">Este atributo existente do Active Directory contém o número de telefone do usuário.</span><span class="sxs-lookup"><span data-stu-id="aee40-905">This existing Active Directory attribute contains the telephone number for the user.</span></span></p></td>
<td><p><span data-ttu-id="aee40-906">Novo no sistema operacional Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="aee40-906">New in Windows 2000 operating system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

