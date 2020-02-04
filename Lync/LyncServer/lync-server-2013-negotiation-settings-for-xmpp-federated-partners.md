---
title: 'Lync Server 2013: Configurações de negociação para parceiros de XMPP federados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Negotiation settings for XMPP federated partners
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552456(v=OCS.15)
ms:contentKeyID: 48679567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 995ee34d0a2dcf28ca6aa4f8158d0e08d1533191
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765932"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="86200-102">Configurações de negociação para parceiros de XMPP federados no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86200-102">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86200-103">_**Tópico da última modificação:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="86200-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="86200-104">As configurações dos tipos de negociação na configuração de um parceiro do XMPP têm uma ampla variedade de combinações possíveis.</span><span class="sxs-lookup"><span data-stu-id="86200-104">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="86200-105">Nem todas essas combinações são válidas.</span><span class="sxs-lookup"><span data-stu-id="86200-105">Not all of these combinations are valid.</span></span> <span data-ttu-id="86200-106">A tabela detalhada neste tópico definirá as configurações válidas e inválidas.</span><span class="sxs-lookup"><span data-stu-id="86200-106">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="86200-107">As configurações comuns são apresentadas na primeira tabela, a segunda tabela que detalha todas as combinações possíveis.</span><span class="sxs-lookup"><span data-stu-id="86200-107">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="86200-108">Observe que você não pode ter a *autenticação simples e a camada de segurança* (SASL) **, a menos** que o TLS ( *Transport Layer Security* ) também esteja disponível.</span><span class="sxs-lookup"><span data-stu-id="86200-108">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="86200-109">SASL é enviada em um formato não criptografado (legível) e nunca deve ser transmitida, a menos que seja protegida por outro meio, como TLS.</span><span class="sxs-lookup"><span data-stu-id="86200-109">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="86200-110">Métodos comuns de negociação de Federação XMPP</span><span class="sxs-lookup"><span data-stu-id="86200-110">Common XMPP Federation Negotiation Methods</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86200-111">Transport Layer Security (TLS)</span><span class="sxs-lookup"><span data-stu-id="86200-111">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="86200-112">Camada de segurança e autenticação simples (SASL)</span><span class="sxs-lookup"><span data-stu-id="86200-112">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="86200-113">Autenticação Dialback</span><span class="sxs-lookup"><span data-stu-id="86200-113">Dialback Authentication</span></span></th>
<th><span data-ttu-id="86200-114">Método (s) de autenticação esperado (s)</span><span class="sxs-lookup"><span data-stu-id="86200-114">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="86200-115">Observações</span><span class="sxs-lookup"><span data-stu-id="86200-115">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86200-116">Obrigatório </span><span class="sxs-lookup"><span data-stu-id="86200-116">Required</span></span></p></td>
<td><p><span data-ttu-id="86200-117">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="86200-117">Required</span></span></p></td>
<td><p><span data-ttu-id="86200-118">Falso</span><span class="sxs-lookup"><span data-stu-id="86200-118">False</span></span></p></td>
<td><p><span data-ttu-id="86200-119">SASL sobre TLS</span><span class="sxs-lookup"><span data-stu-id="86200-119">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="86200-120">O TLS e o SASL são necessários ajuda a garantir que o fluxo de mensagens SASL seja seguro.</span><span class="sxs-lookup"><span data-stu-id="86200-120">TLS and SASL required helps to ensure that the SASL message stream is secure.</span></span> <span data-ttu-id="86200-121">Dialback não está disponível e não pode ser usado para um método de fallback se o parceiro federado do XMPP não definiu o TLS como obrigatório ou opcional.</span><span class="sxs-lookup"><span data-stu-id="86200-121">Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86200-122">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="86200-122">Required</span></span></p></td>
<td><p><span data-ttu-id="86200-123">Opcional</span><span class="sxs-lookup"><span data-stu-id="86200-123">Optional</span></span></p></td>
<td><p><span data-ttu-id="86200-124">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="86200-124">True</span></span></p></td>
<td><p><span data-ttu-id="86200-125">SASL sobre TLS, TLS Dialback, TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="86200-125">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="86200-126">Ao exigir TLS, se o parceiro federado do XMPP tiver sido definido SASL para opcional ou obrigatório, o SASL será usado.</span><span class="sxs-lookup"><span data-stu-id="86200-126">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used.</span></span> <span data-ttu-id="86200-127">Se SASL não estiver disponível, o Dialback em TLS será usado.</span><span class="sxs-lookup"><span data-stu-id="86200-127">If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86200-128">Opcional </span><span class="sxs-lookup"><span data-stu-id="86200-128">Optional</span></span></p></td>
<td><p><span data-ttu-id="86200-129">Opcional</span><span class="sxs-lookup"><span data-stu-id="86200-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="86200-130">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="86200-130">True</span></span></p></td>
<td><p><span data-ttu-id="86200-131">SASL sobre TLS, TLS Dialback, TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="86200-131">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="86200-132">Embora seja bastante flexível nos métodos de negociação oferecidos, essas configurações dependem das configurações do parceiro de Federação do XMPP.</span><span class="sxs-lookup"><span data-stu-id="86200-132">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings.</span></span> <span data-ttu-id="86200-133">Se o parceiro tiver o TLS opcional ou obrigatório, mas o SASL não for compatível, o TLS Dialback estará disponível.</span><span class="sxs-lookup"><span data-stu-id="86200-133">If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available.</span></span> <span data-ttu-id="86200-134">Se o parceiro tiver TLS e SASL definido como opcional ou obrigatório, a seleção ideal de TLS sobre o SASL será usada.</span><span class="sxs-lookup"><span data-stu-id="86200-134">If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86200-135">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="86200-135">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="86200-136">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="86200-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="86200-137">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="86200-137">True</span></span></p></td>
<td><p><span data-ttu-id="86200-138">TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="86200-138">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="86200-139">Em muitos casos, o TCP Dialback é a única solução possível.</span><span class="sxs-lookup"><span data-stu-id="86200-139">In many cases, TCP Dialback is the only possible solution.</span></span> <span data-ttu-id="86200-140">Menos desejável do que outras opções, ele fornece um certo nível de confiança.</span><span class="sxs-lookup"><span data-stu-id="86200-140">Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="86200-141">Matriz de métodos de negociação de Federação XMPP-concluída</span><span class="sxs-lookup"><span data-stu-id="86200-141">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86200-142">Transport Layer Security (TLS)</span><span class="sxs-lookup"><span data-stu-id="86200-142">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="86200-143">Camada de segurança e autenticação simples (SASL)</span><span class="sxs-lookup"><span data-stu-id="86200-143">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="86200-144">Autenticação Dialback</span><span class="sxs-lookup"><span data-stu-id="86200-144">Dialback Authentication</span></span></th>
<th><span data-ttu-id="86200-145">Método de autenticação esperado</span><span class="sxs-lookup"><span data-stu-id="86200-145">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="86200-146">Observações, aviso ou erro para uma configuração inválida</span><span class="sxs-lookup"><span data-stu-id="86200-146">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86200-147">Obrigatório </span><span class="sxs-lookup"><span data-stu-id="86200-147">Required</span></span></p></td>
<td><p><span data-ttu-id="86200-148">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="86200-148">Required</span></span></p></td>
<td><p><span data-ttu-id="86200-149">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="86200-149">True</span></span></p></td>
<td><p><span data-ttu-id="86200-150">SASL sobre TLS</span><span class="sxs-lookup"><span data-stu-id="86200-150">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="86200-151">O Dialback não funcionará se o SASL e o TLS forem obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="86200-151">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86200-152">Obrigatório </span><span class="sxs-lookup"><span data-stu-id="86200-152">Required</span></span></p></td>
<td><p><span data-ttu-id="86200-153">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="86200-153">Required</span></span></p></td>
<td><p><span data-ttu-id="86200-154">Falso</span><span class="sxs-lookup"><span data-stu-id="86200-154">False</span></span></p></td>
<td><p><span data-ttu-id="86200-155">SASL sobre TLS</span><span class="sxs-lookup"><span data-stu-id="86200-155">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86200-156">Opcional</span><span class="sxs-lookup"><span data-stu-id="86200-156">Optional</span></span></p></td>
<td><p><span data-ttu-id="86200-157">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="86200-157">Required</span></span></p></td>
<td><p><span data-ttu-id="86200-158">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="86200-158">True</span></span></p></td>
<td><p><span data-ttu-id="86200-159">SASL sobre TLS, TLS Dialback, TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="86200-159">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="86200-160">SASL requer TLS.</span><span class="sxs-lookup"><span data-stu-id="86200-160">SASL requires TLS.</span></span> <span data-ttu-id="86200-161">Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="86200-161">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86200-162">Opcional</span><span class="sxs-lookup"><span data-stu-id="86200-162">Optional</span></span></p></td>
<td><p><span data-ttu-id="86200-163">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="86200-163">Required</span></span></p></td>
<td><p><span data-ttu-id="86200-164">Falso</span><span class="sxs-lookup"><span data-stu-id="86200-164">False</span></span></p></td>
<td><p><span data-ttu-id="86200-165">SASL sobre TLS</span><span class="sxs-lookup"><span data-stu-id="86200-165">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="86200-166">SASL requer TLS.</span><span class="sxs-lookup"><span data-stu-id="86200-166">SASL requires TLS.</span></span> <span data-ttu-id="86200-167">Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="86200-167">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86200-168">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="86200-168">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="86200-169">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="86200-169">Required</span></span></p></td>
<td><p><span data-ttu-id="86200-170">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="86200-170">True</span></span></p></td>
<td><p><span data-ttu-id="86200-171">TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="86200-171">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="86200-172">SASL requer TLS.</span><span class="sxs-lookup"><span data-stu-id="86200-172">SASL requires TLS.</span></span> <span data-ttu-id="86200-173">Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="86200-173">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86200-174">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="86200-174">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="86200-175">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="86200-175">Required</span></span></p></td>
<td><p><span data-ttu-id="86200-176">Falso</span><span class="sxs-lookup"><span data-stu-id="86200-176">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="86200-177">Configuração inválida</span><span class="sxs-lookup"><span data-stu-id="86200-177">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="86200-178">Como a SASL requer TLS, e o TLS não está disponível, o SASL/TLS não pode ser bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="86200-178">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed.</span></span> <span data-ttu-id="86200-179">TCP Dialback é definido como false e não pode ser usado.</span><span class="sxs-lookup"><span data-stu-id="86200-179">TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86200-180">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="86200-180">Required</span></span></p></td>
<td><p><span data-ttu-id="86200-181">Opcional</span><span class="sxs-lookup"><span data-stu-id="86200-181">Optional</span></span></p></td>
<td><p><span data-ttu-id="86200-182">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="86200-182">True</span></span></p></td>
<td><p><span data-ttu-id="86200-183">SASL sobre TLS, TLS Dialback</span><span class="sxs-lookup"><span data-stu-id="86200-183">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86200-184">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="86200-184">Required</span></span></p></td>
<td><p><span data-ttu-id="86200-185">Opcional</span><span class="sxs-lookup"><span data-stu-id="86200-185">Optional</span></span></p></td>
<td><p><span data-ttu-id="86200-186">Falso</span><span class="sxs-lookup"><span data-stu-id="86200-186">False</span></span></p></td>
<td><p><span data-ttu-id="86200-187">SASL sobre TLS</span><span class="sxs-lookup"><span data-stu-id="86200-187">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86200-188">Opcional </span><span class="sxs-lookup"><span data-stu-id="86200-188">Optional</span></span></p></td>
<td><p><span data-ttu-id="86200-189">Opcional</span><span class="sxs-lookup"><span data-stu-id="86200-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="86200-190">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="86200-190">True</span></span></p></td>
<td><p><span data-ttu-id="86200-191">SASL sobre TLS, TLS Dialback, TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="86200-191">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="86200-192">SASL requer TLS.</span><span class="sxs-lookup"><span data-stu-id="86200-192">SASL requires TLS.</span></span> <span data-ttu-id="86200-193">Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="86200-193">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86200-194">Opcional </span><span class="sxs-lookup"><span data-stu-id="86200-194">Optional</span></span></p></td>
<td><p><span data-ttu-id="86200-195">Opcional</span><span class="sxs-lookup"><span data-stu-id="86200-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="86200-196">Falso</span><span class="sxs-lookup"><span data-stu-id="86200-196">False</span></span></p></td>
<td><p><span data-ttu-id="86200-197">SASL sobre TLS</span><span class="sxs-lookup"><span data-stu-id="86200-197">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="86200-198">SASL requer TLS.</span><span class="sxs-lookup"><span data-stu-id="86200-198">SASL requires TLS.</span></span> <span data-ttu-id="86200-199">Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="86200-199">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86200-200">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="86200-200">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="86200-201">Opcional</span><span class="sxs-lookup"><span data-stu-id="86200-201">Optional</span></span></p></td>
<td><p><span data-ttu-id="86200-202">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="86200-202">True</span></span></p></td>
<td><p><span data-ttu-id="86200-203">TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="86200-203">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="86200-204">SASL requer TLS.</span><span class="sxs-lookup"><span data-stu-id="86200-204">SASL requires TLS.</span></span> <span data-ttu-id="86200-205">Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="86200-205">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86200-206">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="86200-206">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="86200-207">Opcional</span><span class="sxs-lookup"><span data-stu-id="86200-207">Optional</span></span></p></td>
<td><p><span data-ttu-id="86200-208">Falso</span><span class="sxs-lookup"><span data-stu-id="86200-208">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="86200-209">Configuração inválida</span><span class="sxs-lookup"><span data-stu-id="86200-209">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="86200-210">SASL requer TLS.</span><span class="sxs-lookup"><span data-stu-id="86200-210">SASL requires TLS.</span></span> <span data-ttu-id="86200-211">Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="86200-211">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86200-212">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="86200-212">Required</span></span></p></td>
<td><p><span data-ttu-id="86200-213">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="86200-213">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="86200-214">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="86200-214">True</span></span></p></td>
<td><p><span data-ttu-id="86200-215">TLS Dialback</span><span class="sxs-lookup"><span data-stu-id="86200-215">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="86200-216">A configuração permite o TLS Dialback.</span><span class="sxs-lookup"><span data-stu-id="86200-216">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86200-217">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="86200-217">Required</span></span></p></td>
<td><p><span data-ttu-id="86200-218">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="86200-218">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="86200-219">Falso</span><span class="sxs-lookup"><span data-stu-id="86200-219">False</span></span></p></td>
<td><p><span data-ttu-id="86200-220">Configuração inválida</span><span class="sxs-lookup"><span data-stu-id="86200-220">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="86200-221">SASL ou Dialback devem ser habilitados.</span><span class="sxs-lookup"><span data-stu-id="86200-221">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86200-222">Opcional</span><span class="sxs-lookup"><span data-stu-id="86200-222">Optional</span></span></p></td>
<td><p><span data-ttu-id="86200-223">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="86200-223">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="86200-224">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="86200-224">True</span></span></p></td>
<td><p><span data-ttu-id="86200-225">TLS Dialback, TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="86200-225">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="86200-226">Com base nas opções de negociação do outro ponto de extremidade, o TCP ou o TLS Dialback será aceito.</span><span class="sxs-lookup"><span data-stu-id="86200-226">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86200-227">Opcional</span><span class="sxs-lookup"><span data-stu-id="86200-227">Optional</span></span></p></td>
<td><p><span data-ttu-id="86200-228">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="86200-228">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="86200-229">Falso</span><span class="sxs-lookup"><span data-stu-id="86200-229">False</span></span></p></td>
<td><p><span data-ttu-id="86200-230">Configuração inválida</span><span class="sxs-lookup"><span data-stu-id="86200-230">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="86200-231">SASL ou Dialback devem ser habilitados.</span><span class="sxs-lookup"><span data-stu-id="86200-231">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86200-232">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="86200-232">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="86200-233">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="86200-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="86200-234">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="86200-234">True</span></span></p></td>
<td><p><span data-ttu-id="86200-235">TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="86200-235">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="86200-236">O TCP Dialback é o único método de negociação disponível</span><span class="sxs-lookup"><span data-stu-id="86200-236">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86200-237">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="86200-237">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="86200-238">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="86200-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="86200-239">Falso</span><span class="sxs-lookup"><span data-stu-id="86200-239">False</span></span></p></td>
<td><p><span data-ttu-id="86200-240">Configuração inválida</span><span class="sxs-lookup"><span data-stu-id="86200-240">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="86200-241">SASL ou Dialback devem ser habilitados.</span><span class="sxs-lookup"><span data-stu-id="86200-241">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

