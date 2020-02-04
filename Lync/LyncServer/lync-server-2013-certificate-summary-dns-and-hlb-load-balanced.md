---
title: 'Lync Server 2013: Resumo de certificado - Cargas de DNS e de HLB balanceadas'
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
ms.openlocfilehash: b8cd6d86844629544b54670eb07c3433d19f99f2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736651"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="f9ace-102">Resumo de certificado - Cargas de DNS e de HLB balanceadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9ace-102">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9ace-103">_**Tópico da última modificação:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="f9ace-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="f9ace-104">Os requisitos de certificado para um diretor com balanceamento de carga de DNS e um balanceador de carga de hardware usarão um certificado padrão com um nome de assunto e nomes alternativos de entidades para os serviços que o diretor pode receber.</span><span class="sxs-lookup"><span data-stu-id="f9ace-104">Certificate requirements for a Director with DNS load balancing and a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="f9ace-105">Um certificado é solicitado para cada diretor do pool.</span><span class="sxs-lookup"><span data-stu-id="f9ace-105">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="f9ace-106">É importante lembrar que o balanceador de carga de hardware é o balanceamento de carga somente do tráfego de proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="f9ace-106">It is important to remember that the hardware load balancer is load balancing only the traffic from the reverse proxy.</span></span> <span data-ttu-id="f9ace-107">Além disso, há um certificado de token OAuth para fins de autenticação do servidor para servidor que está instalado em cada servidor.</span><span class="sxs-lookup"><span data-stu-id="f9ace-107">Additionally, there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="f9ace-108">Certificados para o diretor</span><span class="sxs-lookup"><span data-stu-id="f9ace-108">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9ace-109">Componente</span><span class="sxs-lookup"><span data-stu-id="f9ace-109">Component</span></span></th>
<th><span data-ttu-id="f9ace-110">Nome da entidade (SN)</span><span class="sxs-lookup"><span data-stu-id="f9ace-110">Subject name (SN)</span></span></th>
<th><span data-ttu-id="f9ace-111">Nomes alternativos de entidades (SAN)</span><span class="sxs-lookup"><span data-stu-id="f9ace-111">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="f9ace-112">Comentários</span><span class="sxs-lookup"><span data-stu-id="f9ace-112">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9ace-113">Padrão</span><span class="sxs-lookup"><span data-stu-id="f9ace-113">Default</span></span></p></td>
<td><p><span data-ttu-id="f9ace-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f9ace-114">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="f9ace-115">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f9ace-115">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="f9ace-116">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f9ace-116">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="f9ace-117">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9ace-117">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="f9ace-118">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9ace-118">meet.contoso.com</span></span></p>
<p><span data-ttu-id="f9ace-119">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9ace-119">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="f9ace-120">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9ace-120">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="f9ace-121">(Opcionalmente) \*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9ace-121">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f9ace-122">Os certificados do diretor podem ser solicitados de uma CA (autoridade de certificação) gerenciada internamente ou de uma CA pública.</span><span class="sxs-lookup"><span data-stu-id="f9ace-122">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="f9ace-123">O diretor responde a solicitações do proxy reverso no perímetro ou do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="f9ace-123">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="f9ace-124">Os clientes internos não usarão o diretor.</span><span class="sxs-lookup"><span data-stu-id="f9ace-124">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="f9ace-125">Ou uma entrada curinga para as URLs simples</span><span class="sxs-lookup"><span data-stu-id="f9ace-125">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9ace-126">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="f9ace-126">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="f9ace-127">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f9ace-127">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="f9ace-128">Sem entrada</span><span class="sxs-lookup"><span data-stu-id="f9ace-128">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="f9ace-129">Observe que o tamanho mínimo da chave é 1024, mas você pode receber um aviso de que o tamanho mínimo recomendado da chave é 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="f9ace-129">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="f9ace-130">O certificado OAuthTokenIssuer é um certificado de finalidade única para a finalidade de autenticar servidores em um ambiente em larga escala e pode ser solicitado de uma CA interna ou de uma CA pública.</span><span class="sxs-lookup"><span data-stu-id="f9ace-130">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA.</span></span> <span data-ttu-id="f9ace-131">O certificado é necessário.</span><span class="sxs-lookup"><span data-stu-id="f9ace-131">The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

