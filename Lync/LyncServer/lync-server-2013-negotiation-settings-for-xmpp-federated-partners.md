---
title: 'Lync Server 2013: Configurações de negociação para parceiros de XMPP federados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Negotiation settings for XMPP federated partners
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552456(v=OCS.15)
ms:contentKeyID: 48679567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02d72870e4060be6aa4ec428159af7ab19cb68b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826707"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="426f1-102">Configurações de negociação para parceiros de XMPP federados no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="426f1-102">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="426f1-103">_**Tópico da última modificação:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="426f1-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="426f1-104">As configurações dos tipos de negociação na configuração de um parceiro do XMPP têm uma ampla variedade de combinações possíveis.</span><span class="sxs-lookup"><span data-stu-id="426f1-104">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="426f1-105">Nem todas essas combinações são válidas.</span><span class="sxs-lookup"><span data-stu-id="426f1-105">Not all of these combinations are valid.</span></span> <span data-ttu-id="426f1-106">A tabela detalhada neste tópico definirá as configurações válidas e inválidas.</span><span class="sxs-lookup"><span data-stu-id="426f1-106">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="426f1-107">As configurações comuns são apresentadas na primeira tabela, a segunda tabela que detalha todas as combinações possíveis.</span><span class="sxs-lookup"><span data-stu-id="426f1-107">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="426f1-108">Observe que você não pode ter a *autenticação simples e a camada de segurança* (SASL) **, a menos** que o TLS ( *Transport Layer Security* ) também esteja disponível.</span><span class="sxs-lookup"><span data-stu-id="426f1-108">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="426f1-109">SASL é enviada em um formato não criptografado (legível) e nunca deve ser transmitida, a menos que seja protegida por outro meio, como TLS.</span><span class="sxs-lookup"><span data-stu-id="426f1-109">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="426f1-110">Métodos comuns de negociação de Federação XMPP</span><span class="sxs-lookup"><span data-stu-id="426f1-110">Common XMPP Federation Negotiation Methods</span></span>

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
<th><span data-ttu-id="426f1-111">Transport Layer Security (TLS)</span><span class="sxs-lookup"><span data-stu-id="426f1-111">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="426f1-112">Camada de segurança e autenticação simples (SASL)</span><span class="sxs-lookup"><span data-stu-id="426f1-112">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="426f1-113">Autenticação Dialback</span><span class="sxs-lookup"><span data-stu-id="426f1-113">Dialback Authentication</span></span></th>
<th><span data-ttu-id="426f1-114">Método (s) de autenticação esperado (s)</span><span class="sxs-lookup"><span data-stu-id="426f1-114">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="426f1-115">Observações</span><span class="sxs-lookup"><span data-stu-id="426f1-115">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="426f1-116">Obrigatório </span><span class="sxs-lookup"><span data-stu-id="426f1-116">Required</span></span></p></td>
<td><p><span data-ttu-id="426f1-117">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="426f1-117">Required</span></span></p></td>
<td><p><span data-ttu-id="426f1-118">False</span><span class="sxs-lookup"><span data-stu-id="426f1-118">False</span></span></p></td>
<td><p><span data-ttu-id="426f1-119">SASL sobre TLS</span><span class="sxs-lookup"><span data-stu-id="426f1-119">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="426f1-120">O TLS e o SASL são necessários ajuda a garantir que o fluxo de mensagens SASL seja seguro.</span><span class="sxs-lookup"><span data-stu-id="426f1-120">TLS and SASL required helps to ensure that the SASL message stream is secure.</span></span> <span data-ttu-id="426f1-121">Dialback não está disponível e não pode ser usado para um método de fallback se o parceiro federado do XMPP não definiu o TLS como obrigatório ou opcional.</span><span class="sxs-lookup"><span data-stu-id="426f1-121">Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426f1-122">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="426f1-122">Required</span></span></p></td>
<td><p><span data-ttu-id="426f1-123">Opcional</span><span class="sxs-lookup"><span data-stu-id="426f1-123">Optional</span></span></p></td>
<td><p><span data-ttu-id="426f1-124">True</span><span class="sxs-lookup"><span data-stu-id="426f1-124">True</span></span></p></td>
<td><p><span data-ttu-id="426f1-125">SASL sobre TLS, TLS Dialback, TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="426f1-125">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="426f1-126">Ao exigir TLS, se o parceiro federado do XMPP tiver sido definido SASL para opcional ou obrigatório, o SASL será usado.</span><span class="sxs-lookup"><span data-stu-id="426f1-126">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used.</span></span> <span data-ttu-id="426f1-127">Se SASL não estiver disponível, o Dialback em TLS será usado.</span><span class="sxs-lookup"><span data-stu-id="426f1-127">If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426f1-128">Opcional </span><span class="sxs-lookup"><span data-stu-id="426f1-128">Optional</span></span></p></td>
<td><p><span data-ttu-id="426f1-129">Opcional</span><span class="sxs-lookup"><span data-stu-id="426f1-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="426f1-130">True</span><span class="sxs-lookup"><span data-stu-id="426f1-130">True</span></span></p></td>
<td><p><span data-ttu-id="426f1-131">SASL sobre TLS, TLS Dialback, TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="426f1-131">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="426f1-132">Embora seja bastante flexível nos métodos de negociação oferecidos, essas configurações dependem das configurações do parceiro de Federação do XMPP.</span><span class="sxs-lookup"><span data-stu-id="426f1-132">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings.</span></span> <span data-ttu-id="426f1-133">Se o parceiro tiver o TLS opcional ou obrigatório, mas o SASL não for compatível, o TLS Dialback estará disponível.</span><span class="sxs-lookup"><span data-stu-id="426f1-133">If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available.</span></span> <span data-ttu-id="426f1-134">Se o parceiro tiver TLS e SASL definido como opcional ou obrigatório, a seleção ideal de TLS sobre o SASL será usada.</span><span class="sxs-lookup"><span data-stu-id="426f1-134">If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426f1-135">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="426f1-135">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="426f1-136">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="426f1-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="426f1-137">True</span><span class="sxs-lookup"><span data-stu-id="426f1-137">True</span></span></p></td>
<td><p><span data-ttu-id="426f1-138">TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="426f1-138">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="426f1-139">Em muitos casos, o TCP Dialback é a única solução possível.</span><span class="sxs-lookup"><span data-stu-id="426f1-139">In many cases, TCP Dialback is the only possible solution.</span></span> <span data-ttu-id="426f1-140">Menos desejável do que outras opções, ele fornece um certo nível de confiança.</span><span class="sxs-lookup"><span data-stu-id="426f1-140">Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="426f1-141">Matriz de métodos de negociação de Federação XMPP-concluída</span><span class="sxs-lookup"><span data-stu-id="426f1-141">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

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
<th><span data-ttu-id="426f1-142">Transport Layer Security (TLS)</span><span class="sxs-lookup"><span data-stu-id="426f1-142">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="426f1-143">Camada de segurança e autenticação simples (SASL)</span><span class="sxs-lookup"><span data-stu-id="426f1-143">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="426f1-144">Autenticação Dialback</span><span class="sxs-lookup"><span data-stu-id="426f1-144">Dialback Authentication</span></span></th>
<th><span data-ttu-id="426f1-145">Método de autenticação esperado</span><span class="sxs-lookup"><span data-stu-id="426f1-145">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="426f1-146">Observações, aviso ou erro para uma configuração inválida</span><span class="sxs-lookup"><span data-stu-id="426f1-146">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="426f1-147">Obrigatório </span><span class="sxs-lookup"><span data-stu-id="426f1-147">Required</span></span></p></td>
<td><p><span data-ttu-id="426f1-148">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="426f1-148">Required</span></span></p></td>
<td><p><span data-ttu-id="426f1-149">True</span><span class="sxs-lookup"><span data-stu-id="426f1-149">True</span></span></p></td>
<td><p><span data-ttu-id="426f1-150">SASL sobre TLS</span><span class="sxs-lookup"><span data-stu-id="426f1-150">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="426f1-151">O Dialback não funcionará se o SASL e o TLS forem obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="426f1-151">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426f1-152">Obrigatório </span><span class="sxs-lookup"><span data-stu-id="426f1-152">Required</span></span></p></td>
<td><p><span data-ttu-id="426f1-153">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="426f1-153">Required</span></span></p></td>
<td><p><span data-ttu-id="426f1-154">False</span><span class="sxs-lookup"><span data-stu-id="426f1-154">False</span></span></p></td>
<td><p><span data-ttu-id="426f1-155">SASL sobre TLS</span><span class="sxs-lookup"><span data-stu-id="426f1-155">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426f1-156">Opcional</span><span class="sxs-lookup"><span data-stu-id="426f1-156">Optional</span></span></p></td>
<td><p><span data-ttu-id="426f1-157">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="426f1-157">Required</span></span></p></td>
<td><p><span data-ttu-id="426f1-158">True</span><span class="sxs-lookup"><span data-stu-id="426f1-158">True</span></span></p></td>
<td><p><span data-ttu-id="426f1-159">SASL sobre TLS, TLS Dialback, TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="426f1-159">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="426f1-160">SASL requer TLS.</span><span class="sxs-lookup"><span data-stu-id="426f1-160">SASL requires TLS.</span></span> <span data-ttu-id="426f1-161">Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="426f1-161">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426f1-162">Opcional</span><span class="sxs-lookup"><span data-stu-id="426f1-162">Optional</span></span></p></td>
<td><p><span data-ttu-id="426f1-163">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="426f1-163">Required</span></span></p></td>
<td><p><span data-ttu-id="426f1-164">False</span><span class="sxs-lookup"><span data-stu-id="426f1-164">False</span></span></p></td>
<td><p><span data-ttu-id="426f1-165">SASL sobre TLS</span><span class="sxs-lookup"><span data-stu-id="426f1-165">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="426f1-166">SASL requer TLS.</span><span class="sxs-lookup"><span data-stu-id="426f1-166">SASL requires TLS.</span></span> <span data-ttu-id="426f1-167">Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="426f1-167">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426f1-168">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="426f1-168">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="426f1-169">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="426f1-169">Required</span></span></p></td>
<td><p><span data-ttu-id="426f1-170">True</span><span class="sxs-lookup"><span data-stu-id="426f1-170">True</span></span></p></td>
<td><p><span data-ttu-id="426f1-171">TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="426f1-171">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="426f1-172">SASL requer TLS.</span><span class="sxs-lookup"><span data-stu-id="426f1-172">SASL requires TLS.</span></span> <span data-ttu-id="426f1-173">Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="426f1-173">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426f1-174">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="426f1-174">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="426f1-175">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="426f1-175">Required</span></span></p></td>
<td><p><span data-ttu-id="426f1-176">False</span><span class="sxs-lookup"><span data-stu-id="426f1-176">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="426f1-177">Configuração inválida</span><span class="sxs-lookup"><span data-stu-id="426f1-177">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="426f1-178">Como a SASL requer TLS, e o TLS não está disponível, o SASL/TLS não pode ser bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="426f1-178">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed.</span></span> <span data-ttu-id="426f1-179">TCP Dialback é definido como false e não pode ser usado.</span><span class="sxs-lookup"><span data-stu-id="426f1-179">TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426f1-180">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="426f1-180">Required</span></span></p></td>
<td><p><span data-ttu-id="426f1-181">Opcional</span><span class="sxs-lookup"><span data-stu-id="426f1-181">Optional</span></span></p></td>
<td><p><span data-ttu-id="426f1-182">True</span><span class="sxs-lookup"><span data-stu-id="426f1-182">True</span></span></p></td>
<td><p><span data-ttu-id="426f1-183">SASL sobre TLS, TLS Dialback</span><span class="sxs-lookup"><span data-stu-id="426f1-183">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426f1-184">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="426f1-184">Required</span></span></p></td>
<td><p><span data-ttu-id="426f1-185">Opcional</span><span class="sxs-lookup"><span data-stu-id="426f1-185">Optional</span></span></p></td>
<td><p><span data-ttu-id="426f1-186">False</span><span class="sxs-lookup"><span data-stu-id="426f1-186">False</span></span></p></td>
<td><p><span data-ttu-id="426f1-187">SASL sobre TLS</span><span class="sxs-lookup"><span data-stu-id="426f1-187">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426f1-188">Opcional </span><span class="sxs-lookup"><span data-stu-id="426f1-188">Optional</span></span></p></td>
<td><p><span data-ttu-id="426f1-189">Opcional</span><span class="sxs-lookup"><span data-stu-id="426f1-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="426f1-190">True</span><span class="sxs-lookup"><span data-stu-id="426f1-190">True</span></span></p></td>
<td><p><span data-ttu-id="426f1-191">SASL sobre TLS, TLS Dialback, TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="426f1-191">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="426f1-192">SASL requer TLS.</span><span class="sxs-lookup"><span data-stu-id="426f1-192">SASL requires TLS.</span></span> <span data-ttu-id="426f1-193">Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="426f1-193">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426f1-194">Opcional </span><span class="sxs-lookup"><span data-stu-id="426f1-194">Optional</span></span></p></td>
<td><p><span data-ttu-id="426f1-195">Opcional</span><span class="sxs-lookup"><span data-stu-id="426f1-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="426f1-196">False</span><span class="sxs-lookup"><span data-stu-id="426f1-196">False</span></span></p></td>
<td><p><span data-ttu-id="426f1-197">SASL sobre TLS</span><span class="sxs-lookup"><span data-stu-id="426f1-197">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="426f1-198">SASL requer TLS.</span><span class="sxs-lookup"><span data-stu-id="426f1-198">SASL requires TLS.</span></span> <span data-ttu-id="426f1-199">Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="426f1-199">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426f1-200">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="426f1-200">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="426f1-201">Opcional</span><span class="sxs-lookup"><span data-stu-id="426f1-201">Optional</span></span></p></td>
<td><p><span data-ttu-id="426f1-202">True</span><span class="sxs-lookup"><span data-stu-id="426f1-202">True</span></span></p></td>
<td><p><span data-ttu-id="426f1-203">TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="426f1-203">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="426f1-204">SASL requer TLS.</span><span class="sxs-lookup"><span data-stu-id="426f1-204">SASL requires TLS.</span></span> <span data-ttu-id="426f1-205">Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="426f1-205">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426f1-206">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="426f1-206">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="426f1-207">Opcional</span><span class="sxs-lookup"><span data-stu-id="426f1-207">Optional</span></span></p></td>
<td><p><span data-ttu-id="426f1-208">False</span><span class="sxs-lookup"><span data-stu-id="426f1-208">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="426f1-209">Configuração inválida</span><span class="sxs-lookup"><span data-stu-id="426f1-209">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="426f1-210">SASL requer TLS.</span><span class="sxs-lookup"><span data-stu-id="426f1-210">SASL requires TLS.</span></span> <span data-ttu-id="426f1-211">Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="426f1-211">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426f1-212">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="426f1-212">Required</span></span></p></td>
<td><p><span data-ttu-id="426f1-213">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="426f1-213">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="426f1-214">True</span><span class="sxs-lookup"><span data-stu-id="426f1-214">True</span></span></p></td>
<td><p><span data-ttu-id="426f1-215">TLS Dialback</span><span class="sxs-lookup"><span data-stu-id="426f1-215">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="426f1-216">A configuração permite o TLS Dialback.</span><span class="sxs-lookup"><span data-stu-id="426f1-216">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426f1-217">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="426f1-217">Required</span></span></p></td>
<td><p><span data-ttu-id="426f1-218">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="426f1-218">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="426f1-219">False</span><span class="sxs-lookup"><span data-stu-id="426f1-219">False</span></span></p></td>
<td><p><span data-ttu-id="426f1-220">Configuração inválida</span><span class="sxs-lookup"><span data-stu-id="426f1-220">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="426f1-221">SASL ou Dialback devem ser habilitados.</span><span class="sxs-lookup"><span data-stu-id="426f1-221">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426f1-222">Opcional</span><span class="sxs-lookup"><span data-stu-id="426f1-222">Optional</span></span></p></td>
<td><p><span data-ttu-id="426f1-223">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="426f1-223">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="426f1-224">True</span><span class="sxs-lookup"><span data-stu-id="426f1-224">True</span></span></p></td>
<td><p><span data-ttu-id="426f1-225">TLS Dialback, TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="426f1-225">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="426f1-226">Com base nas opções de negociação do outro ponto de extremidade, o TCP ou o TLS Dialback será aceito.</span><span class="sxs-lookup"><span data-stu-id="426f1-226">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426f1-227">Opcional</span><span class="sxs-lookup"><span data-stu-id="426f1-227">Optional</span></span></p></td>
<td><p><span data-ttu-id="426f1-228">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="426f1-228">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="426f1-229">False</span><span class="sxs-lookup"><span data-stu-id="426f1-229">False</span></span></p></td>
<td><p><span data-ttu-id="426f1-230">Configuração inválida</span><span class="sxs-lookup"><span data-stu-id="426f1-230">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="426f1-231">SASL ou Dialback devem ser habilitados.</span><span class="sxs-lookup"><span data-stu-id="426f1-231">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426f1-232">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="426f1-232">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="426f1-233">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="426f1-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="426f1-234">True</span><span class="sxs-lookup"><span data-stu-id="426f1-234">True</span></span></p></td>
<td><p><span data-ttu-id="426f1-235">TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="426f1-235">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="426f1-236">O TCP Dialback é o único método de negociação disponível</span><span class="sxs-lookup"><span data-stu-id="426f1-236">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426f1-237">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="426f1-237">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="426f1-238">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="426f1-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="426f1-239">False</span><span class="sxs-lookup"><span data-stu-id="426f1-239">False</span></span></p></td>
<td><p><span data-ttu-id="426f1-240">Configuração inválida</span><span class="sxs-lookup"><span data-stu-id="426f1-240">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="426f1-241">SASL ou Dialback devem ser habilitados.</span><span class="sxs-lookup"><span data-stu-id="426f1-241">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

