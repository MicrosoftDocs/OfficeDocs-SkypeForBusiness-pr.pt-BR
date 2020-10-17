---
title: 'Lync Server 2013: Resumo de certificado-balanceamento de carga DNS e HLB'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - DNS and HLB load balanced
ms:assetid: 8318a1a4-b423-47b7-95e6-9541adfad391
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205047(v=OCS.15)
ms:contentKeyID: 48184676
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 743818f81f5083e9c5d3a7877d2518d05176a5e7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499288"
---
# <a name="certificate-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="4a155-102">Resumo de certificado-carga de DNS e HLB balanceada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a155-102">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a155-103">_**Última modificação do tópico:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="4a155-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="4a155-104">Os requisitos de certificado para um diretor com balanceamento de carga DNS e um balanceador de carga de hardware usarão um certificado padrão que tem um nome de entidade e nomes alternativos de entidade para serviços que o diretor pode receber.</span><span class="sxs-lookup"><span data-stu-id="4a155-104">Certificate requirements for a Director with DNS load balancing and a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="4a155-105">Um certificado é solicitado para cada diretor no pool.</span><span class="sxs-lookup"><span data-stu-id="4a155-105">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="4a155-106">É importante lembrar que o balanceador de carga de hardware equilibra somente o tráfego do proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="4a155-106">It is important to remember that the hardware load balancer is load balancing only the traffic from the reverse proxy.</span></span> <span data-ttu-id="4a155-107">Ademais, há um certificado OAuth Token para fins de autenticação entre servidores instalado em cada servidor.</span><span class="sxs-lookup"><span data-stu-id="4a155-107">Additionally, there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="4a155-108">Certificados para Diretor</span><span class="sxs-lookup"><span data-stu-id="4a155-108">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4a155-109">Componente</span><span class="sxs-lookup"><span data-stu-id="4a155-109">Component</span></span></th>
<th><span data-ttu-id="4a155-110">Nome da entidade (SN)</span><span class="sxs-lookup"><span data-stu-id="4a155-110">Subject name (SN)</span></span></th>
<th><span data-ttu-id="4a155-111">SAN (nomes alternativos da entidade)</span><span class="sxs-lookup"><span data-stu-id="4a155-111">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="4a155-112">Comments</span><span class="sxs-lookup"><span data-stu-id="4a155-112">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a155-113">Padrão</span><span class="sxs-lookup"><span data-stu-id="4a155-113">Default</span></span></p></td>
<td><p><span data-ttu-id="4a155-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="4a155-114">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="4a155-115">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="4a155-115">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="4a155-116">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="4a155-116">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="4a155-117">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4a155-117">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="4a155-118">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4a155-118">meet.contoso.com</span></span></p>
<p><span data-ttu-id="4a155-119">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4a155-119">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="4a155-120">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4a155-120">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="4a155-121">(Opcional) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4a155-121">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4a155-122">Os certificados do diretor podem ser solicitados de uma CA (autoridade de certificação) gerenciada internamente ou de uma AC pública.</span><span class="sxs-lookup"><span data-stu-id="4a155-122">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="4a155-123">O diretor responde às solicitações do proxy reverso no perímetro ou do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="4a155-123">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="4a155-124">Os clientes internos não usarão o diretor.</span><span class="sxs-lookup"><span data-stu-id="4a155-124">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="4a155-125">Ou uma entrada curinga para os URLs simples</span><span class="sxs-lookup"><span data-stu-id="4a155-125">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a155-126">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="4a155-126">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="4a155-127">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="4a155-127">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="4a155-128">Nenhuma entrada</span><span class="sxs-lookup"><span data-stu-id="4a155-128">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="4a155-129">Observe que o comprimento mínimo de chave é 1024, mas você pode receber um aviso de que o comprimento de chave mínimo recomendado é 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="4a155-129">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="4a155-p103">O certificado OAuthTokenIssuer é um certificado para o fim único de autenticar servidores em um ambiente de grande escala e pode ser solicitado de um CA interno ou público. O certificado é exigido.</span><span class="sxs-lookup"><span data-stu-id="4a155-p103">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

