---
title: 'Lync Server 2013: Resumo de certificado-diretor único'
description: 'Lync Server 2013: Resumo de certificado-diretor único.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Single Director
ms:assetid: 1b769a76-cbf3-46e9-a955-f6cde5faff93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204720(v=OCS.15)
ms:contentKeyID: 48183546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cf930a73d9989ec44f52f1d70ee9e0f900e4d6f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572157"
---
# <a name="certificate-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="d5330-103">Resumo de certificado-diretor único no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5330-103">Certificate summary - Single Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5330-104">_**Última modificação do tópico:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="d5330-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="d5330-105">Os requisitos de certificado para um único diretor consistem em um certificado padrão que tem um nome de entidade e nomes alternativos de entidade para serviços que o diretor pode receber.</span><span class="sxs-lookup"><span data-stu-id="d5330-105">Certificate requirements for a single Director consist of a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="d5330-106">Além disso, há um certificado OAuth Token para fins de autenticação servidor para servidor.</span><span class="sxs-lookup"><span data-stu-id="d5330-106">Additionally, there is an OAuth Token certificate for server to server authentication purposes.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="d5330-107">Certificados para Diretor</span><span class="sxs-lookup"><span data-stu-id="d5330-107">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d5330-108">Componente</span><span class="sxs-lookup"><span data-stu-id="d5330-108">Component</span></span></th>
<th><span data-ttu-id="d5330-109">Nome da entidade (SN)</span><span class="sxs-lookup"><span data-stu-id="d5330-109">Subject name (SN)</span></span></th>
<th><span data-ttu-id="d5330-110">SAN (nomes alternativos da entidade)</span><span class="sxs-lookup"><span data-stu-id="d5330-110">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="d5330-111">Comments</span><span class="sxs-lookup"><span data-stu-id="d5330-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d5330-112">Padrão</span><span class="sxs-lookup"><span data-stu-id="d5330-112">Default</span></span></p></td>
<td><p><span data-ttu-id="d5330-113">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="d5330-113">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="d5330-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="d5330-114">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="d5330-115">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5330-115">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="d5330-116">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5330-116">meet.contoso.com</span></span></p>
<p><span data-ttu-id="d5330-117">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5330-117">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="d5330-118">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5330-118">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="d5330-119">(Opcional) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5330-119">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d5330-120">Os certificados do diretor podem ser solicitados de uma CA (autoridade de certificação) gerenciada internamente ou de uma AC pública.</span><span class="sxs-lookup"><span data-stu-id="d5330-120">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="d5330-121">O diretor responde às solicitações do proxy reverso no perímetro ou do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="d5330-121">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="d5330-122">Os clientes internos não usarão o diretor.</span><span class="sxs-lookup"><span data-stu-id="d5330-122">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="d5330-123">Ou uma entrada curinga para os URLs simples</span><span class="sxs-lookup"><span data-stu-id="d5330-123">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5330-124">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="d5330-124">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="d5330-125">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="d5330-125">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="d5330-126">Nenhuma entrada</span><span class="sxs-lookup"><span data-stu-id="d5330-126">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="d5330-127">Observe que o comprimento mínimo de chave é 1024, mas você pode receber um aviso de que o comprimento de chave mínimo recomendado é 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="d5330-127">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="d5330-p103">O certificado OAuthTokenIssuer é um certificado para o fim único de autenticar servidores em um ambiente de grande escala e pode ser solicitado de um CA interno ou público. O certificado é exigido.</span><span class="sxs-lookup"><span data-stu-id="d5330-p103">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

