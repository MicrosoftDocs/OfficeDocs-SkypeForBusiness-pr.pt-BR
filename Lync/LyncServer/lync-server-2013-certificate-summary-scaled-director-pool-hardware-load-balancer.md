---
title: Resumo de certificado-pool de diretores em escala, balanceador de carga de hardware
description: Resumo de certificado-pool de diretores em escala, balanceador de carga de hardware.
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
ms.openlocfilehash: 08abc37940cd41a29d6620cfc0a2a801de4a8e38
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572227"
---
# <a name="certificate-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="2c466-103">Resumo de certificado-pool de diretores em escala, balanceador de carga de hardware no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c466-103">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c466-104">_**Última modificação do tópico:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="2c466-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="2c466-105">Os requisitos de certificado para um diretor com um balanceador de carga de hardware usarão um certificado padrão que tenha um nome de entidade e nomes alternativos de entidade para serviços que o pool de diretor possa receber.</span><span class="sxs-lookup"><span data-stu-id="2c466-105">Certificate requirements for a Director with a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director pool can receive.</span></span> <span data-ttu-id="2c466-106">Um certificado é solicitado para cada diretor no pool.</span><span class="sxs-lookup"><span data-stu-id="2c466-106">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="2c466-107">Adicionalmente, há um certificado OAuth Token para propósitos de autenticação servidor para servidor que é instalado em cada servidor.</span><span class="sxs-lookup"><span data-stu-id="2c466-107">Additionally there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-a-scaled-director-using-a-hardware-load-balancer"></a><span data-ttu-id="2c466-108">Certificados para um Diretor escalado utilizando um balanceador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="2c466-108">Certificates for a Scaled Director Using a Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2c466-109">Componente</span><span class="sxs-lookup"><span data-stu-id="2c466-109">Component</span></span></th>
<th><span data-ttu-id="2c466-110">Nome da entidade (SN)</span><span class="sxs-lookup"><span data-stu-id="2c466-110">Subject name (SN)</span></span></th>
<th><span data-ttu-id="2c466-111">SAN (nomes alternativos da entidade)</span><span class="sxs-lookup"><span data-stu-id="2c466-111">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="2c466-112">Comments</span><span class="sxs-lookup"><span data-stu-id="2c466-112">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2c466-113">Padrão</span><span class="sxs-lookup"><span data-stu-id="2c466-113">Default</span></span></p></td>
<td><p><span data-ttu-id="2c466-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2c466-114">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="2c466-115">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2c466-115">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="2c466-116">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2c466-116">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="2c466-117">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2c466-117">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="2c466-118">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2c466-118">meet.contoso.com</span></span></p>
<p><span data-ttu-id="2c466-119">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2c466-119">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="2c466-120">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2c466-120">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="2c466-121">(Opcional) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2c466-121">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2c466-122">Os certificados do diretor podem ser solicitados de uma CA (autoridade de certificação) gerenciada internamente ou de uma AC pública.</span><span class="sxs-lookup"><span data-stu-id="2c466-122">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="2c466-123">O diretor responde às solicitações do proxy reverso no perímetro ou do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="2c466-123">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span></p>
<p><span data-ttu-id="2c466-124">Ou uma entrada curinga para os URLs simples</span><span class="sxs-lookup"><span data-stu-id="2c466-124">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c466-125">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="2c466-125">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="2c466-126">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2c466-126">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="2c466-127">Nenhuma entrada</span><span class="sxs-lookup"><span data-stu-id="2c466-127">No Entry</span></span></p></td>
<td>


> [!IMPORTANT]
> <span data-ttu-id="2c466-128">Observe que o comprimento mínimo de chave é 1024, mas você pode receber um aviso de que o comprimento de chave mínimo recomendado é 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="2c466-128">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


<p><span data-ttu-id="2c466-p102">O certificado OAuthTokenIssuer é um certificado para o fim único de autenticar servidores em um ambiente de grande escala e pode ser solicitado de um CA interno ou público. O certificado é exigido.</span><span class="sxs-lookup"><span data-stu-id="2c466-p102">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

