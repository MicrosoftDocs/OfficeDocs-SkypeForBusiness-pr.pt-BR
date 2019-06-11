---
title: Resumo do certificado-SIP, Federação do XMPP e mensagens instantâneas públicas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 933d6351-cfa6-4432-b3ed-1aff3ac92065
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618372(v=OCS.15)
ms:contentKeyID: 49105659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6dccb46b9f2b6d934f1cd0960bb11a369fb585ad
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836623"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="f5010-102">Resumo do certificado-SIP, Federação do XMPP e mensagens instantâneas públicas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5010-102">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5010-103">_**Tópico da última modificação:** 2013-03-15_</span><span class="sxs-lookup"><span data-stu-id="f5010-103">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="f5010-104">Os certificados que você precisa para a Federação com o Microsoft Lync Server 2013, o Lync Server 2010 e o Office Communications Server normalmente serão atendidos pelos certificados que você configurar, solicitar e atribuir ao seu servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="f5010-104">The certificates that you need for federating with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server will typically be met by the certificates that you configure, request and assign to your Edge Server.</span></span>

<span data-ttu-id="f5010-105">Os requisitos de certificado para habilitar e estabelecer comunicações com os parceiros do protocolo de presença Extensible Messaging e de presença (XMPP) exigem a adição de entradas para seus domínios do XMPP.</span><span class="sxs-lookup"><span data-stu-id="f5010-105">Certificate requirements for enabling and establishing communications with extensible messaging and presence protocol (XMPP) partners require addition of entries for your XMPP domains.</span></span> <span data-ttu-id="f5010-106">O registro incluído no certificado como um nome alternativo de assunto (SAN) será o domínio que pode participar de comunicações XMPP.</span><span class="sxs-lookup"><span data-stu-id="f5010-106">The record that is included on the certificate as a subject alternative name (SAN) will be the domain that can participate in XMPP communications.</span></span> <span data-ttu-id="f5010-107">O domínio pode ser o domínio de nível raiz (por exemplo, contoso.com) se você quiser habilitar o XMPP para o seu domínio inteiro ou pode ser selecionado domínios filho (por exemplo, corp.contoso.com, finance.contoso.com) se você estiver habilitando XMPP para um subconjunto de usuários.</span><span class="sxs-lookup"><span data-stu-id="f5010-107">The domain can be the root-level domain (for example, contoso.com) if you want to enable XMPP for your entire domain, or can be selected child domains (for example, corp.contoso.com, finance.contoso.com) if you are enabling XMPP for a subset of users.</span></span>

<span data-ttu-id="f5010-108">Para configurar certificados para conectividade de mensagens instantâneas públicas, observe que não há nada diferente de outros tipos de Federação SIP ou até mesmo dos certificados de servidor de borda padrão, exceto que o America Online (AOL) requer um certificado ou certificados (em o caso de um pool de bordas) também contenha o EKU do cliente.</span><span class="sxs-lookup"><span data-stu-id="f5010-108">To configure certificates for public Instant Messaging connectivity, note that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="f5010-109">O EKU do cliente é uma adição ao certificado e faz parte do certificado público externo atribuído ao seu servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="f5010-109">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<span data-ttu-id="f5010-110">Para confirmar que você atendeu aos requisitos de certificado corretos para a implantação do servidor de borda, revise os tópicos listados na seção intitulada **Consulte também**.</span><span class="sxs-lookup"><span data-stu-id="f5010-110">To confirm that you have met the correct certificate requirements for your Edge Server deployment, review the topics listed in the section titled **See Also**.</span></span>

<div>



<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5010-111">Componente</span><span class="sxs-lookup"><span data-stu-id="f5010-111">Component</span></span></th>
<th><span data-ttu-id="f5010-112">Nome do assunto</span><span class="sxs-lookup"><span data-stu-id="f5010-112">Subject name</span></span></th>
<th><span data-ttu-id="f5010-113">Nomes alternativos de entidades (SAN)</span><span class="sxs-lookup"><span data-stu-id="f5010-113">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="f5010-114">Comentários</span><span class="sxs-lookup"><span data-stu-id="f5010-114">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5010-115">Borda externa/de acesso</span><span class="sxs-lookup"><span data-stu-id="f5010-115">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="f5010-116">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5010-116">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f5010-117">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5010-117">sip.contoso.com</span></span></p>
<p><span data-ttu-id="f5010-118">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5010-118">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="f5010-119">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5010-119">contoso.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="f5010-120">Para dar suporte ao namespace contoso.com XMPP</span><span class="sxs-lookup"><span data-stu-id="f5010-120">To support the contoso.com XMPP namespace</span></span>


<p><span data-ttu-id="f5010-121">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="f5010-121">sip.fabrikam.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="f5010-122">Para dar suporte ao namespace SIP fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="f5010-122">To support the fabrikam.com SIP namespace</span></span>


<p><span data-ttu-id="f5010-123">fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="f5010-123">fabrikam.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="f5010-124">Para dar suporte ao namespace fabrikam.com XMPP</span><span class="sxs-lookup"><span data-stu-id="f5010-124">To support the fabrikam.com XMPP namespace</span></span>

</td>
<td><p><span data-ttu-id="f5010-125">O certificado deve ser de uma CA pública e deve ter o EKU do servidor e o cliente EKU se a conectividade de IM pública com AOL for implantada.</span><span class="sxs-lookup"><span data-stu-id="f5010-125">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="f5010-126">O certificado é atribuído às interfaces do servidor de borda externo para:</span><span class="sxs-lookup"><span data-stu-id="f5010-126">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="f5010-127">Serviço de Borda de Acesso</span><span class="sxs-lookup"><span data-stu-id="f5010-127">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="f5010-128">Serviço de Borda de Webconferência</span><span class="sxs-lookup"><span data-stu-id="f5010-128">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="f5010-129">Serviço de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="f5010-129">A/V Edge service</span></span></p></li>
</ul>



> [!NOTE]
> <span data-ttu-id="f5010-130">Tecnicamente, um certificado não é atribuído à borda A/V.</span><span class="sxs-lookup"><span data-stu-id="f5010-130">Technically, a certificate is not assigned to the A/V Edge.</span></span> <span data-ttu-id="f5010-131">A comunicação e a autenticação seguras são gerenciadas por meio do serviço de autenticação de retransmissão de mídia (MRAS).</span><span class="sxs-lookup"><span data-stu-id="f5010-131">Secure communication and authentication is managed by way of the Media Relay Authentication Service (MRAS).</span></span> <span data-ttu-id="f5010-132">O MRAS usa o certificado atribuído à interface interna do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="f5010-132">MRAS uses the certificate assigned to the Edge Server internal interface.</span></span>


<p><span data-ttu-id="f5010-133">Observe que as SANs são adicionadas automaticamente ao certificado com base em suas definições no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="f5010-133">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder.</span></span> <span data-ttu-id="f5010-134">Você adiciona entradas de SAN conforme necessário para domínios SIP adicionais e outras entradas de que você precisa para dar suporte.</span><span class="sxs-lookup"><span data-stu-id="f5010-134">You add SAN entries as needed for additional SIP domains and other entries that you need to support.</span></span> <span data-ttu-id="f5010-135">O nome do requerente é replicado na SAN e deve estar presente para a operação correta.</span><span class="sxs-lookup"><span data-stu-id="f5010-135">The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f5010-136">Confira também</span><span class="sxs-lookup"><span data-stu-id="f5010-136">See Also</span></span>


[<span data-ttu-id="f5010-137">Exemplo de configuração de XMPP no Lync Server 2013 – federação XMPP com Google Talk</span><span class="sxs-lookup"><span data-stu-id="f5010-137">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="f5010-138">Planejar certificados do Servidor de Borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5010-138">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  
[<span data-ttu-id="f5010-139">Resumo de certificado - única borda consolidada com endereços IP privados usando NAT no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5010-139">Certificate summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[<span data-ttu-id="f5010-140">Resumo de certificado - Única borda consolidada com endereços IP públicos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5010-140">Certificate summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[<span data-ttu-id="f5010-141">Resumo de certificado - borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5010-141">Certificate summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)  
[<span data-ttu-id="f5010-142">Resumo de certificado - Borda consolidade em escala, balanceamento de carga de DNS com endereços IP públicos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5010-142">Certificate summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[<span data-ttu-id="f5010-143">Resumo de certificado - Borda consolidada em escala com balanceadores de carga de hardware no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5010-143">Certificate summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

