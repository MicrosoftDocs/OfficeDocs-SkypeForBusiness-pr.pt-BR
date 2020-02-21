---
title: 'Lync Server 2013: Resumo de certificado-conectividade de mensagens instantâneas públicas'
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
ms.openlocfilehash: 3cacf411f348199376e1564be37f683854480872
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="4d0f1-102">Resumo de certificado-conectividade de mensagens instantâneas públicas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d0f1-102">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d0f1-103">_**Última modificação do tópico:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="4d0f1-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="4d0f1-104">Para configurar certificados para conectividade de mensagens instantâneas públicas, você deve primeiro observar que não há nada diferente de outros tipos de Federação SIP ou mesmo de certificados de servidor de borda padrão, exceto que America Online (AOL) requer um único configuração de certificado.</span><span class="sxs-lookup"><span data-stu-id="4d0f1-104">To configure certificates for public Instant Messaging connectivity, you should first notice that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a unique certificate configuration.</span></span> <span data-ttu-id="4d0f1-105">Além do uso avançado de chave (EKU) do servidor usual, a America Online requer que o certificado ou certificados (no caso de um pool de borda) também contenham o EKU do cliente.</span><span class="sxs-lookup"><span data-stu-id="4d0f1-105">In addition to the usual server enhanced key usage (EKU), America Online requires the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="4d0f1-106">O EKU do cliente é uma adição ao certificado e faz parte do certificado público externo atribuído ao servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="4d0f1-106">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="4d0f1-107">Resumo do certificado – Conectividade de mensagem instantânea pública</span><span class="sxs-lookup"><span data-stu-id="4d0f1-107">Certificate Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d0f1-108">Componente</span><span class="sxs-lookup"><span data-stu-id="4d0f1-108">Component</span></span></th>
<th><span data-ttu-id="4d0f1-109">Nome da entidade</span><span class="sxs-lookup"><span data-stu-id="4d0f1-109">Subject name</span></span></th>
<th><span data-ttu-id="4d0f1-110">Nomes alternativos de entidade (SAN)/Ordem</span><span class="sxs-lookup"><span data-stu-id="4d0f1-110">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="4d0f1-111">Comentários</span><span class="sxs-lookup"><span data-stu-id="4d0f1-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d0f1-112">Borda de Acesso/Externo</span><span class="sxs-lookup"><span data-stu-id="4d0f1-112">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="4d0f1-113">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4d0f1-113">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4d0f1-114">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4d0f1-114">sip.contoso.com</span></span></p>
<p><span data-ttu-id="4d0f1-115">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4d0f1-115">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="4d0f1-116">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="4d0f1-116">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="4d0f1-117">O certificado deve ser de uma autoridade de certificação pública e deve ter o EKU do servidor e o EKU do cliente se a conectividade de IM pública com AOL for implantada.</span><span class="sxs-lookup"><span data-stu-id="4d0f1-117">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="4d0f1-118">O certificado é atribuído às interfaces do servidor de borda externo para:</span><span class="sxs-lookup"><span data-stu-id="4d0f1-118">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="4d0f1-119">Serviço de Borda de Acesso</span><span class="sxs-lookup"><span data-stu-id="4d0f1-119">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="4d0f1-120">Web Conferencing Edge service</span><span class="sxs-lookup"><span data-stu-id="4d0f1-120">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="4d0f1-121">serviço de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="4d0f1-121">A/V Edge service</span></span></p></li>
</ul>
<p><span data-ttu-id="4d0f1-p103">Observe que os SANs são adicionados automaticamente ao certificado com base nas suas definições no Construtor de Topologia. É possível adicionar entradas SAN conforme necessário para domínios SIP adicionais e outras enteadas que precisam de suporte. O nome do assunto é replicado no SAN e deve estar presente para a operação correta.</span><span class="sxs-lookup"><span data-stu-id="4d0f1-p103">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder. You add SAN entries as needed for additional SIP domains and other entries that you need to support. The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4d0f1-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="4d0f1-125">See Also</span></span>


[<span data-ttu-id="4d0f1-126">Cenários para acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d0f1-126">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

