---
title: 'Lync Server 2013: configurações de negociação para parceiros federados XMPP'
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
ms.openlocfilehash: bdb09d52970b5fd97395acda6a2e4fbc824a378d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505588"
---
# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="5080f-102">Configurações de negociação para parceiros federados XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5080f-102">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5080f-103">_**Última modificação do tópico:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="5080f-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="5080f-104">As configurações dos tipos de negociação na configuração de um parceiro do XMPP têm uma ampla variedade de combinações possíveis.</span><span class="sxs-lookup"><span data-stu-id="5080f-104">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="5080f-105">Nem todas essas combinações são válidas.</span><span class="sxs-lookup"><span data-stu-id="5080f-105">Not all of these combinations are valid.</span></span> <span data-ttu-id="5080f-106">A tabela detalhada neste tópico definirá as configurações válidas e inválidas.</span><span class="sxs-lookup"><span data-stu-id="5080f-106">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="5080f-107">As configurações comuns são apresentadas na primeira tabela, a segunda tabela detalhando todas as combinações possíveis.</span><span class="sxs-lookup"><span data-stu-id="5080f-107">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="5080f-108">Observe que você não pode ter a *autenticação simples e a camada de segurança* (SASL) **, a menos** que *Transport Layer Security* (TLS) também esteja disponível.</span><span class="sxs-lookup"><span data-stu-id="5080f-108">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="5080f-109">O SASL é enviado em um formato não criptografado (legível) e nunca deve ser transmitido, a menos que seja protegido por outro meio, como o TLS.</span><span class="sxs-lookup"><span data-stu-id="5080f-109">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="5080f-110">Métodos comuns de negociação de Federação XMPP</span><span class="sxs-lookup"><span data-stu-id="5080f-110">Common XMPP Federation Negotiation Methods</span></span>

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
<th><span data-ttu-id="5080f-111">TLS (Transport Layer Security)</span><span class="sxs-lookup"><span data-stu-id="5080f-111">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="5080f-112">Autenticação simples e camada de segurança (SASL)</span><span class="sxs-lookup"><span data-stu-id="5080f-112">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="5080f-113">Autenticação Dialback</span><span class="sxs-lookup"><span data-stu-id="5080f-113">Dialback Authentication</span></span></th>
<th><span data-ttu-id="5080f-114">Método (s) de autenticação esperado</span><span class="sxs-lookup"><span data-stu-id="5080f-114">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="5080f-115">Observações</span><span class="sxs-lookup"><span data-stu-id="5080f-115">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5080f-116">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="5080f-116">Required</span></span></p></td>
<td><p><span data-ttu-id="5080f-117">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="5080f-117">Required</span></span></p></td>
<td><p><span data-ttu-id="5080f-118">Falso</span><span class="sxs-lookup"><span data-stu-id="5080f-118">False</span></span></p></td>
<td><p><span data-ttu-id="5080f-119">SASL sobre TLS</span><span class="sxs-lookup"><span data-stu-id="5080f-119">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="5080f-120">O TLS e o SASL necessários ajudam a garantir que o fluxo de mensagens SASL seja seguro.</span><span class="sxs-lookup"><span data-stu-id="5080f-120">TLS and SASL required helps to ensure that the SASL message stream is secure.</span></span> <span data-ttu-id="5080f-121">Dialback não está disponível e não pode ser usado para um método fallback se o parceiro federado do XMPP não definiu o TLS como obrigatório ou opcional.</span><span class="sxs-lookup"><span data-stu-id="5080f-121">Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5080f-122">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="5080f-122">Required</span></span></p></td>
<td><p><span data-ttu-id="5080f-123">Opcional</span><span class="sxs-lookup"><span data-stu-id="5080f-123">Optional</span></span></p></td>
<td><p><span data-ttu-id="5080f-124">Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="5080f-124">True</span></span></p></td>
<td><p><span data-ttu-id="5080f-125">SASL sobre TLS, TLS Dialback, TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="5080f-125">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="5080f-126">Ao exigir TLS, se o parceiro federado XMPP tiver definido SASL como opcional ou obrigatório, o SASL será usado.</span><span class="sxs-lookup"><span data-stu-id="5080f-126">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used.</span></span> <span data-ttu-id="5080f-127">Se SASL não estiver disponível, o Dialback sobre TLS será usado.</span><span class="sxs-lookup"><span data-stu-id="5080f-127">If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5080f-128">Opcional</span><span class="sxs-lookup"><span data-stu-id="5080f-128">Optional</span></span></p></td>
<td><p><span data-ttu-id="5080f-129">Opcional</span><span class="sxs-lookup"><span data-stu-id="5080f-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="5080f-130">Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="5080f-130">True</span></span></p></td>
<td><p><span data-ttu-id="5080f-131">SASL sobre TLS, TLS Dialback, TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="5080f-131">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="5080f-132">Embora muito flexível nos métodos de negociação oferecidos, essas configurações dependem das configurações do parceiro de Federação do XMPP.</span><span class="sxs-lookup"><span data-stu-id="5080f-132">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings.</span></span> <span data-ttu-id="5080f-133">Se o parceiro tiver o TLS opcional ou necessário, mas o SASL não for suportado, o TLS Dialback estará disponível.</span><span class="sxs-lookup"><span data-stu-id="5080f-133">If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available.</span></span> <span data-ttu-id="5080f-134">Se o parceiro tiver TLS e SASL definido como Optional ou Required, a seleção ideal de TLS sobre o SASL será usada.</span><span class="sxs-lookup"><span data-stu-id="5080f-134">If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5080f-135">Não Suportado</span><span class="sxs-lookup"><span data-stu-id="5080f-135">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="5080f-136">Não Suportado</span><span class="sxs-lookup"><span data-stu-id="5080f-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="5080f-137">Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="5080f-137">True</span></span></p></td>
<td><p><span data-ttu-id="5080f-138">TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="5080f-138">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="5080f-139">Em muitos casos, o TCP Dialback é a única solução possível.</span><span class="sxs-lookup"><span data-stu-id="5080f-139">In many cases, TCP Dialback is the only possible solution.</span></span> <span data-ttu-id="5080f-140">Menos desejável que outras opções, ele fornece algum nível de confiança.</span><span class="sxs-lookup"><span data-stu-id="5080f-140">Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="5080f-141">Matriz de métodos de negociação de Federação XMPP-Complete</span><span class="sxs-lookup"><span data-stu-id="5080f-141">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

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
<th><span data-ttu-id="5080f-142">TLS (Transport Layer Security)</span><span class="sxs-lookup"><span data-stu-id="5080f-142">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="5080f-143">Autenticação simples e camada de segurança (SASL)</span><span class="sxs-lookup"><span data-stu-id="5080f-143">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="5080f-144">Autenticação Dialback</span><span class="sxs-lookup"><span data-stu-id="5080f-144">Dialback Authentication</span></span></th>
<th><span data-ttu-id="5080f-145">Método de autenticação esperado</span><span class="sxs-lookup"><span data-stu-id="5080f-145">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="5080f-146">Observações, avisos ou erros de configuração não válida</span><span class="sxs-lookup"><span data-stu-id="5080f-146">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5080f-147">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="5080f-147">Required</span></span></p></td>
<td><p><span data-ttu-id="5080f-148">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="5080f-148">Required</span></span></p></td>
<td><p><span data-ttu-id="5080f-149">Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="5080f-149">True</span></span></p></td>
<td><p><span data-ttu-id="5080f-150">SASL sobre TLS</span><span class="sxs-lookup"><span data-stu-id="5080f-150">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="5080f-151">O Dialback não funcionará se ambos SASL e TLS forem necessários.</span><span class="sxs-lookup"><span data-stu-id="5080f-151">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5080f-152">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="5080f-152">Required</span></span></p></td>
<td><p><span data-ttu-id="5080f-153">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="5080f-153">Required</span></span></p></td>
<td><p><span data-ttu-id="5080f-154">Falso</span><span class="sxs-lookup"><span data-stu-id="5080f-154">False</span></span></p></td>
<td><p><span data-ttu-id="5080f-155">SASL sobre TLS</span><span class="sxs-lookup"><span data-stu-id="5080f-155">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5080f-156">Opcional</span><span class="sxs-lookup"><span data-stu-id="5080f-156">Optional</span></span></p></td>
<td><p><span data-ttu-id="5080f-157">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="5080f-157">Required</span></span></p></td>
<td><p><span data-ttu-id="5080f-158">Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="5080f-158">True</span></span></p></td>
<td><p><span data-ttu-id="5080f-159">SASL sobre TLS, TLS Dialback, TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="5080f-159">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="5080f-160">SASL exige o protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="5080f-160">SASL requires TLS.</span></span> <span data-ttu-id="5080f-161">Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="5080f-161">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5080f-162">Opcional</span><span class="sxs-lookup"><span data-stu-id="5080f-162">Optional</span></span></p></td>
<td><p><span data-ttu-id="5080f-163">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="5080f-163">Required</span></span></p></td>
<td><p><span data-ttu-id="5080f-164">Falso</span><span class="sxs-lookup"><span data-stu-id="5080f-164">False</span></span></p></td>
<td><p><span data-ttu-id="5080f-165">SASL sobre TLS</span><span class="sxs-lookup"><span data-stu-id="5080f-165">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="5080f-166">SASL exige o protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="5080f-166">SASL requires TLS.</span></span> <span data-ttu-id="5080f-167">Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="5080f-167">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5080f-168">Não suportado</span><span class="sxs-lookup"><span data-stu-id="5080f-168">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="5080f-169">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="5080f-169">Required</span></span></p></td>
<td><p><span data-ttu-id="5080f-170">Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="5080f-170">True</span></span></p></td>
<td><p><span data-ttu-id="5080f-171">TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="5080f-171">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="5080f-172">SASL exige o protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="5080f-172">SASL requires TLS.</span></span> <span data-ttu-id="5080f-173">Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="5080f-173">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5080f-174">Não suportado</span><span class="sxs-lookup"><span data-stu-id="5080f-174">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="5080f-175">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="5080f-175">Required</span></span></p></td>
<td><p><span data-ttu-id="5080f-176">Falso</span><span class="sxs-lookup"><span data-stu-id="5080f-176">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="5080f-177">Não é uma configuração válida</span><span class="sxs-lookup"><span data-stu-id="5080f-177">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="5080f-178">Como o SASL requer o TLS, e o TLS não está disponível, o SASL/TLS não pode ser bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="5080f-178">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed.</span></span> <span data-ttu-id="5080f-179">TCP Dialback está definido como false e não pode ser usado.</span><span class="sxs-lookup"><span data-stu-id="5080f-179">TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5080f-180">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="5080f-180">Required</span></span></p></td>
<td><p><span data-ttu-id="5080f-181">Opcional</span><span class="sxs-lookup"><span data-stu-id="5080f-181">Optional</span></span></p></td>
<td><p><span data-ttu-id="5080f-182">Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="5080f-182">True</span></span></p></td>
<td><p><span data-ttu-id="5080f-183">SASL sobre TLS, TLS Dialback</span><span class="sxs-lookup"><span data-stu-id="5080f-183">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5080f-184">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="5080f-184">Required</span></span></p></td>
<td><p><span data-ttu-id="5080f-185">Opcional</span><span class="sxs-lookup"><span data-stu-id="5080f-185">Optional</span></span></p></td>
<td><p><span data-ttu-id="5080f-186">Falso</span><span class="sxs-lookup"><span data-stu-id="5080f-186">False</span></span></p></td>
<td><p><span data-ttu-id="5080f-187">SASL sobre TLS</span><span class="sxs-lookup"><span data-stu-id="5080f-187">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5080f-188">Opcional</span><span class="sxs-lookup"><span data-stu-id="5080f-188">Optional</span></span></p></td>
<td><p><span data-ttu-id="5080f-189">Opcional</span><span class="sxs-lookup"><span data-stu-id="5080f-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="5080f-190">Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="5080f-190">True</span></span></p></td>
<td><p><span data-ttu-id="5080f-191">SASL sobre TLS, TLS Dialback, TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="5080f-191">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="5080f-192">SASL exige o protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="5080f-192">SASL requires TLS.</span></span> <span data-ttu-id="5080f-193">Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="5080f-193">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5080f-194">Opcional</span><span class="sxs-lookup"><span data-stu-id="5080f-194">Optional</span></span></p></td>
<td><p><span data-ttu-id="5080f-195">Opcional</span><span class="sxs-lookup"><span data-stu-id="5080f-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="5080f-196">Falso</span><span class="sxs-lookup"><span data-stu-id="5080f-196">False</span></span></p></td>
<td><p><span data-ttu-id="5080f-197">SASL sobre TLS</span><span class="sxs-lookup"><span data-stu-id="5080f-197">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="5080f-198">SASL exige o protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="5080f-198">SASL requires TLS.</span></span> <span data-ttu-id="5080f-199">Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="5080f-199">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5080f-200">Não suportado</span><span class="sxs-lookup"><span data-stu-id="5080f-200">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="5080f-201">Opcional</span><span class="sxs-lookup"><span data-stu-id="5080f-201">Optional</span></span></p></td>
<td><p><span data-ttu-id="5080f-202">Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="5080f-202">True</span></span></p></td>
<td><p><span data-ttu-id="5080f-203">TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="5080f-203">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="5080f-204">SASL exige o protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="5080f-204">SASL requires TLS.</span></span> <span data-ttu-id="5080f-205">Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="5080f-205">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5080f-206">Não suportado</span><span class="sxs-lookup"><span data-stu-id="5080f-206">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="5080f-207">Opcional</span><span class="sxs-lookup"><span data-stu-id="5080f-207">Optional</span></span></p></td>
<td><p><span data-ttu-id="5080f-208">Falso</span><span class="sxs-lookup"><span data-stu-id="5080f-208">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="5080f-209">Não é uma configuração válida</span><span class="sxs-lookup"><span data-stu-id="5080f-209">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="5080f-210">SASL exige o protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="5080f-210">SASL requires TLS.</span></span> <span data-ttu-id="5080f-211">Permitir que o TLS seja opcional pode resultar em negociações de sessão com falha.</span><span class="sxs-lookup"><span data-stu-id="5080f-211">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5080f-212">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="5080f-212">Required</span></span></p></td>
<td><p><span data-ttu-id="5080f-213">Não suportado</span><span class="sxs-lookup"><span data-stu-id="5080f-213">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="5080f-214">Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="5080f-214">True</span></span></p></td>
<td><p><span data-ttu-id="5080f-215">TLS Dialback</span><span class="sxs-lookup"><span data-stu-id="5080f-215">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="5080f-216">A configuração permite o TLS Dialback.</span><span class="sxs-lookup"><span data-stu-id="5080f-216">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5080f-217">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="5080f-217">Required</span></span></p></td>
<td><p><span data-ttu-id="5080f-218">Não suportado</span><span class="sxs-lookup"><span data-stu-id="5080f-218">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="5080f-219">Falso</span><span class="sxs-lookup"><span data-stu-id="5080f-219">False</span></span></p></td>
<td><p><span data-ttu-id="5080f-220">Não é uma configuração válida</span><span class="sxs-lookup"><span data-stu-id="5080f-220">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="5080f-221">SASL ou Dialback deve estar habilitado.</span><span class="sxs-lookup"><span data-stu-id="5080f-221">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5080f-222">Opcional</span><span class="sxs-lookup"><span data-stu-id="5080f-222">Optional</span></span></p></td>
<td><p><span data-ttu-id="5080f-223">Não suportado</span><span class="sxs-lookup"><span data-stu-id="5080f-223">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="5080f-224">Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="5080f-224">True</span></span></p></td>
<td><p><span data-ttu-id="5080f-225">TLS Dialback, TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="5080f-225">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="5080f-226">Com base nas opções de negociação do outro ponto de extremidade, os Dialback TCP ou TLS serão aceitos.</span><span class="sxs-lookup"><span data-stu-id="5080f-226">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5080f-227">Opcional</span><span class="sxs-lookup"><span data-stu-id="5080f-227">Optional</span></span></p></td>
<td><p><span data-ttu-id="5080f-228">Não suportado</span><span class="sxs-lookup"><span data-stu-id="5080f-228">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="5080f-229">Falso</span><span class="sxs-lookup"><span data-stu-id="5080f-229">False</span></span></p></td>
<td><p><span data-ttu-id="5080f-230">Não é uma configuração válida</span><span class="sxs-lookup"><span data-stu-id="5080f-230">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="5080f-231">SASL ou Dialback deve estar habilitado.</span><span class="sxs-lookup"><span data-stu-id="5080f-231">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5080f-232">Não Suportado</span><span class="sxs-lookup"><span data-stu-id="5080f-232">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="5080f-233">Não Suportado</span><span class="sxs-lookup"><span data-stu-id="5080f-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="5080f-234">Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="5080f-234">True</span></span></p></td>
<td><p><span data-ttu-id="5080f-235">TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="5080f-235">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="5080f-236">O TCP Dialback é o único método de negociação disponível</span><span class="sxs-lookup"><span data-stu-id="5080f-236">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5080f-237">Não Suportado</span><span class="sxs-lookup"><span data-stu-id="5080f-237">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="5080f-238">Não Suportado</span><span class="sxs-lookup"><span data-stu-id="5080f-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="5080f-239">Falso</span><span class="sxs-lookup"><span data-stu-id="5080f-239">False</span></span></p></td>
<td><p><span data-ttu-id="5080f-240">Não é uma configuração válida</span><span class="sxs-lookup"><span data-stu-id="5080f-240">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="5080f-241">SASL ou Dialback deve estar habilitado.</span><span class="sxs-lookup"><span data-stu-id="5080f-241">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

