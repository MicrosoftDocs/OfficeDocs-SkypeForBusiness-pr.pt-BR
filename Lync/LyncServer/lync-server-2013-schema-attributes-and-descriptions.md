---
title: 'Lync Server 2013: atributos e descrições do esquema'
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
ms.openlocfilehash: 72da4adb0f660604dba7f20c9ddc333425086df2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="f13ab-102">Atributos e descrições de esquema no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f13ab-102">Schema attributes and descriptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f13ab-103">_**Tópico da última modificação:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="f13ab-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="f13ab-104">Esta seção descreve todos os atributos de esquema usados pelo Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f13ab-104">This section describes all the schema attributes used by Lync Server 2013.</span></span> <span data-ttu-id="f13ab-105">Para as classes associadas a atributos, consulte [atributos de esquema por classe no Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="f13ab-105">For the classes associated with attributes, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span> <span data-ttu-id="f13ab-106">Para obter uma lista de classes e atributos que são novos no Lync Server 2013, consulte [mudanças de esquema no Lync server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="f13ab-106">For a list of classes and attributes that are new in Lync Server 2013, see [Schema changes in Lync Server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span></span>

<span data-ttu-id="f13ab-107">Os atributos que são pares vinculados são especificados como links de encaminhamento ou links para trás.</span><span class="sxs-lookup"><span data-stu-id="f13ab-107">Attributes that are linked pairs are specified as forward links or back links.</span></span> <span data-ttu-id="f13ab-108">Um atributo que faz referência a outro objeto é um link de encaminhamento; o atributo do outro objeto que faz referência novamente ao primeiro objeto é um link para trás.</span><span class="sxs-lookup"><span data-stu-id="f13ab-108">An attribute that refers to another object is a forward link; the attribute of the other object that refers back to the first object is a back link.</span></span> <span data-ttu-id="f13ab-109">Os links de encaminhamento são atualizáveis, enquanto links de volta são somente leitura.</span><span class="sxs-lookup"><span data-stu-id="f13ab-109">Forward links are updatable, while back links are read-only.</span></span>

<span data-ttu-id="f13ab-110">Alguns atributos têm um valor de máscara de bits.</span><span class="sxs-lookup"><span data-stu-id="f13ab-110">Some attributes have a bit-mask value.</span></span> <span data-ttu-id="f13ab-111">Para esses atributos, cada configuração é representada por um bit, e o valor decimal exibido representa a posição do bit.</span><span class="sxs-lookup"><span data-stu-id="f13ab-111">For these attributes, each setting is represented by a bit, and the displayed decimal value represents the bit position.</span></span> <span data-ttu-id="f13ab-112">Posições de bit começam com bit 0.</span><span class="sxs-lookup"><span data-stu-id="f13ab-112">Bit positions start with bit 0.</span></span> <span data-ttu-id="f13ab-113">Por exemplo, 1 (binário) é bit 0 definido e 10000 (binário) é um bit 4 definido.</span><span class="sxs-lookup"><span data-stu-id="f13ab-113">For example, 1 (binary) is bit 0 set and 10000 (binary) is bit 4 set.</span></span> <span data-ttu-id="f13ab-114">Cada bit representa uma propriedade.</span><span class="sxs-lookup"><span data-stu-id="f13ab-114">Each bit represents a property.</span></span> <span data-ttu-id="f13ab-115">Veja a seguir alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="f13ab-115">The following are some examples:</span></span>

  - <span data-ttu-id="f13ab-116">10000 (binário) tem um valor decimal de 16 (ou seja, bit 4 é definido).</span><span class="sxs-lookup"><span data-stu-id="f13ab-116">10000 (binary) has a decimal value of 16 (that is, bit 4 is set).</span></span>

  - <span data-ttu-id="f13ab-117">100 milhões (binário) tem um valor decimal de 256 (ou seja, o bit 8 é definido).</span><span class="sxs-lookup"><span data-stu-id="f13ab-117">100000000 (binary) has a decimal value of 256 (that is, bit 8 is set).</span></span>

  - <span data-ttu-id="f13ab-118">1100 (binário) tem um valor decimal de 12 (ou seja, os bits 2 e 3 são definidos; as propriedades representadas por ambos os bits são habilitadas).</span><span class="sxs-lookup"><span data-stu-id="f13ab-118">1100 (binary) has a decimal value of 12 (that is, bits 2 and 3 are set; properties represented by both bits are enabled).</span></span>

  - <span data-ttu-id="f13ab-119">1111000001 (binário) tem um valor decimal de 961 (ou seja, bits 0, 6, 7, 8 e 9 são definidos; as propriedades de cada um desses bits são habilitadas).</span><span class="sxs-lookup"><span data-stu-id="f13ab-119">1111000001 (binary) has a decimal value of 961 (that is, bits 0, 6, 7, 8, and 9 are set; properties for each of these bits are enabled).</span></span>

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a><span data-ttu-id="f13ab-120">Atributos de esquema do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f13ab-120">Schema Attributes for Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f13ab-121">Atributo</span><span class="sxs-lookup"><span data-stu-id="f13ab-121">Attribute</span></span></th>
<th><span data-ttu-id="f13ab-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="f13ab-122">Description</span></span></th>
<th><span data-ttu-id="f13ab-123">Comentários</span><span class="sxs-lookup"><span data-stu-id="f13ab-123">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-124">Atributos</span><span class="sxs-lookup"><span data-stu-id="f13ab-124">dnsHostName</span></span></p></td>
<td><p><span data-ttu-id="f13ab-125">Um atributo existente nos serviços de domínio Active Directory que agora está associado às classes <strong>msRTCSIP-pool</strong> e <strong>msRTCSIP-MonitoringServer</strong> .</span><span class="sxs-lookup"><span data-stu-id="f13ab-125">An existing attribute in Active Directory Domain Services that is now associated with the <strong>msRTCSIP-Pool</strong> and <strong>msRTCSIP-MonitoringServer</strong> classes.</span></span> <span data-ttu-id="f13ab-126">Esse atributo especifica o nome de domínio totalmente qualificado (FQDN) de um pool ou um servidor de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="f13ab-126">This attribute specifies the fully qualified domain name (FQDN) of a pool or Monitoring Server.</span></span></p>
<p><span data-ttu-id="f13ab-127">Um valor válido para cada segmento é de 63 caracteres; um valor válido para o FQDN inteiro é de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="f13ab-127">A valid value for each segment is 63 characters; a valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-128">Novo no Microsoft Office Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="f13ab-128">New in Microsoft Office Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-129">msDS-SourceObjectDN</span><span class="sxs-lookup"><span data-stu-id="f13ab-129">msDS-SourceObjectDN</span></span></p></td>
<td><p><span data-ttu-id="f13ab-130">Esse atributo contém a representação de cadeia de caracteres do nome diferenciado (DN) do objeto em outra floresta que corresponde a esse objeto.</span><span class="sxs-lookup"><span data-stu-id="f13ab-130">This attribute contains the string representation of the distinguished name (DN) of the object in another forest that corresponds to this object.</span></span> <span data-ttu-id="f13ab-131">Esse atributo é usado para expansão do grupo de distribuição e atendimento automático.</span><span class="sxs-lookup"><span data-stu-id="f13ab-131">This attribute is used for distribution group expansion and auto attendance.</span></span> <span data-ttu-id="f13ab-132">Esse atributo é definido no esquema padrão do Active Directory para Windows Server 2003 R2.</span><span class="sxs-lookup"><span data-stu-id="f13ab-132">This attribute is defined in the default Active Directory schema for Windows Server 2003 R2.</span></span></p>
<p><span data-ttu-id="f13ab-133">Para evitar a necessidade de uma atualização do AD DS para o Windows Server 2003 R2, a preparação do esquema do Active Directory estende o esquema do Windows Server 2003 com essa definição de atributo.</span><span class="sxs-lookup"><span data-stu-id="f13ab-133">To avoid requiring an upgrade of AD DS to Windows Server 2003 R2, Active Directory schema preparation extends the Windows Server 2003 schema with this attribute definition.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-134">Novo no Microsoft Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-134">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-135">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="f13ab-135">msExchUCVoiceMailSettings</span></span></p></td>
<td><p><span data-ttu-id="f13ab-136">Esse atributo com vários valores contém as configurações da caixa postal.</span><span class="sxs-lookup"><span data-stu-id="f13ab-136">This multi-valued attribute holds voice mail settings.</span></span> <span data-ttu-id="f13ab-137">Esse atributo é compartilhado com o Exchange Unified Messaging (UM).</span><span class="sxs-lookup"><span data-stu-id="f13ab-137">This attribute is shared with Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="f13ab-138">Novo no Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-138">New in Microsoft Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-139">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="f13ab-139">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="f13ab-140">Esse atributo de vários valores contém identificadores para políticas de retenção que se aplicam ao usuário.</span><span class="sxs-lookup"><span data-stu-id="f13ab-140">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="f13ab-141">As políticas de retenção preservam os itens da caixa de correio para o usuário durante o período de espera.</span><span class="sxs-lookup"><span data-stu-id="f13ab-141">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="f13ab-142">Esse atributo é compartilhado com o Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="f13ab-142">This attribute is shared with Exchange 2013.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-143">Novo no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f13ab-143">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-144">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="f13ab-144">msRTCSIP-AcpInfo</span></span></p></td>
<td><p><span data-ttu-id="f13ab-145">Esse atributo armazena informações do provedor de audioconferência de áudio para um usuário.</span><span class="sxs-lookup"><span data-stu-id="f13ab-145">This attribute stores audio conferencing provider information for a user.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-146">Novo no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-146">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-147">msRTCSIP-ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="f13ab-147">msRTCSIP-ApplicationDestination</span></span></p></td>
<td><p><span data-ttu-id="f13ab-148">Esse atributo aponta para a entrada de serviço confiável do contato do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f13ab-148">This attribute points to the trusted service entry for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-149">Novo no Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f13ab-149">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-150">msRTCSIP-Aplicativolist</span><span class="sxs-lookup"><span data-stu-id="f13ab-150">msRTCSIP-ApplicationList</span></span></p></td>
<td><p><span data-ttu-id="f13ab-151">Esse atributo contém uma lista de aplicativos hospedados no servidor de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="f13ab-151">This attribute contains a list of hosted applications on the application server.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-152">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f13ab-152">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-153">msRTCSIP – ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="f13ab-153">msRTCSIP-ApplicationOptions</span></span></p></td>
<td><p><span data-ttu-id="f13ab-154">Esse atributo especifica as opções para o contato do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f13ab-154">This attribute specifies the options for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-155">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f13ab-155">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-156">msRTCSIP-ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="f13ab-156">msRTCSIP-ApplicationPrimaryLanguage</span></span></p></td>
<td><p><span data-ttu-id="f13ab-157">Esse atributo contém o idioma principal para o contato do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f13ab-157">This attribute contains the primary language for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-158">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f13ab-158">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-159">msRTCSIP-ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="f13ab-159">msRTCSIP-ApplicationSecondaryLanguages</span></span></p></td>
<td><p><span data-ttu-id="f13ab-160">Esse atributo Multiple Value contém os idiomas secundários para o contato do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f13ab-160">This multiple value attribute contains the secondary languages for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-161">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f13ab-161">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-162">msRTCSIP-ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="f13ab-162">msRTCSIP-ApplicationServerBL</span></span></p></td>
<td><p><span data-ttu-id="f13ab-163">Esse atributo contém uma lista de servidores de aplicativos que pertencem a este pool.</span><span class="sxs-lookup"><span data-stu-id="f13ab-163">This attribute contains a list of application servers that belong to this pool.</span></span> <span data-ttu-id="f13ab-164">O link encaminhamento correspondente a este atributo de link regressivo é <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span><span class="sxs-lookup"><span data-stu-id="f13ab-164">The corresponding forward link to this back link attribute is <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-165">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f13ab-165">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-166">msRTCSIP-ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="f13ab-166">msRTCSIP-ApplicationServerPoolLink</span></span></p></td>
<td><p><span data-ttu-id="f13ab-167">Esse atributo aponta para o pool ao qual esse servidor de aplicativos pertence.</span><span class="sxs-lookup"><span data-stu-id="f13ab-167">This attribute points to the pool to which this application server belongs.</span></span> <span data-ttu-id="f13ab-168">Este é o link encaminhar.</span><span class="sxs-lookup"><span data-stu-id="f13ab-168">This is the forward link.</span></span> <span data-ttu-id="f13ab-169">O link regressivo correspondente é <strong>msRTCSIP-ApplicationServerBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="f13ab-169">The corresponding backward link is <strong>msRTCSIP-ApplicationServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-170">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f13ab-170">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-171">msRTCSIP-ArchiveDefault (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-171">msRTCSIP-ArchiveDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="f13ab-172">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="f13ab-172">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="f13ab-173">Obsoleto no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-173">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-174">msRTCSIP-ArchiveDefaultFlags (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-174">msRTCSIP-ArchiveDefaultFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-175">Esse atributo especifica o padrão global dentro do limite da floresta para arquivar todas as comunicações do usuário.</span><span class="sxs-lookup"><span data-stu-id="f13ab-175">This attribute specifies the global default within the forest boundary for archiving all user communications.</span></span> <span data-ttu-id="f13ab-176">Isso é imposto pela camada do agente de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="f13ab-176">This is enforced by the archiving agent layer.</span></span> <span data-ttu-id="f13ab-177">O intervalo de valores para esse atributo é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f13ab-177">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="f13ab-178"><strong>True</strong>: arquivar todos os usuários</span><span class="sxs-lookup"><span data-stu-id="f13ab-178"><strong>TRUE</strong>: Archive all users</span></span></p></li>
<li><p><span data-ttu-id="f13ab-179"><strong>False</strong>: Não arquivar todos os usuários</span><span class="sxs-lookup"><span data-stu-id="f13ab-179"><strong>FALSE</strong>: Do not archive all users</span></span></p></li>
</ul>
<p><span data-ttu-id="f13ab-180">Esse atributo controla globalmente, dentro do limite da floresta, como as comunicações do usuário em uma rede interna são arquivadas.</span><span class="sxs-lookup"><span data-stu-id="f13ab-180">This attribute globally controls, within the forest boundary, how user communications within an internal network are archived.</span></span></p>
<p><span data-ttu-id="f13ab-181"><strong>Comportamento do Live Communications Server 2005 (agora desativado)</strong></span><span class="sxs-lookup"><span data-stu-id="f13ab-181"><strong>Live Communications Server 2005 behavior (now retired)</strong></span></span></p>
<p><span data-ttu-id="f13ab-182">O intervalo de valores para esse atributo é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f13ab-182">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="f13ab-183">0: arquivar o corpo da mensagem [bit 0]</span><span class="sxs-lookup"><span data-stu-id="f13ab-183">0: Archive the message body [bit 0]</span></span></p></li>
<li><p><span data-ttu-id="f13ab-184">1: Não arquivar o corpo da mensagem [bit 0]</span><span class="sxs-lookup"><span data-stu-id="f13ab-184">1: Do not archive the message body [bit 0]</span></span></p></li>
</ul>
<p><span data-ttu-id="f13ab-185"><strong>Comportamento do Office Communications Server 2007</strong></span><span class="sxs-lookup"><span data-stu-id="f13ab-185"><strong>Office Communications Server 2007 behavior</strong></span></span></p>
<p><span data-ttu-id="f13ab-186">O intervalo de valores para esse atributo é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f13ab-186">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="f13ab-187">0: ArchiveFederationDefaultWithoutBody (desativado)</span><span class="sxs-lookup"><span data-stu-id="f13ab-187">0: ArchiveFederationDefaultWithoutBody (retired)</span></span></p></li>
<li><p><span data-ttu-id="f13ab-188">1-2: ArchiveInternalCommunications</span><span class="sxs-lookup"><span data-stu-id="f13ab-188">1-2: ArchiveInternalCommunications</span></span></p></li>
<li><p><span data-ttu-id="f13ab-189">3-4: ArchiveFederatedCommunications</span><span class="sxs-lookup"><span data-stu-id="f13ab-189">3-4: ArchiveFederatedCommunications</span></span></p></li>
<li><p><span data-ttu-id="f13ab-190">5: RecordPresenceRegistrations</span><span class="sxs-lookup"><span data-stu-id="f13ab-190">5: RecordPresenceRegistrations</span></span></p></li>
<li><p><span data-ttu-id="f13ab-191">6: RecordIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="f13ab-191">6: RecordIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="f13ab-192">7: RecordGroupIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="f13ab-192">7: RecordGroupIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="f13ab-193">8: RecordFileTransferInstances</span><span class="sxs-lookup"><span data-stu-id="f13ab-193">8: RecordFileTransferInstances</span></span></p></li>
<li><p><span data-ttu-id="f13ab-194">9: RecordAudioCallDetails</span><span class="sxs-lookup"><span data-stu-id="f13ab-194">9: RecordAudioCallDetails</span></span></p></li>
<li><p><span data-ttu-id="f13ab-195">10: RecordVideoCallDetails</span><span class="sxs-lookup"><span data-stu-id="f13ab-195">10: RecordVideoCallDetails</span></span></p></li>
<li><p><span data-ttu-id="f13ab-196">11: RecordRemoteAssistanceCallDetails</span><span class="sxs-lookup"><span data-stu-id="f13ab-196">11: RecordRemoteAssistanceCallDetails</span></span></p></li>
<li><p><span data-ttu-id="f13ab-197">12: RecordApplicationSharingDetails</span><span class="sxs-lookup"><span data-stu-id="f13ab-197">12: RecordApplicationSharingDetails</span></span></p></li>
<li><p><span data-ttu-id="f13ab-198">13: RecordMeetingInstantiations</span><span class="sxs-lookup"><span data-stu-id="f13ab-198">13: RecordMeetingInstantiations</span></span></p></li>
<li><p><span data-ttu-id="f13ab-199">14: RecordMeetingJoins</span><span class="sxs-lookup"><span data-stu-id="f13ab-199">14: RecordMeetingJoins</span></span></p></li>
<li><p><span data-ttu-id="f13ab-200">15: RecordDataJoins</span><span class="sxs-lookup"><span data-stu-id="f13ab-200">15: RecordDataJoins</span></span></p></li>
<li><p><span data-ttu-id="f13ab-201">16: RecordAVJoins</span><span class="sxs-lookup"><span data-stu-id="f13ab-201">16: RecordAVJoins</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f13ab-202">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="f13ab-202">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="f13ab-203">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-203">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-204">msRTCSIP-ArchiveFederationDefault (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-204">msRTCSIP-ArchiveFederationDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="f13ab-205">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="f13ab-205">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="f13ab-206">Obsoleto no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-206">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-207">msRTCSIP-ArchiveFederationDefaultFlags (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-207">msRTCSIP-ArchiveFederationDefaultFlags (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="f13ab-208">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="f13ab-208">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="f13ab-209">Obsoleto no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-209">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-210">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="f13ab-210">msRTCSIP-ArchivingEnabled</span></span></p></td>
<td><p><span data-ttu-id="f13ab-211">Esse atributo é um inteiro usado como um campo de bits para controlar se as comunicações de um único usuário devem ser arquivadas.</span><span class="sxs-lookup"><span data-stu-id="f13ab-211">This attribute is an integer used as a bit field to control whether a single user’s communications are to be archived.</span></span> <span data-ttu-id="f13ab-212">Esse controle é imposto pela camada do agente de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="f13ab-212">This control is enforced by the archiving agent layer.</span></span> <span data-ttu-id="f13ab-213">Ele está marcado para replicação de catálogo global.</span><span class="sxs-lookup"><span data-stu-id="f13ab-213">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="f13ab-214">O escopo desse atributo é específico para um único usuário ou contato.</span><span class="sxs-lookup"><span data-stu-id="f13ab-214">The scope of this attribute is specific to a single user or contact.</span></span> <span data-ttu-id="f13ab-215">Os valores válidos (e posições de bit associadas) do Lync Server são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="f13ab-215">The valid values (and associated bit positions) in Lync Server are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="f13ab-216">0: Não arquivar (nenhum conjunto de bits)</span><span class="sxs-lookup"><span data-stu-id="f13ab-216">0: Do not archive (no bit set)</span></span></p></li>
<li><p><span data-ttu-id="f13ab-217">1: desativado (posição do bit 0)</span><span class="sxs-lookup"><span data-stu-id="f13ab-217">1: Retired (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="f13ab-218">2: desativado (posição do bit 1)</span><span class="sxs-lookup"><span data-stu-id="f13ab-218">2: Retired (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="f13ab-219">4: Arquivar comunicações internas (posição do bit 2)</span><span class="sxs-lookup"><span data-stu-id="f13ab-219">4: Archive internal communications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="f13ab-220">8: Arquivar comunicações federadas (posição de bit 3)</span><span class="sxs-lookup"><span data-stu-id="f13ab-220">8: Archive federated communications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="f13ab-221">Os valores válidos anteriormente no Live Communications Server 2005 são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="f13ab-221">Previously valid values in Live Communications Server 2005 are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="f13ab-222">0: Use o valor padrão definido por <strong>msRTCSIP-ArchiveDefault</strong> e <strong>msRTCSIP-ArchiveFederation</strong> nesta ordem de precedência:</span><span class="sxs-lookup"><span data-stu-id="f13ab-222">0:Use the default value defined by <strong>msRTCSIP-ArchiveDefault</strong> and <strong>msRTCSIP-ArchiveFederation</strong> in this order of precedence:</span></span></p>
<ul>
<li><p><span data-ttu-id="f13ab-223">1: arquivo morto</span><span class="sxs-lookup"><span data-stu-id="f13ab-223">1: Archive</span></span></p></li>
<li><p><span data-ttu-id="f13ab-224">2: Não arquivar</span><span class="sxs-lookup"><span data-stu-id="f13ab-224">2: Do not archive</span></span></p></li>
<li><p><span data-ttu-id="f13ab-225">3: arquivar sem o corpo da mensagem</span><span class="sxs-lookup"><span data-stu-id="f13ab-225">3: Archive without the message body</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="f13ab-226">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="f13ab-226">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-227">msRTCSIP-ArchivingServerData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-227">msRTCSIP-ArchivingServerData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-228">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="f13ab-228">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-229">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-229">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-230">msRTCSIP-ArchivingServerVersion (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-230">msRTCSIP-ArchivingServerVersion (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-231">Esse atributo define a versão do serviço de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="f13ab-231">This attribute defines the version of the Archiving service.</span></span> <span data-ttu-id="f13ab-232">Esse atributo é um tipo de inteiro que aumenta o monotonously que aumenta com cada lançamento oficial do produto.</span><span class="sxs-lookup"><span data-stu-id="f13ab-232">This attribute is a monotonously increasing integer type that increments with each official product release.</span></span> <span data-ttu-id="f13ab-233">Os valores válidos possíveis são:</span><span class="sxs-lookup"><span data-stu-id="f13ab-233">The possible valid values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="f13ab-234">Indefinido: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="f13ab-234">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="f13ab-235">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="f13ab-235">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="f13ab-236">                 Live Communications Server 2005 com SP1</span><span class="sxs-lookup"><span data-stu-id="f13ab-236">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="f13ab-237">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="f13ab-237">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="f13ab-238">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="f13ab-238">4: Office Communications Server 2007 R2</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f13ab-239">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-239">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="f13ab-240">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-240">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-241">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="f13ab-241">msRTCSIP-BackEndServer</span></span></p></td>
<td><p><span data-ttu-id="f13ab-242">Esse atributo especifica o FQDN do servidor back-end do pool.</span><span class="sxs-lookup"><span data-stu-id="f13ab-242">This attribute specifies the FQDN of the Back End Server of the pool.</span></span> <span data-ttu-id="f13ab-243">Como só pode haver um único servidor back-end por pool, esse é um atributo de valor único.</span><span class="sxs-lookup"><span data-stu-id="f13ab-243">Because there can only be a single Back End Server per pool, this is a single-valued attribute.</span></span></p>
<p><span data-ttu-id="f13ab-244">O valor válido para cada segmento é de 63 caracteres; o valor válido para o FQDN inteiro é de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="f13ab-244">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-245">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="f13ab-245">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-246">msRTCSIP-ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="f13ab-246">msRTCSIP-ConferenceDirectoryHomePool</span></span></p></td>
<td><p><span data-ttu-id="f13ab-247">Esse atributo contém o identificador do pool que hospeda o diretório de conferências.</span><span class="sxs-lookup"><span data-stu-id="f13ab-247">This attribute contains the identifier of the pool that hosts the conference directory.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-248">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f13ab-248">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-249">msRTCSIP-ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="f13ab-249">msRTCSIP-ConferenceDirectoryId</span></span></p></td>
<td><p><span data-ttu-id="f13ab-250">Esse atributo contém o identificador de um diretório de conferências.</span><span class="sxs-lookup"><span data-stu-id="f13ab-250">This attribute contains the identifier of a conference directory.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-251">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f13ab-251">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-252">msRTCSIP-ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="f13ab-252">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p></td>
<td><p><span data-ttu-id="f13ab-253">Esse atributo contém o identificador do pool ao qual o diretório de conferências está sendo movido.</span><span class="sxs-lookup"><span data-stu-id="f13ab-253">This attribute contains the identifier of the pool to which the conference directory is being moved.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-254">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f13ab-254">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-255">msRTCSIP-padrão</span><span class="sxs-lookup"><span data-stu-id="f13ab-255">msRTCSIP-Default</span></span></p></td>
<td><p><span data-ttu-id="f13ab-256">Esse atributo booliano define se o uso do telefone é um uso padrão.</span><span class="sxs-lookup"><span data-stu-id="f13ab-256">This Boolean attribute defines whether the phone usage is a default usage.</span></span> <span data-ttu-id="f13ab-257">Se esse atributo estiver definido como <strong>true</strong>, o uso do telefone será um uso padrão e não poderá ser excluído pelo administrador.</span><span class="sxs-lookup"><span data-stu-id="f13ab-257">If this attribute is set to <strong>TRUE</strong>, the phone usage is a default usage and cannot be deleted by the administrator.</span></span> <span data-ttu-id="f13ab-258">Se esse atributo estiver definido como <strong>false</strong>, o uso poderá ser excluído.</span><span class="sxs-lookup"><span data-stu-id="f13ab-258">If this attribute is set to <strong>FALSE</strong>, the usage can be deleted.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-259">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-259">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-260">msRTCSIP-DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="f13ab-260">msRTCSIP-DefaultCWAExternalURL</span></span></p></td>
<td><p><span data-ttu-id="f13ab-261">Esse atributo identifica a URL do Communicator Web Access para usuários que estão fora da organização.</span><span class="sxs-lookup"><span data-stu-id="f13ab-261">This attribute identifies the Communicator Web Access URL for users who are outside the organization.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-262">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f13ab-262">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-263">msRTCSIP-DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="f13ab-263">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
<td><p><span data-ttu-id="f13ab-264">Esse atributo identifica a URL do Communicator Web Access para os usuários que estão dentro da organização.</span><span class="sxs-lookup"><span data-stu-id="f13ab-264">This attribute identifies the Communicator Web Access URL for users who are inside the organization.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-265">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f13ab-265">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-266">msRTCSIP-DefaultLocationProfileLink (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-266">msRTCSIP-DefaultLocationProfileLink (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-267">Esse atributo com valor único contém o nome diferenciado (DN) de um objeto de classe de perfil de localização atribuído a ele.</span><span class="sxs-lookup"><span data-stu-id="f13ab-267">This single-valued attribute contains the distinguished name (DN) of a location profile class object assigned to it.</span></span></p>
<p><span data-ttu-id="f13ab-268">Link encaminhar: <strong>ID do link 11036</strong></span><span class="sxs-lookup"><span data-stu-id="f13ab-268">Forward link: <strong>Link ID 11036</strong></span></span></p>
<p><span data-ttu-id="f13ab-269">O link regressivo correspondente é <strong>msRTCSIP-ServerReferenceBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="f13ab-269">The corresponding backward link is <strong>msRTCSIP-ServerReferenceBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-270">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-270">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-271">msRTCSIP-DefaultPolicy (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-271">msRTCSIP-DefaultPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-272">Esse atributo booliano especifica se a política é uma política padrão.</span><span class="sxs-lookup"><span data-stu-id="f13ab-272">This Boolean attribute specifies whether the policy is a default policy.</span></span> <span data-ttu-id="f13ab-273">A política é uma política padrão quando definida como <strong>true</strong>.</span><span class="sxs-lookup"><span data-stu-id="f13ab-273">The policy is a default policy when set to <strong>TRUE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-274">Novo no Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="f13ab-274">New in Office Communications Server 2007</span></span></p>
<p><span data-ttu-id="f13ab-275">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-275">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-276">msRTCSIP-DefaultRouteToEdgeProxy (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-276">msRTCSIP-DefaultRouteToEdgeProxy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-277">Esse atributo especifica o FQDN do servidor de borda que executa o serviço de borda de acesso, se ele puder ser acessado diretamente ou do balanceador de carga de hardware para um pool de servidores que executam o serviço de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="f13ab-277">This attribute specifies the FQDN of either the Edge Server running the Access Edge service, if it can be accessed directly, or of the hardware load balancer for a pool of servers running Access Edge service.</span></span> <span data-ttu-id="f13ab-278">Se os servidores que executam o serviço de borda de acesso só puderem ser acessados por meio de um ou mais directors, esse atributo especificará o FQDN e, opcionalmente, o número da porta do diretor ou do balanceador de carga de hardware que serve um pool de directors.</span><span class="sxs-lookup"><span data-stu-id="f13ab-278">If the servers running Access Edge service can be accessed only through one or more Directors, this attribute specifies the FQDN and, optionally, the port number of the Director or of the hardware load balancer serving a Director pool.</span></span></p>
<p><span data-ttu-id="f13ab-279">O valor válido para cada segmento é de 63 caracteres; o valor válido para o FQDN inteiro é de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="f13ab-279">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-280">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="f13ab-280">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="f13ab-281">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-281">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-282">msRTCSIP-DefaultRouteToEdgeProxyPort (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-282">msRTCSIP-DefaultRouteToEdgeProxyPort (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-283">Esse atributo representa o número da porta que deve ser usado para conexão com o serviço de borda de acesso do servidor que está executando.</span><span class="sxs-lookup"><span data-stu-id="f13ab-283">This attribute represents the port number that should be used to connect to the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="f13ab-284">O valor válido é um valor inteiro que especifica a porta a ser usada.</span><span class="sxs-lookup"><span data-stu-id="f13ab-284">The valid value is an integer value specifying the port to be used.</span></span> <span data-ttu-id="f13ab-285">O valor padrão é 5061.</span><span class="sxs-lookup"><span data-stu-id="f13ab-285">The default value is 5061.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-286">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="f13ab-286">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="f13ab-287">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-287">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-288">msRTCSIP-DefPresenceSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-288">msRTCSIP-DefPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-289">Esse atributo representa o período de tempo limite da assinatura de presença padrão.</span><span class="sxs-lookup"><span data-stu-id="f13ab-289">This attribute represents the default presence subscription time-out period.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-290">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-290">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-291">msRTCSIP-DefRegistrationTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-291">msRTCSIP-DefRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-292">Esse atributo representa a janela de tempo limite de registro padrão.</span><span class="sxs-lookup"><span data-stu-id="f13ab-292">This attribute represents the default registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-293">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-293">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-294">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-294">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-295">Esse atributo representa a janela de tempo limite de assinatura de dados de roaming padrão.</span><span class="sxs-lookup"><span data-stu-id="f13ab-295">This attribute represents the default roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-296">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-296">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-297">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="f13ab-297">msRTCSIP-DeploymentLocator</span></span></p></td>
<td><p><span data-ttu-id="f13ab-298">Esse atributo é usado em uma topologia de domínio dividido e contém um FQDN (nome de domínio totalmente qualificado).</span><span class="sxs-lookup"><span data-stu-id="f13ab-298">This attribute is used in a split domain topology and contains a fully qualified domain name (FQDN).</span></span></p></td>
<td><p><span data-ttu-id="f13ab-299">Novo no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-299">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-300">msRTCSIP-Descrição (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-300">msRTCSIP-Description (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-301">Este atributo de cadeia de caracteres UNICODE com valor único contém uma descrição amigável da regra de normalização ou rota telefônica.</span><span class="sxs-lookup"><span data-stu-id="f13ab-301">This single-valued UNICODE string attribute contains a friendly description of this phone route or normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-302">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-302">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="f13ab-303">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-303">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-304">msRTCSIP-DomainData</span><span class="sxs-lookup"><span data-stu-id="f13ab-304">msRTCSIP-DomainData</span></span></p></td>
<td><p><span data-ttu-id="f13ab-305">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="f13ab-305">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-306">msRTCSIP-DomainName</span><span class="sxs-lookup"><span data-stu-id="f13ab-306">msRTCSIP-DomainName</span></span></p></td>
<td><p><span data-ttu-id="f13ab-307">Esse atributo representa um domínio configurado para o registrador.</span><span class="sxs-lookup"><span data-stu-id="f13ab-307">This attribute represents a domain configured for the Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-308">msRTCSIP-EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="f13ab-308">msRTCSIP-EdgeProxyData</span></span></p></td>
<td><p><span data-ttu-id="f13ab-309">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="f13ab-309">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-310">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="f13ab-310">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-311">msRTCSIP-EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="f13ab-311">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="f13ab-312">Esse atributo especifica o FQDN do serviço de borda de acesso do servidor que está executando.</span><span class="sxs-lookup"><span data-stu-id="f13ab-312">This attribute specifies the FQDN of the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="f13ab-313">O valor válido para cada segmento é de 63 caracteres; o valor válido para o FQDN inteiro é de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="f13ab-313">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-314">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="f13ab-314">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-315">msRTCSIP-EnableBestEffortNotify (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-315">msRTCSIP-EnableBestEffortNotify (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-316">Esse atributo controla se um servidor gera uma solicitação de notificação de melhor esforço (enviar notificação), em vez de uma solicitação de notificação, em resposta a uma solicitação de assinatura de um cliente.</span><span class="sxs-lookup"><span data-stu-id="f13ab-316">This attribute controls whether a server generates a Best Effort NOTIFY (BENOTIFY) request, instead of a NOTIFY request, in response to a SUBSCRIBE request from a client.</span></span> <span data-ttu-id="f13ab-317">Mynotify é uma extensão de aprimoramento do desempenho para o handshake de notificação de assinatura em que o servidor gera solicitações de notificação de notificação, em vez de solicitações regulares de notificação.</span><span class="sxs-lookup"><span data-stu-id="f13ab-317">BENOTIFY is a performance-enhancing extension to the subscribe notification handshake where the server generates BENOTIFY requests, instead of regular NOTIFY requests.</span></span> <span data-ttu-id="f13ab-318">O benefício do desempenho é que uma solicitação de notificação não requer uma resposta de 200 OK do cliente, pois a solicitação de notificação faz.</span><span class="sxs-lookup"><span data-stu-id="f13ab-318">The performance benefit is that a BENOTIFY request does not require a 200 OK response from the client as the NOTIFY request does.</span></span></p>
<p><span data-ttu-id="f13ab-319">Os valores válidos são <strong>true</strong> ou <strong>false</strong>.</span><span class="sxs-lookup"><span data-stu-id="f13ab-319">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="f13ab-320">O Live Communications Server 2003 não oferece suporte a solicitações de notificação de notificação.</span><span class="sxs-lookup"><span data-stu-id="f13ab-320">Live Communications Server 2003 does not support BENOTIFY requests.</span></span> <span data-ttu-id="f13ab-321">Para interoperar com os aplicativos do servidor escritos com a API do servidor do Live Communications Server 2003 em execução no Live Communications Server 2005 e em servidores de terceiros, as solicitações de notificação podem ser desabilitadas definindo seu valor como <STRONG>false</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="f13ab-321">To interoperate with server applications written with the Live Communications Server 2003 server API running on Live Communications Server 2005 and third-party servers, BENOTIFY requests can be disabled by setting its value to <STRONG>FALSE</STRONG>.</span></span> <span data-ttu-id="f13ab-322">Mynotify não faz parte do processo de padronização SIP do IETF (Internet Engineering Task Force).</span><span class="sxs-lookup"><span data-stu-id="f13ab-322">BENOTIFY is not currently part of the IETF (Internet Engineering Task Force) SIP standardization process.</span></span>


</div></td>
<td><p><span data-ttu-id="f13ab-323">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="f13ab-323">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="f13ab-324">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-324">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-325">msRTCSIP-EnableFederation (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-325">msRTCSIP-EnableFederation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-326">Esse atributo é uma opção global que os administradores de ti usam para configurar se os usuários têm permissão para se comunicar com usuários de outras organizações.</span><span class="sxs-lookup"><span data-stu-id="f13ab-326">This attribute is a global switch that IT administrators use to configure whether users are allowed to communicate with users from other organizations.</span></span> <span data-ttu-id="f13ab-327">Ele permite que um administrador substitua o atributo <strong>FederationEnabled</strong> de um usuário individual.</span><span class="sxs-lookup"><span data-stu-id="f13ab-327">It enables an administrator to overwrite an individual user’s <strong>FederationEnabled</strong> attribute.</span></span> <span data-ttu-id="f13ab-328">Esse atributo pode ser útil para ajudar a proteger a rede interna de ataques pela Internet que podem ser causados por worms, vírus ou ataques direcionados à empresa.</span><span class="sxs-lookup"><span data-stu-id="f13ab-328">This attribute can be useful to help protect the internal network from Internet attacks that may be caused by worms, viruses, or targeted attacks on the company.</span></span></p>
<p><span data-ttu-id="f13ab-329">Os valores válidos (e posições de bit associadas) são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="f13ab-329">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="f13ab-330">1: habilitado para conectividade de IM pública (posição do bit 0)</span><span class="sxs-lookup"><span data-stu-id="f13ab-330">1: Enabled for public IM connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="f13ab-331">2: reservado (posição do bit 1)</span><span class="sxs-lookup"><span data-stu-id="f13ab-331">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="f13ab-332">4: reservado (posição do bit 2)</span><span class="sxs-lookup"><span data-stu-id="f13ab-332">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="f13ab-333">8: reservado (posição do bit 3)</span><span class="sxs-lookup"><span data-stu-id="f13ab-333">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="f13ab-334">16: controle de chamada remota habilitado [telefonia] (posição de bit 4)</span><span class="sxs-lookup"><span data-stu-id="f13ab-334">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="f13ab-335">64: AllowOrganizeMeetingWithAnonymousParticipants (permite que os usuários convidem usuários anônimos para reuniões (posição de bit 6)</span><span class="sxs-lookup"><span data-stu-id="f13ab-335">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="f13ab-336">128: UCEnabled (habilitar usuários para comunicação unificada) (posição de bit 7)</span><span class="sxs-lookup"><span data-stu-id="f13ab-336">128: UCEnabled (enable users for unified communications) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="f13ab-337">256: EnabledForEnhancedPresence (habilitar usuário para conectividade de IM pública) (posição de bit 8)</span><span class="sxs-lookup"><span data-stu-id="f13ab-337">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="f13ab-338">512: RemoteCallControlDualMode (posição do bit 9)</span><span class="sxs-lookup"><span data-stu-id="f13ab-338">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f13ab-339">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="f13ab-339">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="f13ab-340">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-340">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-341">msRTCSIP-EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="f13ab-341">msRTCSIP-EnterpriseServices</span></span></p></td>
<td><p><span data-ttu-id="f13ab-342">Esse atributo indica se os serviços corporativos são carregados em determinado servidor.</span><span class="sxs-lookup"><span data-stu-id="f13ab-342">This attribute indicates whether the Enterprise Services are loaded on the given server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-343">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="f13ab-343">msRTCSIP-ExtensionData</span></span></p></td>
<td><p><span data-ttu-id="f13ab-344">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="f13ab-344">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-345">msRTCSIP-ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="f13ab-345">msRTCSIP-ExternalAccessCode</span></span></p></td>
<td><p><span data-ttu-id="f13ab-346">Esse atributo contém o código de discagem para acesso externo.</span><span class="sxs-lookup"><span data-stu-id="f13ab-346">This attribute contains the dial code for external access.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-347">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f13ab-347">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-348">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="f13ab-348">msRTCSIP-FederationEnabled</span></span></p></td>
<td><p><span data-ttu-id="f13ab-349">Esse atributo controla se um único usuário está habilitado para Federação.</span><span class="sxs-lookup"><span data-stu-id="f13ab-349">This attribute controls whether a single user is enabled for federation.</span></span> <span data-ttu-id="f13ab-350">Ela é imposta pela camada de serviços corporativos.</span><span class="sxs-lookup"><span data-stu-id="f13ab-350">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="f13ab-351">Ele está marcado para replicação de catálogo global.</span><span class="sxs-lookup"><span data-stu-id="f13ab-351">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="f13ab-352">Os valores válidos são <strong>true</strong> ou <strong>false</strong>.</span><span class="sxs-lookup"><span data-stu-id="f13ab-352">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-353">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="f13ab-353">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-354">msRTCSIP-FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="f13ab-354">msRTCSIP-FrontEndServers</span></span></p></td>
<td><p><span data-ttu-id="f13ab-355">Esse atributo é uma lista de vários valores dos nomes de domínio de todos os servidores Enterprise Edition associados a um pool.</span><span class="sxs-lookup"><span data-stu-id="f13ab-355">This attribute is a multi-valued list of the domain names of all Enterprise Edition servers associated with a pool.</span></span></p>
<p><span data-ttu-id="f13ab-356">Link para trás: <strong>ID do link 11023</strong></span><span class="sxs-lookup"><span data-stu-id="f13ab-356">Back link: <strong>Link ID 11023</strong></span></span></p>
<p><span data-ttu-id="f13ab-357">O link encaminhamento correspondente para esse link regressivo é <strong>msRTCSIP-PoolAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="f13ab-357">The corresponding forward link to this back link is <strong>msRTCSIP-PoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-358">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="f13ab-358">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-359">msRTCSIP-gateways (obsoletos)</span><span class="sxs-lookup"><span data-stu-id="f13ab-359">msRTCSIP-Gateways (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-360">Este atributo de cadeia de caracteres de múltiplos valores contém uma lista de gateways e portas (por gateway).</span><span class="sxs-lookup"><span data-stu-id="f13ab-360">This multi-valued string attribute contains a list of gateways and ports (per gateway).</span></span></p></td>
<td><p><span data-ttu-id="f13ab-361">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-361">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-362">msRTCSIP-GlobalSettingsData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-362">msRTCSIP-GlobalSettingsData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-363">Esse atributo armazena nomes de valor: pares de valores.</span><span class="sxs-lookup"><span data-stu-id="f13ab-363">This attribute stores name:value pairs.</span></span> <span data-ttu-id="f13ab-364">O par de nomes já definido: é para a configuração <strong>permitir sondagem para presença</strong> .</span><span class="sxs-lookup"><span data-stu-id="f13ab-364">The already-defined name:value pair is for the <strong>allow polling for presence</strong> setting.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-365">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-365">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-366">msRTCSIP-Groupingid</span><span class="sxs-lookup"><span data-stu-id="f13ab-366">msRTCSIP-GroupingID</span></span></p></td>
<td><p><span data-ttu-id="f13ab-367">Esse atributo é um identificador exclusivo de um grupo usado para agrupar entradas do catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="f13ab-367">This attribute is a unique identifier of a group that is used to group address book entries.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-368">Novo no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-368">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-369">msRTCSIP-HomeServer (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-369">msRTCSIP-HomeServer (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="f13ab-370">Novo no Live Communications Server 2003 (não usado).</span><span class="sxs-lookup"><span data-stu-id="f13ab-370">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="f13ab-371">Obsoleto no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="f13ab-371">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-372">msRTCSIP-HomeServerString (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-372">msRTCSIP-HomeServerString (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="f13ab-373">Novo no Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="f13ab-373">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="f13ab-374">Obsoleto no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="f13ab-374">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-375">msRTCSIP-HomeUsers (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-375">msRTCSIP-HomeUsers (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="f13ab-376">Novo no Live Communications Server 2003 (não usado).</span><span class="sxs-lookup"><span data-stu-id="f13ab-376">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="f13ab-377">Obsoleto no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="f13ab-377">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-378">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="f13ab-378">msRTCSIP-InternetAccessEnabled</span></span></p></td>
<td><p><span data-ttu-id="f13ab-379">Esse atributo controla se um único usuário está habilitado para o acesso de usuário externo.</span><span class="sxs-lookup"><span data-stu-id="f13ab-379">This attribute controls whether a single user is enabled for outside user access.</span></span> <span data-ttu-id="f13ab-380">Ela é imposta pela camada de serviços corporativos.</span><span class="sxs-lookup"><span data-stu-id="f13ab-380">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="f13ab-381">Ele está marcado para replicação de catálogo global.</span><span class="sxs-lookup"><span data-stu-id="f13ab-381">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="f13ab-382">Os valores válidos são <strong>true</strong> ou <strong>false</strong>.</span><span class="sxs-lookup"><span data-stu-id="f13ab-382">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-383">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="f13ab-383">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-384">msRTCSIP-IsMaster (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-384">msRTCSIP-IsMaster (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="f13ab-385">Novo no Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="f13ab-385">New in Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="f13ab-386">Obsoleto no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="f13ab-386">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-387">Linha de msRTCSIP</span><span class="sxs-lookup"><span data-stu-id="f13ab-387">msRTCSIP-Line</span></span></p></td>
<td><p><span data-ttu-id="f13ab-388">Esse atributo com valor único contém a ID do dispositivo (o URI SIP ou o URI do TEL do telefone que o usuário controla) usado pelo Lync para telefonia.</span><span class="sxs-lookup"><span data-stu-id="f13ab-388">This single-valued attribute contains the device ID (either the SIP URI or the TEL URI of the phone the user controls) used by Lync for telephony.</span></span> <span data-ttu-id="f13ab-389">Esse atributo está marcado para replicação de catálogo global e está indexado.</span><span class="sxs-lookup"><span data-stu-id="f13ab-389">This attribute is marked for Global Catalog replication and is indexed.</span></span> <span data-ttu-id="f13ab-390">Se um usuário estiver habilitado para o Enterprise Voice, esse atributo armazenará a versão normalizada E. 164 do número de telefone do usuário.</span><span class="sxs-lookup"><span data-stu-id="f13ab-390">If a user is enabled for Enterprise Voice, this attribute stores the E.164 normalized version of the user’s phone number.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-391">Novo no Microsoft Office Live Communications Server 2005 com SP1</span><span class="sxs-lookup"><span data-stu-id="f13ab-391">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-392">msRTCSIP-LineServer</span><span class="sxs-lookup"><span data-stu-id="f13ab-392">msRTCSIP-LineServer</span></span></p></td>
<td><p><span data-ttu-id="f13ab-393">Esse atributo com valor único contém o URI SIP do servidor do gateway CSTA-SIP.</span><span class="sxs-lookup"><span data-stu-id="f13ab-393">This single-valued attribute contains the SIP URI of the CSTA-SIP gateway server.</span></span> <span data-ttu-id="f13ab-394">Esse atributo está marcado para replicação de catálogo global, mas não está indexado.</span><span class="sxs-lookup"><span data-stu-id="f13ab-394">This attribute is marked for Global Catalog replication but is not indexed.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-395">Novo no Microsoft Office Live Communications Server 2005 com SP1</span><span class="sxs-lookup"><span data-stu-id="f13ab-395">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-396">msRTCSIP-LocalNormalizationData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-396">msRTCSIP-LocalNormalizationData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-397">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="f13ab-397">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-398">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-398">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="f13ab-399">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-399">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-400">msRTCSIP-LocalNormalizationLinks (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-400">msRTCSIP-LocalNormalizationLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-401">Este atributo de valores múltiplos contém uma lista de nomes diferenciais de normalização (DN) locais associados a este perfil de local.</span><span class="sxs-lookup"><span data-stu-id="f13ab-401">This multi-valued attribute contains a list of local normalization distinguished names (DN) associated with this location profile.</span></span> <span data-ttu-id="f13ab-402">O tipo desse atributo é um binário DN.</span><span class="sxs-lookup"><span data-stu-id="f13ab-402">The type of this attribute is a DN binary.</span></span> <span data-ttu-id="f13ab-403">Há uma relação um-para-muitos entre o perfil de local e as regras de normalização locais.</span><span class="sxs-lookup"><span data-stu-id="f13ab-403">There is a one-to-many relationship between location profile and local normalization rules.</span></span> <span data-ttu-id="f13ab-404">A ordenação da lista de DNs de normalização local deve ser mantida na ordem especificada pelo administrador.</span><span class="sxs-lookup"><span data-stu-id="f13ab-404">The ordering of the list of local normalization DNs must be maintained in the order specified by the administrator.</span></span> <span data-ttu-id="f13ab-405">A preservação do pedido é mantida pela parte binária do binário DN, que especifica o índice do pedido.</span><span class="sxs-lookup"><span data-stu-id="f13ab-405">The preservation of order is maintained by the binary portion of the DN binary, which specifies the order index.</span></span></p>
<p><span data-ttu-id="f13ab-406">Link encaminhar: <strong>ID do link 11034</strong></span><span class="sxs-lookup"><span data-stu-id="f13ab-406">Forward link: <strong>Link ID 11034</strong></span></span></p>
<p><span data-ttu-id="f13ab-407">O link regressivo correspondente a este atributo de link de encaminhamento é <strong>msRTCSIP-LocationProfileBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="f13ab-407">The corresponding back link to this forward link attribute is <strong>msRTCSIP-LocationProfileBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-408">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-408">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="f13ab-409">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-409">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-410">msRTCSIP-LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="f13ab-410">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
<td><p><span data-ttu-id="f13ab-411">Esse atributo contém uma lista de opções para a regra de normalização.</span><span class="sxs-lookup"><span data-stu-id="f13ab-411">This attribute contains a list of options for the normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-412">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f13ab-412">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-413">msRTCSIP-LocationName (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-413">msRTCSIP-LocationName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-414">Esse atributo com valor único contém um nome amigável para o perfil de local que indica qual local esse perfil representa.</span><span class="sxs-lookup"><span data-stu-id="f13ab-414">This single-valued attribute contains a friendly name for the location profile that indicates which location this profile represents.</span></span> <span data-ttu-id="f13ab-415">Como pode haver vários perfis de localização, o administrador precisa de uma maneira de distinguir entre diferentes perfis.</span><span class="sxs-lookup"><span data-stu-id="f13ab-415">Because there can be multiple location profiles, the administrator needs a way to distinguish between different profiles.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-416">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-416">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="f13ab-417">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-417">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-418">msRTCSIP-locationProfileBL (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-418">msRTCSIP-locationProfileBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-419">Esse atributo com valores múltiplos contém uma lista de nomes distintos do perfil de local.</span><span class="sxs-lookup"><span data-stu-id="f13ab-419">This multi-valued attribute contains a list of location profile distinguished names.</span></span> <span data-ttu-id="f13ab-420">Esse atributo especifica o link back para um ou mais perfis de local.</span><span class="sxs-lookup"><span data-stu-id="f13ab-420">This attribute specifies the back link to one or more location profiles.</span></span></p>
<p><span data-ttu-id="f13ab-421">Link para trás: <strong>ID do link 11035</strong></span><span class="sxs-lookup"><span data-stu-id="f13ab-421">Back link: <strong>Link ID 11035</strong></span></span></p>
<p><span data-ttu-id="f13ab-422">Esse atributo corresponde ao link Forward <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="f13ab-422">This attribute corresponds to the forward link <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-423">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-423">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="f13ab-424">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-424">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-425">msRTCSIP-LocationProfileData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-425">msRTCSIP-LocationProfileData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-426">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="f13ab-426">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-427">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-427">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="f13ab-428">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-428">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-429">msRTCSIP-LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="f13ab-429">msRTCSIP-LocationProfileOptions</span></span></p></td>
<td><p><span data-ttu-id="f13ab-430">Esse atributo contém as opções do perfil de local.</span><span class="sxs-lookup"><span data-stu-id="f13ab-430">This attribute contains the options for the location profile.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-431">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f13ab-431">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-432">msRTCSIP-MappingContact</span><span class="sxs-lookup"><span data-stu-id="f13ab-432">msRTCSIP-MappingContact</span></span></p></td>
<td><p><span data-ttu-id="f13ab-433">Este atributo de vários valores contém uma lista de contatos do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f13ab-433">This multiple-value attribute holds a list of application contacts.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-434">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f13ab-434">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-435">msRTCSIP-MappingLocation</span><span class="sxs-lookup"><span data-stu-id="f13ab-435">msRTCSIP-MappingLocation</span></span></p></td>
<td><p><span data-ttu-id="f13ab-436">Esse atributo de vários valores contém uma lista de perfis de localização.</span><span class="sxs-lookup"><span data-stu-id="f13ab-436">This multiple-value attribute holds a list of location profiles.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-437">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f13ab-437">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-438">msRTCSIP-MaxNumOutstandingSearchPerServer (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-438">msRTCSIP-MaxNumOutstandingSearchPerServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-439">Esse atributo representa o número máximo de solicitações de pesquisa pendentes por servidor.</span><span class="sxs-lookup"><span data-stu-id="f13ab-439">This attribute represents the maximum number of outstanding search requests per server.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-440">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-440">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-441">msRTCSIP-MaxNumSubscriptionsPerUser (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-441">msRTCSIP-MaxNumSubscriptionsPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-442">O atributo representa o número máximo de assinaturas por usuário.</span><span class="sxs-lookup"><span data-stu-id="f13ab-442">The attribute represents the maximum number of subscriptions per user.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-443">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-443">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-444">msRTCSIP-MaxPresenceSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-444">msRTCSIP-MaxPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-445">Esse atributo representa a janela de tempo limite máximo da assinatura.</span><span class="sxs-lookup"><span data-stu-id="f13ab-445">This attribute represents the maximum subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-446">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-446">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-447">msRTCSIP-MaxRegistrationsTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-447">msRTCSIP-MaxRegistrationsTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-448">Esse atributo representa a janela de tempo limite de registros máximos.</span><span class="sxs-lookup"><span data-stu-id="f13ab-448">This attribute represents the maximum registrations time-out window.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-449">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-449">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-450">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-450">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-451">Esse atributo representa a janela de tempo limite de máximo de assinaturas de roaming de dados.</span><span class="sxs-lookup"><span data-stu-id="f13ab-451">This attribute represents the maximum roaming data subscriptions time-out window.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-452">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-452">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-453">msRTCSIP-MCUData</span><span class="sxs-lookup"><span data-stu-id="f13ab-453">msRTCSIP-MCUData</span></span></p></td>
<td><p><span data-ttu-id="f13ab-454">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="f13ab-454">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-455">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-455">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-456">msRTCSIP-MCUFactoryAddress</span><span class="sxs-lookup"><span data-stu-id="f13ab-456">msRTCSIP-MCUFactoryAddress</span></span></p></td>
<td><p><span data-ttu-id="f13ab-457">Esse atributo é um atributo de ponto de controle de serviço na classe Computer que especifica um link de volta para a fábrica da unidade de controle multiponto (MCU) à qual ele pertence.</span><span class="sxs-lookup"><span data-stu-id="f13ab-457">This attribute is a service control point attribute under the computer class that specifies a link back to the multipoint control unit (MCU) Factory to which it belongs.</span></span> <span data-ttu-id="f13ab-458">Esse atributo e este ponto de controle de serviço é criado para cada Microsoft MCU.</span><span class="sxs-lookup"><span data-stu-id="f13ab-458">This service control point and attribute is created for every Microsoft MCU.</span></span> <span data-ttu-id="f13ab-459">Cada Microsoft MCU deve encontrar o servidor back-end do pool ao qual ele pertence, para recuperar as configurações no nível do pool.</span><span class="sxs-lookup"><span data-stu-id="f13ab-459">Each Microsoft MCU must find the Back End Server of the pool to which it belongs, in order to retrieve pool-level settings from it.</span></span></p>
<p><span data-ttu-id="f13ab-460">O valor desse atributo é o nome diferenciado (DN) da fábrica do MCU.</span><span class="sxs-lookup"><span data-stu-id="f13ab-460">The value of this attribute is the distinguished name (DN) of the MCU Factory.</span></span> <span data-ttu-id="f13ab-461">Esse é um atributo de valor único e marcado para replicação de catálogo global.</span><span class="sxs-lookup"><span data-stu-id="f13ab-461">This is a single-valued attribute and marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="f13ab-462">Link encaminhar: <strong>ID do link 11026</strong></span><span class="sxs-lookup"><span data-stu-id="f13ab-462">Forward link: <strong>Link ID 11026</strong></span></span></p>
<p><span data-ttu-id="f13ab-463">O link regressivo correspondente a este atributo de link de encaminhamento é <strong>msRTCSIP-MCUServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="f13ab-463">The corresponding back link to this forward link attribute is <strong>msRTCSIP-MCUServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-464">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-464">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-465">msRTCSIP-MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="f13ab-465">msRTCSIP-MCUFactoryData</span></span></p></td>
<td><p><span data-ttu-id="f13ab-466">Este é um atributo reservado de várias cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="f13ab-466">This is a multi-string reserved attribute.</span></span> <span data-ttu-id="f13ab-467">As configurações armazenadas nesse atributo são representadas como pares nome = valor.</span><span class="sxs-lookup"><span data-stu-id="f13ab-467">Settings stored in this attribute are represented as name=value pairs.</span></span> <span data-ttu-id="f13ab-468">Pares nome = valor atualmente definidos são:</span><span class="sxs-lookup"><span data-stu-id="f13ab-468">Currently defined name=value pairs are:</span></span></p>
<ul>
<li><p><span data-ttu-id="f13ab-469">FactoryURL = &lt;URL&gt;</span><span class="sxs-lookup"><span data-stu-id="f13ab-469">FactoryURL = &lt;URL&gt;</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f13ab-470">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-470">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-471">msRTCSIP-MCUFactoryPath</span><span class="sxs-lookup"><span data-stu-id="f13ab-471">msRTCSIP-MCUFactoryPath</span></span></p></td>
<td><p><span data-ttu-id="f13ab-472">Esse é um atributo de valor único que contém o nome diferenciado (DN) de uma única fábrica de MCU associada a um pool.</span><span class="sxs-lookup"><span data-stu-id="f13ab-472">This is a single-valued attribute that contains the distinguished name (DN) of a single MCU factory associated with a pool.</span></span></p>
<p><span data-ttu-id="f13ab-473">Link encaminhar: <strong>ID do link 11024</strong></span><span class="sxs-lookup"><span data-stu-id="f13ab-473">Forward link: <strong>Link ID 11024</strong></span></span></p>
<p><span data-ttu-id="f13ab-474">O link regressivo correspondente a este atributo de link de encaminhamento é <strong>msRTCSIP-PoolAddresses</strong>.</span><span class="sxs-lookup"><span data-stu-id="f13ab-474">The corresponding back link to this forward link attribute is <strong>msRTCSIP-PoolAddresses</strong>.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-475">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-475">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-476">msRTCSIP-MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="f13ab-476">msRTCSIP-MCUFactoryProviderID</span></span></p></td>
<td><p><span data-ttu-id="f13ab-477">Esse atributo é uma cadeia de caracteres com valor único que especifica o GUID do provedor de fábrica MCU.</span><span class="sxs-lookup"><span data-stu-id="f13ab-477">This attribute is a single-valued string that specifies the GUID of the MCU factory provider.</span></span> <span data-ttu-id="f13ab-478">Com base no valor GUID, o processo de fábrica do MCU determina se o tipo de MCU deve ser atendido.</span><span class="sxs-lookup"><span data-stu-id="f13ab-478">Based on the GUID value, the MCU factory process determines whether to service this MCU type.</span></span> <span data-ttu-id="f13ab-479">Se o valor GUID for <strong>{F0810510-424F-46ef-84fe-6CC720DF1791}</strong>, o processo de fábrica do MCU (disponível por padrão no Lync Server) o processará.</span><span class="sxs-lookup"><span data-stu-id="f13ab-479">If the GUID value is <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, then the MCU factory process (available by default in Lync Server) will process it.</span></span> <span data-ttu-id="f13ab-480">Para qualquer outro valor de GUID, o processo de fábrica da MCU não irá atender ao tipo de MCU.</span><span class="sxs-lookup"><span data-stu-id="f13ab-480">For any other GUID value, the MCU factory process will not service the MCU type.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-481">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-481">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-482">msRTCSIP-MCUServers</span><span class="sxs-lookup"><span data-stu-id="f13ab-482">msRTCSIP-MCUServers</span></span></p></td>
<td><p><span data-ttu-id="f13ab-483">Esse atributo é uma lista com vários valores de nomes diferenciados (DN).</span><span class="sxs-lookup"><span data-stu-id="f13ab-483">This attribute is a multi-valued list of distinguished names (DN).</span></span> <span data-ttu-id="f13ab-484">Esse atributo contém uma lista de todos os servidores MCU do mesmo tipo e fornecedor associados a essa fábrica de MCU.</span><span class="sxs-lookup"><span data-stu-id="f13ab-484">This attribute contains a list of all MCU servers of the same type and vendor associated with this MCU factory.</span></span> <span data-ttu-id="f13ab-485">O valor válido para cada segmento é de 63 caracteres; o valor válido para o FQDN inteiro é de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="f13ab-485">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p>
<p><span data-ttu-id="f13ab-486">Link para trás: ID do link 11027</span><span class="sxs-lookup"><span data-stu-id="f13ab-486">Back link: Link ID 11027</span></span></p>
<p><span data-ttu-id="f13ab-487">O link encaminhamento correspondente para esse link regressivo é <strong>msRTCSIP-MCUFactoryAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="f13ab-487">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-488">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-488">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-489">msRTCSIP-MCUType</span><span class="sxs-lookup"><span data-stu-id="f13ab-489">msRTCSIP-MCUType</span></span></p></td>
<td><p><span data-ttu-id="f13ab-490">Esse atributo é uma cadeia de caracteres com valor único que especifica a mídia que a MCU pode manipular.</span><span class="sxs-lookup"><span data-stu-id="f13ab-490">This attribute is a single-valued string that specifies the medium the MCU can handle.</span></span></p>
<p><span data-ttu-id="f13ab-491">Os tipos válidos com suporte são:</span><span class="sxs-lookup"><span data-stu-id="f13ab-491">Supported valid types are:</span></span></p>
<ul>
<li><p><span data-ttu-id="f13ab-492">reunião</span><span class="sxs-lookup"><span data-stu-id="f13ab-492">meeting</span></span></p></li>
<li><p><span data-ttu-id="f13ab-493">áudio-vídeo</span><span class="sxs-lookup"><span data-stu-id="f13ab-493">audio-video</span></span></p></li>
<li><p><span data-ttu-id="f13ab-494">chat</span><span class="sxs-lookup"><span data-stu-id="f13ab-494">chat</span></span></p></li>
<li><p><span data-ttu-id="f13ab-495">telefone-conf</span><span class="sxs-lookup"><span data-stu-id="f13ab-495">phone-conf</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f13ab-496">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-496">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-497">msRTCSIP-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="f13ab-497">msRTCSIP-MCUVendor</span></span></p></td>
<td><p><span data-ttu-id="f13ab-498">Esse atributo é uma cadeia de caracteres de valor único que especifica o nome de um fornecedor de MCU.</span><span class="sxs-lookup"><span data-stu-id="f13ab-498">This attribute is a single-valued string that specifies an MCU vendor’s name.</span></span> <span data-ttu-id="f13ab-499">Todos os Microsoft MCUs especificarão esse atributo para ser <strong>Microsoft Corporation</strong>.</span><span class="sxs-lookup"><span data-stu-id="f13ab-499">All Microsoft MCUs will specify this attribute to be <strong>Microsoft Corporation</strong>.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-500">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-500">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-501">msRTCSIP-MeetingFlags (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-501">msRTCSIP-MeetingFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-502">Esse atributo define diferentes opções de reunião que são habilitadas globalmente para todos os usuários ou objetos de contato.</span><span class="sxs-lookup"><span data-stu-id="f13ab-502">This attribute defines different meeting options that are enabled globally for all users or contact objects.</span></span> <span data-ttu-id="f13ab-503">Esse atributo é um valor de máscara de bits do tipo inteiro.</span><span class="sxs-lookup"><span data-stu-id="f13ab-503">This attribute is a bit-mask value of integer type.</span></span></p>
<p><span data-ttu-id="f13ab-504">Os valores válidos (e posições de bit associadas) são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="f13ab-504">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="f13ab-505">0: AllowOrganizeMeetingWithAnonymousParticipants é nenhum (não permitir que os usuários convidem usuários anônimos para reuniões) (nenhum bit definido)</span><span class="sxs-lookup"><span data-stu-id="f13ab-505">0: AllowOrganizeMeetingWithAnonymousParticipants is None (do not allow users to invite anonymous users to meetings) (no bits set)</span></span></p></li>
<li><p><span data-ttu-id="f13ab-506">4: o AllowOrganizeMeetingWithAnonymousParticipants é todos (permitir que todos os usuários convidem usuários anônimos para reuniões) (posição do bit 2)</span><span class="sxs-lookup"><span data-stu-id="f13ab-506">4: AllowOrganizeMeetingWithAnonymousParticipants is Everyone (allow all users to invite anonymous users to meetings) (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="f13ab-507">8: AllowOrganizeMeetingWithAnonymousParticipants é UsePerUserSetting (permitir que os usuários convidem usuários anônimos para reuniões com base na configuração por usuário) (posição de bit 3)</span><span class="sxs-lookup"><span data-stu-id="f13ab-507">8: AllowOrganizeMeetingWithAnonymousParticipants is UsePerUserSetting (allow users to invite anonymous users to meetings based on per user setting) (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="f13ab-508">16: UserPerUserMeetingPolicy (a política de reunião é definida por usuário) (posição 4 do bit)</span><span class="sxs-lookup"><span data-stu-id="f13ab-508">16: UserPerUserMeetingPolicy (meeting policy is defined per user) (bit position 4)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f13ab-509">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-509">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="f13ab-510">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-510">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-511">msRTCSIP-MeetingPolicy (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-511">msRTCSIP-MeetingPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-512">Esse atributo especifica o nome diferenciado (DN) da política que o administrador atribuiu para este usuário como um atributo de valor único.</span><span class="sxs-lookup"><span data-stu-id="f13ab-512">This attribute specifies the distinguished name (DN) of the policy the administrator has assigned for this user as a single-valued attribute.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-513">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-513">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="f13ab-514">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-514">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-515">msRTCSIP-MinPresenceSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-515">msRTCSIP-MinPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-516">Esse atributo representa a janela de tempo limite de assinatura de presença mínima.</span><span class="sxs-lookup"><span data-stu-id="f13ab-516">This attribute represents the minimum presence subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-517">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-517">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-518">msRTCSIP-MinRegistrationTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-518">msRTCSIP-MinRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-519">Esse atributo representa a janela de tempo limite de inscrição mínima.</span><span class="sxs-lookup"><span data-stu-id="f13ab-519">This attribute represents the minimum registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-520">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-520">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="f13ab-521">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-521">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-522">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-522">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-523">Esse atributo representa a janela de tempo limite de assinatura de dados de roaming mínimo.</span><span class="sxs-lookup"><span data-stu-id="f13ab-523">This attribute represents the minimum roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-524">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-524">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="f13ab-525">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-525">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-526">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="f13ab-526">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="f13ab-527">Esse atributo é usado para armazenar o back-end do SQL Server espelhado usado pelo pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="f13ab-527">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-528">Novo no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f13ab-528">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-529">msRTCSIP-MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="f13ab-529">msRTCSIP-MobilityFlags</span></span></p></td>
<td><p><span data-ttu-id="f13ab-530">Esse atributo contém opções e sinalizadores que definem as configurações de mobilidade.</span><span class="sxs-lookup"><span data-stu-id="f13ab-530">This attribute contains options and flags that define mobility settings.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-531">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f13ab-531">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-532">msRTCSIP-MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="f13ab-532">msRTCSIP-MobilityPolicy</span></span></p></td>
<td><p><span data-ttu-id="f13ab-533">Esse atributo contém o DN para um objeto de política de mobilidade.</span><span class="sxs-lookup"><span data-stu-id="f13ab-533">This attribute contains the DN for a mobility policy object.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-534">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f13ab-534">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-535">msRTCSIP-NumDevicesPerUser (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-535">msRTCSIP-NumDevicesPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-536">Esse atributo representa o número permitido de dispositivos nos quais um usuário pode se registrar para comunicações SIP e se inscrever na presença.</span><span class="sxs-lookup"><span data-stu-id="f13ab-536">This attribute represents the allowed number of devices on which a user can register for SIP communications and subscribe to presence.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-537">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-537">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="f13ab-538">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-538">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-539">msRTCSIP-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="f13ab-539">msRTCSIP-OptionFlags</span></span></p></td>
<td><p><span data-ttu-id="f13ab-540">Esse atributo especifica as opções que são habilitadas para o objeto de contato ou usuário.</span><span class="sxs-lookup"><span data-stu-id="f13ab-540">This attribute specifies the options that are enabled for the user or contact object.</span></span> <span data-ttu-id="f13ab-541">Esse atributo é um valor de máscara de bits do tipo inteiro.</span><span class="sxs-lookup"><span data-stu-id="f13ab-541">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="f13ab-542">Cada opção é representada por um pouco.</span><span class="sxs-lookup"><span data-stu-id="f13ab-542">Each option is represented by a bit.</span></span> <span data-ttu-id="f13ab-543">Esse atributo está marcado para replicação de catálogo global.</span><span class="sxs-lookup"><span data-stu-id="f13ab-543">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="f13ab-544">Os valores válidos (e posições de bit associadas) são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="f13ab-544">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="f13ab-545">1: habilitado para conectividade de mensagens instantâneas (IM) públicas (posição do bit 0)</span><span class="sxs-lookup"><span data-stu-id="f13ab-545">1: Enabled for public instant messaging (IM) connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="f13ab-546">2: reservado (posição do bit 1)</span><span class="sxs-lookup"><span data-stu-id="f13ab-546">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="f13ab-547">4: reservado (posição do bit 2)</span><span class="sxs-lookup"><span data-stu-id="f13ab-547">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="f13ab-548">8: reservado (posição do bit 3)</span><span class="sxs-lookup"><span data-stu-id="f13ab-548">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="f13ab-549">16: controle de chamada remota habilitado [telefonia] (posição de bit 4)</span><span class="sxs-lookup"><span data-stu-id="f13ab-549">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="f13ab-550">64: AllowOrganizeMeetingWithAnonymousParticipants (permite que os usuários convidem usuários anônimos para reuniões (posição de bit 6)</span><span class="sxs-lookup"><span data-stu-id="f13ab-550">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="f13ab-551">128: UCEnabled (habilitar usuários para UC) (posição do bit 7)</span><span class="sxs-lookup"><span data-stu-id="f13ab-551">128: UCEnabled (enable users for UC) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="f13ab-552">256: EnabledForEnhancedPresence (habilitar usuário para conectividade de IM pública) (posição de bit 8)</span><span class="sxs-lookup"><span data-stu-id="f13ab-552">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="f13ab-553">512: RemoteCallControlDualMode (posição do bit 9)</span><span class="sxs-lookup"><span data-stu-id="f13ab-553">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f13ab-554">Novo no Live Communications Server 2005 com SP1.</span><span class="sxs-lookup"><span data-stu-id="f13ab-554">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-555">msRTCSIP-OriginatorSID</span><span class="sxs-lookup"><span data-stu-id="f13ab-555">msRTCSIP-OriginatorSID</span></span></p></td>
<td><p><span data-ttu-id="f13ab-556">Esse atributo é usado em topologias de floresta central e de recursos para habilitar o logon único quando os objetos do usuário da conta principal do Windows NT Server são copiados para esse atributo do usuário ou do objeto de contato correspondente no recurso ou na floresta central.</span><span class="sxs-lookup"><span data-stu-id="f13ab-556">This attribute is used in resource and central forest topologies to enable single sign-on when a user’s ObjectSID from the Windows NT Server principal account is copied into this attribute of the corresponding user or contact object in the resource or central forest.</span></span> <span data-ttu-id="f13ab-557">O Communicator Web Access procura por um usuário no AD DS usando esse atributo ou o ObjectID do usuário.</span><span class="sxs-lookup"><span data-stu-id="f13ab-557">Communicator Web Access searches for a user in AD DS using this attribute or the user’s ObjectSID.</span></span> <span data-ttu-id="f13ab-558">Esse atributo está marcado para replicação de catálogo global.</span><span class="sxs-lookup"><span data-stu-id="f13ab-558">This attribute is marked for global catalog replication.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-559">msRTCSIP-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="f13ab-559">msRTCSIP-OwnerUrn</span></span></p></td>
<td><p><span data-ttu-id="f13ab-560">Esse atributo é o nome de recurso uniforme (URN) do proprietário de um contato de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f13ab-560">This attribute is the Uniform Resource Name (URN) of the owner for an application contact.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-561">Novo no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-561">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-562">msRTCSIP-padrão (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-562">msRTCSIP-Pattern (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-563">Este atributo de cadeia de caracteres de valor único contém um padrão usado para números de discagem correspondentes no formato E. 164.</span><span class="sxs-lookup"><span data-stu-id="f13ab-563">This single-valued string attribute contains a pattern used for matching dial numbers into E.164 format.</span></span> <span data-ttu-id="f13ab-564">Se o número de discagem coincidir com esse padrão, a tradução será aplicada ao número discado.</span><span class="sxs-lookup"><span data-stu-id="f13ab-564">If the dial number matches this pattern, the translation is applied to the dialed number.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-565">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-565">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="f13ab-566">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-566">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-567">msRTCSIP-PhoneRouteBL (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-567">msRTCSIP-PhoneRouteBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-568">Este atributo de valores múltiplos contém uma lista de nomes distintos de rota de telefone (DN).</span><span class="sxs-lookup"><span data-stu-id="f13ab-568">This multi-valued attribute contains a list of phone route distinguished names (DN).</span></span> <span data-ttu-id="f13ab-569">Esse atributo especifica o link para trás para uma ou mais rotas de telefone.</span><span class="sxs-lookup"><span data-stu-id="f13ab-569">This attribute specifies the back link to one or more phone routes.</span></span></p>
<p><span data-ttu-id="f13ab-570">Link para trás: <strong>ID do link 11033</strong></span><span class="sxs-lookup"><span data-stu-id="f13ab-570">Back link: <strong>Link ID 11033</strong></span></span></p>
<p><span data-ttu-id="f13ab-571">Esse atributo corresponde ao link Forward <strong>msRTCSIP-RouteUsageLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="f13ab-571">This attribute corresponds to the forward link <strong>msRTCSIP-RouteUsageLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-572">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-572">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="f13ab-573">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-573">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-574">msRTCSIP-PhoneRouteData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-574">msRTCSIP-PhoneRouteData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-575">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="f13ab-575">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-576">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-576">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-577">msRTCSIP-PhoneRouteName (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-577">msRTCSIP-PhoneRouteName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-578">Esse atributo de cadeia de caracteres UNICODE de valor único especifica o nome amigável da rota do telefone, para que ele possa ser referenciado facilmente pelo administrador.</span><span class="sxs-lookup"><span data-stu-id="f13ab-578">This single valued UNICODE string attribute specifies the friendly name of the phone route, so it can easily be referenced by the administrator.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-579">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-579">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-580">msRTCSIP-PhoneUsageData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-580">msRTCSIP-PhoneUsageData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-581">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="f13ab-581">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-582">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-582">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="f13ab-583">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-583">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-584">msRTCSIP-PolicyContent (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-584">msRTCSIP-PolicyContent (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-585">Esse atributo é uma cadeia de caracteres Unicode com um único valor.</span><span class="sxs-lookup"><span data-stu-id="f13ab-585">This attribute is a single-valued Unicode string.</span></span> <span data-ttu-id="f13ab-586">Este atributo de cadeia de caracteres contém a definição de política no formato XML.</span><span class="sxs-lookup"><span data-stu-id="f13ab-586">This string attribute contains the policy definition in XML format.</span></span> <span data-ttu-id="f13ab-587">A definição do esquema XML é comum em diferentes tipos de política, apenas as configurações são diferentes para cada tipo de política.</span><span class="sxs-lookup"><span data-stu-id="f13ab-587">The XML schema definition is common across different policy types, only the settings are different for each policy type.</span></span></p>
<p><span data-ttu-id="f13ab-588">A definição de esquema XML (XSD) é definida da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="f13ab-588">The XML schema definition (XSD) is defined as follows:</span></span></p>
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
<td><p><span data-ttu-id="f13ab-589">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-589">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="f13ab-590">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-590">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-591">msRTCSIP-PolicyData (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-591">msRTCSIP-PolicyData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-592">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="f13ab-592">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-593">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-593">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="f13ab-594">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-594">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-595">msRTCSIP-PolicyType (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-595">msRTCSIP-PolicyType (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-596">Esse atributo de cadeia de caracteres Unicode com valor único contém o tipo de política.</span><span class="sxs-lookup"><span data-stu-id="f13ab-596">This single-valued Unicode string attribute contains the policy type.</span></span> <span data-ttu-id="f13ab-597">Os tipos de política válidos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="f13ab-597">Valid policy types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="f13ab-598">reunião</span><span class="sxs-lookup"><span data-stu-id="f13ab-598">meeting</span></span></p></li>
<li><p><span data-ttu-id="f13ab-599">telefonia</span><span class="sxs-lookup"><span data-stu-id="f13ab-599">telephony</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f13ab-600">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-600">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="f13ab-601">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-601">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-602">msRTCSIP-PoolAddress</span><span class="sxs-lookup"><span data-stu-id="f13ab-602">msRTCSIP-PoolAddress</span></span></p></td>
<td><p><span data-ttu-id="f13ab-603">Esse atributo especifica um link de volta para o pool ao qual um computador pertence.</span><span class="sxs-lookup"><span data-stu-id="f13ab-603">This attribute specifies a link back to the pool to which a computer belongs.</span></span> <span data-ttu-id="f13ab-604">Esse atributo é definido independentemente de o computador estar executando a edição Standard ou Enterprise do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f13ab-604">This attribute is set regardless of whether the computer is running the Standard Edition or the Enterprise Edition of Lync Server.</span></span> <span data-ttu-id="f13ab-605">Esse atributo está marcado para replicação de catálogo global.</span><span class="sxs-lookup"><span data-stu-id="f13ab-605">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="f13ab-606">O valor válido é o nome de domínio do pool.</span><span class="sxs-lookup"><span data-stu-id="f13ab-606">The valid value is the domain name of the pool.</span></span></p>
<p><span data-ttu-id="f13ab-607">Link encaminhar: <strong>ID do link 11022</strong></span><span class="sxs-lookup"><span data-stu-id="f13ab-607">Forward link: <strong>Link ID 11022</strong></span></span></p>
<p><span data-ttu-id="f13ab-608">O link regressivo correspondente a este atributo de link de encaminhamento é <strong>msRTCSIP-FrontEndServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="f13ab-608">The corresponding back link to this forward link attribute is <strong>msRTCSIP-FrontEndServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-609">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="f13ab-609">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-610">msRTCSIP-PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="f13ab-610">msRTCSIP-PoolAddresses</span></span></p></td>
<td><p><span data-ttu-id="f13ab-611">Esse é um atributo de valores múltiplos que contém uma lista de nomes diferenciados (DN) de pools com os quais a fábrica do MCU está associada.</span><span class="sxs-lookup"><span data-stu-id="f13ab-611">This is a multi-valued attribute that contains a list of the distinguished names (DN) of pools with which the MCU factory is associated.</span></span></p>
<p><span data-ttu-id="f13ab-612">Link para trás: <strong>ID do link 11025</strong></span><span class="sxs-lookup"><span data-stu-id="f13ab-612">Back link: <strong>Link ID 11025</strong></span></span></p>
<p><span data-ttu-id="f13ab-613">O link encaminhamento correspondente para esse link regressivo é <strong>msRTCSIP-MCUFactoryPath</strong>.</span><span class="sxs-lookup"><span data-stu-id="f13ab-613">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryPath</strong>.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-614">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-614">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-615">msRTCSIP-PoolData</span><span class="sxs-lookup"><span data-stu-id="f13ab-615">msRTCSIP-PoolData</span></span></p></td>
<td><p><span data-ttu-id="f13ab-616">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="f13ab-616">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-617">Novo no Live Communications Server 2005 com SP1.</span><span class="sxs-lookup"><span data-stu-id="f13ab-617">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-618">msRTCSIP-PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="f13ab-618">msRTCSIP-PoolDisplayName</span></span></p></td>
<td><p><span data-ttu-id="f13ab-619">Esse atributo especifica um nome arbitrário para um pool que é exibido pelo console de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="f13ab-619">This attribute specifies an arbitrary name for a pool that is displayed by the management console.</span></span> <span data-ttu-id="f13ab-620">Esse nome pode ser alterado pelo administrador.</span><span class="sxs-lookup"><span data-stu-id="f13ab-620">This name can be changed by the administrator.</span></span></p>
<p><span data-ttu-id="f13ab-621">O valor válido é uma cadeia de caracteres que representa o nome de um pool.</span><span class="sxs-lookup"><span data-stu-id="f13ab-621">The valid value is a string representing the name of a pool.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-622">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="f13ab-622">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-623">msRTCSIP-PoolDomainFQDN</span><span class="sxs-lookup"><span data-stu-id="f13ab-623">msRTCSIP-PoolDomainFQDN</span></span></p></td>
<td><p><span data-ttu-id="f13ab-624">Esse atributo é um valor de cadeia de caracteres de valor único.</span><span class="sxs-lookup"><span data-stu-id="f13ab-624">This attribute is a single-valued string value.</span></span> <span data-ttu-id="f13ab-625">O valor desse atributo, quando presente, representa o FQDN do domínio do pool se o administrador quiser criar um pool de front-end com um FQDN que não esteja em conformidade com a estrutura de domínio do Active Directory na qual o pool de front-ends é criado (por exemplo, um SIP namespace desincluído do namespace DNS (sistema de nomes de domínio)).</span><span class="sxs-lookup"><span data-stu-id="f13ab-625">The value of this attribute, when present, represents the pool’s domain FQDN if the administrator wants to create a Front End pool with an FQDN that does not conform to the Active Directory domain structure in which the Front End pool is created (for example, a SIP namespace disjoined from Domain Name System (DNS) namespace).</span></span></p>
<p><span data-ttu-id="f13ab-626">Recomendamos que você mapeie o FQDN do domínio do pool de front-end para a parte do nome do domínio como o domínio do Active Directory no qual o pool reside.</span><span class="sxs-lookup"><span data-stu-id="f13ab-626">We recommend that you map the Front End pool domain FQDN to the domain name portion as the Active Directory domain in which the pool resides.</span></span> <span data-ttu-id="f13ab-627">Portanto, quando nenhum valor estiver presente nesse atributo, o FQDN do pool de front-end usará como padrão a estrutura de nomes de domínio do Active Directory, como indicado pelo atributo <strong>dNSHostName</strong> .</span><span class="sxs-lookup"><span data-stu-id="f13ab-627">Therefore, when no value is present in this attribute, the Front End pool FQDN will default to the Active Directory domain name structure, as denoted by the <strong>dnsHostName</strong> attribute.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-628">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-628">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-629">msRTCSIP-PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="f13ab-629">msRTCSIP-PoolFunctionality</span></span></p></td>
<td><p><span data-ttu-id="f13ab-630">Uma lista de vários valores de todos os nomes de domínio de todos os servidores do Lync Server, Enterprise Edition associados a um pool.</span><span class="sxs-lookup"><span data-stu-id="f13ab-630">A multi-valued list of the domain names of all Lync Server, Enterprise Edition servers associated with a pool.</span></span> <span data-ttu-id="f13ab-631">Esse atributo do tipo Integer define se o pool é capaz de enviar mensagens instantâneas (IM) e presença e reuniões.</span><span class="sxs-lookup"><span data-stu-id="f13ab-631">This attribute of type integer defines whether the pool is capable of instant messaging (IM) and presence, and meetings.</span></span></p>
<p><span data-ttu-id="f13ab-632">Os possíveis tipos de valor válidos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="f13ab-632">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="f13ab-633">Indefinido: serviço de mensagem instantânea e de presença (Live Communications Server 2005 e 2003)</span><span class="sxs-lookup"><span data-stu-id="f13ab-633">Undefined: IM and Presence Service (Live Communications Server 2005 and 2003)</span></span></p></li>
<li><p><span data-ttu-id="f13ab-634">1: serviço de mensagem instantânea e de presença (Lync Server)</span><span class="sxs-lookup"><span data-stu-id="f13ab-634">1: IM and Presence Service (Lync Server)</span></span></p></li>
<li><p><span data-ttu-id="f13ab-635">2: mensagens de chat e presença e serviço de reunião (Lync Server)</span><span class="sxs-lookup"><span data-stu-id="f13ab-635">2: IM and Presence and Meeting Service (Lync Server)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f13ab-636">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-636">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-637">msRTCSIP-Pooltype</span><span class="sxs-lookup"><span data-stu-id="f13ab-637">msRTCSIP-PoolType</span></span></p></td>
<td><p><span data-ttu-id="f13ab-638">Esse atributo especifica se um pool de servidores está executando o Standard Edition Server ou o Enterprise Edition Server.</span><span class="sxs-lookup"><span data-stu-id="f13ab-638">This attribute specifies whether a server pool is running Standard Edition server or Enterprise Edition server.</span></span> <span data-ttu-id="f13ab-639">Esse atributo é um valor de máscara de bits do tipo inteiro.</span><span class="sxs-lookup"><span data-stu-id="f13ab-639">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="f13ab-640">Cada opção é representada por um pouco.</span><span class="sxs-lookup"><span data-stu-id="f13ab-640">Each option is represented by a bit.</span></span></p>
<p><span data-ttu-id="f13ab-641">Os valores válidos (e posições de bit associadas) são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="f13ab-641">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="f13ab-642">1: servidor de edição padrão, usuários de host (posição do bit 0)</span><span class="sxs-lookup"><span data-stu-id="f13ab-642">1: Standard Edition server, hosts users (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="f13ab-643">2: Enterprise Edition Server, usuários de host (posição de bit 1)</span><span class="sxs-lookup"><span data-stu-id="f13ab-643">2: Enterprise Edition server, hosts users (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="f13ab-644">4: servidor Standard Edition, aplicativos de host (posição 2 do bit)</span><span class="sxs-lookup"><span data-stu-id="f13ab-644">4: Standard Edition server, hosts applications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="f13ab-645">8: Enterprise Edition Server, aplicativos de host (posição de bit 3)</span><span class="sxs-lookup"><span data-stu-id="f13ab-645">8: Enterprise Edition server, hosts applications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="f13ab-646">Como o Lync Server não oferece suporte a pools que hospedam apenas aplicativos, os únicos valores válidos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="f13ab-646">Because Lync Server does not support pools that host only applications, the only valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="f13ab-647">5: servidor Standard Edition, hospeda usuários e aplicativos (posições de bit 0 e 2)</span><span class="sxs-lookup"><span data-stu-id="f13ab-647">5: Standard Edition server, hosts users and applications (bit positions 0 and 2)</span></span></p></li>
<li><p><span data-ttu-id="f13ab-648">10: Enterprise Edition Server, hospeda usuários e aplicativos (posições de bit 1 e 3)</span><span class="sxs-lookup"><span data-stu-id="f13ab-648">10: Enterprise Edition server, hosts users and applications (bit positions 1 and 3)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f13ab-649">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="f13ab-649">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-650">msRTCSIP-PoolVersion</span><span class="sxs-lookup"><span data-stu-id="f13ab-650">msRTCSIP-PoolVersion</span></span></p></td>
<td><p><span data-ttu-id="f13ab-651">Esse atributo define a versão do pool.</span><span class="sxs-lookup"><span data-stu-id="f13ab-651">This attribute defines the pool version.</span></span> <span data-ttu-id="f13ab-652">É um tipo de inteiro que é incrementado com cada lançamento de produto principal.</span><span class="sxs-lookup"><span data-stu-id="f13ab-652">It is an integer type that is incremented with each major product release.</span></span></p>
<p><span data-ttu-id="f13ab-653">Os possíveis tipos de valor válidos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="f13ab-653">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="f13ab-654">0: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="f13ab-654">0: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="f13ab-655">1: Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="f13ab-655">1: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="f13ab-656">2: Live Communications Server 2005 com SP1</span><span class="sxs-lookup"><span data-stu-id="f13ab-656">2: Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="f13ab-657">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="f13ab-657">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="f13ab-658">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="f13ab-658">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="f13ab-659">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="f13ab-659">5: Lync Server 2010</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f13ab-660">Live Communications Server 2005 com SP1.</span><span class="sxs-lookup"><span data-stu-id="f13ab-660">Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-661">msRTCSIP-PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="f13ab-661">msRTCSIP-PresenceFlags</span></span></p></td>
<td><p><span data-ttu-id="f13ab-662">Esse atributo contém opções e sinalizadores que definem as configurações de presença.</span><span class="sxs-lookup"><span data-stu-id="f13ab-662">This attribute contains options and flags that define presence settings.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-663">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f13ab-663">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-664">msRTCSIP-PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="f13ab-664">msRTCSIP-PresencePolicy</span></span></p></td>
<td><p><span data-ttu-id="f13ab-665">Esse atributo contém o DN para um objeto de política de presença.</span><span class="sxs-lookup"><span data-stu-id="f13ab-665">This attribute contains the DN for a presence policy object.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-666">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f13ab-666">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-667">msRTCSIP-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="f13ab-667">msRTCSIP-PrimaryHomeServer</span></span></p></td>
<td><p><span data-ttu-id="f13ab-668">Esse atributo habilita um usuário ou contato para mensagens SIP.</span><span class="sxs-lookup"><span data-stu-id="f13ab-668">This attribute enables a user or contact for SIP messaging.</span></span> <span data-ttu-id="f13ab-669">Ele é adicionado à classe Contact porque, na topologia de floresta central, objetos de contato, não objetos de usuário, estão habilitados para SIP.</span><span class="sxs-lookup"><span data-stu-id="f13ab-669">It is added to the contact class because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="f13ab-670">O valor válido é o DN do servidor Standard Edition ou do pool Front-end da edição Enterprise onde um usuário é hospedado.</span><span class="sxs-lookup"><span data-stu-id="f13ab-670">The valid value is the DN of the Standard Edition server or Enterprise Edition Front End pool where a user is homed.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-671">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="f13ab-671">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-672">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="f13ab-672">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="f13ab-673">Esse atributo contém o endereço SIP de um determinado usuário.</span><span class="sxs-lookup"><span data-stu-id="f13ab-673">This attribute contains the SIP address of a given user.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-674">msRTCSIP-privado</span><span class="sxs-lookup"><span data-stu-id="f13ab-674">msRTCSIP-PrivateLine</span></span></p></td>
<td><p><span data-ttu-id="f13ab-675">Esse atributo contém a ID do dispositivo de linha particular.</span><span class="sxs-lookup"><span data-stu-id="f13ab-675">This attribute contains the device ID of the private line device.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-676">Novo no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-676">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-677">msRTCSIP-roteável</span><span class="sxs-lookup"><span data-stu-id="f13ab-677">msRTCSIP-Routable</span></span></p></td>
<td><p><span data-ttu-id="f13ab-678">Esse atributo é um atributo booliano usado para determinar se o Lync Server está autorizado a direcionar para esse serviço usando seu endereço GRUU.</span><span class="sxs-lookup"><span data-stu-id="f13ab-678">This attribute is a Boolean attribute used to determine whether Lync Server is authorized to route to this service using its GRUU address.</span></span> <span data-ttu-id="f13ab-679">Se esse valor for definido como <strong>true</strong>, o Lync Server estará autorizado a direcionar para esse serviço.</span><span class="sxs-lookup"><span data-stu-id="f13ab-679">If this value is set to <strong>TRUE</strong>, Lync Server is authorized to route to this service.</span></span> <span data-ttu-id="f13ab-680">Se esse valor for definido como <strong>false</strong>, o Lync Server não será autorizado a encaminhar para esse serviço.</span><span class="sxs-lookup"><span data-stu-id="f13ab-680">If this value is set to <strong>FALSE</strong>, Lync Server is not authorized to route to this service.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-681">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-681">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-682">msRTCSIP-RouteUsageAttribute (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-682">msRTCSIP-RouteUsageAttribute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-683">Este atributo de cadeia de caracteres UNICODE com valor único define um atributo que qualifica o uso de uma rota telefônica.</span><span class="sxs-lookup"><span data-stu-id="f13ab-683">This single-valued UNICODE string attribute defines an attribute that qualifies the usage for a phone route.</span></span> <span data-ttu-id="f13ab-684">A seleção de uma rota telefônica é determinada com base em dois elementos: o atributo Usage atribuído à rota do telefone e os atributos de uso da política permitidos do chamador.</span><span class="sxs-lookup"><span data-stu-id="f13ab-684">Selection of a phone route is determined based on two elements: the usage attribute assigned to the phone route and the caller’s allowed policy usage attributes.</span></span> <span data-ttu-id="f13ab-685">A primeira rota telefônica com um atributo Usage que corresponda ao uso permitido pelo chamador está selecionada.</span><span class="sxs-lookup"><span data-stu-id="f13ab-685">The first phone route with a usage attribute that matches the caller’s allowed usage is selected.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-686">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-686">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="f13ab-687">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-687">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-688">msRTCSIP-RouteUsageLinks (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-688">msRTCSIP-RouteUsageLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-689">Este atributo de nome diferenciado (DN) contém uma lista de nomes diferenciados de uso de rota.</span><span class="sxs-lookup"><span data-stu-id="f13ab-689">This multi-valued distinguished name (DN) attribute contains a list of route usage distinguished names.</span></span></p>
<p><span data-ttu-id="f13ab-690">Link encaminhar: <strong>ID do link 11032</strong></span><span class="sxs-lookup"><span data-stu-id="f13ab-690">Forward link: <strong>Link ID 11032</strong></span></span></p>
<p><span data-ttu-id="f13ab-691">Esse atributo é um link de encaminhamento para o link regressivo correspondente <strong>msRTCSIP-PhoneRouteBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="f13ab-691">This attribute is a forward link to the corresponding back link <strong>msRTCSIP-PhoneRouteBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-692">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-692">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-693">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="f13ab-693">msRTCSIP-RoutingPoolDN</span></span></p></td>
<td><p><span data-ttu-id="f13ab-694">Esse atributo contém o DN que aponta para o pool que todo o tráfego SIP endereçado a essa MCU ou serviço confiável deve passar.</span><span class="sxs-lookup"><span data-stu-id="f13ab-694">This attribute contains the DN that points to the pool that all SIP traffic addressed to this MCU or Trusted Service must go through.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-695">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f13ab-695">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-696">msRTCSIP-RuleName (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-696">msRTCSIP-RuleName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-697">Esse atributo de cadeia de caracteres UNICODE com valor único especifica o nome amigável da regra de normalização para que possa ser referenciado facilmente por um administrador.</span><span class="sxs-lookup"><span data-stu-id="f13ab-697">This single-valued UNICODE string attribute specifies the friendly name of the normalization rule, so it can easily be referenced by an administrator.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-698">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-698">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="f13ab-699">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-699">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-700">msRTCSIP-SchemaVersion</span><span class="sxs-lookup"><span data-stu-id="f13ab-700">msRTCSIP-SchemaVersion</span></span></p></td>
<td><p><span data-ttu-id="f13ab-701">Esse atributo representa a versão do esquema atualmente implantada na organização.</span><span class="sxs-lookup"><span data-stu-id="f13ab-701">This attribute represents the schema version currently deployed in the organization.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-702">msRTCSIP-SearchMaxRequests (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-702">msRTCSIP-SearchMaxRequests (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-703">Esse atributo limita o número de resultados da pesquisa a ser retornado de uma pesquisa de diretório quando um usuário pesquisa um contato usando o Communicator.</span><span class="sxs-lookup"><span data-stu-id="f13ab-703">This attribute limits the number of search results to be returned from a directory search when a user searches for a contact using Communicator.</span></span> <span data-ttu-id="f13ab-704">Esse atributo irá substituir o valor fornecido pelo cliente.</span><span class="sxs-lookup"><span data-stu-id="f13ab-704">This attribute will override the value provided by the client.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-705">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-705">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-706">msRTCSIP-SearchMaxResults (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-706">msRTCSIP-SearchMaxResults (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-707">Esse atributo limita o número de solicitações de pesquisa retornadas.</span><span class="sxs-lookup"><span data-stu-id="f13ab-707">This attribute limits the number of search requests returned.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-708">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-708">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-709">msRTCSIP-ServerBL</span><span class="sxs-lookup"><span data-stu-id="f13ab-709">msRTCSIP-ServerBL</span></span></p></td>
<td><p><span data-ttu-id="f13ab-710">Este atributo de valores múltiplos é um link regressivo que contém uma lista de nomes diferenciados (DN).</span><span class="sxs-lookup"><span data-stu-id="f13ab-710">This multi-valued attribute is a back link that contains a list of distinguished names (DN).</span></span> <span data-ttu-id="f13ab-711">Este DNs aponta para um objeto de pool ou <strong>TrustedService</strong> .</span><span class="sxs-lookup"><span data-stu-id="f13ab-711">These DNs point to a pool or <strong>TrustedService</strong> object.</span></span></p>
<p><span data-ttu-id="f13ab-712">Esse atributo corresponde ao link Forward <strong>msRTCSIP-TrustedServiceLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="f13ab-712">This attribute corresponds to the forward link <strong>msRTCSIP-TrustedServiceLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-713">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-713">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-714">msRTCSIP-ServerData</span><span class="sxs-lookup"><span data-stu-id="f13ab-714">msRTCSIP-ServerData</span></span></p></td>
<td><p><span data-ttu-id="f13ab-715">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="f13ab-715">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-716">msRTCSIP-ServerReferenceBL (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-716">msRTCSIP-ServerReferenceBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-717">Esse atributo de valores múltiplos contém uma lista de nomes distintos.</span><span class="sxs-lookup"><span data-stu-id="f13ab-717">This multi-valued attribute contains a list of distinguished names.</span></span> <span data-ttu-id="f13ab-718">Esses nomes diferenciados são links de volta que fazem referência a outros objetos do servidor que podem ser atribuídos a um perfil de local padrão.</span><span class="sxs-lookup"><span data-stu-id="f13ab-718">These distinguished names are back links that reference other server objects that can be assigned a default location profile.</span></span></p>
<p><span data-ttu-id="f13ab-719">Link para trás: <strong>ID do link 11037</strong></span><span class="sxs-lookup"><span data-stu-id="f13ab-719">Back link: <strong>Link ID 11037</strong></span></span></p>
<p><span data-ttu-id="f13ab-720">O link encaminhamento correspondente para esse link regressivo é <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span><span class="sxs-lookup"><span data-stu-id="f13ab-720">The corresponding forward link to this back link is <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span></span></p>
<p><span data-ttu-id="f13ab-721">Este atributo back link faz referência a pools e somente servidores de mediação.</span><span class="sxs-lookup"><span data-stu-id="f13ab-721">This back link attribute references pools and Mediation Servers only.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-722">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-722">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="f13ab-723">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-723">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-724">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="f13ab-724">msRTCSIP-ServerVersion</span></span></p></td>
<td><p><span data-ttu-id="f13ab-725">Esse atributo define as informações sobre a versão do servidor.</span><span class="sxs-lookup"><span data-stu-id="f13ab-725">This attribute defines the version information of the server.</span></span> <span data-ttu-id="f13ab-726">Este número de versão se aplica a todas as funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="f13ab-726">This version number applies to all server roles.</span></span> <span data-ttu-id="f13ab-727">É um número inteiro monotonously que aumenta em incrementos com cada lançamento oficial do produto.</span><span class="sxs-lookup"><span data-stu-id="f13ab-727">It is a monotonously increasing integer that increments with each official product release.</span></span></p>
<p><span data-ttu-id="f13ab-728">Os valores válidos possíveis são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="f13ab-728">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="f13ab-729">Indefinido: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="f13ab-729">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="f13ab-730">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="f13ab-730">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="f13ab-731">                 Live Communications Server 2005 com SP1</span><span class="sxs-lookup"><span data-stu-id="f13ab-731">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="f13ab-732">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="f13ab-732">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="f13ab-733">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="f13ab-733">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="f13ab-734">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="f13ab-734">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="f13ab-735">6: Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f13ab-735">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f13ab-736">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-736">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-737">msRTCSIP-SourceObjectType</span><span class="sxs-lookup"><span data-stu-id="f13ab-737">msRTCSIP-SourceObjectType</span></span></p></td>
<td><p><span data-ttu-id="f13ab-738">Esse atributo de valor único de tipo inteiro especifica o tipo de objeto ao qual o <strong>msDS-SourceObjectDN</strong> aponta, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="f13ab-738">This single-valued attribute of integer type specifies the type of object the <strong>msDS-SourceObjectDN</strong> points to, as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="f13ab-739">nulo | 0x00000001: representa um objeto de usuário principal do Windows NT Server de uma floresta diferente</span><span class="sxs-lookup"><span data-stu-id="f13ab-739">null | 0x00000001: Represents a Windows NT Server principal user object from a different forest</span></span></p></li>
<li><p><span data-ttu-id="f13ab-740">Os atributos a seguir representam um tipo de grupo de uma floresta diferente para expansão do grupo de distribuição:</span><span class="sxs-lookup"><span data-stu-id="f13ab-740">The following attributes represent a group type from a different forest for distribution group expansion:</span></span></p>
<ul>
<li><p><span data-ttu-id="f13ab-741">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="f13ab-741">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="f13ab-742">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="f13ab-742">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="f13ab-743">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="f13ab-743">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="f13ab-744">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="f13ab-744">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="f13ab-745">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span><span class="sxs-lookup"><span data-stu-id="f13ab-745">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span></span></p></li>
<li><p><span data-ttu-id="f13ab-746">0x90000000: representa um objeto de atendente automático ou de acesso do assinante da mesma floresta ou de uma floresta diferente</span><span class="sxs-lookup"><span data-stu-id="f13ab-746">0x90000000: Represents an Auto-Attendant or subscriber access object from the same forest or a different forest</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="f13ab-747">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-747">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-748">msRTCSIP-SubscriptionAuthRequired (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-748">msRTCSIP-SubscriptionAuthRequired (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="f13ab-749">Novo no Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="f13ab-749">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="f13ab-750">Obsoleto no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="f13ab-750">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-751">msRTCSIP-TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="f13ab-751">msRTCSIP-TargetHomeServer</span></span></p></td>
<td><p><span data-ttu-id="f13ab-752">Esse atributo permite mover um usuário ou objeto de contato de um pool do Lync Server para outro.</span><span class="sxs-lookup"><span data-stu-id="f13ab-752">This attribute enables you to move a user or contact object from one Lync Server pool to another.</span></span> <span data-ttu-id="f13ab-753">Esse atributo é adicionado à classe Contact, porque na topologia de floresta central, objetos de contato, não objetos de usuário, são SIP habilitados.</span><span class="sxs-lookup"><span data-stu-id="f13ab-753">This attribute is added to the contact class, because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="f13ab-754">O valor válido é o DN do servidor de edição padrão ou do pool de front-end para o qual um usuário deve ser movido.</span><span class="sxs-lookup"><span data-stu-id="f13ab-754">The valid value is the DN of the destination Standard Edition server or Front End pool to which a user is to be moved.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-755">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="f13ab-755">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-756">msRTCSIP-TargetPhoneNumber (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-756">msRTCSIP-TargetPhoneNumber (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-757">Este atributo de cadeia de caracteres de valor único contém um padrão ou um intervalo de números de telefone para direcionar para os gateways especificados definidos em <strong>msRTCSIP-gateways</strong>.</span><span class="sxs-lookup"><span data-stu-id="f13ab-757">This single-valued string attribute contains a phone number pattern or range to route to the specified gateways defined in <strong>msRTCSIP-Gateways</strong>.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-758">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-758">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-759">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="f13ab-759">msRTCSIP-TargetUserPolicies</span></span></p></td>
<td><p><span data-ttu-id="f13ab-760">Esse atributo armazena pares de nome-valor para políticas de destino para usuários do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f13ab-760">This attribute stores name-value pairs for target policies for Lync Server users.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-761">Novo no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-761">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-762">msRTCSIP-Tenantid</span><span class="sxs-lookup"><span data-stu-id="f13ab-762">msRTCSIP-TenantId</span></span></p></td>
<td><p><span data-ttu-id="f13ab-763">Esse atributo armazena o identificador exclusivo de um locatário.</span><span class="sxs-lookup"><span data-stu-id="f13ab-763">This attribute stores the unique identifier for a tenant.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-764">Novo no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-764">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-765">msRTCSIP-tradução (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-765">msRTCSIP-Translation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-766">Esse atributo é usado pelo recurso de voz do Lync Server e contém a cadeia de caracteres de tradução para aplicar o número discado, se for encontrada uma correspondência.</span><span class="sxs-lookup"><span data-stu-id="f13ab-766">This attribute is used by the voice feature of Lync Server and contains the translation string to apply on the dialed number, if a match is found.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-767">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-767">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="f13ab-768">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-768">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-769">msRTCSIP-TrustedMCUData</span><span class="sxs-lookup"><span data-stu-id="f13ab-769">msRTCSIP-TrustedMCUData</span></span></p></td>
<td><p><span data-ttu-id="f13ab-770">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="f13ab-770">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-771">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-771">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-772">msRTCSIP-TrustedMCUFQDN</span><span class="sxs-lookup"><span data-stu-id="f13ab-772">msRTCSIP-TrustedMCUFQDN</span></span></p></td>
<td><p><span data-ttu-id="f13ab-773">Esse atributo é um valor de cadeia de caracteres que contém o FQDN do MCU.</span><span class="sxs-lookup"><span data-stu-id="f13ab-773">This attribute is a string value that contains the FQDN of the MCU.</span></span> <span data-ttu-id="f13ab-774">Esse é um atributo de valor único.</span><span class="sxs-lookup"><span data-stu-id="f13ab-774">This is a single-valued attribute.</span></span> <span data-ttu-id="f13ab-775">O valor válido para cada segmento é de 63 caracteres; o valor válido para o FQDN inteiro é de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="f13ab-775">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-776">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-776">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-777">msRTCSIP-TrustedProxyData</span><span class="sxs-lookup"><span data-stu-id="f13ab-777">msRTCSIP-TrustedProxyData</span></span></p></td>
<td><p><span data-ttu-id="f13ab-778">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="f13ab-778">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-779">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-779">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-780">msRTCSIP-TrustedProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="f13ab-780">msRTCSIP-TrustedProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="f13ab-781">Esse atributo é um valor de cadeia de caracteres que contém o FQDN do servidor que está executando o servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="f13ab-781">This attribute is a string value that contains the FQDN of the server running Proxy Server.</span></span> <span data-ttu-id="f13ab-782">Esse atributo tem valor único.</span><span class="sxs-lookup"><span data-stu-id="f13ab-782">This attribute is single-valued.</span></span> <span data-ttu-id="f13ab-783">O valor válido para cada segmento é de 63 caracteres; o valor válido para o FQDN inteiro é de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="f13ab-783">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-784">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-784">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-785">msRTCSIP-TrustedServerData</span><span class="sxs-lookup"><span data-stu-id="f13ab-785">msRTCSIP-TrustedServerData</span></span></p></td>
<td><p><span data-ttu-id="f13ab-786">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="f13ab-786">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-787">msRTCSIP-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="f13ab-787">msRTCSIP-TrustedServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="f13ab-788">Esse atributo é um atributo de valor único que representa o FQDN de um servidor confiável.</span><span class="sxs-lookup"><span data-stu-id="f13ab-788">This attribute is a single-valued attribute that represents the FQDN of a trusted server.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-789">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="f13ab-789">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-790">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="f13ab-790">msRTCSIP-TrustedServerVersion</span></span></p></td>
<td><p><span data-ttu-id="f13ab-791">Esse atributo especifica o número da versão de um servidor na lista de servidores confiáveis.</span><span class="sxs-lookup"><span data-stu-id="f13ab-791">This attribute specifies the version number of a server in the trusted server list.</span></span></p>
<p><span data-ttu-id="f13ab-792">Os valores válidos possíveis são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="f13ab-792">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="f13ab-793">NULL: Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="f13ab-793">NULL: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="f13ab-794">2: Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="f13ab-794">2: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="f13ab-795">3: Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="f13ab-795">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="f13ab-796">4: Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="f13ab-796">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="f13ab-797">5: Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="f13ab-797">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="f13ab-798">6: Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f13ab-798">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f13ab-799">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="f13ab-799">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-800">msRTCSIP-TrustedServiceFlags</span><span class="sxs-lookup"><span data-stu-id="f13ab-800">msRTCSIP-TrustedServiceFlags</span></span></p></td>
<td><p><span data-ttu-id="f13ab-801">Esse atributo define as opções que são habilitadas para o serviço confiável.</span><span class="sxs-lookup"><span data-stu-id="f13ab-801">This attribute defines the options that are enabled for the trusted service.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-802">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f13ab-802">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-803">msRTCSIP-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="f13ab-803">msRTCSIP-TrustedServiceLinks</span></span></p></td>
<td><p><span data-ttu-id="f13ab-804">Esse atributo com vários valores contém uma lista de nomes diferenciados (DN) que fazem referência a um objeto de serviço confiável, como um serviço de autenticação de retransmissão de mídia.</span><span class="sxs-lookup"><span data-stu-id="f13ab-804">This multi-valued attribute contains a list of distinguished names (DN) that reference a trusted service object, such as a Media Relay Authentication Service.</span></span> <span data-ttu-id="f13ab-805">Um serviço de autenticação de retransmissão de mídia (posicionado fisicamente no servidor de borda executando o serviço de conferência A/V) deve estar associado a um pool para dar suporte a cenários de áudio para usuários remotos.</span><span class="sxs-lookup"><span data-stu-id="f13ab-805">A Media Relay Authentication Service (physically collocated on the Edge Server running the A/V Conferencing service) must be associated with a pool to support audio scenarios for remote users.</span></span></p>
<p><span data-ttu-id="f13ab-806">O link regressivo correspondente a este atributo de link de encaminhamento é <strong>msRTCSIP-ServerBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="f13ab-806">The corresponding back link to this forward link attribute is <strong>msRTCSIP-ServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-807">UC</span><span class="sxs-lookup"><span data-stu-id="f13ab-807">UC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-808">msRTCSIP-TrustedServicePort</span><span class="sxs-lookup"><span data-stu-id="f13ab-808">msRTCSIP-TrustedServicePort</span></span></p></td>
<td><p><span data-ttu-id="f13ab-809">Esse atributo é um inteiro que define o número da porta usada para se conectar a este serviço GRUU.</span><span class="sxs-lookup"><span data-stu-id="f13ab-809">This attribute is an integer that defines the port number used to connect to this GRUU service.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-810">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-810">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-811">msRTCSIP-TrustedServiceType</span><span class="sxs-lookup"><span data-stu-id="f13ab-811">msRTCSIP-TrustedServiceType</span></span></p></td>
<td><p><span data-ttu-id="f13ab-812">Esse atributo é um valor de cadeia de caracteres que define o tipo de serviço GRUU que ele representa.</span><span class="sxs-lookup"><span data-stu-id="f13ab-812">This attribute is a string value that defines the type of GRUU service it represents.</span></span></p>
<p><span data-ttu-id="f13ab-813">Os tipos de serviço GRUU válidos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="f13ab-813">The valid GRUU service types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="f13ab-814">MediationServer</span><span class="sxs-lookup"><span data-stu-id="f13ab-814">MediationServer</span></span></p></li>
<li><p><span data-ttu-id="f13ab-815">Gateway</span><span class="sxs-lookup"><span data-stu-id="f13ab-815">Gateway</span></span></p></li>
<li><p><span data-ttu-id="f13ab-816">Serviço de autenticação de retransmissão de mídia (MRAS)</span><span class="sxs-lookup"><span data-stu-id="f13ab-816">Media Relay Authentication Service (MRAS)</span></span></p></li>
<li><p><span data-ttu-id="f13ab-817">QoSM</span><span class="sxs-lookup"><span data-stu-id="f13ab-817">QoSM</span></span></p></li>
<li><p><span data-ttu-id="f13ab-818">msRTCSIP-userextension CWA</span><span class="sxs-lookup"><span data-stu-id="f13ab-818">msRTCSIP-UserExtension CWA</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f13ab-819">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-819">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-820">msRTCSIP-TrustedWebComponentsServerData</span><span class="sxs-lookup"><span data-stu-id="f13ab-820">msRTCSIP-TrustedWebComponentsServerData</span></span></p></td>
<td><p><span data-ttu-id="f13ab-821">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="f13ab-821">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-822">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-822">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-823">msRTCSIP-TrustedWebComponentsServerFQDN</span><span class="sxs-lookup"><span data-stu-id="f13ab-823">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="f13ab-824">Esse atributo é um valor de cadeia de caracteres que contém o FQDN do IIS que executa serviços Web do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f13ab-824">This attribute is a string value that contains the FQDN of the IIS running Lync Server Web Services.</span></span> <span data-ttu-id="f13ab-825">Esse é um atributo de valor único.</span><span class="sxs-lookup"><span data-stu-id="f13ab-825">This is a single-valued attribute.</span></span> <span data-ttu-id="f13ab-826">O valor válido para cada segmento é de 63 caracteres; o valor válido para o FQDN inteiro é de 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="f13ab-826">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-827">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-827">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-828">msRTCSIP-UCFlags (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-828">msRTCSIP-UCFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-829">Esse atributo define opções de comunicação unificadas diferentes que são habilitadas globalmente para todos os objetos de contato ou usuário.</span><span class="sxs-lookup"><span data-stu-id="f13ab-829">This attribute defines different UC options that are enabled globally to all user or contact objects.</span></span> <span data-ttu-id="f13ab-830">Esse atributo é um valor de máscara de bits do tipo inteiro.</span><span class="sxs-lookup"><span data-stu-id="f13ab-830">This attribute is a bit-mask value of integer type.</span></span> <span data-ttu-id="f13ab-831">Cada opção é representada pela presença de um pouco.</span><span class="sxs-lookup"><span data-stu-id="f13ab-831">Each option is represented by the presence of a bit.</span></span></p>
<p><span data-ttu-id="f13ab-832">O possível valor válido (e a posição de bit associado) são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="f13ab-832">The possible valid value (and associated bit position) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="f13ab-833">4: UsePerUserUCPolicy (posição do bit 2)</span><span class="sxs-lookup"><span data-stu-id="f13ab-833">4: UsePerUserUCPolicy (bit position 2)</span></span></p></li>
</ul>
<p><span data-ttu-id="f13ab-834">Quando este bit é definido, a política de UC é definida por usuário.</span><span class="sxs-lookup"><span data-stu-id="f13ab-834">When this bit is set, the UC policy is defined per user.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-835">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-835">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-836">msRTCSIP-UCPolicy (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-836">msRTCSIP-UCPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-837">Esse atributo com valor único contém o DN (nome distinto) da política de UC que o administrador atribuiu para este usuário.</span><span class="sxs-lookup"><span data-stu-id="f13ab-837">This single-valued attribute contains the distinguished name (DN) of the UC policy that the administrator has assigned for this user.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-838">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-838">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-839">msRTCSIP-userdomainlist (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-839">msRTCSIP-UserDomainList (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="f13ab-840">Esse atributo fornece uma lista de todos os domínios em uma floresta que hospeda usuários habilitados para SIP.</span><span class="sxs-lookup"><span data-stu-id="f13ab-840">This attribute provides a list of all the domains in a forest that host SIP-enabled users.</span></span> <span data-ttu-id="f13ab-841">O padrão é uma lista vazia, indicando que todos os domínios na floresta são habilitados para SIP.</span><span class="sxs-lookup"><span data-stu-id="f13ab-841">The default is an empty list, indicating that all domains in the forest are SIP-enabled.</span></span></p>
<p><span data-ttu-id="f13ab-842">Os valores válidos são várias cadeias de caracteres que representam os nomes de domínio de domínios individuais.</span><span class="sxs-lookup"><span data-stu-id="f13ab-842">Valid values are multiple strings representing the domain names of individual domains.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-843">Novo no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="f13ab-843">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="f13ab-844">Obsoleto no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-844">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-845">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="f13ab-845">msRTCSIP-UserEnabled</span></span></p></td>
<td><p><span data-ttu-id="f13ab-846">Esse atributo determina se o usuário está habilitado no momento para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f13ab-846">This attribute determines whether the user is currently enabled for Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-847">msRTCSIP-userextension</span><span class="sxs-lookup"><span data-stu-id="f13ab-847">msRTCSIP-UserExtension</span></span></p></td>
<td><p><span data-ttu-id="f13ab-848">Este atributo de valores múltiplos contém uma lista de pares de nomes e valores no formato de &quot;nome = valor. &quot; Esse atributo está marcado para replicação de catálogo global.</span><span class="sxs-lookup"><span data-stu-id="f13ab-848">This multi-valued attribute contains a list of name-value pairs in the format of &quot;name=value.&quot; This attribute is marked for global catalog replication.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-849">Novo no Live Communications Server 2005 com SP1.</span><span class="sxs-lookup"><span data-stu-id="f13ab-849">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-850">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="f13ab-850">msRTCSIP-UserLocationProfile</span></span></p></td>
<td><p><span data-ttu-id="f13ab-851">Esse atributo contém o nome diferenciado (DN) que aponta para um objeto de perfil de local.</span><span class="sxs-lookup"><span data-stu-id="f13ab-851">This attribute contains the distinguished name (DN) that points to a location profile object.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-852">Novo no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f13ab-852">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-853">msRTCSIP-políticas do</span><span class="sxs-lookup"><span data-stu-id="f13ab-853">msRTCSIP-UserPolicies</span></span></p></td>
<td><p><span data-ttu-id="f13ab-854">Esse atributo armazena pares de nome-valor para políticas de usuário.</span><span class="sxs-lookup"><span data-stu-id="f13ab-854">This attribute stores name-value pairs for user policies.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-855">Novo no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f13ab-855">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-856">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="f13ab-856">msRTCSIP-UserPolicy</span></span></p></td>
<td><p><span data-ttu-id="f13ab-857">Esse é um atributo com valores múltiplos que contém uma lista de nomes diferenciados com binário (DN_WITH_BINARY) apontando para políticas de usuários globais de tipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="f13ab-857">This is a multi-valued attribute containing a list of distinguished names with binary (DN_WITH_BINARY) pointing to global user policies of different types.</span></span> <span data-ttu-id="f13ab-858">A parte binária indica o tipo de política para a qual a parte DN aponta.</span><span class="sxs-lookup"><span data-stu-id="f13ab-858">The binary part indicates the type of policy to which the DN portion points.</span></span></p>
<p><span data-ttu-id="f13ab-859">Os valores binários válidos são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="f13ab-859">The valid binary values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="f13ab-860">0x00000001: política de reunião</span><span class="sxs-lookup"><span data-stu-id="f13ab-860">0x00000001: Meeting policy</span></span></p></li>
<li><p><span data-ttu-id="f13ab-861">0x00000002: política de UC</span><span class="sxs-lookup"><span data-stu-id="f13ab-861">0x00000002: UC policy</span></span></p></li>
<li><p><span data-ttu-id="f13ab-862">0x00000005: política de presença</span><span class="sxs-lookup"><span data-stu-id="f13ab-862">0x00000005: Presence policy</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f13ab-863">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-863">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-864">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="f13ab-864">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="f13ab-865">Esta é a ID do grupo de roteamento SIP.</span><span class="sxs-lookup"><span data-stu-id="f13ab-865">This is the SIP routing group ID.</span></span> <span data-ttu-id="f13ab-866">Os usuários no mesmo grupo serão registrados no mesmo servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="f13ab-866">Users in the same group will register to the same Front End Server.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-867">Novo no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f13ab-867">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-868">msRTCSIP-WebComponentsData</span><span class="sxs-lookup"><span data-stu-id="f13ab-868">msRTCSIP-WebComponentsData</span></span></p></td>
<td><p><span data-ttu-id="f13ab-869">Esse é um atributo com vários valores.</span><span class="sxs-lookup"><span data-stu-id="f13ab-869">This is a multi-valued attribute.</span></span> <span data-ttu-id="f13ab-870">Esse atributo é reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="f13ab-870">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-871">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-871">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-872">msRTCSIP-WebComponentsPoolAddress</span><span class="sxs-lookup"><span data-stu-id="f13ab-872">msRTCSIP-WebComponentsPoolAddress</span></span></p></td>
<td><p><span data-ttu-id="f13ab-873">Esse atributo de valor único aponta para o servidor do pool ou da edição padrão ao qual os componentes Web pertencem.</span><span class="sxs-lookup"><span data-stu-id="f13ab-873">This single-valued attribute points to the pool or Standard Edition server to which the web components belong.</span></span></p>
<p><span data-ttu-id="f13ab-874">Link encaminhar: <strong>ID do link 11028</strong></span><span class="sxs-lookup"><span data-stu-id="f13ab-874">Forward link: <strong>Link ID 11028</strong></span></span></p>
<p><span data-ttu-id="f13ab-875">O link regressivo correspondente a este atributo de link de encaminhamento é <strong>msRTCSIP-WebComponentsServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="f13ab-875">The corresponding back link to this forward link attribute is <strong>msRTCSIP-WebComponentsServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-876">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-876">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-877">msRTCSIP-WebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="f13ab-877">msRTCSIP-WebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="f13ab-878">Esse atributo é uma lista de vários valores de nomes distintos.</span><span class="sxs-lookup"><span data-stu-id="f13ab-878">This attribute is a multi-valued list of distinguished names.</span></span> <span data-ttu-id="f13ab-879">Esse atributo contém uma lista de todos os servidores da Web associados a este pool.</span><span class="sxs-lookup"><span data-stu-id="f13ab-879">This attribute contains a list of all Web servers associated with this pool.</span></span></p>
<p><span data-ttu-id="f13ab-880">Link para trás: <strong>ID do link 11029</strong></span><span class="sxs-lookup"><span data-stu-id="f13ab-880">Back link: <strong>Link ID 11029</strong></span></span></p>
<p><span data-ttu-id="f13ab-881">O link encaminhamento correspondente para esse link regressivo é <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="f13ab-881">The corresponding forward link to this back link is <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-882">Novo no Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="f13ab-882">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-883">msRTCSIP-WMIInstanceId (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="f13ab-883">msRTCSIP-WMIInstanceId (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="f13ab-884">Novo no Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="f13ab-884">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="f13ab-885">Obsoleto no Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="f13ab-885">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-886">OtherIPPhone</span><span class="sxs-lookup"><span data-stu-id="f13ab-886">OtherIPPhone</span></span></p></td>
<td><p><span data-ttu-id="f13ab-887">Esse atributo existente do Active Directory é usado por telefonia para especificar a lista de endereços TCP/IP alternativos para um telefone.</span><span class="sxs-lookup"><span data-stu-id="f13ab-887">This existing Active Directory attribute is used by telephony to specify the list of alternate TCP/IP addresses for a phone.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-888">Novo no sistema operacional Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="f13ab-888">New in Windows Server 2008 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-889">PhoneOfficeOther</span><span class="sxs-lookup"><span data-stu-id="f13ab-889">PhoneOfficeOther</span></span></p></td>
<td><p><span data-ttu-id="f13ab-890">Esse atributo existente do Active Directory é usado pelos componentes de voz no Lync Server, somente para objetos de contato, com a finalidade de direcionar chamadas para o atendedor automático da Unificação de mensagens e os números de acesso do Assinante.</span><span class="sxs-lookup"><span data-stu-id="f13ab-890">This existing Active Directory attribute is used by the voice components in Lync Server, for contact objects only, for the purpose of routing calls to the unified messaging auto-attendant and subscriber access numbers.</span></span> <span data-ttu-id="f13ab-891">O endereço de encaminhamento de chamadas incondicionais é armazenado nesse atributo de vários valores.</span><span class="sxs-lookup"><span data-stu-id="f13ab-891">The unconditional call forwarding address is stored in this multi-valued attribute.</span></span> <span data-ttu-id="f13ab-892">Esta conta é criada para o propósito específico de acesso automático e do Assinante.</span><span class="sxs-lookup"><span data-stu-id="f13ab-892">This account is created for the specific purpose of auto-attendant and subscriber access.</span></span> <span data-ttu-id="f13ab-893">Os atributos da conta não devem ser modificados pelos administradores.</span><span class="sxs-lookup"><span data-stu-id="f13ab-893">This account’s attributes should not be modified by administrators.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-894">Novo no sistema operacional Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="f13ab-894">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f13ab-895">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="f13ab-895">ProxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="f13ab-896">Este atributo de vários valores do Active Directory existente faz parte do esquema base do Active Directory introduzido no Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="f13ab-896">This existing Active Directory multi-valued attribute is part of the base Active Directory schema introduced in Windows 2000.</span></span> <span data-ttu-id="f13ab-897">Esse atributo contém os vários endereços X400, X500 e SMTP do email do usuário.</span><span class="sxs-lookup"><span data-stu-id="f13ab-897">This attribute contains the various X400, X500, and SMTP addresses of the user’s email.</span></span> <span data-ttu-id="f13ab-898">No Live Communications Server 2003 e posterior, o URI SIP do usuário é adicionado a essa lista usando a &quot;marca SIP&quot; :.</span><span class="sxs-lookup"><span data-stu-id="f13ab-898">In Live Communications Server 2003 and later, the user’s SIP URI is added to this list, using the &quot;sip:&quot; tag.</span></span></p>
<p><span data-ttu-id="f13ab-899">Os seguintes aplicativos pesquisam o URI do SIP do usuário deste atributo:</span><span class="sxs-lookup"><span data-stu-id="f13ab-899">The following applications search the user’s SIP URI from this attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="f13ab-900">Cliente de mensagens e colaboração do Microsoft Office Outlook 2003</span><span class="sxs-lookup"><span data-stu-id="f13ab-900">Microsoft Office Outlook 2003 messaging and collaboration client</span></span></p></li>
<li><p><span data-ttu-id="f13ab-901">Microsoft Office SharePoint Server 2007</span><span class="sxs-lookup"><span data-stu-id="f13ab-901">Microsoft Office SharePoint Server 2007</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f13ab-902">Novo no sistema operacional Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="f13ab-902">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f13ab-903">TelephoneNumber</span><span class="sxs-lookup"><span data-stu-id="f13ab-903">TelephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="f13ab-904">Esse atributo existente do Active Directory contém o número de telefone do usuário.</span><span class="sxs-lookup"><span data-stu-id="f13ab-904">This existing Active Directory attribute contains the telephone number for the user.</span></span></p></td>
<td><p><span data-ttu-id="f13ab-905">Novo no sistema operacional Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="f13ab-905">New in Windows 2000 operating system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

