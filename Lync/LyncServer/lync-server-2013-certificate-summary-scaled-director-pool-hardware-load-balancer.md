---
title: Resumo de certificado - pool Certificate summary - pool de diretores em escala, balanceador de carga de hardware
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Scaled Director pool, hardware load balancer
ms:assetid: 45940add-8027-418d-b79a-9033b494762f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204846(v=OCS.15)
ms:contentKeyID: 48183992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21b1688641d09e00c82ea952d57bd2a9547ac0dd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836626"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="4c764-102">Resumo de certificado - pool Certificate summary - pool de diretores em escala, balanceador de carga de hardware no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c764-102">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c764-103">_**Tópico da última modificação:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="4c764-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="4c764-104">Os requisitos de certificado para um diretor com um balanceador de carga de hardware usarão um certificado padrão que tenha um nome de requerente e nomes alternativos de assunto para os serviços que o pool do diretor pode receber.</span><span class="sxs-lookup"><span data-stu-id="4c764-104">Certificate requirements for a Director with a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director pool can receive.</span></span> <span data-ttu-id="4c764-105">Um certificado é solicitado para cada diretor do pool.</span><span class="sxs-lookup"><span data-stu-id="4c764-105">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="4c764-106">Além disso, há um certificado de token OAuth para fins de autenticação do servidor para servidor que está instalado em cada servidor.</span><span class="sxs-lookup"><span data-stu-id="4c764-106">Additionally there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-a-scaled-director-using-a-hardware-load-balancer"></a><span data-ttu-id="4c764-107">Certificados para um diretor em escala usando um balanceador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="4c764-107">Certificates for a Scaled Director Using a Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c764-108">Componente</span><span class="sxs-lookup"><span data-stu-id="4c764-108">Component</span></span></th>
<th><span data-ttu-id="4c764-109">Nome da entidade (SN)</span><span class="sxs-lookup"><span data-stu-id="4c764-109">Subject name (SN)</span></span></th>
<th><span data-ttu-id="4c764-110">Nomes alternativos de entidades (SAN)</span><span class="sxs-lookup"><span data-stu-id="4c764-110">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="4c764-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="4c764-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c764-112">Padrão</span><span class="sxs-lookup"><span data-stu-id="4c764-112">Default</span></span></p></td>
<td><p><span data-ttu-id="4c764-113">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="4c764-113">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="4c764-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="4c764-114">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="4c764-115">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="4c764-115">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="4c764-116">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4c764-116">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="4c764-117">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4c764-117">meet.contoso.com</span></span></p>
<p><span data-ttu-id="4c764-118">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4c764-118">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="4c764-119">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4c764-119">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="4c764-120">(Opcionalmente) \*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="4c764-120">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4c764-121">Os certificados do diretor podem ser solicitados de uma CA (autoridade de certificação) gerenciada internamente ou de uma CA pública.</span><span class="sxs-lookup"><span data-stu-id="4c764-121">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="4c764-122">O diretor responde a solicitações do proxy reverso no perímetro ou do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="4c764-122">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span></p>
<p><span data-ttu-id="4c764-123">Ou uma entrada curinga para as URLs simples</span><span class="sxs-lookup"><span data-stu-id="4c764-123">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c764-124">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="4c764-124">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="4c764-125">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="4c764-125">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="4c764-126">Sem entrada</span><span class="sxs-lookup"><span data-stu-id="4c764-126">No Entry</span></span></p></td>
<td>


> [!IMPORTANT]
> <span data-ttu-id="4c764-127">Observe que o tamanho mínimo da chave é 1024, mas você pode receber um aviso de que o tamanho mínimo recomendado da chave é 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="4c764-127">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


<p><span data-ttu-id="4c764-128">O certificado OAuthTokenIssuer é um certificado de finalidade única para a finalidade de autenticar servidores em um ambiente em larga escala e pode ser solicitado de uma CA interna ou de uma CA pública.</span><span class="sxs-lookup"><span data-stu-id="4c764-128">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA.</span></span> <span data-ttu-id="4c764-129">O certificado é necessário.</span><span class="sxs-lookup"><span data-stu-id="4c764-129">The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

