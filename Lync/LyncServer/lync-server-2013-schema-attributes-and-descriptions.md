---
title: 'Lync Server 2013: atributos e descrições de esquema'
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
ms.openlocfilehash: a1c8259312e3ba4e939bd784e189f5aae495605d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182664"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="18f6a-102">Atributos e descrições de esquema no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18f6a-102">Schema attributes and descriptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18f6a-103">_**Última modificação do tópico:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="18f6a-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="18f6a-104">Esta seção descreve todos os atributos de esquema usados pelo Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="18f6a-104">This section describes all the schema attributes used by Lync Server 2013.</span></span> <span data-ttu-id="18f6a-105">Para as classes associadas a atributos, confira [atributos de esquema por classe no Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="18f6a-105">For the classes associated with attributes, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span> <span data-ttu-id="18f6a-106">Para obter uma lista de classes e atributos que são novos no Lync Server 2013, consulte [Schema Changes in Lync server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="18f6a-106">For a list of classes and attributes that are new in Lync Server 2013, see [Schema changes in Lync Server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span></span>

<span data-ttu-id="18f6a-107">Os atributos que são pares vinculados são especificados como links de encaminhamento ou links de volta.</span><span class="sxs-lookup"><span data-stu-id="18f6a-107">Attributes that are linked pairs are specified as forward links or back links.</span></span> <span data-ttu-id="18f6a-108">Um atributo que se refere a outro objeto é um vínculo progressivo; o atributo do outro objeto que se refere novamente ao primeiro objeto é um vínculo inverso.</span><span class="sxs-lookup"><span data-stu-id="18f6a-108">An attribute that refers to another object is a forward link; the attribute of the other object that refers back to the first object is a back link.</span></span> <span data-ttu-id="18f6a-109">Os links de encaminhamento são atualizáveis, enquanto os links de volta são somente leitura.</span><span class="sxs-lookup"><span data-stu-id="18f6a-109">Forward links are updatable, while back links are read-only.</span></span>

<span data-ttu-id="18f6a-110">Alguns atributos têm um valor de máscara de bits.</span><span class="sxs-lookup"><span data-stu-id="18f6a-110">Some attributes have a bit-mask value.</span></span> <span data-ttu-id="18f6a-111">Para esses atributos, cada configuração é representada por um bit e o valor decimal exibido representa a posição de bit.</span><span class="sxs-lookup"><span data-stu-id="18f6a-111">For these attributes, each setting is represented by a bit, and the displayed decimal value represents the bit position.</span></span> <span data-ttu-id="18f6a-112">As posições de bit começam com bit 0.</span><span class="sxs-lookup"><span data-stu-id="18f6a-112">Bit positions start with bit 0.</span></span> <span data-ttu-id="18f6a-113">Por exemplo, 1 (binário) é bit 0 definido e 10000 (binário) é um bit 4 definido.</span><span class="sxs-lookup"><span data-stu-id="18f6a-113">For example, 1 (binary) is bit 0 set and 10000 (binary) is bit 4 set.</span></span> <span data-ttu-id="18f6a-114">Cada bit representa uma propriedade.</span><span class="sxs-lookup"><span data-stu-id="18f6a-114">Each bit represents a property.</span></span> <span data-ttu-id="18f6a-115">Estes são alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="18f6a-115">The following are some examples:</span></span>

  - <span data-ttu-id="18f6a-116">10000 (binário) tem um valor decimal de 16 (ou seja, o bit 4 é definido).</span><span class="sxs-lookup"><span data-stu-id="18f6a-116">10000 (binary) has a decimal value of 16 (that is, bit 4 is set).</span></span>

  - <span data-ttu-id="18f6a-117">100 milhões (binário) tem um valor decimal de 256 (ou seja, o bit 8 é definido).</span><span class="sxs-lookup"><span data-stu-id="18f6a-117">100000000 (binary) has a decimal value of 256 (that is, bit 8 is set).</span></span>

  - <span data-ttu-id="18f6a-118">1100 (binário) tem um valor decimal de 12 (ou seja, os bits 2 e 3 são definidos; as propriedades representadas por ambos os bits estão habilitadas).</span><span class="sxs-lookup"><span data-stu-id="18f6a-118">1100 (binary) has a decimal value of 12 (that is, bits 2 and 3 are set; properties represented by both bits are enabled).</span></span>

  - <span data-ttu-id="18f6a-119">1111000001 (binário) tem um valor decimal de 961 (ou seja, os bits 0, 6, 7, 8 e 9 são definidos; as propriedades de cada um desses bits estão habilitadas).</span><span class="sxs-lookup"><span data-stu-id="18f6a-119">1111000001 (binary) has a decimal value of 961 (that is, bits 0, 6, 7, 8, and 9 are set; properties for each of these bits are enabled).</span></span>

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a><span data-ttu-id="18f6a-120">Atributos de esquema para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18f6a-120">Schema Attributes for Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="18f6a-121">Atributo</span><span class="sxs-lookup"><span data-stu-id="18f6a-121">Attribute</span></span></th>
<th><span data-ttu-id="18f6a-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="18f6a-122">Description</span></span></th>
<th><span data-ttu-id="18f6a-123">Comentários</span><span class="sxs-lookup"><span data-stu-id="18f6a-123">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-124">dnsHostName</span><span class="sxs-lookup"><span data-stu-id="18f6a-124">dnsHostName</span></span></p></td>
<td><p><span data-ttu-id="18f6a-125">Um atributo existente nos serviços de domínio do Active Directory que agora está associado às classes <strong>msRTCSIP-pool</strong> e <strong>msRTCSIP-MonitoringServer</strong> .</span><span class="sxs-lookup"><span data-stu-id="18f6a-125">An existing attribute in Active Directory Domain Services that is now associated with the <strong>msRTCSIP-Pool</strong> and <strong>msRTCSIP-MonitoringServer</strong> classes.</span></span> <span data-ttu-id="18f6a-126">Este atributo especifica o FQDN (nome de domínio totalmente qualificado) de um pool ou de um servidor de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="18f6a-126">This attribute specifies the fully qualified domain name (FQDN) of a pool or Monitoring Server.</span></span></p>
<p><span data-ttu-id="18f6a-127">Um valor válido para cada segmento é 63 caracteres; um valor válido para o FQDN inteiro é de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="18f6a-127">A valid value for each segment is 63 characters; a valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-128">Novo no Microsoft Office Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="18f6a-128">New in Microsoft Office Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-129">msDS-SourceObjectDN</span><span class="sxs-lookup"><span data-stu-id="18f6a-129">msDS-SourceObjectDN</span></span></p></td>
<td><p><span data-ttu-id="18f6a-130">Este atributo contém a representação de cadeia de caracteres do DN (nome diferenciado) do objeto em outra floresta que corresponde a esse objeto.</span><span class="sxs-lookup"><span data-stu-id="18f6a-130">This attribute contains the string representation of the distinguished name (DN) of the object in another forest that corresponds to this object.</span></span> <span data-ttu-id="18f6a-131">Este atributo é usado para expansão de grupo de distribuição e presença automática.</span><span class="sxs-lookup"><span data-stu-id="18f6a-131">This attribute is used for distribution group expansion and auto attendance.</span></span> <span data-ttu-id="18f6a-132">Esse atributo é definido no esquema padrão do Active Directory para o Windows Server 2003 R2.</span><span class="sxs-lookup"><span data-stu-id="18f6a-132">This attribute is defined in the default Active Directory schema for Windows Server 2003 R2.</span></span></p>
<p><span data-ttu-id="18f6a-133">Para evitar a necessidade de uma atualização do AD DS para o Windows Server 2003 R2, a preparação do esquema do Active Directory estende o esquema do Windows Server 2003 com essa definição de atributo.</span><span class="sxs-lookup"><span data-stu-id="18f6a-133">To avoid requiring an upgrade of AD DS to Windows Server 2003 R2, Active Directory schema preparation extends the Windows Server 2003 schema with this attribute definition.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-134">Novo no Microsoft Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-134">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-135">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="18f6a-135">msExchUCVoiceMailSettings</span></span></p></td>
<td><p><span data-ttu-id="18f6a-136">Este atributo com valores múltiplos contém configurações de caixa postal.</span><span class="sxs-lookup"><span data-stu-id="18f6a-136">This multi-valued attribute holds voice mail settings.</span></span> <span data-ttu-id="18f6a-137">Este atributo é compartilhado com a Unificação de mensagens (UM) do Exchange.</span><span class="sxs-lookup"><span data-stu-id="18f6a-137">This attribute is shared with Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="18f6a-138">Novo no Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-138">New in Microsoft Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-139">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="18f6a-139">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="18f6a-140">Este atributo de vários valores mantém identificadores para manter políticas aplicadas ao usuário.</span><span class="sxs-lookup"><span data-stu-id="18f6a-140">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="18f6a-141">Políticas de retenção preservam os itens das caixas de correio para o usuário pela duração da retenção.</span><span class="sxs-lookup"><span data-stu-id="18f6a-141">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="18f6a-142">Este atributo é compartilhado com o Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="18f6a-142">This attribute is shared with Exchange 2013.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-143">Novo no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="18f6a-143">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-144">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="18f6a-144">msRTCSIP-AcpInfo</span></span></p></td>
<td><p><span data-ttu-id="18f6a-145">Este atributo armazena informações do provedor de audioconferência para um usuário.</span><span class="sxs-lookup"><span data-stu-id="18f6a-145">This attribute stores audio conferencing provider information for a user.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-146">Novo no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-146">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-147">msRTCSIP-ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="18f6a-147">msRTCSIP-ApplicationDestination</span></span></p></td>
<td><p><span data-ttu-id="18f6a-148">Este atributo aponta para a entrada de serviço confiável para o contato de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="18f6a-148">This attribute points to the trusted service entry for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-149">Novo no Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="18f6a-149">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-150">msRTCSIP-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="18f6a-150">msRTCSIP-ApplicationList</span></span></p></td>
<td><p><span data-ttu-id="18f6a-151">Este atributo contém uma lista de aplicativos hospedados no servidor de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="18f6a-151">This attribute contains a list of hosted applications on the application server.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-152">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="18f6a-152">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-153">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="18f6a-153">msRTCSIP-ApplicationOptions</span></span></p></td>
<td><p><span data-ttu-id="18f6a-154">Este atributo especifica as opções para o contato de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="18f6a-154">This attribute specifies the options for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-155">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="18f6a-155">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-156">msRTCSIP-ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="18f6a-156">msRTCSIP-ApplicationPrimaryLanguage</span></span></p></td>
<td><p><span data-ttu-id="18f6a-157">Este atributo contém o idioma principal para o contato de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="18f6a-157">This attribute contains the primary language for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-158">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="18f6a-158">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-159">msRTCSIP-ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="18f6a-159">msRTCSIP-ApplicationSecondaryLanguages</span></span></p></td>
<td><p><span data-ttu-id="18f6a-160">Este atributo de vários valores contém os idiomas secundários para o contato de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="18f6a-160">This multiple value attribute contains the secondary languages for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-161">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="18f6a-161">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-162">msRTCSIP-ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="18f6a-162">msRTCSIP-ApplicationServerBL</span></span></p></td>
<td><p><span data-ttu-id="18f6a-163">Este atributo contém uma lista de servidores de aplicativos que pertencem a esse pool.</span><span class="sxs-lookup"><span data-stu-id="18f6a-163">This attribute contains a list of application servers that belong to this pool.</span></span> <span data-ttu-id="18f6a-164">O vínculo sequencial correspondente a este atributo de vínculo inverso é <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span><span class="sxs-lookup"><span data-stu-id="18f6a-164">The corresponding forward link to this back link attribute is <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-165">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="18f6a-165">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-166">msRTCSIP-ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="18f6a-166">msRTCSIP-ApplicationServerPoolLink</span></span></p></td>
<td><p><span data-ttu-id="18f6a-167">Este atributo aponta para o pool ao qual pertence este servidor de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="18f6a-167">This attribute points to the pool to which this application server belongs.</span></span> <span data-ttu-id="18f6a-168">Este é o link de encaminhamento.</span><span class="sxs-lookup"><span data-stu-id="18f6a-168">This is the forward link.</span></span> <span data-ttu-id="18f6a-169">O vínculo inverso correspondente é <strong>msRTCSIP-ApplicationServerBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="18f6a-169">The corresponding backward link is <strong>msRTCSIP-ApplicationServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-170">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="18f6a-170">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-171">msRTCSIP-ArchiveDefault (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-171">msRTCSIP-ArchiveDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="18f6a-172">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="18f6a-172">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="18f6a-173">Obsoleto no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-173">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-174">msRTCSIP-ArchiveDefaultFlags (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-174">msRTCSIP-ArchiveDefaultFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-175">Este atributo especifica o padrão global dentro do limite da floresta para o arquivamento de todas as comunicações do usuário.</span><span class="sxs-lookup"><span data-stu-id="18f6a-175">This attribute specifies the global default within the forest boundary for archiving all user communications.</span></span> <span data-ttu-id="18f6a-176">Isso é imposto pela camada do agente de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="18f6a-176">This is enforced by the archiving agent layer.</span></span> <span data-ttu-id="18f6a-177">O intervalo de valores para esse atributo é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="18f6a-177">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="18f6a-178"><strong>True</strong>: arquivar todos os usuários</span><span class="sxs-lookup"><span data-stu-id="18f6a-178"><strong>TRUE</strong>: Archive all users</span></span></p></li>
<li><p><span data-ttu-id="18f6a-179"><strong>False</strong>: Não arquivar todos os usuários</span><span class="sxs-lookup"><span data-stu-id="18f6a-179"><strong>FALSE</strong>: Do not archive all users</span></span></p></li>
</ul>
<p><span data-ttu-id="18f6a-180">Este atributo controla globalmente, dentro do limite da floresta, como as comunicações do usuário em uma rede interna são arquivadas.</span><span class="sxs-lookup"><span data-stu-id="18f6a-180">This attribute globally controls, within the forest boundary, how user communications within an internal network are archived.</span></span></p>
<p><span data-ttu-id="18f6a-181"><strong>Comportamento do Live Communications Server 2005 (agora desativado)</strong></span><span class="sxs-lookup"><span data-stu-id="18f6a-181"><strong>Live Communications Server 2005 behavior (now retired)</strong></span></span></p>
<p><span data-ttu-id="18f6a-182">O intervalo de valores para esse atributo é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="18f6a-182">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="18f6a-183">0: arquivar o corpo da mensagem [bit 0]</span><span class="sxs-lookup"><span data-stu-id="18f6a-183">0: Archive the message body [bit 0]</span></span></p></li>
<li><p><span data-ttu-id="18f6a-184">1: não arquiva o corpo da mensagem [bit 0]</span><span class="sxs-lookup"><span data-stu-id="18f6a-184">1: Do not archive the message body [bit 0]</span></span></p></li>
</ul>
<p><span data-ttu-id="18f6a-185"><strong>Comportamento do Office Communications Server 2007</strong></span><span class="sxs-lookup"><span data-stu-id="18f6a-185"><strong>Office Communications Server 2007 behavior</strong></span></span></p>
<p><span data-ttu-id="18f6a-186">O intervalo de valores para esse atributo é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="18f6a-186">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="18f6a-187">0: ArchiveFederationDefaultWithoutBody (desativado)</span><span class="sxs-lookup"><span data-stu-id="18f6a-187">0: ArchiveFederationDefaultWithoutBody (retired)</span></span></p></li>
<li><p><span data-ttu-id="18f6a-188">1-2: ArchiveInternalCommunications</span><span class="sxs-lookup"><span data-stu-id="18f6a-188">1-2: ArchiveInternalCommunications</span></span></p></li>
<li><p><span data-ttu-id="18f6a-189">3-4: ArchiveFederatedCommunications</span><span class="sxs-lookup"><span data-stu-id="18f6a-189">3-4: ArchiveFederatedCommunications</span></span></p></li>
<li><p><span data-ttu-id="18f6a-190">5: RecordPresenceRegistrations</span><span class="sxs-lookup"><span data-stu-id="18f6a-190">5: RecordPresenceRegistrations</span></span></p></li>
<li><p><span data-ttu-id="18f6a-191">6: RecordIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="18f6a-191">6: RecordIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="18f6a-192">7: RecordGroupIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="18f6a-192">7: RecordGroupIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="18f6a-193">8: RecordFileTransferInstances</span><span class="sxs-lookup"><span data-stu-id="18f6a-193">8: RecordFileTransferInstances</span></span></p></li>
<li><p><span data-ttu-id="18f6a-194">9: RecordAudioCallDetails</span><span class="sxs-lookup"><span data-stu-id="18f6a-194">9: RecordAudioCallDetails</span></span></p></li>
<li><p><span data-ttu-id="18f6a-195">10: RecordVideoCallDetails</span><span class="sxs-lookup"><span data-stu-id="18f6a-195">10: RecordVideoCallDetails</span></span></p></li>
<li><p><span data-ttu-id="18f6a-196">11: RecordRemoteAssistanceCallDetails</span><span class="sxs-lookup"><span data-stu-id="18f6a-196">11: RecordRemoteAssistanceCallDetails</span></span></p></li>
<li><p><span data-ttu-id="18f6a-197">12: RecordApplicationSharingDetails</span><span class="sxs-lookup"><span data-stu-id="18f6a-197">12: RecordApplicationSharingDetails</span></span></p></li>
<li><p><span data-ttu-id="18f6a-198">13: RecordMeetingInstantiations</span><span class="sxs-lookup"><span data-stu-id="18f6a-198">13: RecordMeetingInstantiations</span></span></p></li>
<li><p><span data-ttu-id="18f6a-199">14: RecordMeetingJoins</span><span class="sxs-lookup"><span data-stu-id="18f6a-199">14: RecordMeetingJoins</span></span></p></li>
<li><p><span data-ttu-id="18f6a-200">15: RecordDataJoins</span><span class="sxs-lookup"><span data-stu-id="18f6a-200">15: RecordDataJoins</span></span></p></li>
<li><p><span data-ttu-id="18f6a-201">16: RecordAVJoins</span><span class="sxs-lookup"><span data-stu-id="18f6a-201">16: RecordAVJoins</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="18f6a-202">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="18f6a-202">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="18f6a-203">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-203">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-204">msRTCSIP-ArchiveFederationDefault (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-204">msRTCSIP-ArchiveFederationDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="18f6a-205">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="18f6a-205">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="18f6a-206">Obsoleto no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-206">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-207">msRTCSIP-ArchiveFederationDefaultFlags (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-207">msRTCSIP-ArchiveFederationDefaultFlags (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="18f6a-208">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="18f6a-208">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="18f6a-209">Obsoleto no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-209">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-210">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="18f6a-210">msRTCSIP-ArchivingEnabled</span></span></p></td>
<td><p><span data-ttu-id="18f6a-211">Este atributo é um inteiro usado como um campo de bits para controlar se as comunicações de um único usuário devem ser arquivadas.</span><span class="sxs-lookup"><span data-stu-id="18f6a-211">This attribute is an integer used as a bit field to control whether a single user’s communications are to be archived.</span></span> <span data-ttu-id="18f6a-212">Esse controle é imposto pela camada do agente de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="18f6a-212">This control is enforced by the archiving agent layer.</span></span> <span data-ttu-id="18f6a-213">Ele está marcado para replicação do catálogo global.</span><span class="sxs-lookup"><span data-stu-id="18f6a-213">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="18f6a-214">O escopo desse atributo é específico para um único usuário ou contato.</span><span class="sxs-lookup"><span data-stu-id="18f6a-214">The scope of this attribute is specific to a single user or contact.</span></span> <span data-ttu-id="18f6a-215">Os valores válidos (e posições de bit associadas) no Lync Server são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="18f6a-215">The valid values (and associated bit positions) in Lync Server are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="18f6a-216">0: Não arquivar (sem conjunto de bits)</span><span class="sxs-lookup"><span data-stu-id="18f6a-216">0: Do not archive (no bit set)</span></span></p></li>
<li><p><span data-ttu-id="18f6a-217">1: desativado (posição de bit 0)</span><span class="sxs-lookup"><span data-stu-id="18f6a-217">1: Retired (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="18f6a-218">2: desativado (posição de bit 1)</span><span class="sxs-lookup"><span data-stu-id="18f6a-218">2: Retired (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="18f6a-219">4: Arquivar comunicações internas (posição de bit 2)</span><span class="sxs-lookup"><span data-stu-id="18f6a-219">4: Archive internal communications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="18f6a-220">8: Arquivar comunicações federadas (posição de bit 3)</span><span class="sxs-lookup"><span data-stu-id="18f6a-220">8: Archive federated communications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="18f6a-221">Os valores válidos anteriormente no Live Communications Server 2005 são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="18f6a-221">Previously valid values in Live Communications Server 2005 are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="18f6a-222">0: Use o valor padrão definido pelo <strong>msRTCSIP-ArchiveDefault</strong> e <strong>msRTCSIP-ArchiveFederation</strong> nesta ordem de precedência:</span><span class="sxs-lookup"><span data-stu-id="18f6a-222">0:Use the default value defined by <strong>msRTCSIP-ArchiveDefault</strong> and <strong>msRTCSIP-ArchiveFederation</strong> in this order of precedence:</span></span></p>
<ul>
<li><p><span data-ttu-id="18f6a-223">1: arquivar</span><span class="sxs-lookup"><span data-stu-id="18f6a-223">1: Archive</span></span></p></li>
<li><p><span data-ttu-id="18f6a-224">2: Não arquivar</span><span class="sxs-lookup"><span data-stu-id="18f6a-224">2: Do not archive</span></span></p></li>
<li><p><span data-ttu-id="18f6a-225">3: arquivar sem o corpo da mensagem</span><span class="sxs-lookup"><span data-stu-id="18f6a-225">3: Archive without the message body</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="18f6a-226">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="18f6a-226">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-227">msRTCSIP-ArchivingServerData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-227">msRTCSIP-ArchivingServerData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-228">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="18f6a-228">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-229">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-229">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-230">msRTCSIP-ArchivingServerVersion (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-230">msRTCSIP-ArchivingServerVersion (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-231">Este atributo define a versão do serviço de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="18f6a-231">This attribute defines the version of the Archiving service.</span></span> <span data-ttu-id="18f6a-232">Este atributo é um tipo inteiro de monotonously que aumenta com cada versão oficial do produto.</span><span class="sxs-lookup"><span data-stu-id="18f6a-232">This attribute is a monotonously increasing integer type that increments with each official product release.</span></span> <span data-ttu-id="18f6a-233">Os valores válidos possíveis são:</span><span class="sxs-lookup"><span data-stu-id="18f6a-233">The possible valid values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="18f6a-234">Indefinido: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="18f6a-234">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="18f6a-235">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="18f6a-235">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="18f6a-236">                 Live Communications Server 2005 with SP1</span><span class="sxs-lookup"><span data-stu-id="18f6a-236">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="18f6a-237">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="18f6a-237">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="18f6a-238">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="18f6a-238">4: Office Communications Server 2007 R2</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="18f6a-239">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-239">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="18f6a-240">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-240">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-241">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="18f6a-241">msRTCSIP-BackEndServer</span></span></p></td>
<td><p><span data-ttu-id="18f6a-242">Este atributo especifica o FQDN do servidor back-end do pool.</span><span class="sxs-lookup"><span data-stu-id="18f6a-242">This attribute specifies the FQDN of the Back End Server of the pool.</span></span> <span data-ttu-id="18f6a-243">Como só pode haver um único servidor back-end por pool, este é um atributo de valor único.</span><span class="sxs-lookup"><span data-stu-id="18f6a-243">Because there can only be a single Back End Server per pool, this is a single-valued attribute.</span></span></p>
<p><span data-ttu-id="18f6a-244">O valor válido para cada segmento é 63 caracteres; o valor válido para o FQDN inteiro é de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="18f6a-244">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-245">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="18f6a-245">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-246">msRTCSIP-ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="18f6a-246">msRTCSIP-ConferenceDirectoryHomePool</span></span></p></td>
<td><p><span data-ttu-id="18f6a-247">Este atributo contém o identificador do pool que hospeda o diretório de conferências.</span><span class="sxs-lookup"><span data-stu-id="18f6a-247">This attribute contains the identifier of the pool that hosts the conference directory.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-248">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="18f6a-248">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-249">msRTCSIP-ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="18f6a-249">msRTCSIP-ConferenceDirectoryId</span></span></p></td>
<td><p><span data-ttu-id="18f6a-250">Este atributo contém o identificador de um diretório de conferência.</span><span class="sxs-lookup"><span data-stu-id="18f6a-250">This attribute contains the identifier of a conference directory.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-251">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="18f6a-251">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-252">msRTCSIP-ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="18f6a-252">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p></td>
<td><p><span data-ttu-id="18f6a-253">Este atributo contém o identificador do pool ao qual o diretório de conferência está sendo movido.</span><span class="sxs-lookup"><span data-stu-id="18f6a-253">This attribute contains the identifier of the pool to which the conference directory is being moved.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-254">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="18f6a-254">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-255">msRTCSIP-padrão</span><span class="sxs-lookup"><span data-stu-id="18f6a-255">msRTCSIP-Default</span></span></p></td>
<td><p><span data-ttu-id="18f6a-256">Este atributo booliano define se o uso do telefone é um uso padrão.</span><span class="sxs-lookup"><span data-stu-id="18f6a-256">This Boolean attribute defines whether the phone usage is a default usage.</span></span> <span data-ttu-id="18f6a-257">Se esse atributo for definido como <strong>true</strong>, o uso de telefone será um uso padrão e não poderá ser excluído pelo administrador.</span><span class="sxs-lookup"><span data-stu-id="18f6a-257">If this attribute is set to <strong>TRUE</strong>, the phone usage is a default usage and cannot be deleted by the administrator.</span></span> <span data-ttu-id="18f6a-258">Se esse atributo for definido como <strong>false</strong>, o uso poderá ser excluído.</span><span class="sxs-lookup"><span data-stu-id="18f6a-258">If this attribute is set to <strong>FALSE</strong>, the usage can be deleted.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-259">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-259">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-260">msRTCSIP-DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="18f6a-260">msRTCSIP-DefaultCWAExternalURL</span></span></p></td>
<td><p><span data-ttu-id="18f6a-261">Este atributo identifica a URL do Communicator Web Access para usuários que estão fora da organização.</span><span class="sxs-lookup"><span data-stu-id="18f6a-261">This attribute identifies the Communicator Web Access URL for users who are outside the organization.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-262">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="18f6a-262">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-263">msRTCSIP-DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="18f6a-263">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
<td><p><span data-ttu-id="18f6a-264">Este atributo identifica a URL do Communicator Web Access para usuários que estão dentro da organização.</span><span class="sxs-lookup"><span data-stu-id="18f6a-264">This attribute identifies the Communicator Web Access URL for users who are inside the organization.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-265">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="18f6a-265">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-266">msRTCSIP-DefaultLocationProfileLink (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-266">msRTCSIP-DefaultLocationProfileLink (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-267">Este atributo de valor único contém o nome diferenciado (DN) de um objeto de classe de perfil de local atribuído a ele.</span><span class="sxs-lookup"><span data-stu-id="18f6a-267">This single-valued attribute contains the distinguished name (DN) of a location profile class object assigned to it.</span></span></p>
<p><span data-ttu-id="18f6a-268">Link encaminhar: <strong>link ID 11036</strong></span><span class="sxs-lookup"><span data-stu-id="18f6a-268">Forward link: <strong>Link ID 11036</strong></span></span></p>
<p><span data-ttu-id="18f6a-269">O vínculo inverso correspondente é <strong>msRTCSIP-ServerReferenceBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="18f6a-269">The corresponding backward link is <strong>msRTCSIP-ServerReferenceBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-270">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-270">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-271">msRTCSIP-DefaultPolicy (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-271">msRTCSIP-DefaultPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-272">Este atributo booliano especifica se a política é uma política padrão.</span><span class="sxs-lookup"><span data-stu-id="18f6a-272">This Boolean attribute specifies whether the policy is a default policy.</span></span> <span data-ttu-id="18f6a-273">A política é uma política padrão quando definida como <strong>true</strong>.</span><span class="sxs-lookup"><span data-stu-id="18f6a-273">The policy is a default policy when set to <strong>TRUE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-274">Novo no Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="18f6a-274">New in Office Communications Server 2007</span></span></p>
<p><span data-ttu-id="18f6a-275">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-275">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-276">msRTCSIP-DefaultRouteToEdgeProxy (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-276">msRTCSIP-DefaultRouteToEdgeProxy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-277">Este atributo especifica o FQDN do servidor de borda que executa o serviço de borda de acesso, se ele puder ser acessado diretamente ou do balanceador de carga de hardware para um pool de servidores que executam o serviço de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="18f6a-277">This attribute specifies the FQDN of either the Edge Server running the Access Edge service, if it can be accessed directly, or of the hardware load balancer for a pool of servers running Access Edge service.</span></span> <span data-ttu-id="18f6a-278">Se os servidores que executam o serviço de borda de acesso podem ser acessados apenas por um ou mais directors, este atributo especifica o FQDN e, opcionalmente, o número da porta do diretor ou do balanceador de carga de hardware que atendem a um pool de diretores.</span><span class="sxs-lookup"><span data-stu-id="18f6a-278">If the servers running Access Edge service can be accessed only through one or more Directors, this attribute specifies the FQDN and, optionally, the port number of the Director or of the hardware load balancer serving a Director pool.</span></span></p>
<p><span data-ttu-id="18f6a-279">O valor válido para cada segmento é 63 caracteres; o valor válido para o FQDN inteiro é de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="18f6a-279">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-280">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="18f6a-280">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="18f6a-281">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-281">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-282">msRTCSIP-DefaultRouteToEdgeProxyPort (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-282">msRTCSIP-DefaultRouteToEdgeProxyPort (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-283">Este atributo representa o número da porta que deve ser usada para se conectar ao servidor que executa o serviço de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="18f6a-283">This attribute represents the port number that should be used to connect to the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="18f6a-284">O valor válido é um valor inteiro que especifica a porta a ser usada.</span><span class="sxs-lookup"><span data-stu-id="18f6a-284">The valid value is an integer value specifying the port to be used.</span></span> <span data-ttu-id="18f6a-285">O valor padrão é 5061.</span><span class="sxs-lookup"><span data-stu-id="18f6a-285">The default value is 5061.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-286">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="18f6a-286">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="18f6a-287">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-287">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-288">msRTCSIP-DefPresenceSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-288">msRTCSIP-DefPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-289">Este atributo representa o período de tempo limite da assinatura de presença padrão.</span><span class="sxs-lookup"><span data-stu-id="18f6a-289">This attribute represents the default presence subscription time-out period.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-290">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-290">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-291">msRTCSIP-DefRegistrationTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-291">msRTCSIP-DefRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-292">Este atributo representa a janela do tempo limite de registro padrão.</span><span class="sxs-lookup"><span data-stu-id="18f6a-292">This attribute represents the default registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-293">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-293">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-294">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-294">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-295">Este atributo representa a janela de tempo limite da assinatura de dados de roaming padrão.</span><span class="sxs-lookup"><span data-stu-id="18f6a-295">This attribute represents the default roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-296">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-296">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-297">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="18f6a-297">msRTCSIP-DeploymentLocator</span></span></p></td>
<td><p><span data-ttu-id="18f6a-298">Este atributo é usado em uma topologia de domínio dividido e contém um FQDN (nome de domínio totalmente qualificado).</span><span class="sxs-lookup"><span data-stu-id="18f6a-298">This attribute is used in a split domain topology and contains a fully qualified domain name (FQDN).</span></span></p></td>
<td><p><span data-ttu-id="18f6a-299">Novo no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-299">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-300">msRTCSIP-Description (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-300">msRTCSIP-Description (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-301">Este atributo de cadeia de caracteres UNICODE de valor único contém uma descrição amigável da rota de telefone ou da regra de normalização.</span><span class="sxs-lookup"><span data-stu-id="18f6a-301">This single-valued UNICODE string attribute contains a friendly description of this phone route or normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-302">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-302">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="18f6a-303">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-303">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-304">msRTCSIP-DomainData</span><span class="sxs-lookup"><span data-stu-id="18f6a-304">msRTCSIP-DomainData</span></span></p></td>
<td><p><span data-ttu-id="18f6a-305">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="18f6a-305">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-306">msRTCSIP-DomainName</span><span class="sxs-lookup"><span data-stu-id="18f6a-306">msRTCSIP-DomainName</span></span></p></td>
<td><p><span data-ttu-id="18f6a-307">Este atributo representa um domínio configurado para o registrador.</span><span class="sxs-lookup"><span data-stu-id="18f6a-307">This attribute represents a domain configured for the Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-308">msRTCSIP-EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="18f6a-308">msRTCSIP-EdgeProxyData</span></span></p></td>
<td><p><span data-ttu-id="18f6a-309">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="18f6a-309">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-310">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="18f6a-310">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-311">msRTCSIP-EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="18f6a-311">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="18f6a-312">Este atributo especifica o FQDN do servidor que executa o serviço de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="18f6a-312">This attribute specifies the FQDN of the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="18f6a-313">O valor válido para cada segmento é 63 caracteres; o valor válido para o FQDN inteiro é de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="18f6a-313">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-314">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="18f6a-314">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-315">msRTCSIP-EnableBestEffortNotify (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-315">msRTCSIP-EnableBestEffortNotify (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-316">Este atributo controla se um servidor gera uma solicitação de notificação de melhor esforço (benotificar), em vez de uma solicitação de notificação, em resposta a uma solicitação de assinatura de um cliente.</span><span class="sxs-lookup"><span data-stu-id="18f6a-316">This attribute controls whether a server generates a Best Effort NOTIFY (BENOTIFY) request, instead of a NOTIFY request, in response to a SUBSCRIBE request from a client.</span></span> <span data-ttu-id="18f6a-317">BENOTIFY é uma extensão de aumento de desempenho para o handshake de notificação de assinatura onde o servidor gera solicitações de notificação de atendimento, em vez de solicitações de notificação regulares.</span><span class="sxs-lookup"><span data-stu-id="18f6a-317">BENOTIFY is a performance-enhancing extension to the subscribe notification handshake where the server generates BENOTIFY requests, instead of regular NOTIFY requests.</span></span> <span data-ttu-id="18f6a-318">O benefício de desempenho é que uma solicitação de notificação de atendimento não requer uma resposta de 200 OK do cliente à medida que a solicitação de notificação faz.</span><span class="sxs-lookup"><span data-stu-id="18f6a-318">The performance benefit is that a BENOTIFY request does not require a 200 OK response from the client as the NOTIFY request does.</span></span></p>
<p><span data-ttu-id="18f6a-319">Os valores válidos são <strong>true</strong> ou <strong>false</strong>.</span><span class="sxs-lookup"><span data-stu-id="18f6a-319">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="18f6a-320">O Live Communications Server 2003 não dá suporte a solicitações de notificação de notificações.</span><span class="sxs-lookup"><span data-stu-id="18f6a-320">Live Communications Server 2003 does not support BENOTIFY requests.</span></span> <span data-ttu-id="18f6a-321">Para interoperar com aplicativos de servidor escritos com a API de servidor do Live Communications Server 2003 em execução no Live Communications Server 2005 e servidores de terceiros, as solicitações de notificações podem ser desabilitadas definindo seu valor como <STRONG>false</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="18f6a-321">To interoperate with server applications written with the Live Communications Server 2003 server API running on Live Communications Server 2005 and third-party servers, BENOTIFY requests can be disabled by setting its value to <STRONG>FALSE</STRONG>.</span></span> <span data-ttu-id="18f6a-322">O benotification não faz parte do processo de padronização SIP do IETF (Internet Engineering Task Force).</span><span class="sxs-lookup"><span data-stu-id="18f6a-322">BENOTIFY is not currently part of the IETF (Internet Engineering Task Force) SIP standardization process.</span></span>


</div></td>
<td><p><span data-ttu-id="18f6a-323">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="18f6a-323">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="18f6a-324">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-324">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-325">msRTCSIP-EnableFederation (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-325">msRTCSIP-EnableFederation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-326">Este atributo é uma opção global que os administradores de ti usam para configurar se os usuários têm permissão para se comunicar com os usuários de outras organizações.</span><span class="sxs-lookup"><span data-stu-id="18f6a-326">This attribute is a global switch that IT administrators use to configure whether users are allowed to communicate with users from other organizations.</span></span> <span data-ttu-id="18f6a-327">Permite que um administrador substitua o atributo <strong>FederationEnabled</strong> de um usuário individual.</span><span class="sxs-lookup"><span data-stu-id="18f6a-327">It enables an administrator to overwrite an individual user’s <strong>FederationEnabled</strong> attribute.</span></span> <span data-ttu-id="18f6a-328">Esse atributo pode ser útil para ajudar a proteger a rede interna contra ataques da Internet que podem ser causados por worms, vírus ou ataques direcionados à empresa.</span><span class="sxs-lookup"><span data-stu-id="18f6a-328">This attribute can be useful to help protect the internal network from Internet attacks that may be caused by worms, viruses, or targeted attacks on the company.</span></span></p>
<p><span data-ttu-id="18f6a-329">Os valores válidos (e as posições de bit associadas) são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="18f6a-329">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="18f6a-330">1: habilitado para conectividade de IM pública (posição de bit 0)</span><span class="sxs-lookup"><span data-stu-id="18f6a-330">1: Enabled for public IM connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="18f6a-331">2: reservado (posição de bit 1)</span><span class="sxs-lookup"><span data-stu-id="18f6a-331">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="18f6a-332">4: reservado (posição de bit 2)</span><span class="sxs-lookup"><span data-stu-id="18f6a-332">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="18f6a-333">8: reservado (posição de bit 3)</span><span class="sxs-lookup"><span data-stu-id="18f6a-333">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="18f6a-334">16: controle de chamada remota habilitado [telefonia] (posição de bit 4)</span><span class="sxs-lookup"><span data-stu-id="18f6a-334">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="18f6a-335">64: AllowOrganizeMeetingWithAnonymousParticipants is (permitir que os usuários convidem usuários anônimos para reuniões (posição de bit 6)</span><span class="sxs-lookup"><span data-stu-id="18f6a-335">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="18f6a-336">128: UCEnabled (habilitar usuários para comunicações unificadas) (posição de bit 7)</span><span class="sxs-lookup"><span data-stu-id="18f6a-336">128: UCEnabled (enable users for unified communications) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="18f6a-337">256: EnabledForEnhancedPresence (habilitar usuário para conectividade de IM pública) (posição de bit 8)</span><span class="sxs-lookup"><span data-stu-id="18f6a-337">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="18f6a-338">512: RemoteCallControlDualMode (posição de bit 9)</span><span class="sxs-lookup"><span data-stu-id="18f6a-338">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="18f6a-339">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="18f6a-339">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="18f6a-340">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-340">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-341">msRTCSIP-EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="18f6a-341">msRTCSIP-EnterpriseServices</span></span></p></td>
<td><p><span data-ttu-id="18f6a-342">Este atributo indica se os serviços corporativos são carregados em um determinado servidor.</span><span class="sxs-lookup"><span data-stu-id="18f6a-342">This attribute indicates whether the Enterprise Services are loaded on the given server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-343">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="18f6a-343">msRTCSIP-ExtensionData</span></span></p></td>
<td><p><span data-ttu-id="18f6a-344">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="18f6a-344">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-345">msRTCSIP-ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="18f6a-345">msRTCSIP-ExternalAccessCode</span></span></p></td>
<td><p><span data-ttu-id="18f6a-346">Este atributo contém o código de discagem para acesso externo.</span><span class="sxs-lookup"><span data-stu-id="18f6a-346">This attribute contains the dial code for external access.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-347">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="18f6a-347">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-348">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="18f6a-348">msRTCSIP-FederationEnabled</span></span></p></td>
<td><p><span data-ttu-id="18f6a-349">Este atributo controla se um único usuário está habilitado para Federação.</span><span class="sxs-lookup"><span data-stu-id="18f6a-349">This attribute controls whether a single user is enabled for federation.</span></span> <span data-ttu-id="18f6a-350">Ela é imposta pela camada de serviços corporativos.</span><span class="sxs-lookup"><span data-stu-id="18f6a-350">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="18f6a-351">Ele está marcado para replicação do catálogo global.</span><span class="sxs-lookup"><span data-stu-id="18f6a-351">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="18f6a-352">Os valores válidos são <strong>true</strong> ou <strong>false</strong>.</span><span class="sxs-lookup"><span data-stu-id="18f6a-352">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-353">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="18f6a-353">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-354">msRTCSIP-FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="18f6a-354">msRTCSIP-FrontEndServers</span></span></p></td>
<td><p><span data-ttu-id="18f6a-355">Este atributo é uma lista de vários valores dos nomes de domínio de todos os servidores Enterprise Edition associados a um pool.</span><span class="sxs-lookup"><span data-stu-id="18f6a-355">This attribute is a multi-valued list of the domain names of all Enterprise Edition servers associated with a pool.</span></span></p>
<p><span data-ttu-id="18f6a-356">Vínculo inverso: <strong>link ID 11023</strong></span><span class="sxs-lookup"><span data-stu-id="18f6a-356">Back link: <strong>Link ID 11023</strong></span></span></p>
<p><span data-ttu-id="18f6a-357">O vínculo sequencial correspondente a este vínculo inverso é <strong>msRTCSIP-PoolAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="18f6a-357">The corresponding forward link to this back link is <strong>msRTCSIP-PoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-358">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="18f6a-358">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-359">msRTCSIP-gateways (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-359">msRTCSIP-Gateways (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-360">Este atributo de cadeia de caracteres de valores múltiplos contém uma lista de gateways e portas (por gateway).</span><span class="sxs-lookup"><span data-stu-id="18f6a-360">This multi-valued string attribute contains a list of gateways and ports (per gateway).</span></span></p></td>
<td><p><span data-ttu-id="18f6a-361">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-361">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-362">msRTCSIP-GlobalSettingsData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-362">msRTCSIP-GlobalSettingsData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-363">Este atributo armazena nomes: pares de valores.</span><span class="sxs-lookup"><span data-stu-id="18f6a-363">This attribute stores name:value pairs.</span></span> <span data-ttu-id="18f6a-364">O par nome já definido: valor é para a configuração <strong>permitir sondagem de presença</strong> .</span><span class="sxs-lookup"><span data-stu-id="18f6a-364">The already-defined name:value pair is for the <strong>allow polling for presence</strong> setting.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-365">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-365">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-366">msRTCSIP-Groupingid</span><span class="sxs-lookup"><span data-stu-id="18f6a-366">msRTCSIP-GroupingID</span></span></p></td>
<td><p><span data-ttu-id="18f6a-367">Este atributo é um identificador exclusivo de um grupo usado para agrupar entradas do catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="18f6a-367">This attribute is a unique identifier of a group that is used to group address book entries.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-368">Novo no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-368">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-369">msRTCSIP-HomeServer (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-369">msRTCSIP-HomeServer (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="18f6a-370">Novo no Live Communications Server 2003 (não usado).</span><span class="sxs-lookup"><span data-stu-id="18f6a-370">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="18f6a-371">Obsoleto no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="18f6a-371">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-372">msRTCSIP-HomeServerString (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-372">msRTCSIP-HomeServerString (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="18f6a-373">Novo no Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="18f6a-373">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="18f6a-374">Obsoleto no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="18f6a-374">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-375">msRTCSIP-HomeUsers (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-375">msRTCSIP-HomeUsers (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="18f6a-376">Novo no Live Communications Server 2003 (não usado).</span><span class="sxs-lookup"><span data-stu-id="18f6a-376">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="18f6a-377">Obsoleto no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="18f6a-377">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-378">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="18f6a-378">msRTCSIP-InternetAccessEnabled</span></span></p></td>
<td><p><span data-ttu-id="18f6a-379">Este atributo controla se um único usuário está habilitado para o acesso de usuário externo.</span><span class="sxs-lookup"><span data-stu-id="18f6a-379">This attribute controls whether a single user is enabled for outside user access.</span></span> <span data-ttu-id="18f6a-380">Ela é imposta pela camada de serviços corporativos.</span><span class="sxs-lookup"><span data-stu-id="18f6a-380">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="18f6a-381">Ele está marcado para replicação do catálogo global.</span><span class="sxs-lookup"><span data-stu-id="18f6a-381">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="18f6a-382">Os valores válidos são <strong>true</strong> ou <strong>false</strong>.</span><span class="sxs-lookup"><span data-stu-id="18f6a-382">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-383">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="18f6a-383">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-384">msRTCSIP-IsMaster (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-384">msRTCSIP-IsMaster (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="18f6a-385">Novo no Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="18f6a-385">New in Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="18f6a-386">Obsoleto no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="18f6a-386">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-387">Linha msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="18f6a-387">msRTCSIP-Line</span></span></p></td>
<td><p><span data-ttu-id="18f6a-388">Este atributo de valor único contém a ID do dispositivo (o URI do SIP ou o URI de TEL do telefone que os controles de usuário) usados pelo Lync para telefonia.</span><span class="sxs-lookup"><span data-stu-id="18f6a-388">This single-valued attribute contains the device ID (either the SIP URI or the TEL URI of the phone the user controls) used by Lync for telephony.</span></span> <span data-ttu-id="18f6a-389">Esse atributo é marcado para replicação de catálogo global e é indexado.</span><span class="sxs-lookup"><span data-stu-id="18f6a-389">This attribute is marked for Global Catalog replication and is indexed.</span></span> <span data-ttu-id="18f6a-390">Se um usuário estiver habilitado para o Enterprise Voice, este atributo armazenará a versão normalizada E. 164 do número de telefone do usuário.</span><span class="sxs-lookup"><span data-stu-id="18f6a-390">If a user is enabled for Enterprise Voice, this attribute stores the E.164 normalized version of the user’s phone number.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-391">Novo no Microsoft Office Live Communications Server 2005 com SP1</span><span class="sxs-lookup"><span data-stu-id="18f6a-391">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-392">msRTCSIP-LineServer</span><span class="sxs-lookup"><span data-stu-id="18f6a-392">msRTCSIP-LineServer</span></span></p></td>
<td><p><span data-ttu-id="18f6a-393">Este atributo de valor único contém o URI SIP do servidor de gateway CSTA-SIP.</span><span class="sxs-lookup"><span data-stu-id="18f6a-393">This single-valued attribute contains the SIP URI of the CSTA-SIP gateway server.</span></span> <span data-ttu-id="18f6a-394">Este atributo está marcado para replicação de catálogo global, mas não está indexado.</span><span class="sxs-lookup"><span data-stu-id="18f6a-394">This attribute is marked for Global Catalog replication but is not indexed.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-395">Novo no Microsoft Office Live Communications Server 2005 com SP1</span><span class="sxs-lookup"><span data-stu-id="18f6a-395">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-396">msRTCSIP-LocalNormalizationData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-396">msRTCSIP-LocalNormalizationData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-397">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="18f6a-397">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-398">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-398">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="18f6a-399">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-399">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-400">msRTCSIP-LocalNormalizationLinks (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-400">msRTCSIP-LocalNormalizationLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-401">Este atributo com valores múltiplos contém uma lista de nomes distintos de normalização (DN) locais associados a esse perfil de local.</span><span class="sxs-lookup"><span data-stu-id="18f6a-401">This multi-valued attribute contains a list of local normalization distinguished names (DN) associated with this location profile.</span></span> <span data-ttu-id="18f6a-402">O tipo desse atributo é um binário DN.</span><span class="sxs-lookup"><span data-stu-id="18f6a-402">The type of this attribute is a DN binary.</span></span> <span data-ttu-id="18f6a-403">Há uma relação um-para-muitos entre o perfil de local e as regras de normalização local.</span><span class="sxs-lookup"><span data-stu-id="18f6a-403">There is a one-to-many relationship between location profile and local normalization rules.</span></span> <span data-ttu-id="18f6a-404">A ordenação da lista de DNs de normalização local deve ser mantida na ordem especificada pelo administrador.</span><span class="sxs-lookup"><span data-stu-id="18f6a-404">The ordering of the list of local normalization DNs must be maintained in the order specified by the administrator.</span></span> <span data-ttu-id="18f6a-405">A preservação do pedido é mantida pela parte binária do binário DN, que especifica o índice de pedidos.</span><span class="sxs-lookup"><span data-stu-id="18f6a-405">The preservation of order is maintained by the binary portion of the DN binary, which specifies the order index.</span></span></p>
<p><span data-ttu-id="18f6a-406">Link encaminhar: <strong>link ID 11034</strong></span><span class="sxs-lookup"><span data-stu-id="18f6a-406">Forward link: <strong>Link ID 11034</strong></span></span></p>
<p><span data-ttu-id="18f6a-407">O vínculo inverso correspondente a este atributo de vínculo sequencial é <strong>msRTCSIP-LocationProfileBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="18f6a-407">The corresponding back link to this forward link attribute is <strong>msRTCSIP-LocationProfileBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-408">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-408">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="18f6a-409">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-409">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-410">msRTCSIP-LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="18f6a-410">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
<td><p><span data-ttu-id="18f6a-411">Este atributo contém uma lista de opções para a regra de normalização.</span><span class="sxs-lookup"><span data-stu-id="18f6a-411">This attribute contains a list of options for the normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-412">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="18f6a-412">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-413">msRTCSIP-LocationName (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-413">msRTCSIP-LocationName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-414">Esse atributo de valor único contém um nome amigável para o perfil de local que indica qual local esse perfil representa.</span><span class="sxs-lookup"><span data-stu-id="18f6a-414">This single-valued attribute contains a friendly name for the location profile that indicates which location this profile represents.</span></span> <span data-ttu-id="18f6a-415">Como pode haver vários perfis de local, o administrador precisa de uma maneira de distinguir entre diferentes perfis.</span><span class="sxs-lookup"><span data-stu-id="18f6a-415">Because there can be multiple location profiles, the administrator needs a way to distinguish between different profiles.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-416">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-416">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="18f6a-417">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-417">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-418">msRTCSIP-locationProfileBL (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-418">msRTCSIP-locationProfileBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-419">Este atributo com valores múltiplos contém uma lista de nomes distintos do perfil de local.</span><span class="sxs-lookup"><span data-stu-id="18f6a-419">This multi-valued attribute contains a list of location profile distinguished names.</span></span> <span data-ttu-id="18f6a-420">Este atributo especifica o vínculo inverso com um ou mais perfis de local.</span><span class="sxs-lookup"><span data-stu-id="18f6a-420">This attribute specifies the back link to one or more location profiles.</span></span></p>
<p><span data-ttu-id="18f6a-421">Vínculo inverso: <strong>link ID 11035</strong></span><span class="sxs-lookup"><span data-stu-id="18f6a-421">Back link: <strong>Link ID 11035</strong></span></span></p>
<p><span data-ttu-id="18f6a-422">Este atributo corresponde ao vínculo sequencial <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="18f6a-422">This attribute corresponds to the forward link <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-423">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-423">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="18f6a-424">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-424">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-425">msRTCSIP-LocationProfileData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-425">msRTCSIP-LocationProfileData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-426">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="18f6a-426">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-427">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-427">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="18f6a-428">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-428">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-429">msRTCSIP-LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="18f6a-429">msRTCSIP-LocationProfileOptions</span></span></p></td>
<td><p><span data-ttu-id="18f6a-430">Este atributo contém as opções para o perfil de local.</span><span class="sxs-lookup"><span data-stu-id="18f6a-430">This attribute contains the options for the location profile.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-431">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="18f6a-431">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-432">msRTCSIP-MappingContact</span><span class="sxs-lookup"><span data-stu-id="18f6a-432">msRTCSIP-MappingContact</span></span></p></td>
<td><p><span data-ttu-id="18f6a-433">Este atributo de vários valores contém uma lista de contatos de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="18f6a-433">This multiple-value attribute holds a list of application contacts.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-434">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="18f6a-434">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-435">msRTCSIP-MappingLocation</span><span class="sxs-lookup"><span data-stu-id="18f6a-435">msRTCSIP-MappingLocation</span></span></p></td>
<td><p><span data-ttu-id="18f6a-436">Este atributo de vários valores contém uma lista de perfis de local.</span><span class="sxs-lookup"><span data-stu-id="18f6a-436">This multiple-value attribute holds a list of location profiles.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-437">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="18f6a-437">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-438">msRTCSIP-MaxNumOutstandingSearchPerServer (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-438">msRTCSIP-MaxNumOutstandingSearchPerServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-439">Este atributo representa o número máximo de solicitações de pesquisa pendentes por servidor.</span><span class="sxs-lookup"><span data-stu-id="18f6a-439">This attribute represents the maximum number of outstanding search requests per server.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-440">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-440">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-441">msRTCSIP-MaxNumSubscriptionsPerUser (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-441">msRTCSIP-MaxNumSubscriptionsPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-442">O atributo representa o número máximo de inscrições por usuário.</span><span class="sxs-lookup"><span data-stu-id="18f6a-442">The attribute represents the maximum number of subscriptions per user.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-443">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-443">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-444">msRTCSIP-MaxPresenceSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-444">msRTCSIP-MaxPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-445">Este atributo representa a janela de tempo limite máximo da assinatura.</span><span class="sxs-lookup"><span data-stu-id="18f6a-445">This attribute represents the maximum subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-446">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-446">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-447">msRTCSIP-MaxRegistrationsTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-447">msRTCSIP-MaxRegistrationsTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-448">Este atributo representa a janela de tempo limite de registros máximos.</span><span class="sxs-lookup"><span data-stu-id="18f6a-448">This attribute represents the maximum registrations time-out window.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-449">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-449">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-450">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-450">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-451">Este atributo representa a janela de tempo limite máximo de assinaturas de dados móveis.</span><span class="sxs-lookup"><span data-stu-id="18f6a-451">This attribute represents the maximum roaming data subscriptions time-out window.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-452">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-452">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-453">msRTCSIP-MCUData</span><span class="sxs-lookup"><span data-stu-id="18f6a-453">msRTCSIP-MCUData</span></span></p></td>
<td><p><span data-ttu-id="18f6a-454">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="18f6a-454">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-455">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-455">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-456">msRTCSIP-MCUFactoryAddress</span><span class="sxs-lookup"><span data-stu-id="18f6a-456">msRTCSIP-MCUFactoryAddress</span></span></p></td>
<td><p><span data-ttu-id="18f6a-457">Este atributo é um atributo de ponto de controle de serviço na classe Computer que especifica um link de volta à fábrica da unidade de controle multiponto (MCU) à qual ele pertence.</span><span class="sxs-lookup"><span data-stu-id="18f6a-457">This attribute is a service control point attribute under the computer class that specifies a link back to the multipoint control unit (MCU) Factory to which it belongs.</span></span> <span data-ttu-id="18f6a-458">Esse atributo e o ponto de controle de serviço são criados para cada Microsoft MCU.</span><span class="sxs-lookup"><span data-stu-id="18f6a-458">This service control point and attribute is created for every Microsoft MCU.</span></span> <span data-ttu-id="18f6a-459">Cada Microsoft MCU deve localizar o servidor back-end do pool ao qual ele pertence, para recuperar as configurações de nível de pool.</span><span class="sxs-lookup"><span data-stu-id="18f6a-459">Each Microsoft MCU must find the Back End Server of the pool to which it belongs, in order to retrieve pool-level settings from it.</span></span></p>
<p><span data-ttu-id="18f6a-460">O valor desse atributo é o nome diferenciado (DN) da fábrica MCU.</span><span class="sxs-lookup"><span data-stu-id="18f6a-460">The value of this attribute is the distinguished name (DN) of the MCU Factory.</span></span> <span data-ttu-id="18f6a-461">Este é um atributo de valor único e marcado para replicação de catálogo global.</span><span class="sxs-lookup"><span data-stu-id="18f6a-461">This is a single-valued attribute and marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="18f6a-462">Link encaminhar: <strong>link ID 11026</strong></span><span class="sxs-lookup"><span data-stu-id="18f6a-462">Forward link: <strong>Link ID 11026</strong></span></span></p>
<p><span data-ttu-id="18f6a-463">O vínculo inverso correspondente a este atributo de vínculo sequencial é <strong>msRTCSIP-MCUServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="18f6a-463">The corresponding back link to this forward link attribute is <strong>msRTCSIP-MCUServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-464">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-464">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-465">msRTCSIP-MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="18f6a-465">msRTCSIP-MCUFactoryData</span></span></p></td>
<td><p><span data-ttu-id="18f6a-466">Este é um atributo reservado de cadeia de caracteres múltipla.</span><span class="sxs-lookup"><span data-stu-id="18f6a-466">This is a multi-string reserved attribute.</span></span> <span data-ttu-id="18f6a-467">As configurações armazenadas nesse atributo são representadas como pares nome = valor.</span><span class="sxs-lookup"><span data-stu-id="18f6a-467">Settings stored in this attribute are represented as name=value pairs.</span></span> <span data-ttu-id="18f6a-468">Os pares name = value atualmente definidos são:</span><span class="sxs-lookup"><span data-stu-id="18f6a-468">Currently defined name=value pairs are:</span></span></p>
<ul>
<li><p><span data-ttu-id="18f6a-469">FactoryURL = &lt;URL&gt;</span><span class="sxs-lookup"><span data-stu-id="18f6a-469">FactoryURL = &lt;URL&gt;</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="18f6a-470">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-470">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-471">msRTCSIP-MCUFactoryPath</span><span class="sxs-lookup"><span data-stu-id="18f6a-471">msRTCSIP-MCUFactoryPath</span></span></p></td>
<td><p><span data-ttu-id="18f6a-472">Este é um atributo de valor único que contém o nome diferenciado (DN) de uma única fábrica de MCU associada a um pool.</span><span class="sxs-lookup"><span data-stu-id="18f6a-472">This is a single-valued attribute that contains the distinguished name (DN) of a single MCU factory associated with a pool.</span></span></p>
<p><span data-ttu-id="18f6a-473">Link encaminhar: <strong>link ID 11024</strong></span><span class="sxs-lookup"><span data-stu-id="18f6a-473">Forward link: <strong>Link ID 11024</strong></span></span></p>
<p><span data-ttu-id="18f6a-474">O vínculo inverso correspondente a este atributo de vínculo sequencial é <strong>msRTCSIP-PoolAddresses</strong>.</span><span class="sxs-lookup"><span data-stu-id="18f6a-474">The corresponding back link to this forward link attribute is <strong>msRTCSIP-PoolAddresses</strong>.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-475">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-475">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-476">msRTCSIP-MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="18f6a-476">msRTCSIP-MCUFactoryProviderID</span></span></p></td>
<td><p><span data-ttu-id="18f6a-477">Este atributo é uma cadeia de caracteres de valor único que especifica o GUID do provedor de fábrica MCU.</span><span class="sxs-lookup"><span data-stu-id="18f6a-477">This attribute is a single-valued string that specifies the GUID of the MCU factory provider.</span></span> <span data-ttu-id="18f6a-478">Com base no valor de GUID, o processo de fábrica da MCU determina se deve ser atendido este tipo de MCU.</span><span class="sxs-lookup"><span data-stu-id="18f6a-478">Based on the GUID value, the MCU factory process determines whether to service this MCU type.</span></span> <span data-ttu-id="18f6a-479">Se o valor de GUID for <strong>{F0810510-424F-46ef-84fe-6CC720DF1791}</strong>, o processo de fábrica MCU (disponível por padrão no Lync Server) o processará.</span><span class="sxs-lookup"><span data-stu-id="18f6a-479">If the GUID value is <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, then the MCU factory process (available by default in Lync Server) will process it.</span></span> <span data-ttu-id="18f6a-480">Para qualquer outro valor de GUID, o processo de fábrica MCU não irá atender ao tipo MCU.</span><span class="sxs-lookup"><span data-stu-id="18f6a-480">For any other GUID value, the MCU factory process will not service the MCU type.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-481">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-481">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-482">msRTCSIP-MCUServers</span><span class="sxs-lookup"><span data-stu-id="18f6a-482">msRTCSIP-MCUServers</span></span></p></td>
<td><p><span data-ttu-id="18f6a-483">Este atributo é uma lista de vários valores de nomes diferenciados (DN).</span><span class="sxs-lookup"><span data-stu-id="18f6a-483">This attribute is a multi-valued list of distinguished names (DN).</span></span> <span data-ttu-id="18f6a-484">Este atributo contém uma lista de todos os servidores MCU do mesmo tipo e fornecedor associados a essa fábrica de MCU.</span><span class="sxs-lookup"><span data-stu-id="18f6a-484">This attribute contains a list of all MCU servers of the same type and vendor associated with this MCU factory.</span></span> <span data-ttu-id="18f6a-485">O valor válido para cada segmento é 63 caracteres; o valor válido para o FQDN inteiro é de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="18f6a-485">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p>
<p><span data-ttu-id="18f6a-486">Vínculo inverso: link ID 11027</span><span class="sxs-lookup"><span data-stu-id="18f6a-486">Back link: Link ID 11027</span></span></p>
<p><span data-ttu-id="18f6a-487">O vínculo sequencial correspondente a este vínculo inverso é <strong>msRTCSIP-MCUFactoryAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="18f6a-487">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-488">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-488">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-489">msRTCSIP-MCUType</span><span class="sxs-lookup"><span data-stu-id="18f6a-489">msRTCSIP-MCUType</span></span></p></td>
<td><p><span data-ttu-id="18f6a-490">Este atributo é uma cadeia de caracteres de valor único que especifica o meio que o MCU pode lidar.</span><span class="sxs-lookup"><span data-stu-id="18f6a-490">This attribute is a single-valued string that specifies the medium the MCU can handle.</span></span></p>
<p><span data-ttu-id="18f6a-491">Os tipos válidos suportados são:</span><span class="sxs-lookup"><span data-stu-id="18f6a-491">Supported valid types are:</span></span></p>
<ul>
<li><p><span data-ttu-id="18f6a-492">Atenda</span><span class="sxs-lookup"><span data-stu-id="18f6a-492">meeting</span></span></p></li>
<li><p><span data-ttu-id="18f6a-493">áudio-vídeo</span><span class="sxs-lookup"><span data-stu-id="18f6a-493">audio-video</span></span></p></li>
<li><p><span data-ttu-id="18f6a-494">chat</span><span class="sxs-lookup"><span data-stu-id="18f6a-494">chat</span></span></p></li>
<li><p><span data-ttu-id="18f6a-495">Phone-conf</span><span class="sxs-lookup"><span data-stu-id="18f6a-495">phone-conf</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="18f6a-496">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-496">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-497">msRTCSIP-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="18f6a-497">msRTCSIP-MCUVendor</span></span></p></td>
<td><p><span data-ttu-id="18f6a-498">Este atributo é uma cadeia de caracteres de valor único que especifica o nome de um fornecedor MCU.</span><span class="sxs-lookup"><span data-stu-id="18f6a-498">This attribute is a single-valued string that specifies an MCU vendor’s name.</span></span> <span data-ttu-id="18f6a-499">Todos os Microsoft MCUs especificarão esse atributo como <strong>Microsoft Corporation</strong>.</span><span class="sxs-lookup"><span data-stu-id="18f6a-499">All Microsoft MCUs will specify this attribute to be <strong>Microsoft Corporation</strong>.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-500">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-500">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-501">msRTCSIP-MeetingFlags (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-501">msRTCSIP-MeetingFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-502">Este atributo define opções de reunião diferentes que são habilitadas globalmente para todos os usuários ou objetos de contato.</span><span class="sxs-lookup"><span data-stu-id="18f6a-502">This attribute defines different meeting options that are enabled globally for all users or contact objects.</span></span> <span data-ttu-id="18f6a-503">Este atributo é um valor de máscara de bits de tipo inteiro.</span><span class="sxs-lookup"><span data-stu-id="18f6a-503">This attribute is a bit-mask value of integer type.</span></span></p>
<p><span data-ttu-id="18f6a-504">Os valores válidos (e as posições de bit associadas) são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="18f6a-504">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="18f6a-505">0: AllowOrganizeMeetingWithAnonymousParticipants is é nenhum (não permitir que os usuários convidem usuários anônimos para reuniões) (nenhum bit definido)</span><span class="sxs-lookup"><span data-stu-id="18f6a-505">0: AllowOrganizeMeetingWithAnonymousParticipants is None (do not allow users to invite anonymous users to meetings) (no bits set)</span></span></p></li>
<li><p><span data-ttu-id="18f6a-506">4: AllowOrganizeMeetingWithAnonymousParticipants is é todos (permitir que todos os usuários convidem usuários anônimos para reuniões) (posição de bit 2)</span><span class="sxs-lookup"><span data-stu-id="18f6a-506">4: AllowOrganizeMeetingWithAnonymousParticipants is Everyone (allow all users to invite anonymous users to meetings) (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="18f6a-507">8: AllowOrganizeMeetingWithAnonymousParticipants is é UsePerUserSetting (permitir que os usuários convidem usuários anônimos para reuniões com base na configuração do usuário) (posição de bit 3)</span><span class="sxs-lookup"><span data-stu-id="18f6a-507">8: AllowOrganizeMeetingWithAnonymousParticipants is UsePerUserSetting (allow users to invite anonymous users to meetings based on per user setting) (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="18f6a-508">16: UserPerUserMeetingPolicy (a política de reunião é definida por usuário) (posição de bit 4)</span><span class="sxs-lookup"><span data-stu-id="18f6a-508">16: UserPerUserMeetingPolicy (meeting policy is defined per user) (bit position 4)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="18f6a-509">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-509">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="18f6a-510">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-510">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-511">msRTCSIP-MeetingPolicy (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-511">msRTCSIP-MeetingPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-512">Este atributo especifica o nome diferenciado (DN) da política que o administrador atribuiu a este usuário como um atributo de valor único.</span><span class="sxs-lookup"><span data-stu-id="18f6a-512">This attribute specifies the distinguished name (DN) of the policy the administrator has assigned for this user as a single-valued attribute.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-513">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-513">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="18f6a-514">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-514">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-515">msRTCSIP-MinPresenceSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-515">msRTCSIP-MinPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-516">Este atributo representa a janela de tempo limite de assinatura de presença mínima.</span><span class="sxs-lookup"><span data-stu-id="18f6a-516">This attribute represents the minimum presence subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-517">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-517">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-518">msRTCSIP-MinRegistrationTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-518">msRTCSIP-MinRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-519">Este atributo representa a janela do tempo limite mínimo de registro.</span><span class="sxs-lookup"><span data-stu-id="18f6a-519">This attribute represents the minimum registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-520">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-520">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="18f6a-521">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-521">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-522">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-522">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-523">Este atributo representa a janela de tempo limite de assinatura de dados de roaming mínimo.</span><span class="sxs-lookup"><span data-stu-id="18f6a-523">This attribute represents the minimum roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-524">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-524">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="18f6a-525">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-525">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-526">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="18f6a-526">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="18f6a-527">Este atributo é usado para armazenar o backend do SQL Server espelhado usado pelo pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="18f6a-527">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-528">Novo no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="18f6a-528">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-529">msRTCSIP-MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="18f6a-529">msRTCSIP-MobilityFlags</span></span></p></td>
<td><p><span data-ttu-id="18f6a-530">Este atributo contém opções e sinalizadores que definem as configurações de mobilidade.</span><span class="sxs-lookup"><span data-stu-id="18f6a-530">This attribute contains options and flags that define mobility settings.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-531">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="18f6a-531">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-532">msRTCSIP-MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="18f6a-532">msRTCSIP-MobilityPolicy</span></span></p></td>
<td><p><span data-ttu-id="18f6a-533">Este atributo contém o DN de um objeto de política de mobilidade.</span><span class="sxs-lookup"><span data-stu-id="18f6a-533">This attribute contains the DN for a mobility policy object.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-534">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="18f6a-534">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-535">msRTCSIP-NumDevicesPerUser (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-535">msRTCSIP-NumDevicesPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-536">Este atributo representa o número permitido de dispositivos nos quais um usuário pode se registrar para comunicações SIP e inscrever-se em presença.</span><span class="sxs-lookup"><span data-stu-id="18f6a-536">This attribute represents the allowed number of devices on which a user can register for SIP communications and subscribe to presence.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-537">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-537">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="18f6a-538">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-538">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-539">msRTCSIP-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="18f6a-539">msRTCSIP-OptionFlags</span></span></p></td>
<td><p><span data-ttu-id="18f6a-540">Este atributo especifica as opções que são habilitadas para o usuário ou objeto de contato.</span><span class="sxs-lookup"><span data-stu-id="18f6a-540">This attribute specifies the options that are enabled for the user or contact object.</span></span> <span data-ttu-id="18f6a-541">Este atributo é um valor de máscara de bits do tipo inteiro.</span><span class="sxs-lookup"><span data-stu-id="18f6a-541">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="18f6a-542">Cada opção é representada por um bit.</span><span class="sxs-lookup"><span data-stu-id="18f6a-542">Each option is represented by a bit.</span></span> <span data-ttu-id="18f6a-543">Este atributo está marcado para replicação de catálogo global.</span><span class="sxs-lookup"><span data-stu-id="18f6a-543">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="18f6a-544">Os valores válidos (e as posições de bit associadas) são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="18f6a-544">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="18f6a-545">1: habilitado para conectividade de mensagens instantâneas públicas (IM) (posição de bit 0)</span><span class="sxs-lookup"><span data-stu-id="18f6a-545">1: Enabled for public instant messaging (IM) connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="18f6a-546">2: reservado (posição de bit 1)</span><span class="sxs-lookup"><span data-stu-id="18f6a-546">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="18f6a-547">4: reservado (posição de bit 2)</span><span class="sxs-lookup"><span data-stu-id="18f6a-547">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="18f6a-548">8: reservado (posição de bit 3)</span><span class="sxs-lookup"><span data-stu-id="18f6a-548">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="18f6a-549">16: controle de chamada remota habilitado [telefonia] (posição de bit 4)</span><span class="sxs-lookup"><span data-stu-id="18f6a-549">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="18f6a-550">64: AllowOrganizeMeetingWithAnonymousParticipants is (permitir que os usuários convidem usuários anônimos para reuniões (posição de bit 6)</span><span class="sxs-lookup"><span data-stu-id="18f6a-550">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="18f6a-551">128: UCEnabled (habilitar usuários para UC) (posição de bit 7)</span><span class="sxs-lookup"><span data-stu-id="18f6a-551">128: UCEnabled (enable users for UC) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="18f6a-552">256: EnabledForEnhancedPresence (habilitar usuário para conectividade de IM pública) (posição de bit 8)</span><span class="sxs-lookup"><span data-stu-id="18f6a-552">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="18f6a-553">512: RemoteCallControlDualMode (posição de bit 9)</span><span class="sxs-lookup"><span data-stu-id="18f6a-553">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="18f6a-554">Novo no Live Communications Server 2005 com SP1.</span><span class="sxs-lookup"><span data-stu-id="18f6a-554">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-555">msRTCSIP-OriginatorSID</span><span class="sxs-lookup"><span data-stu-id="18f6a-555">msRTCSIP-OriginatorSID</span></span></p></td>
<td><p><span data-ttu-id="18f6a-556">Esse atributo é usado em topologias de floresta central e de recursos para habilitar o logon único quando o objeto userid da conta principal do Windows NT Server é copiado para este atributo do usuário ou do objeto de contato correspondente na floresta de recursos ou central.</span><span class="sxs-lookup"><span data-stu-id="18f6a-556">This attribute is used in resource and central forest topologies to enable single sign-on when a user’s ObjectSID from the Windows NT Server principal account is copied into this attribute of the corresponding user or contact object in the resource or central forest.</span></span> <span data-ttu-id="18f6a-557">O Communicator Web Access pesquisa um usuário no AD DS usando este atributo ou o objeto userid.</span><span class="sxs-lookup"><span data-stu-id="18f6a-557">Communicator Web Access searches for a user in AD DS using this attribute or the user’s ObjectSID.</span></span> <span data-ttu-id="18f6a-558">Este atributo está marcado para replicação de catálogo global.</span><span class="sxs-lookup"><span data-stu-id="18f6a-558">This attribute is marked for global catalog replication.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-559">msRTCSIP-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="18f6a-559">msRTCSIP-OwnerUrn</span></span></p></td>
<td><p><span data-ttu-id="18f6a-560">Este atributo é o nome de recurso uniforme (URN) do proprietário de um contato de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="18f6a-560">This attribute is the Uniform Resource Name (URN) of the owner for an application contact.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-561">Novo no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-561">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-562">msRTCSIP-Pattern (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-562">msRTCSIP-Pattern (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-563">Este atributo de cadeia de caracteres de valor único contém um padrão usado para números de discagem correspondentes no formato E. 164.</span><span class="sxs-lookup"><span data-stu-id="18f6a-563">This single-valued string attribute contains a pattern used for matching dial numbers into E.164 format.</span></span> <span data-ttu-id="18f6a-564">Se o número de discagem corresponder a este padrão, a tradução será aplicada ao número discado.</span><span class="sxs-lookup"><span data-stu-id="18f6a-564">If the dial number matches this pattern, the translation is applied to the dialed number.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-565">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-565">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="18f6a-566">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-566">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-567">msRTCSIP-PhoneRouteBL (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-567">msRTCSIP-PhoneRouteBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-568">Este atributo com valores múltiplos contém uma lista de nomes distintos de rotas de telefone (DN).</span><span class="sxs-lookup"><span data-stu-id="18f6a-568">This multi-valued attribute contains a list of phone route distinguished names (DN).</span></span> <span data-ttu-id="18f6a-569">Este atributo especifica o vínculo inverso com uma ou mais rotas de telefone.</span><span class="sxs-lookup"><span data-stu-id="18f6a-569">This attribute specifies the back link to one or more phone routes.</span></span></p>
<p><span data-ttu-id="18f6a-570">Vínculo inverso: <strong>link ID 11033</strong></span><span class="sxs-lookup"><span data-stu-id="18f6a-570">Back link: <strong>Link ID 11033</strong></span></span></p>
<p><span data-ttu-id="18f6a-571">Este atributo corresponde ao vínculo sequencial <strong>msRTCSIP-RouteUsageLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="18f6a-571">This attribute corresponds to the forward link <strong>msRTCSIP-RouteUsageLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-572">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-572">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="18f6a-573">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-573">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-574">msRTCSIP-PhoneRouteData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-574">msRTCSIP-PhoneRouteData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-575">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="18f6a-575">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-576">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-576">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-577">msRTCSIP-PhoneRouteName (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-577">msRTCSIP-PhoneRouteName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-578">Este atributo de cadeia de caracteres UNICODE de valor único especifica o nome amigável da rota de telefone, para que possa ser facilmente referenciado pelo administrador.</span><span class="sxs-lookup"><span data-stu-id="18f6a-578">This single valued UNICODE string attribute specifies the friendly name of the phone route, so it can easily be referenced by the administrator.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-579">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-579">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-580">msRTCSIP-PhoneUsageData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-580">msRTCSIP-PhoneUsageData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-581">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="18f6a-581">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-582">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-582">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="18f6a-583">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-583">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-584">msRTCSIP-PolicyContent (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-584">msRTCSIP-PolicyContent (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-585">Este atributo é uma cadeia de caracteres Unicode de valor único.</span><span class="sxs-lookup"><span data-stu-id="18f6a-585">This attribute is a single-valued Unicode string.</span></span> <span data-ttu-id="18f6a-586">Este atributo de cadeia de caracteres contém a definição de política no formato XML.</span><span class="sxs-lookup"><span data-stu-id="18f6a-586">This string attribute contains the policy definition in XML format.</span></span> <span data-ttu-id="18f6a-587">A definição de esquema XML é comum entre diferentes tipos de política, apenas as configurações são diferentes para cada tipo de política.</span><span class="sxs-lookup"><span data-stu-id="18f6a-587">The XML schema definition is common across different policy types, only the settings are different for each policy type.</span></span></p>
<p><span data-ttu-id="18f6a-588">A definição de esquema XML (XSD) é definida da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="18f6a-588">The XML schema definition (XSD) is defined as follows:</span></span></p>
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
<td><p><span data-ttu-id="18f6a-589">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-589">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="18f6a-590">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-590">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-591">msRTCSIP-PolicyData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-591">msRTCSIP-PolicyData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-592">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="18f6a-592">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-593">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-593">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="18f6a-594">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-594">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-595">msRTCSIP-PolicyType (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-595">msRTCSIP-PolicyType (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-596">Este atributo de cadeia de caracteres Unicode de valor único contém o tipo de política.</span><span class="sxs-lookup"><span data-stu-id="18f6a-596">This single-valued Unicode string attribute contains the policy type.</span></span> <span data-ttu-id="18f6a-597">Os tipos de política válidos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="18f6a-597">Valid policy types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="18f6a-598">Atenda</span><span class="sxs-lookup"><span data-stu-id="18f6a-598">meeting</span></span></p></li>
<li><p><span data-ttu-id="18f6a-599">telefonia</span><span class="sxs-lookup"><span data-stu-id="18f6a-599">telephony</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="18f6a-600">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-600">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="18f6a-601">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-601">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-602">msRTCSIP-PoolAddress</span><span class="sxs-lookup"><span data-stu-id="18f6a-602">msRTCSIP-PoolAddress</span></span></p></td>
<td><p><span data-ttu-id="18f6a-603">Este atributo especifica um link de volta para o pool ao qual um computador pertence.</span><span class="sxs-lookup"><span data-stu-id="18f6a-603">This attribute specifies a link back to the pool to which a computer belongs.</span></span> <span data-ttu-id="18f6a-604">Esse atributo é definido independentemente se o computador está executando a edição Standard ou Enterprise Edition do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="18f6a-604">This attribute is set regardless of whether the computer is running the Standard Edition or the Enterprise Edition of Lync Server.</span></span> <span data-ttu-id="18f6a-605">Este atributo está marcado para replicação de catálogo global.</span><span class="sxs-lookup"><span data-stu-id="18f6a-605">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="18f6a-606">O valor válido é o nome de domínio do pool.</span><span class="sxs-lookup"><span data-stu-id="18f6a-606">The valid value is the domain name of the pool.</span></span></p>
<p><span data-ttu-id="18f6a-607">Link encaminhar: <strong>link ID 11022</strong></span><span class="sxs-lookup"><span data-stu-id="18f6a-607">Forward link: <strong>Link ID 11022</strong></span></span></p>
<p><span data-ttu-id="18f6a-608">O vínculo inverso correspondente a este atributo de vínculo sequencial é <strong>msRTCSIP-FrontEndServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="18f6a-608">The corresponding back link to this forward link attribute is <strong>msRTCSIP-FrontEndServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-609">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="18f6a-609">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-610">msRTCSIP-PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="18f6a-610">msRTCSIP-PoolAddresses</span></span></p></td>
<td><p><span data-ttu-id="18f6a-611">Este é um atributo com valores múltiplos que contém uma lista de nomes diferenciados (DN) de pools com os quais a fábrica MCU está associada.</span><span class="sxs-lookup"><span data-stu-id="18f6a-611">This is a multi-valued attribute that contains a list of the distinguished names (DN) of pools with which the MCU factory is associated.</span></span></p>
<p><span data-ttu-id="18f6a-612">Vínculo inverso: <strong>link ID 11025</strong></span><span class="sxs-lookup"><span data-stu-id="18f6a-612">Back link: <strong>Link ID 11025</strong></span></span></p>
<p><span data-ttu-id="18f6a-613">O vínculo sequencial correspondente a este vínculo inverso é <strong>msRTCSIP-MCUFactoryPath</strong>.</span><span class="sxs-lookup"><span data-stu-id="18f6a-613">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryPath</strong>.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-614">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-614">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-615">msRTCSIP-PoolData</span><span class="sxs-lookup"><span data-stu-id="18f6a-615">msRTCSIP-PoolData</span></span></p></td>
<td><p><span data-ttu-id="18f6a-616">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="18f6a-616">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-617">Novo no Live Communications Server 2005 com SP1.</span><span class="sxs-lookup"><span data-stu-id="18f6a-617">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-618">msRTCSIP-PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="18f6a-618">msRTCSIP-PoolDisplayName</span></span></p></td>
<td><p><span data-ttu-id="18f6a-619">Este atributo especifica um nome arbitrário para um pool que é exibido pelo console de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="18f6a-619">This attribute specifies an arbitrary name for a pool that is displayed by the management console.</span></span> <span data-ttu-id="18f6a-620">Esse nome pode ser alterado pelo administrador.</span><span class="sxs-lookup"><span data-stu-id="18f6a-620">This name can be changed by the administrator.</span></span></p>
<p><span data-ttu-id="18f6a-621">O valor válido é uma cadeia de caracteres que representa o nome de um pool.</span><span class="sxs-lookup"><span data-stu-id="18f6a-621">The valid value is a string representing the name of a pool.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-622">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="18f6a-622">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-623">msRTCSIP-PoolDomainFQDN</span><span class="sxs-lookup"><span data-stu-id="18f6a-623">msRTCSIP-PoolDomainFQDN</span></span></p></td>
<td><p><span data-ttu-id="18f6a-624">Este atributo é um valor de cadeia de caracteres de valor único.</span><span class="sxs-lookup"><span data-stu-id="18f6a-624">This attribute is a single-valued string value.</span></span> <span data-ttu-id="18f6a-625">O valor desse atributo, quando presente, representa o FQDN do domínio do pool se o administrador quiser criar um pool de front-ends com um FQDN que não esteja de acordo com a estrutura de domínio do Active Directory na qual o pool de front-ends é criado (por exemplo, um SIP namespace desassociado do namespace DNS (sistema de nomes de domínio).</span><span class="sxs-lookup"><span data-stu-id="18f6a-625">The value of this attribute, when present, represents the pool’s domain FQDN if the administrator wants to create a Front End pool with an FQDN that does not conform to the Active Directory domain structure in which the Front End pool is created (for example, a SIP namespace disjoined from Domain Name System (DNS) namespace).</span></span></p>
<p><span data-ttu-id="18f6a-626">Recomendamos que você mapeie o FQDN do domínio do pool de front-ends para a parte do nome de domínio como o domínio do Active Directory no qual o pool reside.</span><span class="sxs-lookup"><span data-stu-id="18f6a-626">We recommend that you map the Front End pool domain FQDN to the domain name portion as the Active Directory domain in which the pool resides.</span></span> <span data-ttu-id="18f6a-627">Portanto, quando nenhum valor estiver presente nesse atributo, o FQDN do pool de front-ends será o padrão para a estrutura de nome de domínio do Active Directory, conforme indicado pelo atributo <strong>dNSHostName</strong> .</span><span class="sxs-lookup"><span data-stu-id="18f6a-627">Therefore, when no value is present in this attribute, the Front End pool FQDN will default to the Active Directory domain name structure, as denoted by the <strong>dnsHostName</strong> attribute.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-628">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-628">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-629">msRTCSIP-PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="18f6a-629">msRTCSIP-PoolFunctionality</span></span></p></td>
<td><p><span data-ttu-id="18f6a-630">Uma lista de vários valores dos nomes de domínio de todos os servidores do Lync Server, Enterprise Edition associados a um pool.</span><span class="sxs-lookup"><span data-stu-id="18f6a-630">A multi-valued list of the domain names of all Lync Server, Enterprise Edition servers associated with a pool.</span></span> <span data-ttu-id="18f6a-631">Este atributo do tipo Integer define se o pool é capaz de mensagens instantâneas (IM) e presença e reuniões.</span><span class="sxs-lookup"><span data-stu-id="18f6a-631">This attribute of type integer defines whether the pool is capable of instant messaging (IM) and presence, and meetings.</span></span></p>
<p><span data-ttu-id="18f6a-632">Os tipos de valor válidos possíveis são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="18f6a-632">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="18f6a-633">Indefinido: serviço de mensagens instantâneas e presença (Live Communications Server 2005 e 2003)</span><span class="sxs-lookup"><span data-stu-id="18f6a-633">Undefined: IM and Presence Service (Live Communications Server 2005 and 2003)</span></span></p></li>
<li><p><span data-ttu-id="18f6a-634">1: serviço de mensagens instantâneas e presença (Lync Server)</span><span class="sxs-lookup"><span data-stu-id="18f6a-634">1: IM and Presence Service (Lync Server)</span></span></p></li>
<li><p><span data-ttu-id="18f6a-635">2: mensagens instantâneas e serviços de presença e de reunião (Lync Server)</span><span class="sxs-lookup"><span data-stu-id="18f6a-635">2: IM and Presence and Meeting Service (Lync Server)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="18f6a-636">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-636">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-637">msRTCSIP-Pooltype</span><span class="sxs-lookup"><span data-stu-id="18f6a-637">msRTCSIP-PoolType</span></span></p></td>
<td><p><span data-ttu-id="18f6a-638">Este atributo especifica se um pool de servidores está executando o Standard Edition Server ou o servidor Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="18f6a-638">This attribute specifies whether a server pool is running Standard Edition server or Enterprise Edition server.</span></span> <span data-ttu-id="18f6a-639">Este atributo é um valor de máscara de bits do tipo inteiro.</span><span class="sxs-lookup"><span data-stu-id="18f6a-639">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="18f6a-640">Cada opção é representada por um bit.</span><span class="sxs-lookup"><span data-stu-id="18f6a-640">Each option is represented by a bit.</span></span></p>
<p><span data-ttu-id="18f6a-641">Os valores válidos (e as posições de bit associadas) são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="18f6a-641">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="18f6a-642">1: servidor Standard Edition, hospeda usuários (posição de bit 0)</span><span class="sxs-lookup"><span data-stu-id="18f6a-642">1: Standard Edition server, hosts users (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="18f6a-643">2: servidor Enterprise Edition, hospeda usuários (posição de bit 1)</span><span class="sxs-lookup"><span data-stu-id="18f6a-643">2: Enterprise Edition server, hosts users (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="18f6a-644">4: servidor Standard Edition, hospeda aplicativos (posição de bit 2)</span><span class="sxs-lookup"><span data-stu-id="18f6a-644">4: Standard Edition server, hosts applications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="18f6a-645">8: servidor Enterprise Edition, hospeda aplicativos (posição de bit 3)</span><span class="sxs-lookup"><span data-stu-id="18f6a-645">8: Enterprise Edition server, hosts applications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="18f6a-646">Como o Lync Server não dá suporte a pools que hospedam apenas aplicativos, os únicos valores válidos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="18f6a-646">Because Lync Server does not support pools that host only applications, the only valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="18f6a-647">5: servidor Standard Edition, hospeda usuários e aplicativos (posições de bit 0 e 2)</span><span class="sxs-lookup"><span data-stu-id="18f6a-647">5: Standard Edition server, hosts users and applications (bit positions 0 and 2)</span></span></p></li>
<li><p><span data-ttu-id="18f6a-648">10: servidor Enterprise Edition, hospeda usuários e aplicativos (posições de bit 1 e 3)</span><span class="sxs-lookup"><span data-stu-id="18f6a-648">10: Enterprise Edition server, hosts users and applications (bit positions 1 and 3)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="18f6a-649">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="18f6a-649">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-650">msRTCSIP-PoolVersion</span><span class="sxs-lookup"><span data-stu-id="18f6a-650">msRTCSIP-PoolVersion</span></span></p></td>
<td><p><span data-ttu-id="18f6a-651">Este atributo define a versão do pool.</span><span class="sxs-lookup"><span data-stu-id="18f6a-651">This attribute defines the pool version.</span></span> <span data-ttu-id="18f6a-652">É um tipo inteiro que é incrementado com cada lançamento de produto principal.</span><span class="sxs-lookup"><span data-stu-id="18f6a-652">It is an integer type that is incremented with each major product release.</span></span></p>
<p><span data-ttu-id="18f6a-653">Os tipos de valor válidos possíveis são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="18f6a-653">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="18f6a-654">0: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="18f6a-654">0: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="18f6a-655">1: Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="18f6a-655">1: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="18f6a-656">2: Live Communications Server 2005 com SP1</span><span class="sxs-lookup"><span data-stu-id="18f6a-656">2: Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="18f6a-657">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="18f6a-657">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="18f6a-658">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="18f6a-658">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="18f6a-659">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="18f6a-659">5: Lync Server 2010</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="18f6a-660">Live Communications Server 2005 com SP1.</span><span class="sxs-lookup"><span data-stu-id="18f6a-660">Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-661">msRTCSIP-PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="18f6a-661">msRTCSIP-PresenceFlags</span></span></p></td>
<td><p><span data-ttu-id="18f6a-662">Este atributo contém opções e sinalizadores que definem configurações de presença.</span><span class="sxs-lookup"><span data-stu-id="18f6a-662">This attribute contains options and flags that define presence settings.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-663">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="18f6a-663">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-664">msRTCSIP-PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="18f6a-664">msRTCSIP-PresencePolicy</span></span></p></td>
<td><p><span data-ttu-id="18f6a-665">Este atributo contém o DN de um objeto de política de presença.</span><span class="sxs-lookup"><span data-stu-id="18f6a-665">This attribute contains the DN for a presence policy object.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-666">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="18f6a-666">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-667">msRTCSIP-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="18f6a-667">msRTCSIP-PrimaryHomeServer</span></span></p></td>
<td><p><span data-ttu-id="18f6a-668">Este atributo habilita um usuário ou contato para mensagens SIP.</span><span class="sxs-lookup"><span data-stu-id="18f6a-668">This attribute enables a user or contact for SIP messaging.</span></span> <span data-ttu-id="18f6a-669">Ela é adicionada à classe Contact porque na topologia de floresta central, os objetos de contato, não os objetos de usuário, estão habilitados para SIP.</span><span class="sxs-lookup"><span data-stu-id="18f6a-669">It is added to the contact class because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="18f6a-670">O valor válido é o DN do servidor Standard Edition ou pool de front-ends Enterprise Edition onde um usuário está hospedado.</span><span class="sxs-lookup"><span data-stu-id="18f6a-670">The valid value is the DN of the Standard Edition server or Enterprise Edition Front End pool where a user is homed.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-671">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="18f6a-671">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-672">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="18f6a-672">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="18f6a-673">Este atributo contém o endereço SIP de um determinado usuário.</span><span class="sxs-lookup"><span data-stu-id="18f6a-673">This attribute contains the SIP address of a given user.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-674">msRTCSIP-privado</span><span class="sxs-lookup"><span data-stu-id="18f6a-674">msRTCSIP-PrivateLine</span></span></p></td>
<td><p><span data-ttu-id="18f6a-675">Este atributo contém a ID do dispositivo de linha privada.</span><span class="sxs-lookup"><span data-stu-id="18f6a-675">This attribute contains the device ID of the private line device.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-676">Novo no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-676">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-677">msRTCSIP-roteável</span><span class="sxs-lookup"><span data-stu-id="18f6a-677">msRTCSIP-Routable</span></span></p></td>
<td><p><span data-ttu-id="18f6a-678">Este atributo é um atributo booliano usado para determinar se o Lync Server está autorizado a encaminhar para esse serviço usando seu endereço GRUU.</span><span class="sxs-lookup"><span data-stu-id="18f6a-678">This attribute is a Boolean attribute used to determine whether Lync Server is authorized to route to this service using its GRUU address.</span></span> <span data-ttu-id="18f6a-679">Se esse valor for definido como <strong>true</strong>, o Lync Server estará autorizado a encaminhar para esse serviço.</span><span class="sxs-lookup"><span data-stu-id="18f6a-679">If this value is set to <strong>TRUE</strong>, Lync Server is authorized to route to this service.</span></span> <span data-ttu-id="18f6a-680">Se esse valor for definido como <strong>false</strong>, o Lync Server não está autorizado a encaminhar para esse serviço.</span><span class="sxs-lookup"><span data-stu-id="18f6a-680">If this value is set to <strong>FALSE</strong>, Lync Server is not authorized to route to this service.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-681">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-681">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-682">msRTCSIP-RouteUsageAttribute (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-682">msRTCSIP-RouteUsageAttribute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-683">Este atributo de cadeia de caracteres UNICODE de valor único define um atributo que qualifica o uso de uma rota de telefone.</span><span class="sxs-lookup"><span data-stu-id="18f6a-683">This single-valued UNICODE string attribute defines an attribute that qualifies the usage for a phone route.</span></span> <span data-ttu-id="18f6a-684">A seleção de uma rota de telefone é determinada com base em dois elementos: o atributo de uso atribuído à rota de telefone e os atributos de uso de política permitidos do chamador.</span><span class="sxs-lookup"><span data-stu-id="18f6a-684">Selection of a phone route is determined based on two elements: the usage attribute assigned to the phone route and the caller’s allowed policy usage attributes.</span></span> <span data-ttu-id="18f6a-685">A primeira rota de telefone com um atributo de uso que corresponda ao uso permitido pelo chamador está selecionada.</span><span class="sxs-lookup"><span data-stu-id="18f6a-685">The first phone route with a usage attribute that matches the caller’s allowed usage is selected.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-686">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-686">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="18f6a-687">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-687">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-688">msRTCSIP-RouteUsageLinks (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-688">msRTCSIP-RouteUsageLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-689">Este atributo de nome diferenciado (DN) com valores múltiplos contém uma lista de nomes diferenciados de uso de rota.</span><span class="sxs-lookup"><span data-stu-id="18f6a-689">This multi-valued distinguished name (DN) attribute contains a list of route usage distinguished names.</span></span></p>
<p><span data-ttu-id="18f6a-690">Link encaminhar: <strong>link ID 11032</strong></span><span class="sxs-lookup"><span data-stu-id="18f6a-690">Forward link: <strong>Link ID 11032</strong></span></span></p>
<p><span data-ttu-id="18f6a-691">Este atributo é um link de encaminhamento para o vínculo inverso correspondente <strong>msRTCSIP-PhoneRouteBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="18f6a-691">This attribute is a forward link to the corresponding back link <strong>msRTCSIP-PhoneRouteBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-692">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-692">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-693">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="18f6a-693">msRTCSIP-RoutingPoolDN</span></span></p></td>
<td><p><span data-ttu-id="18f6a-694">Este atributo contém o DN que aponta para o pool que todo o tráfego SIP endereçado a essa MCU ou serviço confiável deve passar.</span><span class="sxs-lookup"><span data-stu-id="18f6a-694">This attribute contains the DN that points to the pool that all SIP traffic addressed to this MCU or Trusted Service must go through.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-695">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="18f6a-695">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-696">msRTCSIP-RuleName (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-696">msRTCSIP-RuleName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-697">Este atributo de cadeia de caracteres UNICODE de valor único especifica o nome amigável da regra de normalização, para que possa ser facilmente referenciado por um administrador.</span><span class="sxs-lookup"><span data-stu-id="18f6a-697">This single-valued UNICODE string attribute specifies the friendly name of the normalization rule, so it can easily be referenced by an administrator.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-698">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-698">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="18f6a-699">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-699">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-700">msRTCSIP-SchemaVersion</span><span class="sxs-lookup"><span data-stu-id="18f6a-700">msRTCSIP-SchemaVersion</span></span></p></td>
<td><p><span data-ttu-id="18f6a-701">Este atributo representa a versão do esquema atualmente implantada na organização.</span><span class="sxs-lookup"><span data-stu-id="18f6a-701">This attribute represents the schema version currently deployed in the organization.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-702">msRTCSIP-SearchMaxRequests (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-702">msRTCSIP-SearchMaxRequests (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-703">Este atributo limita o número de resultados de pesquisa a serem retornados de uma pesquisa de diretório quando um usuário procura um contato usando o Communicator.</span><span class="sxs-lookup"><span data-stu-id="18f6a-703">This attribute limits the number of search results to be returned from a directory search when a user searches for a contact using Communicator.</span></span> <span data-ttu-id="18f6a-704">Este atributo substituirá o valor fornecido pelo cliente.</span><span class="sxs-lookup"><span data-stu-id="18f6a-704">This attribute will override the value provided by the client.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-705">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-705">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-706">msRTCSIP-SearchMaxResults (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-706">msRTCSIP-SearchMaxResults (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-707">Esse atributo limita o número de solicitações de pesquisa retornadas.</span><span class="sxs-lookup"><span data-stu-id="18f6a-707">This attribute limits the number of search requests returned.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-708">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-708">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-709">msRTCSIP-ServerBL</span><span class="sxs-lookup"><span data-stu-id="18f6a-709">msRTCSIP-ServerBL</span></span></p></td>
<td><p><span data-ttu-id="18f6a-710">Esse atributo com valores múltiplos é um vínculo inverso que contém uma lista de nomes diferenciados (DN).</span><span class="sxs-lookup"><span data-stu-id="18f6a-710">This multi-valued attribute is a back link that contains a list of distinguished names (DN).</span></span> <span data-ttu-id="18f6a-711">Esse DNs aponta para um objeto pool ou <strong>TrustedService</strong> .</span><span class="sxs-lookup"><span data-stu-id="18f6a-711">These DNs point to a pool or <strong>TrustedService</strong> object.</span></span></p>
<p><span data-ttu-id="18f6a-712">Este atributo corresponde ao vínculo sequencial <strong>msRTCSIP-TrustedServiceLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="18f6a-712">This attribute corresponds to the forward link <strong>msRTCSIP-TrustedServiceLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-713">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-713">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-714">msRTCSIP-Serverrestauração</span><span class="sxs-lookup"><span data-stu-id="18f6a-714">msRTCSIP-ServerData</span></span></p></td>
<td><p><span data-ttu-id="18f6a-715">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="18f6a-715">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-716">msRTCSIP-ServerReferenceBL (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-716">msRTCSIP-ServerReferenceBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-717">Este atributo com valores múltiplos contém uma lista de nomes distintos.</span><span class="sxs-lookup"><span data-stu-id="18f6a-717">This multi-valued attribute contains a list of distinguished names.</span></span> <span data-ttu-id="18f6a-718">Esses nomes distintos são links de volta que fazem referência a outros objetos de servidor que podem ser atribuídos a um perfil de local padrão.</span><span class="sxs-lookup"><span data-stu-id="18f6a-718">These distinguished names are back links that reference other server objects that can be assigned a default location profile.</span></span></p>
<p><span data-ttu-id="18f6a-719">Vínculo inverso: <strong>link ID 11037</strong></span><span class="sxs-lookup"><span data-stu-id="18f6a-719">Back link: <strong>Link ID 11037</strong></span></span></p>
<p><span data-ttu-id="18f6a-720">O vínculo sequencial correspondente a este vínculo inverso é <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span><span class="sxs-lookup"><span data-stu-id="18f6a-720">The corresponding forward link to this back link is <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span></span></p>
<p><span data-ttu-id="18f6a-721">Este atributo de vínculo inverso faz referência somente a pools e servidores de mediação.</span><span class="sxs-lookup"><span data-stu-id="18f6a-721">This back link attribute references pools and Mediation Servers only.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-722">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-722">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="18f6a-723">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-723">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-724">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="18f6a-724">msRTCSIP-ServerVersion</span></span></p></td>
<td><p><span data-ttu-id="18f6a-725">Este atributo define as informações de versão do servidor.</span><span class="sxs-lookup"><span data-stu-id="18f6a-725">This attribute defines the version information of the server.</span></span> <span data-ttu-id="18f6a-726">Este número de versão se aplica a todas as funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="18f6a-726">This version number applies to all server roles.</span></span> <span data-ttu-id="18f6a-727">É um número inteiro de monotonously que aumenta com o lançamento de cada produto oficial.</span><span class="sxs-lookup"><span data-stu-id="18f6a-727">It is a monotonously increasing integer that increments with each official product release.</span></span></p>
<p><span data-ttu-id="18f6a-728">Os valores válidos possíveis são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="18f6a-728">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="18f6a-729">Indefinido: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="18f6a-729">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="18f6a-730">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="18f6a-730">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="18f6a-731">                 Live Communications Server 2005 with SP1</span><span class="sxs-lookup"><span data-stu-id="18f6a-731">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="18f6a-732">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="18f6a-732">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="18f6a-733">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="18f6a-733">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="18f6a-734">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="18f6a-734">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="18f6a-735">6: Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18f6a-735">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="18f6a-736">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-736">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-737">msRTCSIP-SourceObjectType</span><span class="sxs-lookup"><span data-stu-id="18f6a-737">msRTCSIP-SourceObjectType</span></span></p></td>
<td><p><span data-ttu-id="18f6a-738">Este atributo de valor único de tipo inteiro especifica o tipo de objeto ao qual o <strong>msDS-SourceObjectDN</strong> aponta, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="18f6a-738">This single-valued attribute of integer type specifies the type of object the <strong>msDS-SourceObjectDN</strong> points to, as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="18f6a-739">nulo | 0x00000001: representa um objeto de usuário principal do Windows NT Server de uma floresta diferente</span><span class="sxs-lookup"><span data-stu-id="18f6a-739">null | 0x00000001: Represents a Windows NT Server principal user object from a different forest</span></span></p></li>
<li><p><span data-ttu-id="18f6a-740">Os atributos a seguir representam um tipo de grupo de uma floresta diferente para expansão de grupo de distribuição:</span><span class="sxs-lookup"><span data-stu-id="18f6a-740">The following attributes represent a group type from a different forest for distribution group expansion:</span></span></p>
<ul>
<li><p><span data-ttu-id="18f6a-741">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="18f6a-741">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="18f6a-742">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="18f6a-742">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="18f6a-743">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="18f6a-743">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="18f6a-744">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="18f6a-744">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="18f6a-745">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span><span class="sxs-lookup"><span data-stu-id="18f6a-745">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span></span></p></li>
<li><p><span data-ttu-id="18f6a-746">0x90000000: representa um objeto de atendedor automático ou de acesso de assinante da mesma floresta ou de uma floresta diferente</span><span class="sxs-lookup"><span data-stu-id="18f6a-746">0x90000000: Represents an Auto-Attendant or subscriber access object from the same forest or a different forest</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="18f6a-747">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-747">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-748">msRTCSIP-SubscriptionAuthRequired (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-748">msRTCSIP-SubscriptionAuthRequired (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="18f6a-749">Novo no Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="18f6a-749">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="18f6a-750">Obsoleto no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="18f6a-750">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-751">msRTCSIP-TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="18f6a-751">msRTCSIP-TargetHomeServer</span></span></p></td>
<td><p><span data-ttu-id="18f6a-752">Este atributo permite mover um objeto de usuário ou de contato de um pool do Lync Server para outro.</span><span class="sxs-lookup"><span data-stu-id="18f6a-752">This attribute enables you to move a user or contact object from one Lync Server pool to another.</span></span> <span data-ttu-id="18f6a-753">Esse atributo é adicionado à classe Contact, porque na topologia de floresta central, os objetos de contato, não os objetos de usuário, estão habilitados para SIP.</span><span class="sxs-lookup"><span data-stu-id="18f6a-753">This attribute is added to the contact class, because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="18f6a-754">O valor válido é o DN do servidor Standard Edition ou pool de front-ends para o qual o usuário deve ser movido.</span><span class="sxs-lookup"><span data-stu-id="18f6a-754">The valid value is the DN of the destination Standard Edition server or Front End pool to which a user is to be moved.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-755">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="18f6a-755">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-756">msRTCSIP-TargetPhoneNumber (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-756">msRTCSIP-TargetPhoneNumber (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-757">Este atributo de cadeia de caracteres de valor único contém um padrão ou intervalo de números de telefone para rotear para os gateways especificados em <strong>msRTCSIP-gateways</strong>.</span><span class="sxs-lookup"><span data-stu-id="18f6a-757">This single-valued string attribute contains a phone number pattern or range to route to the specified gateways defined in <strong>msRTCSIP-Gateways</strong>.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-758">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-758">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-759">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="18f6a-759">msRTCSIP-TargetUserPolicies</span></span></p></td>
<td><p><span data-ttu-id="18f6a-760">Este atributo armazena pares nome-valor para políticas de destino para usuários do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="18f6a-760">This attribute stores name-value pairs for target policies for Lync Server users.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-761">Novo no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-761">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-762">msRTCSIP-Tenantid</span><span class="sxs-lookup"><span data-stu-id="18f6a-762">msRTCSIP-TenantId</span></span></p></td>
<td><p><span data-ttu-id="18f6a-763">Este atributo armazena o identificador exclusivo de um locatário.</span><span class="sxs-lookup"><span data-stu-id="18f6a-763">This attribute stores the unique identifier for a tenant.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-764">Novo no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-764">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-765">msRTCSIP-Translation (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-765">msRTCSIP-Translation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-766">Este atributo é usado pelo recurso de voz do Lync Server e contém a cadeia de caracteres de conversão a ser aplicada no número discado, se uma correspondência for encontrada.</span><span class="sxs-lookup"><span data-stu-id="18f6a-766">This attribute is used by the voice feature of Lync Server and contains the translation string to apply on the dialed number, if a match is found.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-767">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-767">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="18f6a-768">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-768">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-769">msRTCSIP-TrustedMCUData</span><span class="sxs-lookup"><span data-stu-id="18f6a-769">msRTCSIP-TrustedMCUData</span></span></p></td>
<td><p><span data-ttu-id="18f6a-770">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="18f6a-770">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-771">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-771">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-772">msRTCSIP-TrustedMCUFQDN</span><span class="sxs-lookup"><span data-stu-id="18f6a-772">msRTCSIP-TrustedMCUFQDN</span></span></p></td>
<td><p><span data-ttu-id="18f6a-773">Este atributo é um valor String que contém o FQDN do MCU.</span><span class="sxs-lookup"><span data-stu-id="18f6a-773">This attribute is a string value that contains the FQDN of the MCU.</span></span> <span data-ttu-id="18f6a-774">Este é um atributo de valor único.</span><span class="sxs-lookup"><span data-stu-id="18f6a-774">This is a single-valued attribute.</span></span> <span data-ttu-id="18f6a-775">O valor válido para cada segmento é 63 caracteres; o valor válido para o FQDN inteiro é de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="18f6a-775">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-776">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-776">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-777">msRTCSIP-TrustedProxyData</span><span class="sxs-lookup"><span data-stu-id="18f6a-777">msRTCSIP-TrustedProxyData</span></span></p></td>
<td><p><span data-ttu-id="18f6a-778">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="18f6a-778">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-779">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-779">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-780">msRTCSIP-TrustedProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="18f6a-780">msRTCSIP-TrustedProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="18f6a-781">Este atributo é um valor String que contém o FQDN do servidor de proxy em execução.</span><span class="sxs-lookup"><span data-stu-id="18f6a-781">This attribute is a string value that contains the FQDN of the server running Proxy Server.</span></span> <span data-ttu-id="18f6a-782">Este atributo tem valor único.</span><span class="sxs-lookup"><span data-stu-id="18f6a-782">This attribute is single-valued.</span></span> <span data-ttu-id="18f6a-783">O valor válido para cada segmento é 63 caracteres; o valor válido para o FQDN inteiro é de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="18f6a-783">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-784">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-784">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-785">msRTCSIP-TrustedServerData</span><span class="sxs-lookup"><span data-stu-id="18f6a-785">msRTCSIP-TrustedServerData</span></span></p></td>
<td><p><span data-ttu-id="18f6a-786">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="18f6a-786">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-787">msRTCSIP-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="18f6a-787">msRTCSIP-TrustedServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="18f6a-788">Este atributo é um atributo de valor único que representa o FQDN de um servidor confiável.</span><span class="sxs-lookup"><span data-stu-id="18f6a-788">This attribute is a single-valued attribute that represents the FQDN of a trusted server.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-789">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="18f6a-789">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-790">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="18f6a-790">msRTCSIP-TrustedServerVersion</span></span></p></td>
<td><p><span data-ttu-id="18f6a-791">Este atributo especifica o número de versão de um servidor na lista de servidores confiáveis.</span><span class="sxs-lookup"><span data-stu-id="18f6a-791">This attribute specifies the version number of a server in the trusted server list.</span></span></p>
<p><span data-ttu-id="18f6a-792">Os valores válidos possíveis são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="18f6a-792">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="18f6a-793">NULO: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="18f6a-793">NULL: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="18f6a-794">2: Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="18f6a-794">2: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="18f6a-795">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="18f6a-795">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="18f6a-796">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="18f6a-796">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="18f6a-797">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="18f6a-797">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="18f6a-798">6: Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18f6a-798">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="18f6a-799">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="18f6a-799">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-800">msRTCSIP-TrustedServiceFlags</span><span class="sxs-lookup"><span data-stu-id="18f6a-800">msRTCSIP-TrustedServiceFlags</span></span></p></td>
<td><p><span data-ttu-id="18f6a-801">Este atributo define as opções que são habilitadas para o serviço confiável.</span><span class="sxs-lookup"><span data-stu-id="18f6a-801">This attribute defines the options that are enabled for the trusted service.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-802">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="18f6a-802">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-803">msRTCSIP-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="18f6a-803">msRTCSIP-TrustedServiceLinks</span></span></p></td>
<td><p><span data-ttu-id="18f6a-804">Este atributo com valores múltiplos contém uma lista de nomes diferenciados (DN) que fazem referência a um objeto de serviço confiável, como um serviço de autenticação de retransmissão de mídia.</span><span class="sxs-lookup"><span data-stu-id="18f6a-804">This multi-valued attribute contains a list of distinguished names (DN) that reference a trusted service object, such as a Media Relay Authentication Service.</span></span> <span data-ttu-id="18f6a-805">Um serviço de autenticação de retransmissão de mídia (colocado fisicamente no servidor de borda executando o serviço de conferência A/V) deve estar associado a um pool para dar suporte a cenários de áudio para usuários remotos.</span><span class="sxs-lookup"><span data-stu-id="18f6a-805">A Media Relay Authentication Service (physically collocated on the Edge Server running the A/V Conferencing service) must be associated with a pool to support audio scenarios for remote users.</span></span></p>
<p><span data-ttu-id="18f6a-806">O vínculo inverso correspondente a este atributo de vínculo sequencial é <strong>msRTCSIP-ServerBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="18f6a-806">The corresponding back link to this forward link attribute is <strong>msRTCSIP-ServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-807">UC</span><span class="sxs-lookup"><span data-stu-id="18f6a-807">UC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-808">msRTCSIP-TrustedServicePort</span><span class="sxs-lookup"><span data-stu-id="18f6a-808">msRTCSIP-TrustedServicePort</span></span></p></td>
<td><p><span data-ttu-id="18f6a-809">Este atributo é um número inteiro que define o número da porta usada para se conectar ao serviço GRUU.</span><span class="sxs-lookup"><span data-stu-id="18f6a-809">This attribute is an integer that defines the port number used to connect to this GRUU service.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-810">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-810">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-811">msRTCSIP-TrustedServiceType</span><span class="sxs-lookup"><span data-stu-id="18f6a-811">msRTCSIP-TrustedServiceType</span></span></p></td>
<td><p><span data-ttu-id="18f6a-812">Este atributo é um valor String que define o tipo de serviço GRUU que ele representa.</span><span class="sxs-lookup"><span data-stu-id="18f6a-812">This attribute is a string value that defines the type of GRUU service it represents.</span></span></p>
<p><span data-ttu-id="18f6a-813">Os tipos de serviço válidos do GRUU são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="18f6a-813">The valid GRUU service types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="18f6a-814">MediationServer</span><span class="sxs-lookup"><span data-stu-id="18f6a-814">MediationServer</span></span></p></li>
<li><p><span data-ttu-id="18f6a-815">Gateway</span><span class="sxs-lookup"><span data-stu-id="18f6a-815">Gateway</span></span></p></li>
<li><p><span data-ttu-id="18f6a-816">Serviço de autenticação de retransmissão de mídia (MRAS)</span><span class="sxs-lookup"><span data-stu-id="18f6a-816">Media Relay Authentication Service (MRAS)</span></span></p></li>
<li><p><span data-ttu-id="18f6a-817">QoSM</span><span class="sxs-lookup"><span data-stu-id="18f6a-817">QoSM</span></span></p></li>
<li><p><span data-ttu-id="18f6a-818">msRTCSIP-userextension CWA</span><span class="sxs-lookup"><span data-stu-id="18f6a-818">msRTCSIP-UserExtension CWA</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="18f6a-819">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-819">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-820">msRTCSIP-TrustedWebComponentsServerData</span><span class="sxs-lookup"><span data-stu-id="18f6a-820">msRTCSIP-TrustedWebComponentsServerData</span></span></p></td>
<td><p><span data-ttu-id="18f6a-821">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="18f6a-821">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-822">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-822">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-823">msRTCSIP-TrustedWebComponentsServerFQDN</span><span class="sxs-lookup"><span data-stu-id="18f6a-823">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="18f6a-824">Este atributo é um valor String que contém o FQDN do IIS que executa os serviços Web do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="18f6a-824">This attribute is a string value that contains the FQDN of the IIS running Lync Server Web Services.</span></span> <span data-ttu-id="18f6a-825">Este é um atributo de valor único.</span><span class="sxs-lookup"><span data-stu-id="18f6a-825">This is a single-valued attribute.</span></span> <span data-ttu-id="18f6a-826">O valor válido para cada segmento é 63 caracteres; o valor válido para o FQDN inteiro é de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="18f6a-826">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-827">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-827">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-828">msRTCSIP-UCFlags (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-828">msRTCSIP-UCFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-829">Este atributo define opções de UC diferentes que são habilitadas globalmente para todos os objetos de contato ou usuário.</span><span class="sxs-lookup"><span data-stu-id="18f6a-829">This attribute defines different UC options that are enabled globally to all user or contact objects.</span></span> <span data-ttu-id="18f6a-830">Este atributo é um valor de máscara de bits de tipo inteiro.</span><span class="sxs-lookup"><span data-stu-id="18f6a-830">This attribute is a bit-mask value of integer type.</span></span> <span data-ttu-id="18f6a-831">Cada opção é representada pela presença de um bit.</span><span class="sxs-lookup"><span data-stu-id="18f6a-831">Each option is represented by the presence of a bit.</span></span></p>
<p><span data-ttu-id="18f6a-832">O valor válido possível (e a posição de bit associada) são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="18f6a-832">The possible valid value (and associated bit position) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="18f6a-833">4: UsePerUserUCPolicy (posição de bit 2)</span><span class="sxs-lookup"><span data-stu-id="18f6a-833">4: UsePerUserUCPolicy (bit position 2)</span></span></p></li>
</ul>
<p><span data-ttu-id="18f6a-834">Quando esse bit é definido, a política de UC é definida por usuário.</span><span class="sxs-lookup"><span data-stu-id="18f6a-834">When this bit is set, the UC policy is defined per user.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-835">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-835">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-836">msRTCSIP-UCPolicy (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-836">msRTCSIP-UCPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-837">Este atributo de valor único contém o nome diferenciado (DN) da política de UC que o administrador atribuiu para este usuário.</span><span class="sxs-lookup"><span data-stu-id="18f6a-837">This single-valued attribute contains the distinguished name (DN) of the UC policy that the administrator has assigned for this user.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-838">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-838">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-839">msRTCSIP-userdomainlist (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-839">msRTCSIP-UserDomainList (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="18f6a-840">Este atributo fornece uma lista de todos os domínios em uma floresta que hospedam usuários habilitados para SIP.</span><span class="sxs-lookup"><span data-stu-id="18f6a-840">This attribute provides a list of all the domains in a forest that host SIP-enabled users.</span></span> <span data-ttu-id="18f6a-841">O padrão é uma lista vazia, indicando que todos os domínios na floresta são habilitados para SIP.</span><span class="sxs-lookup"><span data-stu-id="18f6a-841">The default is an empty list, indicating that all domains in the forest are SIP-enabled.</span></span></p>
<p><span data-ttu-id="18f6a-842">Os valores válidos são várias cadeias de caracteres que representam os nomes de domínio de domínios individuais.</span><span class="sxs-lookup"><span data-stu-id="18f6a-842">Valid values are multiple strings representing the domain names of individual domains.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-843">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="18f6a-843">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="18f6a-844">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-844">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-845">msRTCSIP-userhabilitado</span><span class="sxs-lookup"><span data-stu-id="18f6a-845">msRTCSIP-UserEnabled</span></span></p></td>
<td><p><span data-ttu-id="18f6a-846">Este atributo determina se o usuário está atualmente habilitado para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="18f6a-846">This attribute determines whether the user is currently enabled for Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-847">msRTCSIP-userextension</span><span class="sxs-lookup"><span data-stu-id="18f6a-847">msRTCSIP-UserExtension</span></span></p></td>
<td><p><span data-ttu-id="18f6a-848">Este atributo com valores múltiplos contém uma lista de pares nome-valor no formato de &quot;nome = valor. &quot; Este atributo está marcado para replicação de catálogo global.</span><span class="sxs-lookup"><span data-stu-id="18f6a-848">This multi-valued attribute contains a list of name-value pairs in the format of &quot;name=value.&quot; This attribute is marked for global catalog replication.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-849">Novo no Live Communications Server 2005 com SP1.</span><span class="sxs-lookup"><span data-stu-id="18f6a-849">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-850">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="18f6a-850">msRTCSIP-UserLocationProfile</span></span></p></td>
<td><p><span data-ttu-id="18f6a-851">Este atributo contém o nome diferenciado (DN) que aponta para um objeto de perfil de local.</span><span class="sxs-lookup"><span data-stu-id="18f6a-851">This attribute contains the distinguished name (DN) that points to a location profile object.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-852">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="18f6a-852">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-853">msRTCSIP-userpolicies</span><span class="sxs-lookup"><span data-stu-id="18f6a-853">msRTCSIP-UserPolicies</span></span></p></td>
<td><p><span data-ttu-id="18f6a-854">Este atributo armazena pares nome-valor para políticas de usuário.</span><span class="sxs-lookup"><span data-stu-id="18f6a-854">This attribute stores name-value pairs for user policies.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-855">Novo no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="18f6a-855">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-856">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="18f6a-856">msRTCSIP-UserPolicy</span></span></p></td>
<td><p><span data-ttu-id="18f6a-857">Este é um atributo com valores múltiplos contendo uma lista de nomes distintos com binário (DN_WITH_BINARY) apontando para políticas de usuário global de tipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="18f6a-857">This is a multi-valued attribute containing a list of distinguished names with binary (DN_WITH_BINARY) pointing to global user policies of different types.</span></span> <span data-ttu-id="18f6a-858">A parte binária indica o tipo de política para o qual a parte DN aponta.</span><span class="sxs-lookup"><span data-stu-id="18f6a-858">The binary part indicates the type of policy to which the DN portion points.</span></span></p>
<p><span data-ttu-id="18f6a-859">Os valores binários válidos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="18f6a-859">The valid binary values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="18f6a-860">0x00000001: política de reunião</span><span class="sxs-lookup"><span data-stu-id="18f6a-860">0x00000001: Meeting policy</span></span></p></li>
<li><p><span data-ttu-id="18f6a-861">0x00000002: política de UC</span><span class="sxs-lookup"><span data-stu-id="18f6a-861">0x00000002: UC policy</span></span></p></li>
<li><p><span data-ttu-id="18f6a-862">0x00000005: política de presença</span><span class="sxs-lookup"><span data-stu-id="18f6a-862">0x00000005: Presence policy</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="18f6a-863">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-863">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-864">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="18f6a-864">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="18f6a-p165">Este é o ID do grupo de roteamento SIP. Os usuários no mesmo grupo irão ser registrados para o mesmo Servidor de Front-end.</span><span class="sxs-lookup"><span data-stu-id="18f6a-p165">This is the SIP routing group ID. Users in the same group will register to the same Front End Server.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-867">Novo no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="18f6a-867">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-868">msRTCSIP-WebComponentsData</span><span class="sxs-lookup"><span data-stu-id="18f6a-868">msRTCSIP-WebComponentsData</span></span></p></td>
<td><p><span data-ttu-id="18f6a-869">Este é um atributo com vários valores.</span><span class="sxs-lookup"><span data-stu-id="18f6a-869">This is a multi-valued attribute.</span></span> <span data-ttu-id="18f6a-870">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="18f6a-870">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-871">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-871">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-872">msRTCSIP-WebComponentsPoolAddress</span><span class="sxs-lookup"><span data-stu-id="18f6a-872">msRTCSIP-WebComponentsPoolAddress</span></span></p></td>
<td><p><span data-ttu-id="18f6a-873">Esse atributo de valor único aponta para o pool ou servidor Standard Edition ao qual os componentes Web pertencem.</span><span class="sxs-lookup"><span data-stu-id="18f6a-873">This single-valued attribute points to the pool or Standard Edition server to which the web components belong.</span></span></p>
<p><span data-ttu-id="18f6a-874">Link encaminhar: <strong>link ID 11028</strong></span><span class="sxs-lookup"><span data-stu-id="18f6a-874">Forward link: <strong>Link ID 11028</strong></span></span></p>
<p><span data-ttu-id="18f6a-875">O vínculo inverso correspondente a este atributo de vínculo sequencial é <strong>msRTCSIP-WebComponentsServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="18f6a-875">The corresponding back link to this forward link attribute is <strong>msRTCSIP-WebComponentsServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-876">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-876">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-877">msRTCSIP-WebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="18f6a-877">msRTCSIP-WebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="18f6a-878">Este atributo é uma lista de vários valores de nomes distintos.</span><span class="sxs-lookup"><span data-stu-id="18f6a-878">This attribute is a multi-valued list of distinguished names.</span></span> <span data-ttu-id="18f6a-879">Este atributo contém uma lista de todos os servidores Web associados a esse pool.</span><span class="sxs-lookup"><span data-stu-id="18f6a-879">This attribute contains a list of all Web servers associated with this pool.</span></span></p>
<p><span data-ttu-id="18f6a-880">Vínculo inverso: <strong>link ID 11029</strong></span><span class="sxs-lookup"><span data-stu-id="18f6a-880">Back link: <strong>Link ID 11029</strong></span></span></p>
<p><span data-ttu-id="18f6a-881">O vínculo sequencial correspondente a este vínculo inverso é <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="18f6a-881">The corresponding forward link to this back link is <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-882">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="18f6a-882">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-883">msRTCSIP-WMIInstanceId (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="18f6a-883">msRTCSIP-WMIInstanceId (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="18f6a-884">Novo no Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="18f6a-884">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="18f6a-885">Obsoleto no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="18f6a-885">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-886">OtherIPPhone</span><span class="sxs-lookup"><span data-stu-id="18f6a-886">OtherIPPhone</span></span></p></td>
<td><p><span data-ttu-id="18f6a-887">Esse atributo existente do Active Directory é usado por telefonia para especificar a lista de endereços TCP/IP alternativos de um telefone.</span><span class="sxs-lookup"><span data-stu-id="18f6a-887">This existing Active Directory attribute is used by telephony to specify the list of alternate TCP/IP addresses for a phone.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-888">Novo no sistema operacional Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="18f6a-888">New in Windows Server 2008 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-889">PhoneOfficeOther</span><span class="sxs-lookup"><span data-stu-id="18f6a-889">PhoneOfficeOther</span></span></p></td>
<td><p><span data-ttu-id="18f6a-890">Este atributo existente do Active Directory é usado pelos componentes de voz no Lync Server, apenas para objetos de contato, para fins de roteamento de chamadas para o atendedor automático da Unificação de mensagens e os números de acesso do Assinante.</span><span class="sxs-lookup"><span data-stu-id="18f6a-890">This existing Active Directory attribute is used by the voice components in Lync Server, for contact objects only, for the purpose of routing calls to the unified messaging auto-attendant and subscriber access numbers.</span></span> <span data-ttu-id="18f6a-891">O endereço de encaminhamento de chamadas não condicional é armazenado nesse atributo com valores múltiplos.</span><span class="sxs-lookup"><span data-stu-id="18f6a-891">The unconditional call forwarding address is stored in this multi-valued attribute.</span></span> <span data-ttu-id="18f6a-892">Essa conta é criada para a finalidade específica do atendedor automático e acesso ao Assinante.</span><span class="sxs-lookup"><span data-stu-id="18f6a-892">This account is created for the specific purpose of auto-attendant and subscriber access.</span></span> <span data-ttu-id="18f6a-893">Os atributos da conta não devem ser modificados pelos administradores.</span><span class="sxs-lookup"><span data-stu-id="18f6a-893">This account’s attributes should not be modified by administrators.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-894">Novo no sistema operacional Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="18f6a-894">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18f6a-895">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="18f6a-895">ProxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="18f6a-896">Este atributo de múltiplos valores do Active Directory existente é parte do esquema base do Active Directory introduzido no Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="18f6a-896">This existing Active Directory multi-valued attribute is part of the base Active Directory schema introduced in Windows 2000.</span></span> <span data-ttu-id="18f6a-897">Este atributo contém os vários endereços X400, X500 e SMTP do email do usuário.</span><span class="sxs-lookup"><span data-stu-id="18f6a-897">This attribute contains the various X400, X500, and SMTP addresses of the user’s email.</span></span> <span data-ttu-id="18f6a-898">No Live Communications Server 2003 e posterior, o URI do SIP do usuário é adicionado a essa lista, &quot;usando a&quot; marca SIP:.</span><span class="sxs-lookup"><span data-stu-id="18f6a-898">In Live Communications Server 2003 and later, the user’s SIP URI is added to this list, using the &quot;sip:&quot; tag.</span></span></p>
<p><span data-ttu-id="18f6a-899">Os seguintes aplicativos pesquisam o URI do SIP do usuário a partir deste atributo:</span><span class="sxs-lookup"><span data-stu-id="18f6a-899">The following applications search the user’s SIP URI from this attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="18f6a-900">Cliente de mensagens e colaboração do Microsoft Office Outlook 2003</span><span class="sxs-lookup"><span data-stu-id="18f6a-900">Microsoft Office Outlook 2003 messaging and collaboration client</span></span></p></li>
<li><p><span data-ttu-id="18f6a-901">Microsoft Office SharePoint Server 2007</span><span class="sxs-lookup"><span data-stu-id="18f6a-901">Microsoft Office SharePoint Server 2007</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="18f6a-902">Novo no sistema operacional Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="18f6a-902">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18f6a-903">TelephoneNumber</span><span class="sxs-lookup"><span data-stu-id="18f6a-903">TelephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="18f6a-904">Este atributo existente do Active Directory contém o número de telefone do usuário.</span><span class="sxs-lookup"><span data-stu-id="18f6a-904">This existing Active Directory attribute contains the telephone number for the user.</span></span></p></td>
<td><p><span data-ttu-id="18f6a-905">Novo no sistema operacional Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="18f6a-905">New in Windows 2000 operating system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

