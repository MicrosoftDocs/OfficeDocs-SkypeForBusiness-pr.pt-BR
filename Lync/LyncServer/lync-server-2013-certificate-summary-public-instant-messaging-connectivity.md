---
title: 'Lync Server 2013: Resumo do certificado-conectividade de mensagens instantâneas públicas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Public instant messaging connectivity
ms:assetid: 2b3687ee-50c2-4c1c-880e-8dcf8bd4f309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618370(v=OCS.15)
ms:contentKeyID: 49105657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c93e79eed643d608ac9ab04516222227fc7c1f6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="3847b-102">Resumo do certificado-conectividade de mensagens instantâneas públicas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3847b-102">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3847b-103">_**Tópico da última modificação:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="3847b-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="3847b-104">Para configurar certificados para conectividade de mensagens instantâneas públicas, primeiro você deve observar que não há nada diferente de outros tipos de Federação SIP ou até mesmo dos certificados de servidor de borda padrão, exceto que o America Online (AOL) requer um único configuração de certificado.</span><span class="sxs-lookup"><span data-stu-id="3847b-104">To configure certificates for public Instant Messaging connectivity, you should first notice that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a unique certificate configuration.</span></span> <span data-ttu-id="3847b-105">Além do uso de chave avançada (EKU) do servidor usual, a America Online exige que o certificado ou certificados (no caso de um pool de bordas) também contenham o EKU do cliente.</span><span class="sxs-lookup"><span data-stu-id="3847b-105">In addition to the usual server enhanced key usage (EKU), America Online requires the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="3847b-106">O EKU do cliente é uma adição ao certificado e faz parte do certificado público externo atribuído ao seu servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="3847b-106">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="3847b-107">Resumo do certificado – conectividade de mensagens instantâneas públicas</span><span class="sxs-lookup"><span data-stu-id="3847b-107">Certificate Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3847b-108">Componente</span><span class="sxs-lookup"><span data-stu-id="3847b-108">Component</span></span></th>
<th><span data-ttu-id="3847b-109">Nome do assunto</span><span class="sxs-lookup"><span data-stu-id="3847b-109">Subject name</span></span></th>
<th><span data-ttu-id="3847b-110">Nomes alternativos de assunto (SAN)/Order</span><span class="sxs-lookup"><span data-stu-id="3847b-110">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="3847b-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="3847b-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3847b-112">Borda externa/de acesso</span><span class="sxs-lookup"><span data-stu-id="3847b-112">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="3847b-113">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3847b-113">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="3847b-114">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3847b-114">sip.contoso.com</span></span></p>
<p><span data-ttu-id="3847b-115">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3847b-115">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="3847b-116">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="3847b-116">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="3847b-117">O certificado deve ser de uma CA pública e deve ter o EKU do servidor e o cliente EKU se a conectividade de IM pública com AOL for implantada.</span><span class="sxs-lookup"><span data-stu-id="3847b-117">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="3847b-118">O certificado é atribuído às interfaces do servidor de borda externo para:</span><span class="sxs-lookup"><span data-stu-id="3847b-118">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="3847b-119">Serviço de Borda de Acesso</span><span class="sxs-lookup"><span data-stu-id="3847b-119">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="3847b-120">Serviço de Borda de Webconferência</span><span class="sxs-lookup"><span data-stu-id="3847b-120">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="3847b-121">Serviço de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="3847b-121">A/V Edge service</span></span></p></li>
</ul>
<p><span data-ttu-id="3847b-122">Observe que as SANs são adicionadas automaticamente ao certificado com base em suas definições no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="3847b-122">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder.</span></span> <span data-ttu-id="3847b-123">Você adiciona entradas de SAN conforme necessário para domínios SIP adicionais e outras entradas de que você precisa para dar suporte.</span><span class="sxs-lookup"><span data-stu-id="3847b-123">You add SAN entries as needed for additional SIP domains and other entries that you need to support.</span></span> <span data-ttu-id="3847b-124">O nome do requerente é replicado na SAN e deve estar presente para a operação correta.</span><span class="sxs-lookup"><span data-stu-id="3847b-124">The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3847b-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="3847b-125">See Also</span></span>


[<span data-ttu-id="3847b-126">Cenários de acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3847b-126">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

