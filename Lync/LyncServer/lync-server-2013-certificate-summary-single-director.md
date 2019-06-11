---
title: 'Lync Server 2013: Resumo do certificado - Diretor único'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Single Director
ms:assetid: 1b769a76-cbf3-46e9-a955-f6cde5faff93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204720(v=OCS.15)
ms:contentKeyID: 48183546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e44be0ca76a1926a1515657a9d7d5646a49390c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836622"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="8b78a-102">Resumo do certificado - Diretor único no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b78a-102">Certificate summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b78a-103">_**Tópico da última modificação:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="8b78a-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="8b78a-104">Os requisitos de certificado para um único diretor consistem em um certificado padrão que tem um nome de assunto e nomes alternativos de assunto para serviços que o diretor pode receber.</span><span class="sxs-lookup"><span data-stu-id="8b78a-104">Certificate requirements for a single Director consist of a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="8b78a-105">Além disso, há um certificado de token OAuth para fins de autenticação do servidor para servidor.</span><span class="sxs-lookup"><span data-stu-id="8b78a-105">Additionally, there is an OAuth Token certificate for server to server authentication purposes.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="8b78a-106">Certificados para o diretor</span><span class="sxs-lookup"><span data-stu-id="8b78a-106">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b78a-107">Componente</span><span class="sxs-lookup"><span data-stu-id="8b78a-107">Component</span></span></th>
<th><span data-ttu-id="8b78a-108">Nome da entidade (SN)</span><span class="sxs-lookup"><span data-stu-id="8b78a-108">Subject name (SN)</span></span></th>
<th><span data-ttu-id="8b78a-109">Nomes alternativos de entidades (SAN)</span><span class="sxs-lookup"><span data-stu-id="8b78a-109">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="8b78a-110">Comentários</span><span class="sxs-lookup"><span data-stu-id="8b78a-110">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b78a-111">Padrão</span><span class="sxs-lookup"><span data-stu-id="8b78a-111">Default</span></span></p></td>
<td><p><span data-ttu-id="8b78a-112">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="8b78a-112">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="8b78a-113">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="8b78a-113">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="8b78a-114">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b78a-114">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="8b78a-115">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b78a-115">meet.contoso.com</span></span></p>
<p><span data-ttu-id="8b78a-116">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b78a-116">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="8b78a-117">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b78a-117">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="8b78a-118">(Opcionalmente) \*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="8b78a-118">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8b78a-119">Os certificados do diretor podem ser solicitados de uma CA (autoridade de certificação) gerenciada internamente ou de uma CA pública.</span><span class="sxs-lookup"><span data-stu-id="8b78a-119">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="8b78a-120">O diretor responde a solicitações do proxy reverso no perímetro ou do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="8b78a-120">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="8b78a-121">Os clientes internos não usarão o diretor.</span><span class="sxs-lookup"><span data-stu-id="8b78a-121">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="8b78a-122">Ou uma entrada curinga para as URLs simples</span><span class="sxs-lookup"><span data-stu-id="8b78a-122">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b78a-123">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="8b78a-123">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="8b78a-124">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="8b78a-124">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="8b78a-125">Sem entrada</span><span class="sxs-lookup"><span data-stu-id="8b78a-125">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="8b78a-126">Observe que o tamanho mínimo da chave é 1024, mas você pode receber um aviso de que o tamanho mínimo recomendado da chave é 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="8b78a-126">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="8b78a-127">O certificado OAuthTokenIssuer é um certificado de finalidade única para a finalidade de autenticar servidores em um ambiente em larga escala e pode ser solicitado de uma CA interna ou de uma CA pública.</span><span class="sxs-lookup"><span data-stu-id="8b78a-127">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA.</span></span> <span data-ttu-id="8b78a-128">O certificado é necessário.</span><span class="sxs-lookup"><span data-stu-id="8b78a-128">The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

