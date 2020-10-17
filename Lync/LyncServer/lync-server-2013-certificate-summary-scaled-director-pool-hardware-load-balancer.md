---
title: Resumo de certificado-pool de diretores em escala, balanceador de carga de hardware
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Scaled Director pool, hardware load balancer
ms:assetid: 45940add-8027-418d-b79a-9033b494762f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204846(v=OCS.15)
ms:contentKeyID: 48183992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c08fb5710e25bf4504d7cb2d10020138221b22c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507918"
---
# <a name="certificate-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="b21a8-102">Resumo de certificado-pool de diretores em escala, balanceador de carga de hardware no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b21a8-102">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b21a8-103">_**Última modificação do tópico:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="b21a8-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="b21a8-104">Os requisitos de certificado para um diretor com um balanceador de carga de hardware usarão um certificado padrão que tenha um nome de entidade e nomes alternativos de entidade para serviços que o pool de diretor possa receber.</span><span class="sxs-lookup"><span data-stu-id="b21a8-104">Certificate requirements for a Director with a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director pool can receive.</span></span> <span data-ttu-id="b21a8-105">Um certificado é solicitado para cada diretor no pool.</span><span class="sxs-lookup"><span data-stu-id="b21a8-105">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="b21a8-106">Adicionalmente, há um certificado OAuth Token para propósitos de autenticação servidor para servidor que é instalado em cada servidor.</span><span class="sxs-lookup"><span data-stu-id="b21a8-106">Additionally there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-a-scaled-director-using-a-hardware-load-balancer"></a><span data-ttu-id="b21a8-107">Certificados para um Diretor escalado utilizando um balanceador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="b21a8-107">Certificates for a Scaled Director Using a Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b21a8-108">Componente</span><span class="sxs-lookup"><span data-stu-id="b21a8-108">Component</span></span></th>
<th><span data-ttu-id="b21a8-109">Nome da entidade (SN)</span><span class="sxs-lookup"><span data-stu-id="b21a8-109">Subject name (SN)</span></span></th>
<th><span data-ttu-id="b21a8-110">SAN (nomes alternativos da entidade)</span><span class="sxs-lookup"><span data-stu-id="b21a8-110">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="b21a8-111">Comments</span><span class="sxs-lookup"><span data-stu-id="b21a8-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b21a8-112">Padrão</span><span class="sxs-lookup"><span data-stu-id="b21a8-112">Default</span></span></p></td>
<td><p><span data-ttu-id="b21a8-113">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="b21a8-113">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="b21a8-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="b21a8-114">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="b21a8-115">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="b21a8-115">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="b21a8-116">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b21a8-116">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="b21a8-117">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b21a8-117">meet.contoso.com</span></span></p>
<p><span data-ttu-id="b21a8-118">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b21a8-118">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="b21a8-119">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b21a8-119">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="b21a8-120">(Opcional) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b21a8-120">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b21a8-121">Os certificados do diretor podem ser solicitados de uma CA (autoridade de certificação) gerenciada internamente ou de uma AC pública.</span><span class="sxs-lookup"><span data-stu-id="b21a8-121">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="b21a8-122">O diretor responde às solicitações do proxy reverso no perímetro ou do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="b21a8-122">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span></p>
<p><span data-ttu-id="b21a8-123">Ou uma entrada curinga para os URLs simples</span><span class="sxs-lookup"><span data-stu-id="b21a8-123">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b21a8-124">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="b21a8-124">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="b21a8-125">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="b21a8-125">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="b21a8-126">Nenhuma entrada</span><span class="sxs-lookup"><span data-stu-id="b21a8-126">No Entry</span></span></p></td>
<td>


> [!IMPORTANT]
> <span data-ttu-id="b21a8-127">Observe que o comprimento mínimo de chave é 1024, mas você pode receber um aviso de que o comprimento de chave mínimo recomendado é 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="b21a8-127">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


<p><span data-ttu-id="b21a8-p102">O certificado OAuthTokenIssuer é um certificado para o fim único de autenticar servidores em um ambiente de grande escala e pode ser solicitado de um CA interno ou público. O certificado é exigido.</span><span class="sxs-lookup"><span data-stu-id="b21a8-p102">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

