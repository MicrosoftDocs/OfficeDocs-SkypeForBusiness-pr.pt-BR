---
title: 'Lync Server 2013: configurações de negociação para parceiros federados XMPP'
description: 'Lync Server 2013: configurações de negociação para parceiros federados XMPP.'
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
ms.openlocfilehash: 6ac3d9c69d407dc750a1afb35f0a448869a88f09
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578637"
---
# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="4f0a5-103">Configurações de negociação para parceiros federados XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f0a5-103">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f0a5-104">_**Última modificação do tópico:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="4f0a5-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="4f0a5-105">As configurações dos tipos de negociação na configuração de um parceiro do XMPP têm uma ampla variedade de combinações possíveis.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-105">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="4f0a5-106">Nem todas essas combinações são válidas.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-106">Not all of these combinations are valid.</span></span> <span data-ttu-id="4f0a5-107">A tabela detalhada neste tópico definirá as configurações válidas e inválidas.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-107">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="4f0a5-108">As configurações comuns são apresentadas na primeira tabela, a segunda tabela detalhando todas as combinações possíveis.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-108">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="4f0a5-109">Observe que você não pode ter a *autenticação simples e a camada de segurança* (SASL) **, a menos** que *Transport Layer Security* (TLS) também esteja disponível.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-109">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="4f0a5-110">O SASL é enviado em um formato não criptografado (legível) e nunca deve ser transmitido, a menos que seja protegido por outro meio, como o TLS.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-110">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="4f0a5-111">Métodos comuns de negociação de Federação XMPP</span><span class="sxs-lookup"><span data-stu-id="4f0a5-111">Common XMPP Federation Negotiation Methods</span></span>

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
<th><span data-ttu-id="4f0a5-112">TLS (Transport Layer Security)</span><span class="sxs-lookup"><span data-stu-id="4f0a5-112">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="4f0a5-113">Autenticação simples e camada de segurança (SASL)</span><span class="sxs-lookup"><span data-stu-id="4f0a5-113">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="4f0a5-114">Autenticação Dialback</span><span class="sxs-lookup"><span data-stu-id="4f0a5-114">Dialback Authentication</span></span></th>
<th><span data-ttu-id="4f0a5-115">Método (s) de autenticação esperado</span><span class="sxs-lookup"><span data-stu-id="4f0a5-115">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="4f0a5-116">Observações</span><span class="sxs-lookup"><span data-stu-id="4f0a5-116">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f0a5-117">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="4f0a5-117">Required</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-118">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="4f0a5-118">Required</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-119">Falso</span><span class="sxs-lookup"><span data-stu-id="4f0a5-119">False</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-120">SASL sobre TLS</span><span class="sxs-lookup"><span data-stu-id="4f0a5-120">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-121">O TLS e o SASL necessários ajudam a garantir que o fluxo de mensagens SASL seja seguro.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-121">TLS and SASL required helps to ensure that the SASL message stream is secure.</span></span> <span data-ttu-id="4f0a5-122">Dialback não está disponível e não pode ser usado para um método fallback se o parceiro federado do XMPP não definiu o TLS como obrigatório ou opcional.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-122">Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f0a5-123">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="4f0a5-123">Required</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-124">Opcional</span><span class="sxs-lookup"><span data-stu-id="4f0a5-124">Optional</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-125">Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-125">True</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-126">SASL sobre TLS, TLS Dialback, TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="4f0a5-126">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-127">Ao exigir TLS, se o parceiro federado XMPP tiver definido SASL como opcional ou obrigatório, o SASL será usado.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-127">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used.</span></span> <span data-ttu-id="4f0a5-128">Se SASL não estiver disponível, o Dialback sobre TLS será usado.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-128">If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f0a5-129">Opcional</span><span class="sxs-lookup"><span data-stu-id="4f0a5-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-130">Opcional</span><span class="sxs-lookup"><span data-stu-id="4f0a5-130">Optional</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-131">Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-131">True</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-132">SASL sobre TLS, TLS Dialback, TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="4f0a5-132">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-133">Embora muito flexível nos métodos de negociação oferecidos, essas configurações dependem das configurações do parceiro de Federação do XMPP.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-133">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings.</span></span> <span data-ttu-id="4f0a5-134">Se o parceiro tiver o TLS opcional ou necessário, mas o SASL não for suportado, o TLS Dialback estará disponível.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-134">If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available.</span></span> <span data-ttu-id="4f0a5-135">Se o parceiro tiver TLS e SASL definido como Optional ou Required, a seleção ideal de TLS sobre o SASL será usada.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-135">If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f0a5-136">Não Suportado</span><span class="sxs-lookup"><span data-stu-id="4f0a5-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-137">Não Suportado</span><span class="sxs-lookup"><span data-stu-id="4f0a5-137">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-138">Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-138">True</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-139">TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="4f0a5-139">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-140">Em muitos casos, o TCP Dialback é a única solução possível.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-140">In many cases, TCP Dialback is the only possible solution.</span></span> <span data-ttu-id="4f0a5-141">Menos desejável que outras opções, ele fornece algum nível de confiança.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-141">Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="4f0a5-142">Matriz de métodos de negociação de Federação XMPP-Complete</span><span class="sxs-lookup"><span data-stu-id="4f0a5-142">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

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
<th><span data-ttu-id="4f0a5-143">TLS (Transport Layer Security)</span><span class="sxs-lookup"><span data-stu-id="4f0a5-143">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="4f0a5-144">Autenticação simples e camada de segurança (SASL)</span><span class="sxs-lookup"><span data-stu-id="4f0a5-144">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="4f0a5-145">Autenticação Dialback</span><span class="sxs-lookup"><span data-stu-id="4f0a5-145">Dialback Authentication</span></span></th>
<th><span data-ttu-id="4f0a5-146">Método de autenticação esperado</span><span class="sxs-lookup"><span data-stu-id="4f0a5-146">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="4f0a5-147">Observações, avisos ou erros de configuração não válida</span><span class="sxs-lookup"><span data-stu-id="4f0a5-147">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f0a5-148">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="4f0a5-148">Required</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-149">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="4f0a5-149">Required</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-150">Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-150">True</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-151">SASL sobre TLS</span><span class="sxs-lookup"><span data-stu-id="4f0a5-151">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="4f0a5-152">O Dialback não funcionará se ambos SASL e TLS forem necessários.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-152">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f0a5-153">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="4f0a5-153">Required</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-154">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="4f0a5-154">Required</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-155">Falso</span><span class="sxs-lookup"><span data-stu-id="4f0a5-155">False</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-156">SASL sobre TLS</span><span class="sxs-lookup"><span data-stu-id="4f0a5-156">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f0a5-157">Opcional</span><span class="sxs-lookup"><span data-stu-id="4f0a5-157">Optional</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-158">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="4f0a5-158">Required</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-159">Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-159">True</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-160">SASL sobre TLS, TLS Dialback, TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="4f0a5-160">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="4f0a5-161">SASL exige o protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-161">SASL requires TLS.</span></span> <span data-ttu-id="4f0a5-162">Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-162">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f0a5-163">Opcional</span><span class="sxs-lookup"><span data-stu-id="4f0a5-163">Optional</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-164">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="4f0a5-164">Required</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-165">Falso</span><span class="sxs-lookup"><span data-stu-id="4f0a5-165">False</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-166">SASL sobre TLS</span><span class="sxs-lookup"><span data-stu-id="4f0a5-166">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="4f0a5-167">SASL exige o protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-167">SASL requires TLS.</span></span> <span data-ttu-id="4f0a5-168">Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-168">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f0a5-169">Não suportado</span><span class="sxs-lookup"><span data-stu-id="4f0a5-169">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-170">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="4f0a5-170">Required</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-171">Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-171">True</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-172">TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="4f0a5-172">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="4f0a5-173">SASL exige o protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-173">SASL requires TLS.</span></span> <span data-ttu-id="4f0a5-174">Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-174">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f0a5-175">Não suportado</span><span class="sxs-lookup"><span data-stu-id="4f0a5-175">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-176">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="4f0a5-176">Required</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-177">Falso</span><span class="sxs-lookup"><span data-stu-id="4f0a5-177">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="4f0a5-178">Não é uma configuração válida</span><span class="sxs-lookup"><span data-stu-id="4f0a5-178">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="4f0a5-179">Como o SASL requer o TLS, e o TLS não está disponível, o SASL/TLS não pode ser bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-179">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed.</span></span> <span data-ttu-id="4f0a5-180">TCP Dialback está definido como false e não pode ser usado.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-180">TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f0a5-181">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="4f0a5-181">Required</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-182">Opcional</span><span class="sxs-lookup"><span data-stu-id="4f0a5-182">Optional</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-183">Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-183">True</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-184">SASL sobre TLS, TLS Dialback</span><span class="sxs-lookup"><span data-stu-id="4f0a5-184">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f0a5-185">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="4f0a5-185">Required</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-186">Opcional</span><span class="sxs-lookup"><span data-stu-id="4f0a5-186">Optional</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-187">Falso</span><span class="sxs-lookup"><span data-stu-id="4f0a5-187">False</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-188">SASL sobre TLS</span><span class="sxs-lookup"><span data-stu-id="4f0a5-188">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f0a5-189">Opcional</span><span class="sxs-lookup"><span data-stu-id="4f0a5-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-190">Opcional</span><span class="sxs-lookup"><span data-stu-id="4f0a5-190">Optional</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-191">Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-191">True</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-192">SASL sobre TLS, TLS Dialback, TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="4f0a5-192">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="4f0a5-193">SASL exige o protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-193">SASL requires TLS.</span></span> <span data-ttu-id="4f0a5-194">Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-194">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f0a5-195">Opcional</span><span class="sxs-lookup"><span data-stu-id="4f0a5-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-196">Opcional</span><span class="sxs-lookup"><span data-stu-id="4f0a5-196">Optional</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-197">Falso</span><span class="sxs-lookup"><span data-stu-id="4f0a5-197">False</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-198">SASL sobre TLS</span><span class="sxs-lookup"><span data-stu-id="4f0a5-198">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="4f0a5-199">SASL exige o protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-199">SASL requires TLS.</span></span> <span data-ttu-id="4f0a5-200">Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-200">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f0a5-201">Não suportado</span><span class="sxs-lookup"><span data-stu-id="4f0a5-201">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-202">Opcional</span><span class="sxs-lookup"><span data-stu-id="4f0a5-202">Optional</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-203">Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-203">True</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-204">TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="4f0a5-204">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="4f0a5-205">SASL exige o protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-205">SASL requires TLS.</span></span> <span data-ttu-id="4f0a5-206">Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-206">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f0a5-207">Não suportado</span><span class="sxs-lookup"><span data-stu-id="4f0a5-207">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-208">Opcional</span><span class="sxs-lookup"><span data-stu-id="4f0a5-208">Optional</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-209">Falso</span><span class="sxs-lookup"><span data-stu-id="4f0a5-209">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="4f0a5-210">Não é uma configuração válida</span><span class="sxs-lookup"><span data-stu-id="4f0a5-210">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="4f0a5-211">SASL exige o protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-211">SASL requires TLS.</span></span> <span data-ttu-id="4f0a5-212">Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-212">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f0a5-213">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="4f0a5-213">Required</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-214">Não suportado</span><span class="sxs-lookup"><span data-stu-id="4f0a5-214">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-215">Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-215">True</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-216">TLS Dialback</span><span class="sxs-lookup"><span data-stu-id="4f0a5-216">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-217">A configuração permite o TLS Dialback.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-217">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f0a5-218">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="4f0a5-218">Required</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-219">Não suportado</span><span class="sxs-lookup"><span data-stu-id="4f0a5-219">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-220">Falso</span><span class="sxs-lookup"><span data-stu-id="4f0a5-220">False</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-221">Não é uma configuração válida</span><span class="sxs-lookup"><span data-stu-id="4f0a5-221">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="4f0a5-222">SASL ou Dialback deve estar habilitado.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-222">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f0a5-223">Opcional</span><span class="sxs-lookup"><span data-stu-id="4f0a5-223">Optional</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-224">Não suportado</span><span class="sxs-lookup"><span data-stu-id="4f0a5-224">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-225">Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-225">True</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-226">TLS Dialback, TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="4f0a5-226">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-227">Com base nas opções de negociação do outro ponto de extremidade, os Dialback TCP ou TLS serão aceitos.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-227">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f0a5-228">Opcional</span><span class="sxs-lookup"><span data-stu-id="4f0a5-228">Optional</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-229">Não suportado</span><span class="sxs-lookup"><span data-stu-id="4f0a5-229">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-230">Falso</span><span class="sxs-lookup"><span data-stu-id="4f0a5-230">False</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-231">Não é uma configuração válida</span><span class="sxs-lookup"><span data-stu-id="4f0a5-231">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="4f0a5-232">SASL ou Dialback deve estar habilitado.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-232">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f0a5-233">Não Suportado</span><span class="sxs-lookup"><span data-stu-id="4f0a5-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-234">Não Suportado</span><span class="sxs-lookup"><span data-stu-id="4f0a5-234">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-235">Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-235">True</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-236">TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="4f0a5-236">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-237">O TCP Dialback é o único método de negociação disponível</span><span class="sxs-lookup"><span data-stu-id="4f0a5-237">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f0a5-238">Não Suportado</span><span class="sxs-lookup"><span data-stu-id="4f0a5-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-239">Não Suportado</span><span class="sxs-lookup"><span data-stu-id="4f0a5-239">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-240">Falso</span><span class="sxs-lookup"><span data-stu-id="4f0a5-240">False</span></span></p></td>
<td><p><span data-ttu-id="4f0a5-241">Não é uma configuração válida</span><span class="sxs-lookup"><span data-stu-id="4f0a5-241">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="4f0a5-242">SASL ou Dialback deve estar habilitado.</span><span class="sxs-lookup"><span data-stu-id="4f0a5-242">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

