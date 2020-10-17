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
ms.openlocfilehash: bdc4bba8064332d7fa3f90d0d6a3d4b9f6cef9e6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512778"
---
# <a name="certificate-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="18ab9-102">Resumo de certificado-conectividade de mensagens instantâneas públicas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18ab9-102">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18ab9-103">_**Última modificação do tópico:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="18ab9-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="18ab9-104">Para configurar certificados para conectividade de mensagens instantâneas públicas, você deve primeiro observar que não há nada diferente de outros tipos de Federação SIP ou mesmo de certificados de servidor de borda padrão, exceto que America Online (AOL) requer uma configuração de certificado exclusiva.</span><span class="sxs-lookup"><span data-stu-id="18ab9-104">To configure certificates for public Instant Messaging connectivity, you should first notice that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a unique certificate configuration.</span></span> <span data-ttu-id="18ab9-105">Além do uso avançado de chave (EKU) do servidor usual, a America Online requer que o certificado ou certificados (no caso de um pool de borda) também contenham o EKU do cliente.</span><span class="sxs-lookup"><span data-stu-id="18ab9-105">In addition to the usual server enhanced key usage (EKU), America Online requires the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="18ab9-106">O EKU do cliente é uma adição ao certificado e faz parte do certificado público externo atribuído ao servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="18ab9-106">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="18ab9-107">Resumo do certificado – Conectividade de mensagem instantânea pública</span><span class="sxs-lookup"><span data-stu-id="18ab9-107">Certificate Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="18ab9-108">Componente</span><span class="sxs-lookup"><span data-stu-id="18ab9-108">Component</span></span></th>
<th><span data-ttu-id="18ab9-109">Nome da entidade</span><span class="sxs-lookup"><span data-stu-id="18ab9-109">Subject name</span></span></th>
<th><span data-ttu-id="18ab9-110">Nomes alternativos de entidade (SAN)/Ordem</span><span class="sxs-lookup"><span data-stu-id="18ab9-110">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="18ab9-111">Comments</span><span class="sxs-lookup"><span data-stu-id="18ab9-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18ab9-112">Borda de Acesso/Externo</span><span class="sxs-lookup"><span data-stu-id="18ab9-112">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="18ab9-113">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="18ab9-113">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="18ab9-114">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="18ab9-114">sip.contoso.com</span></span></p>
<p><span data-ttu-id="18ab9-115">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="18ab9-115">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="18ab9-116">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="18ab9-116">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="18ab9-117">O certificado deve ser de uma autoridade de certificação pública e deve ter o EKU do servidor e o EKU do cliente se a conectividade de IM pública com AOL for implantada.</span><span class="sxs-lookup"><span data-stu-id="18ab9-117">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="18ab9-118">O certificado é atribuído às interfaces do servidor de borda externo para:</span><span class="sxs-lookup"><span data-stu-id="18ab9-118">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="18ab9-119">Serviço de Borda de Acesso</span><span class="sxs-lookup"><span data-stu-id="18ab9-119">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="18ab9-120">Web Conferencing Edge service</span><span class="sxs-lookup"><span data-stu-id="18ab9-120">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="18ab9-121">serviço de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="18ab9-121">A/V Edge service</span></span></p></li>
</ul>
<p><span data-ttu-id="18ab9-p103">Observe que os SANs são adicionados automaticamente ao certificado com base nas suas definições no Construtor de Topologia. É possível adicionar entradas SAN conforme necessário para domínios SIP adicionais e outras enteadas que precisam de suporte. O nome do assunto é replicado no SAN e deve estar presente para a operação correta.</span><span class="sxs-lookup"><span data-stu-id="18ab9-p103">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder. You add SAN entries as needed for additional SIP domains and other entries that you need to support. The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="18ab9-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="18ab9-125">See Also</span></span>


[<span data-ttu-id="18ab9-126">Cenários para acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18ab9-126">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

